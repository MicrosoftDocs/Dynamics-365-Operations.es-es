---
title: Verifique que la doble escritura esté configurada en aplicaciones Finance and Operations y Common Data Service
description: Este tema explica cómo puede determinar si la escritura doble está configurada en aplicaciones Finance and Operations y en Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 2ddac76871a3ac574a1edcb5446be6c64e5e4682
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997239"
---
# <a name="verify-that-dual-write-is-configured-in-finance-and-operations-apps-and-common-data-service"></a>Verifique que la doble escritura esté configurada en aplicaciones Finance and Operations y Common Data Service

[!include [banner](../../includes/banner.md)]



Este tema proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Common Data Service. Específicamente explica cómo puede determinar si la escritura doble está configurada en aplicaciones Finance and Operations y en Common Data Service.

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a>Verifique que la doble escritura esté configurada en una aplicación Finance and Operations

Para determinar si los errores que ve cuando intenta guardar registros para la actualización provienen de doble escritura, primero verifique que la doble escritura esté configurada.

+ Si tiene privilegios de administrador en la aplicación Finance and Operations, vaya a **Espacios de trabajo \> Gestión de datos** y seleccione el mosaico **Doble escritura**. Si se muestran los detalles de los entornos vinculados y la lista de mapas de entidades que se están ejecutando, se configura la escritura doble.

    ![Comprobar la conexión de la aplicación Finance and Operations con privilegios de administrador](media/verify_fin_ops_1.png)

+ Si no tiene privilegios de administrador, aparecerá un mensaje de error: *No se pueden escribir datos en la entidad nombre de la entidad \<entity name\>*. En el ejemplo de la siguiente ilustración, no puede crear un registro de cliente en la aplicación Finance and Operations, porque la escritura doble está configurada, pero el grupo de clientes y los datos de referencia de términos de pago no existen en Common Data Service.

    ![Verificando la conexión de la aplicación Finance and Operations cuando no tiene privilegios de administrador](media/verify_fin_ops_2.png)

Para obtener información sobre cómo solucionar problemas al crear datos en aplicaciones Finance and Operations, consulte [Solucionar problemas de sincronización en vivo](dual-write-troubleshooting-live-sync.md).

## <a name="verify-that-dual-write-is-configured-in-common-data-service"></a>Verifique que la doble escritura esté configurada en Common Data Service

Cuando crea datos, si ve el campo **Empresa** en páginas en Common Data Service, la doble escritura está configurada.

![Verificando la conexión Common Data Service](media/verify_cds.png)

Para obtener información sobre cómo solucionar problemas al crear datos en Common Data Service, consulte [Solucionar problemas de sincronización en vivo](dual-write-troubleshooting-live-sync.md).

Para obtener información sobre cómo ver los detalles del error si encuentra algún error mientras crea datos en Common Data Service, consulte [Habilitar y ver el inicio de sesión de seguimiento del complemento Common Data Service para ver detalles del error](dual-write-troubleshooting.md#enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details).
