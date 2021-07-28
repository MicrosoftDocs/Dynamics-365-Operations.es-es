---
title: Crear una jerarquía de navegación de canales
description: En este tema se describe cómo crear una nueva jerarquía de navegación de canales en Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 04/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: e43c4c00545dfecb2f9a2192f81cd25300e3d6e6
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6352479"
---
# <a name="create-a-channel-navigation-hierarchy"></a>Crear una jerarquía de navegación de canales


[!include [banner](includes/banner.md)]

En este tema se describe cómo crear una nueva jerarquía de navegación de canales en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

Una jerarquía de navegación de canales se usa para agrupar y organizar productos en categorías para que se puedan examinar productos en línea o en los puntos de venta (PDV).

## <a name="create-a-channel-navigation-hierarchy"></a>Crear una jerarquía de navegación de canales

Para crear una jerarquía de navegación de canales, siga estos pasos.

1. En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Productos y categorías \> Categorías de navegación de canales**.
1. En el panel de acciones, seleccione **Nueva**.
1. Escriba un nombre en el cuadro **Nombre**.
1. En el cuadro **Descripción**, escriba una descripción.
1. Seleccione **Crear**.
1. En el panel de acciones, seleccione **Nodo de categoría nueva** para crear un nodo raíz.
1. Escriba un nombre en el cuadro **Nombre**.
1. En el cuadro **Descripción**, escriba una descripción.
1. En el cuadro **Nombre descriptivo**, escriba un nombre descriptivo.
1. En el panel de acciones, seleccione **Guardar**.

La siguiente imagen muestra un ejemplo de nodo raíz.

![Ejemplo de nodo raíz.](media/create-channel-hierarchy-1.png)

## <a name="create-navigation-category-nodes"></a>Crear nodos de categoría de navegación

Para crear nodos de categoría de navegación adicionales para representar las categorías de productos en el canal, siga estos pasos.

1. En el panel de navegación, seleccione el nodo principal al que desea agregar una categoría.
1. En el Panel de acción, seleccione **Nueva categoría de nodo**.
1. Escriba un nombre en el cuadro **Nombre**.
1. En el cuadro **Descripción**, escriba una descripción.
1. En el cuadro **Nombre descriptivo**, escriba un nombre descriptivo.
1. En el cuadro **Orden de visualización**, escriba un orden de visualización (opcional).
1. En el panel de acciones, seleccione **Guardar**.

La siguiente imagen muestra un ejemplo de jerarquía de navegación de canales completada.

![Ejemplo de jerarquía de canales.](media/create-channel-hierarchy-2.png)

## <a name="add-products-to-category-nodes"></a>Agregar productos a nodos de categoría

Para agregar productos a nodos de categoría, siga estos pasos.

1. Seleccione un nodo de categoría.
1. En **Productos**, seleccione **Agregar**.
1. Utilice el número de producto o el nombre del producto para buscar los nuevos productos que desea agregar y, a continuación, seleccione **Aceptar**.
1. En el panel de acciones, seleccione **Guardar**.

> [!NOTE]
> Agregar productos a un nodo dentro de la jerarquía de navegación de canales no es suficiente para que los productos se muestren en un canal seleccionado, los productos también se deben clasificar en un canal. Para obtener más información sobre selecciones, consute [Administración de selecciones](assortments.md).

La imagen siguiente muestra un ejemplo de nodo con productos agregados.

![Productos agregados a nodos de categoría.](media/create-channel-hierarchy-3.png)

## <a name="add-product-attribute-groups-to-category-nodes"></a>Agregar grupos de atributos de producto a nodos de categoría

> [!NOTE]
> Los grupos de atributos deben crearse antes de que pueda agregarlos a un nodo dentro de la jerarquía de navegación de canales.

Para agregar un grupo de atributos de producto a un nodo de categoría, siga estos pasos.

1. Seleccione un nodo de categoría.
1. En **Grupo de atributos de producto**, seleccione **Agregar**.
1. Busque los grupos de atributos que desea agregar y, a continuación, seleccione **Aceptar**.
1. En el panel de acciones, seleccione **Guardar**.

La imagen siguiente muestra un ejemplo de nodo con grupos de atributos de producto agregados.

![Grupos de atributos de producto en un nodo.](media/create-channel-hierarchy-4.png)

## <a name="additional-resources"></a>Recursos adicionales

[Configurar selecciones](set-up-assortments.md)

[Administrar atributos y grupos de atributos](attribute-attributegroups-lifecycle.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
