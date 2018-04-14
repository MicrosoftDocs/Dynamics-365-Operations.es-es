---
title: "Configuración de una decisión condicional en un flujo de trabajo"
description: "Use el siguiente procedimiento para configurar las propiedades de una decisión condicional."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195703
ms.assetid: cd5554a4-210c-4c20-a7d3-4b1563c2b5df
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 597a6a254dcd623f9e7c59a0309eeedee1b5adee
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="configure-a-conditional-decision-in-a-workflow"></a>Configuración de una decisión condicional en un flujo de trabajo

[!INCLUDE [banner](../includes/banner.md)]

Use el siguiente procedimiento para configurar las propiedades de una decisión condicional.

Una decisión condicional es un punto en el que un flujo de trabajo se divide en dos ramas. Para configurar una decisión condicional, en el editor de flujo de trabajo, haga clic con el botón derecho en la decisión condicional y, a continuación, haga clic en **Propiedades** para abrir el formulario **Propiedades**.

## <a name="name-a-decision"></a>Asignar un nombre a una decisión
Siga estos pasos para asignar un nombre a una decisión condicional.
1.  En el panel izquierdo, haga clic en **Configuración básica**.
2.  En el campo **Nombre**, escriba un nombre único para la decisión condicional.

## <a name="set-conditions"></a> Establecimiento de condiciones
Para decidir la rama que se usa, el sistema evalúa el documento enviado para determinar si cumple con determinadas condiciones.
1.  En el panel izquierdo, haga clic en **Configuración básica**.
2.  Haga clic en **Agregar condición**.
3.  Escriba una condición.
4.  Escriba condiciones adicionales, si fuera necesario.
5.  Para comprobar que las condiciones definidas se hayan configurado correctamente, siga estos pasos:
    1.  Haga clic en **Probar** para abrir el formulario **Probar la condición del flujo de trabajo**.
    2.  Seleccione un registro del área **Comprobar condición** del formulario.
    3.  Haga clic en **Probar**. El sistema evalúa el registro seleccionado para determinar si reúne las condiciones definidas.
    4.  Haga clic en **Aceptar** o en **Cancelar** para regresar al formulario **Propiedades**.






