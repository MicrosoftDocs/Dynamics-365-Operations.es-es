---
title: Definir directivas de gastos
description: Se pueden definir políticas de gastos que deben cumplir sus trabajadores al especificar y enviar informes de gastos y pedidos de viaje en Microsoft Dynamics 365 Finance.
author: ryansandness
manager: AnnBe
ms.date: 04/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicyListPage, TrvPolicyRule
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7d3b4a8f6cf74bb1fe7e53a4dfdd607f604e16e3
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187461"
---
# <a name="define-expense-policies"></a>Definir directivas de gastos

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

## <a name="policy-tips"></a>Consejos de directiva
Aquí hay algunas sugerencias que pueden ayudarle cuando cree nuevas directivas para la gestión de gastos. 
* Las directivas son entran en vigor por fecha y no surtirán efecto si la directiva se crea con una fecha posterior a la fecha que el gasto produjo. Por ejemplo, si crea una nueva directiva hoy para aplicar un gasto máximo de comida de 50 €, ningún gasto existente especificado ayer no será comprobado con esta directiva.
* Al crear una directiva para una categoría de gastos que se pueda detallar, considere agregar una condición para el tipo de línea de gastos. Algunas directivas como requerir un recibo puede que no tengan sentido para las líneas detalladas y se deben aplicar únicamente a la línea de encabezado o línea no detallada. 

## <a name="when-to-evaluate-policies"></a>Cuándo evaluar directivas

En parámetros de gestión de gastos, hay una opción para evaluar cualquier directiva de gestión de gastos cuando se guarda una línea o cuando se envía un informe de gastos. Si elige evaluar cuando se guarda una línea, esto garantiza que los usuarios tengan visibilidad anterior en lo que necesitan hacer para completar su informe de gastos de una vez. Si no, se puede retrasar la evaluación de la directiva y ahorrar tiempo si hace que la validación aparezca al final, durante el envío al flujo de trabajo.
