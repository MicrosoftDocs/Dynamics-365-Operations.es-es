---
title: Crear un elemento de menú del dispositivo móvil para la consolidación del número de matrícula
description: Este procedimiento muestra cómo crear un elemento de menú del dispositivo móvil para el trabajo de consolidación de la matrícula de entidad.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b3f5f572461de007f137ffa7ea05c535371f95b7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977247"
---
# <a name="create-a-mobile-device-menu-item-for-license-plate-consolidation"></a>Crear un elemento de menú del dispositivo móvil para la consolidación del número de matrícula

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo crear un elemento de menú del dispositivo móvil para el trabajo de consolidación de la matrícula de entidad. Esto permite a los trabajadores del almacén consolidar artículos de una matrícula de entidad de almacén con los artículos de otra matrícula de entidad de almacén dentro de la misma ubicación. Por ejemplo, es posible que utilicen esto si los pasos subsiguientes fueran iguales en ambos pedidos de trabajo, de modo que el trabajo sólo deba realizarse para los artículos combinados. Puede utilizar este procedimiento en la empresa de datos de demostración USMF. La tarea la realizará normalmente el responsable del almacén. Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.

1. Vaya a Gestión de almacenes > Configurar > Dispositivo móvil > Elementos de menú del dispositivo móvil.
2. Haga clic en Nuevo.
3. En el campo Nombre del elemento de menú, escriba un valor.
4. En el campo Título, escriba un valor.
5. En el campo Modo, seleccione "Indirecto".
6. En el campo Código de actividad, seleccione "Consolidar matrículas".

