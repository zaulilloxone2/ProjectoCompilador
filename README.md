# Analizador Sintáctico 
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
En la clase de Seminario de Traductores 2 se nos pidió generar un pequeño analizador léxico y ahora uno sintactico, que identifique los tokens de las variasbles, numeros enteros, bucles y más.
### Metodología:

Debido a un problema con la implementación de la pila en el analizador sintáctico, decidí hablar con el maestro para establecer una nueva ruta siguiendo una metodología que ví que utiliza una librería externa para trabajar con las reglas y las producciones como si fuese un automata, esta librería se llama Ply, ply es muy vieja y de hecho fue diseñada para python 2.7, tiene un parser que nos ayuda a poder generar una tabla con la información.Cabe mencionar que la gramatica utilizada si difiere a la de C pero en su mayoría tenemos casi la estructura, debido a mi tiempo no pude adaptar mucho del codigo al estilo de C, pero sí la mayoría, escribí algunos programas de prueba que tengo en mi carpeta de pruebas la cual está en el repositorio
esta fue mi gramatica:![image](https://github.com/zaulilloxone2/ProjectoCompilador/blob/8f1b721e7e45292ac88eb62cefb00f17791d57d6/gramatica.png)

Aqui está el código que escribí para definir las producciones de la gramática:
![image](https://github.com/zaulilloxone2/ProjectoCompilador/blob/8e8284be77b1100f08807517d468c3cef68da0ec/Produciones%201.png)
![image](https://github.com/zaulilloxone2/ProjectoCompilador/blob/8e8284be77b1100f08807517d468c3cef68da0ec/produciones%202.png)

### Resultados:
Así nos recibe el programa en su menú, tiene la capacidad para reconor los archivos del sistema windows y darnos a elegir la prueba:
  ![image](https://github.com/zaulilloxone2/ProjectoCompilador/blob/8e8284be77b1100f08807517d468c3cef68da0ec/menu.png)
  
Aqui podemos ver como se corre el primer programa el cual es: 
![image](https://github.com/zaulilloxone2/ProjectoCompilador/blob/8e8284be77b1100f08807517d468c3cef68da0ec/pantalla2.png)

aqui hay un programa mal escrito y su error:
  ![image](https://github.com/zaulilloxone2/ProjectoCompilador/blob/8e8284be77b1100f08807517d468c3cef68da0ec/error.png)

### Problemas y Soluciones:
La documentación fue para python 2.7 y se retuvo que rehacer el código en su totalidad por que las funciones cambiaron mucho con el paso de los años.
Tuve que ponerme en contacto con el creador de PLY y el afortunadamente se encuentra trabajando desde hace dos años para poder llevar su librería a python 3.6 y más, por lo que conseguí su repositorio y logré reimplementar su biblioteca con éxito.

### Conclusiones:
Es un gran reto adptarse a todos estos cambios, sobre todo por que es la primera vez que uso python y además me estoy comenzando a adaptar a Github, si me llegué a trabar en el proceso y la verdad aprendí mucho, aprendí a utilizar las herramientas, a codificar en python y sobre todo a poder entender el analizador, ya que ahora tengo que ahcer el grande. En esta parte además quiero agregar que fue un gran reto reimaginar todo el procesos y tratart de adaptarse alo que un analizador sintáctico debe de hacer, pero me gustó y logré reinventarme y sacar el trabajo adelante
No hay que darse por vencido!!
