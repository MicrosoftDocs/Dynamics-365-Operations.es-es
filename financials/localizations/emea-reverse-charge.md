---
title: Cargo invertido | Microsoft Docs
description: "Este tema explica cómo configurar el impuesto sobre el valor añadido (VAT) de cargo invertido en los países europeos."
author: epodkolz
manager: AnnBe
ms.date: 05/12/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epodkolz
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 6cb473962f40ed9ef2f5f807f089098764f47009
ms.openlocfilehash: b3c94fa73410d9bdcaaec11dee04a7a239e4d45a
ms.contentlocale: es-es
ms.lasthandoff: 06/14/2017

---

# Cargo invertido
<a id="reverse-charge-vat" class="xliff"></a>
Este tema describe un enfoque genérico para configurar el impuesto sobre el valor añadido (VAT) de cargo invertido para países europeos.

El cargo invertido es un esquema de impuestos que transfiere la responsabilidad de la contabilidad y notificación del IVA del vendedor al comprador de mercancías o servicios. Por lo tanto, los destinatarios de mercancías o servicios informan el IVA diferido(en el rol de un vendedor) y el IVA soportado (en el rol de un comprador) en su declaración del IVA.

La directiva de la Unión Europea (EU) deja a los estados miembros determinar cómo se adaptarían los requisitos genéricos a los requisitos locales. Por tanto, en algunos países, el esquema de gasto invertido se implementa sólo para algunas mercancías o servicios y existen condiciones adicionales o umbrales en importes de ventas. En otros países, la responsabilidad de pago del IVA depende del estado del proveedor y el comprador. Si el comprador no es responsable de pagar el IVA, lo debe indicar claramente en la factura que emite el proveedor. Por ejemplo, la factura debe incluir las palabras “cargo invertido” y debe indicar qué posiciones están sujetas al sistema de cargo invertido. 

Para aplicar el cargo invertido, debe completar la configuración siguiente.

## Configurar códigos de impuestos
<a id="set-up-sales-tax-codes" class="xliff"></a>
Recomendamos que use los códigos de impuestos independientes para las operaciones de compra y las operaciones de ventas.

<table>
<body>
<tr>
<td><strong>Impuestos sobre ventas</strong></td>
<td>Cree un código de impuestos para las operaciones de ventas de cargo invertido (<strong>Impuestos</strong> > <strong>Impuestos indirectos</strong> > <strong>Impuestos</strong> > <strong>Códigos de impuestos</strong>).
</td>
</tr>
<tr>
<td><strong>Código de impuestos para compras</strong></td>
<td><p>Cree códigos de impuestos negativos y positivos para el IVA de cargo invertido para las compras (<strong>Impuestos</strong> > <strong>Impuestos indirectos</strong> > <strong>Impuestos</strong> > <strong>Códigos de impuestos</strong>).</p>
<ol>
<li>Cree un código de impuestos con un valor positivo.</li>
<li>Cree un código de impuestos con un valor negativo. Establezca la opción <strong>Permitir porcentaje de impuestos negativo</strong> en <strong>Sí</strong>.
Debe asignar este código de impuestos negativo a un grupo de impuestos de artículos y, a continuación, asignará dicho grupo a los artículos sujetos al IVA de cargo invertido.</li>
</ol>
<p>Para obtener más información, consulte la sección siguiente, sobre cómo configurar grupos de impuestos y grupos de impuestos de artículos.</p>
</td>
</tr>
</tbody>
</table>

## Configurar grupos de impuestos y grupos de impuestos de artículos
<a id="set-up-sales-tax-groups-and-item-sales-tax-groups" class="xliff"></a>
Recomendamos que use los grupos de impuestos independientes para las operaciones de compra y las operaciones de ventas.

<table>
<tr>
<td><strong>Grupo de impuestos sobre ventas</strong></td>
<td>Cree un grupo de impuestos para las operaciones de ventas con cargo invertido (<strong>Impuestos</strong> > <strong>Impuestos indirectos</strong> > <strong>Impuestos</strong> > <strong>Grupos de impuestos</strong>). En la pestaña <strong>Configuración</strong>, incluya el código de impuestos para cargo invertido en este grupo. Seleccione las casillas de verificación <strong>Exento</strong> y <strong>Gasto invertido</strong> para el código de impuestos.</td>
</tr>
<tr>
<td><strong>Grupos de impuestos sobre compras</strong></td>
<td>Cree un grupo de impuestos para las operaciones de compras con cargo invertido (<strong>Impuestos</strong> > <strong>Impuestos indirectos</strong> > <strong>Impuestos</strong> > <strong>Grupos de impuestos</strong>). En la pestaña <strong>Configuración</strong>, incluya los códigos de impuestos negativos y positivos en este grupo. Seleccione la casilla de verificación <strong>Cargo invertido</strong> para el código de impuestos con valor negativo.</td>
</tr>
<tr>
<td><strong>Grupos de impuestos de artículos</strong></td>
<td>Cree o actualice el grupo de impuestos de artículos con el código de impuestos que tenga un valor negativo (<strong>Impuestos</strong> > <strong>Impuestos indirectos</strong> > <strong>Impuestos</strong> > <strong>Grupos de impuestos de artículos</strong>). Debe asignar el grupo de impuestos de artículos predeterminado a los productos y categorías que están sujetos al cargo revertido.</td>
</tr>
</table>

## Configurar los grupos de cargo invertido
<a id="set-up-reverse-charge-groups" class="xliff"></a>
En la página **Grupos de artículos de cargo invertido** (**Impuestos** > **Configuración** > **Impuestos** > **Grupos de artículos de cargo invertido**), puede definir grupos de productos o servicios, o productos individuales o servicios, a los que se puede aplicar el cargo invertido. Para cada grupo de artículos de cargo invertido, defina la lista de artículos, grupos de artículos y categorías para ventas o compras.

## Configurar las reglas de cargo invertido
<a id="set-up-reverse-charge-rules" class="xliff"></a>
En la página **Reglas de cargo invertido** (**Impuestos** > **Configuración** > **Impuestos** > **Reglas de cargo invertido**), puede definir las reglas de la aplicabilidad para fines de compra y venta. Puede configurar un conjunto de reglas de aplicabilidad de cargo invertido. Para cada regla, establezca los siguientes campos:

- **Tipo de documento**: seleccione **Pedido de compra**, **Diario de facturas de proveedor**, **Pedido de ventas**, **Factura de servicios**, **Diario de facturas del cliente** o **Factura de proveedor**.
- **Tipo de país o región del socio**: seleccione **Nacional**, **UE** o **Extranjero**. Además, si la regla se puede aplicar a todos los socios comerciales, independientemente del país o la región de la dirección, seleccione **Todos**.
- **Dirección de entrega local**: seleccione esta casilla para aplicar la regla a las entregas dentro del mismo país o región. Esta casilla no se puede seleccionar para los tipos de documento **Diario de facturas del proveedor** y **Diario de facturas del cliente**.
- **Grupo de artículos de cargo invertido**: seleccione el grupo al que la regla se puede aplicar.
- **Importe del umbral**: el esquema de cargo invertido se aplica a una factura solo si el valor de los artículos o servicios que se incluyen en el grupo de artículos de cargo invertido supera el límite que especifique aquí.

Puede utilizar los campos **Fecha de vigencia** y **Fecha de vencimiento** para definir el período en que es efectiva la regla.

Además, puede especificar si va a aparecer una notificación y si la línea del documento se actualiza con el grupo de impuestos predeterminado de cargo invertido si la condición para dicha línea del documento se cumple. Están disponibles las siguientes opciones:

- **Ninguno**: la línea del documento no se actualiza.
- **Solicitud**: aparece una notificación para confirmar que el cargo invertido se puede aplicar.
- **Establecer**: la línea del documento se actualiza sin la notificación adicional.

## Configurar parámetros predeterminados
<a id="set-up-default-parameters" class="xliff"></a>
Para habilitar la funcionalidad, en la página **Parámetros de contabilidad general**, en la pestaña **Cargo invertido**, establezca la opción **Habilitar cargo invertido** en **Sí**. En el los campos **Grupo de impuestos del pedido de compra** y **Grupo de impuestos de pedido de ventas**, seleccione los grupos de impuestos predeterminados. Cuando se cumple una condición de la aplicabilidad de cargo invertido, la línea de pedido de ventas o compra se actualiza con estos grupos de impuestos.

## Cargo invertido en una factura de ventas
<a id="reverse-charge-on-a-sales-invoice" class="xliff"></a>
Para las ventas sujetas al modelo de cargo invertido, el vendedor no carga el IVA. En su lugar, la factura indica los artículos sujetos al IVA de cargo invertido y el importe total del IVA de cargo invertido.

Cuando se registra una factura de ventas con cargo invertido, las transacciones de impuestos tienen la dirección fiscal de **Impuestos repercutidos** y los impuestos cero, y la casilla de verificación **Cargo invertido** está seleccionada.

## Cargo invertido en una factura de compras
<a id="reverse-charge-on-a-purchase-invoice" class="xliff"></a>
Para las compras sujetas a cargo invertido, el comprador que recibe la factura con el cargo invertido actúa como un comprador y vendedor a efectos contables de IVA.

Cuando se registra una factura de compra con cargo invertido, se crean dos transacciones de impuestos. Una transacción tiene la dirección fiscal de **Impuestos soportados**. La otra transacción tiene la dirección fiscal de **Impuestos repercutidos** y se selecciona la casilla de verificación **Cargo invertido**.

