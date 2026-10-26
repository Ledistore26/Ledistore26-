# Ledistore26 — proyecto inicial

## Qué incluye
- Catálogo adaptable a móvil/tablet/PC con las ocho categorías iniciales.
- Búsqueda, filtro por categoría y carrito.
- Flujo de pedido por WhatsApp con mensaje precargado.
- Modalidad manual para que el cliente elija vendedor o asignación automática por turnos.
- Panel de demostración para productos, vendedores y ajustes.
- Exportación de respaldo JSON.
- Código fuente editable.

## Importante antes de usar con clientes
Esta entrega es un **prototipo inicial**, no una tienda lista para producción:
- Los productos y ajustes se guardan en `localStorage` del navegador y no se sincronizan entre dispositivos.
- El panel administrativo todavía no tiene inicio de sesión; no publiques esta versión tal cual.
- Los teléfonos de WhatsApp deben configurarse desde el panel.
- Los productos de muestra y sus precios son ficticios: reemplázalos antes de vender.
- Para producción hay que conectar una base de datos (por ejemplo Supabase), implementar autenticación/roles, políticas de acceso y almacenamiento seguro de imágenes, y probar el flujo de pedidos.
- La asignación automática de esta demo ocurre en el navegador, no es una cola global entre todos los clientes.
- La tienda no procesa pagos online.

## Requisitos
Node.js 20 o posterior y npm.

## Ejecutar localmente
1. Descomprimí el ZIP.
2. En una computadora con Node.js, dentro de la carpeta del proyecto ejecutá:
   `npm install`
   `npm run dev`
3. Abrí la dirección local que indique Vite.

## Publicar
Este proyecto usa Vite + React, por lo que puede publicarse como sitio estático en un proveedor compatible con uso comercial. Antes de desplegar, revisá las condiciones vigentes del proveedor elegido.
- Build command: `npm run build`
- Output directory: `dist`

## Próxima etapa recomendada
Conectar Supabase y reemplazar el almacenamiento local:
1. Crear tablas para products, categories, vendors, settings y orders.
2. Activar autenticación para administración.
3. Configurar Row Level Security y políticas: clientes pueden leer solo productos activos; solo administradores autenticados pueden crear/editar/eliminar productos y cambiar vendedores.
4. Guardar imágenes en Supabase Storage.
5. Definir asignación automática de vendedores en una función de servidor o RPC atómica para evitar que varios clientes asignen pedidos al mismo turno.
6. Publicar y probar en entorno de prueba antes de usar comercialmente.
