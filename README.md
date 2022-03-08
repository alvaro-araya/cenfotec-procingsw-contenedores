
# Cenfotec - PROCINGSW

## Laboratorio de Contenedores

**Profesor:**  
Raúl Sossa Sossa


**Elaborado por:**  
Hayleen Bonilla  
Miguel Gutierrez  
Alvaro Araya O

**Fecha:**
2022-03-09

## Descripción

A continuación se configurará un ambiente basado en contenedores para dejar trabajando un servidor llamado **iceScrum**. En la configuración se utilizará un servidor MySQL en el que se almacenarán los datos de la aplicación.

La aplicación quedará corriendo como un servidor HTTP en el puerto 8888.

## Instalación de requisitos

### Requisitos

#### Linux

1. Instalar el Docker Engine: https://docs.docker.com/engine/install/
    ```bash
    # Instalador de conveniencia:
    
    $ curl -fsSL https://get.docker.com -o get-docker.sh
    
    $ sudo sh get-docker.sh
    
    ```

2. Instalar el Docker-Compose: https://docs.docker.com/compose/install/
    ```bash
    # Validar la última versión
    
    $ sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
    ```

3. Verificar el resultado de la instalación y las instrucciones en caso de querer ejecutar el docker en versión rootless (con cualquier usuario).

#### Windows

1. Asegurarse de contar con las versiones de Windows 10 2004 (build 19041 o superior) o Windows 11.

2. Ejecutar el comando de instalación:
    ```powershell
    # Abrir una ventana de PowerShell
    
    wsl  --install
    
    ```

3. Instalar la actualización del Linux Kernel Update: https://docs.microsoft.com/en-us/windows/wsl/install-manual#step-4---download-the-linux-kernel-update-package

4. Instalar Docker Desktop: https://docs.docker.com/desktop/windows/install/

5. Instalar el Windows Terminal: https://www.microsoft.com/en-us/p/windows-terminal/9n0dx20hk701#activetab=pivot:overviewtab

#### MacOS

1. Asegurarse de tener la versión de macOS 10.15 o superior en el caso de las Mac basadas en chip Intel.

2. En caso de Mac basadas en el chip M1 de Apple, instalar la última versión de Rosetta:
    ```console
    $ softwareupdate --install-rosetta
    ```

3. Instalar el Docker Desktop: https://docs.docker.com/desktop/mac/install/

## Preparación del ambiente

Es recomendable instalar el Visual Studio Code y las extensiones de Docker:

1. Instalar Visual Studio Code: https://code.visualstudio.com/
2. Abrir Visual Studio Code y ejecutar CTRL+P:
    ```
    ext install ms-azuretools.vscode-docker
    
    ext install ms-vscode-remote.remote-containers
    ```
3. Clonar este repositorio:
    ```
    $ git clone https://github.com/alvaro-araya/cenfotec-procingsw-contenedores.git
    ```
4. Abrir en una consola de terminal el directorio ```procingsw-containers```, asegurarse de que exista el archivo docker-compose.yml en el directorio.

5. Ejecutar el comando de Docker Compose
    ```
    $ docker-compose up
    ```

6. Configuración de los contenedores:
    1. Ingresar a la página: http://localhost:8888/icescrum/setup/edit
    2. Crear la cuenta de administrador.
    3. Dejar los directorios y logs con los valores por defecto.
    4. Chequear la opción de saltar el **Free Trial**.
    5. En los parámetros de la base de datos establecer el tipo de BD como **MySQL**, el nombre del servidor debe ser **icescrum_mysql** (en vez de localhost), nombre de usuario **root** y la clave especificada en el docker-compose.yml.
    6. Revisar los parámetros finales de configuración y enviar la configuración.
    7. Reiniciar los contenedores (docker-compose down o CTRL+C).

### Recursos

[Install Docker](https://www.docker.com/products/docker-desktop)

[DockerHub repository](https://hub.docker.com)

[Docker reference documentation](https://docs.docker.com/reference/)

[Dockerfile reference](https://docs.docker.com/engine/reference/builder/)

[Docker Compose reference](https://docs.docker.com/compose/compose-file/)

[iceScrum](https://www.icescrum.com/)
