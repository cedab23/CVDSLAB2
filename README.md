# Laboratorio #2 CVDS

### Integrantes:
- Juan Andres Rodriguez Peñuela
- Nicolas Pachon Unibio

### Preguntas

#### Cuál es su mayor utilidad

Maven tiene como principal utilidad que permite el manejo de librerias utilizadas en java, generando que a la hora de trabajar en proyectos entre dos o mas personas, no se generen conflictos en sus librerias y se trabajen con la misma version y asimismo, bajo el mismo estandar.

#### Fases de maven y ciclo de vida en la construcción

El ciclo de vida en un proyecto en maven se define por sus fases, cada una encargada de una actividad diferente con el fin de garantizar el buen manejo de un proyecto, siendo las siguientes fases:

- **Validate:** Encargado de verificar que la informacion presente en el proyecto este correcta.

- **Compile:** Compila el codigo fuente presente en el proyecto.

- **Test:** Realiza las respectivas pruebas de unidad en el codigo compilado.

- **Package:** Tiene como funcionalidad el empaquetar el codigo en su respectivo ejecutable.

- **Verify:** Realiza los respectivos tests de integracion para confirmar que se ha cumplido con los requerimentos de cualidad solicitados.

- **Install:** Instala el paquete en el respectivo repositorio local para ser usaco domo dependencia en otros proyectos guardados de forma local.

- **Deploy:** Finalmente, copia el paquete final en el repositorio remoto para que pueda ser compartido y usado por otros desarrolladores o proyectos.


#### Para que sirven los plugins

Los plugins son las palabras clave, o mejor dicho comandos, que se realizan en la consola con la finalidad de que maven ejecute una instruccion en el proyecto o carpte en el que se encuentre presente, estos se dividen en dos tipos, siendo el primero el de construccion y el segundo el de reportes.

#### Qué es y para qué sirve el repositorio central de maven

El repositorio central de maven es, como el nombre indica, un repositorio que tiene la distincion de ser un lugar donde se pueden encontrar librerias y artefactos presentes en proyectos de maven, sirve para manejar elementos en los repositorios locales tales como las dependencias, compatibilidad y versiones de librerias.

### Crear un proyecto con maven

Para generar un proyecto en maven basado en arquetipos se debe tener en cuenta que los comandos seran realizados desde el cmd, siendo especificamente el comando **mvn archetype: create** que es utilizado para generar proyectos basades en unos paramteros, en esta coasion siendo los siguientes:

- ProjectId
- GroupId
- ArtefactId
- Package

Dando como resultado el siguiente comando:

![cmd](images/creationProjectCommand.png)

Y por consecuente, se presento el siguiente resultado indicando que fue añadido satisfactoriamente:

![proyectoMaven](images/folders.png)

El cual posee la siguiente estructura de arbol:

![arbol](images/treeFiles.png)
![arbol](images/treeFolders.png
) 

### Ajustar algunas configuraciones en el proyecto

Se añadieron las configuraciones mencionadas en la ultima seccion de properties.

#### Antes

![Pom](images/PomOriginal.png)

#### Despues

![cambioPom](images/PomChange.png)

### Compilar y ejecutar

Al ultilizar el commando "**mvn package**" nos demostro la siguiente pantalla, por lo cual no fue necesario hacer uso del "**-U**" al tener las dependencias actualizadas. Posteriormente se ejecuto el archivo "**App.java**" bajo el siguiente comando:

![compilacion](images/CompilacionMaven.png)

asimismo, la version extendida de dicho comando sin modificar el pom.xml seria el siguiente:

![compilacionFull](images/mvn-exec-complete.png)


Esto nos brindo el "Hello World!" por defecto presente en el archivo, el cual modificamos para que acepte un argumento de entrada, en este caso el nombre del usuario.

![primeraEjecucion](images/CompilacionArgumento.png)
![primeraEjecucionJuan](images/personalizatedMessage1.png)

Luego la problematica que surgio es que al separar con un espacio el nombre y apellido, este contaba como argumentos distintos y no uno solo, para arreglar se hace el uso de comilllas simples (  **' '**  ) para tomarlo como un solo argumento incluyendo sus espacios, dandonos el siguiente resultado:

![segundaEjecucion](images/mavenCompleto.png)
![segundaEjecucionJuan](images/personalizatedMessage2.png)

En caso de no añadir las comillas simples, no tomaria el apellido como parte del mismo argumento y solo saludaria con el nombre como en la siguiente situación:

![problemaSaludo](images/personalizatedMessageNoCompose.png)

### Hacer esqueleto de la aplicación

Las carpetas añadidas realizaron el siguiente cambio en el arbol del proyecto:

![TreeComplete](images/TreeShapes.png)

una vez realizados los *.java* solicitados, se procedio a ejecutrar los comandos solicitados, dandonos los siguientes resultados:

#### Sin parametro

![NoParameter](images/NoParameter.png)

Esta se ejecuta correctamente, puesto que en el codigo suministrado hay un manejo del caso de un parametro vacio, siendo este el mensaje de error de necesitar dicho parametro.

#### Parametro: qwerty

![qwerty](images/QwertyParameter.png)

Esta se ejecuta correctamente, puesto que en el codigo suministrado hay un manejo del caso de un parametro incorrecto, siendo este el mensaje de error de que "qwerty" no es uno de los tipos validos como parametro.

#### Parametro: Pentagon

![Pentagon](images/PentagonParameter.png)

Esta se ejecuta correctamente, generando un objeto tipo pentágono asociado a su cantidad de lados, el cual se muestra en el mensaje donde menciona su correcta creacion con 5 lados. 

#### Parametro: Hexagon

![Hexagon](images/HexagonParameter.png)

Esta se ejecuta correctamente, generando un objeto tipo hexágono asociado a su cantidad de lados, el cual se muestra en el mensaje donde menciona su correcta creacion con 6 lados. 

Para lograr la correcta ejecución de este codigo, se utilizo el patron de diseño de "simple factory" al tener en cuenta que no tendria una alta escalabilidad como proyecto y asimismo al tratarse de una practica de patrones de diseño asumimos que era mas factible realizarlo con la metodologia de la "simple factory".



