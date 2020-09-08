# Resincronización de Ghostnode

**Instalaciones de script, p. Método CryptoSharks:**

```text
systemctl stop NIX
rm -r ~/.nix/{blocks,chainstate,peers.dat,banlist.dat}
systemctl start NIX
```

**Instalaciones manuales:**

```text
nix-cli stop
rm -r ~/.nix/{blocks,chainstate,peers.dat,banlist.dat}
nixd &
```

**Descargar un bootstrap \(opcional\):**

Las siguientes instrucciones suponen un VPS con Ubuntu 18.04. Realice esta acción después de detener la billetera y eliminar los archivos \(pasos 1 y 2 anteriores\). Después de descomprimir el archivo de arranque, continúe con el paso 3.

 Primero, necesitará instalar python-pip, gdown y descomprimir si aún no lo están.

```text
sudo apt update
sudo apt install python-pip
sudo -H pip install gdown
sudo apt install unzip
```

Descargue y descomprima el archivo bootstrap:

```text
gdown https://drive.google.com/file/d/1pFrfLyy5N5HXgqptEjFrRn3NRgrXrGu3
unzip NIXBlockchain-540622.zip -d ~/.nix
```

{% hint style="warning" %}
**Si por alguna razón estos pasos no solucionan su problema, únase al** [**servidor de Discord**](https://discordapp.com/invite/HGuvDTW) **y solicite ayuda en los canales públicos únicamente. ¡No respondas a ningún DM ya que los estafadores podrían tratar de engañarte para que les des tus fondos!**
{% endhint %}

