# GUIA DE INSTALACION

## REQUISITOS PREVIOS

- Virtual Box o VM Ware

- Maquina Virtual con Sistema Operativo "UBUNTU" version 22.04 o superior
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

### Instalacion para entorno de Laboratorio
 
 - Ir a al sitio oficial de Wazuh https://documentation.wazuh.com/current/quickstart.html

 - Es ese apartado del Link que esta arriba hay un comando donde te instala los tres componentes mas importantes de Wazuh. El Indexer,Dashboard,Server

 - comando: curl -sO https://packages.wazuh.com/4.8/wazuh-install.sh && sudo bash ./wazuh-install.sh -a
  - El comanndo cambia a medida que pasa el tiempo por eso es importante que vayas al sitio oficial por que ahi muestra lo actulizado 

 - 

### Instalacion para entornos de Produccion



