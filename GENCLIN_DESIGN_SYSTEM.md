# GenClin — sistema visual compartido (2026-10-22)

## Identidad aprobada
- Título principal: **Herramientas digitales para genética clínica**.
- Logotipo aprobado: una hélice estilizada con **una sola pareja G–C**, G izquierda y C derecha; mantener imagen aprobada, no reconstruir automáticamente con una geometría distinta.
- **GLR no forma parte del logo**. Firmar por separado en el pie: `GenClin by GLR` y `© 2026 GenClin`.
- Tipografía preferida: Inter; usar fallback `system-ui, -apple-system, sans-serif` sin sustituir encabezados técnicos por serif decorativa.
- Colores de marca: azul marino `#1F3A5F`, azul profundo `#234B63`, azul acero `#527D94`, petróleo `#115E59`, turquesa `#16877F`, salvia `#7FB3A5`, fondo `#F5F9F8`.
- Acentos por aplicación: VariantDesk azul marino, Prioritizer turquesa, AntropoMetrics azul acero, GenClin Scores azul profundo, Acid-Base verde petróleo, HPO Extract salvia. No depender únicamente del color para estado/errores.

## Navegación compartida (sin SSO entre proveedores)
| Herramienta | URL |
|---|---|
| Inicio GenClin | https://genclin.cl/ |
| VariantDesk | https://variantdesk.genclin.cl/ |
| HPO Clinical Prioritizer | https://hpo-clinical-prioritizer.streamlit.app/ |
| AntropoMetrics | https://antropometria.genclin.cl/ |
| GenClin Scores | https://antropometria.genclin.cl/genclin-scores |
| Acid-Base | https://antropometria.genclin.cl/acid-base |
| HPO Extract | https://hpo.genclin.cl/ |

Incorporar una barra accesible (regresar a inicio y abrir cualquiera de las otras herramientas) sin alterar lógica médica, rutas de aplicación, autenticación, cookies, ni exportaciones. El menú debe admitir navegación con teclado y desplazamiento móvil. Para Streamlit, usar componentes nativos o HTML seguro, sin inyectar scripts.

## Control antes de promover
- Comprobar que no haya cambios en criterios ACMG/AMP, cálculos, HPO ranking, datos, servicios backend ni seguridad.
- Probar enlace de regreso, menú móvil, foco visible y contraste WCAG AA.
- Probar acceso autenticado y no autenticado en cada proveedor.
- Confirmar exactamente el PNG/SVG final entregado por el usuario para el logo antes de incluirlo en la rama.

Este archivo documenta el diseño; no habilita cambios de producción ni nuevas rutas públicas.
