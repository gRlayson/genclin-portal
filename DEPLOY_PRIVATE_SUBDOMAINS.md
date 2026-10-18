# Migración a subdominios privados GenClin

## Hosts previstos
- `prioritizer.genclin.cl` → HPO Clinical Prioritizer. Origen actual comprobado por invitación: `https://hpo-clinical-prioritizer.streamlit.app/`. **No usar CNAME directo a Streamlit Community Cloud sin confirmar compatibilidad de hostname/certificado y autenticación**. Preferir host propio con reverse proxy gestionado y protección Access, o migrar Streamlit a un hosting con dominio personalizado.
- `variantdesk.genclin.cl` → VariantDesk. Existe repositorio privado `gRlayson/variantdesk` (rama de trabajo `clinical-core-v1`), y un proyecto Vercel llamado `variantdesk`. Verificar la versión efectiva de ejecución y la ruta de hosting actual antes de apuntar el DNS.

## Requisitos obligatorios antes de activar los enlaces
1. Cloudflare Zero Trust → Access → Applications: política `Allow` para correo autorizado **únicamente**; autenticación One-Time PIN; duración de sesión 24 h.
2. Comprobar protección de hostname Y URL de origen, incluidos Workers.dev, Vercel y dominio Streamlit. Evitar accesos alternativos públicos a datos clínicos.
3. Configurar custom domain/certificado TLS y DNS SOLO una vez que Access esté preparado.
4. Desde sesión privada/no autenticada: petición a cada hostname debe denegarse o solicitar login; en sesión autorizada, cargar la aplicación correctamente. Verificar que no se filtran secretos ni información del caso en HTML, respuestas o logs.
5. Recién entonces fusionar `feature/private-app-subdomains` en `main`. La portada pública debe mantener enlaces anteriores mientras el cambio no sea operable.

Este branch prepara los enlaces pero NO cambia DNS, Zero Trust ni despliegues.