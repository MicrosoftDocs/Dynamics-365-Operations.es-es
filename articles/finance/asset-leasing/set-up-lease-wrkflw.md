---
title: Configurar flujos de trabajo de aprobación de arrendamiento
description: El tema explica cómo configurar un flujo de trabajo de aprobación que se ejecutará cuando se cree un nuevo arrendamiento.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 58c0fd781710b7ab8efeaa7a6874f412279a5924
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "4447793"
---
# <a name="set-up-lease-approval-workflows"></a>Configurar flujos de trabajo de aprobación de arrendamiento

[!include [banner](../includes/banner.md)]

El tema explica cómo configurar un flujo de trabajo de aprobación que se ejecutará cuando se cree un nuevo arrendamiento. Para obtener información sobre cómo utilizar el flujo de trabajo, consulte [Utilizar flujos de trabajo de aprobación de arrendamiento](use-create-lease-wrkflw.md). 

1. Vaya a **Arrendamiento de activos \> Configuración \> Flujo de trabajo de arrendamientos**.
2. En la página **Flujo de trabajo de arrendamiento**, seleccione **Nuevo**.
3. En el cuadro de diálogo que aparece, en **Tipo de flujo de trabajo**, seleccione el vínculo **Flujo de trabajo de arrendamiento**.

    Se abre la aplicación. Después de que se ejecute, inicie sesión en Azure Active Directory (Azure AD) para ser redirigido a la aplicación de flujo de trabajo.

4. Arrastre el elemento **Aprobación de flujo de trabajo de arrendamiento** al flujo de trabajo.
5. Conecte un nodo desde **Inicio** a **Aprobación de flujo de trabajo de arrendamiento**. A continuación, conecte **Aprobación del flujo de trabajo de arrendamiento** a **Fin**.
6. Haga doble clic en **Aprobación de flujo de trabajo de arrendamiento**.
7. Seleccione **Propiedades**, y luego, en **Configuración básica**, introduzca un nombre para el flujo de trabajo.

    En esta página, también puede establecer más parámetros para el flujo de trabajo. Si ha activado **Acciones automáticas**, el sistema tomará automáticamente una acción específica. Se pueden enviar notificaciones si se especifican en la pestaña **Notificaciones**. En la pestaña **Configuración avanzada**, puede especificar un aprobador final, establecer un límite de tiempo y designar acciones específicas que deben completarse.

8. Cuando haya terminado de configurar los parámetros del flujo de trabajo, seleccione **Cerrar**.
9. Seleccione **Paso 1** y luego **Propiedades**.
10. En **Configuración básica**, introduzca un nombre para el paso, cree una línea de asunto para la aprobación y especifique las instrucciones para la aprobación.
11. En la página **Asignación**, seleccione el tipo de asignación.
12. Para asignar usuarios específicos a la aprobación, seleccione **Usuario**, seleccione los usuarios que aprueban los arrendamientos y luego seleccione **Cerrar**.
13. Seleccione **Guardar y cerrar** para crear el flujo de trabajo. Luego, cuando se le solicite, seleccione **Aceptar**.
14. En la página **Crear flujo de trabajo de arrendamiento**, seleccione **Cerrar**.
14. Seleccione el nuevo flujo de trabajo y luego seleccione **Versiones**. Luego seleccione **Activar** para asegurarse de que el flujo de trabajo esté activo.
15. Seleccione **Cerrar**. Aparece la nueva versión activa.
