---
title: Definir puntos de recompensa de fidelización
description: Este procedimiento le muestra la definición de puntos de recompensa de fidelización.
author: scott-tucker
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailLoyaltyRewardPoints
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: af217a5e756db571e3e351b743aa44b842f478f1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000493"
---
# <a name="define-loyalty-reward-points"></a>Definir puntos de recompensa de fidelización

[!include [banner](../includes/banner.md)]

Este procedimiento le muestra la definición de puntos de recompensa de fidelización. Debe configurar puntos de recompensa de fidelización antes de configurar un programa de fidelización. Este procedimiento usa la empresa de datos de demostración USRT.

1. Vaya a Retail y Commerce > Clientes > Fidelidad > Puntos de recompensa de fidelización.
2. Haga clic en Nuevo.
3. En el campo Id. de punto de recompensa, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. En el campo Tipo de punto de recompensa, seleccione una opción.
    * Seleccione la cantidad si desea que los puntos de recompensa se redondeen al entero más próximo. Seleccione Importe si desea que los puntos de recompensa se redondeen según las reglas de redondeo de divisas. Si selecciona Cantidad, omita el paso siguiente de este procedimiento.  
6. En el campo Divisa, escriba un valor.
    * Para los puntos de recompensa de tipo de importe, todos los puntos emitidos tendrán la divisa seleccionada. Para los puntos de recompensa del tipo de cantidad, no se aplica este campo; omita este paso.  
7. Active o desactive la casilla Canjeable.
8. En el campo Clasificación de canjes, escriba un número.
    * Se usa Clasificación de canjes cuando se pueden usar dos o más puntos de recompensa canjeables para pagar productos. Si los dos puntos de recompensa tienen la misma clasificación de canjes, se usará el que necesita reducir el número de puntos.  
9. En el campo Valor de tiempo de vencimiento, escriba un número.
    * Los puntos de recompensa expirarán el número especificado de días, semanas, meses o años tras la emisión de los puntos. Un valor de "0" significa que nunca expirarán los puntos de recompensa de fidelización.  
10. En el campo Unidad de tiempo de vencimiento, seleccione una opción.
11. Haga clic en Guardar.

