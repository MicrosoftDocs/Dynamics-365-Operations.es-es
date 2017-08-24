--- 
title: "Configuración de secuencias numéricas mediante asistente"
description: "Las secuencias numéricas se usan para generar identificadores únicos y legibles para los registros de datos maestros y los registros de transacciones que los necesitan."
author: sericks007
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 5fe6e54b4ebcf6cd611af54e7066a3e39d0e677d
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-number-sequences-by-using-a-wizard"></a>Configuración de secuencias numéricas mediante asistente

[!include[task guide banner](../../includes/task-guide-banner.md)]

Las secuencias numéricas se usan para generar identificadores únicos y legibles para los registros de datos maestros y los registros de transacciones que los necesitan. El registro de datos maestros o de transacciones que necesita un identificador se denomina referencia. Antes de poder crear nuevos registros para una referencia, debe configurar una secuencia numérica y asociarla a la referencia. Este procedimiento explica cómo configurar todas las secuencias numéricas necesarias al mismo tiempo mediante un asistente. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.

1. Vaya a Administración de la organización > Secuencias numéricas > Secuencias numéricas.
2. Haga clic en Generar.
3. Haga clic en Siguiente.
    * En esta página, puede modificar el código de identificación, el valor más bajo y el valor más alto. Además, puede indicar si la secuencia numérica debe ser continua.   
    * No seleccione la opción Continuo si debe preasignar números para la secuencia numérica.     Para agregar un segmento de ámbito al formato de una secuencia numérica, seleccione el formato en la lista y, a continuación, haga clic en Incluir ámbito en el formato.     Para quitar un segmento de ámbito del formato de una secuencia numérica, seleccione el formato en la lista y, a continuación, haga clic en Quitar ámbito del formato.     Para excluir una secuencia numérica de la generación automática, seleccione la secuencia numérica en la lista y, a continuación, haga clic en Eliminar.  
4. Haga clic en Siguiente.
5. Haga clic en Finalizar.


