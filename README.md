# Simulacro Examen Parcial 1 - José Zorrilla
Repositorio destinado para la entrega del Simulacro Examen Parcial 1 - Redes

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

