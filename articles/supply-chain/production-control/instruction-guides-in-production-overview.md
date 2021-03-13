---
title: Proporcionar guías de realidad mixta para trabajadores en producción
description: Este tema explica cómo integrar el módulo de gestión de producción en Microsoft Dynamics 365 Supply Chain Management con Dynamics 365 Guides.
author: cabeln
manager: tfehr
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkGuidesManufacturing
audience: Application User
ms.reviewer: kamaybac
ms.custom: 61943
ms.assetid: a3847f07-fca4-4140-a26f-d83c6ac68dde
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: cabeln
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.15
ms.openlocfilehash: 3e69f9007b6605a07c6bec189b596d36a26f6222
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007224"
---
# <a name="provide-mixed-reality-guides-for-workers-in-production"></a>Proporcionar guías de realidad mixta para trabajadores en producción

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Los trabajadores en los procesos de producción se beneficiarán de las instrucciones pertinentes que se brindan en el momento adecuado en el contexto de su trabajo. Hay *instrucciones* aplicables en varios dominios de trabajo, que incluyen: montaje, servicio, operaciones, certificación y seguridad. En todas estas funciones comerciales básicas, las instrucciones de capacitación continua pueden ayudar a capacitar a los trabajadores para que logren más y trabajen mejor.

## <a name="introduction"></a>Introducción

Puede proporcionar instrucciones de diferentes formas. Un sistema eficiente que se envía fuera de la caja utiliza [Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/).

Dynamics 365 Guides puede ayudar a capacitar a sus empleados con el aprendizaje práctico. Puede definir procesos estandarizados con instrucciones paso a paso que guíen a sus empleados hacia las herramientas y piezas que necesitan y les muestren cómo utilizar estas herramientas en situaciones de trabajo reales.

Puede adjuntar guías a varios aspectos del control de producción, que incluyen:

- [Recursos](#resources)
- [Grupos de recursos](#resource-groups)
- [Productos emitidos](#released-products)
- [Fórmulas ](#formulas)
- [Versiones de fórmula](#formula-versions)
- [Listas de materiales (LMAT)](#bom)
- [Versiones de listas de materiales](#bom-versions)
- [Rutas](#routes)
- [Versiones de ruta](#route-versions)
- [Relaciones de operación de ruta](#route-operation-relations)

> [!NOTE]
> También puede adjuntar guías con Administración de activos. Para obtener más información sobre esa opción, consulte [Integrar Dynamics 365 Supply Chain Management (Administración de activos) con Dynamics 365 Guides](../asset-management/asset-management-guides-integration.md).

Cuando un trabajador de primera línea elige un trabajo en el piso de producción a través de Supply Chain Management, el trabajador puede ver [las guías relevantes](#logic) en la tarjeta de trabajo. Cuando el trabajador elige una guía específica, se muestra un código QR para esa guía en la pantalla. El trabajador luego usa su HoloLens para escanear el código QR, que inicia Guías y muestra las instrucciones necesarias.

Las siguientes subsecciones describen algunos escenarios seleccionados en los que las empresas de todas las industrias pueden ver el mayor valor al usar Guías para presentar instrucciones para la fabricación.

### <a name="assembly"></a>Ensamblado

![Utilizar guías en tareas de montaje](media/instruction-guides-hero-assembly.png "Utilizar guías en tareas de servicio")

Las instrucciones en las operaciones de montaje muestran a los trabajadores las herramientas y piezas que necesitan y cómo utilizarlas en situaciones de trabajo reales.

Los gerentes de producción pueden crear y asignar guías, por ejemplo, para [rutas de producción](routes-operations.md), [relaciones de operación](routes-operations.md#operation-relations) o [listas de materiales](bill-of-material-bom.md). Los trabajadores encontrarán las instrucciones relevantes sobre la experiencia de operación respectiva en el piso de producción.

### <a name="service"></a>Servicio

![Utilizar guías en tareas de servicio](media/instruction-guides-hero-service.png "Utilizar guías en tareas de servicio")

Equipe a los técnicos con instrucciones guiadas en el lugar de trabajo, eliminando la necesidad de programar visitas adicionales.

Los gerentes de servicio pueden asignar guías, por ejemplo, a [productos](../../commerce/product.md) que recorren rutinas de evaluación de la calidad.

### <a name="quality"></a>Calidad

![Utilice guías en tareas de aseguramiento de la calidad](media/instruction-guides-hero-quality.png "Utilice guías en tareas de aseguramiento de la calidad")

Implemente nuevos procesos y garantice una mayor coherencia al convertir el conocimiento de los empleados en una herramienta repetible.

Los gerentes de control de calidad pueden asignar guías, por ejemplo, a [productos](../../commerce/product.md) que recorren rutinas de evaluación de la calidad.

### <a name="certifications"></a>Certificaciones

![Utilice guías para tareas relacionadas con la certificación](media/instruction-guides-hero-certification.png "Utilice guías para tareas relacionadas con la certificación")

Asegúrese de que cada empleado cumpla con altos estándares identificando rápidamente quién necesita ayuda y dónde.

### <a name="safety"></a>Seguridad

![Utilice guías en las instrucciones de seguridad laboral](media/instruction-guides-hero-safety.png "Utilice guías en las instrucciones de seguridad laboral")

Proporcione instrucciones que recorran los procedimientos peligrosos virtualmente antes de intentarlo en el entorno físico. Con un enfoque de realidad mixta, los trabajadores pueden experimentar procedimientos peligrosos de forma virtual.

Los gerentes de producción pueden proporcionar instrucciones de manejo dedicadas para el manejo de materiales peligrosos o procedimientos de manejo delicado al asignar instrucciones a [artículos del producto](../../commerce/product.md), [rutas](routes-operations.md) y [operaciones](routes-operations.md#operation-relations).

## <a name="get-started-with-instructions-and-guides"></a>Empiece con instrucciones y guías

Para habilitar las instrucciones en los procesos de producción, Supply Chain Management proporciona una integración lista para usar con Dynamics 365 Guides. Se requiere una instancia de aplicación instalada y con licencia de Guides para crear, mantener y asignar instrucciones de realidad mixta a los activos y el trabajo de producción.

### <a name="prerequisites"></a>Requisitos previos

Para utilizar esta función, su sistema debe incluir lo siguiente:

- Dynamics 365 Supply Chain Management versión 10.0.15 o posterior
- [Escritura dual](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write) para las aplicaciones de Supply Chain Management.
- [Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) versión 400.0.1.48 o posterior

### <a name="turn-on-the-feature"></a>Activar la característica

Para que la función esté disponible en su sistema, debe habilitar sus claves de configuración. Solo necesita hacer esto una vez. Para hacer esto, un administrador debe hacer lo siguiente:

1. Coloque su sistema en modo de mantenimiento como se describe en [Modo de mantenimiento](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Vaya a **Administración del sistema \> Configuración \> Configuración de licencias**.
1. Amplíe la sección **Realidad mixta** y luego seleccione la casilla **Guía de realidad mixta**.
1. Amplíe la sección **Gestión de producción** y luego seleccione la casilla **Instrucciones de producción**.
1. Desactive el modo de mantenimiento como se describe en [Modo de mantenimiento](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
  
## <a name="configure-how-guides-appear-on-the-shop-floor"></a>Configurar cómo aparecen las guías en el taller

Para configurar cómo aparecen las guías en el taller, vaya a **Realidad mixta \> Dynamics 365 Guides \> Configurar la integración de guías**.

![Configurar la integración de guías para la fabricación](media/instruction-guides-configure-integration.png "Configurar la integración de guías para la fabricación")

Establezca los campos siguientes:

- **URL de Microsoft Dataverse** - Especifique la URL del entorno Microsoft Dataverse en el que crea sus guías. El formato es "contoso.crm4.dynamics.com", donde la primera parte de la URL suele tener el nombre de su organización (como "contoso"), la segunda parte es específica de la región de datos de su entorno (como "crm4")., y la última parte es el dominio (como "dynamics.com"). Una forma de encontrar la URL correcta es ir a [home.dynamics.com](https://home.dynamics.com/) y luego abrir su aplicación Guides. Cuando se abra Guides, verá la URL en la barra de direcciones de su navegador (solo tome la URL base, que debería parecerse al ejemplo anterior). Este valor se utiliza para componer direcciones para sus guías y se codificará en los códigos QR.
- **Tamaño del código QR** - Establezca el tamaño del código QR renderizado. Recomendamos elegir un tamaño que llene la mayor parte de la pantalla, pero no más. Típicamente, *15* es un buen valor.
- **Nivel de corrección de errores del código QR** - Establecer la granularidad del código QR. Una mayor granularidad puede ayudar a aumentar la confiabilidad del código, pero su **Tamaño de código QR** debe ser lo suficientemente grande para admitir el nivel de detalle requerido por el nivel de corrección seleccionado.

> [!TIP]
> - Los tamaños de códigos QR que son demasiado grandes para su pantalla tardarán un poco más en renderizarse y luego se reducirán para adaptarse a su pantalla. Estos no proporcionan ningún beneficio.
> - Los tamaños de código QR que son demasiado pequeños pueden disminuir la capacidad de HoloLens para leer el código correctamente en algunos entornos.
> - Le recomendamos que pruebe la configuración de cada dispositivo que mostrará códigos QR para usuarios de HoloLens. Elija configuraciones que proporcionen suficiente legibilidad en el entorno de su taller.  

## <a name="get-an-overview-of-all-guide-assignments"></a>Obtenga una descripción general de todas las asignaciones de guías

Utilice la página **Todas las guías** para ver la lista de todas las Guías disponibles en su organización y todas las asignaciones a sus procesos y recursos de producción. Para abrirlo, vaya a **Realidad mixta \> Guías \> Todas las guías**. La lista en la parte superior muestra todas las guías disponibles y puede usar el campo aquí para filtrar la lista. La lista en la parte inferior muestra todas las asignaciones de la Guía y proporciona una barra de herramientas para administrarlas.

![Administrar guías](media/instruction-guides-allguides.png "Administrar guías")

Las siguientes secciones describen los tipos de objetos a los que puede asignar guías. Cada guía asignada proporciona instrucciones que se adjuntan automáticamente a los respectivos trabajos de producción y estarán disponibles en el taller.

## <a name="associate-a-guide-to-a-resource"></a><a name="resources"></a>Asociar una guía a un recurso

Agregar una guía a un [recurso](operations-resources.md) para ofrecer la Guía en el contexto de trabajos de producción relevantes.

### <a name="typical-scenario-using-resources"></a>Escenario típico con recursos

Por ejemplo, puede adjuntar una guía con seguridad general de la máquina o instrucciones de manejo a un recurso de tipo máquina. Luego, la Guía estará disponible en cada trabajo que se realice en la máquina.

### <a name="add-a-guide-to-a-resource"></a>Agregar una guía a un recurso

Para agregar una guía a un recurso:

1. Vaya a **Control de producción \> Configuración \> Recursos \> Capacidades de recursos**.
1. En el panel de lista, seleccione el recurso al que desea asignar una guía.
1. Amplíe la ficha desplegable **Guías asociadas**.
1. Seleccione **Añadir** desde la barra de herramientas **Guías asociadas**. Se agrega una nueva línea a la cuadrícula.
1. Para la nueva línea, use la lista desplegable en la columna **Nombre** para elegir la Guía que desea asignar. Si tiene una gran cantidad de guías, puede filtrar la lista para encontrar la que está buscando.
    ![Administrar guías](media/instruction-guides-allguides.png "Administrar guías")

## <a name="associate-a-guide-to-a-resource-group"></a><a name="resource-groups"></a>Asociar una guía a un grupo de recursos

Puede agregar una guía a [grupos de recursos](tasks/define-discrete-manufacturing-resource-group.md) si los usa para administrar grupos de máquinas, líneas de producción o celdas de trabajo.

### <a name="typical-scenarios-using-resource-groups"></a>Escenarios típicos con grupos de recursos

**Ejemplo 1:** Ha definido un grupo de recursos para varias máquinas del mismo modelo. En lugar de asignar la guía de instrucciones de manejo relevante para el modelo de máquina a cada recurso relevante, podría asignar la Guía al grupo de recursos que refleja ese modelo de máquina.

**Ejemplo 2:** Ha definido un grupo de recursos para una celda de trabajo que contiene diferentes máquinas y tiene una guía que proporciona instrucciones generales sobre cómo mantener la celda de trabajo. La Guía se aplica a cualquier actividad de producción en esta celda de trabajo.

### <a name="add-a-guide-to-a-resource-group"></a>Agregar una guía a un grupo de recursos

Para agregar una guía a un grupo de recursos:

1. Vaya a **Control de producción \> Configuración \> Recursos \> Grupos de recursos**.
1. En el panel de lista, seleccione el grupo de recursos al que desea asignar una guía.
1. Amplíe la ficha desplegable **Guías asociadas**.
1. Seleccione **Añadir** desde la barra de herramientas **Guías asociadas**. Se agrega una nueva línea a la cuadrícula.
1. Para la nueva línea, use la lista desplegable en la columna **Nombre** para elegir la Guía que desea asignar. Si tiene una gran cantidad de guías, puede filtrar la lista para encontrar la que está buscando.
    ![Agregar una guía a un grupo de recursos](media/instruction-guides-resourcegroup.png "Agregar una guía a un grupo de recursos")

## <a name="associate-a-guide-to-a-released-product"></a><a name="released-products"></a>Asociar una guía a un producto liberado

Puede agregar una guía a cualquier [producto lanzado](../pim/tasks/create-released-product-single-company.md).

### <a name="typical-scenario-using-released-products"></a>Escenario típico con productos lanzados

Las guías a nivel de producto ayudan a los trabajadores del taller con instrucciones relevantes para operar o manipular un producto o artículo específico liberado.

### <a name="add-a-guide-to-a-released-product"></a>Agregar una guía a un producto liberado

Para agregar una guía a un producto liberado:

1. Vaya a **Gestión de información de producción \> Productos \> Productos despachados**.
1. Abra el producto al que desea asignar una guía.
1. En el panel Acción, abra la pestaña **Ingeniero** y, desde el grupo **Ver**, seleccione **Guías asociadas**.
1. La página **Guías asociadas** se abre para el producto seleccionado.
1. En el Panel de acciones, seleccione **Agregar** para agregar una nueva línea a la cuadrícula. 
1. Para la nueva línea, use la lista desplegable en la columna **Nombre** para elegir la Guía que desea asignar.
    ![Agregar una guía a un producto liberado](media/instruction-guides-ReleasedProduct-AddGuides.png "Agregar una guía a un producto liberado")

## <a name="associate-a-guide-to-a-formula"></a><a name="formulas"></a>Asociar una guía a una fórmula

Puede agregar una guía a cualquier [fórmula](bill-of-material-bom.md#formulas-co-products-and-by-products).

### <a name="typical-scenario-using-formulas"></a>Escenario típico con fórmulas
  
Las guías a nivel de fórmula proporcionan a los trabajadores del taller instrucciones de manejo guiadas en el contexto de una fórmula o receta. Las guías también se pueden asignar a versiones de una fórmula.

> [!NOTE]
> Puede asignar una guía relevante para los procesos de producción basada en una fórmula a una ruta, versión de ruta o relaciones de operación de ruta.  

> Actualmente, las guías no se pueden adjuntar a líneas de fórmula individuales.

### <a name="add-a-guide-to-a-formula"></a>Agregar una guía a una fórmula

Para agregar una guía a una fórmula:

1. Vaya a **Gestión de información de producción \> Listas de materiales y fórmulas \> Fórmulas**.
1. Abra la fórmula a la que desea asignar una guía.
1. Abra la pestaña **Encabezamiento** encima de la pestaña desplegable superior.
1. Amplíe la ficha desplegable **Guías asociadas**.
1. Seleccione **Añadir** desde la barra de herramientas **Guías asociadas**. Se agrega una nueva línea a la cuadrícula.
1. Para la nueva línea, use la lista desplegable en la columna **Nombre** para elegir la Guía que desea asignar.
    ![Agregar una guía a una fórmula](media/instruction-guides-Formula.png "Agregar una guía a una fórmula")

## <a name="associate-a-guide-to-a-formula-version"></a><a name="formula-versions"></a>Asociar una guía a una versión de una fórmula

Puede agregar una guía a cualquier [versión de fórmula](bill-of-material-bom.md#bom-and-formula-versions).

### <a name="typical-scenario-using-formula-versions"></a>Escenario típico con versiones de fórmulas

Las guías adjuntas a una versión individual de una fórmula brindan a los trabajadores del taller instrucciones que explican la producción de esa versión de la receta de la fórmula.

> [!TIP]
> Puede asignar una guía relevante para los procesos de producción basada en esta versión de fórmula a una ruta, versión de ruta o relaciones de operación de ruta.  

> [!NOTE]
> Actualmente, las guías no se pueden adjuntar a líneas de fórmula individuales.

### <a name="add-a-guide-to-a-formula-version"></a>Agregar una guía a una versión de fórmula

Para agregar una guía a una versión de fórmula:

1. Vaya a **Gestión de información de producción \> Listas de materiales y fórmulas \> Fórmulas**.
1. Abra la fórmula que incluye una versión a la que desea asignar una guía.
1. Abra la pestaña **Encabezamiento** encima de la pestaña desplegable superior.
1. Sobre la ficha desplegable **Versiones de fórmulas**, seleccione la versión a la que desea asignar una guía.
1. Sobre la barra de herramientas **Versiones de fórmulas**, seleccione **Guías asociadas**.
    ![Abra las guías asociadas con una versión de fórmula seleccionada](media/instruction-guides-FormulaVersion.png "Abra las guías asociadas con una versión de fórmula seleccionada")
1. La página **Guías asociadas** se abre para la versión de fórmula.
1. En el Panel de acciones, seleccione **Agregar** para agregar una nueva línea a la cuadrícula. 
1. Para la nueva línea, use la lista desplegable en la columna **Nombre** para elegir la Guía que desea asignar.
    ![Agregar una guía a una versión de fórmula](media/instruction-guides-FormulaVersionAddGuide.png "Agregar una guía a una versión de fórmula")

## <a name="associate-a-guide-to-a-bill-of-materials"></a><a name="bom"></a>Asociar una guía a una lista de materiales

Puede agregar una guía a cualquier [lista de materiales](bill-of-material-bom.md) (LMAT).

### <a name="typical-scenario-using-bills-of-materials"></a>Escenario típico con listas de materiales

Las guías adjuntas a una lista de materiales proporcionan a los trabajadores del taller instrucciones que explican cómo preparar y manipular el material de una lista de materiales. Las guías también se pueden asignar a versiones de una LMAT.

> [!NOTE]
> Actualmente, las guías no se pueden adjuntar a líneas de LMAT individuales.

### <a name="add-a-guide-to-a-bill-of-materials"></a>Agregar una guía a una lista de materiales

Para agregar una guía a una lista de materiales:

1. Vaya a **Gestión de información de producción \> Listas de materiales y fórmulas \> Listas de materiales**.
1. Abra la lista de materiales al que desea asignar una guía.
1. Abra la pestaña **Encabezamiento** encima de la pestaña desplegable superior.
1. Amplíe la ficha desplegable **Guías asociadas**.
1. Seleccione **Añadir** desde la barra de herramientas **Guías asociadas**. Se agrega una nueva línea a la cuadrícula.
1. Para la nueva línea, use la lista desplegable en la columna **Nombre** para elegir la Guía que desea asignar.
    ![Agregar una guía a una LMAT](media/instruction-guides-BOM.png "Agregar una guía a una LMAT")

## <a name="associate-a-guide-to-a-bill-of-materials-version"></a><a name="bom-versions"></a>Asociar una guía a una versión de lista de materiales

Puede agregar una guía a cualquier [versión de lista de materiales](bill-of-material-bom.md#bom-and-formula-versions).

### <a name="typical-scenario-using-bill-of-materials-versions"></a>Escenario típico con versiones de listas de materiales

Las guías adjuntas a una versión individual de la lista de materiales brindan a los trabajadores del taller instrucciones que explican cómo preparar y manipular el material para una versión de una lista de materiales que es diferente de la lista de materiales genérica u otras versiones de la misma.

> [!NOTE]
> Actualmente, las guías no se pueden adjuntar a líneas de LMAT individuales.

### <a name="add-a-guide-to-a-bill-of-materials-version"></a>Agregar una guía a una versión de lista de materiales

Para agregar una guía a una versión de lista de materiales:

1. Vaya a **Gestión de información de producción \> Listas de materiales y fórmulas \> Listas de materiales**.
1. Abra la LMAT que incluye una versión a la que desea asignar una guía.
1. Abra la pestaña **Encabezamiento** encima de la pestaña desplegable superior.
1. Sobre la ficha desplegable **Versiones de LMAT**, seleccione la versión a la que desea asignar una guía.
1. Sobre la barra de herramientas **Versiones de LMAT**, seleccione **Guías asociadas**.
    ![Abra las guías asociadas con una versión de LMAT seleccionada](media/instruction-guides-BOMVersion.png "Abra las guías asociadas con una versión de LMAT seleccionada")
1. La página **Guías asociadas** se abre para la versión de LMAT.
1. En el Panel de acciones, seleccione **Agregar** para agregar una nueva línea a la cuadrícula.
1. Para la nueva línea, use la lista desplegable en la columna **Nombre** para elegir la Guía que desea asignar.
    ![Agregar una guía a una versión de LMAT](media/instruction-guides-BOMVersionAddGuide.png "Agregar una guía a una versión de LMAT")

## <a name="associate-a-guide-to-a-route"></a><a name="routes"></a>Asociar una guía a una ruta

Puede agregar una guía a cualquier [ruta](routes-operations.md).

### <a name="typical-scenario-using-routes"></a>Escenario típico con rutas

Las rutas se utilizan normalmente para especificar cómo se producirá un determinado producto publicado en función de una lista de materiales o una versión de lista de materiales y con un conjunto de recursos o grupos de recursos.

Asigne una guía a una ruta para proporcionar instrucciones paso a paso para el proceso de producción respectivo.

### <a name="add-a-guide-to-a-route"></a>Agregar una guía a una ruta

Para agregar una guía a una ruta:

1. Vaya a **Control de producción \> Todas las rutas**.
1. Abra la ruta a la que desea asignar una guía.
1. Amplíe la ficha desplegable **Guías asociadas**.
1. Seleccione **Añadir** desde la barra de herramientas **Guías asociadas**. Se agrega una nueva línea a la cuadrícula.
1. Para la nueva línea, use la lista desplegable en la columna **Nombre** para elegir la Guía que desea asignar.
    ![Agregar una guía a una ruta](media/instruction-guides-Route.png "Agregar una guía a una ruta")

## <a name="associate-a-guide-to-a-route-version"></a><a name="route-versions"></a>Asociar una guía a una versión de una ruta

Puede agregar una guía a cualquier [versión de ruta](routes-operations.md#route-versions).

### <a name="typical-scenario-using-route-versions"></a>Escenario típico con versiones de ruta

Las versiones de rutas se utilizan normalmente para especificar variantes de procesos de producción en función de una ruta existente. Puede asignar diferentes Guías a cada versión de ruta.

### <a name="add-a-guide-to-a-route-version"></a>Agregar una guía a una versión de ruta

Para agregar una guía a una versión de ruta:

1. Vaya a **Control de producción \> Todas las rutas**.
1. Abra la ruta a la que desea asignar una guía.
1. Sobre la ficha desplegable **Versiones**, seleccione la versión a la que desea asignar una guía.
1. Sobre la barra de herramientas **Versiones**, seleccione **Guías asociadas**.
    ![Abra las guías asociadas con una versión de ruta seleccionada](media/instruction-guides-RouteVersion.png "Abra las guías asociadas con una versión de ruta seleccionada")
1. La página **Guías asociadas** se abre para la versión de LMAT.
1. En el Panel de acciones, seleccione **Agregar** para agregar una nueva línea a la cuadrícula.
1. Para la nueva línea, use la lista desplegable en la columna **Nombre** para elegir la Guía que desea asignar.
    ![Agregar una guía a una versión de ruta](media/instruction-guides-RouteVersionAddGuide.png "Agregar una guía a una versión de ruta")

## <a name="associate-a-guide-to-a-route-operation-relation"></a><a name="route-operation-relations"></a>Asociar una guía a una relación de operación de ruta

Puede agregar una guía a cualquier [relación de operación de ruta](routes-operations.md#operation-relations).

### <a name="typical-scenario-using-route-operation-relations"></a>Escenario típico que usa relaciones de operación de ruta

Las relaciones de operación son la forma más específica de agregar orientación al proceso de un producto y sus operaciones relacionadas. Puede especificar una guía para cada operación en una ruta y especificar una guía diferente para cualquier tipo de contexto de relación especificado para una ruta, como para elementos específicos, configuraciones y más. También puede especificar a qué etapas de la operación se aplica la guía (como configuración, puesta en cola, proceso o transporte).

> [!NOTE]
> Si especifica guías para varias relaciones de operación de una ruta, entre esas guías, solo la guía de la relación más específica se mostrará en el piso de producción para el trabajo generado.

### <a name="add-a-guide-to-a-route-operation-relation"></a>Agregar una guía a una relación de operación de ruta

Para agregar una guía a una relación de operación de ruta:

1. Vaya a **Control de producción \> Todas las rutas**.
1. Abra la ruta a la que desea asignar una guía.
1. En el panel Acción, abra la pestaña **Ruta** y, desde el grupo **Mantener**, seleccione **Detalles de ruta**.
1. Se abre la página **Detalles de ruta** para la ruta seleccionada.
1. En la cuadrícula superior, seleccione la operación para la que desea proporcionar orientación.
1. En la cuadrícula inferior, seleccione una relación específica (o la relación genérica **Todos**).
    ![Seleccione una operación y luego una relación](media/instruction-guides-RouteOperationRelation.png "Seleccione una operación y luego una relación")
1. Encima de la cuadrícula inferior, abra la pestaña **Guías asociadas**. ![ La pestaña Guías asociadas](media/instruction-guides-RouteOperationRelation-AddGuide.png "La pestaña Guías asociadas")
1. Seleccione **Añadir** en la barra de herramientas en la parte superior de la cuadrícula inferior para agregar una nueva línea a la cuadrícula.
1. Para la nueva fila, use la lista desplegable en la columna **Nombre** para elegir la Guía que desea asignar. En el resto de la fila, seleccione la casilla de verificación para cada contexto donde la Guía seleccionada debería estar disponible.

> [!NOTE]
> Puede agregar una o más guías para cada etapa de cada operación.

## <a name="select-guides-from-the-shop-floor-execution-interface"></a>Seleccionar guías de la interfaz de ejecución de la planta

Cuando un trabajador abre una lista de trabajos en la interfaz de ejecución de la planta, Supply Chain Management encuentra las guías relevantes para los trabajos que se muestran. Utilice el botón **Guías** para ver las guías relevantes.

![Botón Guías en la interfaz de ejecución de la planta](media/instruction-guides-Shopfloor1.png "Botón Guías en la interfaz de ejecución de la planta")

Entonces coloque un HoloLens y acceda a la guía respectiva echando un vistazo al código QR y activando la Guía respectiva.

![Código QR para acceder a las guías mediante un HoloLens](media/instruction-guides-Shopfloor2.png "Código QR para acceder a las guías mediante un HoloLens")

## <a name="resolving-the-logic-for-selecting-guides"></a><a name="logic"></a>Resolver la lógica para seleccionar guías

Puede agregar guías a los siguientes datos de producción:

- [Recursos](#resources)
- [Grupos de recursos](#resource-groups)
- [Productos emitidos](#released-products)
- [Fórmulas ](#formulas)
- [Versiones de fórmula](#formula-versions)
- [Listas de materiales (LMAT)](#bom)
- [Versiones de listas de materiales](#bom-versions)
- [Rutas](#routes)
- [Versiones de ruta](#route-versions)
- [Relaciones de operación de ruta](#route-operation-relations)

Cuando Supply Chain Management genera los trabajos para el piso de producción, recopilará las Guías relevantes de esas fuentes. Tome nota de las siguientes reglas importantes.

- Si adjunta una versión de lista de materiales o una versión de fórmula a una ruta u orden de producción, las guías adjuntas a esta versión, y también las guías adjuntas a la lista de materiales principal o fórmula de esa versión, se mostrarán en el trabajo.
- Si adjunta una versión de ruta a una orden de producción, las guías adjuntas a esta versión, y también las guías adjuntas a la ruta principal de esa versión, se mostrarán en el trabajo.
- Si define varias relaciones de operación de ruta que incluyen la relación *Todos* y asignar Guías a esos, solo se mostrarán las Guías de la relación más específica para el trabajo.  

![Diagrama de resolución de las Guías relevantes](media/instruction-guides-Resolve.png "Diagrama de resolución de las Guías relevantes")
