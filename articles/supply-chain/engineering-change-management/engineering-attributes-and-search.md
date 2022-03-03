---
title: Atributos de ingeniería y búsqueda de atributos de ingeniería
description: Este tema explica cómo puede utilizar atributos de ingeniería para especificar todas las características no estándar, para garantizar que todos los datos maestros del producto se puedan registrar en el sistema. También explica cómo puede utilizar la búsqueda de atributos de ingeniería para encontrar productos fácilmente, basándose en esas características registradas.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgProductAttributeSearch, EngChgMaintainAttributeInheritance, EngChgAttribute
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 59710f0366418e240a4109e7cf8fcf84073110bf
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103222"
---
# <a name="engineering-attributes-and-engineering-attribute-search"></a>Atributos de ingeniería y búsqueda de atributos de ingeniería

[!include [banner](../includes/banner.md)]

Para asegurarse de que todos los datos maestros del producto puedan registrarse en el sistema, debe utilizar atributos de ingeniería para especificar todas las características no estándar. Después puede utilizar la búsqueda de atributos de ingeniería para encontrar productos fácilmente, basándose en esas características registradas.

## <a name="create-engineering-attributes-and-attribute-types"></a>Crear tipos de atributos y atributos de ingeniería

Normalmente, los productos de ingeniería tienen muchas características y propiedades que debe capturar. Aunque puede registrar algunas de las propiedades mediante los campos de producto estándar, también puede crear nuevas propiedades de ingeniería según sea necesario. Puede definir sus propios *atributos de ingeniería* e incorporarlos a la definición del producto.

Cada atributo de ingeniería debe pertenecer a un *tipo de atributo*. Este requisito existe porque cada atributo de ingeniería debe tener un *tipo de datos* que define los tipos de valores que puede contener. Un tipo de atributo de ingeniería puede ser un tipo estándar (como texto libre, entero o decimal) o un tipo personalizado (como texto que tiene un conjunto específico de valores para seleccionar). Puede reutilizar cada tipo de atributo con cualquier número de atributos de ingeniería.

### <a name="set-up-engineering-attribute-types"></a>Configurar tipos de atributo de ingeniería

Para ver, crear o editar un tipo de atributo de ingeniería, siga estos pasos.

1. Vaya a **Gestión de cambios de ingeniería \> Preparar \> Atributos \> Tipos de atributos**.
1. Seleccione un atributo existente, escriba el panel de lista o seleccione **Nuevo** en el Panel de acciones para crear un nuevo tipo de atributo.
1. Establezca los campos siguientes:

    - **Nombre de tipo de atributo** – Especifique un nombre para el tipo de atributo.
    - **Tipo** - Seleccione un tipo de datos estándar (*Moneda*, *Fecha y hora*, *Decimal*, *Entero*, *Texto*, *Booleano* o *Referencia*).
    - **Lista fija** - Esta opción está disponible solo si configura el campo **Tipo** como *Texto*. Establézcalo en *Sí* para definir valores específicos para atributos de este tipo. En este caso, se creará una lista desplegable. Use la ficha desplegable **Valor** para establecer los valores que están disponibles para este tipo de atributo. Establezca esta opción en *No* para permitir que los usuarios ingresen cualquier valor. En este caso, se creará un campo de entrada.
    - **Rango de valores** - Esta opción está disponible solo si configura el campo **Tipo** como *Entero*, *Decimal* o *Moneda*. Establézcalo en *Sí* para establecer valores mínimos y máximos que serán aceptados para atributos de este tipo. Use la ficha despelgable **Rango** para establecer los valores mínimos y máximos y (para la divisa) la moneda que se aplica a los límites que ingresó. Establezca esta opción en *No* para aceptar cualquier valor. 
    - **Unidad de medida** - Este campo está disponible solo si configura el campo **Tipo** como *Entero* o *Decimal*. Seleccione la unidad de medida que se aplica a este tipo de atributo. Si no se requiere ninguna unidad, deje este campo en blanco.

### <a name="set-up-engineering-attributes"></a>Configurar atributos de ingeniería

Para ver, crear o editar un tipo de atributo de ingeniería, siga estos pasos.

1. Vaya a **Gestión de cambios de ingeniería \> Preparar \> Atributos \> Atributos de ingeniería**.
1. Seleccione un atributo existente en el panel de lista o seleccione **Nuevo** en el Panel de acciones para crear un nuevo atributo.
1. Establezca los campos siguientes:

    - **Nombre**: escriba un nombre para el atributo. Este nombre aparece solo en la página **Atributos de ingeniería**. En el resto del sistema, el valor del campo **Nombre amigable** generalmente se muestra para identificar el atributo.
    - **Tipo de atributo** - Seleccione un tipo de atributo que definió en la sección anterior.
    - **Nombre amigable** - Ingrese un nombre que identifique el atributo en el sistema (excepto en la página **Atributos de ingeniería**). 
    - **Descripción**: escriba una descripción del atributo.
    - **Texto de ayuda** - Ingrese el texto de ayuda que le dice a otros usuarios para qué es el atributo.
    - **Valor por defecto** - Introduzca un valor predeterminado para el atributo. Las opciones que se presentan dependen del tipo de atributo que seleccionó.
    - **Moneda** - Si el tipo de atributo que seleccionó es una moneda, seleccione la moneda que el atributo aceptará y mostrará los valores.

1. Si el tipo de atributo que seleccionó es un número entero o un decimal, se muestra la ficha desplegable **Rango**. En esta ficha rápida, establezca los siguientes campos, según sea necesario:

    - **Acción de tolerancia** - Seleccione cómo debe responder el sistema si un usuario ingresa un valor fuera del rango especificado. Si selecciona *Advertencia*, se muestra una advertencia, pero el usuario puede guardar el valor. Si selecciona *No permitido*, se muestra una advertencia y el valor no se puede guardar hasta que el usuario lo corrija.
    - **Mínimo** - Ingrese el valor mínimo recomendado o aceptado.
    - **Máximo** - Ingrese el valor máximo recomendado o aceptado.

### <a name="engineering-attribute-inheritance"></a>Herencia de atributos de ingeniería

Para estructuras de productos, como listas de materiales (LDM) o fórmulas, los atributos seleccionados se pueden pasar de los artículos secundarios a los artículos principales. Puede pensar en este proceso como "herencia inversa".

#### <a name="turn-engineering-attribute-inheritance-on-or-off"></a>Activar o desactivar la herencia de atributos de ingeniería

Esta característica requiere que se activen las características *Administración de cambios de ingeniería* y *Herencia de atributos mejorada para la administración de cambios de ingeniería* en su sistema. Para obtener detalles sobre cómo activar o desactivar estas características, consulte [Información general de la gestión de cambios de ingeniería](product-engineering-overview.md).

#### <a name="attribute-inheritance-example"></a>Ejemplo de herencia de atributos

Para un producto alimenticio como un pastel de zanahoria, el sistema debe registrar cada alérgeno que contiene el producto. El pastel de zanahoria se puede modelar en el sistema como un producto de ingeniería que tiene una fórmula. Esta fórmula contiene los ingredientes del pastel de zanahoria, como harina, leche, zanahorias y nueces. En este ejemplo, la empresa ofrece dos modelos de pastel de zanahoria: uno que contiene lactosa y otro que no.

La torta que contiene lactosa tiene los siguientes atributos a nivel de ingrediente:

- Ingrediente "harina": atributo "gluten" = sí
- Ingrediente "leche": atributo "lactosa" = sí
- Ingrediente "frutos secos": atributo "frutos secos" = sí

La torta que no contiene lactosa usa leche sin lactosa y tiene los siguientes atributos a nivel de ingrediente:

- Ingrediente "harina": atributo "gluten" = sí
- Ingrediente "leche": atributo "lactosa" = no
- Ingrediente "frutos secos": atributo "frutos secos" = sí

Debido a que estos productos son en su mayoría similares, podría ser conveniente pasar estos atributos de los hijos (las dos variaciones) al producto principal (el pastel de zanahoria básico). Para implementar esta "herencia inversa", puede utilizar la funcionalidad *Herencia de atributos*. Esta funcionalidad se define para cada [versión de ingeniería](engineering-versions-product-category.md).

## <a name="connect-engineering-attributes-to-an-engineering-product-category"></a>Conecte los atributos de ingeniería a una categoría de productos de ingeniería

Algunos atributos de ingeniería se aplican a todos los productos, mientras que otros son específicos de productos individuales o categorías de productos. Por ejemplo, los atributos eléctricos no son necesarios para los productos mecánicos. Por lo tanto, puede configurar *categorías de productos de ingeniería*. Una categoría de producto de ingeniería establece la colección de atributos de ingeniería que deben ser parte de la definición de productos que pertenecen a esa categoría. También puede especificar qué atributos de ingeniería son obligatorios y si existe un valor predeterminado.

Para obtener más información sobre cómo trabajar con categorías de productos de ingeniería, incluida información sobre cómo conectar atributos a categorías, consulte [Versiones de ingeniería y categorías de productos de ingeniería](engineering-versions-product-category.md).

## <a name="set-attribute-values-for-engineering-attributes"></a>Establecer valores para atributos de ingeniería

Los atributos de ingeniería que están conectados a una categoría de producto de ingeniería se presentan cuando crea un nuevo producto de ingeniería que se basa en esa categoría. En ese momento, puede establecer valores para los atributos. Posteriormente, esos valores se pueden cambiar en la página **Versión de ingeniería** o como parte de la gestión de cambios de ingeniería en una orden de cambio de ingeniería. Para más información, ver [Gestionar cambios en productos de ingeniería](engineering-change-management.md).

## <a name="create-an-engineering-product"></a>Crear un producto de ingeniería

Para crear un producto de ingeniería, abra la página **Productos lanzados**. Después, en el panel de acciones, en la pestaña **Producto** del grupo **Nuevo**, seleccione **Producto de ingeniería**.

Debe especificar la categoría de ingeniería a la que pertenece el producto. La categoría establecerá todos los valores y características predeterminados para el producto. También establecerá los atributos que son aplicables al producto. Una vez seleccionada la categoría, se establecerán valores para los atributos. Luego puede modificar esos valores.

## <a name="search-for-products-by-using-engineering-attribute-values"></a>Busque productos utilizando valores de atributos de ingeniería

Puede utilizar la búsqueda de atributos de ingeniería para encontrar productos buscando sus valores de atributos de ingeniería. Por lo tanto, puede encontrar fácilmente productos de ingeniería, en función de sus características. Puede buscar en los productos que pertenecen a una categoría de productos de ingeniería, o puede buscar en todos los productos de ingeniería.

La búsqueda está disponible en las páginas de datos maestros de productos y en los artículos transaccionales del sistema, como los pedidos de cliente. Para un artículo transaccional, puede utilizar la página **Búsqueda de atributos de ingeniería** para buscar un producto. A continuación, puede utilizar el botón **Agregar como nueva línea** para agregar el producto a las líneas de orden de venta. Los productos en los resultados de la búsqueda también se pueden agregar directamente al pedido.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
