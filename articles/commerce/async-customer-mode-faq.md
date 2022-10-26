---
title: P+F sobre el modo de creación de clientes asincrónico
description: Este artículo proporciona respuestas a preguntas frecuentes acerca del modo de creación de clientes asincrónica en Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: 64c895fb9f3e55f7680759fa72626be6660aa67c
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690212"
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

1. Ejecute el trabajo CDX P en Commerce headquarters para asegurarse de que los datos de clientes asíncronos que se almacenan en las tablas **RETAILASYNCCUSTOMERV2**, **RETAILASYNCADDRESSV2**, **RETAILASYNCCUSTOMERCONTACT**, **RETAILASYNCCUSTOMERAFFILIATION** y **RETAILASYNCCUSTOMERATTRIBUTEV2**.
1. Ejecute el trabajo por lotes **Sincronizar las solicitudes de clientes y canales** en Commerce headquarters. Después de la ejecución exitosa del trabajo por lotes, todos los registros que se hayan procesado con éxito de las tablas mencionadas anteriormente tendrán el campo **OnlineOperationCompleted** establecido en **1**.

### <a name="how-do-i-know-which-customer-management-in-asynchronous-mode-operation-has-failed-and-how-do-i-make-changes-if-they-are-required"></a>¿Cómo sé qué administración de clientes en modo asíncrono ha fallado y cómo hago cambios si son necesarios?

Para ver todas las operaciones en modo asíncrono y su estado de sincronización, en la Commerce headquarters vaya a **Comercio y Retail \> Clientes \> Estado de sincronización del cliente**. Para realizar cambios, edite una operación específica, actualice los campos, seleccione **Guardar** y luego seleccione **Sincronizar** para sincronizar los cambios.

