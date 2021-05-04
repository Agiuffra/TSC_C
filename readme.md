#Intro a C

##Ventajas
* Lenguaje de programación de propósito general.
* Es de nivel más bajo que la mayoría, más flexible.
* Permite la creación de programas detallados y compactos.
* Un vasto ecosistema y portabilidad

##Estructura del Programa
* Realiza una tarea en particular.
* Finaliza con ";".
* Las funciones pueden llamarse desde otras funciones.
* Solo hay un "main".
* Los comentarios son para aclarar el programa.

##Fundamentos:
###Funciones
Todas las funciones tienen un tipo de retorno y uno o varios argumentos. Estas deben comenzar con una letra del alfabeto o "_".

**retrono nombre_funcion(argumento)**

```
int main(void)
{
    /* cuerpo de
     * la función */
}

float division(int a, int b)
{
    return (a/b);
}
```

Es recomendable declarar funcion, especificando los argumentos y el tipo de dato que devuelve.

```
#include "main.h"

unsigned int i;
float division(int a, int b);

int main(void)
{
    division(2, 3);
}

float division(int a, int b)
{
    return (a/b);
}
```

###Variables
Al declarar una variable, se debe especificar el tipo antes del nombre. Estos siguen las mismas reglas que las funciones.

tipo|tamaño bits|rango de valores
----|-----------|----------------
char|8|-128 a 127
unsigned char|8|0 a 256
short|16|-32.768 a 32.767
unsigned short|16| 0 a 65535
int|32|-2147483648 a 2147483647
unsigned int|32|0 a 4294967295
long|32|-2147483648 a 2147483647
unsigned long|32|0 a 4294967295
float|32|1.175494351e-38 a 3.40282347e+38
double|64|2.22507385850720138e-308 a 1.79769313486231571e+308

Inicializar es asignar el primer valor a una variable.

```
unsigned int dia=20, mes=4, year=2021;
```

Es posible cambiar el tipo de variable con **(tipo) variable**.

```
float voltaje;
...
    voltaje = ((float)v_adc)*(3.3/4096);
```

Las variables globales se inicializan afuera de cualquier función. Mientras que las locales, dentro de donde se vayan a utilizar. Si hay dos variables con el mismo nombre, la última variable tiene prioridad.

Hay tipos de variables relacionados con el almacenamiento:
* **extern**: se puede utilizar una variable global en archivos distintos.
* **static**: las variables locales mantinen su valor aunque se vuelvan a inicializar. Los globaes se definen como "static" automáticamente.

###Operadores
* aritméticos
  +|-|*|/|%
  -|-|-|-|-
* de comparación
  ==|!=|>|<|>=|<=
  --|--|-|-|--|--
* asignación
  =|++|--|+=|-=|*=|/=|%=
  -|--|--|--|--|--|--|--
* lógicos
  and|or|not
  ---|--|---
* bit a bit
  I|^|&|~|I=|^=|&=
  -|-|-|-|--|--|--
* desplazamiento
  >>|<<|>>=|<<=
  --|--|---|---

###Decisiones
```
if(condicion)
{
} else 
{
}

if(x >= 10)
    x--;

condicion ? suceso : caso contrario

switch(variable)
{
    case A:
        send();
        break;
    case B:
        break;
    case C:
        break;
    default: ...
}
```

###Bucles
```
while(var<10)
{
    var++;
}

do{
    var++;
} while(var<10);

for(int i=0;i<50;i++)
{
    /*codigo*/
}
```

###Directivas de Preprocesador
"include" se utiliza para incluir archivos externos. "define" es par definir macros, convierten fragmentos de código en palabras breves.

```
#include <stdlib.h> // Directorio del compilador.
#include "main.h"   // Directorio del proyecto.

#define PI 3.14159
#define MAX(a,b) (a<b) ? (b) : (a)
```

###Punteros
Un puntero contiene la dirección de memoria de una variable. Utiliza los operadores * y &.

```
int var1 = 123, var2;
int *var_ptr;

int main(void)
{
    while(1)
    {
        var_ptr=&var1;
        var2=*var_ptr;  //var2=123
    }
}
```

###Arreglos
```
int Array[2];
...
    Array[0]=1;
    Array[1]=5;

int Array[2] = {69,12};
char Array[2][2] = 
{
    {'A','B'},
    {'C','D'}
};
```

###Cadenas
```
char string1[] = "Cadena como arreglo \n";
char *string2[] = "Cadena como puntero \n";
```

###Estructura de Datos
```
struct Datos_persona
{
    char nombre[20];
    char apellido[50];
    unsigned char edad;
};

struct Datos_persona estudiante1;
struct Datos_persona estudiante2;

estudiante1.nombre = "Alessandro";
estudiante2.apellido = "Giuffra";

Datos_persona estudiante3 = {
    "Alessandro",
    "Giuffra",
    21
};
```