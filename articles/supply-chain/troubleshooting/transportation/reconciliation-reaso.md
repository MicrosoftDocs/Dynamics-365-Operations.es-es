---
title: Puede agregar solo la cuenta principal como cuenta de crédito por motivos de conciliación
description: Cuando configura un motivo de conciliación en la Administración de transporte, puede agregar solo la cuenta principal como cuenta de crédito.
author: Henrikan
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: TMSFBDetailReconcile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: c4ba48c5b6e3476c203eed2fddf053ce8af873dd6a7665df54560c8894f8c2d1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6750891"
---
# <a name="you-can-add-only-the-main-account-as-the-credit-account-for-reconciliation-reasons"></a>Puede agregar solo la cuenta principal como cuenta de crédito por motivos de conciliación

Número de KB: 4603538

## <a name="symptoms"></a>Síntomas

Cuando configura un motivo de conciliación en la Administración de transporte, puede agregar solo la cuenta principal como cuenta de crédito. No puede agregar un centro de coste o cualquier otra dimensión como la cuenta de crédito. Sin embargo, la cuenta de débito le permite seleccionar otras dimensiones.

## <a name="resolution"></a>Resolución

Si la conciliación no se realiza para pagar al proveedor, sino para acreditar una cuenta principal específica, el sistema no le permite seleccionar una dimensión financiera para la cuenta de crédito cuando configura el motivo de conciliación.

Si la estructura contable necesita un valor de dimensión financiera específico para la cuenta principal de crédito, el diario del proveedor resultante no se puede registrar automáticamente porque falta el valor de la dimensión financiera. Por lo tanto, primero debe especificar manualmente la cuenta de crédito mediante la página **Diario de facturas**.

Debido a que se necesita un valor de dimensión para la cuenta de crédito, el diario de facturas del proveedor no se puede registrar automáticamente. Debe registrarlo manualmente después de agregar manualmente el valor de dimensión a la cuenta principal para la línea de crédito.
