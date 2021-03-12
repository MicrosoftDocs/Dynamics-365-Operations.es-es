---
title: Gestión de reparaciones
description: Agrupe los problemas sistemáticamente como ayuda para la sugerencia de soluciones que han resuelto el problema correctamente en el pasado.
author: ShylaThompson
manager: tfehr
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAConditionTable, SMASymptomArea, SMADiagnosisArea, SMAResolutionTable, SMARepairStage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8ebb9833be5e51fe59e9895e67cd8e55058078aa
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001358"
---
# <a name="repair-management"></a>Gestión de reparaciones       

[!include [banner](../includes/banner.md)]


Para la gestión de reparaciones puede agrupar problemas sistemáticamente. Esto se hace con el fin de contribuir a la sugerencia de soluciones que han resuelto el problema correctamente en el pasado.

Configura los síntomas, el diagnóstico y la resolución. Todos estos valores se pueden aplicar posteriormente cuando recibe un artículo similar para reparación. También puede establecer etapas de reparación que pueden realizar el seguimiento del progreso de un problema de reparación.

## <a name="setting-up-repair-management"></a>Configuración de la gestión de reparaciones

Use los siguientes formularios de configuración para escribir información que se usará para especificar los síntomas, el diagnóstico y la resolución de la reparación.

1.  Haga clic en **Gestión de servicio** \> **Configuración** \> **Reparación** \> **Condiciones**.

2.  Haga clic en **Gestión de servicio** \> **Configuración** \> **Reparación** \> **Áreas de síntoma**.

3.  Haga clic en **Gestión de servicio** \> **Configuración** \> **Reparación** \> **Áreas de diagnóstico**.

4.  Haga clic en **Gestión de servicio** \> **Configuración** \> **Reparación** \> **Resoluciones**.

5.  Haga clic en **Gestión de servicio** \> **Configuración** \> **Reparación** \> **Etapas de reparación**.

## <a name="symptoms-and-conditions"></a>Síntoma y condiciones

Los síntomas representan cómo el cliente caracteriza el problema. Incluyen las observaciones del cliente que indican la necesidad de una reparación.

Puede establecer áreas y códigos de síntomas, así como condiciones. El área de síntomas cubre el área de funcionamiento defectuoso y el código de síntoma cubre el síntoma del funcionamiento defectuoso. La condición describe la situación o el entorno que está presente cuando se produce el problema.

**Ejemplo**

Se recibe un equipo para su reparación debido a un error en la unidad de disco duro tras un amplio período de uso. El error de la unidad de disco duro hace que la pantalla se quede azul. El técnico que recibe el equipo introduce los siguientes síntomas y condiciones:

1.  El área de síntoma es la unidad de disco duro.

2.  El código de síntoma es el error de pantalla azul.

3.  La condición es que se produce un error en el disco duro tras un gran uso.

## <a name="diagnosis-and-resolutions"></a>Diagnósticos y resoluciones

Los campos de diagnósticos y resoluciones son declaraciones desde el punto de vista de la reparación. Se trata de los pasos que ha realizado el técnico para investigar el problema.

El área de diagnósticos cubre la operación que se debe producir para resolver el tema. El código de diagnóstico es cómo se trató el problema y la resolución podría ser que el artículo se reparó, se sustituyó, o que el cliente canceló el pedido. Por ejemplo, si se repara el equipo, el área de diagnósticos sería "pieza defectuosa", el código de diagnóstico podría ser "nueva tarjeta gráfica instalada" y la resolución podría ser "sustituida".

## <a name="repair-stages"></a>Etapas de reparación

Las etapas de reparación indican el progreso del proceso de reparación. La etapa de reparación dispone de un parámetro de aprobación final **Finalizada** que indica que se ha completado la línea de reparación y que se han registrado la fecha y hora de finalización.

## <a name="applying-repair-management"></a>Aplicación de la gestión de reparaciones

Para aplicar la gestión de reparaciones a un artículo, este último deberá establecerse con una relación de objetos de servicio en un pedido de servicio. Desde el pedido de servicio, podrá crear una línea de reparación con la información acerca del problema actual. En la línea de reparación, se define el objeto de servicio que se está reparando y la información acerca de los síntomas, los diagnósticos y la ejecución. También puede crear una nota para ella.

Puede crear líneas de reparación para cada etapa del proceso de reparación.

## <a name="create-a-repair-line-on-a-service-order"></a>Crear una línea de reparación en el pedido de servicio

1.  Haga clic en **Gestión de servicio** \> **Común** \> **Pedidos de servicio** \> **Pedidos de servicio**.

2.  Seleccione el pedido de servicio con el objeto de servicio que necesita reparación.

3.  Haga clic en **Reparar** \> **Líneas de reparación** para abrir el formulario **Líneas de reparación**.

4.  Presione CTRL+N para crear una nueva línea.

5.  Seleccione un objeto de servicio. Puede seleccionar cualquier objeto establecido con una relación de objetos en el pedido de servicio.

6.  Seleccione los valores de síntomas, diagnósticos y ejecución predefinidos pertinentes para la línea de reparación y, a continuación, haga clic en la ficha **Nota** para crear una nota en la línea de reparación, si fuera necesario.

7.  Presione CTRL+S para guardar la nueva línea de reparación. El campo **Fecha y hora de creación** de la ficha **General** del formulario **Líneas de reparación** se actualiza con la hora en la que se guardaron los cambios.

## <a name="tracking-progress-and-resolving-a-repair-issue"></a>Realizar un seguimiento del progreso y resolver un problema de reparación

Puede establecer etapas de reparación de una línea de reparación con el fin de realizar un seguimiento del progreso de la reparación.

Cuando se resuelve un problema de reparación, puede cerrar la línea de reparación. Defina la etapa de reparación en una etapa con una propiedad **Finalizada** habilitada. La fecha y hora actuales se registran como el momento de finalización en la línea.

## <a name="close-a-repair-line-for-a-resolved-issue"></a>Cerrar una línea de reparación para un problema resuelto

1.  Abra el formulario **Líneas de reparación**. Siga el procedimiento anterior para la creación de una línea de reparación para abrir el formulario.

2.  Seleccione la línea de reparación con el problema de reparación que desee cerrar.

3.  En el campo **Etapa de reparación**, seleccione una etapa con la propiedad **Finalizada** habilitada.

  


