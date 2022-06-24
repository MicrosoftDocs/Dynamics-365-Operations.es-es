---
title: Configurar los multivencimientos con la asignación de TDS
description: Este artículo explica cómo configurar multivencimientos con la asignación de impuestos deducidos en el origen (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 48891c32f39b743ce26e265c5682dab28ecb4b27
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868323"
---
# <a name="set-up-payment-schedules-with-tds-allocation"></a>Configurar los multivencimientos con la asignación de TDS

[!include [banner](../includes/banner.md)]

Este artículo explica cómo configurar multivencimientos con la asignación de impuestos deducidos en el origen (TDS).

1. Vaya a **Proveedores \> Configuración de pagos \> Multivencimientos**.

    [![Página de multivencimientos.](./media/apac-ind-TDS-27.png)](./media/apac-ind-TDS-27.png)

2. En el panel de acciones, seleccione **Nuevo** para crear un multivencimiento e introduzca los detalles requeridos.
3. En el campo **Asignación**, seleccione el método que se utilizará para asignar el pago para el multivencimiento:

    - Total
    - Importe fijo
    - Cantidad fija
    - Especificado

    El campo **Asignación de retención de impuestos** muestra el método de asignación de TDS para el multivencimiento. Si selecciona **Total** en el campo **Asignación**, el campo **Asignación de retención de impuestos** se establece automáticamente en **Total**. Si selecciona **Importe fijo**, **Cantidad fija** o **Especificado** en el campo **Asignación**, el campo **Asignación de retención de impuestos** se establece automáticamente en **Proporcionalmente**.

    > [!NOTE]
    > Si el campo **Asignación de retención de impuestos** está configurado en **Total**, los plazos de pago se calculan en base al importe bruto, que incluye el importe de TDS. Si el campo **Asignación de retención de impuestos** está configurado en **Proporcionalmente**, los plazos de pago se calculan en base al importe neto de la factura tras deducir el importe de TDS.

4. Especifique los demás detalles necesarios y cierre la página.
