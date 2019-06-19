---
title: Obtener acceso a las características de vista previa de Microsoft Dynamics 365 for Talent
description: Este tema describe cómo un administrador puede habilitar las características de vista previa en Microsoft Dynamics 365 for Talent, y enumera las características que se habilitan actualmente para la vista previa.
author: tracykeya
manager: AnnBe
ms.date: 05/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: trkeya
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.1.0, Talent April 2019 update
ms.openlocfilehash: 2858451435c358380503c8edc5cb162e6834894a
ms.sourcegitcommit: fcae2e7938d7dbd94b76b0948b084d90d5fc919c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2019
ms.locfileid: "1620605"
---
# <a name="access-preview-features-in-talent"></a>Obtener acceso a las características de vista previa de Talent

[!include[banner](../includes/banner.md)]

Como parte de nuestro desarrollo continuo de las capacidades de administración del capital humano (HCM) para Microsoft Dynamics 365 for Talent, deseamos que los clientes experimenten las nuevas características lo más rápidamente posible. Los administradores pueden ver y utilizar características de vista previa en los entornos. Estas características casi están preparadas para la disponibilidad general y han pasado por un amplio proceso de pruebas. Simplemente estamos buscando una ronda final de comentarios de clientes y de validación antes de estén disponibles de forma general.

Este tema describe cómo puede habilitar las características de vista previa, y enumera las características que están habilitadas actualmente para la vista previa. Esta lista se actualizará a medida que se pongan nuevas características a disposición de todos y a medida que se lancen nuevas características para probarlas previamente. No se da ninguna notificación cuando las nuevas características se lanzan para obtener una vista previa. Los usuarios solo comenzarán a ver las características. Para obtener más información sobre características nuevas en Talent, consulte [Novedades o cambios en Dynamics 365 for Talent](./whats-new.md) y [Notas de la versión de Dynamics 365 y Power Platform](https://docs.microsoft.com/business-applications-release-notes).

## <a name="enable-or-disable-preview-features"></a>Habilitar o deshabilitar las funciones de vista previa

Para obtener acceso a características de vista previa, primero debe permitirlas en el entorno. Habilitar o deshabilitar las características de vista previa es específica del entorno.

> [!IMPORTANT]
> Cuando activa la configuración **Funciones de vista previa**, habilita las características de vista preliminar para todos los usuarios de la organización que se encuentran en dicho entorno. Cuando desactiva la configuración, deshabilita las características de vista previa y hace que no sean accesibles a los usuarios. Las funciones de vista previa tienen compatibilidad limitada en Talent. Es posible que apliquen menos medidas de privacidad y de seguridad, y no se incluyen en el contrato de nivel de servicio (SLA) de Talent. No debe utilizar características de vista preliminar para procesar datos personales (es decir, toda información que pueda identificarle), o para procesar otros datos sujetos a requisitos de conformidad legales o administrativos.

### <a name="attract"></a>Atraer

1. Iniciar sesión en Microsoft Dynamics 365 for Talent: Attract.
2. En el menú **Configuración** (el símbolo de engranaje) en la esquina superior derecha, seleccione **Centro de administración**.
3. En la pestaña **Administración de características**, seleccione la opción que está al lado de **Vista previa de características** para que se vuelva azul y pase a **Activada**.

    ![Habilitar vista previa de características en Attract](./media/attract-enable-preview-features.png)

4. Seleccione o cancele la selección de características individuales de la vista previa. Si no hace nada, se activan todas las funciones disponibles de la vista previa.
5. Actualice al explorador para empezar a ver las nuevas características. Cualquier usuario que ya haya iniciado sesión verá las características la siguiente vez que inicie sesión, o puede actualizar al explorador para ver las características inmediatamente.

> [!NOTE]
> Algunas funciones de vista previa puede requerir configuración adicional. Siga los vínculos que se encuentran junto a la característica de vista preliminar para completar la configuración.

### <a name="core-hr"></a>Core HR

1. Inicie sesión en Talent.
2. Seleccione **Administración del sistema**, y seleccione la pestaña **Vínculos**.
3. En la página **Administración del sistema**, en **Configuración**, seleccione **Parámetros del sistema**.
4. En la página **Parámetros del sistema**, seleccione la pestaña **Características de vista previa**.
5. Establezca la opción **Modo de vista previa de permiso para todos los usuarios** en **Sí** para que las características de vista estén disponibles.

    ![Habilitar vista previa de características en Core HR](./media/corehr-enable-preview-features.png)

> [!NOTE]
> Para deshabilitar las características de vista previa siga los mismos pasos, pero establezca **Habilitar modo de vista previa para todos los usuarios** en **No**. Cuando deshabilita las características de vista previa, estas se vuelven inaccesibles para sus usuarios, y pueden producirse errores en los procesos asociados a las características.

### <a name="onboard"></a>Incorporar

Actualmente no hay características de vista previa disponibles para Microsoft Dynamics 365 for Talent: Onboard.

## <a name="features-that-are-currently-in-preview"></a>Características que están actualmente en vista previa

### <a name="attract"></a>Atraer

- [Recomendación de candidato](./intelligent-recommendations.md#candidate-recommendations) - Si hay más de diez candidatos que tienen curriculums vitae o perfiles completos, los candidatos que mejor cumplan los requisitos de trabajo aparecen en la sección **Candidatos a considerar** en la página del trabajo.
- [Recomendación de trabajo](./intelligent-recommendations.md#job-recommendations) – Si más de diez trabajos se registran en el sitio profesional, Attract proporciona recomendaciones del trabajo a los clientes potenciales.
- [Integración de Broadbean](./posting-jobs-external.md#post-jobs-to-broadbean) – Puede enviar los trabajos desde Attract a Broadbean, un sitio externo de ofertas de empleo. Una vez habilite esta característica de vista previa, debe completar la configuración introduciendo su nombre de usuario de Broadbean, identificador de cliente, y token de cifrado.
- [Análisis](./analytic-reports.md) - En el Centro de análisis, los equipos de contratación pueden ver medidas clave para un trabajo único y medidas agregada a través de todos los trabajos.
- [EEO](./activities-attract.md) - Los nuevos tipos de actividad habilitan el uso de un formulario predefinido para la recopilación de Oportunidad de Igualdad de Empleo (EEO) y los datos de la Oficina de Programas de Cumplimiento de Contratos Federales (OFCCP) del candidato. El formulario predefinido no puede editarse.
- [Recomendación de candidato](./intelligent-recommendations.md#prospect-recommendations) – Attract revisa candidatos pasados y actuales para proporcionar una lista de candidatos potenciales que son una buena coincidencia para su trabajo.
- [Búsqueda por importancia](./attract-talent-pools.md#search-and-view-candidate-profiles) – Puede buscar en la base de datos completa de candidatos según aptitudes específicas, nombres o formaciones académicas. Attract busca todo el perfil y resalta todas las coincidencias que encuentra. Attract también busca todos los documentos que están disponibles para un candidato y ordena de forma inteligente los resultados de la búsqueda.
- [Actividad de la audiencia](./whats-new-talent-march-20.md#setting-the-audience-on-activities) – Puede establecer la audiencia para actividades (como entrevista, programación o comentarios) en **Todos los candidatos**, **Candidatos internos**, o **Candidatos externos**. Las actividades personalizadas, como formularios de Microsoft, vídeos de YouTube se pueden entregar a todos los candidatos, solo candidatos internos, solo candidatos externos o al equipo de contratación.
- [Solicitar con LinkedIn](./career-site.md#enable-applying-for-jobs-with-linkedin-profiles) – Puede configurar una opción en su sitio profesional de Attract para permitir a los candidatos presentarse usando LinkedIn. Esta característica agiliza el proceso de aplicación para los candidatos dejándolos utilizar el perfil de LinkedIn automáticamente para rellenar sus aplicación en el sitio de proyectos profesionales.
- [Seguimiento de origen](./source-tracking.md) – Attract sigue el origen de las solicitudes del candidato para proporcionar información valiosa que le puede servir de ayuda para alcanzar los objetivos de contratación. Usted también puede seleccionar un origen de la aplicación cuando agrega manualmente un candidato a un trabajo o la reserva de talentos.
- [Medallista de plata](./whats-new-talent-march-20.md#designate-silver-medalists-to-assign-high-value-applicants-for-future-positions) – Si algunos candidatos serían un gran aporte para su organización, pero no les ha hecho una oferta para el puesto actual, puede señalarlos como medallistas de plata. Esta función ayuda a reducir el tiempo de contratación la próxima vez que tenga un puesto similar disponible.

### <a name="core-hr"></a>Core HR

- [Validar los datos de la jerarquía de puestos](./whats-new-talent-may-13-2019.md#new-page-to-validate-position-hierarchy-data) – Puede validar la jerarquía directiva para cualquier referencia circular que se importe de forma inadvertida.
- [Especificar códigos de motivo en tipos de baja](./whats-new-talent-may-13-2019.md#specify-reason-codes-on-leave-types) – Puede especificar códigos de motivo para los tipos de baja.
- [Exigir códigos de motivo en solicitudes de tiempo de indisponibilidad](./whats-new-talent-may-13-2019.md#require-reason-codes-for-specific-leave-types-on-time-off-requests) – Además de especificar códigos de motivo para los tipos de baja, puede requerir que los códigos de motivo para las solicitudes de tiempo de indisponibilidad.
- [Proporcionar una lista de bajas y ausencias para RR. HH.](./whats-new-talent-may-13-2019.md#provide-a-leave-and-absence-transaction-list-for-hr) – Puede ver una lista de bajas y de transacciones de ausencia para ayudar a proporcionar información sobre los saldos de ausencias.

### <a name="onboard"></a>Incorporar

Actualmente no hay características de vista previa disponibles para Onboard.

## <a name="feedback"></a>Realimentación

Queremos conocer su experiencia con cualquiera de estas características de la vista previa. Recomendamos que publique con regularidad sus comentarios en los sitios siguientes cuando use estas características u otras:

- [Comunidad](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – Este sitio es un gran recurso en el que los usuarios pueden discutir los casos de uso, hacer preguntas, y obtener ayuda de la comunidad.
- Infórmenos sobre las características que desea ver en el producto, así como los cambios que crea que deberíamos realizar en las características existentes. Sugiera ideas para productos en los siguientes sitios:

    - [Ideas para Attract](https://powerusers.microsoft.com/t5/Ideas-for-Attract/idb-p/Attract)
    - [Ideas para Core HR](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources)
    - [Ideas para Onboard](https://powerusers.microsoft.com/t5/Ideas-for-Onboard/idb-p/Onboard)

Asegúrese de no incluir datos personales (información que podría identificarlo) en los envíos de comentarios o de revisión del producto. La información que se obtiene se puede analizar más, pero no se usará para responder a solicitudes, de acuerdo con las leyes aplicables de privacidad. La información personal obtenida por separado en estos programas está sujeta a la [Declaración de privacidad de Microsoft](https://privacy.microsoft.com/privacystatement).

> [!TIP]
> Marque este tema, y consúltelo a menudo para mantenerse actualizado sobre características nuevas de vista previa a medida que las lanzamos al mercado.

## <a name="see-also"></a>Consulte también

- [Pruebe o compre las aplicaciones Talent](https://dynamics.microsoft.com/talent/overview/)
- [Novedades](./whats-new.md)
- [Notas de la versión](https://docs.microsoft.com/business-applications-release-notes/index)
- [Obtener soporte para Talent](./talent-support.md)
