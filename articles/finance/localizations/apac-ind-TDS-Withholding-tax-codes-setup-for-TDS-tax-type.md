---
title: Configurar códigos de retención de impuestos para tipos de impuestos de TDS
description: Este tema explica cómo configurar códigos de impuestos de impuestos deducidos en el origen (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: add91eaef2ad091df7fd45e3de2dfe3993e6d62fdcbbcfcf95a7fc4953189239
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6754888"
---
# <a name="set-up-withholding-tax-codes-for-the-tds-tax-type"></a>Configurar códigos de retención de impuestos para tipos de impuestos de TDS

[!include [banner](../includes/banner.md)]

Este tema explica cómo configurar códigos de impuestos de impuestos deducidos en el origen (TDS).

1. Vaya a **Impuestos \> Impuestos indirectos \> Retención de impuestos \> Códigos de retenciones de impuestos**.

    [![Página Códigos de retenciones de impuestos.](./media/apac-ind-TDS-17.png)](./media/apac-ind-TDS-17.png)

2. En el panel de acciones, seleccione **Nuevo** para crear un código de retención de impuestos para TDS e introduzca los detalles requeridos.
3. En la ficha desplegable **General**, en el campo **Tipo de impuesto**, seleccione **TDS** para categorizar el código de impuestos como un código de impuestos de TDS.
4. En el campo **Periodo de liquidación**, seleccione el periodo de liquidación para el código de impuestos de TDS.
5. En el campo **Cuenta principal**, seleccione la cuenta contable en la que se debe registrar el importe de TDS.
6. En el campo **Cliente**, seleccione el cliente en la que se debe contabilizar el importe de TDS que se deduce en las transacciones de ventas.

    El campo **Origen** se establece automáticamente en **Porcentaje del importe bruto** y el valor no se puede cambiar.

    > [!NOTE]
    > No puede establecer el origen en **Porcentaje del importe neto** para códigos de impuestos del tipo de impuesto de TDS.

7. En el campo **Componente de retención de impuestos**, seleccione el grupo de componentes de impuestos de TDS para el código de impuestos de TDS.
8. Seleccione **Valores** en el Panel de acciones para abrir la página **Valores de retención de impuestos**.
9. En el campo **Fecha inicial**, introduzca al fecha inicial para el valor de TDS. En el campo **Fecha final**, escriba la fecha final.

    > [!NOTE]
    > Los campo **Límite mínimo**, **Límite superior** y **Excluir %** no están disponibles para códigos de impuestos del tipo de impuesto de TDS.

10. En el campo **Valor**, especifique el porcentaje de TDS para el código de impuestos de TDS.
11. Cierre la página **Valores de retención de impuestos** para volver a la página **Códigos de retención de impuestos**.

    > [!NOTE]
    > El botón **Límites** en la página **Códigos de retención de impuestos** no está disponible para códigos de impuestos del tipo de impuesto de TDS.

12. Cierre la página.
