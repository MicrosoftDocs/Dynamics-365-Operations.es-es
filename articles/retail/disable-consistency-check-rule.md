---
title: Deshabilitar reglas en el comprobador de coherencia para transacciones comerciales
description: Este tema describe la funcionalidad para deshabilitar las reglas del comprobador de coherencia de transacción comercial en Microsoft Dynamics 365 Retail.
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
ms.openlocfilehash: 4bf8df2fb9f8f5c33ceb13eb012fb6879f81ec66
ms.sourcegitcommit: bdbca89bd9b328c282ebfb681f75b8f1ed96e7a8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2019
ms.locfileid: "2586306"
---
# <a name="disable-rules-in-the-retail-transaction-consistency-checker"></a>Deshabilitar reglas en el comprobador de coherencia para transacciones comerciales 

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Los minoristas pueden tener procesos y escenarios empresariales que son únicos para ellos. Por tanto, no todas las reglas que se incluyen de forma predeterminada en el comprobador de coherencia de transacción comercial son aplicables a todos los minoristas. Para adaptar diferencias, Microsoft Dynamics 365 Retail proporciona una función que se puede usar para deshabilitar las reglas que no se pueden aplicar.

Para ver la lista de reglas disponibles en el comprobador de coherencia de transacción comercial en su entorno y ver el estado de cada regla, vaya a **Venta minorista \> Configuración de sede central \> Parámetros \> Parámetros comerciales** y seleccione la pestaña **Validación de transacciones**.

De forma predeterminada, el estado de cada regla se establece en **Habilitado**. Por tanto, todas las reglas se utilizan para validar transacciones comerciales antes de que se incluyan en los extractos comerciales. Para deshabilitar una regla, cambie su estado a **Deshabilitado**. No se consideran las reglas deshabilitadas cuando se validan las transacciones comerciales durante el proceso de cálculo de extractos.

Para omitir el proceso de validación completo, con independencia de las reglas habilitadas, vaya a **Venta minorista \> Configuración de sede central \> Parámetros \> Parámetros comerciales** y, a continuación, en la pestaña **Validación de transacciones**, establezca la opción **Deshabilitar comprobador de coherencia para transacciones comerciales** en **Sí**. Después de que esta opción se establezca en **No**, no se podrá volver a establecer en **Sí** desde la interfaz de usuario (IU).
