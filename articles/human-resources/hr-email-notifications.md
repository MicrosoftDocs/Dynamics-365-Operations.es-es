---
title: Notificación de beneficios por correo electrónico
description: Este artículo proporciona una visión general de la característica de notificación de beneficios por correo electrónico en Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/01/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d550cbb2f639535dbb43765c9fb0632a514fbe8c
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2022
ms.locfileid: "9229923"
---
# <a name="benefits-email-notification"></a>Notificación de beneficios por correo electrónico

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [banner](../includes/preview-banner.md)]

La función de notificación por correo electrónico permite enviar notificaciones y recordatorios por correo electrónico a los empleados en los siguientes escenarios:

- Nueva inscripción de contratación
- Abrir inscripción
- Eventos de vida que reúnen los requisitos

Puede crear y configurar varias plantillas de correo electrónico y enviar las notificaciones mediante el espacio de trabajo **Gestión de beneficios** y la página **Beneficios para los trabajadores**. También puede realizar un seguimiento del historial de notificaciones/recordatorios.

## <a name="set-up-human-resources-shared-parameters"></a>Configurar parámetros compartidos de Recursos humanos

En la página **Parámetros compartidos de recursos humanos**, puede crear plantillas de correo electrónico de beneficios para diferentes tipos de comunicación que se envían a los empleados o grupos de empleados.

## <a name="create-a-new-email-id-template"></a>Crear una nueva plantilla de id. de correo electrónico

Para crear una nueva plantilla de id. de correo electrónico, siga estos pasos:

1. Vaya a **Plantillas de correo electrónico de sistema**.
2. Seleccione **Nuevo**.
3. En el campo **Id. de correo electrónico**, escriba un nombre.
4. Establezca los otros campos según sea necesario.
5. Seleccione **Mensaje de correo electrónico** para cargar la plantilla.
6. En la página **Parámetros compartidos de recursos humanos**, seleccione la nueva plantilla en **Plantillas del sistema** y muévala bajo **Plantillas para beneficios**.

## <a name="send-email-to-employees"></a>Enviar correo electrónico a empleados

Para enviar un correo electrónico a un nuevo empleado que aún no ha comenzado, siga estos pasos.

1. Abra el espacio de trabajo **Administración de beneficios**.
2. Seleccione el mosaico para el grupo de empleados a los que desea enviar el correo electrónico.
3. Seleccione **Enviar correo electrónico**.
4. Seleccione los empleados a los que desea enviar el correo.
5. Seleccione **Enviar correo electrónico**.
6. Seleccione la plantilla que se desea usar.
7. Seleccione **Aceptar** para enviar el correo.

    Puede revisar el mensaje de correo electrónico y el estado desde la página **Beneficio del trabajador** del empleado o seleccionando **Historial de correo electrónico de beneficios** en la sección **Enlaces** del espacio de trabajo **Gestión de beneficios**. También puede enviar el correo electrónico desde la página **Plan de beneficios para trabajadores**.

8. Para ver el historial de correo electrónico de beneficios, en el espacio de trabajo **Gestión de beneficios**, en la sección **Enlaces**, seleccione **Historial de correo electrónico de beneficios**.
9. Vea el historial de correo electrónico completo para los correos electrónicos de beneficios que se han enviado. Para revisar el contenido del correo electrónico, seleccione **Mostrar mensaje**.
10. Seleccione **Trabajador**.
11. En la página **Plan de beneficios para trabajadores**, puede enviar un correo electrónico y ver el historial de correo electrónico de beneficios.

El espacio de trabajo **Gestión de beneficios** incluye diferentes iconos. Puede enviar correos electrónicos seleccionando la plantilla relacionada. Si se han enviado los correos electrónicos de inscripción de nuevos empleados, seleccione el icono **Nueva contratación no iniciada** y, a continuación, seleccione el enlace **Enviar recordatorio**. Puede seleccionar una plantilla de recordatorio y establecer el título de la notificación como primer, segundo o tercer recordatorio.
