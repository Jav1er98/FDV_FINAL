## Práctica 7: Generación de Tile maps.
## Objetivo: Pruebas con las herramientas de Unity para la generación de mapas de tiles.

1. Obtener assets que incorpores a tu proyecto para la generación del mapa: planos e isométricos.

     - los assets utilizados han sido proporcionados por la profesora y se tratan de los siguientes: "2D Ice World" y "Isometric Medieval Pack".
       
      ![Paso 1](gifs/Captura1.png)
      
2. Generar al menos 2 paletas para crear un mapa rectangular. 

     - En el mapa rectangular he generado 3 paletas en las cuales tenemos Ground que se trata del suelo por donde caminaran los sprites, a esta  paleta se le ha incorporado un TileMap Colider junto a un Composer Colider para que pueda caminar y saltar el sprite del zombie, luego la capa Snow para colocar la nieve por encima del hielo y Decoration se tratan de elementos decorativos como los arboles.
     
      ![Paso 2](gifs/Captura2.png)

3. Crear un mapa isométrico.

     - En el mapa isometrico elegimos los elementos que queremos usar para la generación del mapa y empezamos a colocarlos, aqui hemos generado dos paletas para el suelo y los elementos decorativos.
      
      ![Paso 3](gifs/Captura6.png)
      
      ![Paso 4](gifs/Captura5.png)
      
4. En el mapa convencional, incluir obstáculos y paredes.

     - Utilizando los elementos que disponen el asset he generado alguna plataforma para el mapa.
      
      ![Paso 5](gifs/Captura3.png)
      
5. En el mapa isométrico generar zonas elevadas y obstáculos.

     - Colocamos una montaña para generar esa zona elevada como obstaculo también.
     
      ![Paso 6](gifs/Captura7.png)
      
6. Seleccionar sprites para usar como decoración y sprites animados para usar como personaje y como enemigos e incorporarlos al juego  y controlar mediante scripts al menos dos transiciones de animación en el personaje y una de un enemigo

     - Utilizando los sprites y los scripts de la práctica anterior, más los elementos que disponemos en estos assets cumplimentamos este apartado.
      
      ![Paso 7](gifs/Captura4.png)
      
      ![Paso 8](gifs/gif1.gif)
      
7. Incorpora elementos físicos en tu escena que respondan a las siguientes restricciones:

    1. Objeto estático que ejerce de barrera infranqueable
      
      - En este caso he colocado un cubo de hielo con un Rigidbody  Static y un Box Collider 
      
     ![Paso 9](gifs/Ejercicio1.gif)
    
    2. Zona en la que los objetos que caen en ella son impulsados hacia adelante
     
     - He colocado una zona transparente con el sprite de un cuadrado con un collider y siendo "isTrigger" de modo que cuando un objeto entra se activa el evento OnTriggerStay2D() empuja con un AddForce al objeto que este.
    
     ![Paso 10](gifs/Ejercicio2.gif)
    
    3. Objeto que es arrastrado por otro a una distancia fija
     
     - Agregando un Distance Joint 2D a un objeto estático, en este caso el cubo de hielo y lo conectamos con otro dinámico, en este caso el caramelo.
     
     ![Paso 11](gifs/Ejercicio3.gif)
    
    4. Objeto que al colisionar con otros sigue un comportamiento totalmente físico.
    
    - Añado un Rigidboy dinamico a un cubo de hielo y el zombie ejerce una fuerza para impulsarlo.
    
     ![Paso 12](gifs/Ejercicio4.gif)
    
    5. Incluye dos capas que asignes a diferentes tipos de objetos y que permita evitar colisiones entre ellos.
      
      - Añdo 3 cubos de hielo con 3 layer diferentes (layer1, layer2 y layer3), despues en  Project settings y en Physiscs 2D ajustamos las colisiones entre layers.
      
     ![Paso 13](gifs/Captura8.png)
     
     ![Paso 14](gifs/Ejercicio5.gif)
     
    
