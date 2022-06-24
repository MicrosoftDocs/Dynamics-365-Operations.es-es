---
title: Configurar los parámetros de TDS en proveedores y clientes
description: Este artículo explica cómo establecer parámetros en proveedores y clientes para que sean compatibles con las deducciones de impuestos deducidos en el origen (TDS).
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
ms.openlocfilehash: e547b92f9f7e0ccc5b92df4cd991ce402369b568
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883161"
---
# <a name="set-tds-parameters-in-accounts-payable-and-accounts-receivable"></a>Configurar los parámetros de TDS en proveedores y clientes

[!include [banner](../includes/banner.md)]

Este artículo explica cómo establecer parámetros en proveedores y clientes para que sean compatibles con las deducciones de impuestos deducidos en el origen (TDS).

1. Vaya a **Impuesto \> Configuración \> Parámetros \> Parámetros de clientes**.
2. En la pestaña **Actualizaciones**, seleccione **Actualizar líneas de pedido** para abrir el cuadro de diálogo **Actualizar líneas de pedido**.
3. En la sección **Grupo de TDS**, en el campo **Actualizar grupo de TDS**, especifique el método que se utilizará para actualizar el grupo de TDS en el nivel de línea. Esta configuración se utiliza cuando el grupo de TDS se actualiza en un encabezado de pedido. Las siguientes opciones están disponibles:

    - **Nunca**: el grupo de TDS no se actualiza en las líneas de pedido cuando se actualiza en el encabezado del pedido.
    - **Siempre**: el grupo de TDS se actualiza automáticamente en las líneas de pedido cuando se actualiza en el encabezado del pedido.
    - **Bajo petición**: los usuarios reciben un mensaje que les pide que actualicen el grupo de TDS en las líneas de pedido.
4. Seleccione **Aceptar**.

    [![Cuadro de diálogo de actualizar líneas de pedido.](./media/apac-ind-TDS-26.PNG)](./media/apac-ind-TDS-26.PNG)

5. Vaya a **Impuesto \> Configuración \> Parámetros \> Parámetros de proveedores**.
6. En la pestaña **General**, en la ficha desplegable **Dividir según la información de entrega**, establezca la opción **Recepción del producto** a **Sí** para registrar y dividir una recepción de producto que tiene diferentes direcciones de entrega y números de cuenta de impuestos (TAN). Si esta opción se establece en **No**, no puede registrar un albarán de compra que tenga diferentes direcciones de entrega y TAN.
7. Establezca la opción **Factura** a **Sí** para registrar y dividir una factura de compra que tiene diferentes direcciones de entrega y TAN.

    [![Ficha desplegable Dividir según la información de entrega.](./media/apac-ind-TDS-25.png)](./media/apac-ind-TDS-25.png)

8. Cierre la página.
