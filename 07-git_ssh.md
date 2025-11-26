
# 🐙 **Git**

Git es un sistema de control de versiones distribuido utilizado para gestionar proyectos de manera eficiente.

## **Instalación de Git**

Para instalar Git en tu sistema, ejecuta el siguiente comando en la terminal:

```bash
sudo apt-get install git-all
```

## 🔑 **SSH (Secure Shell)**

SSH es un protocolo utilizado para acceder de forma segura a servidores y dispositivos remotos. Una de las funcionalidades clave de SSH es el uso de llaves públicas y privadas para autenticación.

### **Generar una llave SSH**

Para generar una llave SSH, utiliza el siguiente comando:  

```bash
ssh-keygen -t ed25519 -C "correo@gmail.com"
```

🔍 **Explicación de los parámetros:**

- `-t ed25519`: Especifica el tipo de algoritmo de encriptación a utilizar (en este caso, **ed25519**, recomendado por su seguridad y rapidez).
- `-C "correo@gmail.com"`: Añade un comentario identificador para la llave (generalmente tu correo electrónico).  
- `-f ~/.ssh/name_ssh_key`: (Opcional) Define un nombre y ruta personalizados para la llave, en lugar del valor predeterminado (`id_ed25519`).

### **Proceso de generación**

1. Una vez ejecutado el comando, se te pedirá:  
   - **Ruta para guardar la llave**: Presiona `Enter` para usar la predeterminada (`~/.ssh/id_ed25519`) o ingresa un nombre/ruta personalizada.  
   - **Passphrase (frase de paso)**: Opcional, pero recomendable para añadir una capa extra de seguridad. Debes recordarla, ya que se usará para desbloquear la llave.  

2. La herramienta generará dos archivos:  
   - **Llave privada**: No la compartas ni distribuyas.  
   - **Llave pública**: Este archivo puede compartirse para configurar accesos en servidores remotos.

### **Verificar que el agente SSH se está ejecutando**

El agente SSH administra las llaves privadas cargadas para evitar ingresar la passphrase repetidamente. Verifica que esté activo con:  

```bash
eval "$(ssh-agent -s)"
```

🔍 Si está funcionando, aparecerá un mensaje similar:  
`Agent pid 12345`

### **Añadir la llave SSH al agente**

Para cargar tu llave privada en el agente SSH, usa:  

```bash
ssh-add ~/.ssh/private_name_key
```

- **~/.ssh/private_name_key**: Especifica la ruta de tu llave privada generada anteriormente.  
- Te pedirá ingresar la passphrase, si configuraste una.  

🔍 **¿Por qué usar `ssh-add`?**  
Este comando carga tu llave en el agente SSH, lo que permite usarla sin necesidad de ingresarla manualmente cada vez que te conectes a un servidor. El agente gestiona estas llaves de manera temporal durante la sesión.

### **Verificación de la llave pública**

Para visualizar tu llave pública y copiarla al servidor remoto, utiliza:  

```bash
cat ~/.ssh/name_ssh_key.pub
```

Copia el contenido y añádelo al archivo `~/.ssh/authorized_keys` del servidor remoto para permitir el acceso.

### **Otros parámetros útiles de `ssh-keygen`**

- `-b <bits>`: Define el tamaño de la llave (por ejemplo, `-b 4096` para llaves RSA).  
- `-N <passphrase>`: Configura la passphrase directamente al generar la llave.  
- `-q`: Ejecuta el comando en modo silencioso, sin mensajes de confirmación.
