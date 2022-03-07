---
title: Pruebas de gestión de calidad
description: Este tema describe cómo crear pruebas que se puedan usar para pedidos de calidad en Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 95f759d051a520b577cb1cf3d595ce64e0dc4668
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021693"
---
# <a name="quality-management-tests"></a>Pruebas de gestión de calidad

[!include [banner](../includes/banner.md)]

Este tema describe cómo crear pruebas que se puedan usar para pedidos de calidad en Microsoft Dynamics 365 Supply Chain Management.

Utilice la página **Pruebas** para definir y visualizar las pruebas individuales que determinan si sus productos cumplen las especificaciones. Puede asignar una o varias pruebas individuales a un grupo de pruebas. En este caso, también especifica la información específica de la prueba, como los valores de medida aceptables. Los valores de medida se utilizan para pruebas cuantitativas. Para las pruebas cualitativas, se utilizan variables de prueba.

- Para pruebas cuantitativas, el campo **Tipo** está configurado en *Entero* o *Fracción*. También se especifica una unidad de medida. Las especificaciones de calidad y los resultados de la prueba se expresan como números.
- Para las pruebas cualitativas, el campo **Tipo** está establecido en *Opción*. Las pruebas cualitativas requieren información adicional sobre la variable de prueba que se está midiendo y sus opciones enumeradas. Las especificaciones de calidad y los resultados de la prueba se expresan en función de un resultado.

Puede asignar opcionalmente un instrumento de prueba a una prueba. Sin embargo, no se requieren instrumentos de prueba para crear y usar pruebas con pedidos de calidad. Para más información, consulte [Instrumentos de prueba de gestión de calidad](quality-test-instruments.md).

También puede especificar opcionalmente una unidad para una prueba, para indicar la unidad de medida en la que se registran los resultados de la prueba. Por ejemplo, una prueba de temperatura puede incluir una unidad de grados Fahrenheit o grados Celsius.

## <a name="example-of-a-test"></a>Ejemplo de prueba

Una empresa de fabricación realiza dos pruebas en el material adquirido: una prueba cuantitativa sobre la calidad del material y una prueba cualitativa de los daños de embalaje. La empresa especifica información adicional sobre la prueba cualitativa para definir la variable de prueba (por ejemplo, embalaje dañado) y sus resultados. La empresa usa la página **Grupos de prueba** para asignar las dos pruebas a un grupo de pruebas y para especificar la información específica de la prueba. El grupo de pruebas se asigna a un pedido de calidad, de modo que la empresa puede informar de los resultados de prueba para las dos pruebas.

## <a name="create-a-test"></a>Crear una prueba

Siga estos pasos para crear una prueba.

1. Vaya a **Gestión del inventario \> Configurar \> Control de calidad \> Pruebas**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula. Entonces establezca los siguientes campos para la fila nueva:

    - **Prueba**: introduzca un id. o nombre único para la prueba.
    - **Descripción**: escriba una descripción detallada de la prueba.
    - **Tipo**: seleccione el tipo de resultados que produce la prueba. Para pruebas cuantitativas, seleccione *Fracción* o *Entero*. Para pruebas cualitativas, seleccione *Opción*.
    - **Instrumento de prueba**: seleccione un [instrumento de prueba](quality-test-instruments.md) que debe utilizarse para la prueba.
    - **Unidad**: si seleccionó *Fracción* o *Entero* en el campo **Tipo** (es decir, si la prueba es una prueba cuantitativa), seleccione la unidad de medida en la que se deben registrar los resultados de la prueba.

1. Cierre la página.

> [!NOTE]
> Después de guardar una prueba, ya no puede editar el campo **Tipo** en la cuadrícula. Si debe cambiar el tipo de resultados de prueba que se registrarán para una prueba, seleccione **Cambiar el tipo de prueba de calidad** en el panel de acciones. En el cuadro de diálogo **Cambiar el tipo de prueba de calidad**, establezca el campo **Nuevo tipo** en el tipo deseado y luego seleccione **Aceptar** para cerrar el cuadro de diálogo.

## <a name="additional-resources"></a>Recursos adicionales

- [Instrumentos de prueba de gestión de calidad](quality-test-instruments.md)
- [Grupos de pruebas de gestión de calidad](quality-test-groups.md)
- [Variables de prueba de gestión de calidad](quality-test-variables.md)
- [Asociaciones de calidad](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
