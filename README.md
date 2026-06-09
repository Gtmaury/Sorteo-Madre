# Sorteo de Ganadores - TV Zamora

Aplicación web para la presentación en vivo del sorteo de premios de **TV Zamora - Comunicación Total**. Diseñada para ser proyectada en pantalla durante el evento, mostrando a cada ganador con animaciones y efectos visuales.

---

## Descripción

La app muestra una pantalla de portada con el logo de TV Zamora y un botón para iniciar el sorteo. Al comenzar, revela a cada ganador uno por uno con un spinner de carga, animaciones de entrada y confetti. Al finalizar, presenta la lista completa de todos los ganadores.

Los premios sorteados son:

- 12 tablets TCL
- 3 viajes a Margarita

---

## Estructura del proyecto

```
├── index.html          # Estructura HTML principal
├── script.js           # Lógica del sorteo, animaciones y efectos
├── styles.css          # Estilos y animaciones CSS
├── airplane_bg.png     # Imagen de fondo (viajes)
├── tablet_bg.png       # Imagen de fondo (tablets)
├── logotvz.png         # Logo TV Zamora
├── logo_tvz_antes.png  # Logo usado en portada y header
├── logo_tvz_despues.png# Logo usado en pantalla final
├── logo_30_anos.png    # Logo 30 aniversario
└── logo_sp7.png        # Logo SP7 Grupo
```

---

## Flujo de la aplicación

1. **Portada** — Se muestra el logo animado y el botón "Comenzar Sorteo".
2. **Sorteo individual** — Por cada ganador se muestra un spinner (~4.6s) seguido de la revelación con animaciones (nombre, código, ciudad, premio).
3. **Fondo dinámico** — El fondo cambia según el tipo de premio: avión para viajes, tablet para tablets.
4. **Siguiente sorteo** — El botón avanza al siguiente ganador. Al llegar al último, cambia a "Ver Todos los Ganadores".
5. **Lista final** — Se muestra una grilla con todos los ganadores ordenados: viajes primero, luego tablets.

---

## Persistencia

El progreso se guarda automáticamente en `localStorage` bajo la clave `tvzamora_sorteo_progress`. Si se recarga la página durante el sorteo, la app retoma desde el último ganador mostrado sin necesidad de reiniciar.

Para reiniciar el sorteo desde cero, limpiar el `localStorage` del navegador.

---

## Ganadores registrados

| #   | Nombre                          | Código      | Ciudad                   | Premio |
| --- | ------------------------------- | ----------- | ------------------------ | ------ |
| 1   | Neidimar Yerlin Flores Gil      | 00100049217 | Core 8                   | Tablet |
| 2   | Yusmerilys Carolina Guatarasma  | 01100103752 | Maturín                  | Tablet |
| 3   | Ana Gloria González Guzmán      | 00100000007 | Puerto Ordaz             | Tablet |
| 4   | Kiiara Marley Rivas Guerra      | 00500014624 | Santa Bárbara de Barinas | Tablet |
| 5   | Belkys Ruiz de Acuña            | 00100000037 | Guasipati                | Tablet |
| 6   | Yarelys Josefina López Álvarez  | 00200029071 | Upata                    | Tablet |
| 7   | Elizabeth Martínez Díaz         | 00300000996 | Bolívar                  | Tablet |
| 8   | Anyelis del Valle Fernández     | 00600023296 | San Félix                | Tablet |
| 9   | Maria do Amparo Ribeiro da Silva| 00400001819 | Santa Elena de Uairén    | Tablet |
| 10  | Mariauxi Carolina González      | 00800003807 | Soledad                  | Tablet |
| 11  | Osyerlin Mogollón               | 01000000031 | Caicara del Orinoco      | Tablet |

---

## Uso

No requiere instalación ni dependencias. Abrir `index.html` directamente en el navegador.

```bash
# Opcionalmente, servir con cualquier servidor local:
npx serve .
# o
python -m http.server 8080
```

Las fuentes se cargan desde Google Fonts (`Outfit` e `Inter`), por lo que se requiere conexión a internet para la tipografía óptima.

---

## Tecnologías

- HTML5 / CSS3 / JavaScript (Vanilla)
- Canvas API — partículas de fondo y confetti
- CSS Animations & Keyframes
- localStorage para persistencia de sesión
- Google Fonts
