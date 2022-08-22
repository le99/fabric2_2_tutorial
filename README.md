# Tutorial basico Fabric 2.2.0

## Pre-requisitos
Instalar vagrant y virtual box:

https://www.vagrantup.com/docs/installation
https://www.virtualbox.org/


Se require conexion an internet y acceso a la pagina:
https://registry.npmjs.org/

## 1. Correr maquina virtual
Clonar repositorio (o descargar el archivo Vagrantfile)

En la carpeta correr:
```bash
vagrant up

#Para apagar
#vagrant halt
```

## 2. Correr asset-transfer-basic

```bash
vagrant ssh
cd /home/vagrant/hyperledger/fabric-samples/test-network

./network.sh up createChannel -ca -c mychannel -s couchdb -i 2.0.0
./network.sh deployCC -ccn basic -ccp ../asset-transfer-basic/chaincode-javascript/ -ccl javascript

```

```bash
# Segundo teminal
vagrant ssh
cd /home/vagrant/hyperledger/fabric-samples/asset-transfer-basic/application-javascript
rm -rf ./wallet/
node ./app.js
```

http://192.168.50.12:5984/_utils/#
user: admin
pw: adminpw

```bash
cd /home/vagrant/hyperledger/fabric-samples/test-network

#Stop network
./network down

#Stop vagrant
vagrant halt
```
## References
https://github.com/hyperledger/fabric-samples/tree/main/asset-transfer-basic