---
title: Definir programaciones de continuidad
description: Este tema explica la configuración de un programa de continuidad (conocido también como pedidos recurrentes).
author: josaw1
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: MCRContinuitySchedule, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8414377ddec0e001f003f842866725eb58bd75a3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791616"
---
# <a name="define-continuity-schedules"></a>Definir programaciones de continuidad

[!include [banner](../includes/banner.md)]

Este tema explica la configuración de un programa de continuidad (conocido también como pedidos recurrentes). Este tema usa la empresa USRT en los datos de demostración.


## <a name="create-continuity-program"></a>Crear un programa de continuidad
1. Vaya a Retail y Commerce > Continuidad > Programas de continuidad.
2. Haga clic en Nuevo.
3. En el campo Id. de programación, escriba el Id. de programación de continuidad.
4. En el campo Inicio del pedido, seleccione "Primer evento".
    * Si un cliente realiza un pedido nuevo del programa de continuidad, hay dos opciones para las que el producto será enviado:  1. Primer evento: el primer producto en el programa de la continuidad se enviará.  2. Evento actual: el producto actual se enviará. Por ejemplo: tras tres meses en el programa, el cliente recibirá el tercero en el programa.  
5. Seleccione "Sí" para solicitar la fecha de inicio del pedido.
6. Haga clic en Agregar línea.
7. En el campo Número de artículo, escriba el número de artículo del primer producto ("0013").
8. Tipo "CP".
9. Escriba la fecha en que el primer producto esté disponible para el pedido.
10. Haga clic en Agregar línea.
11. En el campo Código de artículo, escriba "0014".
12. En el campo Código de intervalo de fechas, borre el valor para que el campo esté vacío.
    * Para este procedimiento, desactive el intervalo de fechas. Establecerá la fecha como incremental desde la fecha de inicio del primer artículo.  
13. Aquí puede escribir el intervalo en el que se envían los productos. Tipo "30".
    * Para un programa mensual, puede especificar 30 días para el intervalo.  
14. Haga clic en Agregar línea.
15. En el campo Código de artículo, escriba "0015".
16. Tipo "Fin".
17. Haga clic en Guardar.

## <a name="assign-to-continuity-item"></a>Asignar al artículo de continuidad
1. Vaya a Gestión de información de productos > Productos > Productos emitidos.
2. Seleccionar artículo "0016".
    * Para este procedimiento, seleccionará el número de artículo 0016. Normalmente, se habrá creado un producto liberado con una lógica de negocios de continuidad adicional aplicada cuando se coloca en un pedido de ventas en el centro de llamadas.  
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. Haga clic en Editar.
5. Expanda o contraiga la sección Vender.
6. Aquí puede escribir el programa de continuidad que representa este artículo. Especifique el Id. de programación que creó anteriormente.
    * Cuando este artículo se vende en un centro de llamadas, la lógica de negocios adicional se aplica desde el programa de continuidad seleccionado.  
7. Haga clic en Guardar.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]