# Proyecto Compilador Final
![image](https://github.com/zaulilloxone2/Analizador_Lexico/blob/280971c8b4e514785cf26e6cecf40f1f4175a0ed/udg%20logo.jpg) 
#### Alumno: Saul Ezequiel García Ramos
#### Codigo: 215465492
#### Fecha: 05/12/2021
#### Materia: Seminario de Solucion de problemas de Traductores 2
#### Profesor: Michel Emanuel Lopez Franco
#### Sección: D02
#### Carrera: INCO
#### CENTRO UNIVERSITARIO DE CIENCIAS EXACTAS EN INGENIERÍAS CUCEI

### Ojetivo:
En la clase de Seminario de Traductores 2 se nos pidió generar un pequeño compilador que contendra un analizador léxico uno sintactico y uno semantico, que identifique los tokens de las variables, numeros enteros, bucles y más.
### Metodología:
## Analizador Léxico:
Primero que nada definimos nuestra lista de palabras reservadas y tokens:
![image](https://github.com/zaulilloxone2/ProjectoCompilador/blob/303d364dd49884860930ff95ac07d71fbb072104/Palabras%20reservadas.png)

Aqui es donde utilizamos la biblioteca RE para poder detectar las expresiones regulares, utilizamos el lenguaje de RE para los componentes de la gramatica y lo programamos así:

![image](https://github.com/zaulilloxone2/ProjectoCompilador/blob/303d364dd49884860930ff95ac07d71fbb072104/RE.png)

Cabe mencionar que reconoce los saltos de línea nuestro analizador Léxico

## Analizador Sintáctico:
Debido a un problema con la implementación de la pila en el analizador sintáctico, decidí hablar con el maestro para establecer una nueva ruta siguiendo una metodología que ví que utiliza una librería externa para trabajar con las reglas y las producciones como si fuese un automata, esta librería se llama Ply, ply es muy vieja y de hecho fue diseñada para python 2.7, tiene un parser que nos ayuda a poder generar una tabla con la información.Cabe mencionar que la gramatica utilizada si difiere a la de C pero en su mayoría tenemos casi la estructura, debido a mi tiempo no pude adaptar mucho del codigo al estilo de C, pero sí la mayoría, escribí algunos programas de prueba que tengo en mi carpeta de pruebas la cual está en el repositorio.
Esta fue mi gramatica:
![image](https://github.com/zaulilloxone2/ProjectoCompilador/blob/8f1b721e7e45292ac88eb62cefb00f17791d57d6/gramatica.png)

Aqui está el código que escribí para definir las producciones de la gramática:
![image](https://github.com/zaulilloxone2/ProjectoCompilador/blob/8e8284be77b1100f08807517d468c3cef68da0ec/Produciones%201.png)
![image](https://github.com/zaulilloxone2/ProjectoCompilador/blob/8e8284be77b1100f08807517d468c3cef68da0ec/produciones%202.png)

## Analizador Semántico:
Ahora Tenemos nuestro analizador Semántico, este es capaz de poder armar la tabla de estados y reducciones del programa que es ingresado como entrada, además cumple su función de generar 2 árboles sintácticos en este caso, el primero es en formato de identación y el segundo es en formato que reconocerá una página de apoyo llamada Graphviz, esta página nos ayudará a hacer todo mas visual, ahora muestro como tuve que crear clases para mandar objetos como parámetros y poderse imprimir en pantalla, tuve que hacer todas las funciones de las producciones a clases y agregarles dos funciones principales los cuales son la de imprimir y traducir, la función de imprimir nos ayudará a generar el árbol sintactico de identaciones y la de traducir nos ayudará a generar un archivo.vz el cual contiene el formato de apoyo de la página, ahora muestro el código de algunas funciones orque es muy extenso,pero la mayoría lucen igual:

![image](https://github.com/zaulilloxone2/ProjectoCompilador/blob/ae4393e47da9ed1306676e9fd59cc3833c23be81/funciones%20a%20clases.png)

### Resultados:
Así nos recibe el programa en su menú, tiene la capacidad para reconor los archivos del sistema windows y darnos a elegir la prueba:
  ![image](https://github.com/zaulilloxone2/ProjectoCompilador/blob/8e8284be77b1100f08807517d468c3cef68da0ec/menu.png)
  
Aqui podemos ver como se corre el primer programa el cual es:

![image](https://github.com/zaulilloxone2/ProjectoCompilador/blob/8e8284be77b1100f08807517d468c3cef68da0ec/pantalla2.png)

aqui hay un programa mal escrito y su error:

  ![image](https://github.com/zaulilloxone2/ProjectoCompilador/blob/8e8284be77b1100f08807517d468c3cef68da0ec/error.png)
 
 Ahora veemos el árbol sintáctictico identado que se generó del programa 1:
 
 ![image](https://github.com/zaulilloxone2/ProjectoCompilador/blob/ae4393e47da9ed1306676e9fd59cc3833c23be81/arbol%20sintactico%20formato%20identado.png)
 
 Y este es el árbol en el formato de graphviz antes de ser un grafo:
 
 ![image](https://github.com/zaulilloxone2/ProjectoCompilador/blob/ae4393e47da9ed1306676e9fd59cc3833c23be81/arbol%20sintatico%20formato%20graphvitz.png)
 
 Estas imagenes nos muestran las tablas de estados y las reduciones que muestras como se fue transformando la gramatica:
 
 ![image](https://github.com/zaulilloxone2/ProjectoCompilador/blob/ae4393e47da9ed1306676e9fd59cc3833c23be81/tabla%20de%20estados%20del%20analizador%20semantico%201.png)
 
 ![image](https://github.com/zaulilloxone2/ProjectoCompilador/blob/ae4393e47da9ed1306676e9fd59cc3833c23be81/tabla%20de%20estados%202.png)
 
 Estos son los árboles que se generan con la pagina web, hice varios ejemplos:
 
  ![image](https://github.com/zaulilloxone2/ProjectoCompilador/blob/ae4393e47da9ed1306676e9fd59cc3833c23be81/graphviz.png)
  
  ![image](https://github.com/zaulilloxone2/ProjectoCompilador/blob/ae4393e47da9ed1306676e9fd59cc3833c23be81/graphviz%20(2).png)
  
  ![image](https://github.com/zaulilloxone2/ProjectoCompilador/blob/ae4393e47da9ed1306676e9fd59cc3833c23be81/graphviz%20(3).png)
  
  ### GENERACIÓN DE CÓDIGO iNTERMEDIO Y COPILANDO EL CÓDIGO:
 La librería de Yacc tiene varios comandos interesantes y dentro de ellas hay una forma de convertir el parser a código de 3 vías. se uilizan dos nuevos archivos que descargué de su documentación y simplemente se añade a la entrada el programa que se recibe para ser transformado a código de 3 vías:
 aqui está la función que lo pasa:
 
 
 y así queda:
 
 
 
 
 y ejecutado se verá así, cabe mencionar que la biblioteca te deja el lenguaje ensamblador de salida de MIPS ASSembly
 

### Problemas y Soluciones:
La documentación fue para python 2.7 y se retuvo que rehacer el código en su totalidad por que las funciones cambiaron mucho con el paso de los años.
Tuve que ponerme en contacto con el creador de PLY y el afortunadamente se encuentra trabajando desde hace dos años para poder llevar su librería a python 3.6 y más, por lo que conseguí su repositorio y logré reimplementar su biblioteca con éxito.

### Conclusiones:
Es un gran reto adptarse a todos estos cambios, sobre todo por que es la primera vez que uso python y además me estoy comenzando a adaptar a Github, si me llegué a trabar en el proceso y la verdad aprendí mucho, aprendí a utilizar las herramientas, a codificar en python y sobre todo a poder entender el analizador, ya que ahora tengo que ahcer el grande. En esta parte además quiero agregar que fue un gran reto reimaginar todo el procesos y tratar de adaptarse a lo que un analizador sintáctico debe de hacer, pero me gustó y logré reinventarme y sacar el trabajo adelante. Del analizador Semántico una vez que ya teníamos lo previo pues fue muy fácil implementarlo, por el tiempo y complicaciones propias del sistema, la documentacion y demás creo que se logró muy bien el objetivo, espero poder compartir este proyecto con el maestro y que sea de su agrado
No hay que darse por vencido!!

### Referencias:
https://dreampuf.github.io/GraphvizOnline/
https://cs.wmich.edu/~yang/teach/cs485/pl0/pl0grammar.txt?fbclid=IwAR1Zw9Fjy_3yNX8n03iEpAbqak9O9Lz_KKWYa3pGcw8pSC0NL03TNDywz50

