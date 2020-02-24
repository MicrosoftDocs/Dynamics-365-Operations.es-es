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
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-01-18
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 1ae10f406148e213fd0272d1387f15606233be27
ms.sourcegitcommit: 9168621ca9b5061c65f3e05dbc5918b6a11d53d5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2020
ms.locfileid: "3000456"
---
# <a name="subledger-transfer-to-the-general-ledger"></a><span data-ttu-id="abb1d-103">Transferencia de subdiarios a la contabilidad general</span><span class="sxs-lookup"><span data-stu-id="abb1d-103">Subledger transfer to the General ledger</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="abb1d-104">Este tema describe las capacidades de Microsoft Dynamics 365 Finance que están relacionadas con las reglas para transferir lotes de entradas de subdiarios contables.</span><span class="sxs-lookup"><span data-stu-id="abb1d-104">This topic describes capabilities in Microsoft Dynamics 365 Finance that are related to the rules for transferring batches of subledger journal entries.</span></span>

<span data-ttu-id="abb1d-105">En la versión 8.1, se realizaron cambios para permitir la transferencia de reglas, lo que quedó obsoleta la opción Sincrónico.</span><span class="sxs-lookup"><span data-stu-id="abb1d-105">In version 8.1, changes were made to allow the transfer of rules, which deprecated the Synchronous option.</span></span> <span data-ttu-id="abb1d-106">Para obtener más información, consulte [Funciones retiradas u obsoletas para Finance and Operations](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/deprecated-features?toc=/dynamics365/finance/toc.json#finance-and-operations-81-with-platform-update-20).</span><span class="sxs-lookup"><span data-stu-id="abb1d-106">For more information, see [Removed or deprecated features for Finance and Operations](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/deprecated-features?toc=/dynamics365/finance/toc.json#finance-and-operations-81-with-platform-update-20).</span></span>

<span data-ttu-id="abb1d-107">Las siguientes opciones están disponibles para transferir lotes de subdiarios.</span><span class="sxs-lookup"><span data-stu-id="abb1d-107">The following options are available for transferring subledger batches.</span></span> 

 - <span data-ttu-id="abb1d-108">Asíncrono: esta opción programará inmediatamente la transferencia de los asientos contables del subdiario contable a la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="abb1d-108">Asynchronous – This option will immediately schedule the transfer of the subledger accounting entries to the general ledger.</span></span> <span data-ttu-id="abb1d-109">El asiento de la contabilidad general se registrará tan pronto como los recursos estén libres para procesar esta solicitud en el servidor.</span><span class="sxs-lookup"><span data-stu-id="abb1d-109">The general ledger voucher will be recorded as soon as resources are free to process this request on the server.</span></span> 

- <span data-ttu-id="abb1d-110">Lote programado: esta opción agregará los asientos contables del subdiario contable que se transfieren a la cola de procesamiento en la contabilidad general, donde las entradas se procesarán en el orden recibido.</span><span class="sxs-lookup"><span data-stu-id="abb1d-110">Scheduled batch – This option will add the subledger accounting entries that are being transferred to the processing queue in the general ledger, where the entries will be processed in order received.</span></span> <span data-ttu-id="abb1d-111">El asiento de la contabilidad general se registrará a la hora programada si los recursos estén libres para procesar este trabajo por lotes en el servidor.</span><span class="sxs-lookup"><span data-stu-id="abb1d-111">The general ledger voucher will be recorded at the scheduled time if resources are free to process this batch job on the server.</span></span> 
 
<span data-ttu-id="abb1d-112">En la versión 10.0.8, se realizaron mejoras para mejorar el rendimiento de la opción Asincrónico.</span><span class="sxs-lookup"><span data-stu-id="abb1d-112">In version 10.0.8, improvements were made to enhance the performance of the Asynchrounous option.</span></span> <span data-ttu-id="abb1d-113">Esta característica está habilitada debajo del nombre de la característica **Optimización del rendimiento de la transferencia de subdiarios a la contabilidad general**.</span><span class="sxs-lookup"><span data-stu-id="abb1d-113">This feature is enabled under the feature name **Subledger transfer to General Ledger performance optimization**.</span></span> 
 
<span data-ttu-id="abb1d-114">Esta funcionalidad mejora la transferencia de datos desde el subdiario contable a la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="abb1d-114">This functionality improves the transfer of data from the subledger to the general ledger.</span></span> <span data-ttu-id="abb1d-115">Permite que el proceso sea más eficiente y agrupa conjuntos de transacciones más pequeñas para transferir.</span><span class="sxs-lookup"><span data-stu-id="abb1d-115">It allows the process to be more efficient, and it groups together sets of smaller transactions to transfer.</span></span> <span data-ttu-id="abb1d-116">Esto permite un uso más eficiente del servidor por lotes.</span><span class="sxs-lookup"><span data-stu-id="abb1d-116">This allows for a more efficient use of the batch server.</span></span> <span data-ttu-id="abb1d-117">Esta funcionalidad requiere que el servidor por lotes esté configurado, en línea y funcionando para que funcione la opción de transferencia asincrónica.</span><span class="sxs-lookup"><span data-stu-id="abb1d-117">This functionality requires that the batch server be set up, online, and functioning in order for the Asynchrounous transfer option to work.</span></span> 
