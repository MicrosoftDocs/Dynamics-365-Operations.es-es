---
title: Asignar tiendas y equipos si estos últimos ya existen en Microsoft Teams
description: Este artículo cubre cómo asignar tiendas y equipos correspondientes en la sede de Dynamics 365 Commerce si su organización ya ha creado equipos en Microsoft Teams antes de la integración con Commerce.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 4cb18affd0df59dc986602a684a3fe3d418644fd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902746"
---
# <a name="map-stores-and-teams-if-there-are-pre-existing-teams-in-microsoft-teams"></a>Asignar tiendas y equipos si estos últimos ya existen en Microsoft Teams

[!include [banner](includes/banner.md)]

Este artículo cubre cómo asignar tiendas y equipos correspondientes en la sede de Dynamics 365 Commerce si su organización ya ha creado equipos en Microsoft Teams antes de la integración con Commerce.

Su organización puede tener equipos creados para algunas o todas sus tiendas antes de integrar Dynamics 365 Commerce y Microsoft Teams. Si este es el caso, para establecer la sincronización de tareas entre Commerce PDV y Microsoft Teams debe proporcionar la asignación de tiendas y equipo correspondiente en Commerce headquarters.

## <a name="map-stores-and-corresponding-teams-in-commerce-headquarters"></a>Asignar tiendas y equipos correspondientes en la sede de Commerce 

Para asignar tiendas y equipos correspondientes en la sede de Commerce, siga estos pasos.

1. Vaya a **Administración del sistema \> Espacio de trabajo \> Administración de datos**.
1. Seleccione **Exportar**. 
1. En el panel de acciones, haga clic en **Nueva**.
1. En **Nombre del grupo**, introduzca "Exportar asignación de Teams".
1. En la ficha desplegable **Entidades seleccionadas**, seleccione **Agregar entidad**. Aparece el cuadro **Agregar entidad**.  
1. En la lista desplegable **Nombre de la entidad**, seleccione **Asignación de Teams entre origen y equipo**.
1. En la lista desplegable **Formato de datos de destino**, seleccione **CSV**.
1. Seleccione **Agregar** y, a continuación, **Cerrar**.
1. En la parte superior izquierda debajo del Panel de acciones, seleccione **Exportar ahora**.
1. En **Estado de procesamiento de la entidad**, seleccione **Descargar archivo**.
1. En el archivo CSV exportado, introduzca valores para **SOURCETYPE**, **SOURCEID**, y **TEAMID** como sigue:
    - Para **SOURCETYPE**, introduzca "RetailStore". 
    - Para **SOURCEID**, introduzca el número de la tienda (por ejemplo, "000135" para la tienda de San Francisco). Puede encontrar los números de las tiendas en **Retail y Commerce \> Canales \> Tiendas**.
    - Para **TEAMID**, introduzca el identificador de equipo correspondiente de Microsoft Teams (por ejemplo, "5f8bc92b-6aa8-451e-85d1-3949c01ddc6c"). Puede encontrar la información de identificación del equipo en [admin.teams.microsoft.com](https://admin.teams.microsoft.com).
1. Guarde el archivo CSV en su máquina local.
1. Vaya a **Administración del sistema \> Espacio de trabajo \> Administración de datos** y después seleccione **Importar**.
1. En la ficha desplegable **Entidades seleccionadas**, seleccione **Agregar archivo**. Aparece el cuadro **Agregar archivo**.
1. En la lista desplegable **Nombre de la entidad**, seleccione **Asignación de Teams entre origen y equipo**.
1. En la lista desplegable **Formato de datos de origen**, seleccione **CSV**.
1. Seleccione **Cargar y agregar**, seleccione el archivo CSV que guardó anteriormente y luego seleccione **Abrir**.
1. En el cuadro de diálogo **Agregar archivo**, seleccione **Cerrar**.
1. En el panel de acciones, seleccione **Guardar** y luego seleccione **Importar**.

La siguiente imagen de ejemplo muestra el grupo **Exportar asignación de equipos** en Commerce con elementos de **Agregar entidad** y los encabezados del archivo CSV exportado resaltados.

![Exportar asignación de equipos en Commerce con elementos de agregar entidad y los encabezados del archivo CSV exportado resaltados.](media/d365-commerce-data-mgmt-export-entity.png)

> [!NOTE]
> Después de completar los pasos anteriores, siga los pasos en [Sincronizar la gestión de tareas entre Microsoft Teams y PDV](synchronize-tasks-teams-pos.md) para sincronizar la gestión de tareas. 

## <a name="additional-resources"></a>Recursos adicionales

[Información general sobre integración de Dynamics 365 Commerce y Microsoft Teams](commerce-teams-integration.md)

[Habilitar la integración de Dynamics 365 Commerce y Microsoft Teams](enable-teams-integration.md)

[Aprovisionar Microsoft Teams desde Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Sincronizar la gestión de tareas entre Microsoft Teams y Dynamics 365 Commerce PDV](synchronize-tasks-teams-pos.md)

[Administrar roles de usuario en Microsoft Teams](manage-user-roles-teams.md)

[Preguntas frecuentes de la integración de Dynamics 365 Commerce y Microsoft Teams](teams-integration-faq.md)
