---
title: Información de pago del cliente (vista previa)
description: Este tema describe la capacidad de la función de la información de pago que ayuda a mejorar la comprensión de las prácticas más comunes de pago de clientes individuales y puede identificar las circunstancias que justifican el inicio de los procesos de cobro de cobro antes de lo que lo habría hecho de otro modo.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/06/2019
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
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: f9f1e4ae4270380c88069723e768fd44ecf8c113
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2774042"
---
# <a name="customer-payment-insights-preview"></a>Información de pago del cliente (vista previa)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tema describe la capacidad de la función de la información de pago que ayuda a mejorar la comprensión de las prácticas más comunes de pago de clientes individuales y puede identificar las circunstancias que justifican el inicio de los procesos de cobro de cobro antes de lo que lo habría hecho de otro modo. 

## <a name="overview"></a>Visión general

Las organizaciones a menudo encuentran difícil predecir cuándo los clientes pagarán sus facturas. Esta falta de información conduce a previsiones de flujo de efectivo menos precisas, procesos de cobro que empiezan demasiado tarde y pedidos que se entregan a clientes que podrían no realizar el pago. La Información de pago del cliente (versión preliminar) ayuda a las organizaciones a predecir cuándo se pagará una factura de cliente y ayuda a las organizaciones a crear estrategias de cobro que mejoren la probabilidad de que se les pague a tiempo. 

## <a name="predictions"></a>Predicciones

Las predicciones de pago permitirán a las organizaciones mejorar sus procesos empresariales ayudándolas a identificar fácilmente las facturas que probablemente se pagarán tarde, y tomar las medidas adecuadas que mejoren las posibilidades de cobrar a tiempo.

Con el uso de un modelo de aprendizaje automático, que aproveche facturas, pagos y los datos históricos del cliente, la información de los pagos de los clientes (versión preliminar) predice con más precisión cuándo un cliente pagará una factura pendiente.

Para cada factura abierta, la Información de pago del cliente (versión preliminar) predice tres probabilidades de pago:

-   Probabilidad de pago efectuado a tiempo 
-   Probabilidad de pago efectuado tarde
-   Probabilidad de pago efectuado muy tarde

Para ayudar a las organizaciones a comprender el importe total de pago que pueden esperar de un cliente en uno de las tres categoría, a tiempo, tarde y muy tarde, Información de pago del cliente (versión preliminar) también proporcionan una vista agregada de los pagos previstos.

[![Vista agregada de las predicciones de pago](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)

Además, cada factura se asigna a una probabilidad de pago a tiempo. Si la probabilidad de pago a tiempo es inferior al 50 %, las facturas se etiquetan con un círculo rojo para indicar que estas facturas puede requerir la asistencia de cobros. 

[![Lista de posibilidades de pago](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)

Información de pago del cliente (versión preliminar) también proporcionan información contextual para explicar la predicción, como los factores de alto nivel que influenciaron las predicciones, el estado actual del negocio con el cliente, y los detalles sobre el comportamiento histórico de pago del cliente. En muchos negocios, el proceso de cobros se ha sido una actividad reactiva; el proceso de cobros no se inicia hasta que vencen las facturas debidas. 

Con Información de pago del cliente (versión preliminar), las organizaciones pueden ser más proactivas respecto a los cobros. No tienen que esperar más a que las transacciones venzan para iniciar el proceso de cobro. En su lugar, pueden usar la capacidad de predicción de pago para determinar si los cobros proactivos mejorarán la probabilidad de pagar a tiempo. La predicción de pago también proporciona a las empresas la información necesaria para justificar el inicio del proceso de cobros de forma anticipada.

## <a name="methodology"></a>Metodología

Desarrollar e implementar una solución de inteligencia artificial es complicado. Hace falta un equipo de científicos de datos, expertos en la material e ingenieros, que trabajen durante mucho tiempo para formular, desarrollar, implementar y mantener una solución utilizable de inteligencia artificial. Estamos haciendo que sea fácil implementar y utilizar soluciones de inteligencia artificial en Finance. Estamos preempaquetando soluciones de inteligencia artificial en Finance que se incorporan en Microsoft AI Builder. Los usuarios finales, con un solo clic, puede implementar la solución de inteligencia artificial y comenzar aprovechar las prestaciones de las predicciones inteligentes. Si una organización no está satisfecha con la precisión de las predicciones, un usuario avanzado, otra vez con un único clic, puede especificar la experiencia de la extensión de AI Builder y seleccionar o anular la selección de los campos usados para generar predicciones. Una vez que están listos, pueden preparar y publicar los cambios y el modelo recién entrenado se seleccionará automáticamente para las predicciones en Finance.

## <a name="how-to-get-customer-payment-insights-preview"></a>Cómo obtener Información de pago del cliente (versión preliminar)

Si está interesado en probar Información de pago del cliente (versión preliminar), envíe un correo electrónico al [Información de pago del cliente (versión preliminar)](mailto:fiap@microsoft.com).

## <a name="privacy-notice"></a>Aviso de privacidad

Las versiones preliminares (1) pueden utilizar menos medidas de privacidad y seguridad que el servicio Dynamics 365 Finance and Operations, (2) no están incluidas en el acuerdo de nivel de servicio para este servicio, (3) no deben utilizarse para procesar datos personales u otros datos que estén sujetos a requisitos de cumplimiento legal o reglamentario, y (4) tienen soporte limitado.


