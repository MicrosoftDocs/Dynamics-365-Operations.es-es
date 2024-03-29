---
title: El registro TaxTrans no se genera
description: Este artículo proporciona información sobre resolución de problemas que puede ayudar cuando no se genera un registro TaxTrans.
author: qire
ms.date: 04/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 402b1200e96ec8130034a03447ca071477544a88
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846723"
---
# <a name="taxtrans-record-isnt-generated"></a>El registro TaxTrans no se genera

[!include [banner](../includes/banner.md)]

Si selecciona **Impuesto registrado** para una transacción, pero la página **Impuesto registrado** no muestra ninguna línea de impuestos o le falta una línea de impuestos, el registro **TaxTrans** podría no haberse generado.

[![Página de impuestos que no tiene artículos de línea.](./media/taxtrans-is-not-generated-Picture1.png)](./media/taxtrans-is-not-generated-Picture1.png)

Para solucionar este problema, siga los pasos de las siguientes secciones según sea necesario.

## <a name="check-the-sales-tax-before-you-post-the-transaction"></a>Comprobar el impuesto antes de registrar la transacción

1. Antes de registrar la transacción, en la página **Registro de factura**, seleccione **Impuesto** para comprobar el cálculo.

    [![Botón de impuesto en la página Registro de factura.](./media/taxtrans-is-not-generated-Picture2.png)](./media/taxtrans-is-not-generated-Picture2.png)

2. En la página **Transacciones de impuestos temporales**, revise el resultado del cálculo. Si no se calcula ningún impuesto, consulte [El impuesto no se calcula o el importe del impuesto es cero](sales-tax-troubleshooting-tax-not-calculated-amount-zero.md).

## <a name="find-the-taxtrans-record-in-all-posted-sales-tax"></a>Busque el registro TaxTrans en todos los impuestos registrados

1. Vaya a **Impuestos** \> **Consultas e informes** \> **Consultas de impuestos** > **Impuestos registrados**.
2. En el encabezado de la columna **Asiento**, seleccione el símbolo de filtro para encontrar el registro **TaxTrans**.
3. Si encuentra los registros de impuestos que está buscando, compruebe la fecha. Si la fecha difiere de la fecha del encabezado del diario, cree una solicitud de servicio de Microsoft para obtener soporte adicional.

    [![Página de impuestos registrados.](./media/taxtrans-is-not-generated-Picture4.png)](./media/taxtrans-is-not-generated-Picture4.png)

## <a name="debug-to-check-details"></a>Depurar para comprobar detalles

1. Para obtener información sobre cómo depurar y determinar si **TmpTaxWorkTrans** y **TaxUncommitted** se generan correctamente, consulte [El valor del campo en TaxTrans es incorrecto](sales-tax-troubleshooting-field-value-taxtrans-incorrect.md).
2. Si **TaxTmpWorkTrans** o **TaxUncommitted** se generan correctamente, agregue un punto de interrupción en **TaxPost::SaveAndPost ()** e **Impuesto::SaveAndPost** para depurar la razón por la que **TaxTrans** no está insertado.

    [![Puntos de interrupción agregados en el código.](./media/taxtrans-is-not-generated-Picture5.png)](./media/taxtrans-is-not-generated-Picture5.png)

    [![Resultados de los puntos de interrupción agregados.](./media/taxtrans-is-not-generated-Picture6.png)](./media/taxtrans-is-not-generated-Picture6.png)

## <a name="determine-whether-customization-exists"></a>Determinar si existe personalización

Si ha completado los pasos de las secciones anteriores pero no ha encontrado problemas, determine si existe personalización. Si no existe personalización, cree una solicitud de servicio de Microsoft para obtener más soporte.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
