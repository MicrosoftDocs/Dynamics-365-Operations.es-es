---
title: Procesamiento de devoluciones para pago
description: Este procedimiento muestra cómo convertir en notas de abono devoluciones de cliente aprobadas y procesadas.
author: Henrikan
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ce813f0f5d9aa750828b524dd9fdf9b4a9f0854
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572490"
---
# <a name="process-rebates-for-payment"></a>Procesamiento de devoluciones para pago

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo convertir en notas de abono devoluciones de cliente aprobadas y procesadas. Puede ejecutar este procedimiento en la empresa de demostración USMF. La condición previa para este procedimiento es tener una o más reclamaciones de devolución con estado Marcar. Si está usando USMF, debe ejecutar el procedimiento "Generación y procesamiento de devoluciones de cliente" antes de comenzar este procedimiento.


## <a name="convert-rebate-claims-to-credit-note"></a>Conversión de reclamaciones de devolución en notas de abono
1. Vaya a Todos los clientes.
2. En la lista, busque y seleccione el registro deseado.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. En el panel de acciones, haga clic en Cobrar.
5. Haga clic en Liquidar transacciones.
6. Haga clic en Funciones.
7. Haga clic en Programa de devoluciones.
    * La página Devolución muestra las reclamaciones de devolución que ha procesado en el área de trabajo de devoluciones de cliente y que se encuentran en estado Marcar.    
8. Haga clic en Editar.
    * Defina las marcas de verificación del campo Marcar para las reclamaciones que desee incluir en nota de abono.   
9. Haga clic en Funciones.
10. Haga clic en Crear nota de abono.
    * Aparece un mensaje para informarle de que se ha registrado un diario (este es el diario de consumo de clientes, como se haya especificado en la página de parámetros de clientes). Esto hace que el importe real de pasivos (crédito) se desplace al saldo del cliente. Esto significa que se ha abonado la cuenta del cliente, y que se ha adeudado la cuenta de acumulación de devoluciones.  
11. Cierre la página.
12. Haga clic en Cancelar.
    * Esto actualiza la página para que pueda ver las actualizaciones.  
13. En el panel de acciones, haga clic en Cobrar.
14. Haga clic en Liquidar transacciones.
    * Observe cómo se ha agregado al saldo del cliente una transacción por un importe negativo, el cual representa el importe de devolución total, sin referencia de factura.   
15. Haga clic en Cancelar.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]