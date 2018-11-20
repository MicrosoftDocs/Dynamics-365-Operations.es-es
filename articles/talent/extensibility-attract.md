---
title: La extensibilidad en Attract
description: "Este tema describe cómo puede ampliar la aplicación Microsoft Dynamics 365 for Talent - Attract con Microsoft Power Platform."
author: josaw
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
ms.openlocfilehash: 0af60a0aea0f7a5de793631445aaebb37dbb0d74
ms.contentlocale: es-es
ms.lasthandoff: 10/22/2018

---

# <a name="extensibility-in-attract"></a>La extensibilidad en Attract

[!include[banner](../includes/banner.md)]

Microsoft Dynamics 365 for Talent se crea encima de la plataforma Common Data Service (CDS) for Apps y se puede ampliar de distintas formas con Microsoft Power Platform y las capacidades que Common Data Service for Apps ofrece. Por lo tanto, puede configurar y personalizar el sistema mediante Microsoft PowerApps y Microsoft Flow. También puede obtener un análisis adicional sobre personas usando Microsoft Power BI. Además, las nuevas actividades personalizadas, como las actividades de PowerApps y contenido Web (iframe), crean un proceso de contratación más personalizable que nunca. Con estas actividades, puede ajustar el proceso de contratación a sus necesidades y procesos de negocio, y puede asegurarse de que tanto el equipo de contratación como los candidatos tienen una experiencia perfecta y personalizada.

## <a name="take-advantage-of-the-microsoft-power-platform"></a>Aproveche Microsoft Power Platform 

Dado que todos los datos de Attract residen en Common Data Service for Apps, puede usar herramientas de Microsoft Power Platform para especificar sus necesidades empresariales únicas en Attract.

### <a name="powerapps"></a>PowerApps

Puede usar PowerApps para compilar fácilmente aplicaciones que se conecten a sus datos de Attract y que usen expresiones como las de Microsoft Excel para agregar lógica. Las aplicaciones que cree mediante PowerApps se pueden ejecutar en la web y, en dispositivos Apple IOS y Google Android.

Por ejemplo, puede facilitar la asistencia a ferias de carreras universitarias para reclutadores creando una aplicación ligera que les permita digitalizar curriculums vitae e insertar candidatos en un puesto en Attract. Como alternativa, puede crear una aplicación que ayude a atender las necesidades de cumplimiento de su organización. Para obtener más información acerca de PowerApps y cómo utilizarlo para compilar aplicaciones, consulte [Integrar datos en Common Data Service for Apps](https://docs.microsoft.com/en-us/powerapps).

### <a name="microsoft-flow"></a>Microsoft Flow 

Puede usar Microsoft Flow para crear flujos de trabajo automatizados que se ejecutan encima de datos de Attract. Es fácil conectarse a cientos de aplicaciones y servicios populares sin tener que escribir código. Construyendo flujos que interactúan con las entidades de trabajo, candidato, y aplicación en Common Data Service for Apps, puede automatizar distintas acciones. Por ejemplo, cuando un candidato acepta una propuesta, una notificación se puede enviar a un equipo de incorporación, o la noticia se puede anunciar en Twitter. Para obtener más información acerca de flujos, consulte la [documentación de Microsoft Flow](https://docs.microsoft.com/en-us/flow/)

### <a name="power-bi"></a>Power BI

Power BI le permite crear y ver informes personalizados y paneles que le proporcionan una penetración más detallada de los datos de Attract. Para obtener más información sobre Power BI y cómo crear informes interactivos y los paneles, consulte [Documentación de Power BI](https://docs.microsoft.com/en-us/power-bi/).

### <a name="custom-activities"></a>Actividades personalizadas 

Puede agregar actividades personalizadas, como las aplicaciones de PowerApps y de contenido Web (iframe), en el nivel de la plantilla del proceso del trabajo o durante la creación de un nuevo trabajo. Estas actividades le permiten personalizar el proceso de contratación y aportar lógica de negocios exclusiva de su organización a Attract.

#### <a name="powerapps-activity"></a>Actividad de PowerApps 

La actividad de PowerApps permite al creador de un trabajo o proceso de trabajo incorporar una aplicación de PowerApps en el flujo de contratación. Tras crear y publica la aplicación, puede especificar su identificador de la aplicación en la configuración de la actividad. Mediante una aplicación de PowerApps, puede leer y escribir datos en Common Data Service for Apps. Incluso puede vincular la aplicación a un flujo. Por ejemplo, tiene una aplicación que los reclutadores usan para rellenar un formulario mientras realizan entrevistas de teléfono. En este caso, puede vincular la aplicación a un flujo que evalúa si un candidato puede ser avanzado más en el proceso de solicitud de trabajo. Este tipo de actividad se puede visualizar únicamente por los miembros del equipo de contratación. Para obtener más información sobre cómo configurar la actividad de PowerApps, consulte [Las actividades en Attract](./activities-attract.md).

> [!NOTE]
> La actividad de PowerApps está disponible únicamente con el complemento de contratación completo.

#### <a name="web-content-iframe-activity"></a>Actividad de contenido web (iframe)

La actividad de contenido Web (iframe) le permite insertar una solución web personalizada que ha creado en el proceso de contratación o el portal del candidato. Puede leer y escribir datos directamente del Common Data Service for Apps. También puede personalizar la solución de modo que desencadene flujos o aproveche funciones de Microsoft Azure. Para obtener más información sobre cómo configurar la actividad de contenido web, consulte [Actividades en Attract](./activities-attract.md).

> [!NOTE]
> La actividad de contenido web está disponible únicamente con el complemento de contratación completo.

