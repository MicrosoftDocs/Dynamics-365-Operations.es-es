---
title: Conseguir candidatos con LinkedIn Recruiter en Attract
description: Use la integración de LinkedIn proporcionada por Microsoft Dynamics 365 Talent - Attract para conseguir candidatos de trabajo con LinkedIn Recruiter.
author: andreabichsel
manager: AnnBe
ms.date: 08/31/2020
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
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 96e4660c4958bf5f2a0910bfad770e1e713f800f
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528278"
---
# <a name="source-candidates-with-linkedin-recruiter-in-attract"></a>Conseguir candidatos con LinkedIn Recruiter en Attract

[!include [banner](includes/banner.md)]

LinkedIn es la red profesional conectada mayor del mundo, que da acceso al talento superior del mundo. Microsoft Dynamics 365 Talent: Attract le permite obtener candidatos directamente de LinkedIn. Por lo tanto, resulta más fácil que nunca encontrar el talento que necesita para cubrir sus vacantes. Después de configurar su conexión con LinkedIn a través de Attract, puede ver los candidatos potenciales de LinkedIn a sus puestos y exportarlos a Attract con solo un clic.

Si no parece tener esta capacidad, póngase en contacto con su administrador. Para poder aprovechar LinkedIn Recruiter desde Attract, el administrador debe [configurar la integración con LinkedIn](./attract-admin-linkedin.md). A continuación podrá configurar su conexión con LinkedIn Recruiter y comenzar a encontrar candidatos.

>[!IMPORTANT]
>A partir del 1 de julio de 2020, LinkedIn ya no admite Internet Explorer 11. Los usuarios aún pueden obtener acceso a LinkedIn con Internet Explorer 11, pero se le pedirá que actualice o utilice un navegador diferente. Para obtener más información, consulte [Navegadores de Internet admitidos en LinkedIn](https://www.linkedin.com/help/linkedin/answer/4135/supported-internet-browsers-for-linkedin).

## <a name="set-up-your-connection-with-linkedin-recruiter"></a>Configurar su conexión con LinkedIn Recruiter

Para poder comenzar a trabajar con LinkedIn Recruiter a través de Attract, debe configurar su conexión con LinkedIn Recruiter. Para este paso, necesita sus credenciales de LinkedIn Recruiter.

1. Seleccione el botón **Configurar** (icono de engranaje) en la esquina superior derecha de la página.
2. Seleccione **configuración de usuario**.
3. En la pestaña **Conexiones**, seleccione **Conectar** al lado de **LinkedIn**. Siga las instrucciones que se proporcionan en LinkedIn.

    ![[Configurar conexión a LinkedIn Recruiter desde Attract](./media/attract-set-up-linkedin-recruiter-connection.png)](./media/attract-set-up-linkedin-recruiter-connection.png)

## <a name="view-linkedin-candidates-in-attract"></a>Ver los candidatos de LinkedIn en Attract

Tras conectarse a LinkedIn Recruiter, puede ver los perfiles de LinkedIn de los candidatos en Attract.

>[!NOTE]
>Si tiene un puesto de contratante asignado, puede ver la información completa de los candidatos.<br><br>
>Si tiene un puesto de Responsable de contratación o no tiene ningún puesto asignado, asegúrese de cerrar la sesión de LinkedIn o LinkedIn Recruiter antes de navegar a la pestaña LinkedIn de un candidato en Attract. Podrá ver los datos básicos del perfil público del candidato, como su nombre y apellido.

1. En Attract, seleccione **Trabajos** o **Grupos de talentos** a la izquierda, y seleccione un candidato.

    ![[Ver los candidatos de LinkedIn en Attract](./media/attract-view-linkedin-candidates.png)](./media/attract-view-linkedin-candidates.png)

2. En el perfil del candidato, seleccione la pestaña **LinkedIn**. Puede ver el perfil del candidato y el historial de InMail.

   ![Ver la información de LinkedIn de un candidato](./media/attract-candidate-linkedin-tab.png)

Desde aquí, puede realizar las siguientes acciones:

- Seleccione la pestaña **Actividades de contratación** para ver:
   
   - Notas del contratante (tanto públicas como privadas). De forma predeterminada, las notas son privadas y solo visibles para su propietario.
   - Actividad de InMail (pero no el contenido de InMail). Desplácese hasta la parte inferior de la página para ver el intercambio de InMail con su cliente potencial y vea a otros usuarios de su organización que están interactuando con su cliente potencial.
   - Actividad de rechazo de candidatos

- Seleccione **Enviar InMail** para enviar InMail sin tener que salir de Attract.

- Seleccione **Guardar en un trabajo** para guardar el trabajo sin salir de Attract.

> [!NOTE]
> El perfil de LinkedIn de un candidato se mostrará en Attract cuando la información de Attract del candidato coincida con la información de LinkedIn. Las reglas de coincidencia que se utilizan son las siguientes:
> 
> 1. Si el identificador de miembro de LinkedIn y la dirección de correo electrónico coinciden en Attract y LinkedIn, el perfil del candidato se muestra. Los candidatos aún tienen la opción de vincular o desvincular su perfil de LinkedIn de Attract.
> 2. Si identificador de miembro de LinkedIn y la dirección de correo electrónico no coinciden, verá una lista de candidatos posibles. A continuación, puede seleccionar un candidato en la lista y vincular el perfil.
> 3. Si no hay buenas coincidencias, se le notifica que no se ha encontrado ninguna coincidencia.

## <a name="export-linkedin-candidates-to-attract-with-one-click"></a>Exportar los candidatos de LinkedIn a Attract con un clic

A medida que está revisando candidatos en LinkedIn Recruiter, puede exportarlos a los trabajos que tiene actualmente abiertos en Attract. Para este paso, necesita permisos de reclutador o responsable de contratación en Attract. Para obtener más información sobre roles en Attract, consulte [Seguridad y gestión de roles en Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/security-attract).

También debe asegurarse de que el trabajo tiene una etapa de cliente potencial. Para obtener más información, consulte [Actividad de candidatos potenciales](./activities-attract.md#prospect-activity).

1. En Attract, cree un trabajo, asigne los roles adecuados, y active el trabajo.
2. En LinkedIn Recruiter, encuentre a un buen candidato al trabajo, y vaya al perfil del candidato.
3. En el cuadro de búsqueda de la tarjeta de contacto, busque el trabajo mediante el título o el identificador de trabajo que se ha activado en Attract. Si no encuentra el trabajo, haga clic en **Cambiar ATS** para encontrar la instancia de Attract correcta.
4. Seleccione el trabajo y haga clic en **Exportar**.
5. En Attract, abra el trabajo. El candidato exportado aparecerá en la pestaña **cliente potencial** del trabajo.

## <a name="view-attract-information-in-linkedin-recruiter"></a>Ver información de Attract en LinkedIn Recruiter

En LinkedIn Recruiter, puede saber si un candidato ha solicitado otros trabajos en su organización, ver en qué etapa de las solicitudes de trabajo está el candidato y consultar comentarios y valoraciones de Attract.

1. Abra LinkedIn Recruiter, y seleccione un perfil del candidato.
2. Pase el mouse sobre **En el ATS**.
3. Seleccione alguna de las opciones siguientes para ver la información del candidato que se almacena en Attract:

    - **Trabajos y estados** Consulte los trabajos de los que el candidato es parte, el último estado, y cómo el candidato va progresando en cada trabajo.
    - **Comentarios sobre la entrevista** Consulte los comentarios que los entrevistadores han registrado en Attract.
    - **Notas** Vea todas las nota que se hayan especificado para este candidato en Attract.

    ![[Ver información de Attract desde LinkedIn Recruiter](./media/attract-view-information-from-linkedin-recruiter.png)](./media/attract-view-information-from-linkedin-recruiter.png)

> [!NOTE]
> El candidato y los datos de la aplicación no se sincronizarán con LinkedIn Recruiter si el candidato no ha pasado de la etapa de candidato potencial.

## <a name="view-linkedin-talent-pools"></a>Ver grupos de talentos de LinkedIn

Si los candidatos aceptan compartir sus perfiles de LinkedIn con cualquier usuario de la organización, un nuevo registro de candidato se crea en Attract. Estos candidatos aparecerán en un grupos de talentos de LinkedIn creado por el sistema.

1. En Attract, seleccione **Grupos de talentos** en la parte izquierda.
2. Seleccione el grupo de talentos de LinkedIn. Se verá una lista de candidatos y sus perfiles de comprobante de LinkedIn. Los perfiles de comprobante contienen el nombre y los apellidos, y la dirección de correo electrónico del candidato, si el candidato ha elegido compartirlos.

## <a name="see-also"></a>Consulte también

[Integración de Attract con preguntas frecuentes de LinkedIn](./attract-linkedin-faq.md)

[Configurar la integración con LinkedIn para Microsoft Dynamics 365 Talent - Attract](./attract-admin-linkedin.md)

[Crear, aprobar y registrar trabajos en Attract](./creating-jobs-attract.md)

[Publicar trabajos en LinkedIn desde Microsoft Dynamics 365 Talent - Attract](./attract-post-jobs-to-linkedin.md)

[Solución de problemas de la integración con LinkedIn y Microsoft Dynamics 365 Talent - Attract](./attract-troubleshoot-linkedin.md)
