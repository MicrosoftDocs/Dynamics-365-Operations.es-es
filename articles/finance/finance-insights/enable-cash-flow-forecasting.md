---
title: Habilitar las previsiones de flujo de efectivo
description: Este artículo explica cómo activar la característica de previsiones de flujo de efectivo en Finance Insights.
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
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 253e3ea9c1c44573b37503f167b4cb3860683c10
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859886"
---
# <a name="enable-cash-flow-forecasting"></a>Habilitar las previsiones de flujo de efectivo

[!include [banner](../includes/banner.md)]

Este artículo explica cómo activar la característica de previsiones de flujo de efectivo en Finance Insights.

> [!NOTE]
> Para utilizar predicciones de pagos en el flujo de efectivo, debe configurar la característica de predicciones de pagos de clientes como se describe en [Habilitar las predicciones de pagos de clientes](enable-cust-paymnt-prediction.md).
  
1. Abra el espacio de trabajo **Administración de funciones** y siga estos pasos:

    1. Seleccione **Buscar actualizaciones**.
    2. En la pestaña **Todo**, busque **Previsiones de flujo de efectivo**. Si no encuentra esa caraterística, busque **(Versión preliminar) Previsiones de flujo de efectivo**. 
    3. Activar la característica.

2. Vaya a **Gestión de efectivo y banco \> Configuración de pronóstico de flujo de efectivo** y agregue las cuentas de liquidez que deben incluirse en las previsiones. También configure la cuenta de liquidez para pagos en las pestañas **Clientes** y **Proveedores**. Asegúrese de volver a calcular la previsión de flujo de efectivo.

    > [!NOTE]
    > Si no se configuran cuentas de liquidez, no se puede generar el flujo de efectivo.
    >
    > Para obtener más información sobre cómo configurar previsiones de flujo de efectivo, consulte [Previsiones de flujo de efectivo](../cash-bank-management/cash-flow-forecasting.md).

3. Vaya a **Gestión de efectivo y banco \> Configurar \> Finance Insights (versión preliminar) \> Previsiones de flujo de efectivo (versión preliminar)** y siga estos pasos:

    1. En la pestaña **Pronóstico de flujo de efectivo**, seleccione **Habilitar característica**.
    2. Seleccione **Crear modelo de predicción**.

> [!NOTE]
> El entrenamiento del modelo **Pronóstico de flujo de efectivo** requiere datos que contengan más de 100 transacciones y abarquen más de un año. Recomendamos que tenga al menos dos años de datos con más de 1000 transacciones.

Para obtener más información sobre cómo configurar la capacidad de previsión de flujo de efectivo, consulte [Previsiones de flujo de efectivo](cash-flow-forecast-intro.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
