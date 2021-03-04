---
title: Preguntas frecuentes sobre la integración con LinkedIn
description: Este tema responde a las preguntas que puede que tenga acerca de la integración entre LinkedIn y Microsoft Dynamics 365 Talent - Attract.
author: hasrivas
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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: hasrivas
ms.search.validFrom: 2019-07-08
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 35428da709f480e1d3842b7e92deacba200326ee
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462440"
---
# <a name="linkedin-integration-faq"></a>Preguntas frecuentes sobre la integración con LinkedIn

[!include [banner](includes/banner.md)]

LinkedIn es la red profesional conectada mayor el mundo. Microsoft Dynamics Talent: Attract se integra con LinkedIn para darle el acceso al talento superior del mundo. Attract le permite registrar trabajos directamente a LinkedIn, y también permite llevar información del candidato de LinkedIn a Attract.

## <a name="for-recruiters-and-hiring-managers"></a>Para técnicos de selección de personal y responsables de contratación

Aquí hay las respuestas a las preguntas más frecuentes acerca de cómo utilizar Attract y LinkedIn juntos.

### <a name="what-linkedin-features-do-i-get-with-attract"></a>¿Qué características de LinkedIn obtengo con Attract?

La integración de Attract con LinkedIn le permite realizar las siguientes tareas:

- [Registrar trabajos a LinkedIn](./attract-post-jobs-to-linkedin.md) (como listas limitadas gratis).
- [Conseguir candidatos con LinkedIn Recruiter en Microsoft Dynamics 365 Talent - Attract](./attract-linkedin-recruiter.md#export-linkedin-candidates-to-attract-with-one-click).
- [Configurar la integración con LinkedIn para Microsoft Dynamics 365 Talent - Attract](./attract-admin-linkedin.md#set-up-apply-with-linkedin-in-attract).

### <a name="what-do-i-need-before-i-can-post-jobs-to-linkedin"></a>¿Qué necesito antes de que pueda registrar trabajos a LinkedIn?

Su administración debe [configurar la integración de LinkedIn en Attract](./attract-admin-linkedin.md#configure-job-posting-to-linkedin). Después, ya estará listo para comenzar.

### <a name="how-do-i-post-jobs-to-linkedin-from-attract"></a>¿Cómo publico trabajos en LinkedIn desde Attract?

Después de crear un trabajo en Attract, sólo se tiene que seleccionar el botón **Registrar ahora** que corresponde a LinkedIn. Para obtener más información, consulte [Publicar trabajos en LinkedIn desde Microsoft Dynamics 365 Talent - Attract](./attract-post-jobs-to-linkedin.md#post-jobs-to-linkedin).

### <a name="can-i-get-candidate-information-from-linkedin-into-attract"></a>¿Puedo llevar información del candidato de LinkedIn a Attract?

Sí. Si ve un buen candidato en LinkedIn, puede fácilmente exportar la información de dicho candidato en Attract. Para obtener más información, consulte [Conseguir candidatos con LinkedIn Recruiter en Microsoft Dynamics 365 Talent - Attract](attract-linkedin-recruiter.md).

### <a name="how-can-i-get-help-accessing-linkedin-from-attract"></a>¿Cómo puedo obtener ayuda para acceder a LinkedIn desde Attract?

Si está teniendo problemas para iniciar sesión o enviar trabajos a LinkedIn desde Attract, consulte [Solución de problemas de la integración con LinkedIn y Microsoft Dynamics 365 Talent - Attract](./attract-troubleshoot-linkedin.md).

Para otros problemas con Attract, consulte [Obtener soporte para Microsoft Dynamics 365 Talent](./talent-support.md). Para obtener ayuda con LinkedIn, consulte [Página de soporte de LinkedIn](https://www.linkedin.com/help).

## <a name="for-admins-and-developers"></a>Para administradores y desarrolladores

Aquí hay las respuestas a las preguntas más frecuentes acerca de cómo configurar la integración entre Attract y LinkedIn.

### <a name="how-do-i-configure-attract-so-that-recruiters-and-hiring-managers-can-post-jobs-to-linkedin"></a>¿Cómo configuro Attract de modo que los reclutadores y los administradores de contratación puedan registrar trabajos a LinkedIn?

Puede configurar las opciones disponibles en la pestaña **Integración de LinkedIn** en el centro de administración. Para obtener más información, consulte [Configurar la integración con LinkedIn para Microsoft Dynamics 365 Talent - Attract](./attract-admin-linkedin.md).

### <a name="can-i-export-candidate-information-from-linkedin"></a>¿Puedo exportar información del candidato desde LinkedIn?

Sí, pero primero debe configurar la integración con LinkedIn Recruiter. Para obtener más información, consulte [Configurar la integración con LinkedIn para Microsoft Dynamics 365 Talent - Attract](./attract-admin-linkedin.md).

### <a name="how-can-i-post-jobs-to-premium-job-slots-on-linkedin"></a>¿Cómo puedo enviar trabajos a registros de trabajo premium en LinkedIn?

Aunque Attract proporcione una solución completa para registrar trabajos a LinkedIn, puede encontrar que necesita flexibilidad adicional. Por ejemplo, puede que desee poder registrar registros de trabajo premium además de listas limitadas gratis, o puede que desee que LinkedIn procese sus registros de trabajo por lotes más de una vez al día.

#### <a name="types-of-linkedin-job-posts"></a>Tipos de registros de trabajo de LinkedIn

LinkedIn proporciona los siguientes tipos de registros de empleo:

- **Lista limitada** Propuestas de empleo gratis que aparecen en los resultados de búsqueda cuando los candidatos buscan trabajos en LinkedIn y en la página de LinkedIn de una empresa. Las listas limitadas están destinadas a buscadores de trabajo activos. Este tipo de lista es el tipo que Attract proporciona a LinkedIn. No puede promocionar trabajos de listas limitadas en LinkedIn. Si desea promocionar listas limitadas, deberá trabajar con LinkedIn para habilitar el ajuste de trabajo. Para obtener más información acerca del ajuste de trabajo, consulte [Listas limitadas y registros de trabajos premium para el ajuste de trabajo](https://www.linkedin.com/help/recruiter/answer/79049/limited-listings-vs-premium-job-slots-for-job-wrapping) y [Ajuste de trabajo adicional - preguntas más frecuentes](https://www.linkedin.com/help/recruiter/answer/79050/job-wrapping-frequently-asked-questions).
- **Registro de trabajo premium** Registros comprados que aparecen en distintas ubicaciones de LinkedIn, como la fuente de LinkedIn, correos electrónicos, y la área **Puede que te interesen estos trabajos**. Los registros de trabajo premium están destinados a candidatos pasivos, pero también aparecen en las búsquedas de trabajo.

Attract registra trabajos a LinkedIn como listas limitadas. Si desea usar registros de trabajo premium, debe usar el ajuste del trabajo con LinkedIn Recruiter. El ajuste de trabajo requiere un contrato de ajuste de trabajo con LinkedIn. Para obtener más información, consulte [Ajuste de trabajo con LinkedIn Recruiter - Información general](https://www.linkedin.com/help/recruiter/answer/79037).

#### <a name="frequency-of-batch-processing-on-linkedin"></a>Frecuencia de procesamiento por lotes en LinkedIn

LinkedIn procesa los registros de trabajo en un lote mediante Attract una vez al día. Por lo tanto, puede tardar hasta 48 horas para que los trabajos aparezcan en LinkedIn tras registrarlos a través de Attract. Si necesita que los trabajos aparezcan en LinkedIn, o si necesita flexibilidad adicional, puede usar la interfaz de programación de aplicaciones (API) de Recruiter System Connect de LinkedIn. Para obtener más información, consulte [Recruiter System Connect](https://docs.microsoft.com/linkedin/talent/recruiter-system-connect)

#### <a name="table-of-options-for-job-posting-to-linkedin"></a>Tabla de opciones para registrar trabajos en LinkedIn

La tabla siguiente describe las diferentes opciones para registrar trabajos a LinkedIn. Incluye las ventajas de cada opción y información adicional.

|  | Atraer | Ajuste del trabajo con LinkedIn Recruiter | API de Recruiter System Connect |
|---|---|---|---|
| **Descripción** | Attract registra trabajos a LinkedIn como fuente XML. | La empresa establece un contrato con LinkedIn y proporciona una fuente XML para enviar trabajos. | El cliente usa la API para sincronizar información entre Attract y LinkedIn Recruiter. |
| **¿Qué tipo de trabajo puedo enviar?** | Lista limitada | Registro de trabajo premium o lista limitada | Lista limitada |
| **¿Puedo promocionar el trabajo en LinkedIn?** | No | Registros de trabajo premium: Sí<br>Listas limitadas: No | No |
| **¿Cuántas veces LinkedIn envía trabajos?** | Una vez al día | Una vez al día | Varias veces por día, según defina la API |
| **¿Recomendado por LinkedIn?** | No | Sí | No |
| **¿Qué necesito?** | Comprar Attract | Un contrato de ajuste de trabajo con LinkedIn y la compra de registros de trabajo premium | Un contrato de API con LinkedIn | 
| **¿Dónde se puede encontrar más información?** | [Configurar la integración con LinkedIn para Microsoft Dynamics 365 Talent - Attract](./attract-admin-linkedin.md) | [Ajuste del trabajo con LinkedIn Recruiter - Información general](https://www.linkedin.com/help/recruiter/answer/79037) | [Recruiter System Connect](https://docs.microsoft.com/linkedin/talent/recruiter-system-connect) |

> [!NOTE]
> No es necesario una licencia de LinkedIn Recruiter System Connect para enviar trabajos a LinkedIn con Attract.

## <a name="see-also"></a>Consulte también

[Configurar la integración con LinkedIn para Microsoft Dynamics 365 Talent - Attract](./attract-admin-linkedin.md)

[Publicar trabajos en LinkedIn desde Microsoft Dynamics 365 Talent - Attract](./attract-post-jobs-to-linkedin.md)

[Conseguir candidatos con LinkedIn Recruiter en Microsoft Dynamics 365 Talent - Attract](./attract-linkedin-recruiter.md)

[Solución de problemas de la integración con LinkedIn y Microsoft Dynamics 365 Talent - Attract](./attract-troubleshoot-linkedin.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]