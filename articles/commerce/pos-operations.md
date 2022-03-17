---
title: Operaciones de punto de venta (PDV) en línea y sin conexión
description: Este tema ofrece información sobre las operaciones de punto de venta (PDV) en Dynamics 365 Commerce. Especifica en qué parte de la aplicación pueden invocarse las operaciones y si están disponibles en modo sin conexión.
author: jblucher
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2017-09-27
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 0c62e11cc6d39c351321419bb862a5169b162fb7
ms.sourcegitcommit: d2e5d38ed1550287b12c90331fc4136ed546b14c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8349726"
---
# <a name="online-and-offline-point-of-sale-pos-operations"></a>Operaciones de punto de venta (PDV) en línea y sin conexión

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

La mayoría de las acciones que los usuarios realizan en el punto de venta (PDV) se consideran operaciones. Las operaciones se configuran y administran en el back office de Dynamics 365 Commerce . Se pueden agregar muchas operaciones a los botones de la cuadrícula de botones de PDV. Los usuarios pueden seleccionar los botones para invocar las operaciones y para realizar su función. Otras operaciones son parte de la aplicación principal de PDV, y se invocan desde los botones de pantalla o como parte de otros flujos de trabajo o procesos.

En la tabla siguiente se proporcionan los detalles de las operaciones disponibles en Modern POS y PDV en la nube. La tabla también especifica en qué parte de la aplicación pueden invocarse las operaciones y si están disponibles cuando el PDV está en modo sin conexión.

Algunas operaciones no se encuentran disponibles en Modern POS o PDV en la nube. Algunas de estas operaciones son operaciones específicas de la configuración regional que requieren extensiones y configuración adicionales. Otras son características de Microsoft Dynamics AX 2012 que no se admiten actualmente.

Las columnas siguientes especifican dónde pueden ser invocadas las operaciones:

- **Cuadrícula de botones** – La operación se puede asignar a los botones de las cuadrículas de botones de PDV, que son parte de un diseño de pantalla de PDV.
- **Pantalla de transacción** – La operación se pueden invocar desde las cuadrículas de botones de PDV que se configuran en la pantalla de transacción de PDV.
- **Pantalla de bienvenida** – La operación se pueden invocar desde las cuadrículas de botones de PDV que se configuran en la pantalla de bienvenida de PDV.

> [!NOTE]
> Las operaciones que se muestran a continuación se aplican a la última versión de Commerce. Algunas operaciones pueden haber cambiado o puede que no estén disponibles en versiones anteriores.


| ID. | Operación | Descripción | Cuadrícula de botones | Pantalla de transacción | Pantalla de bienvenida | Disponible sin conexión | Específico de configuración regional |
|----|-----------|-------------|-------------|--------------------|----------------|-------------------|-----------------|
| 707 | Activar dispositivo | Active el dispositivo actual permitiendo que un usuario autenticado proporcione información de conexión y asigne un Id de dispositivos y registro. | No | No | No | No | No |
| 134 | Agregar afiliación | Agregue una afiliación preseleccionada a una transacción. Seleccione la afiliación en la página **Propiedades de botón**. | Sí | Sí | No | Sí | No |
| 135 | Agregar afiliación de la lista | Seleccione una afiliación de una lista para agregarla a una transacción. | Sí | Sí | Sí | Sí | No |
| 137 | Agregar afiliación a cliente | Agregar una afiliación a un cliente en la página **Detalles del cliente**. | No | No | No | Sí | No |
| 138 | Quitar afiliación de cliente | Quitar una afiliación en la página **Detalles del cliente**. | No | No | No | Sí | No |
| 643 | Agregar código de vale | Agregue un vale especificando su código en el PDV. | Sí | Sí | No | Sí | No |
| 141 | Agregar cargos de encabezado | Agregue un cargo misceláneo al encabezado del pedido. | Sí | Sí | No | No| No |
| 141 | Agregar cargos de línea | Agregue un cargo misceláneo a una línea de ventas seleccionada. | Sí | Sí | No | No| No |
| 117 | Agregar tarjeta de fidelización | Pida al usuario que introduzca un número de tarjeta de fidelización que se agregará a la transacción actual. | Sí | Sí | No | Sí | No |
| 136 | Agregar número de serie | Esta operación permite al usuario especificar un número de serie para el artículo seleccionado actualmente. | Sí | Sí | No | Sí | No |
| 1214 | Agregar dirección de envío | Esta operación no se admite. | No aplicable | No aplicable | No aplicable | No aplicable | No |
| 519 | Agregar a tarjeta regalo | Agregar dinero a la tarjeta regalo especificada. | Sí | Sí | No | No | No |
| 6000 | Permitir omisión del registro fiscal | Esta operación no se admite. | No aplicable | No aplicable | No aplicable | No aplicable | Sí |
| 1212 | Ingreso bancario | Permite registrar la cantidad de dinero que se envía al banco y otra información, tal como el número de saca. | Sí | Sí | Sí | Sí | No |
| 923 | Comprobación de totales bancarios | Esta operación no se admite. | No aplicable | No aplicable | No aplicable | No aplicable | Sí |
| 915 | Operación en blanco | Esta operación representa un botón personalizable que un programador de software puede programar mediante programación para las operaciones especializadas que necesite el negocio. | Sí | Sí | Sí | Sí | No |
| 1053 | Turno cerrado en ciego | Defina el turno actual como cerrado en ciego y cierre la sesión del usuario. Un turno cerrado en ciego está cerrado a las transacciones adicionales pero sigue siendo abierto a las operaciones de caja registradora, como supresión de forma de pago y declaración por forma de pago. | Sí | Sí | Sí | No | No |
| 310 | Calcular el total | Cuando se retrasa el cálculo del descuento, esta operación inicia el cálculo de la transacción actual. | Sí | Sí | No | Sí | No |
| 642 | Ejecutar todos los productos | Establezca el modo de entrega de todas las líneas como **Ejecutar**. | Sí | Sí | No | Sí\* | No |
| 641 | Ejecutar los productos seleccionados | Establezca el modo de entrega de todas las líneas seleccionadas como **Ejecutar**. | Sí | Sí | No | Sí\* | No |
| 647 | Cambiar modo de entrega | Cambiar el modo de entrega para las líneas de ventas de envío preconfiguradas. | Sí | Sí | No | No| No |
| 1215 | Cambiar contraseña | Esta operación permite al usuario de PDV cambiar la contraseña. | Sí | Sí | Sí | No | No |
| 123 | Cambiar unidad de medida | Cambie la unidad de medida para el artículo de línea seleccionado. | Sí | Sí | No | Sí | No |
| 639 | Borrar representante de ventas predeterminado en transacción | Quite el grupo de ventas de la comisión (representante de ventas) de la transacción. | Sí | Sí | No | Sí | No |
| 106 | Borrar cantidad | Restablezca la cantidad en la línea seleccionada actualmente como **1**. | Sí | Sí | No | Sí | No |
| 640 | Borrar representante de ventas en línea | Quite el grupo de ventas de la comisión (representante de ventas) de la línea seleccionada actualmente. | Sí | Sí | No | Sí | No |
| 121 | Borrar vendedor | Esta operación no se admite. | No aplicable | No aplicable | No aplicable | No aplicable | No |
| 1055 | Cerrar turno | Cierre el turno actual, imprima un informe Z y cierre la sesión del usuario del sistema. | Sí | Sí | Sí | No | No |
| 139 | Concluir transacción | Pide confirmación al usuario para seleccionar el método de pago | Sí | Sí | No | Sí | No |
| 925 | Copiar el cheque bancario | Esta operación no se admite. | No aplicable | No aplicable | No aplicable | No aplicable | Sí |
| 620 | Crear pedido de cliente | Convierta la transacción de PDV en un pedido del cliente. | Sí | Sí | No | Sí\* | No |
| 621 | Crear presupuesto | Convierta la transacción de PDV en un presupuesto de ventas. | Sí | Sí | No | Sí\* | No |
| 636 | Crear transacción comercial | Cree una transacción de ventas estándar cuando el comportamiento de PDV predeterminado es crear pedidos del cliente. | Sí | Sí | No | Sí | No |
| 600 | Cliente  | Agregue el cliente especificado a la transacción. | No | No | No | Sí | No |
| 1100 | Depósito de cuenta de cliente | Permite realizar un pago en la cuenta de un cliente. | Sí | Sí | Sí | Sí | Sí |
| 612 | Agregar cliente | Cree un registro de cliente nuevo. | Sí | Sí | Sí | Sí† | No |
| 603 | Borrado de clientes | Quite al cliente de la transacción actual. | Sí | Sí | No | Sí | No |
| 602 | Búsqueda de clientes | Busque un registro de cliente navegando a la página de búsqueda de clientes en el PDV. | Sí | Sí | Sí | Sí | No |
| 609 | Transacciones del cliente | Esta operación no se admite. | No aplicable | No aplicable | No aplicable | No aplicable | No |
| 917 | Estado de conexión de base de datos | Vea los valores actuales de conexión, y cambiar entre los modos conectado y sin conexión. | Sí | Sí | Sí | Sí | No |
| 1200 | Declarar importe inicial | Declare el importe que se encuentra en la caja registradora al iniciar el día o el turno. | Sí | Sí | Sí | Sí | No |
| 132 | Anular depósito | Permite invalidar el depósito predeterminado para los pedidos de cliente. | Sí | Sí | No | Sí\* | No |
| 913 | Deshabilitar modo Diseño | Esta operación no se admite. | No aplicable | No aplicable | No aplicable | No aplicable | No |
| 912 | Habilitar modo Diseño | Esta operación no se admite. | No aplicable | No aplicable | No aplicable | No aplicable | No |
| 1217 | Desensamblar kits | Desmoten un kit en sus productos de componente. | Sí | Sí | Sí | Sí | No |
| 624 | Mostrar importes de devolución | Esta operación no se admite. | No aplicable | No aplicable | No aplicable | No aplicable | Sí |
| 513 | Mostrar total | Muestra el saldo de la transacción en la pantalla del cliente. | Sí | Sí | Sí | Sí | No |
| 623 | Editar cliente | Edite los detalles del cliente actual. | Sí | Sí | No | No | No |
| 614 | Editar pedido de cliente | Recupere el pedido seleccionado para que se pueda modificar en el PDV. | No | No | No | No | No |
| 615 | Editar presupuesto | Recupere el presupuesto seleccionado para que se pueda modificar en el PDV. | No | No | No | No | No |
| 518 | Cuentas de gastos | Registre el dinero retirado de la caja registradora para gastos ocasionales. | Sí | Sí | Sí | Sí | No |
| 919 | Inicio de sesión extendido | Permite asignar o quitar el permiso para iniciar sesión mediante la digitalización de un código de barras o el pase de una tarjeta. | Sí | Sí | Sí | Sí | No |
| 1201 | Entrada flotante | Agregue dinero adicional a la caja registradora o el turno actual. | Sí | Sí | Sí | Sí | No |
| 1218 | Forzar desbloqueo de periférico | El sistema usa esta operación internamente para desbloquear periféricos de PDV. | No aplicable | No aplicable | No aplicable | No aplicable | No |
| 520 | Saldo de tarjeta regalo | Muestra el saldo de una tarjeta regalo. | Sí | Sí | No | No | No |
| 708 | Desactivar dispositivo | Desactive el dispositivo actual, para que no se pueda utilizar como caja registradora de PDV. | No | No | No | No | No |
| 804 | Operaciones de entrada | Acceda a las funciones de gestión de inventario de la tienda entrante. | Sí | No | Sí | No| No |
| 517 | Cuentas de ingresos | Registre el dinero colocado de la caja registradora por un motivo distinto a una venta. | Sí | Sí | Sí | Sí | No |
| 801 | Búsqueda de inventario | Consulte cantidades disponibles, en pedido y neto no comprometido (ATP) para la tienda actual y otras ubicaciones disponibles. | Sí | Sí | Sí | No | No |
| 806 | Ajuste de inventario | Ajuste el inventario dentro o fuera del almacén de la tienda mediante el diario de ajuste o movimiento. | Sí | Sí | Sí | No | No |
| 807 | Movimiento de inventario | Mueva artículos desde una ubicación de inventario a otra dentro de un almacén. | Sí | Sí | Sí | No | No |
| 122 | Comentario de factura | Permite especificar un comentario sobre la transacción actual. | Sí | Sí | No | Sí | No |
| 511 | Emitir nota de crédito | Emita una nota de crédito para proporcionar un asiento en lugar de una devolución. | Sí | Sí | No | No | No |
| 512 | Emitir tarjeta regalo | Emita una nueva tarjeta regalo por el importe especificado. | Sí | Sí | No | No | No |
| 625 | Emitir tarjeta de fidelización | Emita una tarjeta de fidelización a un cliente para que este pueda participar en el programa de fidelización de la tienda. | Sí | Sí | Sí | No | No |
| 300 | Importe de descuento de línea | Permite especificar un importe de descuento para un elemento de línea de la transacción. Esta operación solo se utiliza para artículos a los que se pueden aplicar descuentos y solo dentro de los límites de descuento especificados. | Sí | Sí | No | Sí | No |
| 301 | Porcentaje de descuento de línea | Permite especificar un porcentaje de descuento para un artículo de línea de la transacción. Esta operación solo se utiliza para artículos a los que se pueden aplicar descuentos y solo dentro de los límites de descuento especificados. | Sí | Sí | No | Sí | No |
| 703 | Bloquear caja registradora | Bloquee la caja registradora actual, para que no se pueda usar, pero no cierre la sesión del usuario actual. | No | No | No | Sí | No |
| 701 | Cerrar sesión | Cierre la sesión del usuario actual de la caja registradora. | Sí | Sí | Sí | Sí | No |
| 521 | Saldo de puntos de tarjeta de fidelización | Muestra el saldo de puntos para la tarjeta de fidelización especificada. | Sí | Sí | No | No | No |
| 142 | Gestionar cargos | Ver y administrar los cargos misceláneos aplicados a la transacción. | Sí | Sí | No | No| No |
| 918 | Administrar cambios | Muestre una lista de turnos activos, suspendidos y cerrados en ciego. | Sí | Sí | Sí | No | No |
| 914 | Minimizar ventana PDV | Esta operación no se admite. | No aplicable | No aplicable | No aplicable | No aplicable | No |
| 1000 | Categoría abierta | Realice una operación “sin venta” y abra la caja registradora seleccionada actualmente. | Sí | Sí | Sí | Sí | No |
| 928 | Cumplimiento de pedido | Esta operación permite a los usuarios seleccionar, empaquetar, envíar, o que volver a llamar los pedidos para recogida en el almacén. | Sí | Sí | Sí | No | No |
| 805 | Operación de salida | Funciones de acceso para gestionar envíos de órdenes de transferencia salientes. | Sí | No | Sí | No| No |
| 129 | Anular impuestos de producto de línea | Reemplaza el impuesto del artículo de línea seleccionado y usa un impuesto especificado distinto. | Sí | Sí | No | Sí | No |
| 130 | Anular impuestos de producto de línea de la lista | Reemplaza el impuesto del artículo de línea seleccionado por otro que el usuario selecciona de una lista. | Sí | Sí | No | Sí | No |
| 127 | Anular impuesto de transacción | Sustituya los impuestos de la transacción y utilice unos impuestos especificados distintos. | Sí | Sí | No | Sí | No |
| 128 | Anular impuesto de transacción de la lista | Sustituya el impuesto de la transacción y utilice el impuesto que el usuario seleccione de una lista. | Sí | Sí | No | Sí | No |
| 131 | Albarán | Cree un albarán del pedido seleccionado. | No | No | No | No | No |
| 710 | Emparejar estación de hardware | Esta operación no se admite. | No aplicable | No aplicable | No aplicable | No aplicable | No |
| 201 | Pagar con tarjeta | Acepte una tarjeta como una tarjeta de crédito o débito como pago. | Sí | Sí | No | Sí | No |
| 200 | Pagar en efectivo | Permite aceptar efectivo como pago. | Sí | Sí | No | Sí | No |
| 206 | Pagar en efectivo rápido | Complete la transacción con un toque, y acepte el importe debido en efectivo (cambio exacto). | Sí | Sí | No | Sí | No |
| 204 | Pagar con cheque | Acepte un cheque como pago. | Sí | Sí | No | Sí | No |
| 213 | Pagar con nota de crédito | Acepte una nota de crédito (asiento) emitida por la tienda. | Sí | Sí | No | No | No |
| 203 | Divisa de pago | Permite aceptar el pago en varias divisas. | Sí | Sí | No | Sí | No |
| 202 | Pagar con cuenta de cliente | Cargue la transacción a la cuenta del cliente. Este método de pago no es válido para los depósitos de pedidos de cliente. | Sí | Sí | No | No | No |
| 214 | Pagar con tarjeta regalo | Acepte una tarjeta regalo que emitió la tienda. | Sí | Sí | No | No | No |
| 207 | Pagar con tarjeta de fidelización | Acepte una tarjeta de fidelización para el pago y canjee puntos para obtener productos autorizados. | Sí | Sí | No | No | No |
| 634 | Historial de pagos | Muestre el historial de pago del cliente para el pedido del cliente actual. | Sí | Sí | No | No | No |
| 803 | Picking y recepción | Abre la página **Picking y recepción**, donde puede seleccionar pedidos para recoger o recibir en la tienda. | Sí | Sí | Sí | No | No |
| 632 | Recoger todos los productos | Establezca el método de cumplimiento **Recogida en tienda** para todas las líneas. | Sí | Sí | No | Sí\* | No |
| 631 | Recoger productos seleccionados | Establezca el método de cumplimiento como **Recogida en tienda** para líneas seleccionadas. | Sí | Sí | No | Sí\* | No |
| 400 | Menú emergente | Esta operación no se admite. | No aplicable | No aplicable | No aplicable | No aplicable | No |
| 101 | Comprobación de precio | Esta operación permite al usuario consultar el precio de un producto especificado. | Sí | Sí | Sí | Sí | No |
| 104 | Anulación del precio | Reemplace el precio de un producto, si este último se ha configurado para permitir anulaciones de precio. | Sí | Sí | No | Sí | No |
| 1058 | Impresión fiscal X | Esta operación no se admite. | No aplicable | No aplicable | No aplicable | No aplicable | Sí |
| 1059 | Impresión fiscal Z | Esta operación no se admite. | No aplicable | No aplicable | No aplicable | No aplicable | Sí |
| 927 | Imprimir etiqueta de artículo | Esta operación no se admite. | No aplicable | No aplicable | No aplicable | No aplicable | No |
| 926 | Imprimir etiqueta de estantería | Esta operación no se admite. | No aplicable | No aplicable | No aplicable | No aplicable | No |
| 1056 | Imprimir X | Imprima e informe X para el turno actual. | Sí | Sí | Sí | No | No |
| 103 | Comentario del producto | Permite agregar un comentario al artículo de línea seleccionado en la transacción. | Sí | Sí | No | Sí | No |
| 100 | Venta de producto | Agregue un producto especificado a la transacción. | Sí | Sí | Sí | Sí | No |
| 108 | Búsqueda de productos | Busque un producto navegando a la página de búsqueda de productos en el PDV. | Sí | Sí | Sí | Sí | No |
| 633 | Fecha de vencimiento de presupuesto | Vea o modifique la fecha de caducidad en un presupuesto de ventas. | Sí | Sí | No | Sí\* | No |
| 627 | Volver a calcular | Recalcule todas las líneas de pedidos e impuestos del cliente, en función de la configuración actual. | Sí | Sí | No | Sí\* | No |
| 143 | Recalcular cargos | Vuelve a calcular los cargos automáticos aplicados al pedido. | Sí | Sí | No | No| No |
| 515 | Recuperar pedido | Busque y recupere pedidos del cliente y presupuestos de ventas. | Sí | Sí | Sí | No | No |
| 504 | Recuperar transacción | Recupere una transacción suspendida anteriormente de la tienda actual. | Sí | Sí | No | Sí‡ | No |
| 305 | Canjear puntos de fidelización | Esta operación no se admite. | No aplicable | No aplicable | No aplicable | No aplicable | Sí |
| 635 | Devolver los gastos de envío | Devuelva los cargos de envío de un pedido cancelado. | No | No | No | No | No |
| 644 | Quitar código de vale | Pida al usuario que quite vales seleccionándolos en una lista de vales que están asociados actualmente a la transacción. | Sí | Sí | No | Sí | No |
| 1057 | Volver a imprimir Z | Vuelva a imprimir el informe Z del turno anterior. | Sí | Sí | Sí | No | No |
| 1216 | Escriba una contraseña nueva | Esta operación permite que un usuario que tiene permiso para restablecer la contraseña restablezca la contraseña de otro empleado mediante una contraseña temporal. | Sí | Sí | Sí | No | No |
| 1219 | Abrir dirección URL en PDV | Abra una URL configurada por el administrador en el PDV. | Sí | Sí | Sí | Sí | No |
| 109 | Devolver producto | Realice la devolución de productos individuales. El siguiente producto digitalizado se muestra como producto devuelto con un precio y una cantidad negativos. | Sí | Sí | No | Sí | No |
| 114 | Transacción de devolución | Recupere una transacción anterior por su número de recibo para devolver algunos o todos los productos. | Sí | Sí | Sí | Sí§ | No |
| 1211 | Ingreso en caja fuerte | Permite realizar un ingreso seguro para trasladar dinero de la caja registradora a la caja fuerte. | Sí | Sí | Sí | Sí | No |
| 516 | Factura de ventas | Esta operación permite al cliente crear pagos para la factura de ventas seleccionada. | Sí | Sí | No | No | No |
| 502 | Vendedor | Establezca el valor **Secretario de ventas** en un pedido de ventas para los pedidos del cliente en el PDV. | Sí | Sí | No | Sí\* | No |
| 2000 | Programar administración | Todavía no se admite esta operación. | Sí | Sí | Sí | No | No |
| 2001 | Programar solicitudes | Todavía no se admite esta operación. | Sí | Sí | Sí | No | No |
| 622 | Buscar pedidos | Esta operación permite a los usuarios preconfigurar los botones de PDV para realizar búsquedas por artículo, cliente, o la categoría. | Sí | Sí | Sí | Sí | No |
| 1213 | Buscar dirección de envío | Esta operación no se admite. | No aplicable | No aplicable | No aplicable | No aplicable | No |
| 709 | Seleccionar hardware station | Seleccione una estación de hardware de una lista de estaciones de hardware disponibles. | Sí | Sí | Sí | Sí | No |
| 637 | Establecer representante de ventas predeterminado en transacción | Seleccione uno de los grupos de ventas aptas de la comisión elegibles (representantes de ventas) como representante de ventas predeterminado para las líneas que se agregan posteriormente. | Sí | Sí | No | Sí | No |
| 105 | Definir cantidad | Permite cambiar la cantidad de un artículo de línea en la transacción. | Sí | Sí | No | Sí | No |
| 638 | Establecer representante de ventas en línea | Seleccione uno de los grupos de ventas aptas de la comisión elegibles (representantes de ventas) para la línea seleccionada actualmente. | Sí | Sí | No | Sí | No |
| 630 | Enviar todos los productos | Establezca el modo de cumplimiento como **Envío** para todos los artículos de línea. | Sí | Sí | No | Sí\* | No |
| 629 | Enviar productos seleccionados | Establezca el modo de cumplimiento como **Envío** para las líneas seleccionadas. | Sí | Sí | No | Sí\* | No |
| 115 | Mostrar diario | Muestra el diario de la tienda. Puede ver transacciones, volver a imprimir recibos y recibos de regalo y recuperar para devolución. | Sí | Sí | Sí | Sí\*\* | No |
| 802 | Recuento de existencias | Cree o modifique los diarios de recuento de existencias para el inventario físico o los recuentos cíclicos. | Sí | Sí | Sí | No | No |
| 401 | Submenú | Esta operación lleva al usuario a otra cuadrícula de botones vinculada. | Sí | Sí | Sí | Sí | No |
| 1054 | Suspender turno | Suspenda el turno actual, para poder activar un turno nuevo o distinto en la caja registradora actual. | Sí | Sí | Sí | No | No |
| 503 | Suspender transacción | Suspenda la transacción de ventas actual, para que pueda recuperarse más adelante en la tienda. | Sí | Sí | No | Sí‡ | No |
| 1004 | Grabador de tareas | Abre el Grabador de tareas para registrar los pasos del procedimiento en el PDV. | No | No | No | Sí | No |
| 1052 | Declaración por forma de pago | Especifique el importe de dinero en la caja registradora para cada método de pago contado. | Sí | Sí | Sí | Sí | No |
| 1210 | Supresión de forma de pago | Saque dinero la caja o turno actual. | Sí | Sí | Sí | Sí | No |
| 920 | Reloj de tiempo | Marque la entrada y la salida de turnos de trabajo y descansos. | Sí | Sí | Sí | No | No |
| 302 | Importe de descuento total | Escriba importe de descuento para la transacción. Esta operación solo se aplica a artículos a los que se pueden aplicar descuentos y solo dentro de los límites de descuento especificados. | Sí | Sí | No | Sí | No |
| 303 | Porcentaje de descuento total | Escriba un porcentaje de descuento para la transacción. Esta operación solo se aplica a artículos a los que se pueden aplicar descuentos y solo dentro de los límites de descuento especificados. | Sí | Sí | No | Sí | No |
| 501 | Comentario de transacción | Permite agregar un comentario a la transacción actual. | Sí | Sí | No | Sí | No |
| 922 | Ver detalles del producto | Abra la página de detalles del producto para el artículo de línea seleccionado actualmente. | Sí | Sí | No | Sí | No |
| 1003 | Ver informes | Muestra los informes que se han configurado para el usuario actual. | Sí | Sí | Sí | No | No |
| 921 | Ver entradas de reloj de tiempo | Muestra las entradas del reloj de tiempo para todos los trabajadores de la tienda. | Sí | Sí | Sí | No | No |
| 211 | Anular pago | Anule la línea de pago seleccionada actualmente desde la transacción. | Sí | Sí | No | Sí | No |
| 102 | Anular producto | Anule el artículo de línea de pago seleccionado actualmente desde la transacción. | Sí | Sí | No | Sí | No |
| 500 | Anular transacción | Anule la transacción actual. | Sí | Sí | No | Sí | No |
| 916 | Windows Workflow Foundation | Esta operación no se admite. | No aplicable | No aplicable | No aplicable | No aplicable | No |
| 924 | Informe X para tarjetas bancarias | Esta operación no se admite. | No aplicable | No aplicable | No aplicable | No aplicable | Sí |
| 311 | Eliminar descuentos del sistema de transacciones | Elimine todos los descuentos aplicados por el sistema, incluidos los descuentos basados en cupones, de la transacción. Esto no elimina los descuentos manuales. | Sí | Sí | Sí | Sí | No |
| 312 | Volver a aplicar los descuentos del sistema | Vuelva a aplicar los descuentos del sistema en la transacción si se eliminaron utilizando la operación **Eliminar descuentos del sistema de la transacción**. | Sí | Sí | Sí | Sí | No |

\* La operación está disponible en modo sin conexión cuando se está creando un pedido de cliente o un presupuesto de ventas, y solo si la creación sin conexión de pedidos de cliente y de presupuestos de ventas se configura en el perfil de funcionalidad de PDV. La operación no se puede realizar cuando los pedidos se crean mediante Real-time Service o cuando se recuperan o editan pedidos.

† La operación se puede realizar en modo sin conexión cuando el PDV está configurado para permitir la creación sin conexión de clientes en el perfil de funcionalidad de PDV.

‡ Cuando el PDV está sin conexión, las transacciones suspendidas se pueden recuperar solo desde la base de datos sin conexión del registro actual. Los usuarios no pueden suspender y recuperar transacciones a través de los registros.

§ Cuando el PDV está sin conexión, solo pueden recuperarse para devolución las transacciones de la base de datos sin conexión actual.

\*\* Cuando el PDV está sin conexión, solo se muestran en el diario las transacciones de la base de datos de canales sin conexión actual.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
