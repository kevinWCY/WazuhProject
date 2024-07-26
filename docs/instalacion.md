# GUIA DE INSTALACION

## REQUISITOS PREVIOS

- Virtual Box o VM Ware o Servidor

- Maquina Virtual con Sistema Operativo "Ubuntu" version 22.04 o superior
 - El servidor Wazuh puede ser instalado en una variedad de distribuciones de Linux pero en mi proyecto lo hare en Ubuntu

- Acceso a internet 

- Privilegios de supersuario 

- Desactivar le firewall

## INSTALACION DEL SISTEMA OPERATIVO 

1.-Ir a la sitio oficial de Ubuntu https://ubuntu.com/download/desktop y descargar la iso Ubuntu LTS mas recientemente actualizada

2.-Al tener instalado Ubuntu ve a configuraciones:

- 2 a procesadores

- 4 de RAM

- 50GB de almacenamiento

3.-En consola actualizar los paquetes de tu SO Ubuntu y tener curl instalado

- sudo apt-get update

- sudo apt-get ungrade

- sudo apt install curl

## INSTALACION DE WAZUH 

### Instalacion para entorno de Laboratorio para VM y Servidor
 
 - Ir a al sitio oficial de Wazuh https://documentation.wazuh.com/current/quickstart.html

 - Es ese apartado del Link que esta arriba hay un comando donde te instala los tres componentes mas importantes de Wazuh. El Indexer,Dashboard,Server

 - comando: curl -sO https://packages.wazuh.com/4.8/wazuh-install.sh && sudo bash ./wazuh-install.sh -a
  - El comanndo cambia a medida que pasa el tiempo por eso es importante que vayas al sitio oficial por que ahi muestra lo actulizado 

 - Al completar la instalacion wazuh te brindara un usuario y contraseña para ingrear al Dashboard de Wazuh:

   INFO: --- Summary ---
   INFO: You can access the web interface https://<wazuh-dashboard-ip> 
      User: admin 
      Password: <ADMIN_PASSWORD> 
   INFO: Installation finished. 


### Instalacion para entornos de Produccion

- Para la intalacion en entornos de produccion los componentes del wazuh se instalan por separado y en diferentes hosts

## INSTALACION DE AGENTES WAZUH

- Puedes instalar los agentes en una gran variedad de Sistemas Operativos por ejemplo en las distros mas usadas de Linux (Ubuntu,Fedora,Debian), en Windows 7 y versiones superiores, MacOS, etc.

- Despues de obtener el usuario y contraseñia de wazuh puedes entrar al dashboard y desde ahi puedes generar el codigo que te proporciona el propio wazuh para que puedas ejecutarlas a la maquina que quieras que sea tu wazuh-agent 

- Una vez que este en el dashboard de wazuh puedes hacer un click al menú desplegable y en la seccion de "server management" hay una seccion donde te dira "+ Deploy new agent" debes ingresar ahi y seguir los pasos que te pide para que te genere un codigo para el SO especifico que quieras que sea tu agente

- Un ejemplo del codigo que te deberia generar para Windows seria este:
 
 1er codigo:

  Invoke-WebRequest -Uri https://packages.wazuh.com/4.x/windows/wazuh-agent-4.8.1-1.msi -OutFile ${env.tmp}\wazuh-agent; msiexec.exe /i ${env.tmp}\wazuh-agent /q WAZUH_MANAGER='167.99.224.23' WAZUH_AGENT_GROUP='default' WAZUH_AGENT_NAME='asdfasd' 
 
 2do codigo: 

  NET START WazuhSvc

- Despues de instalar el agente se te generara un archivo ossec.conf, con este archivo wazuh podra trabajar con tu agente



