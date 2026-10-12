# Ejercicio 13 - Modelo Entidad-Relación de un Sistema de Alquiler de Vehículos y Seguros

## Descripción
Este ejercicio consiste en diseñar un modelo Entidad-Relación (DER) para un sistema de alquiler de vehículos y gestión de seguros. El modelo permite administrar sucursales, vehículos, clientes, contratos de alquiler y la gestión de siniestros con aseguradoras.

## Entidades y atributos

### 1. Sucursal
Representa las oficinas o agencias físicas de la empresa de alquiler.
- **id_sucursal**: identificador único de la sucursal.
- **empleados**: cantidad o listado de empleados en la sucursal.
- **ciudad**: ciudad donde opera la sucursal.
- **nombre**: nombre comercial de la sucursal.
- **direccion**: ubicación física.

### 2. Vehiculo
Representa la flota de automóviles disponible para alquiler.
- **id_vehiculo**: identificador único del vehículo.
- **patente**: número de matrícula o patente.
- **marca**: marca fabricante.
- **vehiculo**: modelo o tipo específico de vehículo.
- **estado**: disponibilidad o estado actual del vehículo.
- **kilometraje**: kilometraje recorrido acumulado.

### 3. Cliente
Representa a los usuarios o arrendatarios de los vehículos.
- **id_cliente**: identificador único del cliente.
- **documento**: número de documento de identidad.
- **nombre**: nombre completo del cliente.
- **licencia**: número de licencia de conducir.
- **estado licencia**: estado de vigencia de la licencia.
- **metodo pago**: forma de pago registrada.
- **telefono**: número de contacto.

### 4. Alquier
Representa el contrato o transacción de renta de un vehículo.
- **id_alquiler**: identificador único del alquiler.
- **id_cliente**: identificador del cliente que alquila.
- **tarifa**: costo base aplicado.
- **fecha retiro**: fecha y hora de entrega del vehículo.
- **fecha devuelto**: fecha y hora de devolución.
- **monto total**: valor total de la transacción.
- **estado**: estado del contrato (ej. activo, finalizado, cancelado).

### 5. Siniestro
Representa los incidentes, accidentes o daños registrados durante el alquiler.
- **id_siniestro**: identificador único del siniestro.
- **id_aseguradora**: identificador de la aseguradora interviniente.
- **nro contacto**: número de contacto o póliza relacionada.
- **descripcion daños**: detalle de los daños sufridos.
- **costo reparacion**: valor económico de la reparación.
- **fecha**: fecha en que ocurrió el siniestro.
- **estado**: estado del siniestro o trámite.

### 6. Aseguradora
Representa las compañías de seguros asociadas para la cobertura de la flota.
- **id_aseguradora**: identificador único de la aseguradora.
- **razon social**: nombre legal de la compañía.
- **telefono**: número de atención.
- **email**: correo electrónico de contacto.
- **estado**: estado de la cobertura o convenio.

## Relaciones y cardinalidades
- **Sucursal – Vehículo (Alquila / 1:N)**: una sucursal administra y alquila múltiples vehículos de la flota.
- **Sucursal – Alquiler (Tiene / 1:N)**: una sucursal registra y gestiona diversos contratos de alquiler.
- **Vehículo – Alquiler (Está / 1:1)**: un vehículo se encuentra vinculado directamente al contrato de alquiler activo.
- **Cliente – Alquiler (Consigue / 1:1)**: un cliente realiza y concreta un alquiler.
- **Alquiler – Siniestro (Puede / 1:1)**: un alquiler puede dar lugar o registrar un siniestro.
- **Siniestro – Aseguradora (Interviene / 1:N)**: un siniestro cuenta con la intervención de una aseguradora para su cobertura.

## Objetivo
Diseñar una base de datos para una empresa de alquiler de automóviles que permita administrar sucursales, controlar el estado y disponibilidad de los vehículos, registrar clientes y contratos de alquiler, y gestionar de manera eficiente los siniestros junto con las aseguradoras.
