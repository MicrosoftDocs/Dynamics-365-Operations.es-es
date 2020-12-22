---
title: Deshabilitar reglas en el comprobador de coherencia para transacciones comerciales
description: En este tema se describe la funcionalidad para deshabilitar las reglas del comprobador de coherencia de la transacción en Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 37209f1c1de19335f5f9fa6636ab55dd8b2fccc1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4459877"
---
# <a name="disable-rules-in-the-retail-transaction-consistency-checker"></a>Deshabilitar reglas en el comprobador de coherencia para transacciones comerciales 

[!include [banner](../includes/banner.md)]

Los minoristas pueden tener procesos y escenarios empresariales que son únicos para ellos. Por tanto, no todas las reglas que se incluyen de forma predeterminada en el comprobador de coherencia de transacción de Commerce son aplicables a todos los minoristas. Para adaptar diferencias, Microsoft Dynamics 365 Commerce proporciona una función que se puede usar para deshabilitar las reglas que no se pueden aplicar.

Para ver la lista de reglas disponibles en el comprobador de coherencia de transacción en su entorno y ver el estado de cada regla, vaya a **Venta minorista \> Retail y Commerce \> Parámetros \> Parámetros de Commerce** y seleccione la pestaña **Validación de transacciones**.

De forma predeterminada, el estado de cada regla se establece en **Habilitado**. Por tanto, todas las reglas se utilizan para validar transacciones antes de que se incluyan en los extractos de Commerce. Para deshabilitar una regla, cambie su estado a **Deshabilitado**. No se consideran las reglas deshabilitadas cuando se validan las transacciones durante el proceso de cálculo de extractos.

Para omitir el proceso de validación completo, con independencia de las reglas habilitadas, vaya a **Retail y Commerce \> Configuración de sede central \> Parámetros \> Parámetros de Commerce** y, a continuación, en la pestaña **Validación de transacciones**, establezca la opción **Deshabilitar comprobador de coherencia para transacciones de Commerce** en **Sí**. Después de que esta opción se establezca en **No**, no se podrá volver a establecer en **Sí** desde la interfaz de usuario (IU).
