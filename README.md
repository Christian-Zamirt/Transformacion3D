## Transformaciones en 3D
La representación de las transformaciones en tres dimensiones es una generalización de la de dos dimensiones.

Los puntos se representan en coordenadas homogeneas como cuartetos y las matrices de transformación son de 4x4.

Usaremos el sistema de coordenadas tridimensional de mano derecha, como se muestra en la figura.

![transf7](https://user-images.githubusercontent.com/72089660/143964846-ceb837f0-f0b5-4080-a64a-2bc78a067674.gif)

Las transformaciones se clasifican de la siguiente manera:

-->Rígidas - Mantianen ángulos y longitudes. Consisten de traslaciones y rotaciones solamente.
	
-->Afines - Conservan solo el paralelismo de líneas. Secuencias de rotaciones, traslaciones y escalamientos.
	
-->No lineales - Deforman los objetos. El valor de dos coordenadas se calcula en función de la tercera. Se pueden usar expresiones lineales, cuadráticas, etc. Pueden modificar la topoloía del objeto

Traslación
Mueve el objeto a una nueva posición. La representación matricial es la siguiente:

![transf8](https://user-images.githubusercontent.com/72089660/143965055-88afe0fd-8202-463d-b388-4eac0c86aa92.gif)

![transf9](https://user-images.githubusercontent.com/72089660/143965063-4a041e6f-bb54-400a-a1ab-4bf255de6b9d.gif)

Escalamiento
El escalamiento c ambia el tamaño del objeto y al mismo tiempo desplaza el objeto a una nueva posición.

![transf10](https://user-images.githubusercontent.com/72089660/143965098-b3f0a744-31df-4ea6-908b-758d464db027.gif)
![transf11](https://user-images.githubusercontent.com/72089660/143965110-e35b2dad-f7f9-4a48-8ef3-1e9cf7e7ce02.gif)

Rotación
La roación en tres dimensiones puede definirse alrededor de cualquier recta en el espacio. Existen tres rotaciones elementales que se definen alrededor de los ejes coordenados. Las matrices correspondientes son las siguientes.

![transf12](https://user-images.githubusercontent.com/72089660/143965215-5ebc1345-1b7a-462f-bcf0-abb2edcd2113.gif)

Una vez explicado los movimientos que se pueden hacer en la 3 dimension procederemos a explicar en el programa que en este caso es un cubo de color creado 
##Aplicadas en java

librerias utilizadas en el programa

![1](https://user-images.githubusercontent.com/72089660/143966224-3f04f7cb-19dc-4244-831c-77ba2584f2ff.PNG)

Se crearon las siguientes clases , DOnde la clase principal es llamada escalonamientoC donde este esta extendido a traves de las siguientes funciones

![3](https://user-images.githubusercontent.com/72089660/143966340-f3ccdc37-8881-4a17-94bc-425bc2a477d9.PNG)





