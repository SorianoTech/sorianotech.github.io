
- [1. Módulo 1. Contexto e introducción al curso](#1-m%C3%B3dulo-1-contexto-e-introducci%C3%B3n-al-curso)
  - [1.1. ¿Qué es la programación y en que sitios está presente?](#11-%C2%BFqu%C3%A9-es-la-programaci%C3%B3n-y-en-que-sitios-est%C3%A1-presente)
  - [1.2. Distintas modalidades y carreras profesionales](#12-distintas-modalidades-y-carreras-profesionales)
    - [1.2.1. Carreras profesionales](#121-carreras-profesionales)
  - [1.3. Concepto general de Programación Estructurada](#13-concepto-general-de-programaci%C3%B3n-estructurada)
    - [Diagramas de flujo](#diagramas-de-flujo)
  - [1.4. Concepto general de Programación Orientada a Objetos (POO)](#14-concepto-general-de-programaci%C3%B3n-orientada-a-objetos-poo)
    - [1.4.1. Objeto](#141-objeto)
    - [¿Qué es Java?](#%C2%BFqu%C3%A9-es-java)
    - [Los lenguajes interpretados y compilados](#los-lenguajes-interpretados-y-compilados)
    - [Servidores Java](#servidores-java)
    - [Frameworks Java](#frameworks-java)
  - [1.5. Programación Estructurada vs Programación Orientada a Objetos](#15-programaci%C3%B3n-estructurada-vs-programaci%C3%B3n-orientada-a-objetos)
  - [1.6. El proyecto CODE.ORG](#16-el-proyecto-codeorg)
  - [1.7. Recursos de estudio gratuitos](#17-recursos-de-estudio-gratuitos)

# 1. Módulo 1. Contexto e introducción al curso

## 1.1. ¿Qué es la programación y en que sitios está presente?

La programación viene del verbo programar, que en el ámbito tecnológico significa, según la RAE:

>Cada una de las operaciones que, en un orden determinado, ejecutan ciertas máquinas.

Hoy en día la programación esta en practicamente todos los
ámbitos de nuestra vida, desde la medicina, hasta la agricultura o desde la aeronaútica hasta los equipos que funcionan en los submarinos, desde las web donde compramos como amazon, hasta la información que consultamos y tramitamos en hacienda. Cualquier cosa que requiera de un procesamiento de datos, intercambio de información entre personas ubicadas en diferentes lugares o equipos que requieran de cálculos matemáticos tendrán presente la programación.

Es por este motivo que aunque hoy en día existen multitud de campos en donde se esta aplicando la programación, continua en crecimiento debido al aumento de la tendencia de utilizar dispositivos electrónicos e internet en nuestra vida cotidiana.

![Uso de internet](img\Grafica-2-usuarios-internet-incremento-con-los-años.jpg)
*Uso de internet en los últimos años

> Ejemplo de programación en java

```java
public class A {
    
    public Integer numeroEntero = new Integer(); /* Variable Global a todos los Métodos */
    
    public Integer método() {
        int num = 1; // Variable Local a método. Puede accederse dentro de este método en cualquier parte, pero no fuera del mismo.
        for (int i = 0;i<numeroEntero.intValue();i++) { // i es local al bucle for, sólo puede ser accedida dentro del mismo.
            num *= i;
        }
        // i = 2; Esta línea provocaría error al no haber declarado la variable i. i fue definida localmente al bucle for.
        return Integer.valueOf(num);
    }

    public void otroMetodo() {
        int num = 1; // Variable local a otroMetodo. num aquí es una variable distinta a la variable num de método
        System.out.println("Variable local num: " + num);
    }
}
```

## 1.2. Distintas modalidades y carreras profesionales

Para poder entender la programación podríamos dividirla en diferentes modalidades o carreras profesionales pero antes podemos realizar una división según su paradigma:

- Imperativa
  - Estructurados
  - Procedimental
  - OOP (Orientada a objetos)
  - otros
- Declarativa
  - Funcional/estructurado
  - Lógico
  - Otros

Otra forma de categorizar las modalidades de programación es según su interpretación:

- Interpretados
- Compilados

La principal diferencia entre un **lenguaje compilado** y uno **interpretado** es que el lenguaje compilado requiere un paso adicional antes de ser ejecutado, la compilación, que convierte el código que escribes a lenguaje de máquina. Un lenguaje interpretado, por otro lado, es convertido a lenguaje de máquina a medida que es ejecutado.

>Los lenguajes compilados transforman el código fuente en codigo máquina.

Un **lenguaje de programación** es un idioma artificial diseñado para expresar procesos que pueden reproducir máquinas. Se usan para crear programas que controlan el comportamiento físico y lógico de una máquina y para expresar algoritmos con precisión. Los llamamos lenguaje porque están formados por un conjunto de símbolos, reglas sintácticas y semánticas que definen su estructura y el significado de los elementos y expresiones.

![Lenguajes de Programación](img\Grafica-2-usuarios-internet-incremento-con-los-años.jpg)

### 1.2.1. Carreras profesionales

En el ámbito de la programación podemos diferenciar las siguientes especialidades:

- Programador (Java ,Cobol, C, C++ , C#,etc..)
- Analista/Consultor
- Analista/Programador
- Desarrollador WEB
  - Front-end
  - Back-end
- Analista de Sistemas
- Desarrollador de APPs para dispositivos móviles (Android, IOS)
- Desarrollador de Videojuegos y plataformas interactivas (UNITY)
- Jefe de proyecto 
- Dev-Ops
  
## 1.3. Concepto general de Programación Estructurada

Para realizar un programa estructurado existen tres tipos básicos de estructuras de
control:

- `Secuencial`: Ejecuta una sentencia detrás de otra.
- `Condicional`: Se evalúa una expresión y, dependiendo del resultado, se decide la
siguiente sentencia a ejecutar. (If, else if, switch)
- `Iterativa o bucle`: Repetimos un bloque de sentencias hasta que sea verdadera una
determinada condición. (do, while, for, do while)

`Diagramas de flujo`: Los diagramas de flujo nos permiten representar una sentencia mediante simbolos.

`Pseudocódigo`: es la representación de todas las intrucciones adaptadas a nuestro lenguaje.

En los avances de la programación estructurada aparecen la creación de módulos que consisten en agrupación de códigos que componen librerías. Estas librerías nos permiten ahorrarnos escribir de nuevo un código que puede ser reutilizado.

Por ejemplo para definir un programa de ajedrez lo podemos dividir en 3 módulos:

- Ajedrez
- Tablero
- Pieza

El contenido del fichero de libreríatablero.h sería:

```c
enum columnas { a, b, c, d, e, f, g, h };
struct tablero {
    int posx;
    enum columnas posy;
    struct pieza mipieza;
    struct tablero *siguiente;
}

int Final(struct tablero *mitablero);
void Inicio(struct tablero *mitablero);
int Pertenece(struct tablero *mitablero, int posx, enum columnas posy);
void Dibuja(struct tablero *mitablero);
int FueraTablero(struct tablero *mitablero, int x1, enum columnas y1, int x2, enumcolumnas y2);
int Valido_T(struct tablero *mitablero, int x1, enum columnas y1, int x2, enum columnas y2);

void Mover(struct tablero *mitablero, int x1, enum columnas y1, int x2, enum columnas y2);
```

[1]: bibliografia\programacion_estructurada.pdf

El fichero de declaración pieza.h incluiría el siguiente código:

```c
enum color { blanco, negro };
enum tipo { peon, torre, caballo, alfil, reina, rey }
struct pieza {
enum color micolor;
enum tipo mitipo;
}
int Valido_P(struct pieza *mipieza, int x1, int y1, int x2, int y2);
```

Al incluir los ficheros tablero.h y pieza.h podemos usar las funciones de los módulos a pesar de no conocer el código interno, solo debemos conocer como funcionan los objetos para utilizarlos.

## 1.4. Concepto general de Programación Orientada a Objetos (POO)

En el caso de los lenguajes orientados a objetos, como es el caso de C++ y Java, el
elemento básico no es la *función*, sino un ente denominado precisamente *objeto*. Un
objeto es la representación en un programa de un concepto, y contiene toda la
información necesaria para abstraerlo: datos que describen sus atributos y operaciones
que pueden realizarse sobre los mismos.

Los niveles de abstracción del POO son:

- Poliformismo
- Herencia
- Encapsulación
- Abstraccion
- Clases
- Objetos
- Métodos
- Paso de Mensajes

![abstraccion](img\OOPs-Concepts.jpg)

[Ejemplos](https://www.geeksforgeeks.org/object-oriented-programming-oops-concept-in-java/)

[2]: https://www.geeksforgeeks.org/object-oriented-programming-oops-concept-in-java/

Los veremos explicados más adelante.

### 1.4.1. Objeto

Un *objeto* no es más que un conjunto de variables (o datos) y métodos (o funciones)
relacionados entre sí. Los objetos en programación se usan para modelar objetos o
entidades del mundo real (el objeto hijo, madre, o farmacéutica, por ejemplo). Un objeto
es, por tanto, la representación en un programa de un concepto, y contiene toda la
información necesaria para abstraerlo: datos que describen sus atributos y operaciones
que pueden realizarse sobre los mismos. La siguiente figura muestra una representación
visual de un objeto.

![Clases y Objetos](img\objetos_clases.jpg)

[2]: bibliografia\ProgramacionOrientadaAObjetos.pdf

### ¿Qué es Java?

Java es un lenguaje multiplataform, desarrollado en 1995 por Sun Microsistems en concreto por James Gosling.

### Los lenguajes interpretados y compilados

Los lenguajes compilados requieren de un proceso antes de ser ejecutados. Eso quiere decir que antes de que puedan funcionar si hay alguna error en el codigo no se llegara a compilar. Sin embargo uno *interpretado* va ejecutando linea a linea.

>Los lenguajes compilados transforman el código fuente en codigo máquina.

**¿Qué lenguajes son compilados?**
C++, Go, Cobol

`Java` es intermedio, por que es compilado a bytecode no a código máquina.

Los programas en bytecode son interpretados por un interprete de bycode

Para correr las aplicaciones de Java se utiliza `Tomcat`.

Java Servlets y JSP (Java Server Pages)

Java Servlet entrega la página al cliente, la equivalencia en PHP sería APACHE, NGINX o lighttp.

### Servidores Java

- [Tomcat](http://tomcat.apache.org)
- [GlassFish](https://www.oracle.com/technetwork/es/middleware/glassfish/overview/index.html)
- OAS
- [WildFly (Antiguo Jboss)](https://wildfly.org/)
- I Planet (OiWS)
- Bea Weblogic

### Frameworks Java

Los Frameworks son herramientas que nos permiten reutilizar código para desarrollar de una forma mas rápida

**¿Qué frameworks se utilizan en Java?**

- [Hibernate](https://hibernate.org/)
- [Spring](https://spring.io/)

## 1.5. Programación Estructurada vs Programación Orientada a Objetos

La principal diferencia entre la estructurada y la orientada a objetos consiste en la forma en la que abstraemos los datos. La estructurada realiza una serie de ordenes de forma ordenada y no es posible acceder a datos predefinidos.

La programación orientada a objetos es mas avanzada ya que nos permite abstraernos a otra seríe de niveles.

## 1.6. El proyecto CODE.ORG

Es una organización sin ánimo de lucro que fomenta el aprendizaje de las ciencias de la computación haciendo la mas accesible y aumentar la participación de mujeres y minorías. Esta apoyada por Amazon, Facebook, Google, la Fundación de Infosys, Microsoft y muchos más.

El ofrece planes de estudios para primaria y secundaria.

Dispone de un catalogo de cursos gratuitos para diferentes edades.

- [Edad 4-11](https://code.org/educate/curriculum/elementary-school)
- [Edades 10-16](https://code.org/educate/curriculum/middle-school)
- [Edades 14-18+](https://code.org/educate/curriculum/high-school)

[Más información ](https://studio.code.org/courses)

También ofrece una sería de herramientas para crear aplicaciones, animaciones y juegos en Javascript( estos recursos están sólo disponible en ingles)

## 1.7. Recursos de estudio gratuitos

[CodeAcademy](http://www.codecademy.com/#!/exercises/0)

[Google Code University](http://code.google.com/edu/)

[Mozilla Developer Network](https://developer.mozilla.org/en-us/learn)

[Khan Academy](https://www.khanacademy.org/cs/tutorials/programming-basics)

[EloquentJavascript](http://eloquentjavascript.net/)

[Codeschool](http://www.codeschool.com/)