# Installing DigitalPersona SDK on Ubuntu 18.04

1. **Navigate to the SDK Directory and Install the SDK**:
   - Open a terminal and navigate to the `sdk/sdk` directory:
     ```bash
     cd sdk/sdk
     ```
   - Run the installation script with `sudo`:
     ```bash
     sudo ./install
     ```

2. **Copy the `Crossmatch` Folder**:
   - Navigate back to the `instalacion-sdk` directory:
     ```bash
     cd ../../instalacion-sdk
     ```
   - Copy the `Crossmatch` folder to `/usr/local/lib`:
     ```bash
     sudo cp -r Crossmatch /usr/local/lib
     ```
   - If you are unable to paste due to permissions, change the permissions of the `lib` folder:
     ```bash
     cd /usr/local
     sudo chmod -R 777 lib
     ```

3. **Copy Text Files `99-*cc`**:
   - Navigate to the `redist` directory:
     ```bash
     cd /opt/Crossmatch/urusdk-linux/redist
     ```
   - Copy the `99-*cc` files to `/etc/udev/rules.d`:
     ```bash
     sudo cp 99-*cc /etc/udev/rules.d/
     ```
   - If you are unable to paste due to permissions, change the permissions of the `rules.d` folder:
     ```bash
     cd /etc/udev
     sudo chmod -R 777 rules.d
     ```

4. **Java Installation for Testing**:
   - Install Java:
     ```bash
     sudo apt-get update
     sudo apt-get install default-jdk
     ```
   - If you are using Ubuntu 22 and want to use Java 17:
     ```bash
     sudo apt-get install openjdk-17-jdk
     ```

5. **Run Java Examples**:
   - Navigate to the Java samples directory:
     ```bash
     cd /opt/Crossmatch/urusdk-linux/linux/samples/bin/java
     ```
   - Execute the sample script:
     ```bash
     sudo ./run_x64.sh
     ```

6. **Running the SDK Finger Server**:
   - Navigate to the `finger` directory:
     ```bash
     cd /path/to/finger
     ```
   - Compile the server:
     ```bash
     make
     ```
   - Run the server:
     ```bash
     ./finger
     ```
   - This will start a mini-server on port 5050, which will detect the biometric device and return the captured image in Base64 format.

These steps should help you successfully install and set up the DigitalPersona SDK on your Ubuntu 18.04 system. If you encounter any issues, make sure to check permissions and ensure all required dependencies are installed.

# instalacion-sdk-digitalpersona
USANDO UBUNTU 18.4
 
entrar a la carpeta sdk/sdk 
abrir la consola e instalar con "sudo ./install" el sdk de DIGITALPERSONA

volver a la carpeta "instalacion-sdk" copiar la carpeta  "Crossmatch" en "usr/local/lib"
	
si no te deja pegar debes darles permiso a la carpeta lib, vamos dentro de la carpeta "local" y abrimos una consola y ejecutamos "sudo chmod -R 777 lib"

luego vamos a "/opt/Crossmatch/urusdk-linux/redist" copiar los archivos de texto 99-*cc
	 
si no  nos deja copiar los archivos abrimos la consola en la carpeta "urusdk-linux" y abrimos una consola y ejecutamos "sudo chmod -R 777 redist"
	
y pegamos los archivos copiados en "etc/udev/rules.d"  y remplazamos

	 
si no te deja pegar debes darles permiso a la carpeta rules.d, vamos dentro de la carpeta "udev" y abrimos una consola y ejecutamos "sudo chmod -R 777 rules.d"

para las pruebas de java debe instalar java e ir a si desea usarlo con ubuntu 22 usar la version 17 de java

ir a los ejemplos en "opt/crossmatch/urusdk-linux/linux/samples/bin/java" y ejecutar "sudo ./run_x64.sh"

---------------------------------------------------------------------------------------

para ejecutar el sdk existe la carpeta finger la cual creara un miniserver en el puerto 5050 el cual detectara el dispositivo biometrico y retronara la imagen capturada en base 64

se ejecuta con el comando "make" para compilar 
el comando "./finger" para correr el servidor
