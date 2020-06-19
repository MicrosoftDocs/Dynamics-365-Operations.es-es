---
title: Eliminar una estimación del proyecto
description: Este tema proporciona información sobre cómo eliminar una estimación del proyecto una vez completa.
author: kfend
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: eb323bdeb2a4701cdc9383b8da29e05a4cab107c
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410262"
---
# <a name="eliminate-a-project-estimate"></a>Eliminar una estimación del proyecto

[!include [banner](../includes/banner.md)]

Las estimaciones del proyecto proporcionan la visión financiera para el trabajo que se estima y programa para un proyecto. Para trabajar con estimaciones para un proyecto, es necesario adjuntar el proyecto a un proyecto de estimación. Un proyecto de estimación se basa siempre en un proyecto existente, pero varios proyectos pueden hacer referencia a un único proyecto de estimación. Solo se pueden adjuntar proyectos de precio fijo e inversión a los proyectos estimados, y esos proyectos deben pertenecer al mismo grupo de proyectos que el proyecto estimado.

Para eliminar un proyecto de estimación, debe estar completado. Los siguientes pasos explican cómo eliminar una estimación.

1. Vaya a **Gestión de proyectos y contabilidad** > **Todos los proyectos** y abra el proyecto. 
2. En la pestaña **Gestionar**, seleccione **Estimados** y, en la página **Estimar**, seleccione **Eliminar**.
3. En la página **Eliminar estimación** de la pestaña **General**, configure las siguientes opciones:

   - **Código de periodo**: seleccione el código de período para elegir los proyectos de estimación apropiados. 
   - **Fecha de estimación**: seleccione la fecha de estimación apropiada para la eliminación.
   - **Eliminar con advertencias WIP**: habilite esta opción para proporcionar notificaciones cuando se elimine una estimación asociada con un trabajo en curso (WIP). Cuando esta opción no está habilitada, la eliminación no puede continuar cuando existan transacciones no estimadas. 
   > [!NOTE]
   > Esta opción solo está disponible si la eliminación se aplica a un proyecto de estimación. No está disponible si se usan registros periódicos. Esta configuración funciona con la configuración de la pestaña **Estimar** de la página **Parámetros del proyecto**, en el grupo de campos **Permitir eliminación cuando existan transacciones no estimadas**.
   - **Establecer etapa en Terminado**: habilite esta opción para establecer la etapa estimada del proyecto en **Terminado** después de ejecutar la eliminación.
   - **Imprimir lista de estimaciones**: seleccione la información que se incluirá cuando se imprima la lista de estimaciones.
   - **Mostrar registro de información**: habilite esta opción para mostrar el registro de información.
   - **Fecha de publicación**: elija la fecha de contabilización en el libro mayor de la estimación.

4.  Seleccione **Aceptar**.
5. Una vez que se completa el proceso de eliminación, el proyecto de estimación eliminado se muestra con un valor negativo. 

Si no tenía la intención de eliminar una estimación, puede seleccionar la estimación eliminada y seleccionar **Invertir eliminación**.   
