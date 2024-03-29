---
title: Fabricantes y modelos de activos
description: Este artículo explica cómo configurar fabricantes de activos y los modelos relacionados en Administración de activos.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetProductLookup, EntAssetModelLookup, EntAssetProduct
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b00cb62926f3a482ec655235b6e2f5880edbcd04
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016286"
---
# <a name="asset-manufacturers-and-models"></a>Fabricantes y modelos de activos

[!include [banner](../../includes/banner.md)]

 

Este artículo explica cómo configurar fabricantes de activos y los modelos relacionados en Administración de activos. Los modelos pueden estar relacionados con los tipos de activos.

## <a name="set-up-product-model-relations"></a>Configurar relaciones entre productos y modelos

1. Seleccione **Administración de activos** \> **Configuración** \> **Activos** \> **Fabricante y modelo**.
2. Seleccione **Nuevo** para crear un producto nuevo.
3. En el campo **Fabricante**, especifique un nombre para el fabricante del activo.
4. En el campo **Descripción**, escriba una descripción.
5. En el FastTab **Modelos** , seleccione **Agregar** para crear un modelo de activo que debe estar relacionado con el fabricante del activo.
6. En el campo **Modelo**, especifique un nombre para el modelo del activo.
7. En el campo **Descripción**, escriba una descripción.
8. En el campo **Tipo de activo**, seleccione el tipo de activo con el que debe estar relacionado el modelo del fabricante.

    > [!NOTE]
    > También puede configurar las relaciones para los tipos, los fabricantes, y los modelos de activos en la búsqueda **Tipos del activo**. Para obtener más información, consulte [Tipos de activo](../setup-for-objects/object-types.md).

    En el FastTab **Detalles**, el campo **Modelos** muestra el número de modelos de activos que se configuran en el fabricante del acivo seleccionado. El campo **Activos** muestra el número de activos que utilizan el fabricante seleccionado.
    
    El campo **Activos** muestra el número de objetos que utilizan el modelo de fabricante.

> [!NOTE]
> Un tipo de activo puede carecer de relaciones de modelo de fabricante de activos, puede estar relacionado con un solo modelo de fabricante de activos o puede estar relacionado con varios modelos de fabricante de activos. Si un tipo de activos está relacionado con al menos un modelo de fabricante, solo las combinaciones configuradas en la búsqueda **Modelo de fabricante** se pueden seleccionar en las páginas de Administración de activos donde se puede configurar una combinación de tipo de activo, fabricante y modelo. Las páginas son **Todos los activos**, **Niveles de servicio de activos**, **Valores predeterminados de tipo de trabajo** y **Líneas de presupuesto de mantenimiento**. Si algunos tipos de activos no están relacionados con ningún modelo de proveedor, en las páginas solo se muestran los tipos de activos y los modelos de fabricante que tampoco tienen ninguna relación con tipos de activos.

## <a name="select-a-manufacturer-and-model-on-an-object"></a>Seleccionar un fabricante y un modelo en un objeto

1. Seleccione **Administración de activos** \> **_Activos_* \> **Todos los activos**.
2. En la columna **Activo**, seleccione el vínculo para el activo. Aparecerá la página **Detalles**.
3. Seleccione **Editar**.
4. En el FastTab **General**, seleccione valores **Fabricante** y **Modelo**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]