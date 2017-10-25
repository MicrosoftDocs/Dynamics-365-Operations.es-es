---
title: Definir directivas de gastos
description: Puede definir las directivas de gastos que los trabajadores deben seguir al insertar y enviar informes de gastos y pedidos de viaje en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.
author: saraschi2
manager: AnnBe
ms.date: 09/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.search.region: Global
ms.author: saraschi2
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 940d6f8c3d878c2c12806ad04a092856df2acb33
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="expense-policies"></a>Directivas de gastos

[!include[banner](../includes/banner.md)]

Puede definir políticas que deben cumplir sus trabajadores al especificar y enviar informes de gastos y pedidos de viaje. Implantar políticas de gastos puede ayudarle a gestionar los gastos de manera eficiente. 

Por ejemplo, puede configurar una directiva que indique que para los gastos en hoteles de Nueva York, el gasto de hotel por noche no puede superar los 250 USD. Si un empleado envía un informe de gastos o una solicitud de viaje en el cual la tarifa de la habitación supera este importe, el sistema notificará al usuario que ha superado el importe de gastos de la directiva. Puede configurar el mensaje que recibirá el trabajador al definir la directiva. 

Puede definir tres tipos de directivas: 

 - Advertencia: permite que el trabajador envíe un informe de gastos o un pedido de viaje, pero el gasto se marcará para todos los aprobadores y para la creación de informes  
 más adelante. 
 - Error: requiere que el trabajador revise el gasto para cumplir con la directiva antes de enviar el informe de gastos o el pedido de viaje. 
 - Justificación: requiere que el trabajador o un director especifique una justificación para exceder el importe de la directiva antes de enviar el informe de gastos o el pedido de viaje. 

También puede configurar un intervalo de fechas para el que estarán vigentes las directivas de gastos. Por ejemplo, las tarifas aéreas entre Dinamarca y Nueva York pueden resultar caras durante la época de vacaciones. Puede definir una regla de gastos de vuelos que restrinja el coste de los vuelos a la ciudad de Nueva York a un límite de 5000 DKK y especificar que esta regla estará en vigencia desde el 15 de marzo hasta el 15 de septiembre. 
