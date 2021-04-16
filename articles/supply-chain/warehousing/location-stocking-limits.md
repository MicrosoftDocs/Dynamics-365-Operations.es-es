---
title: Límites de existencias de la ubicación
description: Este tema describe la funcionalidad para los límites de existencias de ubicaciones.
author: perlynne
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationLimit
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-11-11
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: b9fb3c35f2f2e0fd7c0e3afe132efb4c51f163a9
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831275"
---
# <a name="location-stocking-limits"></a>Límites de existencias de la ubicación

[!include [banner](../includes/banner.md)]

Puede usar la página **Límites de almacenamiento de ubicación** (**Gestión de almacenes \> Preparar \> Almacén \> Límites de almacenamiento de ubicación**) para controlar la capacidad de carga en las ubicaciones de los almacenes sin tener que utilizar los procesos más avanzados para cálculos volumétricos de productos físicos.

El propósito de los límites de existencias de una ubicación es evaluar la cantidad máxima que puede contener una ubicación. Puede configurar la función en cualquiera de los tres niveles, cada uno de los cuales tiene su propia pestaña en la página **Límites de almacenamiento de ubicación**:

- Productos
- Variantes del producto
- Tipos de contenedor

Para cada nivel, puede definir diferentes valores de campo. A continuación, el sistema evaluará la capacidad de una ubicación específica, en función de los valores **Cantidad** y **Unidad** para cada fila. Primero seleccionará el registro coincidente más detallado. Por ejemplo, una fila que tiene un valor en el campo **ID de perfil de ubicación** se evaluará antes de una fila que tenga un valor solo en el campo **Almacén**. También se evaluará la capacidad restante, en función del valor **Cantidad** para el registro de límite de existencias de la ubicación que se utiliza.

En la sección **Productos** de la página, puede definir los siguientes valores de campo para la búsqueda de límites de almacenamiento de ubicación:

- Almacén
- Id. de perfil de ubicación
- Ubicación
- Id. de categoría de tamaño de paquete
- Número de artículo
- Unidad

> [!NOTE]
> No tiene que definir un valor de **Unidad** para cada registro de límite de existencias de ubicación. Los cálculos de capacidad de ubicación se basarán en las cantidades de unidades de inventario. Si no se define una conversión de unidad para un valor que se utiliza, se omitirá el registro de límite de existencias de la ubicación, como si otro valor de **Número de artículo** está definido para ello.

## <a name="example--purchase-order-receiving"></a>Ejemplo: recepción de pedido de compra

Este ejemplo se basa en un conjunto de datos de demostración limpio de *USMF*, donde se establecen los siguientes valores en la pestaña **Variantes de producto** de la página **Límites de almacenamiento de ubicación**.

| Almacén | Id. de perfil de ubicación | Número de artículo | Talla | Cantidad | Unidad |
|-----------|---------------------|-------------|------|----------|------|
| 24        | FLOOR               | D0013       | L    | 300      | c/u   |
| 24        | FLOOR               | D0013       | L    | 240      | c/u   |
| 24        | FLOOR               | D0013       | S    | 360      | c/u   |

Se configuran diferentes variantes de producto de unidad de medida para los productos. Estas variantes están alineadas con los límites de almacenamiento de ubicación para tres paletas (PL):

- **Talla M:** 1 PL = 100 cada uno (Ea)
- **Talla L:** 1 PL = 80 Ea
- **Talla S:** 1 PL = 120 Ea

Por lo tanto, cada lugar donde el valor de **ID de perfil de ubicación** está establecido en *FLOOR* puede llevar *3* *PL* del número de artículo *D0013*.

### <a name="prepare-for-the-example"></a>Prepapar el ejemplo

En este ejemplo, ejecutará un flujo de recepción de órdenes de compra para dos líneas. Sin embargo, primero debe actualizar los datos de demostración de la siguiente manera para asegurarse de que las ubicaciones permitan el transporte de artículos mixtos, solo se utilizan las ubicaciones vacías *FL-002* a *FL-004* y no hay trabajo entrante abierto.

1. Para la ubicación *FL-001*, cambie el valor del campo **Perfil de ubicación** de *FLOOR* a *FLOOR-05*.
1. Para el perfil de ubicación *FLOOR*, configure la opción **Permitir elementos mixtos** en *Sí*.
1. Cree un pedido de compra con las dos líneas siguientes.

    | Almacén | Número de artículo | Talla | Cantidad | Unidad |
    |-----------|-------------|------|----------|------|
    | 24        | D0013       | S    | 4        | PL   |
    | 24        | D0013       | L    | 4        | PL   |

### <a name="process-the-example"></a>Procesar el ejemplo

Primero recibirá una cantidad de *4* de la unidad *PL* en tamaño *S* y revisará las ubicaciones de las líneas de colocación para el trabajo que se crea. Después recibirá una cantidad de *4* de la unidad *PL* en tamaño *L* y revisará las ubicaciones de las líneas de colocación para el trabajo que se crea.

1. En la aplicación móvil Warehouse Management, inicie sesión utilizando *24* como el Id. de usuario y *1* como la contraseña.
1. Seleccione **Entrante** \> **Recepción de compra**.
1. Reciba *4* *PL* del número de artículo *D0013* en tamaño *S*.
1. Revise el trabajo de ubicación que se creó. Debería ver el siguiente resultado:

    - 3 PL -\> FL-002
    - 1 PL -\> FL-003

1. Reciba *4* *PL* del número de artículo *D0013* en tamaño *L*.
1. Revise el trabajo de ubicación que se creó. Debería ver el siguiente resultado:

    - 1 PL -\> FL-003
    - 3 PL -\> FL-004

Según los resultados, puede concluir que el sistema no pudo asignar las ubicaciones correctas de almacenamiento. De lo contrario, ¿por qué el sistema agregó solo *1* *PL* de tamaño *L* a la ubicación *FL-003* en el ultimo paso, no *2* *PL*? Es decir, ¿por qué no hay un total de *3* *PL* para el almacenamiento en esa ubicación?

Para explicar esta aparente falla, debe comprender los criterios de selección para los límites de existencias de la ubicación. El sistema selecciona el registro coincidente más detallado. En este ejemplo, el registro coincidente más detallado es la línea donde el valor **Tamaño** es *L*, el valor **Cantidad** es *240* y el valor **Unidad** es *Ea*. Porque ya tiene trabajo abierto desde la recepción anterior de una cantidad de *120* *Ea* de tamaño *S*, la capacidad restante se calcula como *240* - *120* = *120* *Ea*. Por lo tanto, la capacidad restante solo puede transportar *1* *PL* de *80* *Ea*.

> [!NOTE]
> No puede utilizar los límites de existencias de la ubicación para controlar, por ejemplo, el reabastecimiento de artículos que tienen diferentes cantidades en la misma ubicación. En este caso, utilice una *plantilla de reposición*.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]