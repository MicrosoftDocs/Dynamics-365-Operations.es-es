--- 
title: Ver historial del flujo de trabajo
description: "Siga estos pasos para ver el estado de un documento que envió al sistema de flujo de trabajo para que se lo procese y apruebe."
author: jasongre
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WorkflowStatus
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 212f9fe8bc7807b9209523564ead716959875241
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="view-workflow-history"></a>Ver historial del flujo de trabajo

[!include [task guide banner](../../includes/task-guide-banner.md)]

Siga estos pasos para ver el estado de un documento que envió al sistema de flujo de trabajo para que se lo procese y apruebe. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.

1. Vaya a Comunes > Consultas > Flujo de trabajo > Historial del flujo de trabajo.
    * Utilice este formulario para ver el estado de un documento que se ha enviado al sistema de flujo de trabajo para procesarlo y aprobarlo.  
    * El Id. de la instancia es 	
el código de identificación de la instancia de flujo de trabajo que está procesando, o ha procesado, el documento.  
    * El Estado es el estado del flujo de trabajo del documento.  
    * El ID del flujo de trabajo es el código de identificación del flujo de trabajo que está procesando, o ha procesado, el documento.  
    * El Documetno es el código de identificación del documento.  
    * El tipo de Documento es el tipo de documento que se envió para su procesamiento.  
    * El Flujo de trabajo es el nombre del flujo de trabajo que está procesando, o ha procesado, el documento.  
    * La Versión es el número de versión del flujo de trabajo que está procesando, o ha procesado, el documento.  
    * La Fecha y hora de creación es la fecha y hora en que se envió el documento.  
    * El Tiempo transcurrido es el tiempo que ha pasado desde que se envió el documento.  
    * El botón de Reanudar le permite que reanudar el proceso del flujo de trabajo para el documento seleccionado.  
    * El botón Recuperar le permite recuperar el documento seleccionado para que no sea procesado.   
2. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Asegúrese de que la sección Elementos de trabajo está expandida.    En esta sección puede ver los elementos de trabajo que se están asociados al documento seleccionado. Por ejemplo, es posible que haya completado una tarea, o que el documento se haya aprobado.  
    * El botón Reasignar abrirá un cuadro de diálogo en el que se puede reasignar un elemento de trabajo a otro usuario.  
    * Asegúrese de que la sección Detalles de seguimiento está expandida.    En esta sección puede ver el historial del flujo de trabajo del documento seleccionado.  


