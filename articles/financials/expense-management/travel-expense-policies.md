---
title: Definir directivas de gastos
description: Puede definir las directivas de gastos que los trabajadores deben seguir al insertar y enviar informes de gastos y pedidos de viaje en Microsoft Dynamics 365 for Finance and Operations.
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysPolicyListPage, TrvPolicyRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 3b2a28fe6acf03e52c292048a797ce997f58bcce
ms.contentlocale: es-es
ms.lasthandoff: 03/26/2018

---

# <a name="expense-policies"></a>Directivas de gastos

[!include [banner](../includes/banner.md)]

Puede definir políticas que deben cumplir sus trabajadores al especificar y enviar informes de gastos y pedidos de viaje.         
Implantar políticas de gastos puede ayudarle a gestionar los gastos de manera eficiente.         

Por ejemplo, puede configurar una directiva que indique que para los gastos en hoteles de Nueva York, el gasto de hotel por noche no puede superar los 250 USD.       
Si un trabajador envía un informe de gastos o un pedido de viaje en los que el precio de la habitación supera este importe, el sistema notificará al        
trabajador que se ha superado el importe de gastos de la política. Puede configurar el mensaje que recibirá el trabajador al        
definir la directiva.      
        
Puede definir tres tipos de directivas:         
        
- Advertencia: permite que el trabajador envíe un informe de gastos o un pedido de viaje, pero el gasto se marcará para todos los aprobadores y para la creación de informes        
  más adelante.        

- Error: requiere que el trabajador revise el gasto para cumplir con la directiva antes de enviar el informe de gastos o el pedido de viaje.       
 
  - Justificación: requiere que el trabajador o un director especifique una justificación para exceder el importe de la directiva antes de enviar el informe de gastos o el pedido de viaje.        
 
  También puede configurar un intervalo de fechas para el que estarán vigentes las directivas de gastos. Por ejemplo, las tarifas aéreas entre Dinamarca      
  y Nueva York pueden resultar caras durante la época de vacaciones. Puede definir una regla de gastos que restrinja el      
  coste de los vuelos a Nueva York a un límite de 5000 DKK y especificar que esta regla estará en vigor del 15 de marzo      
  al 15 de septiembre.

