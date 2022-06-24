---
title: Comprobar configuración de doble escritura en aplicaciones de finanzas y operaciones y Dataverse
description: Este artículo explica cómo puede determinar si la escritura doble está configurada en aplicaciones Finanzas y operaciones y en Dataverse.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 7131e6c2c4ca4d9c6bb84ad74bf425faf28bd92c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884470"
---
# <a name="verify-dual-write-configuration-in-finance-and-operations-apps-and-dataverse"></a>Comprobar configuración de doble escritura en aplicaciones de finanzas y operaciones y Dataverse

[!include [banner](../../includes/banner.md)]





Este artículo proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de finanzas y operaciones y Dataverse. Específicamente explica cómo puede determinar si la escritura doble está configurada en aplicaciones Finanzas y operaciones y en Dataverse.

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a>Verifique que la doble escritura esté configurada en una aplicación Finance and Operations

Para determinar si los errores que ve cuando intenta guardar filas para la actualización provienen de doble escritura, primero verifique que la doble escritura esté configurada.

+ Si tiene privilegios de administrador en la aplicación Finance and Operations, vaya a **Espacios de trabajo \> Gestión de datos** y seleccione el mosaico **Doble escritura**. Si se muestran los detalles de los entornos vinculados y la lista de mapas de tablas que se están ejecutando, se configura la escritura doble.

    ![Comprobar la conexión de la aplicación Finance and Operations con privilegios de administrador.](media/verify_fin_ops_1.png)

+ Si no tiene privilegios de administrador, aparecerá un mensaje de error: *No se pueden escribir datos en la entidad nombre de la entidad \<entity name\>*. En el ejemplo de la siguiente ilustración, no puede crear una fila de cliente en la aplicación Finanzas y operaciones, porque la escritura doble está configurada, pero el grupo de clientes y los datos de referencia de términos de pago no existen en Dataverse.

    ![Verificando la conexión de la aplicación Finance and Operations cuando no tiene privilegios de administrador.](media/verify_fin_ops_2.png)

Para obtener información sobre cómo solucionar problemas al crear datos en aplicaciones Finance and Operations, consulte [Solucionar problemas de sincronización en vivo](dual-write-troubleshooting-live-sync.md).

## <a name="verify-that-dual-write-is-configured-in-dataverse"></a>Verifique que la doble escritura esté configurada en Dataverse

Cuando crea datos, si ve la columna **Empresa** en páginas en Dataverse, la doble escritura está configurada.

![Verificando la conexión Dataverse.](media/verify_cds.png)

Para obtener información sobre cómo solucionar problemas al crear datos en Dataverse, consulte [Solucionar problemas de sincronización en vivo](dual-write-troubleshooting-live-sync.md).

Para obtener información sobre cómo ver los detalles del error si encuentra algún error mientras crea datos en Dataverse, consulte [Habilitar y ver el inicio de sesión de seguimiento del complemento Dataverse para ver detalles del error](dual-write-troubleshooting.md#enable-view-trace).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]