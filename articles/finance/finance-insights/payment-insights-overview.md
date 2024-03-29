---
title: Predicciones de pago de cliente
description: Este artículo describe la capacidad de predicciones de pago que puede ayudarle a conocer mejor las prácticas de pago típicas de un cliente. Esta característica también puede ayudarle a identificar circunstancias que deberían provocar que comience procesos de cobro antes de lo haya hecho de otra manera.
author: ShivamPandey-msft
ms.date: 11/03/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 5d16b42b4538a18ca3dd9d3bac25ed1af1441ace
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903171"
---
# <a name="customer-payment-predictions"></a>Predicciones de pago de cliente

[!include [banner](../includes/banner.md)]

Este artículo describe la capacidad de predicciones de pago que puede ayudarle a conocer mejor las prácticas de pago típicas de un cliente. Esta característica también puede ayudarle a identificar circunstancias que deberían provocar que comience procesos de cobros antes de lo haya hecho de otra manera.

## <a name="overview"></a>Información general

Las organizaciones a menudo encuentran difícil predecir cuándo los clientes pagarán sus facturas. Esta falta de información puede causar los siguientes problemas:

- Previsiones de flujo de efectivo menos precisas
- Procesos de cobros que comienzan demasiado tarde
- Pedidos que se entregan a clientes que podrían incumplir su pago

Las predicciones de pagos de clientes ayudan a las organizaciones a predecir cuándo se pagará una factura a un cliente. Por lo tanto, pueden crear estrategias de cobro que ayuden a aumentar la probabilidad de que se paguen puntualmente.

## <a name="predictions"></a>Predicciones

Las predicciones de pago permiten a las organizaciones mejorar sus procesos comerciales ayudándoles a identificar las facturas que probablemente se pagarán con retraso. La organización puede usar esa información para tomar acciones que mejoren las posibilidades de que se le pague puntualmente.

La función de predicciones de pago de clientes utiliza un modelo de aprendizaje automático para predecir con mayor precisión cuándo un cliente pagará una factura pendiente. Este modelo de aprendizaje automático incluye facturas, pagos y datos de clientes históricos.

Para cada factura abierta, la característica asigna tres probabilidades de pago:

- La probabilidad de que el pago se realice puntualmente
- La probabilidad de que el pago se realice tarde
- La probabilidad de que el pago se realice muy tarde

La característica también proporciona una vista agregada de los pagos esperados.

[![Vista agregada de las predicciones de pago.](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)

A cada factura se le asigna a una probabilidad de pago puntual. Las facturas con probabilidad de pago puntual inferior al 50 por ciento se etiquetan con un círculo rojo para indicar que estas facturas pueden requerir la asistencia de un agente de cobros.

[![Lista de posibilidades de pago.](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)

La característica Predicciones de pago de clientes también proporciona información contextual para explicar la predicción. Esta información incluye los principales factores que influyeron en la predicción, el estado actual del negocio con el cliente y detalles sobre el comportamiento de pago histórico del cliente.

En muchas empresas, el proceso de cobro ha sido una actividad reactiva. En otras palabras, el proceso de cobro no comienza hasta que vencen las facturas. Las predicciones de pago del cliente permiten a las organizaciones ser más proactivas respecto a los cobros. Ya no tienen que esperar a que las transacciones venzan para iniciar el proceso de cobros. En su lugar, pueden usar la capacidad de predicciones de pagos para determinar si los cobros proactivos mejorarán la probabilidad de que se pahuen puntualmente.

## <a name="methodology"></a>Metodología

En el pasado, normalmente era difícil desarrollar e implementar una solución de inteligencia artificial (IA). El proceso requería un equipo con científicos de datos, expertos en el tema (SME) e ingenieros, que trabajaban durante mucho tiempo para formular, desarrollar, implementar y mantener una solución utilizable de IA. Las predicciones de pago de los clientes facilitan la implementación y el uso de una solución de inteligencia artificial en Microsoft Dynamics 365 Finance. Microsoft está preempaquetando soluciones de IA creadas sobre Microsoft AI Builder. Por lo tanto, los usuarios pueden implementar la solución de IA con un solo clic del mouse para aprovechar las ventajas de las predicciones inteligentes. Si no está satisfecho con la precisión de las predicciones, un usuario avanzado puede (de nuevo, con un único clic), introducir la experiencia de la extensión de AI Builder y seleccionar o anular la selección de los campos usados para generar predicciones. Cuando esté listo, puede "entrenar" el modelo y publicar los cambios. El modelo recién entrenado se seleccionará automáticamente para generar predicciones en Dynamics 365 Finance.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
