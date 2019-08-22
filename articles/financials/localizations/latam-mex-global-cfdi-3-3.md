---
title: Facturas electrónicas de CFDI globales para México
description: En este tema se ofrece una visión general de la funcionalidad para las facturas electrónicas de CFDI globales para México.
author: v-kikozl
manager: annbe
ms.date: 06/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations, Retail
ms.search.region: Mexico
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2019-06-01
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: 82d8a30c05b2ff8bbf331b51d19f5e347cffd816
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2019
ms.locfileid: "1849356"
---
# <a name="global-cfdi-electronic-invoices-for-mexico"></a>Facturas electrónicas de CFDI globales para México 

[!include[banner](../includes/banner.md)]

La funcionalidad Microsoft Dynamics 365 for Retail para México admite el formato Comprobantes fiscales digitales por internet (CFDI) para comercios minoristas mexicanos. Para obtener más información sobre las facturas electrónicas de CFDI, consulte [Facturas electrónicas (CFDI)](https://docs.microsoft.com/dynamics365/unified-operations/financials/localizations/latam-mex-cfdi-electronic-invoices). Cuando una empresa cierra el proceso diario, debe emitir un documento de CFDI globales para consolidar todos los recibos que se emitieron a los consumidores finales. Este documento incluye la siguiente información para cada transacción que se registra durante el período:

- Un número de recibo
- Un importe correspondiente

## <a name="processing-global-cfdi-documents"></a>Procesar documentos de CFDI globales

La funcionalidad de CFDI globales le permite realizar las siguientes tareas:

- Crear una factura electrónica, en el formato de CFDI global (diseño 3.3), que se basa en el extracto comercial registrado. Para obtener más información sobre el diseño, consulte [Versión 3.3 del diseño de CFDI](https://docs.microsoft.com/dynamics365/unified-operations/financials/localizations/latam-mex-cfdi-3-3).

- Para cada factura electrónica, genere un archivo en el formato .pdf o .xml, y envíelo al cliente como un archivo adjunto de correo electrónico. Después de generar las facturas electrónicas de CFDI globales, un proveedor de servicio de firma digital (PAC) las verifica y certifica de la misma manera que otros documentos de CFDI. Para obtener más información, consulte [Facturas electrónicas (CFDI)](https://docs.microsoft.com/dynamics365/unified-operations/financials/localizations/latam-mex-cfdi-electronic-invoices) y [Consultar e imprimir una factura electrónica](https://docs.microsoft.com/dynamics365/unified-operations/financials/localizations/tasks/mx-00010-inquire-print-electronic-invoice).

Para generar y enviar una factura electrónica de CFDI globales, siga estos pasos.

1. Como paso preparativo, en la pestaña **Venta minorista** de la página **Parámetros de facturas electrónicas** (**Administración de la organización \> Configuración \> Factura electrónica \> Parámetros de facturas electrónicas**), debe especificar los parámetros predeterminados del formato de CFDI globales.
2. Cierre el turno en el punto de venta (PDV).
3. Ejecute el trabajo P en la programación de distribución para transferir transacciones comerciales desde la base de datos del canales hasta Retail Headquarters.
4. Calcule y registre un extracto comercial siguiendo los pasos en [Crear, calcular y registrar un extracto para una tienda](https://docs.microsoft.com/dynamics365/unified-operations/retail/tasks/create-calculate-post-statement-retail-store).
5. Ejecute la operación periódica **Registrar CFDI – Facturas electrónicas** para crear facturas electrónicas de CFDI globales que se basan en un extracto comercial registrado. Puede seleccionar un número de extracto para esta operación periódica. Si no selecciona un número de extracto, el sistema crea facturas electrónicas de CFDI globales para todos los extractos comerciales registrados que aún no se han procesado.

    Como resultado de la operación periódica **Registrar CFDI – Facturas electrónicas**, se crean dos facturas electrónicas de CFDI globales. Una factura electrónica recopila todos los recibos relacionados con las operaciones de ventas, y la otra recopila todos los recibos relacionados con las devoluciones. Para la factura electrónica relacionada con las devoluciones, el atributo **Devolución** se establece en **Sí**. Puede ver estas facturas electrónicas en la página **CFDI (facturas electrónicas)** (**Venta minorista \> Consultas e informes \> CFDI (facturas electrónicas)**).

    El resto de flujos de trabajo, como la comunicación con un proveedor de servicios, la generación de archivos .pdf y .xml, y las funciones manuales son los mismos que los flujos de trabajo para las facturas electrónicas de CFDI normales.

6. Ejecute la operación periódica **Proceso de exportar/importar factura electrónica** para enviar facturas electrónicas al PAC.

## <a name="updates-for-the-global-cfdi-functionality"></a>Actualizaciones para la funcionalidad de CFDI globales

En la versión 10.0.2 de **Microsoft Dynamics 365 for Finance and Operations (mayo de 2019)**, la funcionalidad de CFDI globales se amplió para admitir nuevos requisitos que se han introducido en la segunda revisión de la *Guía de cumplimentación de CFDI globales*. A partir de la versión 10.0.2 de **Microsoft Dynamics 365 for Finance and Operations (mayo de 2019)**, puede realizar las siguientes tareas:

- En la solicitud del cliente, genere una factura electrónica de CFDI normales independiente que se basa en una operación de venta o devolución que se registra en el PDV.

    En este caso, la operación de venta o de devolución debe registrarse como un pedido de cliente. Para obtener más información sobre la funcionalidad para pedidos de cliente, consulte [Pedidos de cliente en Retail Modern POS (MPOS)](https://docs.microsoft.com/dynamics365/unified-operations/retail/customer-orders-overview).

- En una factura electrónica de CFDI que se genera según las devoluciones, especifique identificadores únicos universales (UUID) para facturas electrónicas de CFDI relacionadas con las operaciones de venta originales.

A partir de la versión 10.0.2 de **Microsoft Dynamics 365 for Finance and Operations (mayo de 2019)**, la funcionalidad de CFDI globales también admite los siguientes escenarios adicionales:

- [Devolucioens de artículos a través de múltiples pedidos y facturas de clientes](https://docs.microsoft.com/dynamics365/unified-operations/retail/multireturn)
- Devoluciones de pedidos de cliente que implican un intercambio, cuando una factura de cliente incluye líneas con importes positivos y líneas con importes negativos

### <a name="showing-related-cfdi-documents-in-a-cfdi-electronic-invoice"></a>Mostrar documentos relacionados con CFDI en una factura electrónica de CFDI

Para mostrar los UUID de las ventas originales en facturas electrónicas de CFDI para devoluciones, active el parámetro **Especificar CFDI relacionados en devoluciones** en la pestaña **Venta minorista** de la página **Parámetros de facturas electrónicas** (**Administración de la organización \> Configuración \> Factura electrónica \> Parámetros de facturas electrónicas**). Tras activar este parámetro, se generan documentos de CFDI globales y normales que incluyen la siguiente información:

- Una lista de facturas electrónicas relacionadas.
- Un estado de **Borrador**. (Este estado es un nuevo estado que se introdujo en la versión 10.0.2). Una factura electrónica se establece automáticamente en este estado si un UUID no se especifica para todas las facturas electrónicas relacionadas. El procedimiento periódico **Proceso de exportar/importar factura electrónica** omite todas las facturas electrónicas con un estado de **Borrador**.
- Un archivo XML que se genera, donde la sección **Relacionados de CFDI** contiene la lista de facturas electrónicas relacionadas. Puede ver la lista de facturas electrónicas relacionadas seleccionando **Consultas \> Facturas electrónicas relacionadas**. También puede agregar manualmente una nueva factura electrónica relacionada en la misma página.

    El estado de las facturas electrónicas se actualiza automáticamente más adelante, cuando todas las facturas electrónicas relacionadas obtienen sus UUID. Para actualizar manualmente el estado de una factura electrónica, puede utilizar la función **Marcar como lista** . El estado de la factura electrónica se cambiará y se pondrá a disposición para su exportación.

### <a name="excluding-customer-orders-from-global-cfdi-electronic-invoices"></a>Excluir pedidos de cliente de facturas electrónicas de CFDI globales

Para procesar pedidos de cliente como facturas electrónicas de CFDI normales de la misma manera que los pedidos de ventas se procesan en el módulo **Clientes**, y para excluir dichas operaciones de las facturas electrónicas de CFDI globales, active el parámetro **Excluir pedidos de cliente de CFDI globales** en la pestaña **Venta minorista** de la página **Parámetros de facturas electrónicas** (**Administración de la organización \> Configuración \> Factura electrónica \> Parámetros de facturas electrónicas**). Tras activar este parámetro, se crea una factura electrónica independiente según cada operación de venta o de devolución que se registra a través de un pedido de cliente en el PDV.

Las siguientes operaciones de pedidos de clientes pueden provocar que se registre una factura electrónica de CFDI normales:

- Recogida de pedido de cliente
- Devolución de pedido de cliente
- Pedido de cliente híbrido (Para obtener más información sobre este escenario, consulte [Pedidos de cliente híbridos](https://docs.microsoft.com/dynamics365/unified-operations/retail/hybrid-customer-orders).)

Cuando se desactiva el parámetro **Excluir pedidos de cliente de CFDI globales**, y no se registró ninguna factura de cliente anterior del mismo pedido de cliente y se procesó como una factura electrónica independiente (CFDI normales), los pedidos de cliente se incluyen en las facturas electrónicas de CFDI globales. De lo contrario, los pedidos de cliente se procesan como facturas electrónicas independientes (CFDI normales). Por lo tanto, se excluyen de las facturas electrónicas de CFDI globales.

Los devoluciones de pedidos de cliente se procesan de la misma manera (CFDI globales o CFDI normales) que las operaciones de venta originales.

#### <a name="limitations"></a>Limitaciones

Tenga en cuenta las siguientes limitaciones:

- Todas las facturas de un pedido de ventas original se incluyen en una factura electrónica de devolución como documentos de CFDI relacionados.
- El escenario de devolución de un pedido de cliente que implica un intercambio solo se admite para facturas electrónicas de CFDI globales.
