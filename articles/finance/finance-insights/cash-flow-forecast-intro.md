---
title: Previsión de flujo de efectivo (versión preliminar)
description: Este tema describe la capacidad de pronóstico de flujos de efectivo.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-19
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 3f16c8471123969443af52ff9bed7fc017b8e9c2
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "6339224"
---
# <a name="cash-flow-forecast-preview"></a>Previsión de flujo de efectivo (versión preliminar)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

El flujo de efectivo es crítico para cualquier negocio. Incluso las empresas rentables pueden enfrentarse a la insolvencia si no mantienen el flujo de efectivo para satisfacer las necesidades inmediatas. La capacidad de previsión de flujo de efectivo en las informaciones de Finance puede ayudar a las empresas a monitorear y administrar sus saldos de efectivo de manera efectiva. Esta característica utiliza el aprendizaje automático para ayudar a las empresas a pronosticar los flujos de efectivo con mayor precisión que antes. También puede ayudar a los gerentes a tomar decisiones que optimicen las oportunidades en el contexto de su posición de efectivo actual. 

Para la mayoría de las empresas, administrar el flujo de efectivo y ejecutar la previsión del flujo de efectivo es un proceso tedioso, repetitivo y manual. La mayoría de las empresas confían en soluciones de Microsoft Excel que tienen diversos grados de complejidad. Los desafíos de pronosticar con precisión el flujo de efectivo incluyen los siguientes:

- Los datos no están disponibles para los tomadores de decisiones porque están dispersos en varios lugares, que incluyen: 
  - El sistema de planificación contable o de recursos empresariales
  - El software de planificación financiera
  - Excel
  - Aplicaciones de software adicionales 
- La previsión se basa en el conocimiento interno que reside en "silos" dentro de cada dominio o departamento.
- Medir la precisión de la previsión del flujo de efectivo una vez que se han materializado las finanzas es incierto y difícil.
    
## <a name="details-of-the-cash-flow-forecasts-capability"></a>Detalles de la capacidad de pronóstico de flujo de efectivo
La función de pronóstico de flujo de efectivo incluye la siguiente funcionalidad. 

- Facilita la integración de datos de flujo de efectivo de sistemas externos en Dynamics 365 Finance. Los pronósticos de flujo de efectivo también pueden utilizar el marco de importación y exportación de datos. Este marco facilita la integración con Excel OData. También puede combinar datos de varias fuentes para crear una solución integral de flujo de efectivo. 

- Introduce una posición de efectivo inteligente. La posición de efectivo se crea en función del comportamiento de pago del cliente para predecir cuándo una empresa puede esperar que llegue efectivo a sus cuentas. También analiza los patrones históricos de pago a los proveedores para predecir cuándo es probable que se paguen las facturas y los pedidos futuros. 

- Introduce el pronóstico de flujo de efectivo inteligente para pronósticos a largo plazo, utilizando un pronóstico de serie temporal a través de la integración automatizada con AI Builder.

- Brinda la capacidad de guardar posiciones específicas de flujo de efectivo o pronósticos, editarlos y luego comparar y medir fácilmente el rendimiento del pronóstico con las finanzas reales.

- Permite el análisis hipotético mediante la comparación de instantáneas. Por ejemplo, puede crear varias instantáneas que representen puntos de vista optimistas, pesimistas y más realistas de su flujo de efectivo y luego comparar y ver las diferencias.

- Brinda la capacidad de ver el pronóstico de flujo de efectivo en múltiples divisas, en las entidades jurídicas, y filtrar y ver el flujo de efectivo relacionado con una cuenta bancaria. 

- Le permite filtrar y ver las cuentas bancarias relacionadas con las dimensiones financieras.

La funcionalidad de pronóstico de flujo de efectivo de Dynamics 365 Finance permitirá a su organización transformar la proyección de flujo de efectivo tediosa y compleja, aunque repetitiva, en un proceso simple y automatizado. Automatizar los aspectos más tediosos de la previsión del flujo de efectivo le permite concentrarse en la toma de decisiones críticas para impulsar los resultados comerciales deseados.

## <a name="setting-up-dimensions-for-cash-flow-forecasting"></a>Configurar dimensiones para la previsión del flujo de efectivo
Una nueva pestaña de la página **Configuración de pronósticos de flujo de efectivo** le permite controlar qué dimensiones financieras utilizar para filtrar en el espacio de trabajo **Previsión de flujo de efectivo**. Esta pestaña solo aparecerá cuando la función de pronósticos de flujo de efectivo esté habilitada. 

En la pestaña **Dimensiones**, elija de la lista de dimensiones que se utilizarán para el filtrado y utilice las teclas de flecha para moverlas a la columna de la derecha. Solo se pueden seleccionar dos dimensiones para filtrar los datos de pronósticos de flujo de efectivo. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
