---
title: Preguntas frecuentes de administración de cambios de ingeniería
description: Este tema proporciona respuestas a preguntas frecuentes acerca de la característica de administración de cambios de ingeniería.
author: t-benebo
ms.date: 03/25/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-03-25
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 69232eed8520bafeb734ffad43b333bf9e36909e
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018694"
---
# <a name="engineering-change-management-faq"></a>Preguntas frecuentes de administración de cambios de ingeniería

[!include [banner](../includes/banner.md)]

Este tema proporciona respuestas a preguntas frecuentes acerca de la característica de administración de cambios de ingeniería.

## <a name="should-i-track-the-version-in-transactions"></a>¿Debo seguir la versión en las transacciones?

Cuando crea una categoría de cambio de ingeniería, la página **Detalles de la categoría de cambio de ingeniería** ofrece una opción que se denomina **Seguir versión en transacciones**. ¿Qué es esta opción y qué hace?

- Si configura la opción **Seguimiento de versión en transacciones** en *Sí*, el campo **Grupo de dimensiones** se filtrará para que muestre solo los grupos de dimensiones donde la versión es una dimensión activa.
- Si configura la opción **Seguir versión en transacciones** en *No*, el campo **Grupo de dimensiones** se filtrará para que muestre solo los grupos de dimensiones donde la dimensión de la versión **no** es una dimensión activa.

### <a name="if-you-track-the-version-in-transactions"></a>Si sigue la versión en las transacciones

Para las categorías de ingeniería en las que ha seleccionado un grupo de dimensiones donde la versión es una dimensión activa, seguirá las versiones en las transacciones de los productos de esa categoría. En este caso, el producto de ingeniería será un producto maestro, y cada versión del producto será una variante del producto que utiliza la dimensión de versión. Se pueden utilizar otras dimensiones junto con la dimensión de la versión.

En este caso, cada versión de ingeniería se tratará como una variante en todos los procesos. Por lo tanto, si tiene una variante específica en una transacción (para que pueda determinar qué variante se vendió o se compró), debe administrar las existencias para cada versión, la planificación maestra planificará el suministro para cada versión, etc. Si retira una versión del mercado, debe ajustar manualmente sus fechas de inicio y finalización de vigencia para que reflejen el cambio. También debe administrar su inventario para asegurarse de que no tenga versiones sin usar de artículos en sus almacenes.

Aunque esta opción requiere un mayor esfuerzo de gestión, la recomendamos si requiere una alta trazabilidad de las versiones específicas que se utilizan en cada transacción.

### <a name="if-you-dont-track-the-version-in-transactions"></a>Si no sigue la versión en las transacciones

Para las categorías de ingeniería en las que ha seleccionado un grupo de dimensiones donde la versión **no** es una dimensión activa, **no** seguirá las versiones en las transacciones de los productos de esa categoría. En este caso, si no utiliza ninguna otra dimensión, el producto de ingeniería será un producto distinto. El producto seguirá estando versionado y podrá administrar información sobre versiones específicas (por ejemplo, su lista de materiales \[L. MAT] y ruta), pero no podrá rastrear qué versión específica se usó en cada transacción. Las fechas de en vigor desde y en vigor hasta indican la validez de cada versión.

Esta opción es mucho más fácil de administrar, porque si desea cambiar de una versión a otra, solo tiene que realizar los cambios necesarios en una orden de cambio y luego actualizar las fechas de en vigor desde y en vigor hasta en la versión de ingeniería. Los procesos de producción luego recogerán la L. MAT requerida y la ruta para el producto (y su versión específica).

La mayoría de las organizaciones eligen esta opción porque proporciona administración de versiones y cambios, pero no agrega la sobrecarga adicional de seguir la versión en cada transacción, en el inventario y durante la planificación maestra.

## <a name="which-fields-are-copied-to-the-released-item-template"></a>¿Qué campos se copian en la plantilla de artículo liberado?

Cuando una empresa de ingeniería crea un producto de ingeniería, ese producto se crea como un producto lanzado en la empresa de ingeniería. El producto liberado que se crea se basa en la *plantilla de artículo publicado* seleccionado. (La plantilla de artículo liberado es en sí misma un producto liberado existente). La plantilla de artículo liberado también se utiliza cuando el producto se libera a una empresa operativa. En cada caso, la plantilla de artículo liberado define la mayoría de los valores de campo para el producto publicado, y esos valores provienen de la página **Detalles del producto publicado**.

Las siguientes tablas muestran los campos que se copian durante estos procesos.

| Ficha desplegable | Campos que se copian en la creación de productos en la empresa de ingeniería | Campos que se copian en la liberación a una empresa operativa |
|---|---|---|
| **General** | Todos los campos de la sección **Administración** | Los mismos campos que se copian para la empresa de ingeniería |
| **Compra** | Todos los campos | Todos los campos excepto **Unidad** |
| **Vender** | Todos los campos de las siguientes secciones: **Pedido de ventas**, **Administración**, **Tasación**, **Actualización de precio**, **Precio base de venta**, **Cargos**, **Descuentos** y **Producto alternativo** | Los mismos campos que se copian para la empresa de ingeniería, excepto **Unidad** |
| **Comercio exterior** | Todos los campos | Todos los campos |
| **Administrar inventario** | Todos los campos y secciones, *excepto* **Dimensiones físicas** y **Peso capturado** | Los mismos campos que se copian para la empresa de ingeniería, excepto **Unidad** |
| **Ingeniero**, **Plan**, **Gestionar costes**, **Gestionar proyectos**, **Dimensiones financieras** y **Almacén** | Todos los campos | Todos los campos excepto **Unidad de L. MAT** |
| **Variantes del producto** | Todos los campos de la sección **Variante de producto predeterminada** | Los mismos campos que se copian para la empresa de ingeniería |

Además de los campos que se muestran en la tabla anterior, todas las configuraciones de pedido predeterminadas se copian de la plantilla de artículo liberado, tanto cuando el producto se crea en la empresa de ingeniería como cuando se libera a una empresa operativa. (Para ver la configuración de pedido predeterminada para una plantilla de artículo liberado, abra la página **Detalles del producto liberado** correspondiente y luego, en el panel de acciones, en la pestaña **Administrar inventario**, seleccione **Configuración de pedido predeterminada**).

## <a name="should-i-create-a-separate-legal-entity-for-engineering-products-or-use-an-existing-legal-entity"></a>¿Debo crear una entidad jurídica separada para productos de ingeniería o utilizar una entidad jurídica existente?

Los requisitos de su negocio determinan si debe crear una nueva entidad jurídica para los productos de ingeniería.

Al crear una empresa de ingeniería separada, puede mantener los datos de ingeniería separados y luego agregar modificaciones según sean necesarias para sus empresas operativas locales. De esta forma, puede logar los objetivos siguientes:

- Mantenga una entidad separada donde se crean y administran los productos de ingeniería.
- Evite que los productos de ingeniería aparezcan junto con el resto de sus productos liberados hasta que estén listos y liberados.
- Distinga claramente los datos dictados por la ingeniería y los datos locales.

Por otro lado, probablemente debería utilizar una entidad jurídica existente como una empresa de ingeniería si se le aplican las siguientes condiciones:

- Solo tiene una entidad jurídica en su sistema y/o no necesita una separación clara entre los productos que se están diseñando.
- No desea duplicar algunos datos, como grupos de recursos, recursos, operaciones y (quizás) sitios.

## <a name="what-is-the-nomenclature-for-engineering-versions-and-variants"></a>¿Cuál es la nomenclatura de las versiones y variantes de ingeniería?

La nomenclatura para productos de ingeniería y variantes de productos funciona de la siguiente manera:

- Para el producto de ingeniería (es decir, el producto único si no se usan dimensiones, o el producto maestro si se usa alguna dimensión), la nomenclatura de la regla numérica se define en la categoría de producto de ingeniería. Allí, tiene la opción de usar una secuencia numérica, constantes de texto y nombres y valores de atributos.
- Para cada variante de un producto de ingeniería (si su producto de ingeniería es un producto maestro, las variantes se configuran en la categoría de producto de ingeniería donde especifica el grupo de dimensiones), la nomenclatura de la regla numérica para cada variante se define en el grupo de dimensiones. En este caso, puede utilizar el id. del producto del maestro y los valores y nombres de dimensión.
