# 🍔 FoodFast  
Sistema de Gestión de Pedidos y Entregas de Comida

## 📌 Descripción

FoodFast es un sistema web diseñado para digitalizar y optimizar la gestión de pedidos en restaurantes con servicio a domicilio.  
Permite centralizar la administración de pedidos, coordinación con cocina, asignación de entregas y procesamiento de pagos en un solo sistema.

El objetivo es reemplazar procesos manuales o fragmentados por una solución organizada, eficiente y trazable.

---

## 🎯 Problema que Resuelve

Muchos restaurantes gestionan pedidos manualmente o mediante herramientas no integradas, lo que provoca:

- Desorganización en pedidos  
- Errores en la preparación  
- Retrasos en entregas  
- Falta de visibilidad del estado del pedido  
- Dificultad para controlar pagos  

---

## 👥 Usuarios del Sistema

- **Cliente:** realiza pedidos y consulta estado  
- **Administrador:** supervisa pedidos y gestiona usuarios  
- **Cocina:** recibe pedidos y actualiza estado  
- **Repartidor:** gestiona entregas  

---

## 🚀 Funcionalidades Principales (Scope)

- Registro e inicio de sesión  
- Creación y gestión de pedidos  
- Envío automático de pedidos a cocina  
- Actualización de estado en tiempo real  
- Asignación de entregas  
- Procesamiento de pagos mediante servicio externo  

---

## ❌ No Incluye (Por Ahora)

- Integración bancaria directa  
- Aplicación móvil nativa  
- Sistema de inteligencia artificial  
- Integración con ERP empresarial  

---

## 🏗 Arquitectura del Sistema

El sistema está compuesto por los siguientes módulos principales:

- Autenticación  
- Gestión de Pedidos  
- Asignación a Cocina  
- Gestión de Entregas  
- Base de Datos  

---

## 📊 Diagrama de Contexto

```mermaid
graph TD

subgraph Externos
    Cliente
    Administrador
    Cocina
    Repartidor
    ServicioPagos["Servicio Externo de Pagos"]
end

subgraph FoodFast
    Autenticacion
    GestionPedidos
    AsignacionCocina
    GestionEntregas
    BaseDatos[(Base de Datos)]
end

Cliente -->|Inicia sesión / Registro| Autenticacion
Administrador -->|Gestiona usuarios| Autenticacion
Autenticacion -->|Guarda / Consulta datos| BaseDatos

Cliente -->|Crea pedido| GestionPedidos
GestionPedidos -->|Guarda pedido| BaseDatos
Administrador -->|Supervisa pedidos| GestionPedidos

GestionPedidos -->|Envía pedido a cocina| AsignacionCocina
Cocina -->|Actualiza estado| GestionPedidos

GestionPedidos -->|Pedido listo| GestionEntregas
GestionEntregas -->|Asigna entrega| Repartidor

GestionPedidos -->|Procesa pago| ServicioPagos
