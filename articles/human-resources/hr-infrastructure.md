---
title: 'Fusión de infraestructura de Dynamics 365 Human Resources: actualización de la versión 10.0.25'
description: Este tema proporciona información acerca de la versión 10.0.25 de Microsoft Dynamics 365 Human Resources, que trae la primera oleada de capacidades en la fusión de infraestructura.
author: twheeloc
ms.date: 01/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-27
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9d574f760960241e4d79a988b1b671f224cb345f
ms.sourcegitcommit: 6f6ec4f4ff595bf81f0b8b83f66442d5456efa87
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "8487805"
---
# <a name="dynamics-365-human-resources-infrastructure-merge---release-10025-update"></a>Fusión de infraestructura de Dynamics 365 Human Resources: actualización de la versión 10.0.25

La versión 10.0.25 trae la primera oleada de capacidades en la fusión de infraestructura. Durante la fusión de infraestructura, Microsoft Dynamics 365 Human Resources se fusionará con la infraestructura de Finanzas y Operaciones. Sin embargo, seguirá teniendo licencia como una aplicación independiente, como Dynamics 365 Finance y Dynamics 365 Supply Chain Management. Para obtener más información sobre la fusión de infraestructuras, consulte [Preguntas frecuentes sobre la fusión de infraestructuras de Dynamics 365 Human Resources](../human-resources/hr-infrastructure-merge-faq.md).

La fusión brindará consistencia a los usuarios de Human Resources de las siguientes maneras:

- [La administración del entorno y las integraciones son consistentes entre las aplicaciones de Human Resources y Finanzas y Operaciones.](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/consistent-environment-management-integrations-between-human-resources-finance-operations-apps)

    - Administrar entornos en Microsoft Dynamics Lifecycle Services, búsqueda de problemas y Regression Suite Automation Tool.
    - Hay una base de código única, donde se lanza la nueva funcionalidad para Human Resources como parte del proceso de actualización regular de One Version.
    - La forma en que se aplican mejoras, actualizaciones y revisiones a los entornos es consistente.

- [Se mejoran las opciones de extensibilidad.](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/improve-extensibility-options)

    - Puedes seguir usando las herramientas de Microsoft Power Platform para ampliar según sea necesario.
    - Puede ampliar la funcionalidad a través de formularios, tablas, métodos e interfaces de programación de aplicaciones (API).
    - Puede crear y ampliar entidades.

    Para obtener más información sobre las opciones de extensión disponibles, consulte [Descripción general de la extensibilidad en Dynamics 365](../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md).

- [Crear un conjunto de capacidades de recursos humanos en Dynamics 365.](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/create-one-set-human-resources-capabilities-within-dynamics-365)

    En la versión 10.0.25, las capacidades funcionales que existían solo en Human Resources ahora están disponibles en la infraestructura de Finanzas y Operaciones. Para que los clientes aprovechen estas capacidades en un entorno de Finanzas y Operaciones, las siguientes funciones de Human Resources deben estar habilitadas en la Administración de características.

    | Nombre de característica | Información general | Estado de liberación | 
    |--------------|----------|----------------| 
    | Cálculo de años de servicio | Una opción de configuración le permite seleccionar la fecha que se utiliza para el cálculo de **Años de servicio**. | Disponibilidad general | 
    | Mejoras de experiencia de flujo de trabajo | Esta característica proporciona una experiencia de usuario mejorada para envíos y aprobaciones de flujos de trabajo. | Disponibilidad general | 
    | Imprimir revisiones del rendimiento | Puede imprimir evaluaciones de rendimiento en formato PDF. | Disponibilidad general | 
    | Vínculos personalizados en **Autoservicio para directores** | Puede crear vínculos personalizados que aparecen en la sección **Vínculos relacionados** de **Autoservicio para directores**. | Disponibilidad general | 
    | Vista de compensación entre empresas | Los usuarios pueden ver los planes de compensación en **Autoservicio para directores** en todas las entidades jurídicas sin tener que cambiar de compañía. | Disponibilidad general | 
    | Configurar varios niveles de compensación por trabajo\*&dagger; | Ahora los trabajos admiten varios niveles de compensación. | Versión preliminar | 
    | Administración de tareas\* | Puede crear listas de verificación y tareas para el proceso de incorporación, baja y transición. | Versión preliminar | 
    | Entrada de empleados optimizada | Esta característica proporciona una experiencia de usuario actualizada en la página **Trabajador** existente. | Versión preliminar | 
    | Mejoras en la experiencia de usuario en departamentos de Recursos Humanos | Consulte la tabla en la siguiente sección.  | Versión preliminar | 

\* Esta característica debe activarse antes de la característica **Mejoras en la experiencia del usuario de recursos humanos**.

&dagger; Esta característica no se pueden deshabilitar tras habilitarla.

## <a name="human-resource-user-experience-enhancements"></a>Mejoras en la experiencia del usuario de recursos humanos

| Nombre de característica | Información general | 
|--------------|----------| 
| Eliminar empleo | Puede eliminar un empleo de un empleado. | 
| Familias de trabajos | Puede hacer un seguimiento de un grupo de trabajos que implican un trabajo similar y que requieren capacitación, habilidades, conocimientos y experiencia similares. | 
| Campos de empleo adicionales | Se agregaron los siguientes campos: **Categoría de empleo**, **Tipo de empleo** y **Estado del empleo**. | 
| Página **Trabajadores sin empleo** | Una página muestra una lista de trabajadores que no tienen un registro de empleo. | 
| Actualización de la experiencia del usuario de la dimensión de posición | Hay una experiencia de usuario mejorada para asignar dimensiones de posición por entidad jurídica. | 
| Encargarse de los cambios en el espacio de trabajo **Administración de personal** | Esta característica proporciona un recuento de todos los cambios de dirección que ocurrieron durante un número específico de días que se especifica en la página **Parámetros de recursos humanos**. | 
| Registros que caducan en el espacio de trabajo **Administración de personal** | Esta característica proporciona una lista de elementos que han caducado o que van a caducar para certificados, identificaciones, periodos de prueba, evaluaciones o pruebas. | 
| Página **Validación de la jerarquía de puestos** | Se realiza una comprobación de referencias circulares en la jerarquía de líneas de posición. | 
| Información de nómina específica del país | Los campos de nómina adicionales están disponibles en la página **Empleo del trabajador** según el país o región de la entidad jurídica donde están empleados los trabajadores. | 
| Mejoras en los informes de cumplimiento | Hay opciones de informes adicionales disponibles para EEO-1, Vets 4212 y OSHA300a. | 
| Actualizaciones del espacio de trabajo **Administración de personal** | Se han llevado a cabo actualizaciones para realizar un seguimiento de los cambios de dirección y los registros que caducan. Además, las nuevas pestañas enumeran las acciones de los trabajadores y los puestos. | 
