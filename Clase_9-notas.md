# Clase_9-notas

## STACK DE DESARROLLO (CONTINUACION): TRUFFLE Y GANACHE


### VISUAL STUDIO (PENDIENTE):
- INSTALAR LA EXTENSION: Material Design Icons for Visual Studio Code
	- PONE ICONOS Y COLORES MAS ATRACTIVOS EN LAS CARPETAS Y LOS ARCHIVOS DEL PROYECTO


### TRUFFLE:
#### BOXES: https://trufflesuite.com/boxes/index.html

###  CREAR UN PROYECTO:
https://trufflesuite.com/docs/truffle/quickstart.html
	
  - CREAR UNA CARPETA, EN HOME: Metacoin
	
  - O EN DOCUMENTOS:
mkdir MetaCoin
cd MetaCoin
	
  - DESCARGAR EL PROYECTO: MetaCoin
truffle unbox metacoin
	
  - SI DA ERROR:
truffle.cmd unbox metacoin
	
  - AL EJECUTARLO, SE CREA UNA ESTRUCTURA CON LOS FICHEROS DEL PROYECTO

### ABRIR EL PROYECTO DESDE VISUAL STUDIO:
	- EN EL MENU: ARCHIVO
	- ABRIR CARPETA
	- BUSCAR LA CARPETA: metacoin
	- LA ESTRUCTURA DEL DIRECTORIO TIENE QUE APARECER EN LA PARTE IZQUIERDA
	- CREAR UN ENTORNO DE TRABAJO NUEVO:
Metacoin-Cibernos01.code-workspace

### EXPLORAR LA ESTRUCTURA DEL DIRECTORIO:
	Once this operation is completed, you'll now have a project structure with the following items:
    - contracts/: Directory for Solidity contracts
    - migrations/: Directory for scriptable deployment files
    - test/: Directory for test files for testing your application and contracts
    - truffle.js: Truffle configuration file

### EJECUTAR COMANDOS DESDE EL VISUAL STUDIO:
	- SI EL TERMINAL NO APARECE EN LA PARTE INFERIOR
	- ACTIVARLO, EN EL MENU, EN LA OPCION: VER / TERMINAL
	
### EJECUTAR EL TEST:
	- Testing:
    In a terminal, run the Solidity test:
  - PERO EN ESTE CASO, PARECE QUE NO SE EJECUTA CORRECTAMENTE

	- ESTO LO PUEDO EJECUTAR DESDE UN TERMINAL, PERO FUERA DE VISUAL STUDIO CODE:
truffle test ./test/TestMetaCoin.sol
truffle.cmd test ./test/TestMetaCoin.sol

	- ESTO LO PUEDO EJECUTAR DESDE UN TERMINAL, PERO FUERA DE VISUAL STUDIO CODE:
truffle test ./test/metacoin.js
truffle.cmd test ./test/metacoin.js

	- OPCION: Migrating with Truffle Develop
  
### PERO VAMOS A USAR GANACHE PARA EL EJEMPLO:
	Alternative: Migrating with Ganache

	1º) Download and install Ganache.
	2º) Open truffle-config.js in a text editor. Replace the content with the following:
  
module.exports = {
  networks: {
    development: {
      host: "127.0.0.1",
      port: 7545,
      network_id: "*"
    }
  }
};
	
  - GUARDAR EL ARCHIVO

### ABRIR GANACHE, CON UN NUEVO WORKSPACE:
	- PONERLE UN NOMBRE, POR EJEMPLO:
	Truffle-shuffle01
	- AÑADIR EL PROYECTO DE TRUFFLE
	- HAY QUE PULSAR EL BOTON: ADD PROJECT
	- SE ABRE UNA VENTANA
	- HAY QUE LOCALIZAR LA CARPETA DONDE ESTA EL PROYECTO: METACOIN
	- LO QUE SE NECESITA ES QUE ESTE EL ARCHIVO: truffle-config.js
	- Y HAY QUE DARLE: SAVE WORKSPACE (PARTE SUPERIOR DERECHA)
	- ARRANCA EL GANACHE, CON UN WORKSPACE, CON EL NOMBRE QUE ACABAMOS CREAR

###	LO SIGUIENTE SERIA MIGRAR LOS CONTRATOS DEL PROYECTO METACOIN A GANACHE

	- HAY QUE EJECUTAR EL COMANDO, EN EL TERMINAL:
truffle migrate
truffle.cmd migrate

	- A PARTIR DE AHI, SE EJECUTAN UNA SERIE DE COMANDOS
	- CUANDO TERMINA, SE PUEDE VER LA ACTIVIDAD EN GANACHE:
	BLOQUES, TRANSACCIONES Y CONTRATOS
  
## TRUFFLE CONSOLE
### EN EL TERMINAL, EJECUTAR:

truffle console

truffle.cmd console

	- CAMBIA EL TERMINAL A: 
truffle(development)>

	- SE PUEDE PROBAR CON EL COMANDO:
web3.eth.getAccounts()

	- QUE DA UN LISTADO DE LAS CUENTAS QUE SE HAN CREADO EN GANACHE
	- EL SIGUIENTE COMANDO DA LA PRIMERA DIRECCION:

(await web3.eth.getAccounts())[0]

	- NOTA: CUANDO SE EJECUTA UN COMANDO, A VECES DA COMO SALIDA: undefined

let instance = await MetaCoin.deployed()

