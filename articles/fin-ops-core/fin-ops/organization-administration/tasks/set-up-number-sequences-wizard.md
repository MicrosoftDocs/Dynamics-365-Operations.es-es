---
title: Configurar secuencias numéricas mediante un asistente
description: En ese artículo se explica cómo configurar todas las secuencias numéricas necesarias al mismo tiempo mediante un asistente.
author: SunilGarg
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceWizard
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cae739aad1166eee1abebe3c0adc7939bca55bc4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847074"
---
# <a name="set-up-number-sequences-using-a-wizard"></a>Configurar secuencias numéricas mediante un asistente

[!include [banner](../../includes/banner.md)]

Las secuencias numéricas se usan para generar identificadores únicos y legibles para los registros de datos maestros y los registros de transacciones que los necesitan. El registro de datos maestros o de transacciones que necesita un identificador se denomina referencia. Para poder crear nuevos registros para una referencia, debe configurar una secuencia numérica y asociarla a la referencia. En ese artículo se explica cómo configurar todas las secuencias numéricas necesarias al mismo tiempo mediante un asistente. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.

1. Vaya a **Navegación > Módulos > Administración de la organización > Secuencias numéricas > Secuencias numéricas**.
2. Seleccione **Generar**.
3. Seleccione **Siguiente**.

   - En esta página, puede modificar el código de identificación, el valor más bajo y el valor más alto. Además, puede indicar si la secuencia numérica debe ser continua.   
   - No seleccione la opción **Continuo** si debe preasignar números para la secuencia numérica. Para agregar un segmento de ámbito al formato de una secuencia numérica, seleccione el formato en la lista y, a continuación, seleccione **Incluir ámbito en el formato**. Para quitar un segmento de ámbito del formato de una secuencia numérica, seleccione el formato en la lista y, a continuación, seleccione **Quitar ámbito del formato**. Para excluir una secuencia numérica de la generación automática, seleccione la secuencia numérica en la lista y, a continuación, seleccione **Eliminar**.  

4. Seleccione **Siguiente**.
5. Seleccione **Fin**.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
