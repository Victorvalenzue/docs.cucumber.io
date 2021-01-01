---
title: Introducción
subtitle: Nuevo en Cucumber? ¡Empieza aquí!
weight: 1000
---
Cucumber es una herramienta que soporta [Behaviour-Driven Development(BDD, por sus siglas en inglés)](/docs/bdd), que se refiere al proceso de desarrollo guiado por comportamiento.
Si el desarrollo guiado por comportamiento es nuevo para ti, lee nuestra [introducción a BDD](/docs/bdd) primero.

# ¿Qué es Cucumber?
Bien, ahora que sabes que BDD trata de descubrimiento, colaboración y ejemplos
(y no pruebas), vamos a echar un vistazo a Cucumber.

Cucumber lee especificaciones ejecutables escritas en texto plano y valida
que el software hace lo que la especificación dice. La especificación
consiste en múltiples *ejemplos* o *escenarios*. Por ejemplo:

```gherkin
Scenario: Breaker guesses a word
  Given the Maker has chosen a word
  When the Breaker makes a guess
  Then the Maker is asked to score
```

Cada escenario representa una lista de pasos que Cucumber debe seguir. Cucumber
verifica que el software cumpla con la especificación y genera un
reporte que indica  ✅ éxito o ❌ fracaso(success or failure) por cada escenario.

Para que cucumber pueda entender los escenarios, estos deben seguir ciertas
reglas de sintaxis básicas, llamadas [Gherkin](/docs/gherkin/).

# ¿Qué es Gherkin?

Es un conjunto de reglas gramaticales que hacen al texto plano lo suficientemente estructurado
para que Cucumber lo pueda entender. El escenario mostrado arriba está escrito en Gherkin.

Gherkin sirve para múltiples propósitos:

- Especificación ejecutable sin ambigüedades
- Pruebas automatizadas utilizando Cucumber
- Documentar cómo *actualmente* se comporta el sistema

![Single source of Truth](/img/single-source-of-truth-256x256.png)

La gramática de Cucumber existe en diferentes sabores para muchos [idiomas hablados](/docs/gherkin/reference#spoken-languages),
así su equipo puede utilizar las palabras clave (keywords) en su propio idioma.

Los documentos Gherkin son almacenados en archivos de texto con extensión `.feature` y son típicamente
versionados junto con el software mediante control de código fuente.

Mira la [referencia de Gherkin](/docs/gherkin) para más detalles.

# ¿Qué son las definiciones de pasos?

[Las definiciones de pasos](/docs/cucumber/step-definitions) conectan los pasos de Gherkin
con código de programación. Una definición de paso lleva a cabo la acción que debe
realizar el paso. Entonces, las definiciones de pasos conectan la especificación
con la implementación.

```
┌────────────┐                 ┌──────────────┐                 ┌───────────┐
│   Pasos    │                 │  Definición  │                 │           │
│ en Gherkin ├──coincide con──>│   de Pasos   ├───-manipula──-->│  Sistema  │
│            │                 │              │                 │           │
└────────────┘                 └──────────────┘                 └───────────┘
```

Las definiciones de pasos pueden ser escritas en muchos lenguajes de programación.
Aquí hay un ejemplo utilizando JavaScript:

```javascript
When("{maker} starts a game", function(maker) {
  maker.startGameWithWord({ word: "whale" })
})
```
