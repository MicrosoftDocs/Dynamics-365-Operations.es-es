---
title: Crear y enviar una guía de incorporación con Dynamics 365 Talent - Onboard
description: Este tema explica cómo usar la aplicación Microsoft Dynamics 365 Talent - Onboard para crear una guía de incorporación para los nuevos empleados contratados. Esta tarea es el primer paso esencial en la estrategia de contratación hasta la jubilación de la gestión del capital humano (HCM).
author: andreabichsel
manager: ''
ms.date: 05/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-05-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 3c465c667cbb8a66f301637ca620429b0ddc11c6
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550352"
---
# <a name="create-and-send-an-onboarding-guide-by-using-dynamics-365-talent---onboard"></a>Crear y enviar una guía de incorporación con Dynamics 365 Talent - Onboard

[!include [banner](includes/banner.md)]

Microsoft Dynamics 365 Talent: Onboard permite crear guías de incorporación a partir de plantillas que creó usted mismo, a partir de plantillas disponibles en una galería, o a partir de cero.

Una vez que haya creado una guía de incorporación, puede enviarla al empleado recién contratado. Como alternativa, puede enviarla a varios empleados recién contratados que especifique en un archivo Microsoft Excel que se descarga de aplicación Onboard.

## <a name="create-an-onboarding-guide-from-a-template-and-send-it-to-a-single-new-hire"></a>Crear una guía de incorporación a partir una plantilla y enviarla a un único empleado recién contratado

1. En el menú izquierdo, seleccione **Plantillas**.
2. En **Mis plantillas**, seleccione la plantilla que desee configurar como guía de incorporación para el empleado recién contratado.
3. Edite la plantilla como desee. No olvide de guardar el trabajo a medida que avanza.
4. Cuando haya terminado de editar la plantilla, seleccione **Crear guía**.

    [![Creación de una guía de incorporación a partir de una plantilla](./media/onboard-create-guide.png)](./media/onboard-create-guide.png)

5. En la ventana **Crear guía**, en **A quién va a incorporar**, especifique el nombre o la dirección de correo electrónico del nuevo empleado. Si el nuevo empleado no está en el sistema aún, seleccione **Agregar ahora**, y especifique información de empleado.

    ![[Introducción de información para la guía de incorporación](./media/onboard-create-a-guide-window.png)](./media/onboard-create-a-guide-window.png)

6. En **¿Cuándo empieza**, seleccione una fecha inicial.
7. Si la guía de incorporación debe enviarse automáticamente al nuevo empleado en una fecha concreta, asegúrese de que la opción **Programar una fecha de envío automático** se haya activado, y seleccione la fecha de envío automática. Para enviar inmediatamente la guía, apague la opción **Programar una fecha de envío automático**.
8. Seleccione **Listo**.
9. Cuando haya terminado de editar la guía de incorporación, seleccione **Enviar** en la esquina superior derecha. Luego siga uno de estos pasos:

    - Para enviar al nuevo empleado un vínculo a la guía de incorporación, seleccione **copiar un vínculo**, y después seleccione **Copiar**.
    - Para personalizar el correo electrónico para la guía de incorporación antes de enviarlo, seleccione **Personalizar el mensaje de correo electrónico antes de enviarlo**, seleccione **Siguiente**, personalice el correo electrónico como desee y, a continuación seleccione **Enviar**.
    - Para enviar el mensaje de correo electrónico sin personalizarlo, seleccione **Siguiente**, y después seleccione **Enviar**.

## <a name="create-an-onboarding-guide-from-a-template-and-send-it-to-multiple-new-hires"></a>Crear una guía de incorporación a partir una plantilla y enviarla a varios empleados recién contratados

Onboard le permite enviar una guía de incorporación a varios empleados nuevos al mismo tiempo.

1. En el menú izquierdo, seleccione **Plantillas**.
2. En **Mis plantillas**, seleccione la plantilla que desee configurar como guía de incorporación para empleados recién contratados.
3. Edite la plantilla como desee. No olvide de guardar el trabajo a medida que avanza.
4. Cuando haya terminado de editar la plantilla, seleccione **Crear guía**.
5. En la ventana **Crear una guía**, seleccione **Necesidad incorporar a varias personas a la vez**.

    [![Crear una guía de incorporación para varios empleados nuevos](./media/onboard-send-guide-multiple-people.png)](./media/onboard-send-guide-multiple-people.png)

6. Seleccione **plantilla de empleado nuevo**.
7. Después de que se descargue el archivo.xlsx, seleccione **Abrir**, especifique la información de los empleados en el libro de Excel, y guárdelo.

    [![Descargar la plantilla de Excel para enviar la guía de incorporación a varios empleados recién contratados](./media/onboard-send-guide-download-spreadsheet.png)](./media/onboard-send-guide-download-spreadsheet.png)

    > [!NOTE]
    > Para poder editar el libro, debe seleccionar **Habilitar edición** en Excel.
    > 
    > [![Habilitar edición](./media/onboard-send-guide-enable-editing.png)](./media/onboard-send-guide-enable-editing.png)

8. Arrastre el libro de Excel al área designada en la ventana **Crear múltiples guías**, o haga clic en cualquier lugar de dicha área para examinar y buscar el archivo en su equipo.

    [![Arrastrar el libro editado](./media/onboard-send-guide-drag-spreadsheet.png)](./media/onboard-send-guide-drag-spreadsheet.png)

9. Cuando haya terminado de editar la guía de incorporación, seleccione **Enviar** en la esquina superior derecha. Luego siga uno de estos pasos:

    - Para enviar a los nuevos empleados un vínculo a la guía de incorporación, seleccione **copiar un vínculo**, y después seleccione **Copiar**.
    - Para personalizar el correo electrónico para la guía de incorporación antes de enviarlo, seleccione **Personalizar el mensaje de correo electrónico antes de enviarlo**, seleccione **Siguiente**, personalice el correo electrónico como desee y, a continuación seleccione **Enviar**.
    - Para enviar el mensaje de correo electrónico sin personalizarlo, seleccione **Siguiente**, y después seleccione **Enviar**.

## <a name="create-a-guide-without-using-a-template"></a>Crear una guía sin usar una plantilla

No tiene que siempre crear una guía a partir de una plantilla. Si prefiere, puede crear una guía a partir de cero en su lugar.

1. En el menú izquierdo, seleccione **Guías**, y seleccione el botón **Agregar** (el signo más \[**+**\]).
2. En la ventana **Crear guía**, en **A quién va a incorporar**, especifique el nombre o la dirección de correo electrónico del nuevo empleado. Si el nuevo empleado no está en el sistema aún, seleccione **Agregar ahora**, y especifique información de empleado.

    ![[Introducción de información para la guía de incorporación](./media/onboard-create-a-guide-window.png)](./media/onboard-create-a-guide-window.png)

3. En **¿Cuándo empieza**, seleccione una fecha inicial.
4. Si la guía de incorporación debe enviarse automáticamente al nuevo empleado en una fecha concreta, asegúrese de que la opción **Programar una fecha de envío automático** se haya activado, y seleccione la fecha de envío automática. Para enviar inmediatamente la guía, apague la opción **Programar una fecha de envío automático**.
5. Seleccione **Listo**.

## <a name="save-a-guide-as-a-template"></a>Guardar una guía como plantilla

Puede guardar una guía de incorporación como plantilla. De esta manera, puede ahorrar tiempo cuando deba crear más guías de incorporación posteriormente.

1. En el menú izquierdo, seleccione **Guías**.
2. Seleccione el botón **Más** (el punto suspensivo \[**...**\]) para la guía que desea utilizar para crear una plantilla y, a continuación seleccione **Guardar como plantilla**.

    ![[Guardar una guía de incorporación como plantilla](./media/onboard-save-guide-as-template.png)](./media/onboard-save-guide-as-template.png)

3. En la ventana **Guardar como nueva plantilla**, especifique un nombre para la nueva plantilla y, a continuación, seleccione **Guardar**.

## <a name="next-steps"></a>Pasos siguientes

- [Editar guías y plantillas de incorporación](./onboard-edit-guides-templates.md)
- [Compartir contenido con otros trabajadores](./onboard-share-template.md)
- [Ver el estado de las tareas y los empleados que se incorporan](./onboard-view-status.md)
- [Crear equipos de contratación en Onboard](./onboard-create-team.md)

### <a name="see-also"></a>Consulte también

- [Probar o comprar la aplicación Onboard](https://dynamics.microsoft.com/talent/onboard/)
- [Novedades](./whats-new.md)
- [Notas de la versión](https://docs.microsoft.com/business-applications-release-notes/index)
- [Obtener soporte](./talent-support.md)
