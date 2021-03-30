---
title: L. MAT de activos
description: Este tema describe las listas de materiales (BOM) de activos en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetStandardSparePartsItemGroup, EntAssetObjectBOM
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4e5d6d6245f27534d176ac03ca762aff91afb0ca
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253191"
---
# <a name="asset-boms"></a>L. MAT de activos

[!include [banner](../../includes/banner.md)]

 

Este tema describe las listas de materiales (BOM) de activos en Administración de activos. La página **L. MAT de activos** muestra una lista de todos los elementos (piezas de repuesto y otros) que se utilizan en un activo durante su vida útil completa. Al crear un nuevo activo, debe considerar configurar una L. MAT de activos como parte del procedimiento de configuración. De esta manera, puede realizar un seguimiento del historial de artículos para el activo a partir de la fecha de creación.

Cuando haya completado un trabajo de mantenimiento y el consumo de artículos se ha registrado en una orden de trabajo, puede seguir el consumo de repuestos y otros elementos que se utilicen en el activo. Esta funcionalidad permite conservar un registro completo del consumo de artículos para todos sus activos. Por ejemplo, puede usar el registro para controlar si una pieza de repuesto específica se reemplazará con frecuencia o para realizar un seguimiento de las piezas de repuesto u otros artículos que se usan actualmente en un activo.

> [!NOTE]
> En una orden de trabajo, el consumo de artículos puede incluir repuestos y otros artículos adicionales, como lubricantes, pernos y juntas.

Una L. MAT de activos se puede actualizar automáticamente según la configuración de Administración de activos. Si se ha creado un estado de ciclo de vida de orden de trabajo para conttrolar las órdenes de trabajo finalizadas o completadas y si la opción **Actualizar L. MAT de activos** para ese estado de ciclo de vida de la orden de trabajo se establece en **Sí** en la página **Estados de ciclo de vida de orden de trabajo**, todos los artículos que se usan en la orden de trabajo se actualizarán automáticamente en la página **L. MAT de activos** cuando se actualice la orden de trabajo a ese estado de ciclo de vida. 


También puede actualizar manualmente una lista de materiales de activos creando líneas de artículos nuevas en la página **L. MAT de activos**.

En la página **L. MAT de activos** puede realizar un seguimiento del historial de piezas de repuesto para los activos después de que el consumo de artículos se registre en una orden de trabajo. Para utilizar esta funcionalidad, debe seleccionar los grupos de artículos que se deben usar para el registro de piezas de repuesto en la página **Grupos de artículos de piezas de repuesto**.

Para usar la funcionalidad de lista de materiales de activos, primero debe configurar los grupos de artículos de piezas de repuesto necesarios. A continuación, si desea que la lista de materiales de activos se actualice automáticamente cuando se complete uan orden de trabajo, puede configurar un estado de ciclo de vida de orden de trabajo para gestionar esa actualización. 


## <a name="set-up-spare-parts-item-groups"></a>Configurar grupos de artículos de piezas de repuesto

La configuración del historial de piezas de repuesto se basa en los grupos de artículos creados en el módulo **Gestión de inventarios y almacenes**. En Administración de activos, los grupos de artículos se configuran de manera que pueda realizar un seguimiento del historial de piezas de repuesto para los artículos de los grupos de artículos seleccionados.

1. Seleccione **Administración de activos** \> **Configuración** \> **Activo** \> **Grupos de artículos de piezas de repuesto**.
2. Seleccione **Nuevo** para configurar un grupo de artículos.
3. Seleccione el grupo en el campo **Grupo de artículos**. El nombre del grupo se inserta automáticamente en el campo **Nombre**.

## <a name="view-and-update-asset-boms"></a>Ver y actualizar las listas de materiales de activos

Después de registrar el consumo de artículos en una orden de trabajo, puede ver el consumo de artículos registrado en la página **L. MAT de activos**.

1. Seleccione **Administración de activos** \> **Común** \> **Activos** \> **Activos activos**. Seleccione el activo en la lista y a continuación **L. MAT de activos**.

    > [!NOTE]
    > Para ver todos los registros de consumo de artículos de todos los activos, seleccione **Administración de activos** \> **Consultas** \> **Activos** \> **L. MAT de activos**.

2. Seleccione **Actualizar L. MAT de activos**. Puede agregar activos, tipos de activos y recursos a la actualización como sea necesario seleccionando **Seleccionar**. Seleccione **Aceptar** para iniciar la actualización. También puede configurar la función Actualizar como trabajo por lotes.
3. Si desea ver más información relacionada con los artículos, puede agregar dimensiones de inventario. Seleccione **Inventario** \> **Presentación de dimensiones** y seleccione las casillas de las dimensiones que desea ver. Para conservar esta configuración para todos los activos en la página **L. MAT de activos**, establezca la opción **Guardar configuración** en **Sí**.
4. Para obtener una visión general de dónde se usa el artículo de la línea seleccionada en Administración de activos, en relación con los activos, los valores predeterminados de los tipos de trabajo, las piezas de repuesto y las órdenes de trabajo, seleccione **Artículo donde utilizado**. 
5. Si desea ver solo las líneas de artículos activos, seleccione **Ver** \> **Actual**. Para ver todas las líneas de artículo, incluidas las líneas cuya fecha de caducidad sea anterior a la fecha actual, seleccione **Ver** \> **Todo**.

> [!NOTE]
> Cuando haya completado una orden de trabajo, si algunos artículos o repuestos relacionados con el activo relacionado han caducado o han sido reemplazados por otros artículos o repuestos, recomendamos que actualice la lista de materiales de activos en consecuencia.

## <a name="create-a-new-item-line-in-an-asset-bom"></a>Crear una nueva línea de artículo en una lista de materiales de activos

Puede crear manualmente líneas de artículos para los activos.

1. En la página **L. MAT de activos**, seleccione **Nuevo**.
2. En el campo **Activo**, seleccione el activo para el que va a agregar una línea de artículo.
3. En el campo **Número de línea**, escriba un número secuencial.
4. En el campo **Vigencia**, seleccione una fecha inicial para el artículo.
5. Si el artículo va a expirar, en el campo **Caducidad**, especifique una fecha final.
6. Seleccione el artículo en el campo **Número de artículo**. El nombre se inserta automáticamente en el campo **Nombre de producto**.
7. En el campo **Cantidad**, escriba la cantidad utilziada. El campo **Unidad** se actualiza automáticamente.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]