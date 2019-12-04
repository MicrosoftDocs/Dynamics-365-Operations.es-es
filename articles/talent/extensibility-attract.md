---
title: Extensibilidad en Attract
description: Este tema describe cómo puede ampliar la aplicación Microsoft Dynamics 365 Talent - Attract con la Microsoft Power Platform.
author: andreabichsel
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
ms.openlocfilehash: 9d12a4d48aa369884804c2a0bce9834534b1bec6
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2019
ms.locfileid: "2832870"
---
# <a name="extensibility-in-attract"></a>Extensibilidad en Attract

[!include [banner](includes/banner.md)]

Microsoft Dynamics 365 Talent se crea encima de Common Data Service y se puede ampliar de distintas formas con Microsoft Power Platform y las capacidades que ofrece Common Data Service. Por lo tanto, puede configurar y personalizar el sistema mediante Microsoft Power Apps y Microsoft Power Automate. También puede obtener un análisis adicional sobre personas usando Microsoft Power BI. Además, las nuevas actividades personalizadas, como las actividades de Power Apps y contenido Web (iframe), crean un proceso de contratación más personalizable que nunca. Con estas actividades, puede ajustar el proceso de contratación a sus necesidades y procesos de negocio, y puede asegurarse de que tanto el equipo de contratación como los candidatos tienen una experiencia perfecta y personalizada.

## <a name="extending-option-sets-in-attract"></a>Ampliación de conjuntos de opciones en Attract

Un **conjunto de opciones** (Lista de selección) es un tipo de campo que puede incluirse en una entidad. Define un conjunto de opciones. Cuando un conjunto de opciones se muestra en un formulario utiliza un control de la lista desplegable.  En Attract, hay varios campos que son conjuntos de opciones.  Estamos empezando a introducir la capacidad de extender los conjuntos de opciones, comenzando por el campo de motivo Rechazo, el campo Tipo de empleo , y el campo Tipo de la antigüedad.   Además, puede agregar las etiquetas localizadas de visualización para las opciones que desee agregar. Para obtener más información, consulte [Personalice las etiquetas de la opción establecida](https://docs.microsoft.com/powerapps/developer/common-data-service/customize-labels-support-multiple-languages).

> [!NOTE]
> La propuesta de empleo en la funcionalidad de LinkedIn requiere el uso de los campos **Tipo de empleo** y **Tipo de antigüedad** en la página **Detalles del trabajo**. Los valores predeterminados de estos campos son compatibles con LinkedIn y se visualizan cuando se registra el trabajo. Por lo tanto, si va a publicar trabajos en LinkedIn y modifica los valores del conjunto de opciones existente para estos campos, el trabajo seguirá publicado, pero LinkedIn no mostrará los valores de **Tipo de empleo** y **Tipo de la antigüedad** personalizados.  

A continuación, se enumeran los pasos para actualizar el campo **Motivo de rechazo** con los valores específicos de su negocio.  

1. Para ampliar el conjunto de opciones **Motivo de rechazo**, desplácese a la [página web de gestión de Power Apps](https://admin.powerapps.com).
2. Puede que se le solicite iniciar sesión en la cuenta. Proporcione sus credenciales de ID de usuario y la contraseña que usa para iniciar sesión en Dynamics365 y/o Office365 y, a continuación haga clic en **Siguiente**.
3. En la pestaña **Entornos** , seleccione el entorno que desea administrar, y haga doble clic para ir a la ficha **Detalles**.
4. En la pestaña **Detalles** , seleccione **Centro administración de Dynamics 365**.
5. Seleccione la instancia que desea modificar y seleccione **abierto**.
6. Vaya a **Valores**y luego a **Personalizaciones**, y seleccione **Personalizar el sistema**.
7. Busque la entidad cuyo conjunto de opciones desea expandir seleccionando **Entidades** y expandiendo el grupo. En este ejemplo, será la **Entidad de aplicación de trabajo**.
8. Vaya al campo cuyo conjunto de opciones desea ampliar seleccionando la opción **Campos**. En este ejemplo, será **msdyn_rejectionreason**. Haga doble clic en el campo.
9. En el campo **Conjunto de opciones**, seleccione **Editar**.
10. Seleccione el icono **+**.
11. Especifique una **Etiqueta**.  (Debe ser un valor único - sin duplicados).
12. Seleccione **Guardar**.
13. Seleccione **Publicar** en la parte superior de la página.

## <a name="take-advantage-of-the-microsoft-power-platform"></a>Aprovechar Microsoft Power Platform 

Dado que todos los datos de Attract residen en Common Data Service, puede usar herramientas de Microsoft Power Platform para especificar sus necesidades empresariales únicas en Attract.

### <a name="power-apps"></a>Power Apps

Puede usar Power Apps para compilar fácilmente aplicaciones que se conecten a sus datos de Attract y que usen expresiones como las de Microsoft Excel para agregar lógica. Las aplicaciones que cree mediante Power Apps se pueden ejecutar en la web y, en dispositivos Android Apple IOS y Google.

Por ejemplo, puede facilitar la asistencia a ferias de carreras universitarias para reclutadores creando una aplicación ligera que les permita digitalizar curriculums vitae e insertar candidatos en un puesto en Attract. Como alternativa, puede crear una aplicación que ayude a atender las necesidades de cumplimiento de su organización. Para obtener más información acerca de Power Apps y cómo utilizarlo para compilar aplicaciones, consulte [Integrar datos en Common Data Service](https://docs.microsoft.com/powerapps).

### <a name="microsoft-power-automate"></a>Microsoft Power Automate 

Puede usar Microsoft Power Automate para crear flujos de trabajo automatizados que se ejecutan encima de datos de Attract. Es fácil conectarse a cientos de aplicaciones y servicios populares sin tener que escribir código. Construyendo flujos que interactúan con las entidades de trabajo, candidato, y aplicación en Common Data Service, puede automatizar distintas acciones. Por ejemplo, cuando un candidato acepta una propuesta, una notificación se puede enviar a un equipo de incorporación, o la noticia se puede anunciar en Twitter. Para obtener más información acerca del seguimiento, consulte la [documentación de Microsoft Power Automate](https://docs.microsoft.com/flow/).

### <a name="power-bi"></a>Power BI

Power BI le permite crear y ver informes personalizados y paneles que le proporcionan una penetración más detallada de los datos de Attract. Para obtener más información sobre Power BI y cómo crear informes interactivos y los paneles, consulte [la documentación de Power BI](https://docs.microsoft.com/power-bi/).

### <a name="custom-activities"></a>Actividades personalizadas 

Puede agregar actividades personalizadas, como las aplicaciones de Power Apps y de contenido Web (iframe), en el nivel de la plantilla del proceso del trabajo o durante la creación de un nuevo trabajo. Estas actividades le permiten personalizar el proceso de contratación y aportar lógica de negocios exclusiva de su organización a Attract.

#### <a name="power-apps-activity"></a>Actividad de Power Apps 

La actividad de Power Apps permite al creador de un trabajo o proceso de trabajo incorporar una aplicación de Power Apps en el flujo de contratación. Tras crear y publica la aplicación, puede especificar su identificador de la aplicación en la configuración de la actividad. Mediante una aplicación de Power Apps, puede leer y escribir datos en Common Data Service. Incluso puede vincular la aplicación a un flujo. Por ejemplo, tiene una aplicación que los reclutadores usan para rellenar un formulario mientras realizan entrevistas de teléfono. En este caso, puede vincular la aplicación a un flujo que evalúa si un candidato puede ser avanzado más en el proceso de solicitud de trabajo. Este tipo de actividad se puede visualizar únicamente por los miembros del equipo de contratación. Para obtener más información sobre cómo configurar la actividad de Power Apps, consulte [Actividades los procesos de contratación](./activities-attract.md).

> [!NOTE]
> La actividad de Power Apps está disponible únicamente con el complemento de contratación completo.

#### <a name="web-content-iframe-activity"></a>Actividad de contenido web (iframe)

La actividad de contenido Web (iframe) le permite insertar una solución web personalizada que ha creado en el proceso de contratación o el portal del candidato. Puede leer y escribir datos directamente del Common Data Service. También puede personalizar la solución de modo que desencadene flujos o aproveche funciones de Microsoft Azure. Para obtener más información sobre cómo configurar la actividad de contenido web, consulte las [Actividades en los procesos de contratación](./activities-attract.md).

> [!NOTE]
> La actividad de contenido web está disponible únicamente con el complemento de contratación completo.
