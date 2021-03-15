---
title: Ver el historial de flujo de trabajo
description: Este tema describe los pasos para ver el estado de un documento que envió al sistema de flujo de trabajo para que se lo procese y apruebe.
author: jasongre
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowStatus
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 325478ed89b9c650899001dd08d1c98550fce520
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798989"
---
# <a name="view-workflow-history"></a>Ver el historial de flujo de trabajo

[!include [banner](../../includes/banner.md)]

Este tema describe los pasos para ver el estado de un documento que envió al sistema de flujo de trabajo para que se lo procese y apruebe. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.

1. Vaya a **Panel de exploración > Módulos > Común > Preguntas > Flujo de trabajo > Historial de flujo de trabajo**.
    - Utilice este formulario para ver el estado de un documento que se ha enviado al sistema de flujo de trabajo para procesarlo y aprobarlo.  
    - El **Id. de la instancia** es el código de identificación de la instancia de flujo de trabajo que está procesando, o ha procesado, el documento.  
    - El **Estado** es el estado del flujo de trabajo del documento.  
    - El **ID del flujo de trabajo** es el código de identificación del flujo de trabajo que está procesando, o ha procesado, el documento.  
    - El **Documento** es el código de identificación del documento.  
    - El **Tipo de documento** es el tipo de documento que se envió para su procesamiento.  
    - **Flujo de trabajo** es el nombre del flujo de trabajo que está procesando, o ha procesado, el documento.  
    - **Versión** es el número de versión del flujo de trabajo que está procesando, o ha procesado, el documento.  
    - La **Fecha y hora de creación** es la fecha y hora en que se envió el documento.  
    - El **Tiempo transcurrido** es el tiempo que ha pasado desde que se envió el documento.  
    - El botón de **Reanudar** le permite que reanudar el proceso del flujo de trabajo para el documento seleccionado.  
    - El botón **Recuperar** le permite recuperar el documento seleccionado para que no sea procesado.   
2. En la lista, seleccione el vínculo de la fila deseada.
    - Asegúrese de que la sección **Elementos de trabajo** está expandida. En esta sección puede ver los elementos de trabajo que se están asociados al documento seleccionado. Por ejemplo, es posible que haya completado una tarea, o que el documento se haya aprobado.  
    - El botón **Reasignar** abrirá un cuadro de diálogo en el que se puede reasignar un elemento de trabajo a otro usuario.  
    - Asegúrese de que la sección **Detalles de seguimiento** está expandida. En esta sección puede ver el historial del flujo de trabajo del documento seleccionado.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]