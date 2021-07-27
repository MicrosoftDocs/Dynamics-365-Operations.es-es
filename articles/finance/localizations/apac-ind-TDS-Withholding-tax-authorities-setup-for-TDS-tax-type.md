---
title: Configurar autoridades de retención de impuestos para tipos de impuestos de TDS
description: Este tema explica cómo configurar autoridades de impuestos deducidos en el origen (TDS).
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
ms.openlocfilehash: d9cecb3598e0686192d394903e8bb58d304a7665
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6349961"
---
# <a name="set-up-withholding-tax-authorities-for-the-tds-tax-type"></a>Configurar autoridades de retención de impuestos para tipos de impuestos de TDS

[!include [banner](../includes/banner.md)]

Este tema explica cómo configurar autoridades de impuestos deducidos en el origen (TDS).

1. Vaya a **Impuestos \> Impuestos indirectos \> Autoridades de retención de impuestos**.

    [![Página Autoridades de retenciones de impuestos.](./media/apac-ind-TDS-12.png)](./media/apac-ind-TDS-12.png)

2. En el campo **Tipo de impuesto**, seleccione **TDS** para configurar autoridades de retención de impuestos para el tipo de impuesto TDS.
3. En el panel de acciones, haga clic en **Nuevo** para crear una línea.
4. En el campo **Autoridad de retención de impuestos**, introduzca un nombre para la autoridad de TDS.
5. En el campo **Descripción**, escriba una descripción.
6. En la ficha desplegable **General**, en el campo **Cuenta del proveedor**, seleccione la cuenta del proveedor para la autoridad de TDS.

    > [!NOTE]
    > Debe definir el nombre del banco donde se depositarán los fondos adeudados al proveedor de la autoridad de TDS. El nombre del banco se define en la página **Cuentas bancarias** (**Proveedores \> Todos los proveedores \> Proveedor \> Configurar \> Cuentas bancarias**).

7. Cierre la página.
