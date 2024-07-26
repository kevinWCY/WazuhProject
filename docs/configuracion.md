# GUIA DE CONFIGURACION DE WAZUH 

## Índice

1.- Configuracion inicial del servidor wazuh
2.- Configuracion de Agentes Wazuh
  - Configuracion en Windows
  - Configuracion en Linux
3.- 
4.-

## CONFIGURACION INICIAL DEL SERVIDOR WAZUH

1.- **acceder al servidor por ssh**:

 - Por Seguridad y buenas practica es importante generar llave Privada y Publica para tu servidor
 
 - Acceder al servidor es sencillo: 
  - Si estas en la maquina donde generaste las llaves puedes acceder con la llave publica:
  ej:
   - ssh -i _ruta_llavePublica_ user@ip_servidor

 - Si quieres entrar desde otra Maquina agena a donde generaste las llaves, se puede hacer siempre que uses la llave privada
  ej:
   - ssh -i _ruta_llavePrivada_ user@ip_servidor
