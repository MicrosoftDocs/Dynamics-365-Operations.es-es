---
title: P+F sobre el modo de creación de clientes asincrónico
description: Este artículo proporciona respuestas a preguntas frecuentes acerca del modo de creación de clientes asincrónica en Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 08/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: bd5741aeb3278f1d40d63bb02ca57571a907dc21
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2022
ms.locfileid: "9474079"
---
# <a name="asynchronous-customer-creation-mode-faq"></a>P+F sobre el modo de creación de clientes asincrónico

[!include [banner](includes/banner.md)]

Este artículo proporciona respuestas a preguntas frecuentes acerca del modo de creación de clientes asincrónica en Microsoft Dynamics 365 Commerce.

### <a name="why-cant-i-enable-the-enable-editing-customers-in-asynchronous-mode-feature"></a>¿Por qué no puedo habilitar la función "Habilitar la edición de clientes en modo asíncrono"?

Antes de habilitar la característica **Habilitar la edición de clientes en modo asíncrono**, debe habilitar las siguientes características:

- Mejoras de rendimiento para pedidos de clientes y transacciones de clientes
- Habilitar la creación mejorada de clientes asincrónicos
- Habilitar creación asincrónica para direcciones de clientes

### <a name="why-do-i-still-see-real-time-service-calls-made-to-commerce-headquarters-after-the-enable-editing-customers-in-asynchronous-mode-feature-is-enabled"></a>¿Por qué sigo viendo llamadas de servicio en tiempo real realizadas a Commerce headquarters después de habilitar la función "Habilitar edición de clientes en modo asíncrono"?

Este problema ocurre cuando Commerce Data Exchange (CDX) no se han ejecutado trabajos para garantizar que el estado de la característica y otros metadatos del canal estén sincronizados con el canal. Antes de volver a intentar el escenario, asegúrese de que los siguientes trabajos de CDX se ejecuten en Commerce headquarters:

- 1110 (Configuración global)
- 1010 (Clientes)
- 1070 (Configuración del canal)

Es posible que los datos que se almacenan en caché en Commerce Scale Unit  (CSU) no se reflejen inmediatamente en Commerce headquarters después de que se hayan ejecutado los trabajos de CDX.

### <a name="why-doesnt-commerce-headquarters-show-customer-creation-or-updates-from-the-point-of-sale-pos-or-e-commerce-channel"></a>¿Por qué Commerce headquarters no muestra la creación de clientes o las actualizaciones desde el punto de venta (POS) o el canal de comercio electrónico?

Asegúrese de que las siguientes acciones se hayan realizado en el orden en que se enumeran aquí.

1. Ejecute el trabajo CDX P en Commerce headquarters para asegurarse de que los datos de clientes asíncronos que se almacenan en las tablas **RETAILASYNCCUSTOMERV2**, **RETAILASYNCADDRESSV2**, **RETAILASYNCCUSTOMERCONTACT**, **RETAILASYNCCUSTOMERAFFILIATION** y **RETAILASYNCCUSTOMERATTRIBUTEV2** está disponible en Commerce headquarters.
1. Ejecute el trabajo por lotes **Sincronizar las solicitudes de clientes y canales** en Commerce headquarters. Después de la ejecución exitosa del trabajo por lotes, todos los registros que se hayan procesado con éxito de las tablas mencionadas anteriormente tendrán el campo **OnlineOperationCompleted** establecido en **1**.
