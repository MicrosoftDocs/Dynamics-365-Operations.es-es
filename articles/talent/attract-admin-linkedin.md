---
title: Configurar la integración de LinkedIn con Attract
description: Este tema explica cómo configurar la integración de LinkedIn para Microsoft Dynamics 365 Talent - Attract para poder fácilmente enviar trabajos a LinkedIn desde Attract y, de modo que puedan los reclutadores sincronizar su información de contratación con el perfil de LinkedIn de un candidato.
author: andreabichsel
manager: AnnBe
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-07-08
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 4c518fb7036d44aa52c8db859ee3616fc4e58a06
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2019
ms.locfileid: "2833193"
---
# <a name="set-up-linkedin-integration-with-attract"></a>Configurar la integración de LinkedIn con Attract

[!include [banner](includes/banner.md)]

Ayude sus reclutadores y directores de contratación a atraer el talento superior configurando la integración de LinkedIn con Microsoft Dynamics 365 Talent: Attract. Attract le permite registrar trabajos directamente a LinkedIn, la mayor red conectada profesional.

Los trabajos que envía a LinkedIn a través de Attract son listas limitadas y se proporcionan sin coste extra para su empresa. Estas listas solo están disponibles a través de socios de software de LinkedIn como Attract. No aparecen en el panel **Carreras** en la página de LinkedIn de la empresa, ya que ahí sólo aparecen listas pagadas. Sin embargo, se muestran donde los candidatos potenciales pueden ver todos los trabajos disponibles. Las listas limitadas también se muestran en búsquedas de trabajo de LinkedIn.

Attract proporciona dos formas de integrarse con LinkedIn para ayudarle a conseguir candidatos de este sitio popular de proyectos profesionales:

- Publicar trabajos de Attract en LinkedIn.
- Pasar candidatos de LinkedIn a Attract.

Puede configurar ambas opciones en la pestaña **Integración de LinkedIn** en el centro de administración. Para abrir el centro de administración, vaya a <https://attract.talent.dynamics.com/adminsettings>.

> [!NOTE]
> Paara usar la integración de LinkedIn Recruiter con Attract, necesita el [Complemento de contratación completa](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring) y [Licencias de LinkedIn Recruiter](https://business.linkedin.com/talent-solutions/cx/17/08/recruiter-demo-fs2-k18). Para obtener más información, consulte [Qué versión de Microsoft Dynamics 365 Talent - Attract](./attract-comprehensive-hiring.md).

Si está teniendo problemas para registrar trabajos en LinkedIn consulte [Solución de problemas de la integración con LinkedIn y Microsoft Dynamics 365 Talent - Attract](./attract-troubleshoot-linkedin.md).

Para obtener información sobre otras formas de enviar trabajos a LinkedIn, consulte [Preguntas frecuentes de integración de Attract con LinkedIn](./attract-linkedin-faq.md).

## <a name="configure-job-posting-to-linkedin"></a>Configurar el registro de trabajos en LinkedIn

Antes de poder enviar trabajos de Attract a LinkedIn, necesita un [Identificador de empresa de LinkedIn](https://aka.ms/findID) Su identificador de empresa de LinkedIn es una cadena de números que identifica de forma exclusiva su empresa dentro de LinkedIn. Para obtener más información, consulte [Asociar su identificador de empresa de LinkedIn al panel de trabajos de LinkedIn - preguntas más frecuentes](https://aka.ms/findID).

Attract registra una fuente de sus registros de empleo en LinkedIn, y LinkedIn busca la fuente aproximadamente una vez al día. Sus trabajos pueden tardar hasta 48 horas en ser registrados en el sitio.

Los trabajos que se registran en LinkedIn aparecen en el sitio de LinkedIn activo. LinkedIn no tiene un entorno de prueba para registrar trabajos. Por lo tanto, asegúrese de que no registra accidentalmente trabajos de prueba. 

1. En el menú **Configuración** (el símbolo de engranaje) en la esquina superior derecha, seleccione **Centro de administración**. Como alternativa, vaya a <https://attract.talent.dynamics.com/adminsettings>.
2. Seleccione la ficha **integración de LinkedIn**.
3. En **Nombre de la empresa**, especifique el nombre de la empresa, y en **Identificador de empresa**, especifique el identificador de empresa en LinkedIn. Asegúrese de que coincida el nombre de la empresa con el nombre que aparece en la página de LinkedIn de la empresa. Para obtener más información acerca de los identificadores de empresa de LinkedIn, consulte [Asociar su identificador de empresa de LinkedIn al panel de trabajos de LinkedIn - preguntas más frecuentes](https://www.linkedin.com/help/linkedin/answer/98972).

    Si necesita cambiar información de su organización, consulte [Cambiar la dirección, el contacto técnico, y más de su organización](https://docs.microsoft.com/office365/admin/manage/change-address-contact-and-more). Si todavía tiene problemas, póngase en contacto con [Compatibilidad de LinkedIn](https://www.linkedin.com/help/linkedin).

4. Seleccione **Guardar**.

## <a name="set-up-linkedin-recruiter-with-attract"></a>Configurar LinkedIn Recruiter con Attract 

Para permitir a reclutadores buscar trabajos con LinkedIn Recruiter, debe configurar la integración con LinkedIn Recruiter en Attract. Para completar el proceso de configuración, debe trabajar con el usuario que es un administrador en el contrato de LinkedIn Recruiter de su organización.

1. En el menú **Configuración** (el símbolo de engranaje) en la esquina superior derecha, seleccione **Centro de administración**. Como alternativa, vaya a <https://attract.talent.dynamics.com/adminsettings>.
2. Seleccione la ficha **integración de LinkedIn**.

    [![Vista de administrador de Attract para iniciar la integración de LinkedIn Recruiter](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)

3. Seleccione **Conectar** para iniciar la configuración. Se le guiará a través del proceso de inicio de sesión en LinkedIn.
4. Si tiene usuarios en varios contratos de LinkedIn, seleccione el contrato que desea conectar al sistema de Attract. Si tiene un usuario solo en un contrato de LinkedIn, puede omitir este paso.
5. En **Recruiter System Connect (RSC)**, seleccione **Solicitar**.

    [![Vista de administrador de Attract para solicitar la integración de LinkedIn Recruiter](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)

6. La configuración **Recruiter System Connect (RSC)** ahora debe aparecer como **listo para socios**. Si ve **Notificar al socio** en esta página, espere unos segundos, haga clic en **Notificar al socio**, y actualice la página. El valor debe ahora aparecer como **listo para socio**.

    [![Vista de gestión de Attract para indicar que el lado de Attract de las solicitudes se ha realizado](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)

7. Para completar los pasos siguientes, debe tener privilegios de administración en su contrato de LinkedIn Recruiter.

    1. Inicie sesión en LinkedIn mediante su cuenta de administrador y después seleccione **LinkedIn Recruiter** en la parte superior derecha. 
    2. En el menú **Más** en la parte superior de la página, haga clic en **Valores de administración**, y haga clic en la pestaña **ATS**.
    3. Para habilitar la exportación en un clic para solo un contrato, active **Acceso de nivel de contrato (para cada usuario de este contrato**. Para habilitarlo para toda la empresa, active **Acceso de nivel de empresa (para cada contrato de la empresa)**.

    [![Activar la integración de Attract desde la vista de administración de LinkedIn Recruiter](./media/EnableRSC.png)](./media/EnableRSC.png)

8. En el centro de administración de Attract, seleccione la pestaña **Integración de LinkedIn**. La configuración **Recruiter System Connect (RSC)** ahora debe aparecer como **Habilitado**.

    [![Integración de LinkedIn Recruiter completa](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)

## <a name="set-up-apply-with-linkedin-in-attract"></a>Configuración de Solicitar con LinkedIn en Attract

Puede permitir que los candidatos soliciten sus trabajos con sus perfiles de LinkedIn. Para obtener más información sobre Solicitar con LinkedIn, consulte [el poden de LinkedIn Everywhere: candidaturas con LinkedIn](https://blog.linkedin.com/2011/07/24/apply-with-linkedin).

Esta característica está actualmente en vista previa. Antes de seguir estos pasos, asegúrese de que Solicitar con LinkedIn esté habilitado. Para obtener más información sobre cómo habilitar características de vista previa, consulte [Acceso a funciones de vista preliminar en Microsoft Dynamics 365 Talent](./access-preview-feature.md).

1. En el menú **Configuración** (el símbolo de engranaje) en la esquina superior derecha, seleccione **Centro de administración**. Como alternativa, vaya a <https://attract.talent.dynamics.com/adminsettings>.
2. Seleccione la ficha **integración de LinkedIn**.

    [![Vista de administrador de Attract para iniciar la integración de LinkedIn Recruiter](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)

3. Al lado **Solicitar con LinkedIn**, seleccione **Conectar** para iniciar la configuración. Se le guiará a través del resto del proceso con LinkedIn.

## <a name="see-also"></a>Consulte también

[Integración de Attract con preguntas frecuentes de LinkedIn](./attract-linkedin-faq.md)

[Registrar trabajos en sitios externos profesionales desde Attract](./posting-jobs-external.md)

[Conseguir candidatos con LinkedIn Recruiter en Microsoft Dynamics 365 Talent - Attract](./attract-linkedin-recruiter.md)

[Crear, aprobar y registrar trabajos en Attract](./creating-jobs-attract.md)

[Solución de problemas de la integración con LinkedIn y Microsoft Dynamics 365 Talent - Attract](./attract-troubleshoot-linkedin.md)
