---
title: Suspender configuraciones en el repositorio RCS Global
description: Este tema describe cómo interrumpir las configuraciones en el repositorio RCS Global.
author: JaneA07
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-02-02
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 2bd22e991de376cfd93f75158f1f29716d2559e1
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018742"
---
# <a name="discontinue-configurations-in-the-rcs-global-repository"></a>Suspender configuraciones en el repositorio RCS Global

[!include [banner](../includes/banner.md)]

Este tema describe cómo interrumpir la configuración en el repositorio RCS Global. Anteriormente, solo era posible eliminar configuraciones que ya no eran necesarias. Sin embargo, ahora puede marcar una configuración lanzada como **Interrumpida** en el repositorio RCS Global. Con esta funcionalidad, también puede hacer lo siguiente: 
 
 - Proporcione notificaciones anticipadas cuando se planea suspender una configuración.
 - Incluya detalles aplicables sobre la configuración de reemplazo.
 - Establezca una fecha **Soportado hasta** para la configuración específica, para informar al usuario cuándo se suspenderá.

Cuando interrumpe una versión de configuración, puede especificar la siguiente información opcional:

  - **Configuración de la sustitución**
  - **Versión de configuración de reemplazo**
  - **Nota de texto libre**: utilice este campo para proporcionar enlaces de documentación o referencias
  - **Soportado hasta**: este campo proporciona la fecha propuesta hasta la cual se admitirá la configuración/versión actual. Esta fecha debe actualizarse manualmente.
  
Para interrumpir la configuración, complete los siguientes pasos. 

1. Seleccione si desea interrumpir una sola versión o todas las versiones con la misma configuración en una operación, configurando **Todas las versiones** en **Sí**. 
2. Seleccione el parámetro **Interrumpir** en **Sí**.
3. Seleccione **Aceptar** para interrumpir las configuraciones. El campo **Fecha de interrupción** se completará cuando guarde los cambios.

![Interrumpir la información de configuración](media/Discontinue-details-2.png)
  
Puede revertir la configuración a **Compartido** o ajustar la información de interrupción en cualquier momento. Si comparte una configuración, especifique la fecha **Soportado hasta** y cualquier otra información relacionada con la interrupción para indicar sus planes para la interrupción futura.

Si desea compartir información sobre una interrupción planificada, antes de interrumpir realmente la configuración, el usuario puede completar previamente todos los campos relacionados con el reemplazo, pero dejar el parámetro **Interrumpir** establecido en **No**.

> [!NOTE]
> La interrupción no limita las operaciones con configuraciones. Puede continuar importando, ejecutando o derivando las configuraciones, estos campos son informativos.

## <a name="finance-supports-displaying-this-information-starting-in-version-10014"></a>Finance admite la visualización de esta información a partir de la versión 10.0.14

Dynamics 365 Finance admite la visualización de la información de interrupción, a partir de la versión 10.0.14. En la página **Repositorio global**, puede ver información actualizada relacionada con la interrupción. De forma predeterminada, las configuraciones que están interrumpidas se filtran.
  
La página **Configuraciones importadas** (ERSolutionTable) muestra las configuraciones que ya estaban interrumpidas cuando se importaron. Para aquellas configuraciones que fueron interrumpidas después de la importación, la información de interrupción se puede sincronizar ejecutando el trabajo **Importar actualizaciones de configuraciones**.


