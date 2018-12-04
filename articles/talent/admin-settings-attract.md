---
title: "Configuración de administrador en Attract"
description: "Este tema explica cómo habilitar la funcionalidad de la función para las organizaciones y los usuarios de Attract."
author: 
manager: AnnBe
ms.date: 10/15/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: e890e32049e930b70c2d0aac8aa8206ab999418a
ms.openlocfilehash: 52b48d5daab985c43d59f29ad7b80dda99a7fcef
ms.contentlocale: es-es
ms.lasthandoff: 10/22/2018

---

# <a name="admin-settings-in-attract"></a>Configuración de administrador en Attract
[!include[banner](../includes/banner.md)]

El centro de administración de Microsoft Dynamics 365 for Talent: Attract contiene opciones de configuración, opciones de integración, y las opciones de configuración para la aplicación de Attract.

## <a name="company-information"></a>Información de la compañía

Especifique un nombre para mostrar para la empresa, y agregue un logotipo de la empresa. El nombre para mostrar y el logotipo se podrán entonces utilizar en las publicaciones de trabajo y durante la experiencia de incorporación.

## <a name="linkedin-integration"></a>Integración de LinkedIn

Configurar la integración con con LinkedIn Recruiter System Connect (RSC). Tras conectarse a LinkedIn mediante sus credenciales de LinkedIn, puede sincronizar el perfil de LinkedIn, las solicitudes, las valoraciones de entrevista y las notas de equipo para un candidato. Se requiere una licencia completa de reclutador de LinkedIn. Para obtener más información sobre RSC, consulte [Recruiter System Connect (RSC) – Preguntas más frecuentes](https://www.linkedin.com/help/recruiter/answer/90483).

## <a name="user-permissions"></a>Permisos de usuario

Asigne funciones a usuarios de su organización Las siguientes funciones están disponibles: **Administración**, **Reclutador**, **Administrador de contratación**, y **Solo lectura**. Para obtener más información sobre permisos, consulte [La seguridad y la gestión de roles en Attract](./security-attract.md).

## <a name="feature-management"></a>Administración de características

A medida que se agregan nuevas características, es posible que se lancen en una vista previa pública. Las características de vista preliminar pública no cumplen todos los requisitos de servicio. Recibiéndolas, acepta compartir los datos con sistemas externos. Puede detectar que su organización no requiere todas las nuevas características que se liberan. Puede activar y desactivar características de vista preliminar públicas, en función de las necesidades de su organización.

## <a name="template-management"></a>Administración de plantillas

Una plantilla de proceso de contratación contiene todas las actividades que deben incluirse como parte del proceso de contratación para un trabajo. La organización puede permitir a todos los miembros del equipo o solo a las administraciones que creen plantillas de proceso de contratación. Para permitir que los miembros del equipo creen sus propias plantillas de proceso de contratación, active la funcionalidad de gestión de la plantilla. Para obtener más información acerca de las plantillas de proceso, consulte [Procesar plantillas en Attract](./process-templates-attract.md).

## <a name="email-template-settings"></a>Configuración de plantilla de correo electrónico

Las organizaciones pueden crear plantillas de correo electrónico para distintas situaciones. Puede seleccionar la imagen del encabezado para incluirla en las plantillas de correo electrónico. El encabezado seleccionado aparecerá en todas las plantillas de correo electrónico. En el pie de página de la plantilla, puede agregar un vínculo a la declaración de privacidad y términos de uso de la organización para las comunicaciones. Para obtener más información, vea [Plantillas de correo electrónico en Attract](./email-templates.md).

## <a name="offer-process"></a>Proceso de oferta

Puede configurar el proceso de aprobación para las propuestas de trabajo. Por ejemplo, puede especificar si una oferta debe estar aprobada antes de que se envíe a un candidato. También puede exigir que los aprobadores dejen un comentario con su decisión relativa a la oferta.

Dos flujos de trabajo de aprobación están disponibles: **Paralelo** y **Secuencial**.

- **Paralelo** Las aprobaciones se enviarán a todos los aprobadores al mismo tiempo.
- **Secuencial**: se envían las aprobaciones a los aprobadores en un orden específico.

También puede configurar las opciones relacionadas con la experiencia del candidato. Por ejemplo, una opción permite especificar si los candidatos pueden rechazar una oferta sin discusión adicional. Si establece la opción **Permitir que los candidatos rechacen una oferta sin discusión adicional** en **No**, el botón **Rechazar oferta** estará disponible para los candidatos. Si establece esta opción en **Sí**, candidatos pueden rechazar la propuesta seleccionando un motivo y después seleccionando **Rechazar oferta**.

También puede establecer y aplicar una fecha de vencimiento para las propuestas. Si establece la opción **Requerir una fecha de vencimiento para todas las ofertas** en **Sí**, las propuestas expiran tras el número de horas o de días que especifique.

Para obtener más información acerca de la administración de propuestas, consulte [Configuración de la gestión de ofertas](./offer-setup.md).

