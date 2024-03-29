---
title: Configurar períodos de liquidación de retención de impuestos para el tipo de impuesto de TDS
description: Este artículo explica cómo configurar períodos de liquidación para períodos de liquidación de impuestos deducidos en el origen (TDS).
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
ms.openlocfilehash: 855bda71f0967c53166cf0a7f5e7e465146f34a7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846566"
---
# <a name="set-up-withholding-tax-settlement-periods-for-the-tds-tax-type"></a>Configurar períodos de liquidación de retención de impuestos para el tipo de impuesto de TDS

[!include [banner](../includes/banner.md)]

Este artículo explica cómo configurar períodos de liquidación para períodos de liquidación de impuestos deducidos en el origen (TDS).

1. Vaya a **Impuestos \> Impuestos indirectos \> Retención de impuestos \> Períodos de liquidación de retención de impuestos**.

    [![Página Períodos de liquidación de retención de impuestos.](./media/apac-ind-TDS-13.png)](./media/apac-ind-TDS-13.png)

2. En el campo **Tipo de impuesto**, seleccione **TDS** para configurar períodos de liquidación de retención de impuestos para el tipo de impuesto TDS.
3. Seleccione **Nuevo** para crear una línea.
4. En el campo **Período de liquidación**, especifique un nombre para el período de liquidación de TDS.
5. En el campo **Descripción**, escriba una descripción.
6. En el campo **Autoridad de retención de impuestos**, seleccione la autoridad de TDS para la que está definiendo el período de liquidación de TDS.
7. En la ficha desplegable **General**, en el campo **Intervalo de período**, seleccione el tipo de intervalo de período para el período de liquidación de TDS.
8. En el campo **Número de unidades**, especifique el número de unidades para el tipo de intervalo de período.
9. En la ficha desplegable **Períodos**, en el campo **Fecha inicial**, seleccione la fecha inicial del período de liquidación de TDS. En el campo **Fecha final**, seleccione la fecha final.
10. Para crear un período de liquidación de TDS posterior para un período existente basado en el intervalo de período y las unidades de período, seleccione **Nuevo período**.
11. Para ver los detalles de la liquidación periódica de TDS que se ejecuta para un período de liquidación específico, seleccione **Pagos de retención de impuestos** para abrir la página **Pago de retención de impuestos**.

    > [!NOTE]
    > Para ejecutar el proceso de liquidación periódica de TDS, vaya a **Contabilidad general \> Periódica \> Retención de impuestos \> Pago de retención de impuestos**.

    [![Página Pago de retención de impuestos.](./media/apac-ind-TDS-15.png)](./media/apac-ind-TDS-15.png)

12. Cierre la página.
