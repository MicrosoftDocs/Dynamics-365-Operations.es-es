---
title: Verificar la configuración de doble escritura en aplicaciones de Finance and Operations y Dataverse
description: Este tema explica cómo puede determinar si la escritura doble está configurada en aplicaciones Finance and Operations y en Dataverse.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: af746d1d20ddd1552bce797288c6d62d69d7bd16
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748858"
---
# <a name="verify-dual-write-configuration-in-finance-and-operations-apps-and-dataverse"></a>Verificar la configuración de doble escritura en aplicaciones de Finance and Operations y Dataverse

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Este tema proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Dataverse. Específicamente explica cómo puede determinar si la escritura doble está configurada en aplicaciones Finance and Operations y en Dataverse.

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a>Verifique que la doble escritura esté configurada en una aplicación Finance and Operations

Para determinar si los errores que ve cuando intenta guardar filas para la actualización provienen de doble escritura, primero verifique que la doble escritura esté configurada.

+ Si tiene privilegios de administrador en la aplicación Finance and Operations, vaya a **Espacios de trabajo \> Gestión de datos** y seleccione el mosaico **Doble escritura**. Si se muestran los detalles de los entornos vinculados y la lista de mapas de tablas que se están ejecutando, se configura la escritura doble.

    ![Comprobar la conexión de la aplicación Finance and Operations con privilegios de administrador](media/verify_fin_ops_1.png)

+ Si no tiene privilegios de administrador, aparecerá un mensaje de error: *No se pueden escribir datos en la entidad nombre de la entidad \<entity name\>*. En el ejemplo de la siguiente ilustración, no puede crear una fila de cliente en la aplicación Finance and Operations, porque la escritura doble está configurada, pero el grupo de clientes y los datos de referencia de términos de pago no existen en Dataverse.

    ![Verificando la conexión de la aplicación Finance and Operations cuando no tiene privilegios de administrador](media/verify_fin_ops_2.png)

Para obtener información sobre cómo solucionar problemas al crear datos en aplicaciones Finance and Operations, consulte [Solucionar problemas de sincronización en vivo](dual-write-troubleshooting-live-sync.md).

## <a name="verify-that-dual-write-is-configured-in-dataverse"></a>Verifique que la doble escritura esté configurada en Dataverse

Cuando crea datos, si ve la columna **Empresa** en páginas en Dataverse, la doble escritura está configurada.

![Verificando la conexión Dataverse](media/verify_cds.png)

Para obtener información sobre cómo solucionar problemas al crear datos en Dataverse, consulte [Solucionar problemas de sincronización en vivo](dual-write-troubleshooting-live-sync.md).

Para obtener información sobre cómo ver los detalles del error si encuentra algún error mientras crea datos en Dataverse, consulte [Habilitar y ver el inicio de sesión de seguimiento del complemento Dataverse para ver detalles del error](dual-write-troubleshooting.md#enable-view-trace).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]