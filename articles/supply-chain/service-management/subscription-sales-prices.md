---
title: Precios de venta de suscripción
description: Al crear una suscripción, el precio de ventas deriva de la configuración de precio de ventas que se creó en el formulario Precio de venta (suscripción).
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASalespriceSubscription
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3b4b02af0a535e67818751c437482c3663524474
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817422"
---
# <a name="subscription-sales-prices"></a>Precios de venta de suscripción   

[!include [banner](../includes/banner.md)]


Al crear una suscripción, el precio de ventas deriva de la configuración de precio de ventas que se creó en el formulario **Precio de venta (suscripción)**.

En el formulario **Precio de venta (suscripción)**, puede crear precios de ventas para una suscripción específica o crear precios de ventas que se apliquen de manera más amplia. Para que se aplique un precio de ventas a una suscripción, el código de período y la divisa de la suscripción deben ser idénticos al código de período y a la divisa del precio de ventas.

Si el código de período y la divisa son idénticos tanto para la suscripción como para el precio de ventas, los precios de venta de suscripción se seleccionan basándose en las prioridades que aparecen en la tabla siguiente. Una celda en blanco en la tabla indica un campo vacío, mientras que X indica un valor igual al valor de la suscripción a partir de la cual se genera la transacción.

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Prioridad</p></th>
<th><p><strong>Categoría</strong></p></th>
<th><p><strong>Id. de proyecto</strong></p></th>
<th><p><strong>Suscripción</strong></p></th>
<th><p><strong>Divisa de ventas</strong></p></th>
<th><p><strong>Código del período</strong></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>6</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>7</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>


Cuando se crea una cuota de suscripción, el precio de ventas con el mayor nivel de detalles (como se indica en la tabla anterior) se selecciona como precio de ventas de la suscripción.

## <a name="update-and-index-subscription-sales-prices"></a>Actualizar e indexar precios de ventas de la suscripción

Puede actualizar el precio de ventas de la suscripción actualizando el precio base o el índice. Puede actualizar según un porcentaje o a un valor nuevo.

## <a name="subscription-fee-sales-prices"></a>Precios de venta de las cuotas de suscripción

Al crear una cuota de suscripción, el precio de ventas se basa en la configuración de precio de ventas de la suscripción. Puede usar el precio de base a partir de la configuración de precio de suscripción, o bien crear precios de venta indexados.

## <a name="example"></a>Ejemplo

Desea configurar precios de venta de suscripción de 500 EUR para un nuevo proyecto 9030. En el formulario **Precio de venta (suscripción)**, crea una línea de precio de ventas de suscripción como se indica en la siguiente tabla:

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Válido desde</p></th>
<th><p>Categoría</p></th>
<th><p>Proyecto</p></th>
<th><p>Suscripción</p></th>
<th><p>Código del período</p></th>
<th><p>Divisa de ventas</p></th>
<th><p>Precio de venta</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>28-08-2006</p></td>
<td></td>
<td><p>9030</p></td>
<td></td>
<td><p>Mes</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


Tenga en cuenta que los campos **Categoría** y **Suscripción** están vacíos.

A continuación, cree las siguientes suscripciones:

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Suscripción de servicio</p></th>
<th><p>Proyecto</p></th>
<th><p>Grupo de suscripciones</p></th>
<th><p>Categoría</p></th>
<th><p>Divisa</p></th>
<th><p>Código de período</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>00020_135</p></td>
<td><p>9030</p></td>
<td><p>Sub1</p></td>
<td><p>SubCat1</p></td>
<td><p>EUR</p></td>
<td><p>Mensual</p></td>
</tr>
<tr class="even">
<td><p>00021_135</p></td>
<td><p>9030</p></td>
<td><p>Sub1</p></td>
<td><p>SubCat2</p></td>
<td><p>EUR</p></td>
<td><p>Mensual</p></td>
</tr>
</tbody>
</table>


A continuación, cree cuotas de suscripción tanto para suscripciones como para el grupo de suscripciones Sub1:

1.  Haga clic en **Gestión de servicio** \> **Configuración** \> **Suscripciones de servicio** \> **Grupos de suscripciones**.

2.  En el formulario **Grupos de suscripciones** , haga clic en **Función** \> **Crear cuota de suscripción**.

3.  En el formulario **Crear cuota de suscripción**, especifique la información adecuada. Para obtener más información, vea [Crear transacciones de gastos de suscripción](create-subscription-fee-transactions.md).

Se crean cuotas de suscripción con un precio de ventas de 500 EUR para ambas suscripciones, tal como se muestra en la siguiente tabla:

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Fecha del proyecto</p></th>
<th><p>Suscripción de servicio</p></th>
<th><p>Proyecto</p></th>
<th><p>Categoría</p></th>
<th><p>Fecha inicial</p></th>
<th><p>Fecha final</p></th>
<th><p>Divisa de ventas</p></th>
<th><p>Precio de venta</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>28-08-2006</p></td>
<td><p>00020_135</p></td>
<td><p>9030</p></td>
<td><p>SubCat1</p></td>
<td><p>01-01-2007</p></td>
<td><p>31-03-2007</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
<tr class="even">
<td><p>28-08-2006</p></td>
<td><p>00021_135</p></td>
<td><p>9030</p></td>
<td><p>SubCat2</p></td>
<td><p>01-01-2007</p></td>
<td><p>31-03-2007</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


Más adelante, decide que desea especificar precios de venta para la categoría SubCat1 del proyecto 9030. Por lo tanto, crea una nueva línea de precios de ventas con un precio de ventas de 550 EUR para la combinación del proyecto 9030 y la categoría de cuota SubCat1. Ahora hay dos líneas de precio de ventas de suscripción para el proyecto 9030, tal como se muestra en la siguiente tabla:

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Válido desde</p></th>
<th><p>Categoría</p></th>
<th><p>Proyecto</p></th>
<th><p>Suscripción</p></th>
<th><p>Código del período</p></th>
<th><p>Divisa</p></th>
<th><p>Precio de venta</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>28-08-2007</p></td>
<td></td>
<td><p>9030</p></td>
<td></td>
<td><p>Mes</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
<tr class="even">
<td><p>28-08-2007</p></td>
<td><p>SubCat1</p></td>
<td><p>9030</p></td>
<td></td>
<td><p>Mes</p></td>
<td><p>EUR</p></td>
<td><p>550</p></td>
</tr>
</tbody>
</table>


Repita el procedimiento descrito anteriormente para crear cuotas de suscripción para ambas suscripciones del grupo de suscripciones Sub1. En la siguiente tabla, se muestran las transacciones que se crean para cada suscripción vinculada al grupo de suscripciones.

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Fecha del proyecto</p></th>
<th><p>Suscripción</p></th>
<th><p>Proyecto</p></th>
<th><p>Categoría</p></th>
<th><p>Fecha inicial</p></th>
<th><p>Fecha final</p></th>
<th><p>Divisa de ventas</p></th>
<th><p>Precio de venta</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>28-07-2007</p></td>
<td><p>00020_135</p></td>
<td><p>9030</p></td>
<td><p>SubCat1</p></td>
<td><p>01-01-2008</p></td>
<td><p>31-03-2008</p></td>
<td><p>EUR</p></td>
<td><p>550</p></td>
</tr>
<tr class="even">
<td><p>28-07-2008</p></td>
<td><p>00021_135</p></td>
<td><p>9030</p></td>
<td><p>SubCat2</p></td>
<td><p>01-01-2008</p></td>
<td><p>31-03-2008</p></td>
<td><p>EUR</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


En la primera transacción para la suscripción 00020\_135, el precio de ventas 550 EUR procede del precio de ventas de suscripción configurado para la combinación del proyecto específico y la categoría. En la segunda transacción para la suscripción 00021\_135, el precio de ventas 500 EUR se usa como precio de ventas de suscripción del proyecto porque no hay ningún precio configurado para la combinación de proyecto 9030 y categoría SubCat2.

## <a name="see-also"></a>Consulte también

[Actualizar e indexar precios de ventas de la suscripción](update-and-index-subscription-sales-prices.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]