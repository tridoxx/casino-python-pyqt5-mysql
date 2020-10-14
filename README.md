# casino desarollado en python3.7 ,pyqt5.12.1, mariadb

juego de casino desarollado en python con interfaz grafica en pyqt5, con persistencia de datos en mysql o mariadb.(se debe describir en el archivo de configuración "db.py" el driver)



# juegos 
 cada carpeta tiene un juego distinto que dentro de este tiene su explicación.

# tiene graficas en la pantalla principal y un menu.

# transaciones 

todos los juegos envian la información por el fichero "db.py" a travez de la función ``insertarDatos(total_transaccion,detalle_transacion): `` 

cada juego debe hacer sus operaciones ya sea de suma y de resta, y se deben enviar en la funcion los valores de la siguiente forma.

total_transaccion: se obtiene el ultimo valor de la columna con el mismo nombre en la base de datos, y con este valor se opera, se hacen las respectivas sumas o restas del valor obtenido de la base de datos, y se envia por ese parametro ya sumado o restado.

detalle_transacion: en este valor se envia el respectivo valor de la ganancia o la perdida.

ejemplo 

* dinero recargado: 5000 (traerValor)
* valor de perdida: 3000 (generado por la apuesta)
* (total_transaccion) = valor recargado - valor pedida =valor que genera total *(5000-3000=2000) 
* (detalle_transacion)valor de la perdida : 3000




# Como conectar a la base de datos




# conexion
## para hacer la conexion se necesitan los siguientes datos
* ## servidor de conexion de la base de datos, por defecto el puerto es 3306
* ###       self.db.setHostName("192.168.100.243")
* ## nombre de la base de datos
* ### self.db.setDatabaseName("casino")
* ## usuario para conectarse a la base de datos
* ### self.db.setUserName("usuariocasino")
* ## contraseña del usuario para la base de datos
* ### self.db.setPassword("casino")
## estos son solo datos de ejemplo 
Para conectar con la base de datos deben incluir estas lineas al principio de su código luego de ```import sys, re```




```python
sys.path.append("..") #Necesario para poder importar basedatos
import bd #Importa el script bd.py
```
luego pueden usar:


```python
bd.insertarDatos(100,100)
valor = bd.traerValor()
```
