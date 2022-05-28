---
title: Configurar un cuotas de pago para pagos de la autoridad de TDS
description: Este tema explica cómo configurar las cuotas de pago que se cobran por los pagos de la autoridad con impuestos deducidos en el origen (TDS).
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
ms.openlocfilehash: 290606201eff7aee985983603e7895a8a59233ac
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2022
ms.locfileid: "8725578"
---
# <a name="set-up-payment-fees-for-tds-authority-payments"></a>Configurar un cuotas de pago para pagos de la autoridad de TDS

[!include [banner](../includes/banner.md)]

Este tema explica cómo configurar las cuotas de pago que se cobran por los pagos de la autoridad con impuestos deducidos en el origen (TDS).

1. Vaya a **Proveedores \> Configuración de pagos \> Cuota de pago**.

    [![Página de cuota de pago.](./media/apac-ind-TDS-28.png)](./media/apac-ind-TDS-28.png)

2. Seleccione **Nuevo** para crear una cuota de pago y especificar los detalles necesarios.
3. En el campo **Tipo de cuota**, seleccione el tipo de cuota de pago:

    - **None**
    - **Interés**: se cobran intereses sobre los pagos atrasados que se realizan al proveedor de la autoridad de TDS.
    - **Otros**: se cobran otros cargos sobre los pagos atrasados que se realizan al proveedor de la autoridad de TDS.

    Si selecciona **Interés** u **Otros**, el campo **Cargo** se establece automáticamente en **Contabilidad**.

4. Si ha seleccionado **Interés** u **Otros** en el campo **Tipo de campo**, en el campo **Cuenta principal**, seleccione la cuenta contable en la que se registrarán los intereses u otros cargos.
5. Especifique los otros detalles.
6. En el panel de acciones, seleccione **Configuración de cuota de pago** para abrir la página **Configuración de cuota de pago**, donde puede configurar cuotas de pago para varias combinaciones de bancos, métodos de pago, especificaciones de pago, divisas e intervalos de fechas.

    [![Página de configuración de cuota de pago.](./media/apac-ind-TDS-21.png)](./media/apac-ind-TDS-21.png)

7. En la pestaña **Información general**, en el campo **Agrupaciones**, especifique para qué bancos está configurando la cuota de pago:

    - **Tabla**: la tarifa es válida para una cuenta bancaria específica.
    - **Grupo**: la tarifa es válida para un grupo bancario específico.
    - **Todos**: la cuota es válida para todas las cuentas bancarias.

8. Si ha seleccionado **Tabla** o **Grupo** en el campo **Agrupaciones**, en el campo **Relación del banco**, seleccione la cuenta bancaria o el grupo bancario específicos para los que está configurando la cuota de pago.
9. En el campo **Método de pago**, seleccione el método de pago que se usará para el pago de las cuotas.
10. En el campo **Especificación del pago**, seleccione o introduzca el código de especificación de pago que se generó en la página **Especificación de pago**.
    - Especificación del pago se utiliza con formas de pago de transferencia electrónica de fondos.
12. En el campo **Divisa de pago**, seleccione la divisa que activa la cuota. Solo las transacciones que usan la divisa seleccionada pueden activar la cuota. Si deja este campo en blanco, todas las divisas activan la cuota.
13. En el campo **Porcentaje/Importe**, seleccione el método de cálculo. Las opciones son **Importe**, **Porcentaje** e **Intervalo**.
14. En el campo **Importe de la cuota**, especifique el importe de la cuota como un porcentaje del pago o el importe de un pago.
15. En el campo **Divisa de cuota**, seleccione el código de divisa para la cuota.
16. Seleccione la pestaña **General** para ver o modificar los detalles de la cuenta bancaria seleccionada.

    [![Pestaña General.](./media/apac-ind-TDS-22.png)](./media/apac-ind-TDS-22.png)

16. En el campo **Mínimo**, introduzca el importe mínimo de transacción que activa la cuota.
17. En el campo **Máximo**, introduzca el importe máximo de transacción que activa la cuota.
18. En los campos **Fecha inicial** y **Fecha final**, defina un rango de fechas para calcular las cuotas.
19. En el campo **Cuota mínima**, especifique el importe de la cuota como un porcentaje del pago o el importe de un pago.
20. En el campo **Grupo de impuestos**, seleccione el grupo de impuestos que se utilizará para calcular el impuesto para el importe de la cuota.
21. En el campo **Grupo de impuestos de artículos**, seleccione el grupo de impuestos de artíuclos que se utilizará para calcular el impuesto de artículos para el importe de la cuota.
22. Seleccione la pestaña **Intervalo**. 

    [![Pestaña de intervalo.](./media/apac-ind-TDS-23.png)](./media/apac-ind-TDS-23.png)

23. En el campo **Días**, especifique el número de días entre la fecha de registro (fecha de descuento) del pago y la fecha de vencimiento del pagaré.
24. En el campo **Porcentaje/Importe**, seleccione si la especificación es un porcentaje o una cantidad fija.
25. En el campo **Importe de la cuota**, introduzca el importe de la cuota como un porcentaje del pago o el importe de un pago.
26. Cierre la página **Configuración de cuota de pago**.
27. Cierre la página **Cuota de pago**.
