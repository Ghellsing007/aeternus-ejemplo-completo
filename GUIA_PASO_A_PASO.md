# 🛠️ GUÍA PASO A PASO - PROYECTO EJEMPLO

## 🎯 OBJETIVO
Crear un proyecto Ranvier completo y funcional paso a paso, integrando todas las características de Aeternus-Orbis.

---

## 📋 PASO 1: CREAR LA ESTRUCTURA COMPLETA

# Crear toda la estructura de una vez
mkdir -p aeternus-ejemplo-completo/{bundles/aeternus-ejemplo/{commands,lib,areas/mundo-ejemplo,behaviors,effects,input-events,server-events,player-events},data/{account,player},log,util}

# Crear archivos de áreas
mkdir -p aeternus-ejemplo-completo/bundles/aeternus-ejemplo/areas/mundo-ejemplo

# Estructura visual completa:
aeternus-ejemplo-completo/
├── bundles/
│   └── aeternus-ejemplo/
│       ├── commands/           # Comandos del juego
│       ├── lib/               # Sistemas y librerías
│       ├── areas/             # Mundo del juego
│       │   └── mundo-ejemplo/
│       ├── behaviors/         # Comportamientos de NPCs/Items
│       ├── effects/           # Efectos temporales
│       ├── input-events/      # Eventos de entrada
│       ├── server-events/     # Eventos del servidor
│       ├── player-events/     # Eventos de jugador
│       ├── bundle-info.js     # Info del bundle
│       └── package.json       # Dependencias del bundle
├── data/
│   ├── account/              # Cuentas de usuario
│   └── player/               # Datos de jugadores
├── log/                      # Logs del servidor
├── util/                     # Utilidades
├── ranvier.json             # Configuración principal
├── package.json             # Dependencias del proyecto
└── README.md                # Documentación del ejemplo

### Comando para crear toda la estructura:
```bash
# Desde la carpeta aeternus-ejemplo-completo/
mkdir -p bundles/aeternus-ejemplo/{commands,lib,areas/mundo-ejemplo,behaviors,effects,input-events,server-events,player-events}
mkdir -p data/{account,player}
mkdir -p log util

# Crear archivos .gitkeep para mantener carpetas vacías
touch data/account/.gitkeep
touch data/player/.gitkeep  
touch log/.gitkeep
touch util/.gitkeep
```

### Verificar la estructura:
```bash
tree
# O en Windows:
dir /s
```

---

## 📋 PASO 2: CONFIGURACIÓN BASE

### 2.1 Crear bundle-info.js
```javascript
// bundles/aeternus-ejemplo/bundle-info.js
module.exports = {
  name: 'aeternus-ejemplo',
  title: 'Aeternus-Orbis Ejemplo Completo',
  author: 'Aeternus Team',
  description: 'Ejemplo completo que integra todas las funciones de Ranvier con Aeternus-Orbis'
};
```

### 2.2 Crear package.json del bundle
```json
// bundles/aeternus-ejemplo/package.json
{
  "name": "aeternus-ejemplo",
  "version": "1.0.0",
  "description": "Bundle de ejemplo completo para Aeternus-Orbis",
  "dependencies": {
    "humanize-duration": "^3.14.0"
  }
}
```

---

## 📋 PASO 3: CREAR LOS SISTEMAS CORE

### 3.1 Sistema de Vitae
```javascript
// bundles/aeternus-ejemplo/lib/vitae-system.js
// [Copiar el código completo del sistema de Vitae del proyecto principal]
```

### 3.2 Sistema de Supervivencia  
```javascript
// bundles/aeternus-ejemplo/lib/survival-system.js
// [Copiar el código completo del sistema de supervivencia]
```

### 3.3 Sistema de Combate
```javascript
// bundles/aeternus-ejemplo/lib/combat-system.js
// [Copiar el código completo del sistema de combate]
```

---

## 📋 PASO 4: CREAR EL MUNDO

### 4.1 Configurar el Área
```yaml
# bundles/aeternus-ejemplo/areas/mundo-ejemplo/manifest.yml
title: "Mundo de Ejemplo"
author: "Aeternus Team"
description: "Un mundo pequeño pero completo para demostrar todas las funciones"
level: [1, 10]
behaviors:
  progressive-respawn:
    interval: 60
```

### 4.2 Crear las Habitaciones
```yaml
# bundles/aeternus-ejemplo/areas/mundo-ejemplo/rooms.yml
- id: entrada
  title: "Entrada del Bosque Ejemplo"
  description: |
    Te encuentras en la entrada de un pequeño bosque que sirve como
    ejemplo de las mecánicas de Aeternus-Orbis. El aire vibra con
    energía Vitae y puedes sentir que este lugar es especial.
    
    Al norte se extiende un sendero serpenteante.
  exits:
    - direction: norte
      roomId: "mundo-ejemplo:sendero"
  items: ["mundo-ejemplo:cristal-tutorial"]
  npcs: []

- id: sendero  
  title: "Sendero Serpenteante"
  description: |
    Un sendero de tierra compactada serpentea entre árboles antiguos.
    La Vitae aquí fluctúa de manera visible, creando pequeños destellos
    de luz azulada en el aire. Puedes ir al sur para regresar o
    continuar al norte hacia una cámara misteriosa.
  exits:
    - direction: sur
      roomId: "mundo-ejemplo:entrada"
    - direction: norte  
      roomId: "mundo-ejemplo:camara"
  items: []
  npcs: ["mundo-ejemplo:guardian-ejemplo"]

- id: camara
  title: "Cámara de Cristal Ejemplo"
  description: |
    Una pequeña cámara circular con paredes de cristal que pulsan
    con energía Vitae. En el centro hay un altar que parece ser
    el corazón de este lugar. La energía aquí es intensa pero
    estable, perfecta para la meditación y el descanso.
  exits:
    - direction: sur
      roomId: "mundo-ejemplo:sendero"
  items: ["mundo-ejemplo:altar-ejemplo"]
  npcs: ["mundo-ejemplo:espiritu-ejemplo"]
  behaviors:
    sanctuary: true
```

### 4.3 Crear los NPCs
```yaml
# bundles/aeternus-ejemplo/areas/mundo-ejemplo/npcs.yml
- id: guardian-ejemplo
  name: "Guardián de Ejemplo"
  level: 5
  description: |
    Un guardián de cristal de tamaño mediano que protege el sendero.
    Sus ojos brillan con energía Vitae y parece estar evaluando
    tus intenciones. Es perfecto para practicar combate.
  keywords: ["guardian", "ejemplo", "cristal"]
  
  attributes:
    health: 80
    strength: 8
    dexterity: 6
    constitution: 10
    intelligence: 12
    wisdom: 14
    charisma: 6
  
  behaviors:
    combat: true
    wander: false
  
  dialogue:
    greeting: "El guardián te observa con curiosidad cristalina."
    combat_start: "¡El guardián resuena con energía defensiva!"
    death: "El guardián se fragmenta en cristales brillantes..."
  
  items: ["mundo-ejemplo:fragmento-ejemplo"]
  experience: 50

- id: espiritu-ejemplo
  name: "Espíritu Guía"
  level: 1
  description: |
    Un espíritu amigable que flota sobre el altar. Su propósito
    es ayudar a los nuevos viajeros a entender las mecánicas
    del mundo. Es completamente pacífico y muy informativo.
  keywords: ["espiritu", "guia", "ejemplo"]
  
  attributes:
    health: 100
    strength: 5
    dexterity: 15
    constitution: 8
    intelligence: 20
    wisdom: 22
    charisma: 18
  
  behaviors:
    combat: false
    merchant: false
    helpful: true
  
  dialogue:
    greeting: |
      "¡Bienvenido, viajero! Soy tu guía en este mundo de ejemplo.
      Puedes preguntarme sobre las mecánicas o simplemente explorar."
    help: |
      "Usa 'estado' para ver tus estadísticas, 'meditar' para
      restaurar Vitae, y 'examinar' para inspeccionar cosas."
  
  experience: 0
```

### 4.4 Crear los Items
```yaml
# bundles/aeternus-ejemplo/areas/mundo-ejemplo/items.yml
- id: cristal-tutorial
  name: "Cristal de Tutorial"
  description: |
    Un cristal especial diseñado para enseñar las mecánicas básicas.
    Al usarlo, restaura un poco de Vitae y te da información útil
    sobre el juego. Es perfecto para nuevos jugadores.
  keywords: ["cristal", "tutorial", "ejemplo"]
  
  type: consumable
  
  properties:
    stackable: true
    max_stack: 3
    weight: 0.1
    value: 10
  
  effects:
    vitae_restore: 10
    stability_boost: 5
    tutorial_message: true
  
  use_message: |
    El cristal se disuelve suavemente, enviando conocimiento
    directamente a tu mente junto con energía revitalizante.

- id: fragmento-ejemplo
  name: "Fragmento de Cristal Ejemplo"
  description: |
    Un pequeño fragmento que queda después de derrotar al guardián.
    Aunque es solo un ejemplo, aún contiene un poco de energía
    Vitae residual que podría ser útil.
  keywords: ["fragmento", "cristal", "ejemplo"]
  
  type: material
  
  properties:
    stackable: true
    max_stack: 5
    weight: 0.05
    value: 5
    rarity: "common"
  
  crafting:
    category: "basic-materials"
    tier: 1

- id: altar-ejemplo
  name: "Altar de Ejemplo"
  description: |
    Un altar simple pero funcional que demuestra las mecánicas
    de interacción con objetos del mundo. Puedes tocarlo para
    obtener beneficios o meditar cerca de él.
  keywords: ["altar", "ejemplo", "cristal"]
  
  type: furniture
  
  properties:
    moveable: false
    interactive: true
    weight: 500
    value: 0
  
  interactions:
    examine: |
      El altar tiene runas simples que explican las mecánicas
      básicas del juego. Es claramente educativo.
    
    touch: |
      Al tocar el altar, sientes una conexión con las mecánicas
      del juego. Todo se vuelve más claro.
    
    meditate: |
      Meditas junto al altar y sientes como tu comprensión
      del mundo se profundiza.
  
  effects:
    touch:
      vitae_restore: 5
      stability_boost: 3
    meditate:
      vitae_restore: 15
      stability_boost: 10
      corruption_cleanse: 5
  
  cooldown: 60
```

---

## 📋 PASO 5: CREAR COMANDOS ESENCIALES

### 5.1 Comando Estado
```javascript
// bundles/aeternus-ejemplo/commands/estado.js
// [Copiar el código completo del comando estado]
```

### 5.2 Comando Meditar
```javascript
// bundles/aeternus-ejemplo/commands/meditar.js
// [Copiar el código del comando meditar de la documentación]
```

### 5.3 Comando Examinar
```javascript
// bundles/aeternus-ejemplo/commands/examinar.js
// [Copiar el código del comando examinar de la documentación]
```

---

## 📋 PASO 6: EVENTOS Y COMPORTAMIENTOS

### 6.1 Eventos de Jugador
```javascript
// bundles/aeternus-ejemplo/player-events/login.js
'use strict';

const VitaeSystem = require('../lib/vitae-system');
const SurvivalSystem = require('../lib/survival-system');

module.exports = {
  listeners: {
    login: state => player => {
      // Inicializar sistemas únicos
      VitaeSystem.initializePlayer(player);
      SurvivalSystem.initializePlayer(player);
      
      // Mensaje de bienvenida
      player.sendMessage(`
🌟 ¡Bienvenido a Aeternus-Orbis Ejemplo! 🌟

Este es un mundo de ejemplo que demuestra todas las mecánicas.
Usa estos comandos para empezar:

📊 'estado' - Ver tus estadísticas
🧘 'meditar' - Restaurar Vitae y descansar  
🔍 'examinar <objeto>' - Inspeccionar cosas
🗺️ 'mirar' - Ver tu entorno
🚶 'norte/sur' - Moverte por el mundo

¡Explora y experimenta con todas las mecánicas!
      `);
    }
  }
};
```

### 6.2 Eventos del Servidor
```javascript
// bundles/aeternus-ejemplo/server-events/startup.js
'use strict';

module.exports = {
  listeners: {
    startup: state => {
      console.log('🌟 Aeternus-Orbis Ejemplo iniciado correctamente');
      console.log('📊 Sistemas cargados: Vitae, Supervivencia, Combate');
      console.log('🗺️ Mundo ejemplo: 3 habitaciones, 2 NPCs, 3 items');
      console.log('🎮 ¡Listo para jugar!');
    }
  }
};
```

---

## 📋 PASO 7: TESTING Y VERIFICACIÓN

### 7.1 Instalar Dependencias
```bash
npm install
```

### 7.2 Iniciar el Servidor
```bash
npm start
```

### 7.3 Conectar y Probar
```bash
# En otra terminal
telnet localhost 4000
```

### 7.4 Comandos de Prueba
```
# Crear personaje (seguir el proceso)
# Una vez en el juego:

estado          # Ver estadísticas
mirar           # Ver entorno
examinar cristal # Inspeccionar item
tomar cristal   # Tomar item
usar cristal    # Usar item
norte           # Ir al sendero
examinar guardian # Ver el NPC
atacar guardian # Iniciar combate
norte           # Ir a la cámara (después del combate)
examinar altar  # Ver el altar
tocar altar     # Interactuar
meditar         # Meditar para restaurar
```

---

## 📋 PASO 8: PERSONALIZACIÓN

### 8.1 Modificar Valores
- Cambiar estadísticas de NPCs
- Ajustar efectos de items
- Modificar descripciones

### 8.2 Agregar Contenido
- Crear nuevas habitaciones
- Añadir más NPCs
- Implementar nuevos items

### 8.3 Experimentar
- Modificar sistemas existentes
- Probar nuevas mecánicas
- Crear comandos personalizados

---

## 🎯 RESULTADO FINAL

Al completar todos los pasos tendrás:

✅ **Proyecto Ranvier completo y funcional**
✅ **Todos los sistemas de Aeternus-Orbis integrados**
✅ **Mundo pequeño pero completo para explorar**
✅ **Ejemplos prácticos de todas las mecánicas**
✅ **Base sólida para desarrollo futuro**

¡Perfecto para aprender, experimentar y desarrollar! 🌌⚡