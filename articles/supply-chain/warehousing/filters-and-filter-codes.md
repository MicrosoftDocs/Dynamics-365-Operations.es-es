---
title: Configurar filtros de productos para transacciones de almacén
description: En este tema se describe cómo configurar filtros y filtros de producto para clasificar artículos de inventario de un almacén. También puede usar filtros para especificar qué clientes pueden pedir un artículo concreto y qué artículos se pueden comprar de un proveedor concreto.
author: Mirzaab
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSFilters,WHSFilterGroupTable,EcoResProductDetailsExtended,WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: c3648a2d9df300ecd0c26a12db8093babb3db48f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838259"
---
# <a name="configure-product-filters-for-warehouse-transactions"></a>Configurar filtros de productos para transacciones de almacén

[!include [banner](../includes/banner.md)]

En este tema se describe cómo configurar filtros y filtros de producto para clasificar artículos de inventario de un almacén. También puede usar filtros para especificar qué clientes pueden pedir un artículo concreto y qué artículos se pueden comprar de un proveedor concreto.

Además, puede configurar y usar los códigos de filtros de producto para organizar automáticamente los artículos de inventario en un almacén y combinar los artículos filtrados en los grupos de filtro. Los filtros se pueden utilizar para clasificar los artículos en categorías para los procesos de manipulación, compra y venta. Es posible que desee agrupar elementos o separarlos entre sí cuando la forma en que se manejan se basa en restricciones de peso o manipulación. También puede especificar a qué clientes o proveedores se puede comprar o vender un artículo.

## <a name="prerequisites"></a>Requisitos previos

La tabla siguiente muestra los requisitos previos que deben cumplirse antes de comenzar.

| Requisito previo | Instrucciones |
|---|---|
| Antes de comenzar a configurar productos en la página **Detalles del producto publicado**, debe activar el procesamiento de almacén para el grupo de dimensiones de almacenamiento del producto. | Vaya a **Gestión de información de producto \> Configuración \> Grupos de dimensiones y variantes \> Grupos de dimensiones de almacenamiento** y seleccione o cree un grupo de dimensiones de almacenamiento donde la opción **Utilizar procesos de gestión de almacenes** esté configurada en *Sí*. |
| Si va a utilizar filtros de cliente y / o filtros de proveedor, debe habilitar su uso en los parámetros de gestión de almacén. | Vaya a **Gestión de almacenes \> Configuración \> Parámetros de gestión de almacenes**. En la pestaña **Filtros de productos**, configure la opción **Habilitar filtros de clientes** y / o **Habilitar filtros de proveedores** en *Sí*. |

## <a name="set-up-product-filters"></a>Configurar filtros de producto

Los filtros de producto proporcionan hasta 10 características **Título del filtro**, que son valores de enumeración (enum). Estos valores de enumeración están disponibles para su selección cuando crea un filtro de producto. Los valores de enumeración *Codigo 1* mediante *Codigo 10* están definidos por el sistema y representan una característica o atributo específico de un artículo. Por ejemplo, *Codigo 1* puede representar elementos que tienen una clasificación de material peligroso. *Codigo 2* puede representar artículos que solo los proveedores pueden comprar. Luego, los filtros de producto definen el valor **Código de filtro** que está asociado con un valor **Título del filtro**.

1. Vaya a **Gestión de almacenes \> Configuración \> Filtros de productos \> Filtros de productos**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar un filtro de producto a la cuadrícula.
1. Seleccione un valor en el campo **Título de filtro**.
1. En el campo **Código de filtro**, escriba un valor.

    ![Configurar un filtro de producto](media/Product_Filters10.png "Configurar un filtro de producto")

1. En el campo **Descripción**, especifique un nombre para el código. Por ejemplo, *Codigo 2* podría representar a los proveedores. A continuación, puede crear un filtro de producto para un proveedor o grupo de proveedores específico. Para obtener más información, consulte la sección [Configurar códigos de filtro de proveedor](#vendor-product-filters) más adelante en este tema.

    ![Configuración de filtros de producto](media/Product_Filters.png "Configuración de filtros de producto")

## <a name="set-up-product-filter-groups"></a>Configuración de los grupos de filtro de producto

Puede usar grupos de filtros para agrupar códigos de filtro. Esta función es útil cuando un grupo se usa en una consulta en una directiva de ubicación y desea buscar el grupo en lugar de una serie de códigos. Cada grupo de filtros está asociado a un grupo de artículos.

> [!IMPORTANT]
> No todos los grupos de filtros de productos están disponibles para códigos de filtro superiores a *Codigo 4* (o sea, del *Código 5* al *Código 10*). Por ejemplo, para los productos lanzados, aunque se agregarán todos los códigos de filtro de producto, la agrupación de códigos de filtro no se actualizará. Este comportamiento puede actualizarse en versiones posteriores.

Para configurar grupos de filtros, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Configuración \> Filtros de productos \> Grupos de filtro de producto**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En los campos **Grupo 1** y **Grupo 2**, especifique los nombres que se usarán para clasificar artículos.
1. En la ficha desplegable **Detalles**, seleccione **Nueva** para agregar una línea.
1. En los campos **Fecha / hora de inicio** y **Fecha / hora de finalización**, ingrese las fechas de inicio y finalización para el grupo de filtro.
1. En el campo **Grupo de artículos**, seleccione el grupo de artículos al que se debe aplicar el filtro de productos.
1. En los campos de **Código 1** a **Código 10**, seleccione los códigos de filtro para incluir en el grupo, según sea necesario.

    ![Grupo de artículos](media/ProdFilterGroup.png "Grupo de artículos")

> [!NOTE]
> Si recibe un mensaje de error al cerrar la página, es posible que falte una configuración de código. En la página **Grupos de artículos**, puede hacer que los códigos sean obligatorios para un grupo de artículos seleccionando las casillas de verificación **Asignar filtro Código 1 para el grupo de artículos**, **Asignar filtro Código 2 para el grupo de artículos**, y así sucesivamente.

## <a name="set-up-filter-codes-on-item-groups"></a>Configurar códigos de filtro en grupos de artículos

Al configurar códigos de filtro en un grupo de artículos, puede hacer que los códigos sean necesarios para los productos que están vinculados a ese grupo de artículos.

Para configurar códigos de filtro en grupos de artículos, siga estos pasos.

1. Vaya a **Gestión del inventario \> Configurar \> Inventario \> Grupos de artículos**.
1. En el Panel de acciones, haga clic en **Nuevo** para crear un grupo de artículos.
1. En el campo **Descripción de artículo**, introduzca un nombre.
1. En el campo **Nombre**, escriba una descripción.
1. En la ficha desplegable **Almacén**, en la sección **Filtro requerido**, active las casillas de verificación para los códigos de filtro que se deban especificar para productos asociados al grupo de artículos.

    Para actualizar un producto lanzado, abra su página **Detalles del producto publicado** y, a continuación, en el panel de Acción, seleccione **Editar**. Los filtros que están asociados con los códigos están disponibles en la ficha desplegable **Almacén**.

    ![Grupos de artículos](media/ItemGroup10.png "Grupos de artículos")

1. En la sección **Filtro de grupo de artículos**, seleccione las casillas de verificación de los filtros que deben coincidir para que el grupo de filtros sea el grupo de filtros predeterminado para un elemento.

    Por ejemplo, si se seleccionan las casillas de verificación **Usar filtro Código 1** y **Usar filtro Código 2**, los códigos de filtro 1 y 2 del artículo deben coincidir con la configuración del grupo de filtros para el grupo de artículos con el fin de que el grupo de filtros se pueda seleccionar. Cuando crea un nuevo elemento, el grupo de filtro seleccionado será el grupo de filtro predeterminado en los campos **Grupo 1** y **Grupo 2** en la ficha desplegable **Almacén** de la página **Detalles del producto publicado**.

> [!IMPORTANT]
> Los códigos de filtro de productos están habilitados solo para artículos que utilizan la gestión avanzada de almacenes.

## <a name="specify-filter-codes-for-released-products"></a>Especificar códigos de filtro de productos emitidos

Siga estos pasos para especificar códigos de filtro de productos emitidos. Por ejemplo, puede usar códigos de filtro para agrupar productos peligrosos que compran proveedores específicos.

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. En el Panel de acciones, seleccione **Nuevo** para crear un producto.
1. En el cuadro de diálogo **Nuevo producto lanzado**, introduzca los datos que se requieren para crear la base de un nuevo producto, y luego seleccione **Aceptar**.

    Los códigos de filtro de productos no están habilitados a menos que el grupo de artículos adjunto al producto se haya configurado para códigos de filtro.

    Para obtener más información, consulte [Crear un nuevo producto](../pim/tasks/create-new-product.md).

1. En la ficha desplegable **Almacén**, en la sección **Códigos de filtro de productos**, seleccione los códigos de filtro para los campos de **Código 1** a **Código 10**, según sea necesario, para especificar códigos de filtro para el producto.

## <a name="set-up-generally-available-items"></a>Configurar artículos disponibles en general

Puede hacer que determinados artículos de inventario estén disponibles solo para proveedores, o bien tanto para clientes como para proveedores.

> [!NOTE]
> Los filtros de clientes y proveedores no se aplican a ningún artículo que esté configurado como disponible a nivel general.

Para configurar artículos disponibles a nivel general, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Configuración \> Filtros de productos \> Productos disponibles a nivel general**.
1. En el Panel de acciones, seleccione **Nuevo** para crear un registro.
1. En el campo **Cliente o vendedor**, seleccione *Cliente*, *Vendedor* o *Todos* para que los artículos estén disponibles para clientes, proveedores o ambos.
1. En el campo **Fecha / hora de inicio**, introduzca la fecha y hora en que el artículo estará disponible.
1. En el campo **Grupo de artículos**, seleccione un grupo de artículos.
1. En los campos de **Código 1** a **Código 10**, seleccione los códigos de filtro para limitar los artículos que están disponibles en general.

    Al seleccionar un grupo de artículos, se establece ese grupo de artículos como disponible en general. Al seleccionar códigos de filtro en estos campos, se limitan los elementos que están disponibles.

## <a name="set-up-customer-product-filters"></a>Configurar filtros de productos del cliente

Puede usar este proceso opcional para especificar artículos que deben estar disponibles para un cliente además de los artículos que están disponibles gracias a la configuración de filtro en la página **Artículos disponibles a nivel general**. Puede configurar varios filtros para un solo cliente.

Para configurar códigos de filtro de cliente, siga estos pasos.

1. Vaya a **Ventas y marketing \> Clientes \> Todos los clientes**.
1. Seleccione un cliente.
1. En el panel Acciones, en la pestaña **Cliente**, en el grupo **Configurar**, seleccione **Filtros de producto**.
1. En la página **Códigos de filtro de producto**, en el panel de Acciones, seleccione **Nuevo**.
1. En los campos **Fecha / hora de inicio** y **Fecha / hora de finalización**, ingrese las fechas de inicio y finalización para el grupo del artículo seleccionado.
1. En el campo **Grupo de artículos**, seleccione un grupo de artículos.
1. En los campos de **Código 1** a **Código 10**, seleccione los códigos de filtro que se utilizarán como criterio para limitar los artículos que están disponibles para los clientes en el grupo de artículos seleccionado. Debe realizar una selección para cada código de filtro que esté configurado para el grupo de artículos.

## <a name="set-up-vendor-product-filters"></a><a name="vendor-product-filters"></a>Configurar filtros de productos de proveedor

Puede usar este proceso opcional para especificar artículos que deben estar disponibles para un proveedor además de los artículos que están disponibles gracias a la configuración de filtro en la página **Artículos disponibles a nivel general**. Puede configurar varios filtros para un solo proveedor.

Para configurar códigos de filtro de proveedor, siga estos pasos.

1. Vaya a **Adquisición y abastecimiento \> Proveedores \> Todos los proveedores**.
1. Seleccione un proveedor.
1. En el panel Acciones, en la pestaña **Proveedor**, en el grupo **Configurar**, seleccione **Filtros de producto**.
1. En la página **Códigos de filtro**, en el panel de Acciones, seleccione **Nuevo**.
1. En los campos **Fecha / hora de inicio** y **Fecha / hora de finalización**, ingrese las fechas de inicio y finalización para el grupo del artículo seleccionado.
1. En el campo **Grupo de artículos**, seleccione un grupo de artículos.
1. En los campos de **Código 1** a **Código 10**, seleccione los códigos de filtro que se utilizarán como criterio para limitar los artículos que están disponibles para los proveedores en el grupo de artículos seleccionado. Debe realizar una selección para cada código de filtro que esté configurado para el grupo de artículos.

> [!NOTE]
> La configuración de los filtros de productos del proveedor se aplica a los productos lanzados donde los procesos de gestión del almacén están habilitados para el grupo de dimensiones de almacenamiento asociado. Los códigos de filtro se utilizan para determinar si el sistema permitirá a los usuarios comprar un artículo determinado de un proveedor determinado cuando creen líneas de pedidos de compra. Microsoft Dynamics 365 Supply Chain Management tiene dos métodos para gestionar la aprobación del proveedor. Si existen uno o más productos liberados donde el campo **Método de verificación de proveedor aprobado** está configurado en *Solo advertencia* o *No permitido*, ambos métodos de aprobación de proveedores podrían habilitarse para esos artículos. Esta situación puede causar problemas cuando los usuarios crean líneas de pedidos de compra.

## <a name="see-also"></a>Consulte también

[Para obtener más información, consulte la publicación de blog WMS-Warehouse Filter Codes](http://blog.dynamics-for-operations.com/2017/09/26/wms-warehouse-filter-codes/)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]