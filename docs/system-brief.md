# System Brief – UniPaydocs/system-brief.md

## Problema
La gestión manual o fragmentada de pagos universitarios genera errores en saldos y falta de trazabilidad.

## Stakeholders
- Estudiantes
- Departamento financiero
- Administración
- Soporte TI

## Scope
- Registro e inicio de sesión
- Visualización de saldo
- Registro de pagos
- Historial
- Actualización automática de saldo

## No-Scope
- Integración bancaria real
- Aplicación móvil
- Facturación electrónica avanzada

## Diagrama de Contexto

```mermaid
flowchart LR
    Estudiante -->|Realiza pago| UniPay
    UniPay -->|Actualiza saldo| BaseDatos[(Base de Datos)]
    Administracion -->|Consulta información| UniPay
