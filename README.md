# PastKeys ⌨️

Juego web para memorizar el **pasado simple** y el **participio pasado** de los **500 verbos más usados del inglés** (250 irregulares + 250 regulares), escribiéndolos con el teclado.

## Cómo se juega

- El juego te muestra un verbo en presente (infinitivo) y te pide su **pasado simple** o su **participio pasado**, al azar.
- Escribes la respuesta y pulsas Enter (o «Comprobar»).
- Cada nivel tiene **10 preguntas**. Con **8 aciertos o más** desbloqueas el siguiente nivel.

## Sistema de niveles (50 niveles)

- Los verbos están ordenados por frecuencia de uso real en inglés.
- **Nivel 1:** los 10 verbos más usados (be, have, do, say, get…).
- **Nivel 2:** mazo de los 20 más usados → se eligen 10 al azar.
- **Nivel N:** mazo de los N×10 más usados → 10 al azar.
- **A partir del nivel 4:** las **2 primeras preguntas** de cada ronda salen siempre (al azar) de los **25 verbos más usados**, para que nunca dejes de repasarlos.
- Se aceptan las variantes válidas (p. ej. `got` / `gotten`, `learned` / `learnt`, `was` / `were`).

## Teclado seguro (sin autocorrector) 🔒

Los teclados del móvil (Gboard, teclado de iOS…) autocorrigen o sugieren palabras, lo que arruina el ejercicio. PastKeys lo ataca en dos capas:

1. El campo de texto lleva `autocorrect="off"`, `autocomplete="off"`, `autocapitalize="none"` y `spellcheck="false"`, que desactivan el corrector en iOS/Safari y en la mayoría de teclados Android.
2. Como algunos teclados Android ignoran esos atributos, hay un interruptor de **«Teclado seguro»**: activa un teclado QWERTY dentro del propio juego y bloquea el teclado nativo del sistema (el campo pasa a `readonly`). Así es **imposible** que el autocorrector intervenga.

La preferencia y tu progreso se guardan en el navegador (`localStorage`).

## Publicar en GitHub Pages

1. Crea un repositorio y sube estos 3 archivos: `index.html`, `verbs.js`, `README.md`.
2. En el repositorio: **Settings → Pages → Source: Deploy from a branch → Branch: `main` / (root) → Save**.
3. En un minuto tendrás el juego en `https://TU_USUARIO.github.io/NOMBRE_DEL_REPO/`.

No necesita servidor ni dependencias: es HTML + CSS + JavaScript puro.

## Estructura

```
├── index.html   → la aplicación completa (interfaz + lógica del juego)
├── verbs.js     → base de datos: 500 verbos ordenados por frecuencia
└── README.md
```

Formato de cada verbo en `verbs.js`:

```js
{"b":"get","p":["got"],"pp":["got","gotten"],"es":"obtener, conseguir","i":1}
// b: infinitivo · p: pasado simple · pp: participio · es: traducción · i: 1 irregular / 0 regular
```
