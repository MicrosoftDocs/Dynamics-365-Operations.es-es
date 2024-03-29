---
title: Definir puntos de recompensa de fidelización
description: Este procedimiento le muestra la definición de puntos de recompensa de fidelización.
author: josaw1
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.industry: Retail
ms.search.form: RetailLoyaltyRewardPoints
ms.openlocfilehash: 9acd1429d17393f19a5e059b90a48b0b103535d3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268902"
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



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
