---
title: Configurar búferes de inventario y niveles de inventario
description: Este tema explica cómo configurar búferes de inventario y niveles de inventario que determinan los mensajes de disponibilidad de inventario en los sitios Microsoft Dynamics 365 Commerce.
author: boycezhu
manager: annbe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycez
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: ef58dbb756c7bed3924010cb33eff27af66cd0bd
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982609"
---
# <a name="configure-inventory-buffers-and-inventory-levels"></a>Configurar búferes de inventario y niveles de inventario

[!include [banner](includes/banner.md)]

Este tema explica cómo configurar búferes de inventario y niveles de inventario que determinan los mensajes sobre disponibilidad de inventario en los sitios Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

La sede central de Dynamics 365 Commerce mantiene los datos de inventario y varios canales, como aplicaciones de punto de venta (PDV), escaparates de comercio electrónico y otras aplicaciones integradas personalizadas que extraen e introducen inventario de forma asincrónica. Por lo tanto, los valores de inventario disponibles que se obtienen a través de la página de inventario disponible en la sede central de Commerce, a través de la interfaz de usuario de PDV (UI) y a través de las API de disponibilidad de inventario de comercio electrónico, no siempre tienen una precisión del 100 % en tiempo real.

En lugar de mostrar los valores de inventario reales en los escaparates de comercio electrónico, muchos minoristas prefieren simplemente mostrar mensajes sobre el estado de disponibilidad del inventario (por ejemplo, "Disponible" o "Agotado") para informar a los clientes si un artículo está disponible para la compra o si está potencialmente agotado. Para este enfoque, los búferes de inventario y los niveles de inventario que determinan los mensajes de disponibilidad de inventario deben estar disponibles y configurados.

## <a name="prerequisite-turn-on-the-inventory-buffers-and-inventory-levels-feature"></a>Requisito previo: active la característica de búferes de inventario y niveles de inventario

La característica para búferes de inventario y niveles de inventario se controla a través de la administración de características en la sede de Commerce. Para activar la característica, siga estos pasos.

1. Vaya a **Administración del sistema** \> **Espacios de trabajo** \> **Administración de características**.
1. Busque la característica **Habilitar búferes de inventario y niveles de inventario**, seleccione su fila y luego seleccione **Habilitar ahora**.

Después de activar la característica, puede encontrar niveles de inventario en **Comercio minorista y comercio \> Gestión del inventario**.

## <a name="create-and-configure-an-inventory-level-profile"></a>Crear y configurar un perfil de nivel de inventario.

Un *perfil de nivel de inventario* determina si un estado de cantidad de producto determinado se considera en stock, agotado o en algún otro estado personalizado. Puede crear y configurar múltiples perfiles de nivel de inventario por entidad jurídica. Cada perfil consta de un conjunto de niveles de inventario, y cada nivel está definido por un *rango*, un *código* y una *etiqueta*.

- **Rango**: cada rango está definido por una *cantidad inicial* y una *cantidad final*. Un valor de cantidad cae en un rango si es mayor que la cantidad inicial de ese rango y no supera la cantidad final.
- **Código**: un código es una abreviatura interna que representa el nivel. Los clientes que se integran directamente con las API de inventario pueden usar códigos para construir lógica adicional para un nivel de inventario dado. Por ejemplo, pueden desactivar la capacidad de compra de un producto cuando su código de nivel de inventario es **OOS** ("Agotado").
- **Etiqueta**: una etiqueta es un mensaje significativo dirigido al cliente que transmite un nivel de inventario a los clientes en un sitio de comercio electrónico.

### <a name="create-an-inventory-level-profile"></a>Crear un perfil de nivel de inventario

Para crear un perfil de nivel de inventario, siga estos pasos.

1. Vaya a **Comercio minorista y comercio** \> **Gestión del inventario** \> **Niveles de inventario**.
1. En el panel Acciones, seleccione **Nuevo** y luego introduzca valores en lo campos **Id. de perfil** y **Descripción**.
1. En la ficha desplegable **Rangos**, seleccione **Añadir** para agregar un nuevo nivel y luego introducir valores en las columnas **Cantidad inicial**, **Cantidad final**, **Código** y **Etiqueta** para ese nivel. Repita este paso para agregar más niveles. Según lo requiera, puede editar los valores de la cuadrícula de datos o puede seleccionar **Eliminar** para eliminar un nivel.
1. En el panel Acciones, seleccione **Guardar**.

Cuando se crea un nuevo perfil, se inicializan automáticamente dos niveles de inventario:

- **OOS**: el nivel de "stock agotado", donde el límite inferior del rango es infinito negativo. La cantidad inicial y el código no se pueden editar para este nivel.
- **DISPONIBILIDAD**: el nivel "disponible", donde el límite superior del rango es infinito. La cantidad final y el código no se pueden editar para este nivel.

> [!NOTE]
> No puede haber huecos ni superposición entre rangos en la definición del perfil.

Puede usar el botón **Traducciones** del panel Acciones para configurar cadenas localizadas para el mensaje de etiqueta. Luego debe ejecutar el trabajo de programación de distribución **1110** (**Configuración global**) para sincronizar las cadenas localizadas a los canales.

### <a name="configure-an-inventory-level-profile"></a>Configurarr un perfil de nivel de inventario

Puede configurar un perfil de nivel de inventario en el nivel de categoría de producto o en el nivel de producto individual. Cuando se configura un perfil de nivel de inventario para un producto, el nivel de inventario se determina en función de los rangos definidos en el perfil vinculado. De lo contrario, el nivel de inventario "disponible" o "agotado" se determina en función de si el producto tiene una cantidad positiva disponible.

Para configurar un perfil de nivel de inventario para una categoría, siga estos pasos.

1. Vaya a **Retail y Commerce** \> **Productos y categorías** \> **Jerarquía de productos de Commerce**.
1. Seleccione la categoría para configurar un perfil de nivel de inventario para esta.
1. En la lista desplegable **Vender propiedades del producto**, seleccione una entidad jurídica.
1. En la sección **Inventario de Commerce**, en el campo **Perfil de nivel de inventario**, seleccione uno de los perfiles de nivel de inventario predefinidos.

Puedes usar el botón **Actualizar productos** en el panel Acciones para propagar el valor del perfil de nivel de categoría a los productos subyacentes de la categoría. Para más información, consulte [Gestionar categorías de productos y productos](category-management-product-creation.md).

Para configurar un perfil de nivel de inventario para un producto despachado, siga estos pasos.

1. Vaya a **Retail y Commerce** \> **Productos y categorías** \> **Productos despachados por categoría**.
1. Seleccione un producto y luego abra la página de detalles del producto.
1. En la ficha desplegable **Vender**, en la sección **Inventario de Commerce**, en el campo **Perfil de nivel de inventario**, seleccione uno de los perfiles de nivel de inventario predefinidos.

Cuando se crea un nuevo producto, el campo **Perfil de nivel de inventario**, como muchos otros atributos de nivel de producto, se establecerá en el valor configurado para la categoría a la que está asociado el producto.

> [!NOTE]
> El perfil de nivel de inventario es un atributo específico de entidad jurídica. Para la misma categoría o producto, el valor del perfil de nivel de inventario puede variar entre las entidades legales.

Para sincronizar las configuraciones de los perfiles de nivel de inventario con los canales, siga estos pasos.

1. Vaya a **Retail y Commerce** \> **TI de Retail y Commerce** \> **Programación de distribución**.
1. Ejecute la programación de disribución **1040** (**Producto**).

## <a name="configure-an-inventory-buffer"></a>Configurar un búfer de inventario

El *búfer de inventario* es un valor definido por el usuario que resta la cantidad adicional de un artículo de la cantidad original para calcular la cantidad estimada. Esta cantidad estimada brinda a los minoristas un colchón seguro para que no sobrevendan un producto al vender más que su inventario real disponible. Puede configurar el búfer de inventario en el nivel de categoría de producto o en el nivel de producto individual. Si no se especifica búfer de inventario, se utiliza el valor predeterminado **0** (cero).

Para configurar un búfer de inventario para una categoría, siga estos pasos.

1. Vaya a **Retail y Commerce** \> **Productos y categorías** \> **Jerarquía de productos de Commerce**.
1. Seleccione la categoría para configurar el búfer de inventario para esta.
1. En la lista desplegable **Vender propiedades del producto**, seleccione una entidad jurídica.
1. En la sección **Inventario de comercio**, en el campo **Buffer de inventario**, introduzca un valor positivo.

Puede usar el botón **Actualizar productos** del panel Acciones para propagar el valor del búfer de nivel de categoría a los productos subyacentes de la categoría. Para más información, consulte [Gestionar categorías de productos y productos](category-management-product-creation.md).

Para configurar un búfer de inventario para un producto despachado, siga estos pasos.

1. Vaya a **Retail y Commerce** \> **Productos y categorías** \> **Productos despachados por categoría**.
1. Seleccione un producto y luego abra la página de detalles del producto.
1. En la ficha desplegable **Vender** de la sección **Inventario de comercio**, en el campo **Buffer de inventario**, introduzca un valor positivo.

Cuando se crea un nuevo producto, el campo **Buffer de inventario** se establecerá en el valor configurado para la categoría a la que está asociado el producto.

> [!NOTE]
> Si se configuran tanto el búfer de inventario como los perfiles de nivel de inventario para un producto, la cantidad estimada del producto (es decir, la cantidad original menos el valor del búfer) se usará para el cálculo del rango para determinar el nivel de inventario.

Para sincronizar las configuraciones de los búferes de inventario con los canales, siga estos pasos.

1. Vaya a **Retail y Commerce** \> **TI de Retail y Commerce** \> **Programación de distribución**.
1. Ejecute la programación de disribución **1040** (**Producto**).

## <a name="use-inventory-buffers-and-inventory-levels-in-e-commerce-scenario"></a>Usar búferes de inventario y niveles de inventario en el escenario de comercio electrónico

El creador de sitios de Commerce utiliza las capacidades de búfer de inventario y nivel de inventario en la sede de Commerce para determinar los mensajes de disponibilidad de inventario en los sitios de comercio electrónico. Para obtener más información, consulte [Aplicar configuración de inventario](inventory-settings.md).

Alternativamente, si se integra con una solución de comercio electrónico de terceros, puede usar las API **GetEstimatedAvailability** y **GetEstimatedProductWarehouseAvailability** para mostrar la disponibilidad de inventario de un producto en su escenario de comercio electrónico. Para obtener más información sobre estas API, consulte [Calcular la disponibilidad de inventario para canales minoristas](calculated-inventory-retail-channels.md).

La introducción de búferes de inventario y niveles de inventario permite que estas API devuelvan códigos de nivel de inventario y mensajes de etiqueta que se determinan en función de los valores disponibles y físicos totales disponibles. Las API se pueden configurar además para determinar si la cantidad de inventario se devuelve junto con el mensaje, y si la cantidad disponible se reduce por el valor del búfer de inventario.

Para configurar la respuesta de las API de disponibilidad del producto, siga estos pasos.

1. Vaya a **Retail y Commerce** \> **Configuración de Headquarters** \> **Parámetros** \> **Parámetros de Commerce**.
1. En la sección **Almacenar inventario**, en la pestaña **Inventario**, en el campo **API de disponibilidad de productos para comercio electrónico**, seleccione un valor.
1. Para aplicar la configuración a los canales, ejecute el trabajo de programación de distribución **1110** (**Configuración global**) .

## <a name="additional-resources"></a>Recursos adicionales

[Administrar categorías de productos y productos](category-management-product-creation.md)

[Aplicar configuración de inventario](inventory-settings.md)

[Calcular la disponibilidad de inventario para canales comerciales](calculated-inventory-retail-channels.md)
