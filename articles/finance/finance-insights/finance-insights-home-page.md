---
title: Página de inicio de información financiera (versión preliminar)
description: Finance Insights proporciona modelos configurables y extensibles para ayudarle a predecir con precisión e inteligencia el flujo de efectivo de su empresa, predecir cuándo recibirá los pagos pendientes y generar una propuesta de presupuesto que puede acelerar su proceso de presupuestación. Todas estas características se basan en modelos de Machine Learning inteligentes.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 4876d2d4ad79dc09ce4b372eedf4c6ab31930957
ms.sourcegitcommit: 655b0e16c7aef6182cd58bc816b901470e1bb2ce
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2021
ms.locfileid: "6222519"
---
# <a name="finance-insights-home-page-preview"></a>Página de inicio de información financiera (versión preliminar)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Finance Insights proporciona modelos configurables y extensibles para ayudarle a predecir con precisión e inteligencia el flujo de efectivo de su empresa, predecir cuándo recibirá los pagos pendientes y generar una propuesta de presupuesto que puede acelerar su proceso de presupuestación. Todas estas características se basan en modelos de Machine Learning inteligentes. Cuando estas nuevas capacidades se combinan con la automatización en los pagos y cobros de proveedores, brindan un sistema financiero rico e inteligente que impulsa la toma de decisiones y le ayuda a tomar medidas para responder de manera efectiva a los desafíos comerciales actuales y anticipados.

La versión preliminar de Finance Insights está disponible para implementaciones de prueba en los Estados Unidos de América, Europa y el Reino Unido. Microsoft está agregando gradualmente soporte para más regiones.

Las características en vista previa (GB) pueden y deben activarse solo en entornos de espacio aislado de nivel 2. Los modelos de configuración e inteligencia artificial (IA) que se crean en un entorno de espacio aislado no se pueden migrar a un entorno de producción. Para más información, consulte [Condiciones de uso suplementarias para Vistas previas de Microsoft Dynamics 365](/dynamics365/legal/supp-dynamics365-preview#:~:text=Supplemental%20Terms%20of%20Use%20for%20Microsoft%20Dynamics%20365,%28governing%20your%20use%20of%20Microsoft%20Dynamics%20365%20Online%29.).

## <a name="prerequisites"></a>Requisitos previos

En esta sección se enumeran los requisitos para utilizar la información financiera. Siempre que sea posible, se proporcionan vínculos a fuentes de información adicional.

### <a name="legal-requirements"></a>Requisitos legales

Para solicitar el programa de vista previa, complete el [Contrato de Finance insights Preview para Dynamics 365 Finance](https://forms.office.com/FormsPro/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR56j8lZs0FdAvwT75_WNFyxUM1c0Uzc1RFpaU1RVTEwxVTNWUERPRThUSy4u).

### <a name="system-requirements"></a>Requisitos del sistema

Se requiere un entorno de espacio aislado de nivel 2 (caja múltiple) para obtener una vista previa de la información financiera. Para información general sobre los entornos, consulte [Planificación de entornos](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).

### <a name="version-requirements"></a>Requisitos de las versiones

Este documento se aplica a la versión 10.0.11 de las aplicaciones de Finance and Operations (actualización de la plataforma 35) y versiones posteriores.

### <a name="historical-data-requirements"></a>Requisitos de datos históricos

Se requiere al menos un año de facturas de clientes para entrenar correctamente el modelo de Machine Learning que se usa para la característica de predicciones de pagos de clientes.

Los datos de ejemplo están disponibles para los sistemas de demostración que tienen el conjunto de datos de demostración de Contoso.

### <a name="role-and-permission-requirements"></a>Requisitos de roles y permisos

Se realizarán cambios en Microsoft Dynamics 365 Finance, Microsoft Dynamics Lifecycle Services (LCS), Power Apps y Azure. Se requieren permisos correctos en estos entornos. Estos son algunos ejemplos de los cambios que se harán:

- Se creará un nuevo entorno en Microsoft Power Platform.
- Se crearán una cuenta de almacenamiento, un almacén de claves y una aplicación en Azure.
- El administrador de inquilinos de Active Directory tendrá que autorizar a la aplicación AI Builder para acceder al lago de datos.
- La característica se activará en Dynamics 365.

Será útil familiarizarse con el proceso de creación y administración de recursos en Azure, Microsoft Dataverse y LCS, a medida que complete este proceso.

## <a name="configure-finance-insights"></a>Configurar la información financiera

Debe completar algunos pasos de configuración antes de poder utilizar la información finaciera. Para obtener más información acerca de Finance insights, consulte:
  - Para versiones hasta la 10.0.19: [Configuración de Finance insights - hasta la versión 10.0.19](configure-for-fin-insites.md).
  - Para las versiones 10.0.20 y posteriores: [Configuración de Finance Insights (versión preliminar): versiones 10.0.20 y posteriores](configure-for-fin-insites-PubPrvw.md).

## <a name="create-a-data-integrator-project"></a>Crear un proyecto integrador de datos

Deberá crear un proyecto integrador de datos para que los datos que genera el modelo de Machine Learning puedan fluir hacia Dynamics 365 Finance. Para conocer los pasos para crear ese proyecto, consulte [Crear un proyecto integrador de datos](create-data-integrate-project.md).

## <a name="enable-finance-insights-capabilities"></a>Habilitar las capacidades de información financiera

Cuando haya completado los pasos de configuración y haya configurado los datos de demostración, debe activar y configurar cada capacidad que planea usar: predicciones de pago de clientes, pronóstico de flujo de efectivo y propuestas de presupuesto.

### <a name="enable-customer-payment-predictions"></a>Habilitar las predicciones de pago de clientes
Si está utilizando datos de demostración para probar las predicciones de pago de los clientes, es posible que deba importar datos de demostración adicionales para crear su modelo de IA correctamente. 

Para habilitar las predicciones de pago de clientes, debe completar un conjunto de pasos para crear un modelo de Machine Learning que use los datos de su organización para generar predicciones sobre cuándo es probable que los clientes paguen facturas pendientes y cuándo es probable que se paguen facturas específicas. Para obtener más información y los pasos específicos para completarlo, consulte [Habilitar las predicciones de pago de los clientes](enable-cust-paymnt-prediction.md). 

### <a name="enable-cash-flow-forecasting"></a>Habilitar previsiones de flujo de efectivo
Para habilitar la previsión de flujo de efectivo, debe completar un conjunto de pasos para crear un modelo de Machine Learning que utilice los datos de su organización para generar previsiones de flujo de efectivo. Para obtener más información y los pasos específicos para completarlo, consulte [Habilitar las predicciones de flujo de efectivo](enable-cash-flow-forecasting.md).

### <a name="enable-budget-proposals"></a>Habilitar propuestas de presupuesto

La función de propuestas de presupuestos utiliza un modelo de Machine Learning junto con los datos históricos de su organización para generar una propuesta de presupuesto. La propuesta generada puede ayudarle a comenzar un proceso de presupuestación que es más efectivo y eficiente que un proceso manual. Para conocer los pasos específicos para habilitar esta característica, consulte [Habilitar propuestas de presupuesto](enable-budget-proposal.md). 

## <a name="using-finance-insights-features"></a>Uso de las funciones de información financiera

### <a name="using-customer-payment-predictions"></a>Uso de las predicciones de pago de clientes

La previsión de flujo de efectivo inteligente se basa en la funcionalidad de previsión de flujo de efectivo existente en Dynamics 365 Finance. Para revisar la capacidad existente, consulte [Previsión de flujo de efectivo](../cash-bank-management/cash-flow-forecasting.md).

- Para saber cómo las predicciones de pago de clientes pueden proporcionar la información necesaria para ser actividades de cobro de manera proactiva, consulte [Utilizar las predicciones de pagos de clientes](use-customer-payment-predictions.md).
- Para obtener información que pueda ayudarle a evaluar la efectividad del modelo de predicción después de que haya comenzado a usar la característica, consulte [Evaluar el modelo de predicción de pagos inicial del cliente](evaluate-payment-prediction.md).
- Para obtener información que pueda ayudarlo a ajustar los datos que se utilizan para construir la predicción y, por lo tanto, mejorar su efectividad, consulte [Mejorar el modelo de predicción](improve-model.md).

Para obtener más información sobre los resultados de los modelos de predicción, consulte [Resultados de los modelos de Machine Learning](confusion-matrix.md).

### <a name="using-cash-flow-forecasts"></a>Uso de las previsiones de flujo de efectivo

La capacidad de pronóstico de flujo de efectivo puede ayudarle a estimar con mayor precisión su posición de efectivo. 

- Para conocer las nuevas capacidades de los pronósticos de flujo de efectivo, consulte [Pronóstico de flujo de efectivo](cash-flow-forecast-intro.md).
- Para obtener información sobre la importación de datos externos para incluirlos en su pronóstico de flujo de efectivo aquí, consulte [Utilizar datos externos en las previsiones de flujo de efectivo](external-data-in-cash-flow.md). 
- Para obtener información sobre cómo utilizar un modelo de IA para proyectar el flujo de efectivo a corto plazo, consulte [Posición de efectivo](cash-position.md).
- Para obtener información sobre cómo guardar posiciones de flujo de efectivo y pronósticos de flujo de efectivo como instantáneas, y para comparar una instantánea con los datos reales, consulte [Descripción general de instantáneas](payment-snapshots.md).

### <a name="using-budget-proposal"></a>Uso de propuesta de presupuesto

Para obtener información sobre cómo acelerar la creación de un presupuesto, consulte [Propuestas de presupuesto](budget-proposals.md). 

## <a name="feedback-and-support"></a>Comentarios y soporte técnico

Envíe un correo electrónico a [Información sobre pagos de clientes (Vista previa)](mailto:fiap@microsoft.com) si está interesado en proporcionar comentarios o necesita ayuda.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
