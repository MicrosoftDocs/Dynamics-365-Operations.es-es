---
title: Sincronizar a petición con el motor de precios de Supply Chain Management
description: Este tema describe cómo usar el motor de precios en Microsoft Dynamics 365 Supply Chain Management de Dynamics 365 Sales.
author: RamaKrishnamoorthy
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: bf4154816f01040a236dde77b92ee69396158614
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750773"
---
# <a name="sync-on-demand-with-the-supply-chain-management-pricing-engine"></a>Sincronizar a petición con el motor de precios de Supply Chain Management

[!include [banner](../../includes/banner.md)]



Microsoft Dynamics 365 Supply Chain Management incluye un motor de precios que gestiona acuerdos comerciales, listas de precios, programas de fidelización de clientes, promociones y descuentos. El motor de fijación de precios utiliza reglas complejas para determinar el mejor precio para un presupuesto o pedido determinado. Cuando usa doble escritura, usa precios estáticos o el motor de precios de Dynamics 365 Supply Chain Management en las páginas de Presupuesto y Pedido en Dynamics 365 Sales.

## <a name="use-the-pricing-engine-from-supply-chain-management-in-sales"></a>Usar el motor de precios de Supply Chain Management en Sales

1. En Sales, vaya a **Ventas \> Pedidos**.
2. Seleccione **Nuevo** para crear un pedido nuevo o seleccione uno ya existente en la lista **Mis pedidos**.
3. Agregar una línea de pedido nueva.
4. Si está creando un nuevo pedido, seleccione **Precio de pedido** en el panel de acciones. Si está actualizando un pedido ya existente, seleccione **Recalcular** en el panel de acciones.

    Las siguientes columnas se rellenan automáticamente:

    + Detalles del importe
    + % de descuento
    + Descuento
    + Importe previo al flete
    + Importe del flete
    + Impuestos totales
    + Importe total
    
5. Para garantizar que el sistema considera los acuerdos comerciales y de ventas para calcular el precio:
    1. Navegue a su entorno de Supply Chain Management.
    2. Navegue a **Clientes \> Configuración \> Parámetros de clientes**.
    3. Seleccione la pestaña **Precios** en la barra de navegación lateral.
    4. Bajo la ficha desplegable **Evaluación de acuerdos comerciales**, desmarque la opción **Entrada manual**.

## <a name="how-it-works"></a>Cómo funciona

Cuando selecciona **Precio del pedido** en Sales, la función **Totales** en la pestaña **Pedido de ventas \> Ver** en Supply Chain Management se llama para el pedido de ventas asociado. Los valores en el total del pedido en Sales se utilizan para completar las columnas correspondientes en Supply Chain Management.

Cuando se calcula el total del pedido de ventas en Supply Chain Management, el cálculo evalúa los acuerdos comerciales existentes y los acuerdos de ventas para el cliente y los productos que figuran en el pedido de ventas. Esta información se usa para calcular los totales. Cuando **Precio del pedido** está seleccionado, Sales refleja automáticamente toda la configuración que se ha realizado en Supply Chain Management.

## <a name="limitations"></a>Limitaciones

Cuando se completan las columnas en Sales, se aplican las siguientes limitaciones:

+ La configuración de cargos y asignaciones de cargos en Supply Chain Management no se replica en Sales.
+ El precio no considera precios minoristas especiales que se especifican en la columna **Canal minorista** en la página de línea de pedido de ventas en Supply Chain Management.
+ Descuentos que se definen en la sección **Gestión de permisos comerciales** de Supply Chain Management no se tienen en cuenta.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]