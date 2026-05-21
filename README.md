![Version](https://img.shields.io/badge/version-1.0%20%7C%202.0-brightgreen)
![Python](https://img.shields.io/badge/python-3.x-blue)
![Platform](https://img.shields.io/badge/platform-Kali%20Linux-black)
![Uso](https://img.shields.io/badge/uso-autorizado-red)

# 🔐 Cryptom4n

**Cryptom4n** es una herramienta de escritorio desarrollada en Python para cifrar y descifrar archivos mediante contraseña. Su objetivo es proteger archivos sensibles usando algoritmos criptográficos robustos y una interfaz sencilla de utilizar.

El proyecto cuenta con dos versiones principales:

- **Cryptom4n v1.0**: primera versión con interfaz gráfica, basada en AES-256-CBC.
- **Cryptom4n v2.0**: versión mejorada con interfaz gráfica renovada, múltiples algoritmos de cifrado robusto, cifrado autenticado, detección automática del algoritmo y distribución como binario ELF para Linux.

---

## 📌 Versiones

## 🔐 Cryptom4n v1.0

Cryptom4n v1.0 es la primera versión estable del proyecto. Permite cifrar y descifrar archivos desde una interfaz gráfica simple construida con Tkinter.

### 🚀 Características principales

### 🔒 Cifrado principal

- **AES-256-CBC**: algoritmo de cifrado simétrico ampliamente utilizado.
- **PBKDF2-HMAC-SHA256**: derivación segura de claves a partir de una contraseña.
- **Modo CBC con IV aleatorio**: utiliza un vector de inicialización único por operación.
- **Padding PKCS7**: relleno adecuado para operaciones con cifradores de bloque.

### 🛡️ Características de seguridad

- Generación de clave basada en contraseña.
- Uso de salt aleatorio por cada operación de cifrado.
- Archivos cifrados con almacenamiento de salt e IV.
- Eliminación automática del archivo original después del cifrado.
- Protección mediante contraseña.

### 💻 Interfaz gráfica

- GUI intuitiva desarrollada con Tkinter.
- Selector de archivos.
- Logs en tiempo real con estilo terminal.
- Mensajes de estado visuales.
- Botón para limpiar campos y logs.

### 🔧 Detalles técnicos v1.0

```text
Algoritmo: AES-256-CBC
Derivación de clave: PBKDF2-HMAC-SHA256
Iteraciones: 100,000
Hash: SHA256
Salt: 16 bytes aleatorios
IV: 16 bytes aleatorios
Padding: PKCS7
Extensión cifrada: .encrypted
```

### 📁 Estructura del archivo cifrado v1.0

```text
Bytes 0-15: Salt
Bytes 16-31: IV
Bytes 32-final: Datos cifrados
```

---

## 🔐 Cryptom4n v2.0

Cryptom4n v2.0 es la versión mejorada del proyecto. Esta versión incorpora una interfaz gráfica, nuevos algoritmos criptográficos robustos y mecanismos de cifrado autenticado para proteger tanto la confidencialidad como la integridad de los archivos.

### ✨ Nuevas características

- Selector de algoritmo de cifrado.
- Soporte para múltiples algoritmos robustos.
- Detección automática del algoritmo durante el descifrado.
- Confirmación de contraseña antes de cifrar.
- Indicador de fuerza de contraseña.
- Opción para mostrar u ocultar la contraseña.
- Opción para eliminar el archivo original después de operar.
- Logs de operación en estilo terminal.
- Barra de progreso durante cifrado y descifrado.
- Cabecera personalizada para identificar versión y algoritmo.


### 🔒 Algoritmos soportados en v2.0

- **AES-256-GCM** — opción recomendada para uso general.
- **ChaCha20-Poly1305** — cifrado moderno, robusto y autenticado.
- **AES-128-GCM** — opción rápida y segura.
- **AES-192-GCM** — opción intermedia de AES.
- **AES-256-CCM** — alternativa robusta con cifrado autenticado.
- **AES-128-CCM** — cifrado autenticado con clave de 128 bits.

### 🛡️ Mejoras de seguridad v2.0

- Sustitución del enfoque AES-CBC por modos de cifrado autenticado.
- Uso de cifrado AEAD para proteger confidencialidad e integridad.
- Detección de contraseña incorrecta o archivo alterado.
- Derivación de claves con **PBKDF2-HMAC-SHA256 y 600,000 iteraciones**.
- Eliminación de métodos inseguros como XOR o cifrado simple.
- Detección automática del algoritmo desde la cabecera del archivo cifrado.

### 🔧 Detalles técnicos v2.0

```text
Algoritmo recomendado: AES-256-GCM
Algoritmos alternativos: ChaCha20-Poly1305, AES-GCM, AES-CCM
Derivación de clave: PBKDF2-HMAC-SHA256
Iteraciones: 600,000
Hash: SHA256
Tipo de cifrado: AEAD / cifrado autenticado
Cabecera personalizada: CM4N2
Extensión cifrada: .encrypted
```

---

## 📊 Comparación de versiones

| Característica | Cryptom4n v1.0 | Cryptom4n v2.0 |
|---|---|---|
| Interfaz gráfica | ✅ Sí | ✅ Mejorada |
| Selector de archivos | ✅ Sí | ✅ Sí |
| Logs de operación | ✅ Sí | ✅ Mejorados |
| AES-256-CBC | ✅ Sí | ❌ Reemplazado |
| AES-256-GCM | ❌ No | ✅ Sí |
| ChaCha20-Poly1305 | ❌ No | ✅ Sí |
| AES-CCM | ❌ No | ✅ Sí |
| Cifrado autenticado | ❌ No | ✅ Sí |
| Detección automática de algoritmo | ❌ No | ✅ Sí |
| Confirmación de contraseña | ❌ No | ✅ Sí |
| Indicador de fuerza de contraseña | ❌ No | ✅ Sí |
| Eliminación del archivo original | Automática | Opcional |
| Binario ELF para Linux | ✅ Sí | ✅ Sí |

---

## 📦 Instalación

### Requisitos

- Python 3.6 o superior.
- Paquete `cryptography`.
- Tkinter para la interfaz gráfica.

Instalar dependencia principal:

```bash
pip install cryptography
```

En Kali Linux, si falta Tkinter:

```bash
sudo apt install python3-tk
```

Si el entorno bloquea la instalación global de paquetes:

```bash
pip install cryptography --break-system-packages
```

---

## 🖥️ Ejecución

### Ejecutar desde Python

```bash
python3 cryptom4n.py
```

### Ejecutar binario ELF en Linux

Para v1.0:

```bash
chmod +x cryptom4n
./cryptom4n
```

Para v2.0, nombre recomendado del binario:

```text
cryptom4n-v2.0-linux-x64
```

Ejecución:

```bash
chmod +x cryptom4n-v2.0-linux-x64
./cryptom4n-v2.0-linux-x64
```

---

## 🎯 Uso

### 🔒 Proceso de cifrado

1. Selecciona el archivo usando el botón **Browse** o **Buscar**.
2. Ingresa una contraseña fuerte.
3. En v2.0, confirma la contraseña.
4. En v2.0, selecciona el algoritmo de cifrado.
5. Opcionalmente, marca la opción para eliminar el archivo original.
6. Haz clic en **Encrypt** o **Cifrar**.
7. Se generará un archivo con extensión `.encrypted`.

### 🔓 Proceso de descifrado

1. Selecciona un archivo con extensión `.encrypted`.
2. Ingresa la misma contraseña usada durante el cifrado.
3. Haz clic en **Decrypt** o **Descifrar**.
4. En v2.0, el algoritmo se detecta automáticamente.
5. El archivo original será restaurado.

---

## ⚠️ Consideraciones de seguridad

Ninguna herramienta de cifrado garantiza seguridad absoluta en todos los escenarios. Cryptom4n proporciona una protección sólida cuando se usa correctamente, pero la seguridad depende de la contraseña utilizada, del sistema donde se ejecuta y del manejo seguro de los archivos.

### Recomendaciones de contraseña

- Usa al menos 12 caracteres.
- Combina mayúsculas, minúsculas, números y símbolos.
- Evita palabras comunes, nombres o patrones predecibles.
- No reutilices contraseñas.
- Usa un gestor de contraseñas.

### Notas importantes

- Si olvidas la contraseña, el archivo cifrado no podrá recuperarse.
- Mantén copias de seguridad antes de cifrar archivos importantes.
- Ejecuta la herramienta solo en sistemas confiables.
- Antes de usarla con archivos críticos, valida primero el proceso de cifrado y descifrado.

---

## 🐛 Solución de problemas

### Archivo no encontrado

Verifica que la ruta del archivo sea correcta.

### Error al descifrar

Revisa que:

- La contraseña sea correcta.
- El archivo no haya sido modificado o dañado.
- El archivo tenga la extensión `.encrypted`.

### Error de permisos

Verifica que tengas permisos de lectura y escritura sobre el archivo o carpeta.

### Error de Tkinter en Linux

```bash
sudo apt install python3-tk
```

---

## 🛠️ Mejoras futuras

- Cifrado por lotes.
- Cifrado de carpetas.
- Soporte drag-and-drop.
- Selector de temas.
- Exportación de logs.
- Modo CLI integrado.
- Sobrescritura segura del archivo original.

---

## 👨‍💻 Autor

Creado por **Gh0s7m4n 💀**

---

## ⭐ Apoyo

Si este proyecto te resulta útil, puedes darle una estrella en GitHub.

```text
🔐 Recuerda: un gran poder de cifrado conlleva una gran responsabilidad.
```

---

# English Version

# 🔐 Cryptom4n

**Cryptom4n** is a desktop file encryption and decryption tool developed in Python. It is designed to protect sensitive files using password-based encryption and a simple graphical interface.

The project includes two main versions:

- **Cryptom4n v1.0**: first GUI version based on AES-256-CBC.
- **Cryptom4n v2.0**: improved GUI version with multiple robust encryption algorithms, authenticated encryption, automatic algorithm detection and Linux ELF distribution support.

---

## 📌 Versions

## 🔐 Cryptom4n v1.0

Cryptom4n v1.0 is the first stable graphical version of the project. It allows users to encrypt and decrypt files through a simple Tkinter-based interface.

### 🚀 Main Features

### 🔒 Core Encryption

- **AES-256-CBC**: widely used symmetric encryption algorithm.
- **PBKDF2-HMAC-SHA256**: secure key derivation from user passwords.
- **CBC Mode with Random IV**: uses a unique initialization vector for each encryption operation.
- **PKCS7 Padding**: proper padding for block cipher operations.

### 🛡️ Security Features

- Password-based key generation.
- Random salt for each encryption operation.
- Encrypted files store salt and IV for proper decryption.
- Automatic cleanup of the original file after encryption.
- Password protection.

### 💻 Graphical Interface

- Intuitive GUI built with Tkinter.
- File browser for easy file selection.
- Real-time terminal-style logs.
- Visual status messages.
- Button to clear fields and logs.

### 🔧 Technical Details v1.0

```text
Algorithm: AES-256-CBC
Key Derivation: PBKDF2-HMAC-SHA256
Iterations: 100,000
Hash: SHA256
Salt: 16 random bytes
IV: 16 random bytes
Padding: PKCS7
Encrypted extension: .encrypted
```

### 📁 Encrypted File Structure v1.0

```text
Bytes 0-15: Salt
Bytes 16-31: IV
Bytes 32-end: Encrypted data
```

---

## 🔐 Cryptom4n v2.0

Cryptom4n v2.0 is the improved version of the project. multiple robust encryption algorithms and authenticated encryption mechanisms to protect both confidentiality and integrity.

### ✨ New Features

- Encryption algorithm selector.
- Support for multiple robust algorithms.
- Automatic algorithm detection during decryption.
- Password confirmation before encryption.
- Password strength indicator.
- Option to show or hide the password.
- Option to delete the original file after encryption or decryption.
- Terminal-style operation logs.
- Progress bar during encryption and decryption.
- Custom header to identify version and algorithm.

### 🔒 Supported Algorithms in v2.0

- **AES-256-GCM** — recommended option for general use.
- **ChaCha20-Poly1305** — modern, robust and authenticated encryption.
- **AES-128-GCM** — fast and secure option.
- **AES-192-GCM** — intermediate AES key size option.
- **AES-256-CCM** — robust authenticated encryption alternative.
- **AES-128-CCM** — authenticated encryption with a 128-bit key.

### 🛡️ Security Improvements in v2.0

- Replaced AES-CBC with authenticated encryption modes.
- Added AEAD encryption to protect confidentiality and integrity.
- Added detection for wrong passwords or modified files.
- Improved key derivation using **PBKDF2-HMAC-SHA256 with 600,000 iterations**.
- Removed insecure fallback methods such as XOR or simple encryption.
- Automatic algorithm detection from the encrypted file header.

### 🔧 Technical Details v2.0

```text
Recommended Algorithm: AES-256-GCM
Alternative Algorithms: ChaCha20-Poly1305, AES-GCM, AES-CCM
Key Derivation: PBKDF2-HMAC-SHA256
Iterations: 600,000
Hash: SHA256
Encryption Type: AEAD / authenticated encryption
Custom Header: CM4N2
Encrypted extension: .encrypted
```

---

## 📊 Version Comparison

| Feature | Cryptom4n v1.0 | Cryptom4n v2.0 |
|---|---|---|
| Graphical interface | ✅ Yes | ✅ Improved |
| File browser | ✅ Yes | ✅ Yes |
| Operation logs | ✅ Yes | ✅ Improved |
| AES-256-CBC | ✅ Yes | ❌ Replaced |
| AES-256-GCM | ❌ No | ✅ Yes |
| ChaCha20-Poly1305 | ❌ No | ✅ Yes |
| AES-CCM | ❌ No | ✅ Yes |
| Authenticated encryption | ❌ No | ✅ Yes |
| Automatic algorithm detection | ❌ No | ✅ Yes |
| Password confirmation | ❌ No | ✅ Yes |
| Password strength indicator | ❌ No | ✅ Yes |
| Original file deletion | Automatic | Optional |
| Linux ELF binary | ✅ Yes | ✅ Yes |

---

## 📦 Installation

### Requirements

- Python 3.6 or higher.
- `cryptography` package.
- Tkinter for the graphical interface.

Install the main dependency:

```bash
pip install cryptography
```

On Kali Linux, if Tkinter is missing:

```bash
sudo apt install python3-tk
```

If your environment blocks global Python package installation:

```bash
pip install cryptography --break-system-packages
```

---

## 🖥️ Running the Application

### Run from Python

```bash
python3 cryptom4n.py
```

### Run Linux ELF Binary

For v1.0:

```bash
chmod +x cryptom4n
./cryptom4n
```

For v2.0, recommended binary name:

```text
cryptom4n-v2.0-linux-x64
```

Execution:

```bash
chmod +x cryptom4n-v2.0-linux-x64
./cryptom4n-v2.0-linux-x64
```

---

## 🎯 Usage

### 🔒 Encryption Process

1. Select the file using **Browse** or **Buscar**.
2. Enter a strong password.
3. In v2.0, confirm the password.
4. In v2.0, select the encryption algorithm.
5. Optionally enable deletion of the original file.
6. Click **Encrypt** or **Cifrar**.
7. A file with the `.encrypted` extension will be generated.

### 🔓 Decryption Process

1. Select a file with the `.encrypted` extension.
2. Enter the same password used during encryption.
3. Click **Decrypt** or **Descifrar**.
4. In v2.0, the algorithm is detected automatically.
5. The original file will be restored.

---

## 🧪 Demo

```text
https://dai.ly/x9rr1cw
```

---

## ⚠️ Security Considerations

No encryption tool can guarantee absolute security in every possible scenario. Cryptom4n provides strong protection when used correctly, but security depends on password strength, system integrity and safe file handling.

### Recommended Password Practices

- Use at least 12 characters.
- Combine uppercase letters, lowercase letters, numbers and symbols.
- Avoid common words, names or predictable patterns.
- Do not reuse passwords.
- Use a password manager.

### Important Notes

- If you forget the password, the encrypted file cannot be recovered.
- Keep backups before encrypting important files.
- Run the tool only on trusted systems.
- Before using it with critical files, validate the encryption and decryption process first.

---

## 🐛 Troubleshooting

### File not found

Make sure the file path is correct.

### Decryption error

Check that:

- The password is correct.
- The file has not been modified or corrupted.
- The file has the `.encrypted` extension.

### Permission error

Make sure you have read and write permissions over the file or folder.

### Tkinter error on Linux

```bash
sudo apt install python3-tk
```

---

## 🛠️ Future Improvements

- Batch file encryption.
- Folder encryption.
- Drag-and-drop support.
- Theme selector.
- Exportable logs.
- Integrated CLI mode.
- Secure overwrite option for original files.

---

## 👨‍💻 Author

Created by **Gh0s7m4n 💀**

---

## ⭐ Support

If you find this project useful, consider giving it a star on GitHub.

```text
🔐 Remember: With great encryption power comes great responsibility.
```
