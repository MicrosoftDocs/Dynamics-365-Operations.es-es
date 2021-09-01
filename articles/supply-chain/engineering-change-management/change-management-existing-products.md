---
title: Habilitar la administración de cambios en productos existentes
description: Este tema explica cómo puede habilitar la gestión de cambios para productos existentes. También describe casos en los que su capacidad para habilitar la gestión de cambios es limitada.
author: t-benebo
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-05-02
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 2fd3d2e4f4c3e53913bd811728b0950c63b38bc5afe6fe5282b4cfb05f414619
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6744187"
---
# <a name="enable-change-management-on-existing-products"></a>Habilitar la administración de cambios en productos existentes

[!include [banner](../../includes/banner.md)]

Este tema explica cómo puede habilitar la gestión de cambios para productos existentes. También describe casos en los que su capacidad para habilitar la gestión de cambios es limitada.

Cuando habilita la administración de cambios para un producto existente, puede crear versiones de ese producto y rastrear los cambios que se le realizan a lo largo de su vida. Por lo tanto, puede realizar un seguimiento de esos cambios mediante el uso de órdenes de cambio. Para habilitar la gestión de cambios, debe convertir los productos relevantes a *artículos de ingeniería* (también denominados productos de ingeniería). Los productos de ingeniería son productos que se versionan y gestionan mediante la gestión de cambios. Se proporciona un asistente para guiarlo a través del proceso de conversión.

## <a name="turn-on-the-feature-in-your-system"></a>Activar la función en el sistema

Para usar esta funcionalidad, debe completar las tareas siguientes:

1. Habilite la función de administración de cambios de ingeniería y su clave de configuración como se describe en [Descripción general de la gestión de cambios de ingeniería](product-engineering-overview.md).
1. Active la función *Habilite la gestión de cambios en productos existentes* en la gestión de funciones. Para más información, consulte [Resumen de administración de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="restrictions-and-limitations"></a>Restricciones y limitaciones

No todos los tipos de productos se pueden convertir a todos los demás tipos. Se aplican las siguientes restricciones y limitaciones:

- Cuando convierte un producto en un producto de ingeniería, sigue siendo un *producto*. No se convierte en un *producto maestro*.
- Cuando convierte un producto maestro que tiene un conjunto específico de dimensiones, esas dimensiones se mantienen después del cambio. Por ejemplo, si convierte un producto maestro que tiene la dimensión de tamaño, mantendrá la dimensión de tamaño.

Por lo tanto, si tiene un producto distinto, puede cambiarlo solo a un producto de ingeniería que no rastrea la dimensión del producto en las transacciones (es decir, la dimensión de la versión no se usa). Vea las secciones restantes de este tema para obtener más información sobre estos problemas.

## <a name="prepare-for-conversion-by-creating-all-required-engineering-product-categories"></a>Prepárese para la conversión creando todas las categorías de productos de ingeniería requeridas

Una *categoría de producto de ingeniería* debe asignarse a cada producto de ingeniería. Hará esta tarea cuando ejecute el asistente **Convertir en producto de ingeniería**. Deben existir categorías de productos de ingeniería para todos los productos estándar relevantes *antes de* convertir esos productos.

La categoría de productos de ingeniería proporciona una base para crear un producto de ingeniería y establece un conjunto de valores y políticas predeterminados. La categoría de producto de ingeniería debe coincidir con el producto a la que se asigna. Por ejemplo, el tipo de producto y el grupo de dimensiones deben coincidir tanto con el producto como con su categoría de producto de ingeniería. Para más información, vea [Versiones de ingeniería y categorías de productos de ingeniería](engineering-versions-product-category.md).

> [!IMPORTANT]
> El asistente **Convertir en producto de ingeniería** puede convertir productos solo en productos de ingeniería en los que no se realiza un seguimiento de la versión en las transacciones. Por lo tanto, la opción **Seguimiento de la versión en transacciones** debe establecerse en *No* para categorías de productos de ingeniería que crea para convertir productos existentes.

Para obtener más información sobre cómo crear categorías de productos de ingeniería, consulte [Versiones de ingeniería y categorías de productos de ingeniería](engineering-versions-product-category.md).

## <a name="run-the-convert-to-engineering-product-wizard"></a>Ejecute el asistente Convertir en producto de ingeniería

El asistente **Convertir en producto de ingeniería** le ayuda a convertir uno o más productos existentes en productos de ingeniería. Convierte los productos en productos de ingeniería (productos versionados) donde la versión no se rastrea en las transacciones (es decir, no se usa la dimensión de la versión). Una vez completada la conversión, puede administrar los productos mediante la administración de cambios de ingeniería.

La conversión es permanente. Por lo tanto, no podrá revertirlo más tarde. 

Cada producto de ingeniería convertido seguirá lanzándose en las mismas empresas en las que se lanzó el producto original. Sin embargo, la lista de materiales de ingeniería (BOM) y las rutas no se entregarán automáticamente a esas empresas.

Siga estos pasos para ejecutar el asistente **Convertir en producto de ingeniería** y convertir un producto en un producto de ingeniería.

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. En la cuadrícula, seleccione la casilla para cada producto que desee convertir.
1. En el panel de acciones, en la pestaña **Ingeniero**, en el grupo **Gestión de cambios de ingeniería**, seleccione **Convertir a producto de ingeniería** para abrir el asistente.
1. La primera página del asistente es la página de **Bienvenida**. Si aún no está familiarizado con el proceso de conversión, lea atentamente la información de esta página. Cuando esté listo para continuar, seleccione **Siguiente**.
1. La página **Seleccione los detalles de los productos que se convertirán** muestra cada producto que seleccionó antes de abrir el asistente. Inspeccione la lista. Utilice los botones **Nuevo** y **Eliminar** de la barra de herramientas para agregar y eliminar productos según sea necesario.
1. Utilice los siguientes campos en la parte superior de la cuadrícula para asignar valores predeterminados a cada producto que se enumera. (Podrá cambiar estos valores para productos individuales después de que se complete la conversión). Los valores predeterminados no se asignarán a productos donde ya se haya asignado un valor relevante.

    - **Categoría de ingeniería predeterminada** - Seleccione una categoría de producto de ingeniería inicial para asignar a cada producto listado. La categoría que seleccione se aplicará solo a los productos que sean compatibles con ella.
    - **Versión predeterminada** - Ingrese la versión inicial del producto para asignar a cada producto listado. Cada producto de ingeniería tiene al menos una versión de ingeniería.
    - **Estado del ciclo de vida predeterminado** - Seleccione el estado del ciclo de vida del producto inicial para asignarlo a cada producto de la lista.
    - **La lista de materiales actual será parte del producto de ingeniería** - Seleccione esta casilla de verificación si la lista de materiales actual para cada producto listado debe usarse como una lista de materiales para el producto de ingeniería.

    Para obtener más información sobre la configuración de producto, vea el paso siguiente.

1. Revise cada producto que se enumera en la cuadrícula y evalúe qué tan bien se aplican los valores predeterminados que asignó. Para cada fila, revise la siguiente información y configure los campos relevantes:

    - **Número de producto** - El número del producto.
    - **Nombre de producto** – El nombre del producto.
    - **Categoría de ingeniería** - Seleccione la categoría de producto de ingeniería a la que debe pertenecer el producto después de su conversión. Ya debe existir una categoría apropiada para cada producto, como se explicó en la sección anterior de este tema. Debe asignar una categoría a cada producto.
    - **Versión** - Ingrese la versión inicial del producto para asignar al producto después de convertirlo. Por ejemplo, puede seleccionar un número que se ajuste a la secuencia numérica que ya usa su categoría. Cada versión de ingeniería almacena los datos relevantes para la ingeniería que son específicos de esa versión. Para más información, vea [Versiones de ingeniería y categorías de productos de ingeniería](engineering-versions-product-category.md).
    - **Estado del ciclo de vida del producto** - Seleccione el estado del ciclo de vida del producto en el que debe estar el producto después de su conversión. El estado del ciclo de vida del producto le permite controlar qué transacciones están permitidas para una versión de ingeniería determinada. Para más información, vea [Estados y transacciones del ciclo de vida del producto](product-lifecycle-state-transactions.md).
    - **Tiene lista de materiales** - Una casilla de verificación seleccionada indica que el producto tiene una lista de materiales. La configuración de esta casilla de verificación puede ayudarlo a decidir cómo configurar la casilla **La lista de materiales actual será parte del producto de ingeniería**.
    - **La lista de materiales actual será parte del producto de ingeniería** - Seleccione esta casilla de verificación si la lista de materiales actual del producto debe usarse como una lista de materiales para el producto de ingeniería. Esa lista de materiales será administrada luego por la administración de cambios de ingeniería. Si el producto no tiene una lista de materiales, o si prefiere crear manualmente una lista de materiales para el producto convertido más adelante, desactive esta casilla de verificación.
    - **Tiene errores** - Una casilla de verificación seleccionada indica que la configuración del producto tiene uno o más errores. Por ejemplo, es posible que el tipo de producto o el grupo de dimensiones no coincidan en la categoría. Los productos que tengan errores se omitirán y no se convertirán.

1. Cuando haya terminado, seleccione **Validar** en la barra de herramientas para validar la configuración del producto. Para cada fila, la casilla **Tiene errores** se actualizará para indicar el estado del producto. Ajuste los valores hasta que la configuración de cada producto esté libre de errores.
1. Cuando todos los productos estén configurados correctamente, seleccione **Siguiente** para continuar.
1. La página **Confirmar selección** muestra la cantidad de productos que no tienen errores en su configuración y, por lo tanto, están listos para la conversión. También muestra la cantidad de productos que se omitirán debido a errores. Para ejecutar la conversión como un trabajo por lotes, configure la opción **Ejecutar en lote** como *Si*.
1. Seleccione **Finalizar** para aplicar su configuración y comenzar a convertir los productos en productos de ingeniería.

> [!NOTE]
> Si su sistema está configurado para aceptar productos manualmente antes de su lanzamiento, debe aceptar cada producto convertido utilizando la página **Lanzamientos de productos abiertos** en las empresas correspondientes. Para más información, vea [Revise y acepte el producto antes de lanzarlo en la empresa local](engineering-scenarios.md#accept).
