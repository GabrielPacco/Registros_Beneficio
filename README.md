# Camal · Marcado de piezas

App web (PWA) para marcar piezas de res/cerdo en cámara, **funciona sin internet**
y se instala en el celular. Pensada para reemplazar el trabajo con boletas en mano.

## Qué hace
- Muestra **solo lo que falta** (rojo). Al tocar una pieza, desaparece (con DESHACER).
- **Búsqueda por número** con teclado numérico.
- **Bloques por día**: L, M, MI, J, V.
- Contador **"Faltan X de Y"** para no saltarse piezas.
- Datos guardados en el propio celular → **offline total** una vez cargada.

## Cargar datos
Toca **☰ → Importar lista** y pega el texto del OCR. Formato:
```
V
1234 185
1240 192
J
1567 90
```
Una línea con solo la letra del día (`L M MI J V`) inicia un bloque.
Cada pieza: `número peso`. También vale `1234 185 V` en una sola línea.

## Tecnología
HTML + CSS + JavaScript puro, sin dependencias. PWA con Service Worker
(`sw.js`) y `manifest.webmanifest`. Se sirve como sitio estático (GitHub Pages).

## Uso offline en cámara
1. Abre la app con señal (instálala: "Agregar a pantalla de inicio").
2. Importa la lista del día.
3. Entra a cámara sin señal: la app y los datos siguen disponibles.
