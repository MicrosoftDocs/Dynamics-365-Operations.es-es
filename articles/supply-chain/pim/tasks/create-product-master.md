---
title: Crear un producto maestro
description: Cree un producto maestro para las variantes predefinidas.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5e76c367d4aa6c08332371374a26dd6fdbbdb4eb
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7577345"
---
# <a name="create-a-product-master"></a>Crear un producto maestro

[!include [banner](../../includes/banner.md)]

Cree un producto maestro para las variantes predefinidas. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Este procedimiento se ha pensado para el diseñador de producto.


## <a name="create-a-new-product-master"></a>Crear un nuevo producto maestro
1. Vaya a **Panel de exploración > Módulos > Gestión de información de productos > Productos > Productos maestros**.
2. Haga clic en **Nuevo**.
3. En el campo **Número de producto**, escriba un valor. El número debe ser único. Se puede especificar una secuencia numérica para el campo **Número de producto**. En este caso, el usuario no tiene que especificar un valor.
4. En el campo **Nombre de producto**, escriba un valor. Escriba un nombre del producto que sea descriptivo. El valor predeterminado es el nombre de búsqueda, pero esto lo puede cambiar el usuario.
5. En el campo **Grupo de dimensiones de producto**, haga clic en el botón desplegable para abrir la búsqueda. El grupo de dimensiones del producto determina cuál de las cuatro dimensiones del producto se pueden usar para crear variantes del producto. Este ejemplo usa un grupo con tamaño y color.
6. En la lista, busque y seleccione el registro deseado.
7. En la lista, haga clic en el vínculo de la fila seleccionada. La **tecnología de configuración** predeterminada es Variante predefinida. Es lo que se usará para este ejemplo.
8. Haga clic en **Aceptar**.

## <a name="select-product-dimension-groups"></a>Selección de grupos de dimensiones de producto
1. En el campo **Grupo de colores**, haga clic en el botón desplegable para abrir la búsqueda.
2. En la lista, busque y seleccione el registro deseado.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. En el campo **Grupo de tamaños**, haga clic en el botón desplegable para abrir la búsqueda.
5. En la lista, busque y seleccione el registro deseado.
6. En la lista, haga clic en el vínculo de la fila seleccionada.

## <a name="add-dimension-groups"></a>Agregar grupos de dimensiones
1. En el **Panel de acciones**, haga clic en **Producto**.
2. Haga clic en **Grupos de dimensiones** para abrir el cuadro de diálogo.
3. En el campo **Grupo de dimensiones de almacenamiento**, haga clic en el botón de lista desplegable para abrir la búsqueda. Las dimensiones de almacenamiento ayudan a controlar el modo en que los artículos se almacenan y se toman del inventario. Por ejemplo, una dimensión de almacenamiento puede incluir el sitio y el almacén.
4. En la lista, busque y seleccione el registro deseado.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
6. En el campo **Grupo de dimensiones de seguimiento**, haga clic en el botón de lista desplegable para abrir la búsqueda. El grupo de dimensiones de seguimiento determina qué dimensiones de seguimiento puede agregar a un producto. Por ejemplo, el número de lote y el número de serie se utilizan para hacer un seguimiento de los artículos de inventario.
7. En la lista, busque y seleccione el registro deseado.
8. En la lista, haga clic en el vínculo de la fila seleccionada.
9. Haga clic en **Aceptar**.
10. Haga clic en **Guardar**.
11. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]