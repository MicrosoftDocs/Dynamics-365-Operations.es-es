---
title: IVA intracomunitario para España
description: Este tema proporciona información sobre la funcionalidad dedicada al impuesto sobre el valor añadido intracomunitario (IVA). Explica cómo se activa la funcionalidad, cómo se calculan e imprimen los importes de IVA intracomunitarios, y revisa los importes de IVA intracomunitarios que se han registrado.
author: Anasyash
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendFormletterParameters, VendParameters, TaxTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 271523
ms.search.region: Spain
ms.author: anasyash
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 346020432a38b3e6100788a48006e7f99c99b6e5
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1537806"
---
# <a name="intra-community-vat-for-spain"></a>IVA intracomunitario para España
[!include [banner](../includes/banner.md)]

Este tema proporciona información sobre la funcionalidad dedicada al impuesto sobre el valor añadido intracomunitario (IVA). Explica cómo se activa la funcionalidad, cómo se calculan e imprimen los importes de IVA intracomunitarios, y revisa los importes de IVA intracomunitarios que se han registrado.

La información acerca del impuesto sobre el valor añadido (IVA) intracomunitario se puede calcular y registrar automáticamente. Cuando se registra una factura de proveedor de la Unión Europea (EU), se crean dos transacciones de IVA. Una transacción de IVA se crea para los impuestos pagaderos, y otra transacción de IVA se crea para los impuestos soportados. Antes de poder utilizar la funcionalidad del IVA intracomunitario, debe habilitar la opción **IVA intracomunitario** en la pestaña **Impuestos y contabilidad** de la página **Parámetros de proveedores** .

## <a name="calculating-intracommunity-vat-for-purchase-transactions"></a>Cálculo del IVA intracomunitario para las transacciones de compra
Para calcular el IVA intracomunitario de las transacciones de compra, debe tener dos códigos de impuestos que tengan el mismo porcentaje de impuestos. Sin embargo, un código debe tener un porcentaje de impuestos positivo, y el otro código debe tener un porcentaje de impuestos negativo. También debe tener un grupo de impuestos que contenga un código de impuestos positivo y un código de impuestos negativo. Seleccione la casilla de verificación **IVA intracomunitario** para la línea que tenga un código de impuestos negativo. 

## <a name="printing-intracommunity-vat-on-a-purchase-invoice"></a>Imprimir IVA intracomunitario en una factura de compra
Para imprimir el IVA intracomunitario en una factura de compra, active la opción **Imprimir impuesto de UE en facturas españolas** en la pestaña **Factura** de la página **Configuración de formulario** (**Proveedores** &gt; **Configuración** &gt; **Formularios** &gt; **Configuración de formulario**).

## <a name="printing-invoices-that-have-intracommunity-vat-amounts"></a>Impresión de facturas que tienen importes de IVA intracomunitarios
Para imprimir facturas de compra y facturas intracomunitarias que tienen importes de IVA intracomunitarios, en la página de la factura de proveedor, en la pestaña **Proceso** , haga clic en **Configuración de impresión** &gt; **Opciones de impresión**. En el cuadro de diálogo **Opciones de impresión**, habilite las opciones **Imprimir factura** e **Imprimir autofactura intracomunitaria** .

## <a name="reviewing-posted-intracommunity-vat-amounts"></a>Revisar importes de IVA intracomunitarios enviados
Para revisar los importes de IVA intracomunitarios registrados, ejecute la consulta de impuestos registrados (**Impuestos** &gt; **Consultas e informes** &gt; **Consultas de impuestos** &gt; **Impuestos registrados**). En la página **Impuestos registrados** , en la pestaña **General** , si se selecciona la casilla de verificación **IVA intracomunitario**, la transacción de impuestos es una transacción de IVA intracomunitario. Los libros de IVA de España se deben configurar para que las transacciones de IVA soportadas y repercutidas se reflejen en las secciones adecuadas. Para configurar los libros de IVA para España, haga clic en **Impuestos** &gt; **Configuración** &gt; **Impuestos** &gt; **Libros de IVA españoles**. Para obtener más información, vea el modelo 340 de declaración de IVA de España.


