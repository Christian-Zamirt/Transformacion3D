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

## Aplicado en java

librerias utilizadas en el programa

![1](https://user-images.githubusercontent.com/72089660/143966224-3f04f7cb-19dc-4244-831c-77ba2584f2ff.PNG)

Se crearon las siguientes clases , Donde la clase principal es llamada escalonamientoC donde este esta extendido a traves de las siguientes funciones

![3](https://user-images.githubusercontent.com/72089660/143966340-f3ccdc37-8881-4a17-94bc-425bc2a477d9.PNG)

En la primera funcion se describe el cuerpo del programa asi como tambien es donde a traves del codigo podemos modificar ya sea la traslacion en el eje de las 'x' o bien en el de la 'y' tambien la profundidad o comunmente llamado en las matematiccas el eje de la 'z'


![4](https://user-images.githubusercontent.com/72089660/143991754-227ffd86-cbb1-48eb-93f6-48af65f28cbe.PNG)

En la siguiente función es donde se crea el cubo, y para poder hacer la siguiente transformacion que es la rotación, esto se va a lograr a traves de la clase TransformGroup, tambien denotar que  se dan permiso para que pueda cambiar el comportamiento de objetoGiro en tiempo de ejecución abajo de estos perminsos se esta agragando el objetoGiro que es del tipo TransformGroup al objeto raiz qu es de tipo BranchGroup. Hya que resaltar el uso de dos clases que nos van a permitir completar el giro(rotacion), la primera clase es Alpha este nos proporciona una base de tiempo que puede ser utilizada por un objeto que es de la clase RotationInterpolator para generar una animacion en este universo, en la clase rotacionAlpha se le agregan los parametros -1 este para que se vaya repitiendo el giro y 4000 que son milisegundos en segundos esta cantidad seria 4 segundos. los parametros de la clase rotacionAlpha van a ser utilizados por el objeto de la clase RotationInterpolator que se usa para prporcionar animaciones de objetos, por ejemplo cambios de localizacion, orientacion, tamaños ,rotaciones, entre otros comportamientos, ya en este objeto de la clase RotationInterpolator se relacionan con los objetos tipo alpha rotacionAlpha y objeto de tipo TransformGroup objetoGiro, para que la rotacion funcione se agrega la siguiente linea rotacion.setSchedulingBounds(new BoundingSphere()); esta linea esta ocupando un objeto de BoundingSphere que es una esfera logica que no se puede ver pero esta esta ligada a unas geometrias que esten ligadas al TransformGroup objetoGiro.


![2](https://user-images.githubusercontent.com/72089660/143995928-3a3c9fc4-cab8-449f-8119-579155686479.PNG)

el main

![6](https://user-images.githubusercontent.com/72089660/143996404-87149394-793b-4d0c-a473-8f63bfe2192d.PNG)


Los resultados

en esta parte se ven los cambios de la profundidad o bien el escalonamiento en el eje de la z, tambien cabe racalcar que el cubo esta girando hacia la derecha de forma automatica asi que se esta ocupando dos transformaciones, las cuales son rotacion y escalonamiento.
![resul1](https://user-images.githubusercontent.com/72089660/143996443-9b14364d-2e98-4d2c-abda-a7a15eb159d8.PNG)

![resul2](https://user-images.githubusercontent.com/72089660/143996572-110be9cd-ad91-4fbf-afda-f5502823bd71.PNG)

en esta parte podemos ver la traslacion del objeto por los ejes x y y

![resul2](https://user-images.githubusercontent.com/72089660/143996986-6aa110aa-63fd-44f4-ae25-4bf514ca7ff8.PNG)

![resul3](https://user-images.githubusercontent.com/72089660/143997002-85a1fc63-2267-4e25-9bc5-4261acb4dfb8.PNG)

![resul34](https://user-images.githubusercontent.com/72089660/143997069-43245193-d50e-4245-9e20-eab4d9fe3995.PNG)

![d](https://user-images.githubusercontent.com/72089660/143997165-305f9403-546e-4841-84dc-387511c25bba.PNG)

![z](https://user-images.githubusercontent.com/72089660/143997381-a0eb3ef5-521d-4a1a-bc99-c50b2b51f020.PNG)

nota: para este programa es indispensable la libreria de java3D



