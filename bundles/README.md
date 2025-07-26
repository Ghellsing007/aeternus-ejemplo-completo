# 🎮 AETERNUS-ORBIS - EJEMPLO COMPLETO

## 📋 ¿QUÉ ES ESTE PROYECTO?

Este es un **proyecto ejemplo completo y limpio** de Aeternus-Orbis que integra todas las funciones de Ranvier con ejemplos prácticos. Perfecto para entender cómo funciona todo integrado.

---

## 📁 ESTRUCTURA COMPLETA DEL PROYECTO

```
aeternus-ejemplo-completo/
├── bundles/
│   └── aeternus-ejemplo/
│       ├── commands/           # Comandos del juego
│       ├── lib/               # Sistemas únicos (Vitae, Supervivencia, etc.)
│       ├── areas/             # Mundo del juego
│       │   └── mundo-ejemplo/
│       ├── behaviors/         # Comportamientos de NPCs/Items
│       ├── effects/           # Efectos temporales
│       ├── input-events/      # Eventos de entrada del jugador
│       ├── server-events/     # Eventos del servidor
│       ├── player-events/     # Eventos de jugador
│       ├── bundle-info.js     # Configuración del bundle
│       └── package.json       # Dependencias del bundle
├── data/
│   ├── account/              # Cuentas de usuario
│   └── player/               # Datos de jugadores
├── log/                      # Logs del servidor
├── util/                     # Utilidades del servidor
├── ranvier.json             # Configuración principal
├── package.json             # Dependencias del proyecto
└── README.md                # Esta documentación
```

## 🛠️ CREAR TODA LA ESTRUCTURA

### Comando Único para Crear Todo:
```bash
# Ejecutar desde la carpeta aeternus-ejemplo-completo/
mkdir -p bundles/aeternus-ejemplo/{commands,lib,areas/mundo-ejemplo,behaviors,effects,input-events,server-events,player-events}
mkdir -p data/{account,player}
mkdir -p log util

# Crear archivos .gitkeep para mantener carpetas vacías
touch data/account/.gitkeep
touch data/player/.gitkeep  
touch log/.gitkeep
touch util/.gitkeep
```

### Estructura Visual Detallada:
```
📁 aeternus-ejemplo-completo/
├── 📁 bundles/                    # Módulos del juego
│   └── 📁 aeternus-ejemplo/       # Nuestro bundle de ejemplo
│       ├── 📁 commands/           # Comandos que pueden usar los jugadores
│       │   ├── 📄 estado.js       # Ver estado del personaje
│       │   ├── 📄 meditar.js      # Comando para meditar
│       │   └── 📄 examinar.js     # Examinar objetos/NPCs
│       ├── 📁 lib/                # Sistemas únicos del juego
│       │   ├── 📄 vitae-system.js # Sistema de energía Vitae
│       │   ├── 📄 survival-system.js # Sistema de supervivencia
│       │   └── 📄 combat-system.js   # Sistema de combate
│       ├── 📁 areas/              # Mundo del juego
│       │   └── 📁 mundo-ejemplo/
│       │       ├── 📄 manifest.yml    # Configuración del área
│       │       ├── 📄 rooms.yml       # Habitaciones
│       │       ├── 📄 npcs.yml        # Personajes no jugadores
│       │       └── 📄 items.yml       # Objetos del mundo
│       ├── 📁 behaviors/          # Comportamientos especiales
│       ├── 📁 effects/            # Efectos temporales (buffs/debuffs)
│       ├── 📁 input-events/       # Eventos cuando el jugador escribe
│       ├── 📁 server-events/      # Eventos del servidor (startup, etc.)
│       ├── 📁 player-events/      # Eventos del jugador (login, etc.)
│       ├── 📄 bundle-info.js      # Información del bundle
│       └── 📄 package.json        # Dependencias específicas
├── 📁 data/                       # Datos guardados del juego
│   ├── 📁 account/               # Cuentas de usuario
│   └── 📁 player/                # Datos de personajes
├── 📁 log/                       # Archivos de log del servidor
├── 📁 util/                      # Utilidades del servidor
├── 📄 ranvier.json              # Configuración principal de Ranvier
├── 📄 package.json              # Dependencias del proyecto
└── 📄 README.md                 # Esta documentación
```

---

## 🎯 ¿QUÉ INCLUYE ESTE EJEMPLO?

### ⚡ Sistemas Únicos Implementados:
- **Sistema de Vitae:** Energía que mantiene unido el plano fragmentado
- **Sistema de Supervivencia:** Hambre, sed y fatiga
- **Sistema de Combate:** Peleas con modificadores únicos
- **Sistema de Permadeath:** Muerte permanente con beneficios

### 🗺️ Mundo de Ejemplo:
- **3 habitaciones conectadas** con descripciones inmersivas
- **2 NPCs únicos** (uno hostil, uno pacífico)
- **3 tipos de items** (consumible, material, interactivo)
- **Conexiones lógicas** entre todas las áreas

### 🛠️ Comandos Funcionales:
- `estado` - Ver estadísticas completas del personaje
- `meditar` - Restaurar Vitae y reducir fatiga
- `examinar` - Inspeccionar objetos y NPCs detalladamente
- Todos los comandos básicos de Ranvier

---

## 🚀 CÓMO USAR ESTE EJEMPLO

### 1. Instalar Dependencias:
```bash
npm install
```

### 2. Iniciar el Servidor:
```bash
npm start
```

### 3. Conectar al Juego:
```bash
# En otra terminal
telnet localhost 4000
```

### 4. Comandos de Prueba:
```
# Ver tu estado
estado

# Mirar alrededor
mirar

# Moverte
norte

# Examinar cosas
examinar guardian
examinar cristal

# Interactuar
tomar cristal
usar cristal
meditar
```

---

## 📚 PROPÓSITO EDUCATIVO

Este proyecto sirve como:

### 🎓 **Referencia de Aprendizaje:**
- Ver cómo se integran todos los sistemas
- Entender la estructura de un proyecto Ranvier completo
- Ejemplos prácticos de cada componente

### 🔧 **Base para Desarrollo:**
- Copiar y modificar para tus propios proyectos
- Plantilla limpia y bien estructurada
- Código comentado y documentado

### 🧪 **Laboratorio de Pruebas:**
- Experimentar con nuevas mecánicas
- Probar modificaciones sin afectar el proyecto principal
- Entender el comportamiento de Ranvier

---

## 🎮 CARACTERÍSTICAS DEL EJEMPLO

### Mundo Integrado:
- **Entrada del Bosque:** Punto de inicio con tutorial básico
- **Sendero Místico:** Área intermedia con desafíos
- **Cámara de Cristal:** Área final con recompensas

### NPCs Únicos:
- **Guardián de Cristal:** Enemigo con mecánicas de Vitae
- **Espíritu Ancestral:** NPC pacífico con información

### Items Funcionales:
- **Cristal de Vitae:** Consumible que restaura energía
- **Altar Ancestral:** Objeto interactivo con múltiples usos
- **Fragmentos:** Materiales para crafting futuro

---

## 🔍 CÓMO ESTUDIAR EL CÓDIGO

### 1. Empezar por la Configuración:
- `ranvier.json` - Configuración principal
- `bundle-info.js` - Información del bundle

### 2. Revisar los Sistemas:
- `lib/vitae-system.js` - Sistema único más complejo
- `lib/survival-system.js` - Sistema de necesidades básicas
- `lib/combat-system.js` - Sistema de combate integrado

### 3. Analizar el Contenido:
- `areas/mundo-ejemplo/` - Cómo se estructura un área completa
- `commands/` - Cómo se implementan comandos funcionales

### 4. Entender la Integración:
- Cómo los sistemas se comunican entre sí
- Cómo Ranvier maneja los datos
- Cómo se persiste la información

---

## 🎯 PRÓXIMOS PASOS

1. **Explora el código** - Lee cada archivo para entender su función
2. **Prueba el juego** - Conecta y experimenta con todos los comandos
3. **Modifica algo pequeño** - Cambia una descripción o agrega un item
4. **Crea tu propia área** - Usa este ejemplo como plantilla
5. **Experimenta con sistemas** - Modifica los valores y ve qué pasa

---

## 💡 CONSEJOS PARA DESARROLLADORES

### Al Estudiar:
- Lee los comentarios en el código
- Prueba cada función en el juego
- Modifica valores para ver los efectos
- Usa `console.log()` para debugging

### Al Desarrollar:
- Mantén la estructura limpia
- Documenta tus cambios
- Prueba todo antes de commitear
- Sigue las convenciones establecidas

---

¡Este ejemplo te dará una base sólida para entender y desarrollar con Ranvier! 🌌⚡