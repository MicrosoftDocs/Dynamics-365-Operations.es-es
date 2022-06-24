---
title: Convenios
description: Este artículo describe cómo configurar convenciones para establecer cómo se deben contabilizar los costos en la Contabilidad de inventario global.
author: JennySong-SH
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 0055757a0d012896232de58330ee142f702e4ed1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875405"
---
# <a name="conventions"></a>Convenios

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until 4/30/2022 -->

Una convención es un contenedor para un conjunto de políticas que afectan el comportamiento del sistema. Según los requisitos de su negocio, debe definir convenciones mediante una combinación de las diversas políticas que establecen cómo se deben contabilizar los costos en la Contabilidad de inventario global. Puede asociar cada convención con uno o más libros mayores para garantizar la coherencia en las políticas contables que se aplican en todos los libros mayores.

Para configurar sus convenciones, vaya a **Contabilidad global de inventarios \> Configuración \> Convenciones**. Para cada convención, establezca los siguientes campos:

- **Nombre**: especifique el nombre de la convención.
- **Descripción**: escriba una descripción de la convención.
- **Política de objeto de coste** - Seleccione una política de objeto de coste. Estas políticas determinan el nivel de granularidad que aplica el sistema para calcular y mantener el valor del inventario. Las siguientes opciones predefinidas están disponibles:

    - Producto
    - Producto - Sitio
    - Producto - Sitio - Almacén

    Por ejemplo, si selecciona *Producto - Sitio*, para cada movimiento de inventario (entrada o salida), el sistema calcula y mantiene el costo de inventario de cada producto a nivel de sitio. Por lo tanto, los movimientos de inventario en niveles inferiores, como el nivel de almacén, no afectan el valor del inventario. (Un ejemplo de una transferencia a nivel de almacén es una transferencia de artículo entre dos almacenes en un sitio). Asimismo, no puede ver el costo de inventario en un nivel inferior, como el nivel de almacén.

- **Política de base de medición de insumos** - Seleccione una política de base de medición de insumos. Estas políticas determinan los costos que deben fluir a la cuenta de inventario y los costos que deben cargarse. Las siguientes opciones son relevantes para las empresas comerciales:

    - **Histórico normal** - Todos los componentes del costo fluyen hacia la cuenta de inventario.
    - **Estándar** - El costo estándar fluye hacia las cuentas de inventario y la diferencia entre el costo aplicado y los costos reales se carga a las cuentas de variación. Si desea crear una política de base de medición de entrada *Estándar*, primero debe crear una lista de precios donde la política pueda buscar el costo estándar del artículo.
    - **Lista de precios** - La contabilidad de inventario global admite la obtención de precios de artículos de varias entidades legales. Puede definir una lista de precios que utilizará la política de base de medición de entrada. De esta forma, el sistema sabrá dónde buscar el precio del artículo. Siga estos pasos para configurar listas de precios:

        1. Escriba un nombre en el campo **Nombre**.
        1. En el campo **Descripción**, escriba una descripción.
        1. En el campo **Tipo de coste**, seleccione un tipo de coste (*Costo estándar* o *Costo planificado*).
        1. En el campo **Tipo de precio**, seleccione un tipo de precio (*Costo*, *Compra* o *Precio de venta*).
        1. Agregue una versión de gestión de costes.
        1. En el panel de acciones, seleccione **Precio** para validar los precios de los artículos en la lista de precios.

- **Política de asunción de flujo de costos** - Seleccione una política de suposición de flujo de costos. Estas políticas determinan cómo se eliminan los costos del inventario y se informan como el costo de los bienes vendidos. Las siguientes opciones predefinidas están disponibles:

    - Promedio
    - Específico - Lote

    > [!NOTE]
    > La contabilidad de inventario global es un sistema de inventario perpetuo. Por lo tanto, el sistema rastrea el valor del inventario transacción por transacción.

- **Política de elementos de costo** - Puede definir políticas de elementos de coste y vincularlas a este campo. Un *elemento de costo* es el costo de un recurso consumido por un evento. Puede usar elementos de costo para rastrear y categorizar costos. Para crear políticas de clases de costo, ingrese información en los siguientes lugares:

    - Campo **Nombre**
    - Campo **Descripción**
    - Lista **Elemento de coste**
    - Cuadrícula **Reglas**

    Si no desea desglosar más el valor del inventario, debe crear una lista de elementos de costo que tenga un solo elemento de costo. A continuación, debe crear una política de elementos de costo para asignar todos los tipos de medición relevantes (componentes de costo) a ese elemento de costo.
