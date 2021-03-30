---
title: Configuración de la reasignación de artículos para la selección corta
description: En este tema se muestra cómo permitir que los trabajadores del almacén busquen rápidamente ubicaciones alternativas si no hay suficiente inventario en la ubicación a la que les han dirigido.
author: ShylaThompson
manager: tfehr
ms.date: 06/29/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker, WHSLocationWithWorkException
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3ecd05add44bacae517109f8bab2cb43376fe07c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5216820"
---
# <a name="set-up-short-picking-item-reallocation"></a>Configuración de la reasignación de artículos para la selección corta

[!include [banner](../../includes/banner.md)]

En este procedimiento se muestra cómo permitir que los trabajadores del almacén busquen rápidamente ubicaciones alternativas si no hay suficiente inventario en la ubicación a la que les han dirigido. 

El proceso de reasignación lo controla una **Excepción de trabajo** y lo utiliza el **trabajador** del almacén.

Es posible utilizar procesos de reasignación automáticos, manuales o ambos:

- Reasignación automática: se utilizan directivas de ubicación para determinar si las mercancías están disponibles en otra ubicación. Si es posible, el trabajo se actualizará y el usuario del almacén será dirigido a la ubicación alternativa.
- Reasignación manual: permite al usuario del almacén seleccionar entre una o varias ubicaciones con cantidades de mercancías sin reservar. 
- Automática y manual: si el sistema no puede realizar una reasignación automática y las ubicaciones están disponibles con cantidades sin reservar, se le pedirá al usuario que seleccione una ubicación.

## <a name="set-up-work-exceptions"></a>Configurar excepciones de trabajo
Es posible definir varias excepciones de trabajo con directivas de la reasignación de artículo diferentes para permitir el trabajador del almacén para elegir uno basado en las necesidades de envío que están procesando.

Para crear este procedimiento se utiliza la empresa de datos de prueba USMF.

1. En el **Panel de navegación**, vaya a **Administración de almacenes > Configuración > Trabajo > Excepciones de trabajo**.
2. Haga clic en **Nuevo** 
3. En el campo **Código de excepción de trabajo**, escriba un valor. Este será el título de esta excepción. Por ejemplo, manual de picking corto.
4. En el campo **Descripción**, escriba un valor. Esta será una descripción breve del uso de esta excepción. Por ejemplo, Picking corto: elemento no disponible.
5. En el campo **Tipo de excepción**, seleccione **Picking corto**.
6. Active la casilla **Ajustar inventario**. Se está seleccionada, el inventario se ajustará automáticamente a 0 en la ubicación de picking corto.
7. En el campo **Código de tipo de ajuste predeterminado**, especifique o seleccione un valor. Por ejemplo, en USMF puede seleccionar **Quitar Res Adj Out**. Cada código de tipo de ajuste contiene cuatro características: nombre, descripción, nombre de diario de inventario y **Quitar reservas**. Si **Quitar reservas** está habilitada, se quitarán las reservas de la línea de pedido de picking corto.  
8. En el campo **Reasignación de artículos**, seleccione un valor, como Manual. Si selecciona Manual o Automático y manual, el trabajador del almacén debe estar habilitado para usar la reasignación manual.

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a>Configurar un trabajador para usar la reasignación manual de artículos

Para crear este procedimiento se utiliza la empresa de datos de prueba USMF.

1. Cierre la página.
2. En el **Panel de navegación**, vaya a **Administración de almacenes > Configuración > Trabajador**.
3. Haga clic en **Editar**.
4. En la lista, seleccione un trabajador. Por ejemplo, Julia Funderburk.
5. Expanda la ficha desplegable **Usuarios**.
6. Seleccione un **Id. de usuario** en la lista. Por ejemplo, 24.
7. Expanda la ficha desplegable **Trabajo**.
8. Seleccione **Sí** en el campo **Permitir reasignación de artículos manual**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]