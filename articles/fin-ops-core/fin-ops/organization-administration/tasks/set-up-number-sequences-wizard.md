---
title: Configurar secuencias numéricas mediante un asistente
description: En ese tema se explica cómo configurar todas las secuencias numéricas necesarias al mismo tiempo mediante un asistente.
author: sericks007
manager: AnnBe
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceWizard
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 76dc32f2254ffd2a2e33eef594d6e602092bcb6f
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140516"
---
# <a name="set-up-number-sequences-using-a-wizard"></a>Configurar secuencias numéricas mediante un asistente

[!include [banner](../../includes/banner.md)]

Las secuencias numéricas se usan para generar identificadores únicos y legibles para los registros de datos maestros y los registros de transacciones que los necesitan. El registro de datos maestros o de transacciones que necesita un identificador se denomina referencia. Para poder crear nuevos registros para una referencia, debe configurar una secuencia numérica y asociarla a la referencia. En ese tema se explica cómo configurar todas las secuencias numéricas necesarias al mismo tiempo mediante un asistente. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.

1. Vaya a **Navegación > Módulos > Administración de la organización > Secuencias numéricas > Secuencias numéricas**.
2. Seleccione **Generar**.
3. Seleccione **Siguiente**.

   - En esta página, puede modificar el código de identificación, el valor más bajo y el valor más alto. Además, puede indicar si la secuencia numérica debe ser continua.   
   - No seleccione la opción **Continuo** si debe preasignar números para la secuencia numérica. Para agregar un segmento de ámbito al formato de una secuencia numérica, seleccione el formato en la lista y, a continuación, seleccione **Incluir ámbito en el formato**. Para quitar un segmento de ámbito del formato de una secuencia numérica, seleccione el formato en la lista y, a continuación, seleccione **Quitar ámbito del formato**. Para excluir una secuencia numérica de la generación automática, seleccione la secuencia numérica en la lista y, a continuación, seleccione **Eliminar**.  

4. Seleccione **Siguiente**.
5. Seleccione **Fin**.

