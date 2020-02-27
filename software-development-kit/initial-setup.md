# Configuración Inicial

## **Archivos Requeridos**

#### nixd

Necesitará una instancia en ejecución de nixd que se puede descargar desde [https://github.com/NixPlatform/NixCore/releases](https://github.com/NixPlatform/NixCore/releases). Después de descargar el binario nixd, cree un archivo de configuración en `~/.nix` llamado `nix.conf` y configure el demonio a su gusto. Un ejemplo de trabajo y válido se muestra a continuación. Una vez configurado, simplemente ejecute nixd o configure un servicio systemd para administrarlo.

#### SDK

Puede usar hilo o npm para instalar el SDK.

```text
yarn add nix-core
```

o

```text
npm install nix-core --save
```

## **Configuración de Nodo**

Para establecer una conexión entre la instancia de nixd y el SDK, se requiere un archivo de configuración nix.conf apropiado.

{% code title="nixd.conf" %}
```text
daemon=1
server=1
par=1
rpcbind=127.0.0.1
rpcallowip=127.0.0.1
rpcport=3335
rpcuser=username1
rpcpassword=password1
rpcclienttimeout=30
rpcthreads=2
rpcworkqueue=1000
staking=0
enableaccounts=1
```
{% endcode %}

### **Conectándose al daemon en JavaScript**

Después de que nixd se haya iniciado con la configuración anterior, se puede crear una instancia en el archivo JavaScript de control:

```text
    const Client = require('nix-core');
    const client = new Client({
        username: 'username1',
        password: 'password1',
        port: 3335,
        network: 'mainnet' });
```

Se pueden encontrar más opciones en la documentación del paquete nix-core. Con el objeto de cliente, cualquier comando ahora se puede ejecutar. Puede encontrar una lista de los comandos seleccionados [aquí](https://wiki.nixplatform.io/home/v/espanol/software-development-kit/usage-guide).

## **Nodo oficial del SDK de NIX**

 Alternativamente, puede conectarse a ny.nixplatform.io utilizando los siguientes parámetros:

```text
var RPC_USER = 'yourusername'
var RPC_PASSWORD = 'yourpassword'
var RPC_PORT = 8822
const client = new Client({ network: 'mainnet',
                            port: RPC_PORT,
                            host: 'ny.nixplatform.io',
                            username: RPC_USER,
                            password: RPC_PASSWORD
                          });
```

