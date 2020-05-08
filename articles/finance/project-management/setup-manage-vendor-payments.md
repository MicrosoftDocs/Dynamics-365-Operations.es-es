---
title: Configurar y usar pagos de proveedor de pago al cobro
description: Este tema explica cómo crear términos de pago al cobro (PWP) para que pueda liberar pagos parciales a proveedores, en función de los pagos de los clientes.
author: RadhikaRS
manager: AnnBe
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 390cec62d2790ed10892669e283f2283c6b8e686
ms.sourcegitcommit: 399f128d90b71bd836a1c8c0c8c257b7f9eeb39a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2020
ms.locfileid: "3284122"
---
# <a name="set-up-and-use-pay-when-paid-vendor-payments"></a>Configurar y usar pagos de proveedor de pago al cobro

[!include [banner](../includes/banner.md)]

Al aprobar a un proveedor para trabajar como subcontratista en un proyecto, puede ser conveniente retener el pago al proveedor hasta que el cliente haya pagado el proyecto. Para admitir este escenario, puede configurar las condiciones de pago al cobro (AaC) cuando configure el pedido de compra (PO) con el proveedor.

Por ejemplo, cuando un cliente paga un importe de una factura de proyecto, se puede liberar una parte o todo el importe de la factura del proveedor. Basta con configurar condiciones de pago al cobro que especifiquen que se pagará a un proveedor después de recibir un porcentaje específico del pago relacionado del cliente. Si recibe un pago parcial de un cliente, puede liberar manualmente algunas de las facturas de proveedor relacionadas para el pago.

El siguiente ejemplo describe el proceso cuando se utilizan los términos PWP.

## <a name="example"></a>Ejemplo

Su organización acuerda proporcionar a un cliente 100 computadoras que tengan un software instalado, por un precio de 150,00 dólares estadounidenses (USD) por computadora. Luego contrata a un proveedor para que le proporcione las computadoras que tienen el software instalado. Según el acuerdo, el cliente desea aprobar la calidad de los equipos antes de pagar a su organización. La política de su organización es retener el pago a los proveedores hasta que el cliente le haya pagado. Por lo tanto, configura el proyecto para que tenga un porcentaje de PWP del 100 por cien.

El proveedor le envía las 100 computadoras que tienen el software instalado, junto con una factura por 10 000,00 USD. Debido a que tiene términos de PWP configurados para su proyecto, no le paga al proveedor al recibir las computadoras. En su lugar, envía las computadoras al cliente, junto con una factura por 15 000,00. El cliente examina los equipos y aprueba el importe total de la factura del proyecto.

Una vez recibido el pago completo del cliente, paga 10 000,00 al proveedor por el importe total de la factura de proveedor.

## <a name="set-up-pwp-terms-for-a-project"></a>Configuración de las condiciones PWP de un proyecto

Cuando configura los términos de PWP para un proyecto, debe especificar, como porcentaje, la cantidad mínima que un cliente debe pagarle por el proyecto antes de pagarle al proveedor. El importe de umbral se calcula automáticamente en las facturas de cliente del proyecto. Siga estos pasos para configurar el porcentaje del umbral para los términos PWP.

1. Vaya a **Gestión de proyectos y contabilidad** \> **Proyectos** \> **Todos los proyectos**.
2. Busque y abra el proyecto para el que desea configurar los términos PWP.
3. En la ficha desplegable **Contratos de proveedor**, seleccione **Agregar línea**.
3. En el campo **Código de cuenta**, seleccione una de las opciones siguientes:

    - **Tabla**: las condiciones PWP se aplican a un único proveedor.
    - **Grupo**: las condiciones PWP se aplican a todos los proveedores en un grupo de proveedores.
    - **Todos**: las condiciones PWP se aplican a todos los proveedores.

4. Si seleccionó **Tabla** o **Grupo** en el paso anterior, en el campo **Proveedor/grupo de proveedores**, seleccione el proveedor o el grupo de proveedores al que se aplican los términos PWP. Si seleccionó **Todas** en el paso anterior, el campo **Proveedor/grupo de proveedores** no se puede editar.
5. Si en el proyecto también hay condiciones de retención de proveedor configuradas para el proveedor, en el campo **Condiciones de retención de proveedor**, seleccione el id. de la regla de las condiciones de retención.
6. En el campo **Porcentaje del umbral AaC**, especifique el porcentaje de umbral para el proyecto. El porcentaje especificado para el proyecto define el importe mínimo que debe pagar el cliente antes de que usted pague al proveedor.

## <a name="create-a-po-that-has-pwp-terms"></a>Crear un PO que tenga términos PWP

Si se registra una factura del proveedor, si el proveedor está sujeto a condiciones de PWP, estas se muestran en las líneas del pedido de compra. Para crear una orden de compra que tenga términos de PWP, siga estos pasos.

1. Vaya a **Adquisición y abastecimiento** \> **Pedidos de compra** \> **Todos los pedidos de compra**.
2. En el panel de acciones, haga clic en **Nueva**. Entonces, en el cuadro de diálogo **Crear orden de compra**, ingrese la información requerida y seleccione **Aceptar**.

    Alternativamente, abra una orden de compra existente en la página de lista **Todas las órdenes de compra**.

4. En la página **Pedido de compra**, en la ficha desplegable **Líneas de pedido de compra**, revise los detalles de la línea del pedido de compra para el proveedor. La opción **Pago al cobro** se selecciona automáticamente y el valor del campo **Umbral de porcentaje PWP** se copia automáticamente a este formulario desde el campo **Umbral de porcentaje PWP** en la página **Proyectos**.
6. Si no desea aplicar los términos PWP al proveedor para una línea de pedido, desactive la opción **Pago al cobro**. En este caso, el campo **Umbral de porcentaje de PWP** para la línea de PO se restablecerá en 0 (cero).

## <a name="update-a-customer-payment-and-pay-the-vendor"></a>Actualizar un pago del cliente y pagar al proveedor

Cuando un proveedor completa el trabajo en un proyecto y le envía una factura, debe revisar el estado del proyecto y las facturas de cliente para determinar si se han cumplido las condiciones de PWP para el proyecto. Si las condiciones de AaC del proveedor se cumplieron, puede determinar las líneas de la factura de proveedor que deben pagarse, en función de los pagos del cliente para el proyecto. Si decide pagar al proveedor incluso si las condiciones de PWP no se cumplieron, puede anular las condiciones de PWP en la página **Facturas de proveedor con pago al cobro**.

1. Vaya a **Gestión de proyectos y contabilidad** \> **Consultas e informes** \> **Consultas de retención** \> **Facturas de proveedor con pago al cobro**.
2. En la página **Facturas de proveedor con pago al cobro**, en el campo de búsqueda, introduzca valores para buscar la factura de proveedor que desee revisar y, a continuación, seleccione **Buscar**.
3. En la ficha desplegable **Líneas de factura de proveedor**, seleccione las líneas que desea cambiar.
4. Si se cumplen las condiciones de **Pago al cobro**, para la línea de factura, seleccione **Liberar el pago del proveedor**. La opción **Pago al cobro** se desactiva y el valor del campo **Listo para el pago** cambia a **Sí**.
