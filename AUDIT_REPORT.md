# Nota de auditoría breve — caddy

**Tipo**: Config Docker Compose de reverse proxy (sin código propio). **Score: 65/100**

## Inventario
Compose de Caddy (:80/:443 tcp+udp), red `reverse_proxy`, volúmenes persistentes, TZ America/Bogota.

## Hallazgos
| Sev | Hallazgo |
|---|---|
| P2 | Imagen `caddy:latest` sin pin → builds irreproducibles |
| P2 | `cap_add: NET_ADMIN` innecesario para proxy estándar (reducir superficie) |
| P3 | Revisar contenido de `Caddyfile` y `site/` (no versionados o vacíos) |

## Verificación
Sintaxis YAML correcta. No se levantó el stack (requeriría puertos privilegiados).

*Generada por la auditoría integral ago-2026.*

## Ejecución ago-2026
✅ Imagen pineada a `caddy:2.11.4` · ✅ `NET_ADMIN` eliminado del compose. Pendiente: completar el `Caddyfile` con sitios reales.

