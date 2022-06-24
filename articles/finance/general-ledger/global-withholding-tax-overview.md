---
title: Retención de impuestos global
description: Este artículo proporciona información sobre la funcionalidad de retención de impuestos global y cómo configurarla. La funcionalidad de retención de impuestos global se ha mejorado para las transacciones de proveedores y clientes, de modo que la retención de impuestos se calcula a nivel de artículo.
author: kailiang
ms.date: 01/12/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: kfend
ms.custom:
- "15721"
- intro-internal
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 49d5048b9df30e94d959cf9f22b8ae837b74abdd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846839"
---
# <a name="global-withholding-tax"></a>Retención de impuestos global

[!include [banner](../includes/banner.md)]

Este artículo proporciona información sobre la funcionalidad de retención de impuestos global y explica cómo configurarla. La nueva funcionalidad está disponible en las versiones 10.0.17 y posteriores.

La funcionalidad de retención de impuestos global se ha mejorado para las transacciones de proveedores y clientes, de modo que la retención de impuestos se calcula a nivel de artículo. El saldo en la cuenta de retención de impuestos de las transacciones de compra se puede liquidar ejecutando el trabajo de pago de retención de impuestos en la cuenta de liquidación de retención de impuestos.

> [!NOTE]
> La retención de impuestos global no respalda la función **Mantener cargos** función en las páginas de pedidos de compra, facturas de proveedor y pedidos de ventas.

## <a name="turn-on-global-withholding-tax"></a>Activar la retención de impuestos global

1. En el espacio de trabajo **Administración de características**, seleccione **Retención de impuestos global** y luego seleccione **Habilitar ahora**.
2. Vaya a **Impuesto \> Configuración \> Parámetros \> Parámetros del libro mayor**, y luego, en la pestaña **Retención de impuestos**, configure la opción **Habilitar la retención de impuestos global** a **Sí**.
3. Seleccione **Guardar**.
4. Actualice la página en su navegador web.

> [!NOTE]
> La funcionalidad de retención de impuestos global no se puede activar para países o regiones donde ya existen soluciones de retención de impuestos localizadas. Estas áreas incluyen, entre otras, India, Brasil, Tailandia, Arabia Saudí, Irlanda, Gran Bretaña y Estados Unidos.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
