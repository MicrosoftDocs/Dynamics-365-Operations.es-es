---
title: Visión general de la configuración de almacén
description: Este artículo explica cómo configurar un almacén. Incluye información acerca de cómo habilitar un diseño de almacén y procesos de almacén.
author: perlynne
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation, WHSLocation, WHSLocationBuild, WHSLocationProfile, WHSLocationType, WHSLocDirTable, WHSParameters, WHSWaveTemplateTable, WHSWorkPool, WHSWorkTemplateTable, WHSZone, WHSZoneGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 11554
ms.assetid: 262b7b88-2cce-44f7-9a5b-77c12af1be20
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a8cd436f1b8324335cc39ce54344db834dddebc9
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204617"
---
# <a name="warehouse-configuration-overview"></a>Visión general de la configuración de almacén

[!include [banner](../includes/banner.md)]

Este artículo explica cómo configurar un almacén. Incluye información acerca de cómo habilitar un diseño de almacén y procesos de almacén.

> [!NOTE]
> Este artículo se aplica a las características del módulo **Administración de almacenes** (almacenamiento avanzado). No se aplica a las características de almacenes del módulo **Administración del inventario**.

## <a name="warehouse-layout"></a>Diseño de almacén
El sistema Administración de almacenes de Supply Chain Management le proporciona maneras flexibles de definir el diseño del almacén para satisfacer las necesidades cambiantes, de manera que pueda lograr una eficacia óptima del almacén.

-   Puede establecer áreas de almacenamiento de alta y baja prioridad para la ubicación óptima de las mercancías.
-   Puede dividir el almacén en zonas para acomodar distintas necesidades de almacenamiento, como los requisitos de temperatura, o las diferentes tasas de facturación para los artículos.
-   Puede especificar ubicaciones de almacén en cualquier nivel (por ejemplo, un sitio, almacén, pasillo, estantería, balda y posición en hueco).
-   Puede agrupar las ubicaciones mediante la configuración de restricciones de capacidad física.
-   Puede controlar la manera en que se almacenan y se seleccionan los artículos, en función de las reglas definidas por consultas.

Para usar la administración de almacenes en Supply Chain Management, debe crear un almacén y habilitarlo para actividades de gestión de almacenes más avanzadas o especializadas. En la página **Almacenes**, seleccione la opción **Usar procesos de gestión de almacenes**.

### <a name="zone-groups-zones-location-types-and-locations"></a>Grupos de zona, zonas, tipos de ubicación y ubicaciones

Como parte del proceso de habilitación de una configuración de almacén, debe definir grupos de zonas de almacén y zonas, perfiles de ubicación, tipos de ubicación y ubicaciones.

-   **Grupos de zonas**: agrupación lógica o física de zonas dentro de un almacén.
-   **Zonas**: agrupación lógica o física de ubicaciones dentro de un almacén.
-   **Perfiles de ubicación**: agrupación lógica o física de ubicaciones con las mismas directivas de proceso de ubicación de almacén (por ejemplo, se puede almacenar allí una combinación de diferentes números de artículo y se aplican las mismas restricciones físicas de capacidad).
-   **Tipos de ubicaciones**: agrupación lógica o física de las ubicaciones de almacén. Por ejemplo, puede crear un tipo de ubicación para todas las ubicaciones provisionales. La configuración obligatoria de la página **Parámetros de gestión de almacenes** dirige el proceso de la definición de tipos de ubicación provisional y el tipo final de ubicación de envío.
-   **Ubicaciones**: el nivel más bajo de la información de la ubicación. Las ubicaciones se usan para realizar un seguimiento de dónde se almacena el inventario disponible y se selecciona en un almacén.

Las entidades que crea para definir el diseño del almacén se usan en las consultas que configura en las plantillas de trabajo para manejar los pedidos de trabajo en el almacén. Por lo tanto, al definir las zonas, los tipos de ubicación, etc., piense en cómo se usan diferentes áreas del almacén para distintos procesos. Además, considere factores como las características físicas de un área concreta. Por ejemplo, puede haber áreas donde solo puede usar un tipo determinado de elevador de carga. O bien, si su empresa tiene tanto la producción como los productos terminados dentro de la misma instalación, puede que desee crear un único almacén en Supply Chain Management pero separar entonces las dos operaciones creando dos grupos de zona. Asigne nombres descriptivos a las entidades, de manera que resulte sencillo identificarlas cuando las use en consultas de plantillas.

### <a name="location-stocking-limits-location-profiles-and-fixed-picking-locations"></a>Límites de existencias de la ubicación, perfiles de ubicación y ubicaciones de picking fijas

Debe tener en cuenta el diseño físico del almacén, tanto para determinar las capacidades de almacenamiento (límites de existencias de la ubicación y perfiles de ubicación) y como parte de sus intentos de lograr procesos óptimos de almacén. 

Los límites de existencias en la ubicación ayudan a garantizar que no se cree trabajo para solicitar colocar inventario en una ubicación que no tiene capacidad física para incluir el inventario. Por ejemplo, si algunas ubicaciones dentro de un almacén pueden contener un pallet por ubicación, se pueden habilitar límites de existencias de la ubicación. El valor de **Cantidad** se puede establecer en **1** y el valor de **Unidad** se puede establecer en **Pérdidas y ganancias** dentro de una agrupación de perfil específica. 

Si se requieren cálculos más avanzados para controlar las restricciones de capacidad de ubicación, se puede usar la configuración del perfil de ubicación. En este caso, se consideran el peso y el volumen cuando se realizan los cálculos de la capacidad. 

Para lograr procesos de salida óptimos, debe evaluar si se deben usar ubicaciones de picking fijas y/o ubicaciones de embalaje. A menudo, el reabastecimiento mínimo o máximo se usa para los procesos de reabastecimiento desde un área de almacenaje a las ubicaciones de picking fijas y se pueden habilitar múltiples ubicaciones de picking fijas dentro del mismo almacén y para variantes de producto. Considere la flexibilidad que se puede lograr habilitando las ubicaciones de desbordamiento de reabastecimiento de demanda dedicadas que se usan únicamente para el procesamiento de reabastecimiento de oleada/carga.

### <a name="location-setup-wizard"></a>Asistente para la configuración de ubicaciones

Para crear rápidamente las ubicaciones dentro de un almacén, puede usar el **Asistente para la configuración de ubicaciones**. Como parte de este proceso, puede mantener con facilidad el formato de los nombres de ubicaciones.

## <a name="warehouse-processes"></a>Procesos de almacén
Como parte de la configuración del almacén, es importante que se habiliten procesos de almacén de acuerdo con requisitos empresariales. Los componentes más importantes que debe configurar son plantillas de oleada, plantillas de trabajo, grupos de trabajo y directivas de ubicación.

### <a name="wave-templates"></a>Plantillas de oleada

Las plantillas de oleada ayudan a habilitar el proceso "Liberar al almacén". En cuanto se liberan las líneas de pedido (directamente desde documentos de origen, mediante procesos de trabajo por lotes o mediante las cargas que ya se han creado), se usa la funcionalidad de la plantilla de oleada. 

Puede crear tres tipos de plantillas de oleada: 
-   **Envío**
-   **Pedido de producción**
-   **Kanban** 

Los parámetros se usan para definir cómo de lejos debería llegar el sistema en el procesamiento del trabajo de salida. Una plantilla de oleada se selecciona según la secuencia de la plantilla de oleada y los criterios que se especifican en la plantilla. Si se muestra una plantilla en la parte superior de la secuencia, se comprueban primero los criterios en esa plantilla. Si se puede cumplir los criterios, se procesa la plantilla de oleada. De lo contrario, se comprueban los criterios de la plantilla siguiente, y así sucesivamente. Por lo tanto, es buena idea colocar la plantilla con los criterios más específico en la parte superior de la lista de secuencias de plantillas de oleada, de modo que se procese primero. Por ejemplo, desea procesar todo el trabajo para un transportista específico hoy y retrasa temporalmente el procesamiento del trabajo para otros transportistas. En este caso, la plantilla de oleada que selecciona el trabajo para ese transportista se debe mostrar antes que otras plantillas en la secuencia. De lo contrario, el trabajo para otros transportistas se podría procesar antes de que se complete el trabajo para ese transportista. 

Debe especificar los métodos de proceso de oleada en cada plantilla de oleada. Los métodos disponibles varían, en función del de plantilla de oleada.

### <a name="work-templates"></a>Plantillas de trabajo

Las definiciones de plantilla de trabajo desempeñan un papel importante en la definición de los procesos de trabajo de la gestión de almacenes. Definen qué trabajo se realiza y cómo se realiza. Las plantillas también pueden contener un código de directiva que vincula a un directiva de ubicación para determinar dónde se realiza el trabajo. Las plantillas de trabajo incluyen una consulta que especifica los criterios para el trabajo. Cada plantilla debe incluir al menos una operación de recogida y una operación de colocación para llevar la operación de trabajo básica de transferencia del inventario disponible de una ubicación a otra. 

Si varios trabajadores deben poder procesar el trabajo para algunas de las operaciones de almacén, puede que desee usar el concepto de *etapas* para el inventario y separar la ejecución del trabajo en diferentes clases de trabajo.

### <a name="work-pools"></a>Grupos de trabajo

Los grupos de trabajo se usan para organizar el trabajo en grupos. Por ejemplo, puede crear un grupo de trabajo para clasificar el trabajo que se produce en una ubicación concreta de almacén. Para todos los tipos de trabajo excepto la contabilidad, puede asignar un grupo de trabajo a una plantilla de trabajo. Para el recuento cíclico, puede asignar un grupo de trabajo en las siguientes páginas:

-   Planes de recuento cíclico
-   Umbrales de recuento cíclico
-   Trabajo de recuento cíclico por ubicación
-   Trabajo de recuento cíclico por artículo

Al usar plantillas de trabajo para crear el trabajo, el grupo de trabajo se asigna automáticamente al trabajo. 

Los id. del grupo de trabajo también se pueden usar para limitar el tipo de trabajo que se dirige a un trabajador concreto del almacén, siempre que esta función se configure en el artículo de menú del dispositivo móvil pertinente.

### <a name="location-directives"></a>Directivas de ubicación

Como el nombre sugiere, las directivas de ubicación se usan para dirigir las transacciones de trabajo a las ubicaciones adecuadas del almacén. Es decir, definen dónde realizar el picking y la ubicación. 

Para facilitar y agilizar la definición de las acciones asociadas con cada línea de directiva de ubicación, use una de las estrategias predefinidas. Por ejemplo, puede usar la estrategia **Ubicación vacía sin trabajo entrante** para buscar las ubicaciones libres de un almacén, o puede usar la estrategia **Reserva de lote de FEFO** para el picking de ventas salientes.

<a name="additional-resources"></a>Recursos adicionales
--------

[Configurar ubicaciones en un almacén con WMS](tasks/configure-locations-wms-enabled-warehouse.md)



