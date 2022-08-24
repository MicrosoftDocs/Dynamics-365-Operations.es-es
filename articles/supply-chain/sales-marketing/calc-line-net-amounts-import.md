---
title: Recalcular importes netos de línea al importar pedidos de venta, presupuestos y devoluciones
description: Este artículo describe si el sistema vuelve a calcular los importes netos de las líneas cuando se importan órdenes de venta, cotizaciones y devoluciones, y cómo lo hace. También explica cómo puede controlar el comportamiento en diferentes versiones de Microsoft Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 06/08/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2022-06-08
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: ce34a6be7bc3d14e23bdd8769aa71dc035b983b3
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220622"
---
# <a name="recalculate-line-net-amounts-when-importing-sales-orders-quotations-and-returns"></a>Recalcular importes netos de línea al importar pedidos de venta, presupuestos y devoluciones

[!include [banner](../includes/banner.md)]

Este artículo describe si el sistema vuelve a calcular los importes netos de las líneas cuando se importan órdenes de venta, cotizaciones y devoluciones, y cómo lo hace. También explica cómo puede controlar el comportamiento en diferentes versiones de Microsoft Dynamics 365 Supply Chain Management.

## <a name="how-updates-to-net-line-amounts-are-calculated-on-import"></a>Cómo se calculan las actualizaciones de los importes de línea netos en la importación

Supply Chain Management versión 10.0.23 introdujo la [corrección de errores 604418](https://fix.lcs.dynamics.com/issue/results/?q=604418). Esta corrección de errores cambió las condiciones bajo las cuales el campo **Importe neto** en una línea puede actualizarse o recalcularse cuando se importan actualizaciones de pedidos de venta, devoluciones y cotizaciones existentes. En la versión 10.0.29, puede reemplazar esta corrección de errores activando la característica *Calcular el monto neto de la línea en la importación*. Esta característica tiene un efecto similar, pero proporciona una configuración global que le permite volver al comportamiento anterior si es necesario. Aunque el nuevo comportamiento hace que el sistema funcione de una manera más intuitiva, puede producir resultados inesperados en escenarios específicos donde se cumplen todas las siguientes condiciones:

- Los datos que actualizan los registros existentes se importan a través de la entidad *Líneas de orden de venta V2*, *Líneas de cotización de ventas V2* o *Líneas de pedido de devolución* mediante Open Data Protocol (OData), incluidas las situaciones en las que utiliza escritura dual, importación/exportación a través de Excel y algunas integraciones de terceros.
- [Políticas de evaluación de acuerdos comerciales](/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper) que están en su lugar establecer una política de cambios que restringe las actualizaciones al campo **Importe neto** en líneas de orden de venta, líneas de oferta de venta y/o líneas de orden de devolución.
- Los datos importados incluyen cambios en el campo **Importe neto** en líneas, o cambios (como precio unitario, cantidad o descuento) que harán que el valor del campo **Importe neto** en las líneas que se volverán a calcular para uno o más registros de línea existentes.

En estos escenarios específicos, el efecto de la política de evaluación de acuerdos comerciales es restringir las actualizaciones del campo **Importe neto** en la línea. Esta restricción se conoce como *política de cambios*. Debido a esta política, cuando utiliza la interfaz de usuario para editar o volver a calcular el campo, el sistema le solicita que confirme si desea realizar el cambio. Sin embargo, cuando importa un registro, el sistema debe elegir por usted. Antes de la versión 10.0.23, el sistema siempre dejaba el monto neto de la línea sin cambios, a menos que el monto neto de la línea entrante fuera 0 (cero). Sin embargo, en las versiones más recientes, el sistema siempre actualiza o vuelve a calcular el monto neto según sea necesario, a menos que se le indique explícitamente que no lo haga. Aunque el nuevo comportamiento es más lógico, puede causarle problemas si ya está ejecutando procesos o integraciones que asumen el comportamiento anterior. Este artículo describe cómo volver al comportamiento anterior si es necesario.

## <a name="control-calculations-of-line-net-amounts-in-versions-10029-and-later"></a>Cálculos de control de importes netos de línea en las versiones 10.0.29 y posteriores

Supply Chain Management 10.0.29 introdujo una función denominada *Calcular el monto neto de la línea en la importación*. Esta característica agrega una opción que se llama **Calcular el importe neto de la línea** a la página **Parámetros de cuentas por cobrar**. Esta opción le permite seleccionar entre los comportamientos nuevos y heredados para calcular los montos netos de línea en la importación.

### <a name="turn-the-calculate-line-net-amount-on-import-feature-on-or-off"></a>Active o desactive la función Calcular importe neto de la línea al importar

Cuando actualiza a la versión 10.0.29, la característica *Calcular el monto neto de la línea en la importación* está activada de forma predeterminada, y la nueva opción **Calcular el importe neto de la línea** está configurada inicialmente en *Sí*. El ajuste *Sí* corresponde al nuevo comportamiento estándar. Coincide con el comportamiento del sistema cuando la función está desactivada, excepto en el caso de la funcionalidad del [Parámetro CalculateLineAmount](#CalculateLineAmount), como se describe más adelante en este artículo. La configuración *No* coincide con el comportamiento del sistema anterior a la versión 10.0.23 y se proporciona principalmente para admitir escenarios de integración heredados.

Los administradores pueden activar o desactivar la función *Calcular el monto neto de la línea en la importación* mediante el [Espacio de trabajo de gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="set-the-calculate-line-net-amount-option"></a>Establecer la opción Calcular el importe neto de las líneas

Cuando la función *Calcular el monto neto de la línea en la importación* está activada, puede configurar la opción **Calcular el importe neto de la línea** siguiendo estos pasos.

1. Vaya a **Clientes \> Configuración \> Parámetros de clientes**.
1. En la pestaña **Precios**, en la ficha desplegable **Cálculo del importe neto de la línea a través de la integración**, establezca la opción **Calcular el importe neto de la línea** en uno de los siguientes valores:

    - *Sí* – El sistema siempre recalculará y actualizará los montos de las líneas cuando sea necesario. (Por lo tanto, ignorará la política de evaluación de acuerdos comerciales).
    - *No* – Si el importe neto entrante o existente de cualquier línea es 0 (cero), el valor de esa línea se vuelve a calcular en función de otros valores (como el precio unitario, la cantidad y el descuento). Si el importe neto existente o entrante difiere de 0 (cero) y se establece una política de cambio en el campo **Importe neto** en la línea, el campo no se recalcula ni actualiza, incluso cuando los cambios entrantes en el precio, la cantidad o el descuento de la línea implican que el total de la línea debe recalcularse. Este comportamiento coincide con el de la versión 10.0.22.

### <a name="how-the-calculate-line-net-amount-on-import-feature-affects-the-calculatelineamount-parameter"></a><a name="CalculateLineAmount"></a>Cómo afecta la función Calcular importe neto de línea al importar al parámetro CalculateLineAmount

Cuando la función *Calcular el monto neto de la línea en la importación* está activada, el valor del parámetro `CalculateLineAmount` para las tablas `SalesLine` y `SalesQuotationLine` no tiene ningún efecto. En cambio, el comportamiento es controlado globalmente por la opción **Calcular el importe neto de la línea** que se describe en la sección anterior. Por lo tanto, cuando la función está activada, no debe depender del valor `CalculateLineAmount`.

Cuando la función *Calcular el monto neto de la línea en la importación* está desactivada, el parámetro `CalculateLineAmount` para las tablas `SalesLine` y `SalesQuotationLine` funciona como lo hace en las versiones de Supply Chain Management 10.0.23 a 10.0.28, como se describe en la siguiente sección.

## <a name="control-line-net-amount-calculations-in-versions-10028-and-earlier"></a>Cálculos de importes netos de línea en las versiones 10.0.28 y anteriores

Cuando la [corrección de errores 604418](https://fix.lcs.dynamics.com/issue/results/?q=604418) se introdujo en la versión 10.0.23, se hizo posible seleccionar cómo debería comportarse cada entidad de datos relevante cuando se editaba una cantidad neta de línea o se tenía que volver a calcular debido a otros cambios (como un precio de artículo actualizado). Puede controlar este comportamiento configurando el nuevo parámetro `CalculateLineAmount` para cada línea a uno de los siguientes valores en el archivo importado:

- **`CalculateLineAmount` = *1*** - El campo **Importe neto** de la línea siempre se vuelve a calcular y actualizar, independientemente de si se ha establecido una política de cambios para el campo y del valor del importe neto de la línea entrante o existente.
- **`CalculateLineAmount` = *0*** – Si el importe neto entrante o existente de cualquier línea es 0 (cero), el valor de esa línea se vuelve a calcular en función de otros valores (como el precio unitario, la cantidad y el descuento). Si el importe neto existente o entrante difiere de 0 (cero) y se establece una política de cambio en el campo **Importe neto** en la línea, el campo no se recalcula ni actualiza.  

El comportamiento del sistema depende de su versión de Supply Chain Management:

- En la versión 10.0.22 y anteriores, el sistema siempre se comporta como si `CalculateLineAmount` se establece en *0* y no hay manera de hacer que se comporte como si `CalculateLineAmount` se estableciera en *1*.
- En las versiones 10.0.23 a 10.0.28, el sistema se comporta como si `CalculateLineAmount` se establece en *1* para todas las líneas en las que no está establecido explícitamente en *0* en el archivo de importación.
