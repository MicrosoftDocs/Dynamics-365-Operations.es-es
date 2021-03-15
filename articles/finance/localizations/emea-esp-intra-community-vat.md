---
title: IVA intracomunitario para España
description: Este tema proporciona información sobre la funcionalidad dedicada al impuesto sobre el valor añadido intracomunitario (IVA).
author: Anasyash
manager: AnnBe
ms.date: 07/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendFormletterParameters, VendParameters, TaxTrans
audience: Application User
ms.reviewer: kfend
ms.custom: 271523
ms.search.region: Spain
ms.author: anasyash
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 631e0824c2df36ad1a1c615f1a1dd1c63e793ecc
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992739"
---
# <a name="intra-community-vat-for-spain"></a>IVA intracomunitario para España
[!include [banner](../includes/banner.md)]

Este tema proporciona información sobre la funcionalidad dedicada al impuesto sobre el valor añadido intracomunitario (IVA). Explica cómo se activa la funcionalidad, cómo se calculan e imprimen los importes de IVA intracomunitarios, y revisa los importes de IVA intracomunitarios que se han registrado.

La información acerca del impuesto sobre el valor añadido (IVA) intracomunitario se puede calcular y registrar automáticamente. Cuando se registra una factura de proveedor de la Unión Europea (EU), se crean dos transacciones de IVA. Una transacción de IVA se crea para los impuestos pagaderos, y otra transacción de IVA se crea para los impuestos soportados. Antes de poder utilizar la funcionalidad de IVA intracomunitario, debe habilitar la opción **IVA intracomunitario** en la ficha desplegable **Impuestos** de la pestaña **Impuestos y contabilidad** de la página **Parámetros de proveedores** (**Proveedores** \> **Configuración** \> **Parámetros de proveedores**).

## <a name="calculating-intracommunity-vat-for-purchase-transactions"></a>Cálculo del IVA intracomunitario para las transacciones de compra
Para calcular el IVA intracomunitario de las transacciones de compra, debe tener dos códigos de impuestos que tengan el mismo porcentaje de impuestos. Sin embargo, un código debe tener un porcentaje de impuestos positivo, y el otro código debe tener un porcentaje de impuestos negativo. También debe tener un grupo de impuestos que contenga un código de impuestos positivo y un código de impuestos negativo. Seleccione la casilla de verificación **IVA intracomunitario** para la línea que tenga un código de impuestos negativo. 

## <a name="printing-intracommunity-vat-on-a-purchase-invoice"></a>Imprimir IVA intracomunitario en una factura de compra
Para imprimir el IVA intracomunitario en una factura de compra, active la opción **Imprimir impuesto de UE en facturas españolas** en la pestaña **Factura** de la página **Configuración de formulario** (**Proveedores** \> **Configuración** \> **Formularios** \> **Configuración de formulario**).

## <a name="printing-invoices-that-have-intracommunity-vat-amounts"></a>Impresión de facturas que tienen importes de IVA intracomunitarios
Para imprimir facturas de compra y facturas intracomunitarias que tienen importes de IVA intracomunitarios, en la página de la factura de proveedor, en la pestaña **Proceso**, seleccione **Configuración de impresión** &gt; **Opciones de impresión**. En el cuadro de diálogo **Opciones de impresión**, habilite las opciones **Imprimir factura** e **Imprimir autofactura intracomunitaria** .

> [!NOTE]
> El país de un proveedor debe estar configurado como estado miembro de la UE. Para ello, vaya a **Impuestos** \> **Configuración** \> **Comercio exterior \> Pestaña Propiedades de país/región de Parámetros de comercio exterior**).

## <a name="reviewing-posted-intracommunity-vat-amounts"></a>Revisar importes de IVA intracomunitarios enviados
Para revisar los importes de IVA intracomunitarios registrados, ejecute la consulta de impuestos registrados (**Impuestos** \> **Consultas e informes** \> **Consultas de impuestos** \> **Impuestos registrados**). En la página **Impuestos registrados** , en la pestaña **General** , si se selecciona la casilla de verificación **IVA intracomunitario**, la transacción de impuestos es una transacción de IVA intracomunitario. Los libros de IVA de España se deben configurar para que las transacciones de IVA soportadas y repercutidas se reflejen en las secciones adecuadas. Para configurar los libros de IVA para España, vaya a **Impuestos** \> **Configuración** \> **Impuestos** \> **Libros de IVA españoles**. Para obtener más información, consulte [Informe 340 para España](emea-esp-report-340.md).

## <a name="example"></a>Ejemplo

En el siguiente ejemplo se muestra cómo puede configurar códigos de impuestos y registrar e imprimir transacciones para el IVA intracomunitario.

1. Vaya a **Proveedores** \> **Configuración** \> **Parámetros de proveedores**. 
2. En la pestaña **Impuestos y contabilidad**, en la ficha desplegable **Impuestos**, establezca la opción **IVA intracomunitario** en **Sí**.

![Página de parámetros de proveedores, pestaña de impuestos y contabilidad, campo de IVA intracomunitario](media/1_Intra-community_VAT.png)

3. Vaya a **Impuestos** \> **Impuestos indirectos** \> **Impuestos** \> **Códigos de impuestos** y cree un par de códigos de impuestos con el mismo porcentaje de impuestos para cada índice de impuestos. Un código debe tener un porcentaje de impuestos positivo, y el otro código debe tener un porcentaje de impuestos negativo. Para códigos con porcentaje de impuestos negativo, en la ficha desplegable **Cálculo**, establezca la opción **Permitir porcentaje de impuestos negativo a las ventas** en **Sí**.

| **Código de impuestos** | **Porcentaje** | **Descripción**                       |
|--------------------|----------------|---------------------------------------|
| EU21               | 21             | Compras en la UE con una tasa del 21 por ciento. |
| EU-21              | -21            | Compras en la UE con una tasa del 21 por ciento. |
| EU10               | 10             | Compras en la UE con una tasa del 10 por ciento. |
| EU-10              | -10            | Compras en la UE con una tasa del 10 por ciento. |
| EU4               | 4             | Compras en la UE con una tasa del 4 por ciento. |
| EU-4              | -4            | Compras en la UE con una tasa del 4 por ciento. |

4.  Vaya a **Impuestos** \> **Impuestos indirectos** \> **Impuestos** \> **Grupos de impuestos** y cree un nuevo grupo de impuestos denominado **UE**.
5. En la ficha desplegable **Configuración**, agregue los siguientes códigos.

| **Código de impuestos** | **IVA intracomunitario** |
|--------------------|-------------------------|
| EU21               | Nº                      |
| EU-21              | Sí                     |
| EU10               | Nº                      |
| EU-10              | Sí                     |
| EU4                | Nº                      |
| EU-4               | Sí                     |

6.  Vaya a **Impuestos** \> **Impuestos indirectos** \> **Impuestos** \> **Grupos de impuestos de artículos** y cree los siguientes grupos de impuestos de artículos.

| **Grupo de impuestos de artículos** | **Códigos de impuestos** |
|--------------------------|---------------------|
| 21                       | EU21, EU-21         |
| 10                       | EU10, EU-10         |
| 4                        | EU4, EU-4           |

7.  Vaya a **Proveedores** \> **Facturas** \> **Diario de facturas** y cree la siguiente línea.

| **Fecha**        | **Tipo de transacción** | **Importe neto** | **Importe de IVA** | **Códigos de impuestos** |
|-----------------|----------------------|----------------|----------------|---------------------|
| 1 de enero de 2020 | Factura de cliente     | 1000           | 210            | EU21 EU-21          |

8.  Verifique que haya dos líneas en la lista **Transacciones de impuestos**.

    ![Líneas de transacción de impuestos](media/2_Sales_tax.png)

9.  Seleccione **Registrar** para registrar la transacción y luego seleccione **Aceptar**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]