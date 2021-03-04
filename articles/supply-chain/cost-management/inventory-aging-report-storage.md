---
title: Almacenamiento de informe de vencimiento de inventario
description: Este tema describe la funcionalidad que permite ejecutar un informe de antigüedad de inventario y generar resultados como formulario y gráfico.
author: AndersGirke
manager: tfehr
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2019-01-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: c4a1480cf96a4ba753b436c04eb8f7b01379da48
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436830"
---
# <a name="inventory-aging-report-storage"></a>Almacenamiento de informe de vencimiento de inventario

[!include [banner](../includes/banner.md)]

En Microsoft Dynamics 365 Supply Chain Management, puede ejecutar un informe de **Almacenamiento de informe de vencimiento de inventario** y generar resultados como un formulario y gráfico. En el formulario, las columnas y saldos agregados se ajustan dinámicamente, en función del diseño que se configura. El gráfico proporciona una visión general visual que admite el filtrado y permite explorar en profundidad los detalles. Además, una entidad de datos que se denomina **Informe de vencimiento de inventario** permite exportar los resultados de una ejecución de informe de **Almacenamiento de informe de vencimiento de inventario** en un formato como un archivo Microsoft Excel o PDF.

Este método de ejecutar un informe de **Almacenamiento de informe de vencimiento de inventario** resulta útil cuando los resultados contienen muchas líneas. Por ejemplo, el resultado contendrá muchas líneas si tiene 50 000 artículos y 300 tiendas que se crean como almacenes, y solicita vencimientos de inventario por elemento, sitio y almacén.

## <a name="enable-the-inventory-value-storage-report-feature"></a>Habilitar la función de informe de almacenamiento de valor de inventario

Antes de poder usar esta función debe habilitarla en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y habilitarla si es necesario. Aquí, la función aparece como:

- **Módulo** - Gestión de costes
- **Nombre de la característica**: Almacenamiento de informe de vencimiento de inventario

## <a name="run-an-inventory-aging-report-storage"></a>Ejecutar un almacenamiento de informe de vencimiento de inventario

1. Vaya a **Gestión de costes \> Consultas e informes \> Almacenamiento del informe de vencimiento de inventario**.
1. Seleccione **Nuevo**.
1. En el campo **Identificador de procesos: nombre**, especifique un nombre único para informe.
1. Seleccione el informe **Identificación: Id.** y fíltrelo como sea necesario.

    La ejecución de informes se realiza siempre en un trabajo por lotes.

1. Después de que el trabajo por lotes se complete, se mostrará el resultado en la página **Almacenamiento del informe de vencimiento de inventario**.
1. Para ver el resultado como un formulario con un diseño tradicional de la cuadrículas, seleccione **Ver detalles**. Para ver el resultado como un gráfico agregado, seleccione **Ver gráfico**.

    > [!NOTE]
    > El formulario no incluirá los subtotales definidos en el diseño del informe.

La entidad de los datos **Informe de vencimiento de inventario** le permite exportar el resultado de un informe de **Almacenamiento de informe de vencimiento de inventario** aplicando un filtro para el campo **Identificador de procesos: nombre** a cualquier formato que admita la administración de datos.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]