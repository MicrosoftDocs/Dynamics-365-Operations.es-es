---
title: Integrar aplicaciones de Power Apps en Dynamics 365 - Core HR
description: Este tema explica cómo resolver el problema en el que el elemento de menú de Microsoft Power Apps ha desaparecido del módulo Gestión del sistema.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: b1dd1756be349d85af8e6d7159623a2a95e75526
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898721"
---
# <a name="embed-power-apps-apps-in-dynamics-365---core-hr"></a>Integrar aplicaciones de Power Apps en Dynamics 365 - Core HR

**Emisión**

El elemento de menú **Power Apps** ha desaparecido del módulo **Administración del sistema**.

**Causa**

Se ha cambiado el diseño (IU) de la interfaz de usuario, y Microsoft Power Apps ahora se incluye en el modelo estándar de personalización.

**Resolución**

Se ha cambiado el modo en que las Power Apps se insertan. Ahora las Power Apps se agregan a través del modelo de personalización. Puede agregar Power Apps a casi todas las páginas de Microsoft Dynamics 365 Talent.

Para obtener información detallada acerca de cómo insertar Power Apps en Talent, consulte [Integrar Microsoft Power Apps](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).

Cualquier cliente de Power Apps que incrustara aplicaciones antes del cambio se debe haber actualizado al modelo nuevo.

El botón **Power Apps** se encuentra en la esquina superior derecha de casi cada página de Talent. Puede usar este botón para insertar Power Apps.

He aquí un ejemplo.

1. Vaya a **Administración de personal \> Vínculos \> Trabajadores \> Empleados**.
2. Seleccione el botón **Power Apps** y, a continuación, seleccione **Insertar una PowerApp**.

    ![Botón Power Apps](media/png.png)

3. Complete los campos en el cuadro de diálogo **Insertar un PowerApp** .

    ![Insertar un cuadro de diálogo de PowerApp](media/insert-powerapp.png)

O bien debe seguir estos pasos.

1. En el panel de acciones de la página, en la pestaña **Opciones**, en el grupo **Personalizar**, seleccione **Personalizar este formulario**.

    ![Personalizar el grupo en la ficha de las opciones](media/options.png)

    La barra de herramientas de personalización aparece.

2. En la barra de herramientas, seleccione **Insertar \> PowerApp**.

    ![Inserte una aplicación de Power Apps mediante la barra de herramientas de personalización](media/powerapp-bar.png)
