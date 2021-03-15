---
title: Notificaciones de alertas del cliente por correo electrónico
description: Este tema proporciona información acerca de cómo configurar las reglas que envían notificaciones por correo electrónico para los eventos predefinidos que ocurren.
author: tjvass
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2019-1-29
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: a1d520584e331631bb5a6a88ba6c9a8b50b3d29e
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "4798632"
---
# <a name="client-alert-notifications-by-email"></a>Notificaciones por correo electrónico de alertas del cliente

[!include [banner](../includes/banner.md)]

Puede definir reglas de alertas personalizadas que siguen vistas filtradas de datos y registra automáticamente dichas notificaciones por correo electrónico cuando los eventos predefinidos aparecen. La opción para enviar notificaciones por correo electrónico está disponible para todos los tipos alertas admitidos y también puede activarlas para las reglas de alertas existentes.

Puede usar los controles integrados para crear reglas de alertas que controlan las vistas filtradas guardadas de los trabajos por lotes del sistema. Controlando el valor del campo **Estado** , también puede configurar las reglas de alertas que envían el correo electrónico cuando falla un trabajo por lotes. Una vez ha creado estas reglas de alertas, ya no tiene que comprobar los informes de los cambios en los datos empresariales. En su lugar, puede dejar al servicio de detección de cambios inteligente que lo controle por usted.

Las alertas del cliente dependen del subsistema de correo electrónico que ofrece la integración con Microsoft Office. Se recomienda que use el proveedor del protocolo simple de transferencia de correo (SMTP), de modo que la distribución de correo electrónico no tenga que basarse en un cliente de correo local.

Para enviar notificaciones por correo electrónico, los clientes deben configurar los servicios de correo electrónico integrados. Las notificaciones por correo electrónico se envían a los destinatarios en nombre del propietario de las alertas.

Para obtener más información sobre cómo configurar el correo electrónico, consulte [Configurar y enviar el correo electrónico](../organization-administration/configure-email.md).

En la imagen siguiente se muestra el cuadro **Crear regla de alertas** , que ahora incluye una opción **Enviar correo electrónico** .

[![Cree el cuadro de diálogo de la regla de alerta, donde la opción de correo electrónico de envío se establece en Sí](./media/Create-alert-rule-form.png)](./media/Create-alert-rule-form.png)

> [!NOTE]
> Cuando la opción **Enviar correo electrónico** se establece en **Sí**, las notificaciones de alertas continuarán siendo entregadas Centro de actividades.

## <a name="alert-notification-email-templates"></a>Plantillas de correo electrónico de notificación de alerta

El servicio registra notificaciones por correo electrónico mediante las plantillas de correo electrónico predefinidas que envían los detalles básicos de la notificación de alerta.

La siguiente imagen muestra la estructura de las notificaciones alertas cuando se reciben por correo electrónico.

[![Notificaciones de alerta basadas en plantillas para la creación de registros, cambios de campos y eliminación de plantilla](./media/Alert-email-templates.png)](./media/Alert-email-templates.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]