---
title: Crear catálogos de Commerce para sitios B2B
description: Este tema describe cómo crear catálogos de Commerce para sitios de negocio a negocio (BB2B) de Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 05/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: 7382062706c2de01c499ee05aeb0b45ff6fb37cb
ms.sourcegitcommit: bca0cb730307948368a9aabe322cf963688ed8b1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2022
ms.locfileid: "8782846"
---
# <a name="create-commerce-catalogs-for-b2b-sites"></a>Crear catálogos de Commerce para sitios B2B

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Este tema describe cómo crear catálogos de productos de Commerce para sitios de negocio a negocio (BB2B) de Microsoft Dynamics 365 Commerce. Para obtener respuestas a las preguntas más frecuentes sobre los catálogos de Commerce para sitios B2B, consulte [Catálogos de Commerce para preguntas frecuentes B2B](catalogs-b2b-sites-FAQ.md).

> [!NOTE]
> Este tema se aplica a la versión 10.0.27 Dynamics 365 Commerce y posteriores.

Puede usar los catálogos de Commerce para identificar los productos que desee ofrecer en las tiendas B2B en línea. Al crear un catálogo, identifica las tiendas en línea en las que se ofrecen los productos, agrega los productos que desee incluir y mejora las ofertas de producto mediante la adición de detalles de comercialización. Puede crear varios catálogos para cada tienda B2B en línea.

Los catálogos de productos de Commerce le permiten definir la siguiente información:

- **Jerarquía de navegación específica del catálogo** – Las organizaciones pueden crear una estructura de categoría distinta para su catálogo específico.
- **Metadatos de atributos específicos del catálogo** – Los atributos contienen detalles sobre un producto. Al asignar atributos a una categoría de la jerarquía de navegación, puede definir valores para esos atributos en el nivel de productos que están asignados a esa categoría. Las organizaciones pueden completar entonces estas tareas:

    - Defina valores de atributo específicos del catálogo.
    - Controle la visibilidad de los atributos a nivel de catálogo.
    - Seleccione los refinadores que son específicos de un catálogo individual.

- **Canales** – Las organizaciones pueden asociar más de un canal online B2B a un catálogo. Actualmente, el soporte de un extremo a otro para catálogos solo está disponible para tiendas en línea B2B.
- **Jerarquías de clientes** – Para un canal B2B dado, las organizaciones pueden hacer que un catálogo específico esté disponible para socios B2B seleccionados al asociar jerarquías de clientes con ese catálogo.
- **Grupos de precios** – Puede configurar precios y promociones específicas para un catálogo determinado. Esta capacidad es una razón central para definir un catálogo para un canal B2B. Los grupos de precios para catálogos permiten a las organizaciones hacer que los productos estén disponibles para sus organizaciones B2B previstas y aplicar sus precios y descuentos preferidos. Los clientes B2B que realizan pedidos de un catálogo configurado pueden beneficiarse de precios especiales y promociones después de iniciar sesión en un sitio Commerce B2B. Para configurar precios específicos del catálogo, seleccione **Grupos de precios** en la pestaña **Catálogos** para vincular uno o varios grupos de precios al catálogo. Todos los acuerdos comerciales, diarios de ajuste de precios y descuentos avanzados que se han vinculado al mismo grupo de precios se aplicarán cuando los clientes pidan de ese catálogo. (Los descuentos avanzados incluyen descuentos por umbral, por cantidad y combinados). Para obtener más información acerca de los grupos de precios, consulte [Grupos de precios](price-management.md#price-groups).

> [!NOTE]
> Esta característica está disponible en la versión 10.0.27 Dynamics 365 Commerce. Para configurar configuraciones específicas del catálogo, como la jerarquía de navegación y la jerarquía de clientes, en la sede de Commerce, abra el espacio de trabajo **Gestión de características** (**Administración del sistema \> Espacios de trabajo \> Gestión de características**), habilite la característica **Habilitar el uso de múltiples catálogos en canales minoristas** y, a continuación, ejecute el trabajo **1110 CDX**.

## <a name="catalog-process-flow"></a>Flujo de procesos del catálogo

El proceso de creación y procesamiento de un catálogo consta de cuatro pasos generales. Cada paso se explica en detalle en la siguiente sección.

1. **[Configuración](#configure-the-catalog)**

    - Asociar la jerarquía de navegación.
    - Especificar las fechas de vigencia y vencimiento, si corresponde.
    - Agregar y categorizar productos.
    - Asociar grupos de precios.
    - Asociar una jerarquía de clientes que sea específica para sus organizaciones B2B. 
    - Asociar el grupo de atributos de dimensión predeterminado para refinadores como tamaño, estilo y color.
    - Configurar metadatos de atributos.

1. **[Validación](#validate-the-catalog)** – En este paso, ejecuta reglas de validación que imponen un comportamiento específico. A continuación, encontrará algunos ejemplos:

    - Asegúrese de que no haya productos sin categorizar.
    - Asegúrese de que todos los artículos que se surten en cada canal estén asociados a un catálogo.

1. **[Aprobación](#approve-the-catalog)**
1. **[Publicando](#publish-the-catalog)**

## <a name="set-up-the-catalog"></a>Configurar el catálogo

Utilice la información de esta sección para configurar su catálogo.

### <a name="configure-the-catalog"></a>Configurar el catálogo

En la sede de Commerce, vaya a **Retail y Commerce \> Catálogos y surtidos \> Todos los catálogos** para configurar su catálogo.

Cuando cree un nuevo catálogo, primero debe asociarlo a uno o varios canales. Solo pueden utilizarse los elementos vinculados a su canal seleccionado [surtidos](/dynamics365/unified-operations/retail/assortments) al crear el catálogo. Para asociar el catálogo con uno o más canales, seleccione **Agregar** en la ficha desplegable **Canales de Commerce** de la página **Configuración del catálogo**.

#### <a name="associate-the-navigation-hierarchy"></a>Asociar la jerarquía de navegación

Para agregar productos a un catálogo, debe seleccionar una jerarquía de navegación. La jerarquía de navegación admite la estructura de categoría para el catálogo. Debe seleccionar una de las jerarquías de navegación asociadas a los canales seleccionados en la ficha desplegable **Canales de Commerce** de la página **Catálogo**. Para asociar una jerarquía de navegación predeterminada con cada uno de sus canales, vaya a **Retail y Commerce \> Configuración de canales \> Categorías de canales y atributos de productos**.

#### <a name="specify-time-effective-and-expiration-dates"></a>Especifique las fechas de vigencia y vencimiento

Para especificar las fechas de vigencia y vencimiento de un catálogo, seleccione el nodo superior de la jerarquía del catálogo para volver a la vista principal del encabezado del catálogo. A continuación, en la ficha desplegable **General**, configure las fechas efectiva y de vencimiento según sea necesario.

#### <a name="add-and-categorize-products"></a>Agregar y categorizar productos

Para configurar productos para agregar al catálogo, en la sede de Commerce, vaya a **Retail y Commerce \> Catálogos y surtidos \> Todos los catálogos**. Después, en la pestaña **Catálogos**, seleccione **Agregar productos**.

Como alternativa, seleccione un nodo en la jerarquía de navegación. Entonces podrá agregar productos directamente a una categoría en el catálogo.

#### <a name="associate-price-groups"></a>Asociar grupos de precios

Para configurar precios específicos del catálogo, debe vincular uno o más grupos de precios al catálogo. Para asociar grupos de precios a un catálogo, en la sede de Commerce, vaya a **Retail y Commerce \> Catálogos y surtidos \> Todos los catálogos**. Entonces, en la pestaña **Catálogos**, debajo de **Precios**, Seleccione **Grupos de precios**. Todos los acuerdos comerciales, diarios de ajuste de precios y descuentos comerciales avanzados (umbral, cantidad y combinado) que se han vinculado al mismo grupo de precios se aplicarán cuando los clientes pidan del catálogo.

Para obtener más información acerca de los grupos de precios, vea [Grupos de precios](price-management.md#price-groups).

> [!NOTE]
> No puede crear un nuevo grupo de precios desde la página **Todos los catálogos**. En su lugar, debe crearlo desde la página **Todos los grupos de precios**. A continuación, debe asociarlo con el catálogo en la página **Todos los catálogos**.

#### <a name="associate-a-customer-hierarchy"></a>Asociar una jerarquía de clientes

Para asociar jerarquías de clientes en la sede de Commerce, vaya a **Retail y Commerce \> Catálogos y surtidos \> Todos los catálogos**. A continuación, en la pestaña **Catálogos**, debajo de **Jerarquía de clientes**, seleccione **Asignar jerarquías** para vincular una o más jerarquías de clientes al catálogo.

> [!NOTE]
> No puede crear una nueva jerarquía de clientes desde la página **Todos los catálogos**. En su lugar, debe crearla desde la página **Jerarquías de clientes**. A continuación, debe asociarlo con el catálogo en la página **Todos los catálogos**.

#### <a name="associate-default-dimension-attribute-group-for-refiners-such-as-size-style-and-color"></a>Asociar el grupo de atributos de dimensión predeterminado para refinadores como tamaño, estilo y color

Para asociar un grupo de atributos de dimensión predeterminado para refinadores, como tamaño, estilo y color, en la sede de Commerce, vaya a **Retail y Commerce \> Catálogos y surtidos \> Todos los catálogos**. Entonces, en la pestaña **Catálogos**, debajo de **Atributos**, Seleccione **Grupos de atributos**.

#### <a name="set-attribute-metadata"></a>Configurar metadatos de atributos

Para configurar metadatos de atributos, en la sede de Commerce, vaya a **Retail y Commerce \> Catálogos y surtidos \> Todos los catálogos**. Entonces, en la pestaña **Catálogos**, debajo de **Atributos**, configure **Metadatos de atributos**. Para seleccionar los atributos que deben ser visibles y refinables, seleccione una categoría en la jerarquía de navegación específica del catálogo asociado y, a continuación, en **Atributos del producto del catálogo**, seleccione un atributo. Entonces, seleccione **Mostrar atributo en el canal**. De forma predeterminada, todos los atributos visibles también se pueden buscar. ara hacer que los atributos se puedan refinar opcionalmente, seleccione **Se puede refinar**.

### <a name="validate-the-catalog"></a>Validación del catálogo

Antes de que un nuevo catálogo esté disponible para su uso, debe validarse y publicarse.

Para validar un catálogo, siga estos pasos.

1. En la pestaña **Catálogos** de la página **Todos los catálogos**, en **Validar** seleccione **Validar catálogo** para ejecutar una validación. Este paso es necesario. Validará que la configuración necesaria es precisa.
1. Seleccione **Ver resultados** para ver los detalles de la validación. Si se detectan errores, debe corregir los datos y luego volver a ejecutar la validación hasta que pase.

### <a name="approve-the-catalog"></a>Aprobar el catálogo

Después de que se valide un catálogo, debe aprobarse.

Para iniciar el flujo de trabajo de aprobación de catálogos, siga estos pasos.

1. En el panel de acciones de la página **Todos los catálogos**, selecione **Flujo de trabajo \> Enviar**.
1. Vaya a **Retail y Commerce \> Configuración de sede \> Flujos de trabajo de Commerce** para configurar los pasos y los usuarios autorizados para el flujo de trabajo. El flujo de trabajo definirá los pasos necesarios para obtener el catálogo en un estado **Aprobado**.

### <a name="publish-the-catalog"></a>Publique el catálogo

Después de que un catálogo está en un estado **Aprobado**, puede publicarlo seleccionando **Publicar** en el menú **Catálogos**. Una vez que el catálogo esté en un estado **Publicado**, se puede utilizar en la entrada de pedidos del centro de llamadas y enviar procesos del catálogo. Puede publicar un catálogo manualmente o mediante un proceso por lotes. La fecha de vigencia definida para el catálogo determina cuándo los productos estarán disponibles en la tienda en línea. La fecha de vencimiento definida determina cuándo los productos se quitarán de la tienda en línea.

> [!NOTE]
> Puede publicar un catálogo que contenga productos con advertencias. Sin embargo, dichos productos no aparecerán en la tienda en línea.

## <a name="additional-resources"></a>Recursos adicionales

[Impacto de extensibilidad de los catálogos de Commerce para personalizaciones B2B](catalogs-b2b-sites-dev.md)

[Catálogos comerciales para preguntas frecuentes B2B](catalogs-b2b-sites-FAQ.md)
