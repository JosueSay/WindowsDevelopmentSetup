
# 🐧 **WSL 2 (Windows Subsystem for Linux)**  

**WSL 2** es una herramienta que permite tener el **kernel de Linux** funcional en Windows. Esto es especialmente útil porque, históricamente, muchos sistemas y herramientas de desarrollo web, backend, frontend, e incluso videojuegos se basan en Linux o macOS.  

Microsoft se dio cuenta de que estaba perdiendo parte del público desarrollador, así que integró Linux como una herramienta dentro de Windows.  

## 🔧 **Instalación de WSL 2**  

Para instalar WSL 2, sigue estos pasos:  

1. **Instala Windows Terminal desde la Microsoft Store**  
   Esta herramienta es ideal porque permite personalizar muchas configuraciones mediante un archivo **JSON**.  

   ![Windows Terminal](https://raw.githubusercontent.com/JosueSay/ImageDocs/main/WindowsDevelopmentSetup/windows_terminal.png "Windows Terminal")  

2. **Ejecuta el siguiente comando en una terminal:**

   ```bash
   wsl --install
   ```

   - El sistema solicitará varios permisos, **acéptalos**.  
   - Una vez completado, la instalación estará lista.  

## ⚠️ **Solución de errores comunes**  

### 🔄 **Error de Virtualización**  

Si ocurre un error relacionado con la **virtualización**, sigue estos pasos:  

1. Abre **PowerShell** como **Administrador**.  
2. Ejecuta el siguiente comando para habilitar las características de máquinas virtuales:  

   ```bash
   dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
   ```  

### 🛡️ **Error 0x80370114**  

Este error puede ocurrir al iniciar **Ubuntu** por primera vez. Aquí hay dos posibles soluciones:  

#### **Solución 1: Ajustar la seguridad de Windows**  

1. Abre **Windows Security**.  
2. Ve a **App & Browser Control**.  
3. Haz clic en **Exploit Protection Settings**.  
4. Selecciona la pestaña **Program settings**.  
5. Busca `C:\WINDOWS\System32\vmcompute.exe`.  
6. Haz clic en **Edit** y ajusta la configuración.  

#### **Solución 2: Activar características de Windows**  

1. Abre **"Turn Windows features on or off"** (Activar o desactivar características de Windows).  
2. Activa las siguientes opciones:  
   - **Windows Subsystem for Linux**  
   - **Virtual Machine Platform**  
   - **Windows PowerShell 2.0**  
3. Aplica los cambios y **reinicia la computadora**.  

## 🧑‍💻 **Configuración de la Cuenta Unix**  

Una vez solucionados los errores:  

1. Al iniciar Ubuntu por primera vez, el sistema te pedirá **crear una cuenta Unix**.  
2. Configura un **usuario y contraseña**.  

¡Listo! Ahora tendrás la **terminal Linux disponible** dentro de Windows. 🎉  
