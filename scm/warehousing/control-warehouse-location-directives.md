---
title: "Controlar el trabajo de almacén usando plantillas de trabajo y directivas de ubicación"
description: "Este artículo describe cómo usar plantillas de trabajo y directivas de ubicación para determinar cómo y dónde se realiza el trabajo en el almacén."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSLocDirFailure, WHSLocDirHint, WHSLocDirTable, WHSLocDirTableUOM, WHSRFMenuItem, WHSWork, WHSWorkClass, WHSWorkPool, WHSWorkTemplateTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 72921
ms.assetid: 377ab8af-5b0c-4b5e-a387-06ac1e1820c0
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: f8bcdcf70089aaed06ba0f88cdbec8dfdf9121d1
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017

---

# <a name="control-warehouse-work-by-using-work-templates-and-location-directives"></a>Controlar el trabajo de almacén usando plantillas de trabajo y directivas de ubicación

[!include[banner](../includes/banner.md)]


Este artículo describe cómo usar plantillas de trabajo y directivas de ubicación para determinar cómo y dónde se realiza el trabajo en el almacén.

Las instrucciones que los trabajadores de almacén reciben en un dispositivo móvil están determinadas por las plantillas de trabajo que se configuran en Microsoft Dynamics 365 for Finance and Operations para definir los distintos procesos y tareas de almacén. Las plantillas de trabajo determinan cómo se realiza el trabajo para cada proceso de almacén. Si vincula un directorio de ubicación a plantillas de trabajo, puede ayudar a garantizar que el trabajo se produce en áreas físicas específicas de los almacenes.

## <a name="work-templates"></a>Plantillas de trabajo
La página **Plantillas de trabajo** le permite definir las operaciones de trabajo que se deben realizar en el almacén. Normalmente, las operaciones de trabajo del almacén constan de un par de acciones: un trabajador de almacén recoge inventario disponible en una ubicación y después pone el inventario seleccionado en otra ubicación. 

Las plantillas de trabajo constan de un encabezado y las líneas asociadas. Cada plantilla de trabajo es para un determinado *tipo de pedido de trabajo*. Muchos tipos de pedido de trabajo están asociados con los documentos de origen, como pedidos de ventas o compras. Sin embargo, otros tipos de pedido de trabajo representan procesos independientes de almacén, como recuento cíclico. El *id. del grupo de trabajo* le permite organizar el trabajo en grupos. 

Los ajustes en la definición del encabezado del trabajo se pueden usar para determinar cuándo se debe crear un nuevo elemento de trabajo. Por ejemplo, puede establecer un número máximo de líneas de selcción y un máximo previsto de tiempo de selección. Luego, si el trabajo para un proceso de selección de un pedido de ventas supera cualquiera de estos valores, el trabajo se divide en dos partes. 

Las líneas de trabajo representan las tareas físicas que son necesarias para procesar el trabajo. Por ejemplo, para un proceso de salida de almacén, puede haber una línea de trabajo para seleccionar los artículos dentro del almacén y otra línea para configurar dichos artículos en una zona de espera. Después, puede haber una línea adicional para seleccionar los artículos provisionales de la zona de espera, y otra línea para poner los artículos en un camión como parte del proceso de carga. Puede establecer unn *código directivo* en líneas de la plantilla de trabajo. Un código directivo está vinculado a una ubicación directiva y, por tanto, ayuda a garantizan que el trabajo del almacén se ha procesado en la ubicación correcta en el almacén. 

Puede configurar una consulta para controlar si se usa una determinada plantilla de trabajo. Por ejemplo, puede establecer una limitación para poder utilizar una determinada plantilla solo para el trabajo en un almacén específico. Como alternativa, puede tener varias plantillas que se usan para crear el trabajo para procesar pedidos de venta salientes, en función del origen de venta. El sistema usa el campo **Número de secuencia** para determinar el orden en que las plantillas de trabajo disponibles son evaluadas. Por lo tanto, si tiene una consulta muy específica para una determinada plantilla de trabajo, debe darle un número de secuencia bajo. Dicha consulta se evaluará antes que otras consultas más generales. 

Para detener o poner en pausa un proceso de trabajo, puede usar la configuración **Detener trabajo** en la línea de trabajo. En ese caso, no se le solicitará al trabajador que se está realizando el trabajo que realice la siguiente etapa de trabajo. Para pasar al siguiente paso, dicho trabajador u otro trabajador debe seleccionar el trabajo de nuevo. También puede separar las tareas dentro de un elemento de trabajo mediante un *id. de clase de trabajo* diferente en las líneas de la plantilla de trabajo.

## <a name="location-directives"></a>Directivas de ubicación
Las directivas de ubicación son reglas que ayudan a identifica las ubicaciones de picking y de colocación para el movimiento de inventario. Por ejemplo, en una transacción de pedido de ventas, una directiva de ubicación determina dónde se hará el picking de los artículos y dónde se colocarán los artículos seleccionados. Los directorios de la ubicación constan de un encabezado y las líneas asociadas, y se crean en la página **Directorios de ubicación**. 

En el encabezado, cada directorio de ubicación se debe asociar a un *tipo de pedido de trabajo* que especifica el tipo de transacción de inventario para el cual el directorio se usará, como pedidos de ventas, reabastecimiento o selección de la materia prima. El *tipo de trabajo* especifica si el directorio de la ubicación se usará para seleccionar o colocar el trabajo, o para otro proceso de almacén, como cómputo o cambios de estado del inventario. También debe especificar un *sitio* y un *almacén*. Un *código directivo* que se especifica en el encabezado se puede usar para vincular el directorio de la ubicación a una o varias plantillas de trabajo. 

En cuanto a plantillas de trabajo, puede configurar una consulta para determinar cuándo se usa un directorio concreto de la ubicación. Por ejemplo, puede especificar que cuando el comercio electrónico es el origen de un pedido de ventas, el inventario se debe seleccionar en un área dedicada en el almacén. El sistema usa el campo **Número de secuencia** para determinar el orden en que las directivas disponibles de la ubicación son evaluadas. 

Las líneas directivas de la ubicación establecen restricciones adicionales en la aplicación de las reglas de búsqueda de la ubicación. Puede especificar una cantidad mínima y una cantidad máxima en las que el directorio se debe basar, y puede especificar que el directorio debe ser para una unidad de inventario específica. Por ejemplo, si la unidad de medida es pallets, entonces los artículos en pallets se pueden colocar en una ubicación concreta. También puede especificar si la cantidad se puede dividir entre varias ubicaciones. Como el encabezado de la directiva de ubicación, cada línea directiva de la ubicación tiene un número de secuencia que determina la orden en que las líneas se evalúan. 

Las directivas de la ubicación tienen un nivel de detalle adicional: *acciones de la directiva de la ubicación*. Puede definir varias acciones de las directivas de la ubicación para cada línea. De nuevo, se usa un número de secuencia para determinar el orden en que se evalúan las acciones. En este nivel, puede configurar una consulta para definir cómo encontrar la mejor ubicación en el almacén. También puede usar una configuración de **Estrategia** predefinida para encontrar una ubicación óptima.

### <a name="example-of-the-use-of-location-directives"></a>Ejemplo del uso de las directivas de la ubicación

En este ejemplo, consideraremos un proceso de pedido de compra en el que la directiva de la ubicación debe encontrar capacidad libre dentro de un almacén para los artículos de inventario que acaban de registrarse en el muelle de recepción. Primero, queremos intentar encontrar capacidad libre dentro del almacén consolidando con la existencia de inventario disponible. Si la consolidación no es posible, intentaremos encontrar una ubicación vacía. 

Para esta situación, debemos definir dos acciones de la directiva de la ubicación. La primera acción de la secuencia debe ser usar la estrategia **Consolidar**, y la segunda debería ser la estrategia **Vaciar la ubicación sin trabajo entrante**. A menos que definamos una tercera acción para gestionar una situación de desbordamiento, dos resultados son posibles si no hay capacidad en el almacén: el trabajo puede ser creado aunque no se define ninguna ubicación o el proceso de creación de trabajo puede fallar. El resultado viene determinado por la configuración en la página **Fallos de la directiva de la ubicación**, donde puede decidir si seleccionar la opción **Detener trabajo si falla la directiva de la ubicación** para cada tipo de pedido de trabajo.




