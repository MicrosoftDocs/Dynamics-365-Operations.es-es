---
title: Configurar componentes de impuestos para el tipo de impuestos TDS
description: Este artículo explica cómo configurar componentes de retención de impuestos para el tipo de impuesto de impuesto deducido en el origen (TDS). También explica cómo definir el límite de umbral que se utiliza para calcular TDS para cada componente de TDS.
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
ms.openlocfilehash: df2eb10ce9e372bb1e984f6ae1a2e889bbd90ad0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871168"
---
# <a name="set-up-tax-components-for-the-tds-tax-type"></a>Configurar componentes de impuestos para el tipo de impuestos TDS

[!include [banner](../includes/banner.md)]

Este artículo explica cómo configurar componentes de retención de impuestos para el tipo de impuesto de impuesto deducido en el origen (TDS). Los componentes de TDS son TDS, suplementos, PE-Cess y SHE Cess. Este artículo también explica cómo definir el umbral que se utiliza para calcular TDS para cada componente de TDS. Además, puede definir un umbral de excepción que se utiliza para calcular TDS para cada componente de TDS.

Siga estos pasos para configurar los componentes de TDS.

1. Vaya a **Impuesto \> Configuración \> Retención de impuestos \> Componentes de retención de impuestos**.

    [![Página de componentes de retenciones de impuestos.](./media/apac-ind-TDS-9.png)](./media/apac-ind-TDS-9.png)

2. En campo **Tipo de impuesto**, seleccione **TDS** para configurar componentes de retención de impuestos para el tipo de impuesto TDS.
3. En el panel de acciones, haga clic en **Nuevo** para crear una línea.
4. En el campo **Componente de retención de impuestos**, introduzca un nombre para el componente de TDS.
5. En el campo **Grupo de componentes de retención de impuestos**, seleccione el grupo de componentes de retención de impuestos de TDS al que adjuntar el componente de TDS.
6. En la ficha desplegable **General**, en el campo **Descripción**, escriba una descripción del componente de TDS.
7. En el panel de acciones, seleccione **Umbral** para abrir la página **Umbral** para que pueda definir el umbral que se utiliza para calcular los TDS para el componente de TDS.
8. Use los campos **Fecha inicial** y **Fecha final** para definir el periodo al que se aplica el umbral.
9. En la ficha desplegable **General**, en el campo **Umbral**, introduzca la cantidad de umbral que se utiliza para calcular los TDS para el componente de TDS. El impuesto se deducirá en el origen solo cuando el importe acumulado de la factura supere el umbral.

    Por ejemplo, si el importe del umbral es 10 000, los TDS se calculan después de que el importe acumulado de la factura exceda 10 000 (en otras palabras, cuando es 10 001 o más).

10. En el campo **Umbral de excepción**, introduzca el importe de umbral de excepción que se utiliza para calcular los TDS para el componente de TDS. El impuesto de una línea de factura se deducirá en el origen solo cuando el importe supere el umbral de excepción.

    Por ejemplo, si el importe del umbral de excepción es 5000, los TDS se calculan en una línea de factura específica si el importe de la línea de factura excede 5000 (en otras palabras, si es 5001 o más).

    [![Página de umbral.](./media/apac-ind-TDS-10.png)](./media/apac-ind-TDS-10.png)

    > [!NOTE]
    > El importe del umbral de excepción debe ser menor o igual al importe del umbral.
    >
    > El impuesto se deduce de una transacción si el importe de la transacción cruza el umbral de excepción, incluso si el importe de la factura acumulada no cruza el umbral que se especifica en el campo **Umbral**.

11. Cierre la página **Umbral** para volver a la página **Componentes de retención de impuestos**.
12. En el panel de acciones, seleccione **Copiar** para abrir el cuadro de diálogo **Copiar componentes de retención de impuestos**, así podrá copiar los componentes de TDS que se configuraron para un grupo de componentes de TDS a otro grupo de componentes de TDS.
13. En el campo **Desde**, seleccione el grupo de componentes de TDS desde el que copiar los componentes de TDS. En el campo **Hasata**, seleccione el grupo de componentes de retención de impuestos al que copiar los componentes de TDS.

    > [!NOTE]
    > Los componentes de TDS comunes que se adjuntan a ambos grupos de componentes de TDS no se copian.

14. Seleccione **Aceptar** para copiar y crear componentes de TDS para el otro grupo de componentes de TDS en la página **Componentes de retención de impuestos**.

    [![Cuadro de diálogo Copiar componentes de retención de impuestos.](./media/apac-ind-TDS-11.png)](./media/apac-ind-TDS-11.png)

15. Cierre la página.
