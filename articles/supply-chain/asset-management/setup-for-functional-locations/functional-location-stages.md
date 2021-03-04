---
title: Estados de ciclo de vida de ubicaciones funcionales
description: Este tema describe cómo configurar los estados y modelos de ciclo de vida de la ubicación funcional en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationLifecycleModel, EntAssetFunctionalLocationLifecycleState
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3eedc21dde32671b4f5539ac4e798a8e1329c191
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437152"
---
# <a name="functional-location-lifecycle-states"></a>Estados de ciclo de vida de ubicaciones funcionales

[!include [banner](../../includes/banner.md)]

 

Este tema describe cómo configurar los estados y modelos de ciclo de vida de la ubicación funcional en Administración de activos. Los estados de ciclo de vida de una ubicación funcional definen los estados por los que puede pasar una ubicación funcional, por ejemplo: creada, activa y finalizada. Puede ver todas las ubicaciones funcionales, independientemente de su estado de ciclo de vida, en la página de lista **Todas las ubicaciones funcionales**. Puede cambiar el estado de una ubicación funcional seleccionándola en la página de lista **Todas las ubicaciones funcionales** y seleccionando **Actualizar estado de ubicación funcional**.

## <a name="set-up-functional-location-lifecycle-states"></a>Configurar estados de ciclo de vida de ubicación técnica

1. Seleccione **Administración de activos** > **Configuración** > **Ubicaciones funcionales** > **Estados de ciclo de vida**.
2. Seleccione **Nuevo** para crear un nuevo estado de ubicación funcional.
3. Inserte el identificador de estado en el campo **Estado de ciclo de vida** y un nombre para el estado de la ubicación funcional en el campo **Nombre**. En el campo **Modelos del ciclo de vida**, puede ver el número de modelos de ciclo de vida de ubicación funcional que usan el estado de ubicación funcional.
4. En el FastTab **General**, seleccione "Sí" en el botón de alternar **Activo** si la ubicación funcional está activa en este estado.
5. Seleccione "Sí" en el botón de alternar **Crear activos** si es posible crear automáticamente un activo con el mismo nombre que la ubicación funcional e instalarlo en la ubicación funcional en este estado.  
>[!NOTE]
>Este botón de alternar está relacionado con el campo **Tipo de activo** en el FastTab **General** del formulario **Tipos de ubicación funcional** (**Administración de activos** > **Configuración** > **Ubicaciones funcionales** > **Tipos de ubicación funcional**).
6. Seleccione "Sí" en el botón de alternar **Cambiar el nombre de la ubicación** si es posible modificar el nombre de la ubicación funcional en este estado.
7. Seleccione "Sí" en el botón de alternar **Nuevas sububicaciones** si es posible agregar nuevas sububicaciones a la ubicación funcional en este estado.
8. Seleccione "Sí" en el botón de alternar **Instalar activos** si es posible instalar activos en la ubicación funcional en este estado.
9. Seleccione "Sí" en el botón de alternar **Eliminar ubicación funcional** si es posible eliminar la ubicación funcional en este estado.
10. Seleccione un estado de activo en el campo **Estado del ciclo de vida** si desea que el estado de ciclo de vida de activo de todos los activos instalados en la ubicación funcional se actualicen automáticamente en este estado. Ejemplo: Si cierra una ubicación funcional y establece el estado de ciclo de vida de la ubicación en “Finalizada”, podría cambiar automáticamente el estado del ciclo de vida de los activos instalados en dicha ubicación funcional a "No en uso".


>[!NOTE]
>Los estados de ciclo de vida, los modelos de ciclo de vida y los tipos de ubicación funcional están relacionados y se utilizan de la misma forma que los estados de ciclo de vida de la orden de trabajo, los modelos del ciclo de vida de la orden de trabajo y los tipos de orden de trabajo. 

## <a name="set-up-functional-location-lifecycle-models"></a>Configurar modelos de ciclo de vida de ubicación técnica

Cuando haya creado los estados de ciclo de vida necesarios para las ubicaciones funcionales, se pueden dividir en grupos. Esto se hace para crear un flujo de modelo de ciclo de vida que se pueda utilizar para distintos tipos de ubicaciones funcionales. Como mínimo, debe crearse un modelo de ciclo de vida de ubicación funcional estándar.

1. Seleccione **Administración de activos** > **Configuración** > **Ubicaciones funcionales** > **Modelos de ciclo de vida**.
2. Seleccione **Nuevo** para crear un nuevo modelo de ciclo de vida.
3. Inserte el identificador de modelo de ciclo de vida en el campo **Modelo de ciclo de vida** y un nombre para el modelo de ciclo de vida en el campo **Nombre**. En los campos **Tipos de ubicación funcional** y **Estados de ciclo de vida** puede ver el número de tipos de ubicación funcional que usan el modelo del ciclo de vida y el número de estados seleccionados en el modelo de ciclo de vida.
4. En el FastTab **Estados de ciclo de vida**, seleccione los estados que se van a incluir en el modelo. Para ello, haga clic en un estado en la sección **Estados de ciclo de vida restantes** y haga clic en el botón de la ![flecha atrás](media/02-setup-for-functional-locations.png).
5. Si desea seleccionar todos los estados disponibles para un modelo, haga clic en el botón ![seleccionar todos los estados disponibles](media/03-setup-for-functional-locations.png) . Transfiere todos los estados a la sección **Estados de ciclo de vida seleccionados**.
6. Si desea quitar un estado seleccionado del modelo, seleccione el estado en la sección **Estados de ciclo de vida seleccionados** y seleccione el botón de la ![flecha atrás](media/04-setup-for-functional-locations.png) .
7. Seleccione **Actualizaciones de estado de ciclo de vida** para definir qué estados de ciclo de vida pueden seguir un estado seleccionado.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]