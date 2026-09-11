# Nonograma · Duelo

Duelo de nonogramas para proyectar en clase. Dos jugadores resuelven 3 nonogramas cada uno, uno tras otro, con cronómetro en centésimas de segundo. Gana quien sume menos tiempo.

Comparte el estilo, las animaciones y los sonidos del [Rosco de Matemática](https://github.com/paolovf123/rosco-matematica) y de [Cálculo Mental](https://github.com/paolovf123/calculo-mental).

## Jugar

- **En línea (GitHub Pages):** https://paolovf123.github.io/nonograma/
- **En local:** es un solo archivo, `index.html`. Se puede abrir con doble clic o servir con `python -m http.server 8082`. Las fuentes se cargan de Google Fonts.

## Equipos

Cada jugador elige su país en la pantalla inicial; la bandera y los colores cambian con la elección. Si un jugador elige el país del otro, se intercambian.

| País | Sección |
|---|---|
| Perú | 1ro Chocano |
| España | 1ro Valdelomar |
| Francia | 2do Eguren |
| Japón | 2do Vallejo |
| Portugal | 3ro Ribeyro |
| Alemania | 3ro Alegría |
| Brasil | 4to Arguedas |

La lista vive en `index.html` (constante `PAISES`).

## Cómo funciona

1. **Configuración:** país de cada jugador, tamaño de cada uno de los 3 puzzles (5×5 a 10×10), límite de tiempo por puzzle (0 = sin límite) y si se tachan las filas y columnas ya completas.
2. **Puzzles:** se generan al azar con solución única y sin filas ni columnas completas (nunca aparece el número máximo). Cada jugador recibe puzzles distintos, pero del mismo tamaño en cada ronda.
3. **Turnos:** el jugador 1 resuelve sus 3 puzzles seguidos y después el jugador 2 los suyos.
4. **Cada turno:** las pistas están ocultas hasta pulsar Iniciar. Suena una cuenta regresiva 3-2-1 y arranca el cronómetro. El puzzle se da por resuelto automáticamente cuando todas las filas y columnas cumplen sus números.
5. **Límite:** si se agota, el puzzle cuenta con el límite completo y se muestra la solución. "Rendirse" hace lo mismo.
6. **Resultado:** suma de los 3 tiempos de cada jugador, en centésimas, con el desglose por puzzle.

## Controles

| Acción | Cómo |
|---|---|
| Pintar una casilla | Clic izquierdo (arrastrar para pintar varias) |
| Marcar ✕ (casilla vacía) | Clic derecho |
| Iniciar / siguiente puzzle | `Enter` |
| Pausa (oculta las pistas) | `Espacio` |
| Salir a configuración | `Esc` |

## Práctica

El botón "Práctica · puzzle de ejemplo" abre el nonograma 5×5 de la clase (filas 1, 1, 3, 4, 4 · columnas 2-1, 2, 3, 3, 2), sin límite ni rival, para explicar las reglas antes del duelo.

## Archivos

| Archivo | Para qué sirve |
|---|---|
| `index.html` | El juego completo (HTML, CSS y JS, sin dependencias). Incluye el generador y el solucionador que garantiza solución única. El tablero sigue el estilo en blanco y negro de puzzle-nonograms.com. |
| `.github/workflows/pages.yml` | Publica `index.html` en GitHub Pages en cada push a `main`. |
