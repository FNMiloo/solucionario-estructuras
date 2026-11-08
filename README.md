# Solucionario de estructuras

Aplicación web de una sola página para resolver problemas de análisis estructural con el desarrollo completo paso a paso: fórmulas, sustitución numérica, resultado con unidades y diagramas.

No necesita instalación, servidor ni conexión a internet. Abre `index.html` y listo.

**Demo en línea:** https://fnmiloo.github.io/solucionario-estructuras/

---

## Contenido

| # | Tema | Método |
|---|------|--------|
| 1 | Pórtico con cargas laterales | Método del portal · cortante por columna · diagramas DFC y DMF |
| 2 | Pórtico esbelto | Método del voladizo · fuerzas axiales · momento de volcamiento |
| 3 | Pórtico con vigas | Método de Muto · rigidez lateral D · punto de inflexión |
| 4 | Losa armada en dos direcciones | Coeficientes ACI 318 · relación de lados · franjas de columna |
| 5 | Armadura plana | Rigidez directa · matriz global · fuerzas axiales por barra |

## Características

- **Desarrollo verificable:** cada paso muestra la fórmula, la sustitución con los datos y el resultado.
- **Resultados destacados:** tarjetas con las magnitudes principales de cada problema (cortante basal, momento de volcamiento, momentos de diseño).
- **Diagramas:** esquemas del pórtico, DFC, DMF, fuerzas axiales y armadura con tracción y compresión en colores, generados como SVG.
- **Editor de armaduras:** mesa de trabajo ampliada para crear nudos, barras, apoyos y cargas sobre el dibujo; la armadura se recalcula mientras la editas.
- **Diagnóstico automático:** avisa de hipótesis que no cumplen, relaciones de lados fuera de rango y resultados inconsistentes.
- **Cinco decimales** en todos los resultados, con separadores en español.
- **Exportación:** copiar el desarrollo, descargar CSV (compatible con Excel) e imprimir o guardar como PDF con formato A4, incluyendo los diagramas.
- **Tema claro y oscuro**, diseño adaptable a móvil y navegación por teclado.
- **Persistencia local:** recuerda los datos y el tema entre visitas.
- **Sin dependencias:** HTML, CSS y JavaScript en un único archivo.

## Uso

1. Abre `index.html` en cualquier navegador moderno.
2. Elige el método en las pestañas superiores.
3. Modifica los datos: los resultados se recalculan al escribir.
4. En **Armaduras**, pulsa **Editar armadura** para modificar la geometría en la mesa de trabajo.
5. Usa **Copiar**, **CSV** o **Imprimir** para llevarte el desarrollo.

También puedes enlazar directamente a un método con el ancla, por ejemplo:

```
index.html#muto
```

## Estructura

```
solucionario-estructuras/
├── index.html   # aplicación completa (HTML + CSS + JS)
├── README.md
└── LICENSE
```

El motor de cálculo está en el bloque de módulos de `index.html`. Cada módulo declara sus datos de entrada en `in` y una función `solve(v)` que devuelve la lista de pasos y los diagramas. Para añadir un método basta con agregar un objeto a `MODS` y su nombre corto a `SLUGS`/`SHORT`.

## Criterios de cálculo

- Sistema Internacional de unidades, salvo que el enunciado use otro sistema coherente.
- Formato numérico con cinco decimales; notación científica por debajo de `1×10⁻⁴` o por encima de `1×10⁷`.
- Las hipótesis, convenciones de signo y referencias de cada método aparecen en el propio desarrollo, al pie de cada tema.
- El cortante basal y el momento de volcamiento se calculan por equilibrio global del pórtico.
- En armaduras, la rigidez axial de cada barra es `EA/L` y los apoyos se imponen eliminando sus grados de libertad.

## Referencias

- Hibbeler, R. C. *Structural Analysis*. Pearson.
- McCormac, J. C. y Elling, R. E. *Análisis de estructuras*. Alfaomega.
- ACI 318, *Building Code Requirements for Structural Concrete*.
- Taranath, B. S. *Structural Analysis and Design of Tall Buildings*. McGraw-Hill.

## Aviso

Herramienta con fines docentes. Los resultados deben verificarse antes de utilizarse en un proyecto real.

## Licencia

MIT. Consulta [LICENSE](LICENSE).
