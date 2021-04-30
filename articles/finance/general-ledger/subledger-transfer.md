---
title: Transferencia de subdiarios a la contabilidad general
description: Este tema describe las capacidades de Microsoft Dynamics 365 Finance en relación con el proceso de transferencia de subdiarios en la contabilidad general.
author: roschlom
ms.date: 09/09/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-01-18
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 1efdf095e379b73d553ca3525abbeee8ca35bcbb
ms.sourcegitcommit: 7d0cfb359a4abc7392ddb3f0b3e9539c40b7204d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5897513"
---
# <a name="subledger-transfer-to-the-general-ledger"></a>Transferencia de subdiarios a la contabilidad general

[!include [banner](../includes/banner.md)]

Este tema describe las capacidades de Microsoft Dynamics 365 Finance que están relacionadas con las reglas para transferir lotes de entradas de subdiarios contables.

En la versión 8.1, se realizaron cambios para permitir la transferencia de reglas, lo que dejó en desuso la opción **Sincrónico**. Para obtener más información, consulte [Funciones retiradas u obsoletas para Finance and Operations](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=%2fdynamics365%2ffinance%2ftoc.json#finance-and-operations-81-with-platform-update-20).

Las siguientes opciones están disponibles para transferir lotes de subdiarios. 

 - Asíncrono: esta opción programará inmediatamente la transferencia de los asientos contables del subdiario contable a la contabilidad general. El asiento de la contabilidad general se registrará tan pronto como los recursos estén libres para procesar esta solicitud en el servidor. 

- Lote programado: esta opción agregará los asientos contables del subdiario contable que se transfieren a la cola de procesamiento en la contabilidad general, donde las entradas se procesarán en el orden recibido. El asiento de la contabilidad general se registrará a la hora programada si los recursos estén libres para procesar este trabajo por lotes en el servidor. 
 
En la versión 10.0.8, se realizaron mejoras para mejorar el rendimiento de la opción Asincrónico. Esta característica está habilitada debajo del nombre de la característica **Optimización del rendimiento de la transferencia de subdiarios a la contabilidad general**. 
 
Esta funcionalidad mejora la transferencia de datos desde el subdiario contable a la contabilidad general. Permite que el proceso sea más eficiente y agrupa conjuntos de transacciones más pequeñas para transferir. Esto permite un uso más eficiente del servidor por lotes. Esta funcionalidad requiere que el servidor por lotes esté configurado, en línea y funcionando para que funcione la opción de transferencia Asincrónico. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]