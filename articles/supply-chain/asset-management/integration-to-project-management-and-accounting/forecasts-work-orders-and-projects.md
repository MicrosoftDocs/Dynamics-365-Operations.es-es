---
title: Previsiones, órdenes de trabajo y proyectos
description: En este tema se explica la integración de previsiones y órdenes de trabajo con el módulo Administración de proyectos y contabilidad en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cc1992326c448ee8dc30a9ad8f8f538ebea83e54
ms.sourcegitcommit: f853c8d46ffc8e578387bac4cd48a948916983ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2019
ms.locfileid: "2002393"
---
# <a name="forecasts-work-orders-and-projects"></a>Previsiones, órdenes de trabajo y proyectos

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

En Administración de activos, la integración con el módulo **Administración de proyectos y contabilidad** ayuda a optimizar el control de costes para que los usuarios lleven un seguimiento de los costes en previsiones de tipo trabajo de mantenimiento y trabajos de órdenes de trabajo.

Para llevar el seguimiento de previsiones de tipo trabajo de mantenimiento, se deben establecer dos parámetros:

1. Seleccione un proyecto en **Administración de activos** > **Configuración** > **Parámetros de administración de activos** y, a continuación, en la pestaña **Activos** > en la ficha desplegable **Proyecto**, en el campo **Proyecto de previsión de mantenimiento**, seleccione un proyecto.

2. Cuando cree una línea predeterminada de tipo trabajo de mantenimiento, se crea automáticamente un número de actividad en la página **Valores predeterminados del tipo de trabajo de mantenimiento** (**Administración de activos** > **Configuración** > **Trabajos** > **Valores predeterminados del tipo de trabajo de mantenimiento**).

Las previsiones del tipo de trabajo de mantenimiento tienen dos propósitos: 

- Puede llevar un seguimiento de los costes en las previsiones del tipo de trabajo de mantenimiento en el módulo **Gestión y contabilidad de proyectos**. 
- Las previsiones se transfieren automáticamente a un proyecto de trabajo de orden de trabajo cuando selecciona un tipo de trabajo de mantenimiento en un trabajo de orden de trabajo.

Para llevar un seguimiento de los costes en trabajos de órdenes de trabajo, primero debe configurar los proyectos de las órdenes de trabajo. Para obtener más información, vea [Configuración de proyectos de órdenes de trabajo](../setup-for-work-orders/work-order-project-setup.md).

## <a name="work-order-job-projects"></a>Proyectos de trabajos de órdenes de trabajo

Al crear un trabajo de orden de trabajo en una orden de trabajo, el proyecto de orden de trabajo queda determinado por la configuración del proyecto principal para las órdenes de trabajo en la página **Configuración del proyecto de orden de trabajo** (**Administración de activos** > **Configuración** > **Órdenes de trabajo** > **Configuración del proyecto**).

Los proyectos de trabajos de órdenes de trabajo se crean mediante una combinación de la siguiente información de órdenes de trabajo:

- El tipo de orden de trabajo seleccionada en la orden de trabajo 
- La ubicación técnica relacionada con el activo en el trabajo de la orden de trabajo
- El tipo de activo relacionado con el activo en el trabajo de la orden de trabajo  
- Las horas de inicio y de finalización previstas establecidas en la orden de trabajo  

Parte de esta información puede que no se encuentre en una orden de trabajo. Por lo tanto, la búsqueda de un proyecto principal de orden de trabajo se realiza mediante la combinación disponible de datos y seleccionado el identificador de proyecto que se corresponda con los datos de la orden de trabajo.

Por ejemplo, en la siguiente ilustración, debido al modo que se configuró el tipo de activo **Motor de camión**, cada tarea de orden de trabajo que se crea con el tipo de activo **Motor de camión** será un subproyecto del identificador de proyecto 000186.

![Figura 1](media/01-integration-to-pma.png)

El propósito del identificador del proyecto en el trabajo de orden de trabajo y el número de actividad relacionado, es para llevar un seguimiento de los costes relacionados con el trabajo de la orden de trabajo y el activo seleccionada en el mismo, en el módulo **Gestión y contabilidad de proyectos**. Para ver el identificador y el número de actividad del proyecto, seleccione **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** y seleccione la orden de trabajo. En la ficha desplegable **Detalles de línea**, el campo **Id. de proyecto** muestra el identificador del proyecto y el campo **Número de actividad** muestra el número de actividad. Para obtener más información acerca del control de costes en Administración de activos, consulte [Control de costes y fechas](../controlling-and-reporting/cost-and-date-control.md).

La siguiente ilustración presenta una visión general gráfica de los proyectos de órdenes de trabajo y las actividades de proyecto relacionadas.

![Figura 2](media/02-integration-to-pma.png)

Cuando se crea un trabajo nuevo de orden de trabajo, se creará automáticamente un proyecto de orden de trabajo para el trabajo. Las dimensiones financieras para el activo relacionado con el trabajo de la orden de trabajo se transfieren automáticamente al proyecto de la orden de trabajo.

La actividad del proyecto que se crea para un trabajo de la orden de trabajo tiene información relacionada vinculada. Esta información es acerca del tipo de trabajo de mantenimiento, la variante del tipo de trabajo de mantenimiento y el comercio. Resulta útil si, por ejemplo, se crea un pedido de compra a partir de una orden de trabajo (consulte [Adquisición](../work-orders/procurement.md)) o si usa el módulo **Administración de proyectos y contabilidad** para el registro de horas.

Si el activo se ha instalado en una ubicación técnica, pero se instala más adelante en otra ubicación técnica diferente, las dimensiones financieras relacionadas con la nueva ubicación técnica se actualizan automáticamente en el activo. Posteriormente, cuando cree un trabajo de orden de trabajo para el activo, el proyecto de la orden de trabajo para el trabajo de la orden de trabajo obtiene automáticamente las dimensiones financieras que ahora están relacionadas con el activo. Por tanto, al usar ubicaciones técnicas, se puede llevar un seguimiento de los costes en las ubicaciones técnicas en las que se instaló un activo en un momento determinado. La actualización automática de las dimensiones financieras ayuda a garantizar una rastreabilidad completa de los costes para el control y generación de informes del proyecto.

## <a name="work-order-projects-work-order-lifecycle-states-project-stages-and-project-types"></a>Proyectos de órdenes de trabajo, estados del ciclo de vida de la orden de trabajo, etapas del proyecto y tipos de proyecto

Para ayudarle a garantizar que se usan los estados del ciclo de vida de la orden de trabajo y las etapas del proyecto relacionadas con órdenes de trabajo, tenga en cuenta las dependencias relativas al módulo **Administración de proyectos y contabilidad**:

- En el módulo **Administración de proyectos y contabilidad**, las etapas del proyecto se configuran según los tipos de proyecto en la página **Parámetros de administración de proyectos y contabilidad**.  
- En la página **Parámetros de administración de proyectos y contabilidad**, use las casillas de verificación para seleccionar las etapas relevantes para todos los tipos de proyecto que vaya a utilizar. En las siguientes ilustraciones, se han seleccionado cinco etapas (**Creado**, **Estimado**, **Programado**, **En proceso** y **Finalizado**) para los tipos de proyecto **Tiempo y material** e **Interno**. Estas cinco etapas son relevantes para los trabajos de mantenimiento interno y de mantenimiento del servicio.
- En el módulo **Administración de activos**, los grupos de proyectos definen los tipos de proyecto que configuró en la página **Configuración del proyecto de órdenes de trabajo** > pestaña **Grupo de proyectos** (**Administración de activos** > **Configuración** > **Órdenes de trabajo** > **Configuración de proyecto**).  
- Los grupos de proyectos configurados en la página **Configuración de proyecto de orden de trabajo** se usan cuando se crean órdenes de trabajo. Cuando se crea una orden de trabajo, se creará automáticamente un proyecto de orden de trabajo para la orden de trabajo.  
- Cada estado de ciclo de vida de la orden de trabajo debe tener una etapa de proyecto relacionada.  
- La etapa de proyecto relacionada con un estado de ciclo de vida de la orden de trabajo debe definirse como etapa activa para el grupo de proyecto definido en el proyecto de orden de trabajo. El proyecto de la orden de trabajo se crea automáticamente en una orden de trabajo.
- Al crear una orden de trabajo nueva, la asignación automática de un proyecto de orden de trabajo se basa en la configuración en la página **Configuración del proyecto de la orden de trabajo**.  

Las ilustraciones siguientes muestran las asociaciones entre los grupos de proyectos de órdenes de trabajo, los tipos de proyecto relacionados, las etapas de proyecto y los estados del ciclo de vida de la orden de trabajo.

![Figura 3](media/03-integration-to-pma.png)

![Figura 4](media/04-integration-to-pma.png)

![Figura 5](media/05-integration-to-pma.png)

Para obtener más información sobre cómo configurar tipos de órdenes de trabajo, consulte [Configuración de proyectos de órdenes de trabajo](../setup-for-work-orders/work-order-project-setup.md). Para obtener más información sobre cómo crear estados de ciclo de vida de órdenes de trabajo, consulte [Estados del ciclo de vida de la orden de trabajo](../setup-for-work-orders/work-order-lifecycle-states.md).

La ilustración siguiente muestra una visión general gráfica de los distintos proyectos creados en el módulo **Administración de activos** para habilitar la integración con el módulo **Gestión y contabilidad de proyectos**. También muestra a procesos de trabajo con que los proyectos están relacionados.

![Figura 6](media/06-integration-to-pma.png)

