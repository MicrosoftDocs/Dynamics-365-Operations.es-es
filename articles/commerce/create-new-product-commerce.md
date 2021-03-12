---
title: Crear un producto nuevo en Commerce
description: En este tema se describe cómo crear un producto nuevo en Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 3b578c1bdfe1c6b4bf66cc85cc09ed906fb812a8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965331"
---
# <a name="create-a-new-product-in-commerce"></a>Crear un producto nuevo en Commerce


[!include [banner](includes/banner.md)]

En este tema se describe cómo crear un producto nuevo en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Un producto se define principalmente con un número de producto, un nombre y una descripción. Sin embargo, otros datos también son necesarios para describir un producto o servicio:

## <a name="create-a-new-product"></a>Crear un nuevo producto

1. En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Productos y categorías \> Productos por categoría**.
1. En el panel de acciones, seleccione **Nueva**.
1. En la lista desplegable **Tipo de producto**, seleccione **Artículo** o **Servicio**.
1. En la lista desplegable **Subtipo de producto**, seleccione **Producto** (si el producto no tiene variantes) o **Producto maestro** (si el producto tiene variantes).
1. En el cuadro **Número de producto**, introduzca un número de producto si no aparece especificado.
1. En el cuadro **Nombre del producto**, introduzca un nombre de producto.
1. En el cuadro **Nombre de búsqueda**, escriba un nombre de búsqueda.
1. En la lista desplegable **Categoría comercial**, seleccione una categoría apropiada.
1. Si el producto es un kit, seleccione **Sí** para **Kit de productos**.
1. Si el subtipo de producto es producto maestro, establezca el valor de **Grupo de dimensiones del producto** para incluir las variantes ofrecidas. Entre las opciones se incluyen **Color**, **Tamaño**, **Estilo** y **Configuración**. Es posible que tenga que crear grupos de dimensiones de productos adicionales si es necesario.
1. En la lista desplegable **Tecnología de configuración**, seleccione una opción apropiada.
1. Seleccione **Aceptar**.

La imagen siguiente muestra un ejemplo de adición de producto.

![Crear un producto](media/create-new-product.png)

Una vez que se agrega un producto, se pueden establecer datos adicionales para él, como **Descripción del producto**, **Grupos de variantes**, **Grupos de dimensiones**, **Atributos del producto** y **Productos relacionados**.

La imagen siguiente muestra los detalles adicionales de un producto.

![Detalles de producto](media/create-new-product-2.png)

### <a name="create-product-variants"></a>Crear variantes de productos

Si el subtipo de producto es **Producto maestro**, deberán crearse variantes específicas. 

Para crear variantes de producto, siga estos pasos.

1. En el panel de acciones, seleccione **Variantes del producto**.
1. Si se seleccionaron grupos de variantes en el panel de acciones, seleccione **Sugerencias de variantes*.
1. Seleccione las variantes que desea ofrecer para el producto.
1. Seleccione **Crear**.

## <a name="release-a-product"></a>Liberar un producto

Para vender un producto, primero debe liberarse en una entidad jurídica.

1. En la página del producto, seleccione **Emitir productos**.

    ![Liberar producto](media/create-new-product-3.png)

1. Seleccione el producto que desea liberar y, a continuación, seleccione **Siguiente**.

    ![Elija el producto que desea liberar](media/create-new-product-4.png)

1. Seleccione el conjunto de variantes de producto que desea liberar y, a continuación, seleccione **Siguiente**.

    ![Elegir las variantes que se van a liberar](media/create-new-product-5.png)

1. Seleccione la entidad jurídica y, a continuación, seleccione **Siguiente**.

    ![Elegir entidad jurídica](media/create-new-product-6.png)

1. Seleccione **Fin**.

    ![Finalizar liberación de producto](media/create-new-product-7.png)

## <a name="configure-a-released-product"></a>Configurar un producto liberado

Una vez que se ha liberado un producto, requerirá una configuración adicional que incluya agregar un precio al producto.

1. En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Productos y categorías \> Productos liberados por categoría**.
1. Seleccione el nodo de categoría de productos para el producto liberado y después seleccione el producto en la lista de productos.
1. En el panel de acciones, seleccione **Editar**.
1. En la sección **Comprar** configure las propiedades requeridas, como **Unidad**, **Precio** y **Cantidad**.
1. En el panel de acciones, seleccione **Validar** para asegurarse de que no se notifiquen errores de campos que faltan.
1. En el panel de acciones, seleccione **Guardar**.

En la siguiente imagen se muestra un ejemplo de configuración para un producto liberado.

![Configurar un producto liberado](media/create-new-product-8.png)

## <a name="additional-resources"></a>Recursos adicionales

[Crear entidades jurídicas](channels-legal-entities.md)

[Crear un grupo de variantes](create-variant-group.md) 
