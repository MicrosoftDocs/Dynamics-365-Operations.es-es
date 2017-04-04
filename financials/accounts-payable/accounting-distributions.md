---
title: Distribuciones contables
description: "Este artículo proporciona información acerca de distribuciones contables y describe las opciones disponibles para procesarlas. Las distribuciones contables se usan para asignar importes monetarios para un documento de origen en cuentas contables específicas."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AccountingDistribution
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 17231
ms.assetid: 9030355d-8e6e-408b-9e7d-7b346eaa652c
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: a98ce08dc115bc96cec07c2d6ced10d774785fe9
ms.openlocfilehash: b1057caae6f47e5a17e194834fbbcb9d7d731605
ms.lasthandoff: 03/31/2017


---

# <a name="accounting-distributions"></a>Distribuciones contables

Este artículo proporciona información acerca de distribuciones contables y describe las opciones disponibles para procesarlas. Las distribuciones contables se usan para asignar importes monetarios para un documento de origen en cuentas contables específicas. 

Las distribuciones contables son una capacidad de todo el programa que se usa y se extiende por cada documento de origen, como un pedido de compra, una factura de proveedor, un informe de gastos y una factura de servicios. De forma predeterminada, se genera una distribución contable predeterminada para cada línea del documento de origen y el importe monetario, y se habilita de manera condicional para la modificación. 

> [!Note] 
> Importes monetarios admiten del documento del encabezado de algunos documentos, también como gastos para los pedidos y las facturas. 

Las capacidades genéricas de distribución contable proporcionan las siguientes opciones para procesar distribuciones contables:

-   **Distribuir importes**: permite ver y modificar las distribuciones contables de una línea o encabezado de documento individual y todas las líneas secundarias, como impuestos o gastos.
    -   Para las distribuciones principales de importes monetarios (distribuciones principales), la cuenta principal y las dimensiones financieras se pueden editar directamente en el control de entrada segmentada en la cuadrícula. El precio total es un ejemplo típico de dicha distribución principal.
    -   Los importes de distribuciones se basan en el término divisa para el documento. Normalmente, esta divisa es la divisa de la transacción. Los importes de la divisa de notificación y contabilidad se generan como parte de la contabilidad del subdiario.
    -   Las distribuciones muestran la fecha de contabilidad y el evento de contabilidad. Normalmente, el evento de contabilidad se establece en **Ninguno** hasta que el documento se registra o se registra en el diario. En ese momento, el evento de contabilidad pasa a ser **Original**. Una vez registradas las distribuciones, no es posible modificar las distribuciones.
    -   El botón **Dividir** se puede habilitar para las distribuciones principales. **Dividir** genera nuevas distribuciones contables y la división se puede basar en el porcentaje, el importe o la cantidad.
    -   El botón **Distribuir de forma equitativa** se puede usar junto con **Dividir** para asignar automáticamente el importe de manera equitativa en todas las distribuciones.
    -   El botón **Restablecer** se puede habilitar para distribuciones principales cuando existen más de una distribución. **Restablecer** invierte cualquier modificación manual a la distribución eliminando todas las distribuciones existentes y volviendo a generar las distribuciones predeterminadas.
    -   Cualquier distribución secundaria, como descuento, cargos e impuestos, siempre sigue la distribución principal. Puede ver la relación primaria o secundaria en ** referencia ** &gt; ** información ** principal.
    -   La cuenta principal y la dimensión financiera pueden ser editables también para los elementos secundarios.
    -   Las dimensiones financieras de las distribuciones contables siguen un patrón predeterminado de que se puede extender un documento. Para obtener más información, consulte los artículos relacionados.
    -   Las distribuciones de desviación se pueden generar en escenarios de coincidencia, como la coincidencia entre una factura de proveedor y un pedido de compra. Puede ver las relaciones en la conciliación entre la distribución contable en ** referencia ** &gt; ** la información del documento **.
    -   El botón **Correcto** aparece y está habilitado para documentos que admiten correcciones. ** Correcto ** crea nuevas distribuciones. Primero, se crean las distribuciones que invierten las distribuciones originales. Estas distribuciones no se pueden modificar. Se crea Siguiente, las nuevas distribuciones contables concretas. Estas distribuciones se pueden modificar si las distribuciones originales se pueden modificar.
    -   El botón ** Detalles del proyecto** está habilitado como extensión cuando una línea está relacionada con un proyecto. Las distribuciones contables del proyecto le permiten modificar detalles como la fuente de financiación y las propiedades de la línea.
    -   Puede ver el estado de contabilidad del documento actual en ** ** referencia. El estado es para el documento entero, e indica si el documento se encuentra en proceso o completado.
-   ** Las distribuciones de la vista ** – ver las distribuciones contables para todas las líneas y importes monetarios en el documento. No pueden modificar las distribuciones contables desde esta vista.


Para obtener más información, consulte [las distribuciones contables y los asientos del subdiario contable de forma gratuita Ver el texto a las facturas accounting-distributions-subledger-journal-entries-vendor-invoices.md] ().

