---
title: Comprar y vender bajas
description: Este artículo describe cómo enviar solicitudes para comprar y vender sin permiso Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ESSLeaveBuyRequestEntry, EssWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a6d38a69a73ce14f099beb6b6b560bf6c5686b0c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875724"
---
# <a name="buy-and-sell-leave"></a>Comprar y vender bajas


>[!Important]
>La funcionalidad mencionada en este artículo está disponible actualmente para los clientes de Dynamics 365 Human Resources independiente. Algunas o todas las funciones estarán disponibles como parte de una versión futura de la infraestructura de Finance después de la versión 10.0.26 de Finance.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

En Dynamics 365 Human Resources, puede enviar solicitudes para comprar y vender licencias según las políticas de compra y venta de licencias establecidas por su empresa.  

## <a name="request-to-buy-leave"></a>Solicitud para comprar baja

1. En el espacio de trabajo **Autoservicio de empleados**, seleccione **Solicitar compra de baja** en el icono **Saldos de permisos**. 

2. Agregue un **Tipo de baja** e introduzca un **Importe** por la cantidad de baja que le gustaría comprar. 

3. Seleccione **Enviar** cuando esté listo para enviar su solicitud. 

Sus saldos se actualizarán automáticamente o pasarán por un proceso de aprobación antes de actualizarse. Esto depende de cómo se haya configurado la política de compra.

## <a name="request-to-sell-leave"></a>Solicitud para vender baja

1. En el espacio de trabajo **Autoservicio de empleados**, seleccione **Solicitar venta de baja** en el icono **Saldos de permisos**. 

2. Agregue un **Tipo de baja** e introduzca un **Importe** por la cantidad de baja que le gustaría vender. 

3. Seleccione **Enviar** cuando esté listo para enviar su solicitud.

Sus saldos se actualizarán automáticamente o pasarán por un proceso de aprobación antes de actualizarse. Esto depende de cómo se haya configurado la política de compra.


## <a name="troubleshooting"></a>Solución de problemas 

Si falla un flujo de trabajo de solicitud de licencia de compra o venta, los usuarios con el privilegio **EssLeaveBuySellRequestApprover** puede revisar el registro de mensajes para todas las solicitudes de compra y venta de licencias. Para hacer esto, vaya a **Licencias y ausencias > Enlaces > Compra y venta de solicitudes de licencia> Registro de mensajes** (arriba a la izquierda). **Registro de mensajes** muestra a los usuarios cómo se procesaron las transacciones y el historial de flujo de trabajo asociado.


## <a name="see-also"></a>Consulte también

[Visión general de bajas y ausencias](hr-leave-and-absence-overview.md)</br>
[Gestionar directivas de compra y venta de bajas](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
