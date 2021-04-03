---
title: Configurar secuencias numéricas mediante un asistente
description: En ese tema se explica cómo configurar todas las secuencias numéricas necesarias al mismo tiempo mediante un asistente.
author: sericks007
manager: AnnBe
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceWizard
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b79924e2c8d94b5e5e160a123e9b0cde0971fd96
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560492"
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



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]