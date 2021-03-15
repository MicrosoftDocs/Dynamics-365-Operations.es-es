---
title: Introducción a la API de integración del sistema de seguimiento de candidatos
description: Este tema describe la API de integración del sistema de seguimiento de candidatos (ATS) de Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 48e368fe69443a5105ddba78a887bf9159bfe52a
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125602"
---
# <a name="applicant-tracking-system-integration-api-introduction"></a>Introducción a la API de integración del sistema de seguimiento de candidatos

Este tema describe la API de integración del sistema de seguimiento de candidatos (ATS) de Dynamics 365 Human Resources. La intención de la API es permitir integraciones optimizadas entre Dynamics 365 Human Resources y los ATS asociados.

![Flujo de integración con ATS](media/hr-admin-integration-ats-api-introduction-flow.png)

La experiencia integrada comienza en Recursos Humanos, cuando un gerente de contratación crea una solicitud de contratación. Cuando se activa la solicitud, el ATS extrae el detalle de la solicitud para crear un proyecto de contratación. Luego sigue el proceso de contratación para seleccionar y contratar candidatos para los puestos. Finalmente, el ATS completa la integración de ida y vuelta enviando el registro del candidato seleccionado a Recursos Humanos. El registro de candidato puede luego pasar por más validaciones de incorporación y flujos de trabajo para crear el registro de empleado.

Para habilitar la integración, Recursos Humanos ha agregado los siguientes componentes:

1.  Funcionalidad para crear una solicitud de contratación.
2.  Un perfil de candidato ampliado y flujos de trabajo relacionados.
3.  Una API de integración que abre la nueva funcionalidad para integrar aplicaciones.

Para obtener más información sobre cómo configurar y utilizar la funcionalidad de solicitud de contratación y candidatos, consulte [Contratar candidatos para el trabajo](hr-personnel-recruit.md).

## <a name="microsoft-dataverse"></a>Microsoft Dataverse

Esta API se basa en Microsoft Dataverse (antes Common Data Service). Toda la interacción RESTful con esta API se realiza a través de la API web Microsoft Dataverse, que utiliza OData. Esta API es un subconjunto de la API web de Dataverse. La API web de Dataverse define características como autenticación, SLA, lotes, control de concurrencia y manejo de errores.

Para obtener más información general acerca de la API web de Microsoft Dataverse, consulte:

- [¿Qué es Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)
- [Utilizar la API web de Microsoft Dataverse](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/overview)
- [Guía de desarrollador de Microsoft Dataverse](https://docs.microsoft.com/powerapps/developer/data-platform)

La documentación anterior incluye detalles y orientación para desarrolladores sobre el uso de la API web de Dataverse, como [gestionar la autenticación](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/authenticate-web-api), [realizar operaciones](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/perform-operations-web-api), [uso de Postman con la API](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/use-postman-web-api) y [uso de seguimiento de cambios o tokens delta](https://docs.microsoft.com/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems) con la API.

### <a name="option-sets"></a>Conjuntos de opciones

El modelo de datos para la API de integración ATS descrito en este documento incluye conjuntos de opciones que proporcionan valores enumerados asociados con las propiedades de la entidad. Para obtener detalles sobre cómo trabajar con conjuntos de opciones en la API web de Dataverse, consulte [Crear y actualizar conjuntos de opciones usando la API web](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-update-optionsets). Los conjuntos de opciones se definen para cada entorno de Dataverse.

### <a name="virtual-tables-for-human-resources-in-dataverse"></a>Tablas virtuales para Recursos Humanos en Dataverse

Los puntos de conexión de la API de integración ATS utilizan las capacidades de la plataforma de tabla virtual de Microsoft Dataverse. De forma predeterminada, las tablas virtuales y sus puntos de conexión de API asociados no se implementan para entornos de Recursos Humanos, lo que permite a las organizaciones determinar qué punto de conexión estarán expuestos para el entorno. Para utilizar la API, se deben generar las tablas virtuales para las entidades de Recursos Humanos para el entorno. 

Para obtener información sobre la generación de tablas virtuales para la API, consulte [Configurar tablas virtuales de Dataverse](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).

## <a name="data-model"></a>Modelo de datos

El modelo de datos se centra en dos entidades principales:

- **RecruitingRequest** representa una solicitud a un ATS de contratar para una o más posiciones abiertas. Para una consulta de ejemplo, vea [Consulta de ejemplo para solicitud de contratación](hr-admin-integration-ats-api-recruiting-request-example-query.md).
- **CandidateToHire** representa detalles de un candidato que ha aceptado una oferta para un puesto. **Persona** representa al individuo que es el candidato. Una persona puede tener varios roles en la empresa, como candidato, trabajador, empleado o contratista. Para obtener una consulta de ejemplo, consulte [Consulta de ejemplo para candidato a contratar](hr-admin-integration-ats-api-candidate-to-hire-example-query.md).

El siguiente diagrama ilustra las relaciones dentro de la API. Diversos tipos tienen claves extranjeras para otras entidades preexistentes en Recursos Humanos que no se ilustran aquí. Este documento proporciona información sobre las entidades específicas para los escenarios de integración de contratación. Sin embargo, hay muchas otras entidades en la API web de Dataverse para Dynamics 365 Human Resources que también pueden ser relevantes para su integración. Por ejemplo, es posible que también necesite detalles para trabajadores, trabajos, puestos u otras entidades no definidas aquí. Muchas de estas entidades están referenciadas en relaciones de clave externa o propiedades de navegación.

![Modelo de datos de API de integración de ATS](media/hr-admin-integration-ats-api-data-model.png)

## <a name="recruiting-request-and-related-entities-and-option-sets"></a>Solicitud de contratación, entidades relacionadas y conjuntos de opciones

Consulta de ejemplo: 

- [Consulta de ejemplo para solicitud de contratación](hr-admin-integration-ats-api-recruiting-request-example-query.md)

Entidades:

- [Solicitud de contratación](hr-admin-integration-ats-api-recruiting-request.md)
- [Puesto de solicitud de contratación](hr-admin-integration-ats-api-recruiting-request-position.md)
- [Capacidad de solicitud de contratación](hr-admin-integration-ats-api-recruiting-request-skill.md)
- [Educación de solicitud de contratación](hr-admin-integration-ats-api-recruiting-request-education.md)
- [Ubicación de la solicitud de contratación](hr-admin-integration-ats-api-recruiting-request-location.md)

Conjuntos de opciones:

- [Estado de exención de trabajo](hr-admin-integration-ats-api-job-exempt-status.md)
- [Estado de posición de solicitud de contratación](hr-admin-integration-ats-api-recruiting-request-position-status.md)
- [Estado de solicitud de contratación](hr-admin-integration-ats-api-recruiting-request-status.md)
- [Categoría de trabajo reglamentaria](hr-admin-integration-ats-api-regulatory-job-category.md)

## <a name="candidate-to-hire-and-related-entities-and-option-sets"></a>Candidato a contratar, entidades relacionadas y conjuntos de opciones

Consulta de ejemplo:

- [Consulta de ejemplo para candidato a contratar](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

Entidades:

- [Candidato a contratar](hr-admin-integration-ats-api-candidate-to-hire.md)
- [Persona](hr-admin-integration-ats-api-person.md)
- [Educación personal](hr-admin-integration-ats-api-person-education.md)
- [Experiencia profesional personal](hr-admin-integration-ats-api-person-professional-experience.md)
- [Dirección de la persona](hr-admin-integration-ats-api-person-address.md)
- [Contacto de parte](hr-admin-integration-ats-api-party-contact.md)
- [Habilidad de la persona](hr-admin-integration-ats-api-person-skill.md)
- [Nivel de evaluación](hr-admin-integration-ats-api-rating-level.md)
- [Certificado de la persona](hr-admin-integration-ats-api-person-certificate.md)
- [Tipo de certificado](hr-admin-integration-ats-api-certificate-type.md)
- [Filtrado de persona](hr-admin-integration-ats-api-person-screening.md)
- [Tipos de filtrado](hr-admin-integration-ats-api-screening-types.md)
- [Número de identificación de persona](hr-admin-integration-ats-api-person-identification-number.md)

Conjuntos de opciones:

- [Resultado de integración de candidatos](hr-admin-integration-ats-api-applicant-integration-result.md)
- [En blanco Sí No](hr-admin-integration-ats-api-blank-yes-no.md)
- [Estado de finalización](hr-admin-integration-ats-api-completion-status.md)
- [Tipo de contacto](hr-admin-integration-ats-api-contact-type.md)
- [Base de crédito educativo](hr-admin-integration-ats-api-education-credit-basis.md)
- [Género](hr-admin-integration-ats-api-gender.md)
- [Estado civil](hr-admin-integration-ats-api-marital-status.md)
- [Meses del año](hr-admin-integration-ats-api-months-of-year.md)
- [No Sí](hr-admin-integration-ats-api-no-yes.md)
- [Unidad del período](hr-admin-integration-ats-api-period-unit.md)
- [Frecuencia de cribado](hr-admin-integration-ats-api-screening-frequency.md)
- [Origen de generación de la frecuencia de cribado](hr-admin-integration-ats-api-screening-frequency-generate-from.md)
- [Tipo de nivel de capacidad](hr-admin-integration-ats-api-skill-level-type.md)

## <a name="see-also"></a>Consulte también

[Contratar candidatos de trabajo](hr-personnel-recruit.md)<br>
[¿Qué es Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)<br>
[Utilizar la API web de Microsoft Dataverse](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/overview)<br>
[Crear y actualizar conjuntos de opciones usando la API web](https://docs.microsoft.com/powerapps/developer/data-platform/webapi/create-update-optionsets)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]