---
title: Seguir fuentes para los perfiles y las solicitudes del candidato
description: Este tema proporciona información acerca realizar el seguimiento del origen de los perfiles y las solicitudes del candidato.
author: hachandr
manager: AnnBe
ms.date: 03/18/2019
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
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: ebc82ada31d2803800358cd9aecfe389ada8f0dc
ms.sourcegitcommit: dd1e1636d351a15f9c1b6808bea359417a9bd690
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2019
ms.locfileid: "897482"
---
# <a name="track-sources-for-candidate-profiles-and-applications"></a>Seguir fuentes para los perfiles y las solicitudes del candidato 

[!include[banner](../includes/banner.md)]

> [!NOTE] 
> La funcionalidad de la que se habla en este tema esta disponible como parte de una versión preliminar. El contenido y la funcionalidad están sujetos a cambios. Para utilizar esta función, pida que un administrador la active usando la **Configuración de administración** en Attract. Una versión futura proporcionará informes de seguimiento del origen. Para obtener más información, consulte [Acceder a las características de vista previa en Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/access-preview-feature).

Cuando los candidatos solicitan un trabajo, Attract automáticamente sigue el origen de sus solicitudes, proveyéndole de información valiosa para ayudarle a dirigir sus esfuerzos de contratación. Los reclutadores y los administradores de contratación pueden seleccionar también un origen de la aplicación mientras agregan manualmente un candidato a un trabajo o la reserva de talentos.

Puede ver el origen de la solicitud en los detalles de actividad de solicitud en la pestaña **Actividad** , así como en el historial de la solicitud disponible en **Perfil** en las reservas de talentos. Puede encontrar el origen del perfil de un candidato en los detalles del candidato, en la pestaña **Perfil** en solicitudes y reservas de talentos.

> [!NOTE] 
> Puede encontrar plantillas de proceso en el [Complemento de contratación completa](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/attract-comprehensive-hiring)

## <a name="pre-configured-sources"></a>Fuentes preconfiguradas

La lista de origen predeterminada contiene orígenes comunes de solicitud. Algunos tipos de origen, como **Oportunidades de trabajo** y **Red social**, tienen detalles adicionales de origen. Por ejemplo, **Red social** incluye Facebook y Twitter. El tipo de origen **Referencia** permite especificar un empleado interno como el origen de la referencia. La lista de origen predeterminada incluye los siguientes orígenes preconfigurados:

-   Sitio de desarrollo profesional de Attract

-   Agencia

-   Feria de empleo

-   Marketing de la empresa

-   Conferencias y ferias comerciales

-   Asociación profesional

-   Página de oportunidades de trabajo

    -   Indeed

    -   Seek

    -   CareerBuilder

    -   Google Jobs

    -   Xing

    -   Glassdoor

    -   Monster Jobs

-   Revistas y publicaciones

-   Red social

    -   Facebook

    -   Twitter

-   Contratación en la Universidad

-   LinkedIn

-   Clasificados

-   Referencia

-   Agregado por el reclutador

-   Otras

## <a name="customize-the-source-list"></a>Personalizar la lista de origen 

Puede ampliar la lista de origen para incluir orígenes adicionales de la solicitud. Para personalizar esta lista, siga las instrucciones en [Extender los conjuntos de opciones en Attract](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/extensibility-attract#extending-option-sets-in-attract). Edite la entidad **TalentSource** para incluir orígenes adicionales. 

Para evitar afectar negativamente a la interfaz de usuario (UI), no edite ni elimine los valores (no nombres) de la enumeración **TalentCategory** para:

- **Referencia**
- **LinkedIn**
- **Otras**

En su lugar, puede ampliar la enumeración **TalentSource** para agregar otros tipos de orígenes.
