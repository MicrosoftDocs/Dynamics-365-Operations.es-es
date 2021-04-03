---
title: Propietarios del producto
description: Este tema proporciona información acerca de los propietarios de productos. Un propietario de producto es un grupo de usuarios que son responsables de productos específicos. Solo los miembros del grupo pueden lanzar esos productos. El propietario del producto también se puede utilizar en el flujo de trabajo de aprobación.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgProductOwner
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: a1c3bc6f77fed83cfbbd502cdd469baa491fd81f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5266136"
---
# <a name="product-owners"></a>Propietarios del producto

[!include [banner](../includes/banner.md)]

El propietario del producto es un grupo de usuarios que son responsables de productos específicos. Cuando un grupo de propietarios de productos se asigna a un producto, solo los miembros de ese grupo pueden lanzar el producto. El propietario del producto también se puede utilizar en la gestión de cambios de ingteniería.

Los propietarios de productos son entornos globales. Por tanto, están disponibles para todas las personas jurídicas.

## <a name="create-a-product-owner-group"></a>Crear un grupo de propietarios de productos

Para crear un grupo de propietarios de productos y agregarle miembros, siga estos pasos.

1. Vaya a **Gestión de cambios de ingeniería \> Preparar \> Propietarios del producto**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el campo **Propietario del producto**, especifique un nombre descriptivo para el grupo de productos.
4. En el campo **Nombre**, especifique una descripción del grupo.
5. Sobre la ficha desplegable **Miembros**, agregue los trabajadores que deberían ser miembros del grupo.

## <a name="assign-a-product-owner-to-a-product"></a>Asignar un propietario de producto a un producto

Para asignar un propietario de producto a un producto, siga estos pasos:

1. Abra la página **Detalles de producto** para el producto o producto maestro relevante.
1. En la ficha desplegable **General**, establezca el campo **Dueño del producto** en el nombre del grupo de propietarios de producto relevante.

Mientras que un propietario de producto está asignado a un producto, solo los miembros del grupo de propietarios de producto pueden editar la configuración **Dueño del producto**.

El propietario del producto también es visible en la página **Productos lanzados**.

## <a name="product-owners-and-product-releases"></a>Propietarios de productos y lanzamientos de productos

Solo los usuarios del grupo de propietarios de productos de un producto pueden lanzar ese producto. Sin embargo, hay una excepción cuando el producto es un artículo secundario y su padre es liberado por el propietario del padre. En otras palabras, si el producto es parte de la lista de materiales de otro producto, el sistema no verifica al propietario del producto de cada artículo en la lista de materiales. Solo verifica el propietario del producto del artículo principal.

Por ejemplo, el producto X se asigna al grupo de propietarios de productos *Armarios de diseño*. El producto X también forma parte de la lista de materiales del producto Y, que se asigna al grupo de propietarios de productos *Ponentes de diseño*. Si un usuario del grupo propietario del producto *Ponentes de diseño* lanza el producto y su lista de materiales, el producto X se lanzará junto con el producto Y.

## <a name="product-owners-and-approvals"></a>Propietarios y aprobaciones de productos

Dado que los propietarios de productos saben si los cambios de ingeniería específicos beneficiarán a sus productos, a menudo tiene sentido incluirlos como parte del proceso de aprobación en la gestión de cambios de ingeniería. Puede implementar este enfoque configurando a los propietarios del producto como proveedores participantes en los flujos de trabajo que se utilizan para la gestión de cambios de ingeniería. Luego, el sistema asignará tareas de aprobación en los flujos de trabajo, en función de los productos que se encuentran en las solicitudes de cambio de ingeniería y las órdenes de cambio de ingeniería. Para más información, ver [Gestionar cambios en productos de ingeniería](engineering-change-management.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]