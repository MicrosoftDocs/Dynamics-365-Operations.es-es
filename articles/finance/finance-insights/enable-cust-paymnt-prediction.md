---
title: Habilitar las predicciones de pago de clientes
description: Este artículo explica cómo activar y configurar la característica de predicciones de pago de clientes en Finance Insights.
author: ShivamPandey-msft
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: f04ee9db5efe3595dea30d641c5097d6b90c0d77
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898218"
---
# <a name="enable-customer-payment-predictions"></a>Habilitar las predicciones de pago de clientes

[!include [banner](../includes/banner.md)]

Este artículo explica cómo activar y configurar la característica de predicciones de pago de clientes en Finance Insights. Active la característica en el espacio de trabajo **Administración de características** e introduzca los ajustes de configuración en la página **Configuración de Finance Insights**. Este artículo también incluye información que puede ayudarle a utilizar la característica de manera eficaz.

> [!NOTE]
> Antes de completar los siguientes pasos, asegúrese de completar los pasos de requisitos previos en el artículo [Configurar para Finance Insights](configure-for-fin-insites.md).

1. Active la característica de predicciones de pago del cliente:

    1. Abra el espacio de trabajo **Administración de características**.
    2. Seleccione **Buscar actualizaciones**.
    3. En la pestaña **Todo**, busque **Predicciones de pago de clientes**. Si no encuentra esa caraterística, busque **(Versión preliminar) Previsiones de pago de clientes**. 
    4. Activar la característica.

    La característica Predicciones de pago de cliente ya está activada y lista para configurarse.

2. Configure la característica de Información de pagos de clientes:

    1. Vaya a **Crédito y cobros \> Configurar \> Información financiera \> Predicciones de pago de cliente**.
    2. En la página **Configuración de Finance Insights**, en la pestaña **Predicciones de pago de cliente**, seleccione **Ver los campos de datos usados en el modelo de predicción** para abrir la página **Campos de datos para el modelo de predicción**. Allí, puede ver la lista predeterminada de campos que se utilizan para crear el modelo de predicción de inteligencia artificial (IA) para las predicciones de pago de los clientes.

        Para usar la lista predeterminada de campos para crear el modelo de predicción, cierre la página **Campos de datos para el modelo de predicción**, y luego, en la página **Configuración de Finance Insights**, configure la opción **Habilitar característica** en **Sí**.
        
   > [!NOTE]
   > La característica **Predicciones de pago de cliente** requiere más de 100 transacciones en los seis a nueve meses anteriores. Las transacciones pueden incluir facturas de servicios, pedidos de venta y pagos de clientes. Estos datos deben estar repartidos por toda la configuración **A tiempo**, **Tarde** y **Muy tarde**.    
     

    3. Especifique el período de transacción "muy tarde" para definir qué significa el ámbito de predicción **Muy tarde** para su negocio.

        Para cada factura abierta, el sistema predice la probabilidad de pago en tres ámbitos: **Puntutal**, **Tarde** y **Muy tarde**.

        - **Puntual**: este grupo incluye pagos que se prevé que se pagarán en la fecha de vencimiento de la transacción o antes.
        - **Tarde**: este segmento incluye los pagos que se prevé que se pagarán después de la fecha de vencimiento de la transacción, pero antes del inicio del período de transacción "muy tarde".
        - **Muy tarde**: este segmento incluye los pagos que se prevé que se pagarán después del comienzo del período de transacción "muy tarde".

        > [!NOTE]
        > Si cambia el período de transacción "muy tarde" y selecciona **Cambiar el umbral de tarde** después de creado el modelo de predicción de IA para los pagos de los clientes, se elimina el modelo de predicción existente y se crea un nuevo modelo. El nuevo modelo de predicción moverá las transacciones al período "muy tarde", según la configuración introducida para definirlo.

    4. Una vez que haya terminado de definir el período de transacción "muy tarde", seleccione **Crear modelo de predicción** para crear el modelo de predicción. La sección **Modelo de predicción** de la página **Configuración de Finance Insights** muestra el estado del modelo de predicción.

        > [!NOTE]
        > En cualquier momento, mientras se crea el modelo de predicción, puede seleccionar **Restablecer la creación del modelo** para reiniciar el proceso.

    La característica ya se ha configurado y está lista para utilizarla.

Una vez que la característica se ha activado y configurado, el modelo de predicción se ha creado y está funcionando, la sección **Modelo de predicción** de la página **Parámetros de Finance Insights** muestra la precisión del modelo.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
