# Práctica 12A – Hola React

Respuestas a las preguntas de la práctica y notas de lo realizado.

---

### 1. Compilador y JSX (SWC)

- **Error al compilar sin configuración:**
  Dio un error de sintaxis (`Syntax Error`) porque por defecto SWC lee JavaScript normal y no reconoce la sintaxis de etiquetas como `<div>`.

- **¿En qué se convirtió cada etiqueta del JSX?**
  - En **modo clásico** se convirtieron en llamadas a `React.createElement(...)`.
  - En **modo automático** se convirtieron en llamadas a `_jsx` y `_jsxs` del paquete `react/jsx-runtime`.

- **Si React es «sólo una biblioteca», ¿quién traduce el JSX?**
  El compilador (en este caso SWC, o herramientas como Babel/Vite). React solo da las funciones que se ejecutan, pero el compilador es el que traduce la sintaxis JSX a código JavaScript que el navegador pueda entender.

---

### 2. Proyecto con Vite

- **Contenedor vacío en index.html y quién lo llena:**
  El contenedor es `<div id="root"></div>` en el archivo `index.html`. Lo llena el archivo `src/main.tsx` usando `createRoot(document.getElementById('root')!).render(...)`.

---

### 3. «Hola mundo» sin JSX

- **¿Qué hace createRoot?**
  Toma el elemento del DOM (`#root`) y crea la raíz donde se va a montar y controlar la aplicación de React.

- **¿Qué hace render?**
  Dibuja o muestra en pantalla los elementos/componentes que le pasamos dentro del contenedor.

---

### 4. El primer componente

- **Error al quitar la prop obligatoria:**
  Al usar `<Saludo />` sin la prop `nombre`, el editor/TypeScript marca:
  `Property 'nombre' is missing in type '{}' but required in type 'SaludoProps'. ts(2741)`

- **¿Por qué el nombre de un componente empieza con mayúscula?**
  Para que React y el compilador distingan entre etiquetas HTML normales (como `div`, `p`, `h1` que van en minúsculas) y componentes personalizados creados por nosotros. Si fuera en minúscula, pensaría que es una etiqueta nativa del navegador.

---

### 5. Componentes dentro de componentes

- **¿Cuál es la diferencia entre escribir semestre="8" y semestre={8}?**
  Con comillas (`"8"`) se pasa como un texto (string), lo que marca error porque la interfaz pide un número. Con llaves (`{8}`) se pasa como valor numérico de JavaScript (`number`), que es lo que espera el componente para evaluar si es mayor o igual a 7.

---

### Evidencias

Las capturas y salidas de la práctica están guardadas en la carpeta `evidencias/`.
