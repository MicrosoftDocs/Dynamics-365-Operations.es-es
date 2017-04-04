---
title: "Datos de uso fiscales de la cuenta de facturación"
description: "Para las entidades jurídicas en España, la funcionalidad de datos fiscales de cuenta de factura de uso habilita datos fiscales en pedidos de ventas, facturas de servicios, y los pedidos de compra se actualiza automáticamente, en función de la información de la cuenta de facturación. Este tema proporciona información acerca de la funcionalidad de datos fiscales de cuenta de factura de uso y explica cómo configurarla."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265224
ms.assetid: 8b46e367-0f19-46d1-8fc2-88d035c460a0
ms.search.region: Spain
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 04096f601355f28d81c7c7dcaa341e0325addfcf
ms.lasthandoff: 03/31/2017


---

# <a name="use-fiscal-data-from-the-invoice-account"></a>Datos de uso fiscales de la cuenta de facturación

Para las entidades jurídicas en España, la funcionalidad de datos fiscales de cuenta de factura de uso habilita datos fiscales en pedidos de ventas, facturas de servicios, y los pedidos de compra se actualiza automáticamente, en función de la información de la cuenta de facturación. Este tema proporciona información acerca de la funcionalidad de datos fiscales de cuenta de factura de uso y explica cómo configurarla.

Para las entidades jurídicas en España, la funcionalidad de datos fiscales de cuenta de factura de uso habilita datos fiscales en pedidos de ventas, facturas de servicios, y los pedidos de compra se actualiza automáticamente, en función de la información de la cuenta de facturación. El datos fiscales se actualiza que incluye el nombre del cliente o proveedor, la dirección, y la información fiscal. La funcionalidad de datos fiscales de cuenta de factura de uso afecta a los siguientes módulos:

-   Payable de las cuentas ** cuenta de facturación ** página de cambio
-   Adquisición y abastecimiento
-   Clientes
-   Ventas y marketing

## <a name="accounts-payable-and-procurement-and-sourcing"></a>Proveedores y Adquisición y abastecimiento
Para gestionar la oportunidad de actualización automática fiscal de los datos de cambio de la cuenta de facturación en el módulo Proveedores que necesita configurar un datos fiscales de cuenta de factura de uso del parámetro en la ficha Factura de la página &gt; de los parámetros &gt; de configuración &gt; de la cuenta a pagar de la cuenta a pagar. Están disponibles las siguientes opciones:

-   ** Nunca ** – información se actualiza de la cuenta de proveedor.
-   ** ** – La información se actualiza siempre desde la cuenta de facturación.
-   ** Pregunta ** – A usuario se solicita para especificar si la información se deben actualizar de la cuenta de factura o de la cuenta de proveedor.

Cuando ** datos fiscales de cuenta de factura de uso ** se establece el parámetro, tres campos de un pedido de compra se pueden actualizar acordando el valor del parámetro. Cuando ** cuenta de facturación ** se modifica el campo, los siguientes campos se actualizan con la información de la cuenta de facturación:

-   Nombre
-   Grupo de impuestos sobre las ventas
-   Exención de impuestos

## <a name="accounts-receivable-and-sales-and-marketing"></a>Clientes y Ventas y marketing
Para gestionar el riesgo de cambio fiscal de la actualización automática de los datos en ** cuenta de facturación ** en ** clientes ** el módulo que necesita configurar un parámetro “** datos fiscales de cuenta de factura de uso **” ** factura en el fasttab ** ** las actualizaciones ** de la ficha ** cuenta por cobrar ** &gt; ** de la configuración ** &gt; ** cuenta por cobrar ** ** los parámetros ** página. Están disponibles las siguientes opciones:

-   ** Nunca ** – información se actualiza de la cuenta de cliente.
-   ** ** – La información se actualiza siempre desde la cuenta de facturación.
-   ** Pregunta ** – A usuario se solicita para especificar si la información se deben actualizar de la cuenta de factura o de la cuenta de cliente.

Cuando ** datos fiscales de cuenta de factura de uso ** se establece el parámetro, los siguientes documentos de clientes se pueden actualizar:

-   Pedidos de ventas
-   Facturas de servicios

Cuando ** cuenta de facturación ** se modifica el campo, los siguientes campos se pueden actualizar con la información de la cuenta de facturación:

-   Nombre
-   Grupo de impuestos sobre las ventas
-   Exención de impuestos



