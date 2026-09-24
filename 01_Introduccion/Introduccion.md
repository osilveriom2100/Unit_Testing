# Unit Testing

Las pruebas unitarias son aquellas que se realizan a nivel de código, es decir, se prueban funciones, métodos o pequeñas unidades de lógica para asegurar que funcionen correctamente. El objetivo principal es validar que cada pieza del sistema haga lo que se espera, de forma aislada y repetible.

Estas pruebas son fundamentales para detectar errores en etapas tempranas del desarrollo, reducir costos de corrección y mejorar la calidad del software. También ayudan a mantener el código más legible, mantenible y seguro ante cambios futuros.

## ¿Por qué son importantes?

Las pruebas unitarias permiten a los desarrolladores:

- detectar errores rápidamente
- corregir fallos antes de pasar a niveles de integración o producción
- evitar regresiones cuando se modifica el código
- mejorar la confianza al refactorizar
- documentar el comportamiento esperado de una función

## Frameworks y herramientas

Existen diferentes frameworks de pruebas unitarias para distintos lenguajes de programación. Algunos ejemplos populares incluyen:

- JUnit (Java)
- NUnit (.NET)
- PyTest (Python)
- Jest (JavaScript)

En Python, el módulo `unittest` es una biblioteca estándar que proporciona herramientas para crear y ejecutar pruebas unitarias. También se usa `pytest`, que es muy popular por su sintaxis clara y fácil de leer.

## Tipos de pruebas unitarias

Existen 3 tipos principales de pruebas unitarias:

1. Pruebas de caja negra: Se centran en probar la funcionalidad del código sin tener conocimiento de su estructura interna. Se basan en requisitos y especificaciones.
2. Pruebas de caja blanca: Se enfocan en examinar la estructura interna del código y verificar que todas las rutas posibles se ejecuten correctamente. Requieren conocimiento del código fuente.
3. Pruebas de caja gris: Combinan elementos de las pruebas de caja negra y blanca, evaluando tanto la funcionalidad como la estructura interna del código.

## Objetivo del Unit Testing

El unit test es un tipo de prueba que se centra en verificar el comportamiento de unidades individuales de código, como funciones o métodos, para asegurarse de que produzcan los resultados esperados.

Sus objetivos principales son:

1. Probar la funcionalidad de unidades individuales de código.
2. Verificar que las funciones o métodos produzcan los resultados esperados.
3. Detectar errores en etapas tempranas del desarrollo.
4. Facilitar la detección temprana de errores y mejorar la eficiencia del proceso.
5. Permitir identificar y corregir problemas de manera rápida.
6. Garantizar que los cambios realizados no introduzcan errores inesperados.

## Principios básicos

Una prueba unitaria debe ser:

- pequeña
- rápida
- aislada
- reproducible
- fácil de entender

En general, cada prueba debe validar un solo comportamiento y no depender de otros módulos o servicios externos.

## Ejemplo en Python

```python
# archivo: operaciones.py

def sumar(a, b):
    return a + b
```

```python
# archivo: test_operaciones.py
import unittest
from operaciones import sumar

class TestOperaciones(unittest.TestCase):
    def test_sumar_dos_numeros(self):
        resultado = sumar(2, 3)
        self.assertEqual(resultado, 5)

    def test_sumar_numeros_negativos(self):
        resultado = sumar(-2, 3)
        self.assertEqual(resultado, 1)

if __name__ == "__main__":
    unittest.main()
```

En este ejemplo, la prueba verifica que la función `sumar` devuelva el resultado esperado para distintos casos.

# Integration Testing

Las pruebas de integración se centran en verificar la interacción entre diferentes módulos o componentes del software para asegurarse de que funcionen correctamente juntos. Estas pruebas son importantes porque permiten identificar problemas de comunicación, compatibilidad y flujo de datos entre distintos elementos del sistema.

A diferencia de las pruebas unitarias, aquí se prueba cómo interactúan varias partes del sistema, no cada parte por separado.

## Ejemplo de integración

Supongamos que un sistema tiene:

- una capa de acceso a datos
- una lógica de negocio
- una capa de presentación

Una prueba de integración podría validar que el sistema recupere datos desde la base de datos y los procese correctamente antes de mostrarlos al usuario.

Existen diferentes enfoques para realizar pruebas de integración, como:

- Pruebas de integración de arriba hacia abajo: Se comienza probando los módulos de nivel superior y luego se integran gradualmente los de nivel inferior.
- Pruebas de integración de abajo hacia arriba: Se inicia probando los módulos de nivel inferior y luego se integran gradualmente los superiores.
- Pruebas de integración de tipo "sandwich": Combina ambos enfoques, probando simultáneamente módulos de nivel superior e inferior.

# UI Test End to End

Las pruebas de interfaz de usuario (UI) de extremo a extremo se centran en evaluar la funcionalidad completa de una aplicación desde la perspectiva del usuario final. Estas pruebas simulan escenarios reales de uso, verificando que todas las interacciones con la interfaz funcionen correctamente y que el flujo de trabajo sea coherente.

Estas pruebas son importantes porque permiten garantizar que la experiencia del usuario sea satisfactoria y que la aplicación cumpla con requisitos funcionales y de usabilidad.

## Herramientas comunes

Existen diferentes herramientas y frameworks para realizar pruebas de UI de extremo a extremo, como:

- Selenium: Popular para automatizar pruebas en aplicaciones web.
- Cypress: Framework sencillo y rápido para pruebas front-end.
- TestCafe: Permite escribir pruebas para aplicaciones web con buena experiencia de ejecución.
- Puppeteer: Biblioteca de Node.js para controlar navegadores basados en Chromium.
- Playwright: Framework moderno para automatizar pruebas en varios navegadores.

## Ejemplo de escenario E2E

Un caso típico sería:

1. abrir la aplicación web
2. iniciar sesión
3. navegar a una sección
4. completar un formulario
5. guardar cambios
6. verificar que se muestra un mensaje de éxito

# Pirámide de pruebas de software

La pirámide de pruebas de software es un concepto que representa la proporción y el enfoque de las diferentes pruebas que se deben realizar en un proyecto. La pirámide se divide en tres niveles principales:

1. Pruebas unitarias (base de la pirámide): Son las más numerosas y se centran en validar unidades pequeñas de código. Son rápidas y económicas de ejecutar.
2. Pruebas de integración (nivel intermedio): Verifican que diferentes componentes trabajen juntos de forma correcta.
3. Pruebas de interfaz de usuario (UI) de extremo a extremo (cima de la pirámide): Son las menos numerosas, pero simulan escenarios reales y son más lentas y costosas.

La pirámide de pruebas enfatiza que debe haber más pruebas unitarias que de integración y todavía menos pruebas E2E. Esto ayuda a optimizar tiempo, esfuerzo y recursos, mientras se mantiene una cobertura sólida de calidad.

## Buenas prácticas

- escribir pruebas simples y claras
- probar casos positivos y negativos
- usar nombres descriptivos para cada prueba
- evitar dependencias externas innecesarias
- mantener las pruebas rápidas y aisladas

## Resumen

En resumen, las pruebas unitarias son la base de la calidad en el desarrollo de software. Permiten validar el comportamiento de funciones y métodos de forma aislada, detectar errores tempranamente y reducir riesgos cuando el código evoluciona.

Cuando se combinan con pruebas de integración y pruebas de UI, se obtiene una estrategia de testing mucho más robusta y confiable.

