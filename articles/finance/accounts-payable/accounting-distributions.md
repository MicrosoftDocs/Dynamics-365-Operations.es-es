---
title: Distribuciones contables
description: Este tema proporciona información acerca de distribuciones contables y describe las opciones disponibles para procesarlas.
author: ShylaThompson
ms.date: 09/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AccountingDistribution
audience: Application User
ms.reviewer: roschlom
ms.custom: 17231
ms.assetid: 9030355d-8e6e-408b-9e7d-7b346eaa652c
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3586ad009f4639d3606a935f98108b07d379852567e0faa365749f5b0bea07b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6749231"
---
# <a name="accounting-distributions"></a>Distribuciones contables

[!include [banner](../includes/banner.md)]

Este tema proporciona información acerca de distribuciones contables y describe las opciones disponibles para procesarlas. Las distribuciones contables se usan para asignar importes monetarios para un documento de origen en cuentas contables específicas. 

Las distribuciones contables son una capacidad de todo el programa que se usa y se extiende por cada documento de origen, como un pedido de compra, una factura de proveedor, un informe de gastos y una factura de servicios. De forma predeterminada, se genera una distribución contable predeterminada para cada línea del documento de origen y el importe monetario, y se habilita de manera condicional para la modificación. 

> [!NOTE] 
> Algunos documentos también admiten importes monetarios de documentos de encabezados, como gastos para pedidos y facturas. 

Las capacidades genéricas de distribución contable proporcionan las siguientes opciones para procesar distribuciones contables:

-   **Distribuir importes**: permite ver y modificar las distribuciones contables de una línea o encabezado de documento individual y todas las líneas secundarias, como impuestos o gastos.
    -   Para las distribuciones principales de importes monetarios (distribuciones principales), la cuenta principal y las dimensiones financieras se pueden editar directamente en el control de entrada segmentada en la cuadrícula. El precio total es un ejemplo típico de dicha distribución principal.
    -   Los importes de distribuciones se basan en el término divisa para el documento. Normalmente, esta divisa es la divisa de la transacción. Los importes de la divisa de notificación y contabilidad se generan como parte de la contabilidad del subdiario.
    -   Las distribuciones muestran la fecha de contabilidad y el evento de contabilidad. Normalmente, el evento de contabilidad se establece en **Ninguno** hasta que el documento se registra o se registra en el diario. En ese momento, el evento de contabilidad pasa a ser **Original**. Una vez registradas las distribuciones, no es posible modificar las distribuciones.
    -   El botón **Dividir** se puede habilitar para las distribuciones principales. **Dividir** genera nuevas distribuciones contables y la división se puede basar en el porcentaje, el importe o la cantidad.
    -   El botón **Distribuir de forma equitativa** se puede usar junto con **Dividir** para asignar automáticamente el importe de manera equitativa en todas las distribuciones.
    -   El botón **Restablecer** se puede habilitar para distribuciones principales cuando existen más de una distribución. **Restablecer** invierte cualquier modificación manual a la distribución eliminando todas las distribuciones existentes y volviendo a generar las distribuciones predeterminadas.
    -   Cualquier distribución secundaria, como descuento, cargos e impuestos, siempre sigue la distribución principal. Puede ver la relación principal-secundario en **Referencia** &gt; **Información de elemento principal**.
    -   La cuenta principal y la dimensión financiera pueden ser editables también para los elementos secundarios.
    -   Las dimensiones financieras de las distribuciones contables siguen un patrón predeterminado de que se puede extender un documento.
    -   Las distribuciones de desviación se pueden generar en escenarios de coincidencia, como la coincidencia entre una factura de proveedor y un pedido de compra. Puede ver las relaciones coincidentes entre la distribución contable en **Referencia** &gt; **Información de documento**.
    -   El botón **Correcto** aparece y está habilitado para documentos que admiten correcciones. **Correcto** crea nuevas distribuciones. Primero, se crean las distribuciones que invierten las distribuciones originales. Estas distribuciones no se pueden modificar. A continuación se crean las nuevas distribuciones contables correctas. Estas distribuciones se pueden modificar si las distribuciones originales se pueden modificar.
    -   El botón **Detalles del proyecto** está habilitado como extensión cuando una línea está relacionada con un proyecto. Las distribuciones contables del proyecto le permiten modificar detalles como la fuente de financiación y las propiedades de la línea.
    -   Puede ver el estado de contabilidad del documento actual en **Referencia**. El estado es para el documento entero, e indica si el documento se encuentra en proceso o completado.
-   **Ver distribuciones**: permite ver las distribuciones contables para todas las líneas y todos los importes monetarios en el documento. No pueden modificar las distribuciones contables desde esta vista.

En la versión 10.0.13, se agregó una función que valida la tabla de distribución contable para garantizar que los nuevos campos estén configurados correctamente. Esta característica se llama **Habilitar la validación adicional de datos para documentos utilizando el marco de contabilidad de documentos de origen**. Para usar la función, debe habilitarla usando el espacio de trabajo **Gestión de funciones**. Para habilitar la función, busque el nombre de la función en el campo **Buscar** de la página **Gestión de funciones** y luego seleccione **Habilitar ahora**.

Para obtener más información, consulte [Distribuciones contables y asientos del subdiario contable para las facturas de proveedores](accounting-distributions-subledger-journal-entries-vendor-invoices.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]