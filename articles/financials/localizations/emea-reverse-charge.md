---
title: Cargo invertido
description: "Este tema explica cómo configurar el impuesto sobre el valor añadido (IVA) de cargo invertido en los países europeos y Arabia Saudí."
author: epodkolz
manager: AnnBe
ms.date: 04/05/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Saudi Arabia, Spain, Sweden, United Kingdom
ms.author: epodkolz
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 64518e72dd66961108ff905981cd0405355ed130
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="reverse-charge-vat"></a>Cargo invertido


[!INCLUDE [banner](../includes/banner.md)]


Este tema describe un enfoque genérico para configurar el impuesto sobre el valor añadido (IVA) de cargo invertido para Arabia Saudí y países europeos.

El cargo invertido es un esquema de impuestos que transfiere la responsabilidad de la contabilidad y notificación del IVA del vendedor al comprador de mercancías o servicios. Por lo tanto, los destinatarios de mercancías o servicios reportan el IVA diferido (en el rol de un vendedor) y el IVA soportado (en el rol de un comprador) en su declaración del IVA.

En algunos países y regiones, el esquema de gasto invertido se implementa sólo para algunos bienes y/o servicios y existen condiciones adicionales o umbrales en importes de ventas. En otros países o regiones, la responsabilidad de pago del IVA depende del estado del proveedor y el comprador. Si el comprador no es responsable de pagar el IVA, lo debe indicar claramente en la factura que emite el proveedor. Por ejemplo, la factura debe incluir las palabras “cargo invertido” y debe indicar qué posiciones están sujetas al sistema de cargo invertido. 

Para aplicar el cargo invertido, debe completar la configuración siguiente.

## <a name="set-up-sales-tax-codes"></a>Configurar códigos de impuestos
Recomendamos que use códigos de impuestos independientes para las operaciones de venta y las operaciones de compra.

<table>
<body>
<tr>
<td><strong>Impuestos sobre ventas</strong></td>
<td>Cree un código de impuestos para las operaciones de ventas de cargo invertido (<strong>Impuestos</strong> &gt; <strong>Impuestos indirectos</strong> &gt; <strong>Impuestos</strong> &gt; <strong>Códigos de impuestos</strong>).
</td>
</tr>
<tr>
<td><strong>Código de impuestos para compras</strong></td>
<td><p>Cree códigos de impuestos negativos y positivos para el cargo invertido de IVA para las compras (<strong>Impuesto</strong> &gt; <strong>Impuestos indirectos</strong> &gt; <strong>Impuestos</strong> &gt; <strong>Códigos de impuestos</strong>).</p>
<ol>
<li>Cree un código de impuestos con un valor positivo.</li>
<li>Cree un código de impuestos con un valor negativo. Establezca la opción <strong>Permitir porcentaje de impuestos negativo</strong> en <strong>Sí</strong>.
Debe asignar este código de impuestos negativo a un grupo de impuestos de artículos y, a continuación, asignará dicho grupo a los artículos sujetos al IVA de cargo invertido.</li>
</ol>
<p>Para obtener más información, consulte la sección siguiente, &quot;Configurar grupos de impuestos y grupos de impuestos de artículos.&quot;</p>
</td>
</tr>
</tbody>
</table>

## <a name="set-up-sales-tax-groups-and-item-sales-tax-groups"></a>Configurar grupos de impuestos y grupos de impuestos de artículos
Recomendamos que use los grupos de impuestos independientes para las operaciones de ventas y las operaciones de compras.

<table>
<tr>
<td><strong>Grupo de impuestos sobre ventas</strong></td>
<td>Cree un grupo de impuestos para las operaciones de ventas con cargo invertido (<strong>Impuestos</strong> &gt; <strong>Impuestos indirectos</strong> &gt; <strong>Impuestos</strong> &gt; <strong>Grupos de impuestos</strong>). En la pestaña <strong>Configuración</strong>, incluya el código de impuestos para cargo invertido en este grupo. Seleccione las casillas de verificación <strong>Exento</strong> y <strong>Gasto invertido</strong> para el código de impuestos.</td>
</tr>
<tr>
<td><strong>Grupos de impuestos sobre compras</strong></td>
<td>Cree un grupo de impuestos para las operaciones de compra con cargo invertido (<strong>Impuestos</strong> &gt; <strong>Impuestos indirectos</strong> &gt; <strong>Impuestos</strong> &gt; <strong>Grupos de impuestos</strong>). En la pestaña <strong>Configuración</strong>, incluya los códigos de impuestos negativos y positivos en este grupo. Seleccione la casilla de verificación <strong>Cargo invertido</strong> para el código de impuestos con valor negativo.</td>
</tr>
<tr>
<td><strong>Grupos de impuestos de artículos</strong></td>
<td>Cree o actualice el grupo de impuestos de artículos con el código de impuestos que tenga un valor negativo (<strong>Impuestos</strong> &gt; <strong>Impuestos indirectos</strong> &gt; <strong>Impuestos</strong> &gt; <strong>Grupos de impuestos de artículos</strong>). Debe asignar el grupo de impuestos de artículos predeterminado a los productos y categorías que están sujetos al cargo revertido.</td>
</tr>
</table>

## <a name="set-up-reverse-charge-groups"></a>Configurar los grupos de cargo invertido
En la página **Grupos de artículos de cargo invertido** (**Impuestos** &gt; **Configuración** &gt; **Impuestos** &gt; **Grupos de artículos de cargo invertido**), puede definir grupos de productos o servicios, o productos individuales o servicios, a los que se puede aplicar el cargo invertido. Para cada grupo de artículos de cargo invertido, defina la lista de artículos, grupos de artículos y categorías para ventas o compras.

## <a name="set-up-reverse-charge-rules"></a>Configurar las reglas de cargo invertido
En la página **Reglas de cargo invertido** (**Impuestos** &gt; **Configuración** &gt; **Impuestos** &gt; **Reglas de cargo invertido**), puede definir las reglas de la aplicabilidad para fines de compra y venta. Puede configurar un conjunto de reglas de aplicabilidad de cargo invertido. Para cada regla, establezca los siguientes campos:

- **Tipo de documento**: seleccione **Pedido de compra**, **Diario de facturas de proveedor**, **Pedido de ventas**, **Factura de servicios**, **Diario de facturas del cliente** o **Factura de proveedor**.
- **Tipo de país o región del socio**: seleccione **Nacional**, **UE** o **Extranjero**. Además, si la regla se puede aplicar a todos los socios comerciales, independientemente del país o la región de la dirección, seleccione **Todos**.
- **Dirección de entrega local**: seleccione esta casilla para aplicar la regla a las entregas dentro del mismo país o región. Esta casilla no se puede seleccionar para los tipos de documento **Diario de facturas del proveedor** y **Diario de facturas del cliente**.
- **Grupo de artículos de cargo invertido**: seleccione el grupo al que la regla se puede aplicar.
- **Importe del umbral**: el esquema de cargo invertido se aplica a una factura solo si el valor de los artículos o servicios que se incluyen en el grupo de artículos de cargo invertido supera el límite que especifique aquí.

También puede utilizar los campos **Fecha de vigencia** y **Fecha de vencimiento** para definir el periodo en que es efectiva la regla.

Además, puede especificar si va a aparecer una notificación y si la línea del documento se actualiza con el grupo de impuestos predeterminado de cargo invertido si la condición para dicha línea del documento se cumple. Están disponibles las siguientes opciones:

- **Ninguno**: la línea del documento no se actualiza.
- **Solicitud**: aparece una notificación para confirmar que el cargo invertido se puede aplicar.
- **Establecer**: la línea del documento se actualiza sin la notificación adicional.

## <a name="set-up-default-parameters"></a>Configurar parámetros predeterminados
Para habilitar la funcionalidad para cargo revertido, en la página **Parámetros de contabilidad general**, en la pestaña **Cargo invertido**, establezca la opción **Habilitar cargo invertido** en **Sí**. En el los campos **Grupo de impuestos del pedido de compra** y **Grupo de impuestos de pedido de ventas**, seleccione los grupos de impuestos predeterminados. Cuando se cumple una condición de la aplicabilidad de cargo invertido, la línea de pedido de ventas o compra se actualiza con estos grupos de impuestos.

## <a name="reverse-charge-on-a-sales-invoice"></a>Cargo invertido en una factura de ventas
Para las ventas sujetas al modelo de cargo invertido, el vendedor no carga el IVA. En su lugar, la factura indica los artículos sujetos al IVA de cargo invertido y el importe total del IVA de cargo invertido.

Cuando se registra una factura de ventas con cargo invertido, las transacciones de impuestos tienen la dirección fiscal de **Impuestos repercutidos** y los impuestos cero, y la casilla de verificación **Cargo invertido** está seleccionada.

## <a name="reverse-charge-on-a-purchase-invoice"></a>Cargo invertido en una factura de compras
Para las compras sujetas a cargo invertido, el comprador que recibe la factura con el cargo invertido actúa como un comprador y vendedor a efectos contables de IVA.

Cuando se registra una factura de compra con cargo invertido, se crean dos transacciones de impuestos. Una transacción tiene la dirección fiscal de **Impuestos soportados**. La otra transacción tiene la dirección fiscal de **Impuestos repercutidos** y se selecciona la casilla de verificación **Cargo invertido**.

En el captura de pantalla siguiente, una transacción tiene la dirección **Impuestos soportados** y otra transacción tiene la dirección **Impuestos repercutidos**. 

![Impuestos registrados](media/apac-sau-posted-sales-tax.png)

