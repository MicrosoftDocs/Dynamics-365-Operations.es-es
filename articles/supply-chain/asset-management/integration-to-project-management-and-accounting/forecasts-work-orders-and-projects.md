---
title: Previsiones, órdenes de trabajo y proyectos
description: En este tema se explica la integración de previsiones y órdenes de trabajo con el módulo Administración de proyectos y contabilidad en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/16/2019
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
ms.openlocfilehash: 5e986d139ac9d0a7729bb9787f05332bcc09f59b
ms.sourcegitcommit: 109a6ef2d20758dc4a25c51b11e22dd2214a1cc4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2019
ms.locfileid: "1886825"
---
# <a name="forecasts-work-orders-and-projects"></a>Previsiones, órdenes de trabajo y proyectos

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

En Administración de activos, la integración en el módulo **Administración de proyectos y contabilidad** se hace para optimizar el control de costes, lo que permite a los usuarios llevar un seguimiento de los costes en previsiones de tipo trabajo de mantenimiento y trabajos de órdenes de trabajo.

Para llevar el seguimiento de previsiones de tipo trabajo de mantenimiento, se deben establecer dos parámetros:

1. Seleccione un proyecto en el vínculo **Administración de activos** > **Configuración** > **Parámetros de administración de activos** > **Activos** > pestaña desplegable **Proyectos** > campo **Proyecto de previsión de mantenimiento**.

2. En **Valores predeterminados del tipo de trabajo de mantenimiento**, cuando crea una línea predeterminada de tipo de trabajo de mantenimiento, se crea automáticamente un número de actividad (**Administración de activos** > **Configuración** > **Trabajos** > **Valores predeterminados del tipo de trabajo de mantenimiento**).

Las previsiones del tipo de trabajo de mantenimiento se utilizan para dos cosas: puede llevar un seguimiento de los costes en previsiones del tipo de trabajo de mantenimiento en el módulo **Administración de proyectos y contabilidad**. Además, las previsiones se transfieren automáticamente a un proyecto de trabajo de orden de trabajo cuando selecciona un tipo de trabajo de mantenimiento en un trabajo de orden de trabajo.

Para llevar un seguimiento de los costes en trabajos de órdenes de trabajo, primero debe configurar los proyectos de las órdenes de trabajo. Consulte la sección [Configuración de proyectos de órdenes de trabajo](../setup-for-work-orders/work-order-project-setup.md) para ver una descripción del procedimiento.

## <a name="work-order-job-projects"></a>Proyectos de trabajos de órdenes de trabajo

Al crear un trabajo de orden de trabajo en una orden de trabajo, el proyecto de orden de trabajo queda determinado por la configuración del proyecto principal para los órdenes de trabajo en **Administración de activos** > **Configuración** > **Órdenes de trabajo** > **Configuración del proyecto**.

Los proyectos de trabajos de órdenes de trabajo se crean mediante una combinación de la siguiente información de órdenes de trabajo:

- El tipo de orden de trabajo seleccionada en la orden de trabajo 
- La ubicación técnica relacionada con el activo en el trabajo de la orden de trabajo
- El tipo de activo relacionado con el activo en el trabajo de la orden de trabajo  
- La hora de inicio y de finalización establecida en la orden de trabajo  

Es posible que no toda la información mencionada anteriormente se encuentre en una orden de trabajo. Por lo tanto, la búsqueda de un proyecto principal de orden de trabajo se realiza mediante la combinación disponible de datos y seleccionado el identificador de proyecto que se corresponda con los datos de la orden de trabajo.

Ejemplo: En la siguiente ilustración, la configuración del tipo de activo "Motor de cambión" significa que cada trabajo de la orden de trabajo creado con ese tipo de activo será un proyecto secundario del identificador de proyecto "000186".

![Figura 1](media/01-integration-to-pma.png)

El propósito del identificador del proyecto en el trabajo de la orden de trabajo y el número de actividad asociada (**Administración de activos** > **Común** > **Órdenes de trabajo** > **Todos los pedidos de trabajo** > seleccione la orden de trabajo en la lista > pestaña desplegable **Detalles de la línea** > campo **Identificador del proyecto** y campo **Número de actividad**) es llevar un seguimiento de los costes asociados al trabajo de la orden de trabajo y el activo seleccionado en el trabajo de la orden de trabajo, en el módulo **Administración de proyectos y contabilidad**. 

En la siguiente ilustración, se presenta una visión general gráfica de los proyectos de órdenes de trabajo y las actividades de proyecto relacionadas.

![Figura 2](media/02-integration-to-pma.png)

Cuando se crea un trabajo nuevo de orden de trabajo, se creará automáticamente un proyecto de orden de trabajo para el trabajo. Las dimensiones financieras para el activo relacionado con el trabajo de la orden de trabajo se transfieren automáticamente al proyecto de la orden de trabajo. La actividad de proyecto creada para un trabajo de orden de trabajo tiene información relacionada vinculada a ella con relación al tipo de trabajo de mantenimiento, la variante del tipo de trabajo de mantenimiento y la comercialización. Estos datos son útiles si, por ejemplo, se crea un pedido de compra a partir de una orden de trabajo (consulte [Adquisición](../work-orders/procurement.md)) o si usa el módulo **Administración de proyectos y contabilidad** para el registro de horas.  

Si el activo se ha instalado en una ubicación técnica y dicho activo se instala más adelante en otra ubicación técnica, las dimensiones financieras relacionadas con la nueva ubicación técnica se actualizan automáticamente en el activo. Posteriormente, cuando cree un trabajo de orden de trabajo para el activo, el proyecto de la orden de trabajo para el trabajo de la orden de trabajo obtiene automáticamente las dimensiones financieras que ahora están relacionadas con el activo. Esto significa que al usar ubicaciones técnicas, se puede llevar un seguimiento de los costes en las ubicaciones técnicas en las que se instaló un activo en un momento determinado. La actualización automática de las dimensiones financieras garantiza una rastreabilidad completa de los costes para el control y generación de informes del proyecto.  


## <a name="work-order-projects-work-order-lifecycle-states-project-stages-and-project-types"></a>Proyectos de órdenes de trabajo, estados del ciclo de vida de la orden de trabajo, etapas del proyecto y tipos de proyecto

Para garantizar el uso correcto de los estados del ciclo de vida de la orden de trabajo y las etapas del proyecto relacionadas con órdenes de trabajo, tenga en cuenta las dependencias relativas al módulo **Administración de proyectos y contabilidad**:

- En el módulo **Administración de proyectos y contabilidad**, las etapas del proyecto se configuran según los tipos de proyecto en **Parámetros de administración de proyectos y contabilidad**.  
- En **Parámetros de administración de proyectos y contabilidad**, recuerde seleccionar las casillas relevantes de la etapa de proyecto para todos los tipos de proyecto que vaya a utilizar. En la siguiente ilustración, se han seleccionado cinco etapas **Creado** - **Estimado** - **Programado** - **En proceso** - **Finalizado** para los tipos de proyecto "Tiempo y material" e "Interno". Estas cinco etapas son relevantes para los trabajos de mantenimiento interno y de mantenimiento del servicio.  
- En el **Administración de activos**, los tipos de proyecto los definen los grupos de proyectos que configuró en el formulario **Configuración de proyecto de orden de trabajo** > vínculo **Grupo de proyectos**.  
- Los grupos de proyectos configurados en **Configuración de proyecto de orden de trabajo** se usan cuando se crean órdenes de trabajo. Cuando se crea una orden de trabajo, se creará automáticamente un proyecto de orden de trabajo para la orden de trabajo.  
- Los estados de ciclo de vida de la orden de trabajo deben tener cada uno una etapa de proyecto relacionada.  
- La etapa de proyecto relacionada con un estado de ciclo de vida de la orden de trabajo debe definirse como etapa activa para el grupo de proyecto definido en el proyecto de orden de trabajo. El proyecto de la orden de trabajo se crea automáticamente en una orden de trabajo.  
- Al crear una orden de trabajo nueva, la asignación automática de un proyecto de orden de trabajo se basa en la configuración en **Configuración del proyecto de la orden de trabajo** (**Administración de activos** > **Configuración** > **Órdenes de trabajo** > **Configuración del proyecto**).  

Las asociaciones entre los grupos de proyectos de órdenes de trabajo, los tipos de proyecto relacionados, las etapas de proyecto y los estados del ciclo de vida de la orden de trabajo aparecen en las cifras a continuación.  

![Figura 3](media/03-integration-to-pma.png)

![Figura 4](media/04-integration-to-pma.png)

![Figura 5](media/05-integration-to-pma.png)

Consulte [Configuración de proyectos de órdenes de trabajo](../setup-for-work-orders/work-order-project-setup.md) acerca de cómo configurar proyectos de órdenes de trabajo y [Estados del ciclo de vida del pedido de trabajo](../setup-for-work-orders/work-order-lifecycle-states.md) respecto a cómo crear a estados del ciclo de vida de la orden de trabajo.

La ilustración siguiente muestra una visión general gráfica de los distintos proyectos creados en el módulo **Administración de activos** para permitir la integración con el módulo **Administración de proyectos y contabilidad**, así como los procesos laborales con los que los proyectos están relacionados.

![Figura 6](media/06-integration-to-pma.png)

