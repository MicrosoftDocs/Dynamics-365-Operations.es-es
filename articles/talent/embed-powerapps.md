---
title: Integrar aplicaciones de PowerApps en Core HR
description: Este tema explica cómo resolver el problema en el que el elemento de menú de PowerApps ha desaparecido del módulo Gestión del sistema.
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
ms.openlocfilehash: e3b20e1d0a873c32b8f6f5e28f786febf62db355
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1519074"
---
# <a name="embed-powerapps-apps-in-core-hr"></a>Integrar aplicaciones de PowerApps en Core HR

[!include [banner](includes/banner.md)]

**Emisión**

El elemento de menú **PowerApps** ha desaparecido del módulo **Administración del sistema** .

**Causa**

Se ha cambiado el diseño (IU) de la interfaz de usuario, y Microsoft PowerApps ahora se incluye en el modelo estándar de personalización.

**Resolución**

Se ha cambiado el modo en que las aplicaciones de PowerApps se insertan. Las aplicaciones de PowerApps ahora se agregan a través del modelo de personalización. Puede agregar las aplicaciones de PowerApps a casi todas las páginas de Microsoft Dynamics 365 for Talent.

Para obtener información detallada acerca de cómo insertar aplicaciones de PowerApps en Talent, consulte [Integrar aplicaciones de PowerApps](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).

Cualquier cliente de PowerApps que incrustara aplicaciones antes del cambio se debe haber actualizado al modelo nuevo.

El botón **PowerApps** se encuentra en la esquina superior derecha de casi cada página de Talent. Puede usar este botón para insertar una aplicación de PowerApps.

He aquí un ejemplo.

1. Vaya a **Administración de personal \> Vínculos \> Trabajadores \> Empleados**.
2. Seleccione el botón **PowerApps** y, a continuación, seleccione **Insertar una PowerApp**.

    ![Botón de PowerApps](media/png.png)

3. Complete los campos en el cuadro de diálogo **Insertar un PowerApp** .

    ![Insertar un cuadro de diálogo de PowerApp](media/insert-powerapp.png)

O bien debe seguir estos pasos.

1. En el panel de acciones de la página, en la pestaña **Opciones**, en el grupo **Personalizar**, seleccione **Personalizar este formulario**.

    ![Personalizar el grupo en la ficha de las opciones](media/options.png)

    La barra de herramientas de personalización aparece.

2. En la barra de herramientas, seleccione **Insertar \> PowerApp**.

    ![Inserte una aplicación de PowerApps mediante la barra de herramientas de personalización](media/powerapp-bar.png)
