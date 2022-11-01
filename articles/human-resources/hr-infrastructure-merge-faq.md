---
title: Preguntas frecuentes de la fusión de infraestructura de Dynamics 365 Human Resources
description: Este artículo responde a las preguntas más frecuentes sobre la fusión de la infraestructura para Microsoft Dynamics 365 Human Resources y aplicaciones de finanzas y operaciones.
author: twheeloc
ms.date: 09/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 32698d887b4d228ded588984b09068e3e2fef9a4
ms.sourcegitcommit: 27ce4fc706100b626b81c3a1023238acd872e76c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "9702077"
---
# <a name="dynamics-365-human-resources-infrastructure-merge-faq"></a>Preguntas frecuentes de la fusión de infraestructura de Dynamics 365 Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="what-is-dynamics-365-human-resources"></a>¿Qué es Dynamics 365 Human Resources?

Microsoft Dynamics 365 Human Resources proporciona herramientas que ayudan a los equipos de recursos humanos a aumentar la agilidad organizacional, transformar la experiencia de los empleados y optimizar los programas de recursos humanos para crear un lugar de trabajo donde las personas y la empresa puedan prosperar. Para obtener más información acerca de Dynamics 365 Human Resources, consulte [Dynamics 365 Human Resources](https://dynamics.microsoft.com/human-resources/overview/).

- **Transforme las experiencias de los empleados.** Retenga a los mejores trabajadores capacitando a los gerentes y empleados a través de experiencias de autoservicio conectadas que impulsan el compromiso y el crecimiento.
- **Optimice los programas de recursos humanos.** Reduzca los costes operativos y cree programas de administración de bajas y ausencias, tiempo, beneficios y compensaciones centrados en las personas.
- **Aumente la agilidad de la organización.** Permita que RR. HH. opere con la destreza que requiere el negocio mediante el uso de Dataverse y Microsoft Power Platform para centralizar los datos de las personas y ampliar fácilmente Dynamics 365 Human Resources.
- **Obtenga conocimientos de los recursos.** Tome decisiones basadas en datos a través de la capacidad de analizar y visualizar datos de personas en paneles enriquecidos que están disponibles en cualquier dispositivo.

## <a name="value-and-benefits-of-the-infrastructure-merge"></a>El valor y los beneficios de la infraestructura se fusionan

### <a name="what-is-the-dynamics-365-human-resources-infrastructure-merge"></a>¿Qué es la fusión de infraestructura de Dynamics 365 Human Resources?

Actualmente hay dos conjuntos separados de capacidades de recursos humanos en dos infraestructuras diferentes en Dynamics 365:

- **Dynamics 365 Human Resources** – Una aplicación independiente que se ejecuta en una infraestructura independiente. Cuando se lanzó esta aplicación, la infraestructura estaba separada de otras aplicaciones de operaciones de Dynamics 365. Nuestros clientes usan esta aplicación para aumentar la agilidad de la organización, optimizar los programas de recursos humanos, transformar las experiencias de los empleados y obtener conocimientos de los recursos.
- **Módulo de recursos humanos** – Un conjunto heredado de capacidades que anteriormente formaba parte de la referencia de almacén (SKU) de licencias de Unified Operations. El módulo de recursos humanos se ejecuta en la infraestructura de finanzas y operaciones, que es la misma en todas las aplicaciones de operaciones. Estas aplicaciones incluyen Dynamics 365 Finance, Dynamics 365 Project Operations y Dynamics 365 Supply Chain Management. Los clientes recibieron las capacidades de recursos humanos como parte de Dynamics 365 Finance o Dynamics 365 Supply Chain Management.

En los tres últimos años, Microsoft no ha agregado nuevas capacidades ni mejoras al módulo de recursos humanos. En cambio, nuestras inversiones de la hoja de ruta se han centrado en la aplicación Dynamics 365 Human Resources.

Al incorporar estos dos conjuntos de capacidades en la misma infraestructura, ayudaremos a los clientes a obtener los siguientes beneficios:

- Mejoras que se han agregado a Dynamics 365 Human Resources durante los últimos tres años, incluida la mejora de las bajas y ausencias, administración de prestaciones y la presentación de informes.
- Extensibilidad mejorada a través de Microsoft Power Platform y la capacidad de ampliar la lógica de negocio para personalizar páginas.
- Mejoras en la implementación, actualizaciones y mantenimiento coherentes en términos de gestión del ciclo de vida de las aplicaciones (ALM), Lifecycle Services (LCS), disponibilidad geográfica, etc.
- Más innovación tecnológica a medida que nuestro equipo de ingeniería utiliza servicios compartidos, herramientas y costes de plataforma reducidos.

Esta transición afectará a los clientes que actualmente utilizan Dynamics 365 Human Resources o el módulo de recursos humanos heredado.

## <a name="glossary-of-terms-used-in-this-faq"></a>Glosario de términos utilizados en estas preguntas frecuentes

- **Dynamics 365 Human Resources** – Nuestro producto actual y futuro que ofrece capacidades de recursos humanos al mercado.
- **Módulo de recursos humanos** – Un conjunto de capacidades heredadas que se concedían bajo la licencia de Unified Operations. Las capacidades se habilitan cuando un cliente posee Dynamics 365 Finance o Dynamics 365 Supply Chain Management.
- **Infraestructura de finanzas y operaciones** – La arquitectura de desarrollo que utiliza la cartera de operaciones, incluido Dynamics 365 Finance, Dynamics 365 Supply Chain Management y Dynamics 365 Project Operations. Esta infraestructura es la que se utilizará en el futuro. En estas preguntas frecuentes, el término *infraestructura fusionada* se refiere al entorno de finanzas y operaciones.
- **Infraestructura de recursos humanos** – La arquitectura de desarrollo que se utilizó históricamente para la aplicación Dynamics 365 Human Resources. El proyecto de fusión de la infraestructura introduce Dynamics 365 Human Resources en la infraestructura de finanzas y operaciones. Se suspenderá la infraestructura independiente.

## <a name="general-questions-about-the-infrastructure-merge"></a>Preguntas generales sobre la fusión de la infraestructura

### <a name="will-customers-lose-any-features-or-capabilities"></a>¿Perderán los clientes alguna característica o capacidad?

Nuestro objetivo es minimizar el impacto que esta transición tiene en los clientes. No eliminaremos ninguna característica o capacidad. Habrá paridad funcional entre Dynamics 365 Human Resources y el módulo de RR. HH. En los casos en que exista una característica en ambas infraestructuras, se utilizará la experiencia de Dynamics 365 Human Resources.

### <a name="will-the-user-experience-change"></a>¿Cambiará la experiencia de usuario?

La experiencia de usuario será coherente con la experiencia estándar de la plataforma Dynamics 365. Aunque la experiencia general del panel y los menús seguirá siendo similar, se alineará con la experiencia estándar de la aplicación Dynamics 365 Finance. La navegación incluirá tanto módulos como espacios de trabajo, permitirá favoritos y más. Los espacios de trabajo de Dynamics 365 Human Resources, como **Administración de personal** y **Personas**, se combinarán con la infraestructura de finanzas y operaciones. En el futuro, las nuevas capacidades se entregarán a través de la administración de características, que permite a los clientes ver las nuevas funciones y decidir cuáles quieren usar. Para más información, vea [Descripción general de la administración de características](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) y [Documentación de la interfaz de usuario](../fin-ops-core/fin-ops/get-started/user-interface-elements.md?toc=/dynamics365/human-resources/toc.json).

### <a name="when-will-the-dynamics-365-human-resources-infrastructure-merge-be-completed"></a>¿Cuándo se completará la fusión de la infraestructura de Dynamics 365 Human Resources?

La fusión de la infraestructura se implementará en fases para que los clientes tengan tiempo de planificar y completar los pasos necesarios. Comenzamos a implementar capacidades en el segundo lanzamiento de versiones de Dynamics 2021. Planeamos completar todos los esfuerzos de desarrollo de productos para este proyecto para fines de 2022, segundo lanzamiento de versiones. Tenga en cuenta que los plazos están sujetos a cambios. Para obtener la información más actualizada, consulte [planes de lanzamiento](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-finance).

### <a name="what-training-and-resources-will-be-available-to-help-with-the-infrastructure-merge"></a>¿Qué capacitación y recursos estarán disponibles para ayudar con la fusión de la infraestructura?

Se proporcionará documentación que describe cada paso del proceso de fusión de la infraestructura en detalle. Proporcionaremos recursos de formación adicionales, como vídeos y talleres, según sea necesario para ayudar a los clientes y socios con una transición sin problemas.

### <a name="will-there-be-changes-in-development-capabilities-after-the-infrastructure-merge-is-completed"></a>¿Habrá cambios en las capacidades de desarrollo después de que se complete la fusión de la infraestructura?

Para obtener más información sobre las capacidades de desarrollo, consulte [Desarrollar y personalizar la página de inicio](../fin-ops-core/dev-itpro/dev-tools/developer-home-page.md).

## <a name="feature-availability-questions"></a>Preguntas sobre la disponibilidad de funciones

### <a name="will-the-linkedin-talent-hub-integration-work-on-the-finance-and-operations-infrastructure"></a>¿Funcionará la integración de LinkedIn Talent Hub en la infraestructura de finanzas y operaciones?

No, la integración de LinkedIn Talent Hub no formará parte de la infraestructura fusionada. Hay interfaces de programación de aplicaciones (API) públicas disponibles para crear integraciones con soluciones de reclutamiento y seguimiento de candidatos. Los clientes que planeen usar LinkedIn Talent Hub deben trabajar con su partner de Microsoft para realizar la integración mediante las API proporcionadas. Para obtener más información sobre las API de integración del sistema de seguimiento de candidatos (ATS), consulte [Introducción a la API de integración del sistema de seguimiento de candidatos](./hr-admin-integration-ats-api-introduction.md).

### <a name="will-the-capabilities-that-are-currently-available-only-in-dynamics-365-human-resources-for-example-leave-management-and-benefits-management-be-available-after-the-merge-is-completed"></a>¿Las capacidades que actualmente están disponibles solo en Dynamics 365 Human Resources (por ejemplo, gestión de licencias y gestión de beneficios) estará disponible después de que se complete la fusión?

Sí. Todas las capacidades de la aplicación Dynamics 365 Human Resources se están incorporando a la infraestructura de finanzas y operaciones. Las características estarán disponibles en un enfoque por etapas. Para obtener información actualizada sobre la disponibilidad de características para la infraestructura fusionada, revise regularmente los [planes de lanzamiento](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-finance).

### <a name="will-ceridian-integrations-with-dynamics-365-human-resources-be-available-after-the-infrastructure-merge-is-completed"></a>¿Las integraciones de Ceridian con Dynamics 365 Human Resources estarán disponible tras completar la fusión de la infraestructura?

Ceridian está en proceso de crear una integración V2 con Dynamics 365 Human Resources que aprovecha las API de nómina. La integración basada en archivos que existe actualmente en Dynamics 365 Human Resources no se migrará a la infraestructura de finanzas y operaciones. Para más información, vea [Introducción a la API de nóminas](./hr-admin-integration-payroll-api-introduction.md).

### <a name="will-applicant-tracking-or-onboardingoffboarding-of-employees-functionality-be-included"></a>¿Se incluirá el seguimiento de candidatos o la incorporación/baja de la funcionalidad del empleado?

En versiones anteriores, creamos la API de integración de ATS para permitir a los socios y clientes crear integraciones de ATS con Recursos Humanos. La funcionalidad adicional relacionada con ATS estuvo disponible en el primer lanzamiento de versiones de 2022. Continuaremos mejorando estas API en versiones futuras.

La funcionalidad de recursos humanos que existe actualmente en la infraestructura de finanzas y operaciones incluye algunas funciones de administración de contrataciones que no existen en Dynamics 365 Human Resources. Cuando se complete la fusión de la infraestructura, esta funcionalidad estará disponible para todos los clientes de Recursos Humanos. Esta funcionalidad proporciona una funcionalidad ATS ligera. Sin embargo, no planeamos expandir esta funcionalidad en el futuro. Los clientes que requieren una funcionalidad más avanzada pueden aprovechar las integraciones de ATS de asociados. Para obtener más información sobre las API de integración de ATS, consulte [Introducción a la API de integración del sistema de seguimiento de candidatos](./hr-admin-integration-ats-api-introduction.md).

### <a name="will-the-dynamics-ax-2012-upgrade-tools-be-used-to-upgrade-the-hr-module-in-ax-2012-to-the-dynamics-365-human-resources-app"></a>¿Se utilizarán las herramientas de actualización de Dynamics AX 2012 para actualizar el módulo de recursos humanos en AX 2012 a la aplicación de Dynamics 365 Human Resources?

Sí. La actualización de Dynamics AX 2012 a Dynamics 365 Human Resources seguirá la misma ruta de actualización y las mismas herramientas que se emplean para actualizar a la última versión de otras aplicaciones de finanzas y operaciones, como Dynamics 365 Finance o Dynamics 365 Supply Chain Management.

Para obtener más información sobre la migración a la infraestructura de finanzas y operaciones, consulte [Preguntas frecuentes sobre la migración de clientes de recursos humanos](./customer-migration.md).
