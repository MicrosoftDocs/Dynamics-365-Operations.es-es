--- 
title: "Configurar las recomendaciones del producto accionadas por el aprendizaje automático"
description: "Este procedimiento actualiza los datos en el almacén de entidades que han sido usados por el sistema de aprendizaje automático que acciona las recomendaciones de producto, y, a continuación, habilita las recomendaciones de producto en los clientes de PDV."
author: ashishmsft
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 277ffb879b80fe57deeaa2b52c1543baaf820274
ms.contentlocale: es-es
ms.lasthandoff: 02/07/2018

---
# <a name="configure-machine-learning-powered-product-recommendations"></a>Configurar las recomendaciones del producto accionadas por el aprendizaje automático

[!INCLUDE [task guide banner](../includes/task-guide-banner.md)]

Este procedimiento actualiza los datos en el almacén de entidades que han sido usados por el sistema de aprendizaje automático que acciona las recomendaciones de producto, y, a continuación, habilita las recomendaciones de producto en los clientes de PDV. Este procedimiento usa la empresa USRT en los datos de demostración.

1. Vaya a administración del Sistema > Configuración > Almacén de entidades.
2. En la lista, busque y seleccione el registro "RetailSales".
3. Haga clic en Actualizar.
4. Haga clic en Aceptar
5. Cierre la página.
6. Vaya a Venta minorista y comercio > Configuración de sede central > Parámetros > Parámetros comerciales.
7. Haga clic en la pestaña del aprendizaje automático.
8. Seleccione "Sí" en el campo Habilitar recomendaciones de producto.
    * Si recibe el mensaje “No se pueden recuperar los modelos de recomendación”, significa que ha actualizado el almacén de entidades muy recientemente y es posible que el sistema no haya terminado de asimilar los nuevos datos. Espere entre 2-3 horas y vuelva a intentarlo.  
9. Haga clic en Guardar.
10. Cierre la página.


