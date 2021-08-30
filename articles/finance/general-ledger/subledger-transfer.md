---
title: Transferencia de subdiarios al libro mayor
description: Este tema describe las capacidades que tienen relación con el proceso de transferencia de subdiarios en la contabilidad general.
author: rcarlson
ms.date: 07/20/2021
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
ms.openlocfilehash: 03c04a5eb8b544b582019ddd204382900b162d952842c901f69ed4a853bd8183
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716654"
---
# <a name="subledger-transfer-to-the-general-ledger"></a>Transferencia de subdiarios al libro mayor

[!include [banner](../includes/banner.md)]

Este tema describe las capacidades que están relacionadas con las reglas para transferir lotes de entradas de subdiarios contables.

En la versión 8.1, se realizaron cambios para permitir la transferencia de reglas, lo que dejó en desuso la opción **Sincrónico**. Para obtener más información, consulte [Funciones retiradas u obsoletas para Finance and Operations](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=%2fdynamics365%2ffinance%2ftoc.json#finance-and-operations-81-with-platform-update-20).

Las siguientes opciones están disponibles para transferir lotes de subdiarios:

- **Asíncrono**: esta opción programará inmediatamente la transferencia de los asientos contables del subdiario contable a la contabilidad general. El asiento de la contabilidad general se registrará tan pronto como los recursos estén disponibles para procesar esta solicitud en el servidor.
- **Lote programado**: los asientos contables del Libro mayor auxiliar que deben transferirse se agregan a la cola de procesamiento en el Libro mayor. Las entradas en la cola se procesarán en el orden en que se reciban. Cada asiento de la contabilidad general actualizará cuentas a la hora programada si los recursos están disponibles para procesar este trabajo por lotes en el servidor.

En la versión 10.0.8, se realizaron mejoras para mejorar el rendimiento de la opción **Asincrónico**. Esta característica está habilitada debajo del nombre de la característica **Optimización del rendimiento de la transferencia de subdiarios a la contabilidad general**.

La funcionalidad para la transferencia asincrónica de lotes del libro mayor auxiliar ayuda a mejorar la transferencia de datos del libro mayor auxiliar al libro mayor general. Al agrupar conjuntos de transacciones más pequeñas y transferir las transacciones en grupos, la funcionalidad procesa las transacciones de manera más eficiente. Cuando las transacciones se agrupan, los recursos del servidor por lotes se utilizan de manera más eficiente.

La transferencia asincrónica de lotes del libro mayor auxiliar requiere que el servidor de lotes esté configurado, en línea y en funcionamiento. De lo contrario, la opción de transferencia **Asincrónica** no funcionará.

El cambio de eficiencia a nivel de lote utiliza un único trabajo por lotes recurrente para todas las entidades legales del sistema. En tiempo de ejecución, se crea un nuevo trabajo por lotes para procesar los registros necesarios que aún no se han transferido. Se pueden controlar más configuraciones desde la página **Automatización de procesos** en la administración del sistema. En esa página, puede modificar el proceso en segundo plano, cambiar la frecuencia y definir un período de suspensión.

Para obtener más información sobre la configuración de automatización del proceso [Automatización de proceso](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
