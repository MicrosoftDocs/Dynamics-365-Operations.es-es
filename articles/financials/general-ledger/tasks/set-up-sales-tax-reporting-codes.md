--- 
title: "Configurar códigos de notificación de impuestos"
description: "Los códigos de notificación de impuestos hacen referencia a un número de campo en un informe de impuestos."
author: twheeloc
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: fa32a12e49b6578c41ceb8991237a19ae3f77e17
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-sales-tax-reporting-codes"></a>Configurar códigos de notificación de impuestos

[!include [task guide banner](../../includes/task-guide-banner.md)]

Los códigos de notificación de impuestos hacen referencia a un número de campo en un informe de impuestos. Se usan en diseños de informe específicos de país y en el pago de impuestos por informe de código para imprimir los importes de impuestos para un período de liquidación resumido por código de notificación. Una vez creados los códigos de notificación de impuestos, puede hacer referencia a ellos en las fichas desplegables- Configuración del informe de la página Código de impuestos. 

Esta grabación usa la empresa de demostración DEMF.



1. Vaya a Impuestos > Configuración > Impuestos > Códigos de notificación de impuestos.
2. Haga clic en Nuevo.
3. Seleccione el diseño del informe al que pertenece el código de notificación.
    * Este diseño se usa para filtrar los códigos de notificación disponibles para un código de impuestos. Cada código de impuestos corresponde a un período de liquidación que pertenece a una autoridad fiscal que usa un diseño de informe.  
4. Especifique un número que haga referencia a un campo del informe de impuestos.
5. En el campo de texto del informe, escriba una descripción para mostrar en los informes.
6. En el campo Descripción breve, escriba una descripción para fines internos.
7. Haga clic en Guardar.


