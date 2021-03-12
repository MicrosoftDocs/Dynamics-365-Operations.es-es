---
title: Mecanismo de cargo invertido para el régimen de IVA e IBS
description: Este tema explica cómo configurar el impuesto sobre el valor añadido (IVA) de cargo invertido en los países europeos, Arabia Saudí y Singapur.
author: epodkolz
manager: AnnBe
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Saudi Arabia, Spain, Sweden, United Kingdom, Singapore, Bahrain, Kuwait, Oman, Qatar
ms.author: epodkolz
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 46b26fc1c0c45be894e226080a5aa9d5ae48b595
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006000"
---
# <a name="reverse-charge-mechanism-for-vatgst-scheme"></a>Mecanismo de cargo invertido para el régimen de IVA e IBS

[!include [banner](../includes/banner.md)]

Este tema describe un enfoque genérico para configurar la funcionalidad de cargo invertido para países o regiones que adoptan los esquemas de IVA o IBS.
                                                                                 
La disponibilidad de la funcionalidad por país o región se gestiona mediante las siguientes funciones en el espacio de trabajo **Administración de características**.

| Característica                                              | País/región                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Sin característica específica                                | Austria </br>Bélgica </br>Bulgaria </br>Croacia </br>Chipre </br>República Checa </br>Dinamarca  </br>Estonia  </br>Finlandia  </br>Francia  </br>Alemania  </br>Hungría  </br>Islandia  </br>Irlanda  </br>Italia  </br>Letonia  </br>Liechtenstein  </br>Lituania  </br>Luxemburgo  </br>Países Bajos  </br>Noruega-Polonia </br>Portugal </br>Rumanía  </br>Arabia Saudí </br>Singapur  </br>Eslovaquia  </br>Eslovenia  </br>España  </br>Suecia  </br>Suiza  </br>Reino Unido  </br>Emiratos Árabes Unidos |
| Cargo invertido para países adicionales            | Baréin  </br>Kuwait  </br>Omán  </br>Catar                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Habilitar mecanismo de cargo invertido para el esquema de IVA e IBS | Todos los demás países o regiones excepto:  </br>Brasil  </br>India  </br>Rusia                                                                                                                                                                                                                                                                                                                                                                                         |
 
 Para obtener más información, consulte la sección [Habilitar el mecanismo de cargo invertido para la característica del régimen de IVA e IBS](#enable-reverse-charge) más adelante en este tema.

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

## <a name="set-up-sales-tax-groups-and-item-sales-tax-groups"></a><a name="sales-tax-item-sales-tax-groups"></a>Configurar grupos de impuestos y grupos de impuestos de artículos
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

## <a name="set-up-reverse-charge-item-groups"></a><a name="reverse-charge-item-group"></a>Configurar los grupos de elementos de cargo invertido
En la página **Grupos de artículos de cargo invertido** (**Impuestos** &gt; **Configuración** &gt; **Impuestos** &gt; **Grupos de artículos de cargo invertido**), puede definir grupos de productos o servicios, o productos individuales o servicios, a los que se puede aplicar el cargo invertido. Para cada grupo de artículos de cargo invertido, defina la lista de artículos, grupos de artículos y categorías para ventas o compras.

## <a name="set-up-reverse-charge-rules"></a><a name="reverse-charge-rules"></a>Configurar las reglas de cargo invertido
En la página **Reglas de cargo invertido** (**Impuestos** &gt; **Configuración** &gt; **Impuestos** &gt; **Reglas de cargo invertido**), puede definir las reglas de la aplicabilidad para fines de compra y venta. Puede configurar un conjunto de reglas de aplicabilidad de cargo invertido. Para cada regla, establezca los siguientes campos:

- **Tipo de documento**: seleccione **Pedido de compra**, **Diario de facturas de proveedor**, **Pedido de ventas**, **Factura de servicios**, **Diario de facturas del cliente** o **Factura de proveedor**.
- **Tipo de país o región del socio**: seleccione **Nacional**, **UE**, **GCC** o **Extranjero**. Además, si la regla se puede aplicar a todos los socios comerciales, independientemente del país o la región de la dirección, seleccione **Todos**.
- **Dirección de entrega local**: seleccione esta casilla para aplicar la regla a las entregas dentro del mismo país o región. Esta casilla no se puede seleccionar para los tipos de documento **Diario de facturas del proveedor** y **Diario de facturas del cliente**.
- **Grupo de artículos de cargo invertido**: seleccione el grupo al que la regla se puede aplicar.
- **Importe del umbral**: el esquema de cargo invertido se aplica a una factura solo si el valor de los artículos o servicios que se incluyen en el grupo de artículos de cargo invertido supera el límite que especifique aquí.

También puede utilizar los campos **Fecha de vigencia** y **Fecha de vencimiento** para definir el periodo en que es efectiva la regla.

Además, puede especificar si va a aparecer una notificación y si la línea del documento se actualiza con el grupo de impuestos predeterminado de cargo invertido si la condición para dicha línea del documento se cumple. Están disponibles las siguientes opciones:

- **Ninguno**: la línea del documento no se actualiza.
- **Solicitud**: aparece una notificación para confirmar que el cargo invertido se puede aplicar.
- **Establecer**: la línea del documento se actualiza sin la notificación adicional.

## <a name="set-up-countryregion-properties"></a><a name="Set-up-Country/region-properties"></a>Configurar las propiedades de país/región
En la página **Parámetros de comercio exterior** (**Impuesto** &gt; **Configuración** &gt; **Impuesto** &gt; **Comercio exterior** &gt; **Parámetros de comercio exterior**), en la pestaña **Propiedades de país/región**, establezca el país o región de la entidad jurídica actual en *Nacional*. Configure **Tipo de país/región** de los países o regiones de la UE que participen en comercio de la UE con la entidad jurídica actual en *UE*. Configure **Tipo de país/región** de los países o regiones GCC que participen en comercio GCC con la entidad jurídica actual en *GCC*.

## <a name="set-up-default-parameters"></a>Configurar parámetros predeterminados
Para habilitar la funcionalidad para cargo revertido, en la página **Parámetros de contabilidad general**, en la pestaña **Cargo invertido**, establezca la opción **Habilitar cargo invertido** en **Sí**. En el los campos **Grupo de impuestos del pedido de compra** y **Grupo de impuestos de pedido de ventas**, seleccione los grupos de impuestos predeterminados. Cuando se cumple una condición de la aplicabilidad de cargo invertido, la línea de pedido de ventas o compra se actualiza con estos grupos de impuestos.

## <a name="reverse-charge-on-a-sales-invoice"></a><a name="reverse-charge-sale"></a>Cargo invertido en una factura de ventas
Para las ventas sujetas al modelo de cargo invertido, el vendedor no carga el IVA. En su lugar, la factura indica los artículos sujetos al IVA de cargo invertido y el importe total del IVA de cargo invertido.

Cuando se registra una factura de ventas con cargo invertido, las transacciones de impuestos tienen la dirección fiscal de **Impuestos repercutidos** y los impuestos cero, y las casillas de verificación **Cargo invertido** y **Exento** están seleccionadas.

## <a name="reverse-charge-on-a-purchase-invoice"></a><a name="reverse-charge-purchase"></a>Cargo invertido en una factura de compras
Para las compras sujetas a cargo invertido, el comprador que recibe la factura con el cargo invertido actúa como un comprador y vendedor a efectos contables de IVA.

Cuando se registra una factura de compra con cargo invertido, se crean dos transacciones de impuestos. Una transacción tiene la dirección fiscal de **Impuestos soportados**. La otra transacción tiene la dirección fiscal de **Impuestos repercutidos** y se selecciona la casilla de verificación **Cargo invertido**.

En el captura de pantalla siguiente, una transacción tiene la dirección **Impuestos soportados** y otra transacción tiene la dirección **Impuestos repercutidos**. 

![Impuestos registrados](media/apac-sau-posted-sales-tax.png)

## <a name="enable-reverse-charge-mechanism-for-vatgst-scheme-feature"></a><a name="enable-reverse-charge"></a>Habilitar mecanismo de cargo invertido para la característica de régimen de IVA e IBS
En el espacio de trabajo **Administración de características**, busque la característica y seleccione **Habilitar**.

Después de habilitar la característica, la pestaña **Cargo invertido** está disponible en todas las entidades jurídicas. Habilite la funcionalidad de Cargo invertido para una entidad jurídica estableciendo la opción **Habilitar cargo invertido** en **Sí**.

Las siguientes páginas y elementos de menú relacionados con la configuración de características estarán disponibles:
 - **Grupos de elementos de cargo invertido** (**Impuesto** > **Configuración** > **Impuesto** > **Grupos de elementos de cargo invertido**). Para obtener más información, vea la sección [Configurar grupos de elementos de cargo invertido](#reverse-charge-item-group).
 - **Reglas de cargo invertido** (**Impuesto** > **Configuración** > **Impuesto** > **Reglas de cargo invertido**). Vea [Configurar las reglas de cargo invertido](#reverse-charge-rules).
 - **Parámetros de comercio exterior** (**Impuesto** > **Configuración** > **Impuesto** > **Comercio Exterior** > **Parámetros de comercio exterior**). Vea [Configurar las propiedades de país o región](#Set-up-Country/region-properties).

La casilla de verificación **Cargo invertido** estará disponible en las páginas **Grupo de impuestos** e **Impuesto registrado**. Para obtener más información, vea las secciones [Configurar grupos de impuestos y grupos de impuestos sobre las ventas de artículos](#sales-tax-item-sales-tax-groups), [Cargo invertido en facturas de venta](#reverse-charge-sale) y [Cargo invertido en facturas de compra](#reverse-charge-purchase).
