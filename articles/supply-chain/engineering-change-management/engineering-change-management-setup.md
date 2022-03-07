---
title: Establecer valores comunes para la gestión de cambios de ingeniería
description: Este tema describe cómo establecer valores comunes que se utilizan para los parámetros en varias partes de la gestión de cambios de ingeniería.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgProductParameters, EngChgEcmSeverityTable, EngChgEcmSeverityRuleSet, EngChgEcmSeverityLookup,EngChgEcmSeverityChart,EngChgEcmRequestSeverityChart,EngChgEcmPriorityTable, EngChgEcmPriorityLookup, EngChgEcmPriorityChart, EngChgEcmMaterialDisposition, EngChgEcmEH
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 86de050ef4110e3485a77099440f3402e46cc498
ms.sourcegitcommit: 5f21cfde36c43887ec209bba4a12b830a1746fcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2020
ms.locfileid: "4437307"
---
# <a name="establish-common-values-for-engineering-change-management"></a>Establecer valores comunes para la gestión de cambios de ingeniería

[!include [banner](../includes/banner.md)]

Cuando configura la administración de cambios de ingeniería, debe establecer varias colecciones de valores que se utilizarán para completar listas desplegables en otras partes de la interfaz de usuario (UI). Debe especificar estos valores de acuerdo con los tipos de productos que produce y sus necesidades comerciales específicas.

## <a name="engineering-change-categories"></a>Categoría de cambio de ingeniería

Utiliza categorías de cambio de ingeniería para organizar sus órdenes de cambio de ingeniería, de modo que sean más fáciles de administrar y revisar. Por ejemplo, puede resultarle útil configurar un flujo de trabajo en el que, según la categoría, un departamento específico deba revisar los cambios propuestos. Por lo tanto, la orden de cambio de ingeniería incluye un campo **Categoría**.

Para establecer la colección de categorías de cambios de ingeniería que se utilizan en su empresa, vaya a **Gestión de cambios de ingeniería \> Preparar \> Gestión de cambios de ingeniería \> Categorías de cambio de ingeniería**. Luego, puede usar los botones en el Panel de acciones para agregar, eliminar y editar valores, y para organizarlos en el orden en el que deben aparecer en las listas desplegables donde se muestran.

## <a name="engineering-change-priorities"></a>Prioridades de cambio de ingeniería

Utiliza las prioridades de cambio de ingeniería para indicar la importancia o urgencia de una orden de cambio de ingeniería. Pueden ayudarlo a realizar un seguimiento de la importancia de una orden de cambio de ingeniería, de modo que pueda identificar fácilmente qué órdenes deben procesarse primero y con qué rapidez.

Para establecer la colección de prioridades de cambios de ingeniería que se utilizan en su empresa, vaya a **Gestión de cambios de ingeniería \> Preparar \> Gestión de cambios de ingeniería \> Prioridades de cambio de ingeniería**. Luego, puede usar los botones en el Panel de acciones para agregar, eliminar y editar valores, y para organizarlos en el orden en el que deben aparecer en las listas desplegables donde se muestran.

## <a name="engineering-change-reasons"></a>Motivos del cambio de ingeniería

Las razones del cambio de ingeniería indican la causa o la naturaleza del cambio en la orden de cambio.

Para establecer la colección de razones de cambios de ingeniería que se utilizan en su empresa, vaya a **Gestión de cambios de ingeniería \> Preparar \> Gestión de cambios de ingeniería \> Razones de cambio de ingeniería**. Luego, puede usar los botones en el Panel de acciones para agregar, eliminar y editar valores, y para organizarlos en el orden en el que deben aparecer en las listas desplegables donde se muestran.

## <a name="material-disposal-codes"></a>Códigos de eliminación de material

Utiliza códigos de eliminación de materiales para clasificar los materiales que se utilizan en sus productos terminados o los componentes que deben eliminarse de una manera específica o que requieren algún tratamiento antes de que puedan agregarse a su basura habitual. Cuando agrega un producto relevante a una orden de cambio de ingeniería, puede asignar un código de eliminación como parte de los detalles del cambio.

Para establecer la colección de códigos de disposición de material que se utilizan en su empresa, vaya a **Gestión de cambios de ingeniería \> Preparar \> Gestión de cambios de ingeniería \> Códigos de disposición de material**. Luego, puede usar los botones en el Panel de acciones para agregar, eliminar y editar valores, y para organizarlos en el orden en el que deben aparecer en las listas desplegables donde se muestran.

## <a name="received-customer-approval"></a>Aprobación del cliente recibida

Cuando diseña productos para un cliente específico, el diseño y las especificaciones a menudo deben validarse antes de que el producto pueda configurarse como listo. El campo **Recibió la aprobación del cliente** le permite indicar qué tan avanzado se encuentra el producto en el proceso de aprobación del cliente y / o si se ha recibido la aprobación.

Para establecer la colección de valores de aprobación de cliente recibidos que se utilizan en su empresa, vaya a **Gestión de cambios de ingeniería \> Preparar \> Gestión de cambios de ingeniería \> Aprobación de cliente recibida**. Luego, puede usar los botones en el Panel de acciones para agregar, eliminar y editar valores, y para organizarlos en el orden en el que deben aparecer en las listas desplegables donde se muestran.

## <a name="engineering-change--environmental-health-and-safety-codes"></a>Cambio de ingeniería: códigos de seguridad y salud ambiental

Si en la fabricación de un producto se debe tener en cuenta alguna reglamentación estándar de salud y seguridad ambiental, o reglamentación o procedimiento específico de la empresa, puede utilizar los códigos de salud y seguridad ambiental para definirla. En la orden de cambio de ingeniería, puede indicar qué códigos se aplican a la fabricación de un producto mientras edita los detalles del producto afectado.

Para establecer la colección de valores de salud y seguridad que se utilizan en su empresa, vaya a **Gestión de cambios de ingeniería \> Preparar \> Gestión de cambios de ingeniería \> Códigos de salud y seguridad medioambientales**. Luego, puede usar los botones en el Panel de acciones para agregar, eliminar y editar valores, y para organizarlos en el orden en el que deben aparecer en las listas desplegables donde se muestran.

## <a name="engineering-change-severities"></a>Gravedad de los cambios de ingeniería

Utiliza la gravedad de los cambios de ingeniería para indicar el nivel de impacto que se aplica a los productos en una orden de cambio de ingeniería.

Para establecer la colección de gravedades de cambios de ingeniería que se utilizan en su empresa, vaya a **Gestión de cambios de ingeniería \> Preparar \> Gestión de cambios de ingeniería \> Gravedades de cambio de ingeniería**. Luego, puede usar los botones en el Panel de acciones para agregar, eliminar y editar valores, y para organizarlos en el orden en el que deben aparecer en las listas desplegables donde se muestran.

Puede establecer reglas que se apliquen a cada nivel de gravedad que cree. Para obtener más información sobre cómo asignar estas reglas, consulte la siguiente sección.

## <a name="engineering-change-severity-rule-sets"></a>Conjuntos de reglas de gravedad de cambio de ingeniería

Utilice conjuntos de reglas de gravedad de cambios de ingeniería para establecer un grupo de reglas que puede utilizar para calcular automáticamente la gravedad de la orden de cambio, según el tipo de cambios en los productos afectados. Para usar las reglas de gravedad, abra la página **Parámetros de gestión de cambios de ingeniería** y establezca el campo **Regla de gravedad** en *Calcular* o *Calcular automáticamente*.

Cuando el sistema evalúa la gravedad, procesa las reglas en el orden en que aparecen en la página, de arriba a abajo. Para que se seleccione una regla y se establezca su prioridad, se deben cumplir todas las reglas de un conjunto de reglas.

Para configurar las reglas que se aplican a cada nivel de gravedad de cambio que haya definido, vaya a **Gestión de cambios de ingeniería \> Preparar \> Gestión de cambios de ingeniería \> Conjuntos de reglas de gravedad de cambios de ingeniería**. Luego siga uno de estos pasos.

- Para crear un nuevo conjunto de reglas, seleccione **Nuevo** en el Panel de acciones y luego configure los campos como se describe más adelante en esta sección.
- Para editar un conjunto de reglas existente, selecciónelo en el panel de lista, seleccione **Editar** en el Panel de acciones y luego configure los campos como se describe más adelante en esta sección.
- Para eliminar un conjunto de reglas existente, selecciónelo en el panel de lista y luego seleccione **Eliminar** en el Panel de acciones.
- Para reorganizar la lista de conjuntos de reglas, seleccione un conjunto de reglas en el panel de lista y luego use los botoones **Arriba** y **Abajo** del Panel de acciones para reposicionarlo.

Para cada conjutno de reglas, establezca el siguiente campo:

- **Gravedad** - Seleccione el nivel de gravedad para el que establecer reglas. Use la página **Severidades de cambios de ingeniería** para crear y nombrar los niveles. (Vea la sección anterior para obtener más información).

Utilice los botones de la ficha desplegable **Reglas** para agregar o quitar una regla para la configuración de gravedad actual. Cada regla tiene un campo **Regla** y un campo **Nombre**. Las reglas las establece el sistema e indican los tipos de cambios que puede tener un producto. El nombre indica el tipo de modificación.
