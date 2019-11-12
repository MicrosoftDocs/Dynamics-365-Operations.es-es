---
title: Crear un activo
description: En este tema se describe cómo crear un activo en la Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1a4759f55eceba923b47d906a764edcad34bf2f2
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571608"
---
# <a name="create-an-asset"></a>Crear un activo

[!include [banner](../../includes/banner.md)]

 

En este tema se describe cómo crear un activo en la Administración de activos.

1. Haga clic en **Administración de activos** > **Común** > **Activos** > **Todos los activos** o **Activos activos**.
2. Haga clic en el botón **Nuevo**.
3. En el diálogo **Crear activos**, inserte datos relativos al **Activo** (el id. de activo) y el nombre del activo. Seleccione la fecha y la hora para el activo en el campo **Vigente**. A partir de esa fecha podrá instalar el activo en una ubicación técnica, así como mover y reemplazar el activo en una estructura de activo.
4. En el campo **Tipo de activo**, seleccione el tipo del activo (campo obligatorio). Si es necesario, seleccione **Fabricante del activo** y **Modelo del activo** para el activo. Si solo se ha configurado un producto, ese producto se seleccionará automáticamente en el campo **Fabricante del activo**. Las selecciones disponible en los **Fabricante del activo** y **Modelo del activo** dependerán de la configuración de [Fabricante y modelo del activo](../setup-for-objects/product-and-model.md).
5. En el grupo **Activo principal**, el campo **Activo** está en blanco de forma predeterminada. Si es necesario, puede seleccionar un activo principal. Todos los campos del grupo **Activo principal** se rellenarán automáticamente.
>[!NOTE]  
>Al seleccionar un activo principal, hay dos o tres pestañas disponibles: la pestaña **Mis activos** contiene los activos relacionados con las ubicaciones técnicas a las que usted (el trabajador de mantenimiento conectado al sistema) puede ser asignado. Si no se ha configurado ninguna ubicación técnica para un trabajador de mantenimiento en el formulario [Trabajadores de mantenimiento](../setup-for-objects/workers-and-worker-groups.md), la pestaña **Mis activos** no estará visible. La pestaña **Activos activos** contiene una lista de todos los activos cuyo estado de ciclo de vida es "Activo". La pestaña **Vista de activos** muestra una vista de árbol de las ubicaciones técnicas y los activos instalados en esas ubicaciones.

6. La ubicación técnica predeterminada que ha configurado se sugiere para el activo en el campo **Grupo de activos** > **Ubicación técnica**. Seleccione otra ubicación técnica si es necesario.

>[!NOTE]
>Después de crear un activo, puede instalarlo en otra ubicación técnica si es necesario. Solo se pueden instalar activos de nivel superior (activos que no tienen un activo principal actualmente) en una ubicación técnica. Esto significa que los activos de nivel superior y los activos secundarios se instalan en la ubicación técnica seleccionada. Para obtener más información sobre la instalación de activos en ubicaciones técnicas, consulte [Ubicaciones técnicas](../functional-locations/introduction-to-functional-locations.md).

7. Haga clic en **Aceptar**.
8. Seleccione el activo en la lista **Todos los activos** y haga clic en el botón **Editar** para agregar más información al activo.

## <a name="general-information"></a>Información general

La ubicación técnica con la que el activo está relacionado se muestra en el campo **Ubicación técnica**. Si el activo es un activo principal, se mostrará el número de elementos secundarios relacionados con el activo en el campo **Secundarios**. Si el activo es un activo secundario de un activo existente, el id. del activo principal se muestra en el campo **Principal**.

Puede editar la información del activo de **Fabricante del activo** y **Modelo del activo**, que se usa para administrar piezas de repuesto, piezas de repuesto alternativas y valores predeterminados de tipo de trabajo. Consulte [Fabricante y modelo del activo](../setup-for-objects/product-and-model.md) para obtener más información. También puede agregar información sobre el **Año de modelo** y el **Número de serie**, si es necesario.

Se usa **Estado actual del ciclo de vida** para definir si el activo está activo o inactivo. Al crear un activo, la etapa siempre se establece en la primera en el grupo de almacenamiento provisional de activos. Cuando esté preparado para activar un activo, haga clic en **Actualizar estado del activo** y seleccione el estado de ciclo de vida que ha definido como "activo activo". A continuación, haga clic en **Aceptar**.

**Nota:** Cuando un activo es en estado "inactivo", no es posible crear órdenes de trabajo para el activo. Además, no se pueden programar los trabajos de mantenimiento preventivo para un activo inactivo.

Los campos **Nivel de servicio** e **Importancia** están relacionados con las órdenes de trabajo creadas para el activo. Los campos muestran los valores de **Nivel de servicio** e **Importancia** calculados para la configuración actual del activo. Consulte [Niveles de servicio de activos](../setup-for-objects/object-priorities.md) e [Importancia de activo](../setup-for-objects/object-criticalities.md) para obtener información sobre la configuración de estos valores.

## <a name="asset"></a>Activo

Puede seleccionar un **Recurso** para el activo. La selección de recursos determina qué calendario se utiliza para la programación de órdenes de trabajo. La selección de recursos se utiliza a menudo para los activos fijos. Los recursos y grupos de recursos se configuran en **Administración de la organización** > **Recursos** > **Grupos de recursos** o **Recursos**.

En el campo **Número de activos fijos**, puede seleccionar un activo fijo que desea que esté relacionado con el activo. Esto es relevante si el activo está relacionado con un proyecto de inversión.

- Si el activo está relacionado con un activo fijo, puede crear un tipo de orden de trabajo y usarlo para las órdenes de trabajo relacionadas con un proyecto de inversión. 
- La información sobre los activos fijos de un activo está relacionada con el módulo **Activos fijos** de Dynamics 365 Supply Chain Management. Esto significa que, en **Activos fijos** > **Activos fijos** > **Activos fijos**, puede obtener una visión general de los proyectos de Administración de activos que pueden estar relacionadas con un activo fijo seleccionándolo en y visualizando el contenido en el panel **Información relacionada** > sección **Proyectos asociados**.


## <a name="details"></a>Detalles

En el campo **Activo desde** se muestra la fecha en la que se actualizó el estado de ciclo de vida del activo a un estado activo (consulte [Estados de ciclo de vida de activos](../setup-for-objects/object-stages.md) en relación con la configuración de los estados de ciclo de vida de activo). Si el activo ya no está activo, y ha actualizado el estado de ciclo de vida del activo a un estado de ciclo de vida inactivo, en el campo **Activo hasta** se muestra la fecha desde la que el activo pasó a estar inactivo. Si es necesario, puede cambiar manualmente estas fechas.

Si es necesario, puede insertar una fecha prevista para la sustitución del activo en el campo **Fecha de sustitución**. Se puede insertar un valor estimado para reemplazar el activo en el campo **Valor de sustitución**. Ejemplo: puede usar la información de sustitución para compararla con los costes de mantener un activo, y tomar posteriormente la decisión de comprar un activo nuevo si los costes de mantenimiento aumentan rápidamente en el activo existente.

## <a name="notes"></a>Notas

Puede agregar notas relacionados con el activo en la ficha desplegable **Notas**. Haga clic en el botón **Agregar marca de tiempo** antes de escribir la nota si desea agregar información sobre el usuario y una fecha o una marca de tiempo a la nota.

## <a name="attributes"></a>Atributos

En esta ficha desplegable puede establecer valores de los atributos. Estos atributos se pueden usar para describir las propiedades o las características relacionadas con el activo, como su tamaño, peso o configuración de máquinas.

Haga clic en **Agregar línea** y seleccione el tipo de atributo. A continuación, inserta el **Valor** relacionado con el tipo de atributo y guarde el registro.

>[!NOTE] 
>Puede obtener una visión general de los tipos de atributo de activo y su relación con los activos en **Atributo de activo** y en **Información general de atributos de activo**. Consulte [Información general de atributos de activo](../objects/object-specification-overview.md) para obtener más información.

## <a name="vendor"></a>Proveedor

En la ficha desplegable **Proveedor**, seleccione una cuenta de proveedor para el activo. Además, si se ha concedido una garantía de proveedor, puede insertar aquí la información de la garantía.

## <a name="address"></a>Dirección

En la ficha desplegable **Dirección**, puede insertar la dirección del equipo. Si no se inserta ninguna dirección en el activo, el activo usará la dirección de un activo principal, si este tiene una dirección. Si no hay ninguna dirección relacionada con el activo ni con los activos principales de la jerarquía de activos, puede usarse la dirección de la ubicación técnica en la que está instalado el activo. Si esa ubicación técnica no tiene una dirección relacionada, se usará en el activo la dirección de la ubicación técnica principal.

## <a name="asset-management-plans"></a>Planes de administración de activos

Los planes de mantenimiento se usan para programar trabajos de mantenimiento preventivo a intervalos periódicos en el activo. En esta ficha desplegable puede configurar las líneas del plan de mantenimiento para el activo seleccionado. Se pueden configurar rondas de mantenimiento para varios activos en los que tiene que realizar una tarea similar a intervalos regulares. En la pestaña **Planes de mantenimiento de ubicación técnica** se muestran los planes de mantenimiento relacionados con la ubicación técnica en la que está instalado el activo.

>[!NOTE]
>Si elimina una línea del plan de mantenimiento o una ronda de mantenimiento relacionada con un activo en **Todos los activos**, también elimina automáticamente todas las programaciones de mantenimiento con el estado "Creado" que se crearon a partir del plan de mantenimiento o la ronda de mantenimiento.

## <a name="functional-location-maintenance-plans"></a>Planes de mantenimiento de ubicación técnica

En esta ficha desplegable puede ver información general sobre los planes de mantenimiento relacionados con la ubicación técnica en la que está instalado el activo.

## <a name="maintenance-rounds"></a>Rondas de mantenimiento

En esta ficha desplegable puede agregar o quitar rondas de mantenimiento relacionadas con el activo.

## <a name="financial-dimensions"></a>Dimensiones financieras

Puede seleccionar dimensiones financieras para el activo.
