---
title: Adjuntar códigos de impuestos de TDS a grupos de impuestos de TDS y definir la fórmula para calcular TDS
description: Este artículo explica cómo configurar grupos de impuestos con impuestos deducidos en el origen (TDS) y adjuntar códigos de impuestos TDS a grupos de impuestos TDS. Para calcular TDS para un grupo de impuestos TDS, debe definir la fórmula para los códigos de impuestos TDS que se le adjuntan.
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
ms.openlocfilehash: 3607e44bdcf7a32b156e6b4639ef907aa923cadc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853325"
---
# <a name="attach-tds-tax-codes-to-tds-tax-groups-and-define-the-formula-for-calculating-tds"></a>Adjuntar códigos de impuestos de TDS a grupos de impuestos de TDS y definir la fórmula para calcular TDS

[!include [banner](../includes/banner.md)]

Este artículo explica cómo configurar grupos de impuestos con impuestos deducidos en el origen (TDS) y adjuntar códigos de impuestos TDS a grupos de impuestos TDS. Para calcular TDS para un grupo de impuestos TDS, debe definir la fórmula para los códigos de impuestos TDS que se le adjuntan.

Siga estos pasos para configurar un grupo de impuestos TDS, adjuntarle códigos de impuestos TDS y definir la fórmula para calcular TDS.

1. Vaya a **Impuestos \> Impuestos indirectos \> Retención de impuestos \> Grupos de retenciones de impuestos**.

    [![Página de grupos de retenciones de impuestos.](./media/apac-ind-TDS-29.png)](./media/apac-ind-TDS-29.png)

2. En el panel de acciones, seleccione **Nuevo** para crear un grupo de retención de impuestos para TDS e introduzca los detalles requeridos.
3. En el campo **Tipo de impuesto**, seleccione **TDS**.
4. En la ficha desplegable **Configuración**, seleccione **Agregar** para crear una línea.
5. En el campo **Código de retención de impuestos**, seleccione el código de impuestos de TDS para el grupo de impuestos de TDS. El campo de **Nombre de retención de impuestos** muestra el nombre del código de impuestos TDS y el campo **Valor** muestra el valor.
6. Para ignorar el límite de umbral y el límite de umbral de excepción que se definen para el componente de impuestos de TDS que se adjunta al código de impuestos de TDS en las transacciones de TDS, seleccione la casilla **Omitir el umbral**.
7. Para evitar que el grupo de impuestos se calcule en las transacciones, seleccione la casilla **Exento**.
8. En el panel de acciones, seleccione **Diseñador** para abrir el diseñador de fórmulas, de modo que pueda definir la fórmula para calcular TDS para el grupo de impuestos TDS. En la página **Diseñador**, la pestaña **Impuestos** muestra los códigos de impuestos de TDS que se han seleccionado para el grupo de impuestos de TDS.

    [![Página de diseñador.](./media/apac-ind-TDS-30.png)](./media/apac-ind-TDS-30.png)

9. En la pestaña **Cálculo**, seleccione **Alt + N** para crear una línea. El campo **Id.** muestra el Id. de prioridad generado automáticamente para el cálculo de TDS.
10. En el campo **Código de impuestos**, seleccione el código de impuestos de TDS para el que quiere definir la fórmula. Todos los códigos de impuestos de TDS que se han seleccionado para el grupo de impuestos de TDS están disponibles para su selección en este campo.
11. En el campo **Base imponible**, seleccione la base para calcular TDS:

    - **Importe bruto**: calcule el TDS en función del importe bruto de la transacción (es decir, el importe de la factura) mediante la expresión de cálculo que se define para el código de impuestos.
    - **Importe bruto excluido**: calcule TDS en función de la expresión de cálculo que se define para el código de impuestos.

    > [!NOTE]
    > El campo **Base imponible** no se puede establecer en **Importe bruto excluido** para el código de impuestos TDS que tiene un Id. de prioridad de **1**.

12. El cálculo de TDS se basa en la fórmula que se define en el campo **Expresión de cálculo** para cada código de impuestos que se adjunta al grupo de impuestos TDS. Seleccione el signo más (+), signo menos (-), signo de multiplicación (\*) o el signo de división (/) para introducir la expresión de cálculo para el código de impuestos TDS seleccionado en el campo **Expresión de cálculo**.

    > [!NOTE]
    > No se puede definir ninguna expresión de cálculo para el código de impuestos TDS que tiene un Id. de prioridad de **1**.

13. Para definir la expresión de cálculo para el código de impuestos TDS en el campo **Expresión de cálculo**, agregue los códigos de impuestos TDS que están disponibles en la pestaña **Impuestos**. Para agregar códigos de impuestos TDS en el campo **Expresión de cálculo**, puede utilizar cualquiera de los siguientes métodos:

    - Arrastre el código de impuestos requerido de la pestaña **Impuestos** al campo **Expresión de cálculo**.
    - Toque dos veces (o haga doble clic) en el código de impuestos requerido en la pestaña **Impuestos**.
    - Seleccione y mantenga presionado (o haga clic con el botón derecho) el código de impuestos requerido en la pestaña **Impuestos** y luego seleccione **Agregar código de impuestos**.

    > [!NOTE]
    > Inserte una expresión de cálculo antes de cada código de impuestos TDS. Los códigos de impuestos TDS que se han agregado a la expresión de cálculo aparecen entre paréntesis (\[...\]).

14. Para borrar la expresión de cálculo definida para un código de impuestos en el campo **Expresión de cálculo**, seleccione el botón **C**.
15. Para eliminar un registro en la pestaña **Cálculo**, seleccione **Eliminar**.
16. Cierre la página.
