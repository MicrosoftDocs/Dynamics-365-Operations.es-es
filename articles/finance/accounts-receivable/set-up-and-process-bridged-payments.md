---
title: Configurar y procesar pagos puente
description: En este tema se explica cómo configurar y procesar pagos puente de clientes. Un pago puente es un pago que se registra en la contabilidad general en dos pasos.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPaymMode, VendPaymMode, LedgerJournalTable, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, LedgerJournalTransDaily
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ca93d99ce04e607b137a2755d507022a33ab1be8
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2022
ms.locfileid: "8734202"
---
# <a name="set-up-and-process-bridged-payments"></a>Configurar y procesar pagos puente

[!include [banner](../includes/banner.md)]

Un pago puente es un pago que se registra en la contabilidad general en dos pasos. Por lo general, este enfoque se utiliza cuando el método de pago se establece en **Banco** y debe contabilizar las transacciones en la cuenta bancaria solo cuando la transacción haya sido compensada por el banco. Sin embargo, también puede usarlo para una cuenta contable. En este caso, el sistema mueve el importe de una cuenta principal a otra cuenta principal cuando se procesa la contabilización puente.

Puede crear pagos puente desde Proveedores o Clientes. Aunque este tema explica cómo configurar la contabilización puente para Clientes, los pasos para las transacciones de Proveedores son similares.

## <a name="set-up-bridging-posting"></a>Configuración de contabilización puente

Para usar la contabilización puente, debe configurar uno o más métodos de pago para que usen el método **Contabilización puente**. A continuación, debe seleccionar una cuenta puente.

1. Vaya a **Clientes &gt; Configuración de pagos &gt; Formas de pago**.
2. Seleccione un método de pago existente para habilitar la contabilización puente. De forma alternativa, cree un nuevo método de pago.
3. Seleccione la casilla **Contabilización puente**.
4. En el campo **Contabilización puente**, seleccione la cuenta principal en la que se deben contabilizar los pagos antes de que se compensen en la cuenta bancaria.
5. Cierre la página.

## <a name="process-and-transfer-bridging-posting"></a>Contabilización puente de procesos y transferencias

Siga estos pasos para crear y procesar una contabilización puente

1. Vaya a **Clientes &gt; Pagos &gt; Diario de pagos de clientes**.
2. Seleccione **Nuevo** para crear un diario.
3. Seleccione un nombre en el campo **Nombre**.
4. Agregue líneas al diario de pagos del cliente y seleccione el método de pago configurado para la contabilización puente.
5. Registre el diario. Las transacciones se registrarán en la cuenta principal que seleccionó en el campo **Cuenta puenta** en el procedimiento anterior.

Cuando las transacciones se hayan liquidado en el banco y desee transferir el pago de la cuenta puente a la cuenta de pago especificada para el método de pago, siga estos pasos.

1. Vaya a **Contabilidad general &gt; Movimientos de diario &gt; Diarios generales**.
2. Seleccione **Nuevo** para crear un diario.
3. Seleccione un nombre en el campo **Nombre**.
4. Seleccione **Líneas** para abrir los detalles del diario.
5. Seleccione **Funciones &gt; Seleccionar transacciones puente**.
6. Marque cada pago que se haya liquidado y luego seleccione **Aceptar**.
7. Registre el diario.
