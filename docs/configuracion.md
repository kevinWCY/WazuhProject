# GUIA DE CONFIGURACION DE WAZUH 

## Índice

1.- Configuracion inicial del servidor wazuh
2.- Configuracion de Agentes Wazuh
  - Configuracion en Linux
  - Configuracion en Windows
3.- Configuracion del Dashboard de Wazuh
4.- Monitoreo y Mantenimiento 

## CONFIGURACION INICIAL DEL SERVIDOR WAZUH

1.- **acceder al servidor por ssh**:

- Por Seguridad y buenas practica es importante generar llave Privada y Publica para tu servidor
 
- Acceder al servidor es sencillo:

 - Si estas en la maquina donde generaste las llaves puedes acceder con la llave publica:
 
```bash
    ssh -i _ruta_llavePublica_ user@_ip_servidor
    ```

- Si quieres entrar desde otra Maquina agena a donde generaste las llaves, se puede hacer siempre que uses la llave privada
  
```bash
    ssh -i _ruta_llavePrivada_ user@_ip_servidor
    ```

2.- **configurar el archivo ossec.conf**

- Todos los agentes tienen el archivo ossec.conf 

- Editar el archivo con vim o nano  "/var/ossec/etc/ossec.conf" para que haya comunicaion entre tu agente y wazuh:

```bash
    sudo vim /var/ossec/etc/ossec.conf    //no archivo ossec no siempre estara en esta misma ruta
    ```
3.- **ver el estado de tu servidor wazuh**

- Si al intentar entrar a tu wazuh-dashboard no te deja acceder con el usuario y contraseña que te dieron es probable que alguno de los componentes de wazuh esten inactivos, para verificar eso puedes poner los siguiente:

```bash
    sudo systemctl status wazuh-manager
    ```
```bash
    sudo systemctl status wazuh-manager
    ```
```bash
    sudo systemctl status wazuh-manager
    ```
- Los tres componentes deben estar activos para usar wazuh, para activarlo simplemente usas estos comandos:

```bash
    sudo systemctl start wazuh-manager
    ```
```bash
    sudo systemctl start wazuh-manager
    ```
```bash
    sudo systemctl start wazuh-manager
    ```

4.- **reiniciar los servicios de wazuh**

- Este comando es importante hacerlo porque te actualiza el wazuh si es que hiciste algun cambio en alguno de sus archivos 

```bash
    sudo systemctl restart wazuh-manager
    ```

```bash
    sudo systemctl restart wazuh-indexer
    ```

## CONFIGURACION DE AGENTES WAZUH 

### CONFIGURACION PARA LINUX

1.- **editar el archivo de configuracion del agente** 

```bash
    sudo vim /var/ossec/etc/ossec.conf
    ```
 - Agregar en la seccion <client> en <address> asegurate que la ip sea la del Servidor de Wazuh

  <client>
   <address>IP_Servidor_Wazuh</address>
  </client>

2.- **reiniciar el agente wazuh**
```bash
    sudo sytemctl restart wazuh-agent
    ``` 

### CONFIGURACION PARA WINDOWS 

1.- **editar el archivo de configuracion del agente**
 
- Abre el archivo ossec.conf con powershell con permisos de administrador, puede estar ubicado en:

```bash
    notepad C:\Program Files (x86)\ossec-agent\ossec.conf
    ```
- Asegurate de que en la seccion <client> este la direccion IP del servidor Wazuh

2.- **reinicia los servicios de wazuh-agent**

```bash
    Restart-Service -Name "wazuh-agent"
    ```
## CONFIGURACION DEL DASHBOARD DE WAZUH

1.- **Acceder al dashboard de wazuh**

 - Abrir algun navegado web para acceder al dashboard de wazuh usando la Ip del servidor.
 
    http:/167.99.234.x 

2,- **configurar el Dashboard**

 - ```bash
    sudo vim /var/ossec/etc/ossec.conf
    ```
 - Para configurar el Dashboard hay dos formas de hacerlo, si vas al menu a la seccion de "server management" y de ahi a Settings puedes ver que te aparecera las coniguraciones principales del servidor wazuh 
 
 - La otra forma es ingresando por consola al ossec.conf de tu "servidor de wazuh" 





