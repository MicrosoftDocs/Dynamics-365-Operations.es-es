---
title: Conversión de unidad de medida por variante del producto
description: Este artículo explica cómo configurar las conversiones de unidades de medida para variantes de producto. Incluye un ejemplo de configuración.
author: t-benebo
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: UnitOfMeasureConversion
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: a605e510ac8faa1f92e105c9fcc30222ef78e05e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869644"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a>Conversión de unidad de medida por variante del producto

[!include [banner](../includes/banner.md)]

Este artículo explica cómo configurar las conversiones de unidades de medida para diversas variantes de producto.

En lugar de crear varios productos individuales que deberán mantenerse, puede usar variantes del producto para crear variaciones de un único producto. Por ejemplo, una variante del producto podría ser una camiseta de un tamaño y color determinados.

Anteriormente, las conversiones de unidades solo se podían configurar en el producto maestro. Por lo tanto, todas las variantes de producto tenían las mismas reglas de conversión de unidades. Sin embargo, cuando la función *Conversiones de unidades de medida para variantes de producto* está activada, si sus camisetas se venden en cajas y la cantidad de camisetas que se pueden empaquetar en una caja depende del tamaño de las camisetas, ahora puede configurar conversiones de unidades entre las diferentes tamaños de camisetas y las cajas que se utilizan para el empaquetado.

## <a name="turn-on-the-feature-in-your-system"></a>Activar la función en el sistema

Si ya no ve esta función en su sistema, vaya a [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) y active la función *Conversiones de unidades de medida para variantes de producto*.

## <a name="set-up-a-product-for-unit-conversion-per-variant"></a>Configurar un producto para la conversión de unidades por variante

Las variantes de producto solo se pueden crear solo para productos que sean productos maestro. Para obtener más información, consulte [Crear un producto maestro](tasks/create-product-master.md). La función *Conversiones de unidades de medida para variantes de producto* no está disponible para productos que están configurados para procesos de captura de peso.

Para configurar un producto maestro para admitir la conversión de unidades por variante, siga estos pasos.

1. Vaya a **Gestión de información de productos \> Productos \> Productos maestros**.
1. Cree o abra un producto maestro para ir a su página **Detalles de producto**.
1. Seleccione la opción **Habilitar conversiones de unidades de medida** en *Sí*.
1. En el panel Acciones, en la pestaña **Producto** del grupo **Configurar**, haga clic en **Conversiones de unidades**.
1. Se abrirá la página **Conversiones de unidades**. Seleccione una de las pestañas siguientes:

    - **Conversiones intraclase**: seleccione esta pestaña para convertir entre unidades que pertenecen a la misma clase de unidades.
    - **Conversiones interclase**: seleccione esta pestaña para convertir entre unidades que pertenecen a diferentes clases de unidades.

1. Para agregar una unidad de conversión nueva, haga clic en **Nueva**.
1. Seleccione el campo **Crear conversión para** en uno de los siguientes valores:

    - **Producto**: si selecciona este valor, puede configurar una conversión de unidades para el producto maestro. Esa conversión de unidades se utilizará como alternativa para todas las variantes de producto para las que no esté definida ninguna conversión de unidades.
    - **Variante del producto**: si selecciona este valor, puede configurar una conversión de unidades para una variante del producto específica. Utilicer el campo **Variante del producto** para seleccionar la variante.

    ![Agregar una nueva conversión de unidades.](media/uom-new-conversion.png "Agregar una nueva conversión de unidades")

1. Use los otros campos que se proporcionan para configurar su conversión de unidades.
1. Seleccione **Aceptar** para guardar la nueva conversión de unidades.

> [!TIP]
> Puede abrir la página **Conversiones de unidades** para un producto o una variante de producto desde cualquiera de las siguientes páginas:
> 
> - Detalles de producto
> - Detalles de productos despachados
> - Variantes de Productos despachados

## <a name="example-scenario"></a>Supuesto de ejemplo

En este escenario, una empresa vende camisetas de tamaños pequeño, mediano, grande y extragrande. La camiseta se define como un producto, y los distintos tamaños se definen como variantes de ese producto. Las camisas se empaquetan en cajas. Para los tamaños pequeño, mediano y grande, puede haber cinco camisetas en cada caja. Sin embargo, para el tamaño extragrande, hay espacio para solo cuatro camisetas en cada caja.

La empresa desea realizar un seguimiento de las distintas variantes en la unidad *Piezas*, pero las está vendiendo en la unidad *Cajas*. Para los tamaños pequeño, mediano y grande, la conversión entre la unidad de inventario y la unidad de ventas es de 1 caja = 5 piezas. Para tamaño extragrande, la conversión es 1 caja = 4 piezas.

1. Desde la página **Detalles de producto despachado** del producto **Camiseta**, abra la página la página **Conversión de unidades**.
1. En la página **Conversión de unidades**, configure la siguiente conversión de unidades para la variante del producto despachada **Extragrande**.

    | Campo                 | Configuración                 |
    |-----------------------|-------------------------|
    | Crear conversión para | Variante del producto         |
    | Variante del producto       | Camiseta : : extragrande : : |
    | Desde unidad             | Cajas                   |
    | Factor                | 4                       |
    | Hasta unidad               | Piezas                  |

1. Dado que las variantes del producto **Pequeña**, **Mediana** y **Grande** tienen todas la misma conversión de unidades entre las unidades *Caja* y *Piezas*, puede definir la siguiente conversión de unidades para ellas en el producto maestro.

    | Campo                 | Configuración |
    |-----------------------|---------|
    | Crear conversión para | Producto |
    | Producto               | Camiseta |
    | Desde unidad             | Cajas   |
    | Factor                | 5       |
    | Hasta unidad               | Piezas  |

## <a name="using-excel-to-update-the-unit-conversions"></a>Uso de Excel para actualizar las conversiones de unidades

Si un producto tiene muchas variantes de producto que tienen conversiones de unidades diferentes, es una buena idea exportar las conversiones de unidades al libro de trabajo Microsoft Excel, actualizarlas y luego volver a a publicarlas en Dynamics 365 Supply Chain Management.

Para exportar conversiones de unidades a Excel, en la página **Conversiones de unidades**, en el panel Acciones, seleccione **Abrir en Microsoft Office**.

## <a name="additional-resources"></a>Recursos adicionales

[Gestionar las unidades de medida](tasks/manage-unit-measure.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]