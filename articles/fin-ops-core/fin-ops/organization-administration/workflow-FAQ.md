---
title: Preguntas frecuentes de flujo de trabajo
description: Este tema responde a las preguntas frecuentes acerca del sistema de flujo de trabajo.
author: ChrisGarty
ms.date: 03/01/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0e9e2000684081035f35ea55e1c773a4f6976d74
ms.sourcegitcommit: 967b93bb42413b5b38b817f924015468312a93a0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2022
ms.locfileid: "8370889"
---
# <a name="workflow-faq"></a>Preguntas frecuentes sobre flujos de trabajo

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Este tema responde a las preguntas frecuentes acerca del sistema de flujo de trabajo.

## <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a>¿Por qué se reciben varias notificaciones cuando se rechaza un elemento de trabajo?
Si se rechaza un elemento de trabajo, ese elemento de trabajo se completa como rechazado. Otro elemento de trabajo se crea y se asigna al originador. Esto significa que hay una notificación al originador del elemento de trabajo rechazado, y una notificación independiente al usuario asignado al nuevo elemento de trabajo de “cambio solicitado”. 

Cada notificación es para un elemento de trabajo diferente, pero la semejanza puede provocar la confusión. Estamos buscando formas de mejorar esto en una versión futura.

## <a name="why-are-my-workflow-exports-failing"></a>¿Por qué mis exportaciones del flujo de trabajo están fallando?
Existen actualmente un límite en la función de exportación del flujo de trabajo que impide que los nombres del flujo de trabajo pasen de 48 caracteres. Usar un nombre que sea más largo de 48 caracteres puede resultar en un error “El servidor no puede autenticar la solicitud” y/o evitar que se exporte un archivo sin un tipo de archivo. La siguiente entrada del blog proporciona más detalles [Solución de problemas de exportación del flujo de trabajo](https://community.dynamics.com/365/financeandoperations/b/elandaxdynamicsaxupgradesanddevelopment/posts/workflow-export-troubleshooting).

## <a name="can-the-submitter-of-a-workflow-also-approve-the-workflow"></a>¿El remitente de un flujo de trabajo también puede aprobar el flujo de trabajo?
Sí, el remitente de un flujo de trabajo también puede aprobar el flujo de trabajo si está configurado de ese modo. Para evitar este comportamiento, establezca **Administración del sistema > Flujo de trabajo > Parámetros del flujo de trabajo > General > Aprobador > No permitir aprobación por parte del remitente** en **Sí**.

## <a name="can-i-add-alerts-to-workflows-to-provide-notifications-to-users"></a>¿Puedo agregar alertas a flujos de trabajo para proporcionar notificaciones a los usuarios?
A continuación se muestran algunas áreas fundamentales a tener en cuenta para agregar a los flujos de trabajo para proporcionar notificaciones:
- Alertas frente a mecanismos de notificación de flujo de trabajo
    - Se pueden configurar alertas para cambios de registro. Los flujos de trabajo cambian los registros, por lo que es posible configurar una alerta relacionada con un cambio de registro provocado por un flujo de trabajo. Sin embargo, dado que los flujos de trabajo tienen diferentes opciones de notificación integradas, el uso de alertas no es ideal.
- Notificaciones estándar de flujos de trabajo 
    - Los flujos de trabajo tienen notificaciones por correo electrónico integradas. Un cliente puede configurar las notificaciones para que los usuarios reciban correos electrónicos. Estas notificaciones no generan mensajes del Centro de actividades para los usuarios.
    - En una actualización futura, agregaremos un mensaje del Centro de actividades para que se asigne a un usuario un elemento de trabajo del flujo de trabajo. 
- Agregar notificaciones a flujos de trabajo
    - Se pueden crear mensajes del Centro de actividades para determinados usuarios, como un mensaje creado desde un flujo de trabajo en X++.
    - [Los flujos de trabajo tienen eventos de negocio](../../dev-itpro/business-events/business-events-workflow.md) que el cliente podría utilizar para activar los flujos que tienen las notificaciones que está buscando.   

En resumen, si un usuario no obtiene la notificación adecuada del Centro de actividades cuando se le asigna un elemento de trabajo del flujo de trabajo, utilice [Eventos de negocio del flujo de trabajo](../../dev-itpro/business-events/business-events-workflow.md) con Microsoft Power Automate para proporcionar notificaciones adicionales o distintas.

## <a name="why-is-workflow-editor-not-able-to-start-under-ad-fs"></a>¿Por qué el editor de flujo de trabajo no puede iniciarse en AD FS?
Cuando el editor de flujo de trabajo se ejecuta con los Servicios de federación de Active Directory (AD FS) en un entorno actualizado, es posible que tenga problemas para iniciarse. Si es así, asegúrese de agregar la dirección URL " https://dynamicsaxworkfloweditor/" a la propiedad **Microsoft Dynamics 365 for Operations On-premises - Flujo de trabajo - Aplicación nativa** en la configuración de ADFS.

## <a name="why-am-i-getting-sql-deadlocks-on-workflow-processing"></a>¿Por qué obtengo puntos muertos de SQL en el procesamiento del flujo de trabajo? 
El valor de campo predeterminado para **Número de elementos de flujo de trabajo por lote** sobre el **Parámetros de flujo de trabajo** la página es 0. Un valor de 0 hace que el valor predeterminado cambie a 20 artículos por lote. Tenga cuidado al ajustar este valor porque una gran cantidad de elementos por lote (> 40) puede causar puntos muertos de SQL.

## <a name="what-is-the-workflow-enhanced-error-feature"></a>¿En qué consiste la característica Error mejorado de flujo de trabajo?
La característica Error mejorado de flujo de trabajo incluida en la versión 10.0.13 agrega códigos de error para diferenciar distintas clases de errores del flujo de trabajo. Los mensajes de error notificados serán en su mayoría similares, con pequeñas variaciones para que sean más claros.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
