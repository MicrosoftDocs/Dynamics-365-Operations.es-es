---
title: Deshabilitar las reglas utilizadas en el proceso de validación de transacciones
description: En este artículo se describe la funcionalidad para deshabilitar las reglas de validación de transacciones en Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 12/11/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7d566aa3b829dad281528925a341382f9637fdba
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884887"
---
# <a name="disable-rules-used-in-the-transaction-validation-process"></a>Deshabilitar las reglas utilizadas en el proceso de validación de transacciones

[!include [banner](../includes/banner.md)]

Los minoristas pueden tener procesos y escenarios empresariales que son únicos para ellos. Por tanto, no todas las reglas que se incluyen en el proceso de validación de transacciones de Commerce son aplicables a todos los minoristas. Para adaptar diferencias, Microsoft Dynamics 365 Commerce proporciona funcionalidad que se puede usar para deshabilitar reglas que no se pueden aplicar.

Para ver la lista de reglas que están disponibles en el proceso de validación de transacciones en su entorno, así como para ver el estado de cada regla, vaya a **Retail y Commerce \> Configuración de sede central \> Parámetros\> Parámetros de Commerce** y seleccione la pestaña **Validación de transacciones**. Todas las reglas habilitadas se utilizan para validar transacciones durante el proceso **Validar transacciones de la tienda** y deben pasar para que las transacciones se recopilen y registren en un extracto transaccional.

De forma predeterminada, el estado de cada regla se establece en **Habilitado**. Por tanto, todas las reglas se utilizan para validar transacciones antes de que se puedan incluir en los extractos transaccionales de Commerce. Para deshabilitar una regla, cambie su estado a **Deshabilitado**. Las reglas deshabilitadas no se consideran cuando se validan las transacciones durante el proceso **Validar transacciones de la tienda**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
