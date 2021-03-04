---
title: Habilitar las predicciones de pago de los clientes (versión preliminar)
description: Este tema explica cómo activar y configurar la característica de predicciones de pago de clientes en Finance Insights.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: e10aa9342ec9f089ef8ecec5e1221a31c580fc87
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645002"
---
# <a name="enable-customer-payment-predictions-preview"></a>Habilitar las predicciones de pago de los clientes (versión preliminar)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tema explica cómo activar y configurar la característica de predicciones de pago de clientes en Finance Insights. Active la característica en el espacio de trabajo **Administración de características** e introduzca los ajustes de configuración en la página **Parámetros de información financiera**. Este tema también incluye información que puede ayudarle a utilizar la característica de manera eficaz.

> [!NOTE]
> Antes de completar los siguientes pasos, asegúrese de completar los pasos de requisitos previos en el tema [Configurar para información financiera](configure-for-fin-insites.md).

1. Utilice la información de la página de entorno en Microsoft Dynamics Lifecycle Services (LCS) para conectarse a la instancia principal de Azure SQL para ese entorno. Ejecute el siguiente comando Transact-SQL (T-SQL) para activar paquetes piloto para el entorno de espacio aislado. (Es posible que tenga que activar el acceso para su dirección IP en LCS antes de poder conectarse de forma remota a Application Object Server \[AOS\].)

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED, PARTITION) VALUES ('PayPredEnableFeature', 1, 5637144576)`

    > [!NOTE]
    > Si su implementación de Microsoft Dynamics 365 Finance es una implementación de Service Fabric, puede omitir este paso. El equipo de información financiera ya debería haber activado el paquete piloto por usted. Si no ve la característica en el espacio de trabajo **Administración de características**, o si experimenta problemas al intentar activarlas, póngase en contacto con <fiap@microsoft.com>.

2. Active la característica de información de pago del cliente:

    1. Vaya a **Administración del sistema \> Espacios de trabajo \> Administración de características**.
    2. Busque la característica denominada **Información sobre pagos del cliente (versión preliminar)**.
    3. Seleccione **Habilitar ahora**.

    La característica Información de pagos de clientes ya está activada y lista para configurarse.

3. Configure la característica de Información de pagos de clientes:

    1. Vaya a **Crédito y cobros \> Configurar \> Información financiera \> Parámetros de información financiera**.

        [![Página de parámetros de información financiera antes de configurar la característica](./media/finance-insights-parameters.png)](./media/finance-insights-parameters.png)

    2. En la página **Parámetros de información financiera**, en la pestaña **Información sobre pagos de clientes**, seleccione el vínculo **Ver los campos de datos usados en el modelo de predicción** para abrir la página **Campos de datos para el modelo de predicción**. Allí, puede ver la lista predeterminada de campos que se utilizan para crear el modelo de predicción de inteligencia artificial (IA) para las predicciones de pago de los clientes.

        Para usar la lista predeterminada de campos para crear el modelo de predicción, cierre la página **Campos de datos para el modelo de predicción**, y luego, en la página **Parámetros de información financiera**, configure la opción **Habilitar característica** en **Sí**.

    3. Especifique el período de transacción "muy tarde" para definir qué significa el ámbito de predicción **Muy tarde** para su negocio.

        Para cada factura abierta, el sistema predice la probabilidad de pago en tres ámbitos: **Puntutal**, **Tarde** y **Muy tarde**.

        - **Puntual**: este grupo incluye pagos que se prevé que se pagarán en la fecha de vencimiento de la transacción o antes.
        - **Tarde**: este segmento incluye los pagos que se prevé que se pagarán después de la fecha de vencimiento de la transacción, pero antes del inicio del período de transacción "muy tarde".
        - **Muy tarde**: este segmento incluye los pagos que se prevé que se pagarán después del comienzo del perioro de transacción "muy tarde".

        > [!NOTE]
        > Si cambia el período de transacción "muy tarde" y selecciona **Cambiar el umbral de tarde** después de creado el modelo de predicción de IA para los pagos de los clientes, se elimina el modelo de predicción existente y se crea un nuevo modelo. El nuevo modelo de predicción moverá las transacciones al período "muy tarde", según la configuración introducida para definirlo.

    4. Una vez que haya terminado de definir el período de transacción "muy tarde", seleccione **Crear modelo de predicción** para crear el modelo de predicción. La sección **Modelo de predicción** de la página **Parámetros de información financiera** muestra el estado del modelo de predicción.

        > [!NOTE]
        > En cualquier momento, mientras se crea el modelo de predicción, puede seleccionar **Restablecer la creación del modelo** para reiniciar el proceso.

    La característica ya se ha configurado y está lista para utilizarla.

Una vez que la característica se ha activado y configurado, el modelo de predicción se ha creado y está funcionando, la sección **Modelo de predicción** de la página **Parámetros de información financiera** muestra la precisión del modelo, como se muestra en la siguiente ilustración.

[![Precisión del modelo de predicción en la página de parámetros de información financiera](./media/finance-insights-parameters-accuracy.png)](./media/finance-insights-parameters-accuracy.png)

## <a name="release-details"></a>Detalles de la liberación

La versión preliminar pública de Finance Insights está disponible para implementaciones de prueba en los Estados Unidos de América, Europa y el Reino Unido. Microsoft está agregando gradualmente soporte para más regiones.

Las funciones de versión preliminar pública pueden y deben activarse solo en entornos de espacio aislado de nivel 2. Los modelos de configuración e IA que se crean en un entorno de espacio aislado no se pueden migrar a un entorno de producción. Para más información, consulte [Condiciones de uso suplementarias para Vistas previas de Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/public-preview-terms).

## <a name="privacy-notice"></a>Aviso de privacidad

Las versiones preliminares (1) pueden utilizar menos privacidad y menos medidas de seguridad que el servicio Dynamics 365 Finance and Operations, (2) no están incluidas en el acuerdo de nivel de servicio para este servicio, (3) no deben utilizarse para procesar datos personales u otros datos que estén sujetos a requisitos de cumplimiento legal o reglamentario, y (4) disponen de soporte limitado.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]