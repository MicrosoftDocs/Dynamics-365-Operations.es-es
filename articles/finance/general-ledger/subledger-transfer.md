---
title: Transferencia de subdiarios a la contabilidad general
description: Este tema describe las capacidades de Microsoft Dynamics 365 Finance en relación con el proceso de transferencia de subdiarios en la contabilidad general.
author: roschlom
manager: AnnBe
ms.date: 09/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: aec68b9389ee2ef28e8119087392ac5f18ec5dd2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204794"
---
# <a name="subledger-transfer-to-the-general-ledger"></a>Transferencia de subdiarios a la contabilidad general

[!include [banner](../includes/banner.md)]

Este tema describe las capacidades de Microsoft Dynamics 365 Finance que están relacionadas con las reglas para transferir lotes de entradas de subdiarios contables.

En la versión 8.1, se realizaron cambios para permitir la transferencia de reglas, lo que dejó en desuso la opción **Sincrónico**. Para obtener más información, consulte [Funciones retiradas u obsoletas para Finance and Operations](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/deprecated-features?toc=/dynamics365/finance/toc.json#finance-and-operations-81-with-platform-update-20).

Las siguientes opciones están disponibles para transferir lotes de subdiarios. 

 - Asíncrono: esta opción programará inmediatamente la transferencia de los asientos contables del subdiario contable a la contabilidad general. El asiento de la contabilidad general se registrará tan pronto como los recursos estén libres para procesar esta solicitud en el servidor. 

- Lote programado: esta opción agregará los asientos contables del subdiario contable que se transfieren a la cola de procesamiento en la contabilidad general, donde las entradas se procesarán en el orden recibido. El asiento de la contabilidad general se registrará a la hora programada si los recursos estén libres para procesar este trabajo por lotes en el servidor. 
 
En la versión 10.0.8, se realizaron mejoras para mejorar el rendimiento de la opción Asincrónico. Esta característica está habilitada debajo del nombre de la característica **Optimización del rendimiento de la transferencia de subdiarios a la contabilidad general**. 
 
Esta funcionalidad mejora la transferencia de datos desde el subdiario contable a la contabilidad general. Permite que el proceso sea más eficiente y agrupa conjuntos de transacciones más pequeñas para transferir. Esto permite un uso más eficiente del servidor por lotes. Esta funcionalidad requiere que el servidor por lotes esté configurado, en línea y funcionando para que funcione la opción de transferencia Asincrónico. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]