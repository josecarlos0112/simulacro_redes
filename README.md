# Simulacro Examen Parcial 1 - José Zorrilla
Repositorio destinado para la entrega del Simulacro Examen Parcial 1 - Redes
https://github.com/josecarlos0112/simulacro_redes.git

## Parte I: Conceptos y Teoría

---

### **Pregunta 1: Modelos OSI y TCP/IP**

#### a) Diferencias entre el modelo OSI y el modelo TCP/IP

| Característica      | Modelo OSI                                             | Modelo TCP/IP                                |
|---------------------|--------------------------------------------------------|----------------------------------------------|
| Número de capas     | 7 capas                                                | 4 capas                                      |
| Orientación         | Teórica, académica                                     | Práctica, basada en protocolos reales        |
| Capa de Aplicación  | Aplicación, Presentación y Sesión                      | Solo una capa de Aplicación                  |
| Desarrollo          | Desarrollado por la ISO                                | Departamento de Defensa de EE.UU.            |
| Uso actual          | Referencial y educativo                                | Usado en Internet                            |

#### b) Ventajas y limitaciones de los modelos

| Modelo   | Ventajas                                                             | Limitaciones                                                |
|----------|----------------------------------------------------------------------|-------------------------------------------------------------|
| OSI      | - Buen marco teórico para entender redes<br>- Estructura modular    | - No implementado completamente<br>- Separación ineficiente |
| TCP/IP   | - Basado en estándares reales<br>- Altamente adoptado               | - No separa bien presentación/sesión<br>- Menos claridad     |

---

### **Pregunta 2: Función de la Capa de Transporte**

La capa de transporte provee comunicación **confiable o no confiable** entre procesos. Se encarga de:

- Segmentación y reensamblaje de los datos.
- Control de flujo y errores.
- Multiplexación de aplicaciones.

**Modelo OSI:**  
Capa 4, puede usar **TCP** (confiable) o **UDP** (no confiable).

**Modelo TCP/IP:**  
Ubicada entre la capa de Aplicación e Internet.

**Garantía de entrega con TCP:**

- Establecimiento de conexión (3-way handshake).
- Confirmaciones (ACKs).
- Retransmisión de paquetes perdidos.
- Control de congestión.

**Protocolos comunes:**

- **TCP**: orientado a conexión, confiable.
- **UDP**: sin conexión, no confiable.

---

### **Pregunta 3: TCP vs. UDP**

| Característica              | TCP                                                       | UDP                                           |
|-----------------------------|------------------------------------------------------------|-----------------------------------------------|
| Orientación a conexión      | Sí (3-way handshake)                                       | No (datagramas)                               |
| Fiabilidad y control errores| Alta: ACKs, retransmisión, control de flujo/congestión    | Baja: sin garantía de entrega u orden         |
| Velocidad y orden de entrega| Más lento, garantiza orden                                | Más rápido, no garantiza orden                |
| Aplicaciones                | Navegadores (HTTP/HTTPS), Email (SMTP, IMAP), FTP         | Streaming, videollamadas, DNS, juegos online  |

---

### **Pregunta 4: Protocolo para Transferencia de Archivos**

#### a) Protocolo tradicional

**FTP (File Transfer Protocol)**: Protocolo clásico para la transferencia de archivos.

#### b) Alternativas y diferencias

1. **SFTP (SSH File Transfer Protocol):**
   - Usa **SSH** para conexión segura.
   - Cifra los datos.

2. **FTPS (FTP Secure):**
   - Extensión de FTP con **SSL/TLS**.
   - Usa mismos comandos que FTP pero con cifrado.

| Protocolo | Seguridad | Cifrado requerido | Basado en |
|-----------|-----------|-------------------|-----------|
| FTP       | Baja      | No                | TCP       |
| SFTP      | Alta      | Sí (SSH)          | SSH       |
| FTPS      | Alta      | Sí (SSL/TLS)      | FTP       |

---

### **Pregunta 5: Resolución de Nombres en DNS**

**Proceso detallado:**

1. El usuario escribe la URL (ej. `www.ejemplo.com`).
2. Se consulta la **caché local** del navegador/SO.
3. Si no está, se consulta al **servidor DNS configurado**.
4. Si no tiene la respuesta, realiza una **consulta jerárquica**:
   - **Servidores raíz** → indican los servidores TLD (`.com`, `.org`, etc.).
   - **Servidores TLD** → indican el servidor autoritativo del dominio.
   - **Servidor autoritativo** → responde con la dirección IP.
5. La IP se **almacena en caché** (según el TTL).
6. El navegador **establece conexión con el servidor web** usando la IP.

---

### **Pregunta 6: Comunicación en el Modelo TCP/IP**

El modelo TCP/IP tiene **4 capas**:

1. **Capa de Aplicación**
   - Genera y recibe datos de la aplicación (ej. navegador web).

2. **Capa de Transporte**
   - Segmenta los datos.
   - Asigna puertos (ej. 80 para HTTP).
   - Usa TCP/UDP para enviar los datos.

3. **Capa de Internet**
   - Encapsula en paquetes IP.
   - Añade direcciones IP de origen y destino.
   - Encaminamiento (routing).

4. **Capa de Acceso a Red (o Enlace)**
   - Convierte paquetes en tramas con dirección MAC.
   - Envía por medio físico (Ethernet, WiFi).
   - Verifica integridad y reensambla.

---

## Parte II: Capa Física y Ejercicios Prácticos

---

### **Pregunta 7: Cálculo de Tasa de Transmisión Máxima (Fórmula de Shannon)**

**Fórmula:**

C = B × log₂(1 + SNR)

**Datos:**
- Ancho de banda (B) = 500 MHz = 500 × 10⁶ Hz
- SNR (dB) = 20 dB

**Conversión de SNR a escala lineal:**
SNR (lineal) = 10^(SNR (dB) / 10) = 10^(20 / 10) = 100


**Cálculo de la capacidad:**
C = 500 × 10⁶ × log₂(1 + 100) C ≈ 500 × 10⁶ × 6.6582 C ≈ 3,329.1 × 10⁶ bps = 3.33 Gbps


**Resultado final:**  
**Tasa de transmisión máxima = 3.33 Gbps**

---

### **Pregunta 8: Ubicación de Portadoras para Eficiencia Espectral**

**Datos:**
- Primera portadora: 1.2 GHz
- Ancho de banda del canal: 300 MHz

**a) Portadora anterior:**
1.2 GHz - 300 MHz = 0.9 GHz

**b) Portadora posterior:**
1.2 GHz + 300 MHz = 1.5 GHz


**Importancia:**  
Evita interferencias entre canales y maximiza el uso del espectro, mejorando la eficiencia espectral.

---

### **Pregunta 9: Identificación de Modulación en Función del BER**

**Orden de robustez (mayor a menor):**

1. **BPSK**
2. **QPSK**
3. **16-QAM**
4. **64-QAM**
5. **256-QAM**

**Justificación:**  
A mayor número de símbolos, mayor eficiencia espectral, pero menor tolerancia al ruido. Por eso, BPSK es la más robusta y 256-QAM la más sensible.

---

### **Pregunta 10: Eficiencia del Sistema de Encapsulamiento**

**Datos:**
- Datos originales: 1.5 KB = 1536 bytes
- Cabeceras capas 4 y 3: 40 + 40 = 80 bytes
- Tamaño máximo de trama: 400 bytes
- Capa 1 añade 1 byte de inicio + 1 byte de parada + 1 byte de CRC por cada 2 bytes de datos

#### a) Tamaño del mensaje:
1536 + 80 = 1616 bytes

#### b) Número de tramas de 400 bytes:
Tramas necesarias = ceil(1616 / 400) = 5 tramas

#### c) Sobrecarga de la capa 1 por trama:
400 bytes de datos / 2 = 200 segmentos 200 segmentos × 3 bytes de sobrecarga = 600 bytes Total por trama = 400 + 600 = 1000 bytes

**Total transmitido (5 tramas):**  
5 × 1000 = 5000 bytes

#### d) Eficiencia del sistema:
Eficiencia = (Datos útiles / Total transmitido) × 100 = (1536 / 5000) × 100 ≈ 30.72%


**Resultado final:**  
**Eficiencia del sistema ≈ 30.72%**

---

## Ejercicio práctico en Cisco Packet Tracer

### 🖥️ Topología

- PC0 → Switch → PC1
- Switch conectado al Router0

### 🔌 Tipos de cable a utilizar

| Dispositivo origen | Dispositivo destino | Tipo de cable                        |
|--------------------|---------------------|--------------------------------------|
| PC0                | Switch0             | Cable directo (verde)                |
| PC1                | Switch0             | Cable directo (verde)                |
| Switch0            | Router0             | Cable cruzado (rojo)                 |

---
