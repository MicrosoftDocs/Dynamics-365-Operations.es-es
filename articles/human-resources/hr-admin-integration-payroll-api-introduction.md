---
title: Introducción a la API de integración de nóminas
description: Este tema describe la API de integración de nóminas de Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 61b90c566325bb8d83b09fceebc721cfb14d3fc8
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891135"
---
# <a name="payroll-integration-api-introduction"></a>Introducción a la API de integración de nóminas

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este documento describe la API de integración de nóminas de Dynamics 365 Human Resources. La API permite integraciones optimizadas de un extremo a otro entre los recursos humanos y los sistemas de nómina asociados. La experiencia integrada comienza en Recursos Humanos con el perfil del empleado, salario y deducción e información de cotización. Cuando contrata a un empleado e ingresa el perfil requerido y la información de pago en Recursos Humanos, el sistema de nómina extrae esta información para usarla al procesar la nómina. Cualquier actualización realizada al empleado o la información de pago también se extrae para su uso en ejecuciones de pago posteriores.

![Flujo de integración de nóminas](media/hr-admin-integration-payroll-api-introduction-flow.png)

Para habilitar la integración, Recursos Humanos incluye los siguientes componentes:

- Funcionalidad para marcar a un empleado como listo para pagar
- Una API de integración que abre la nueva funcionalidad para integrar aplicaciones

## <a name="microsoft-dataverse"></a>Microsoft Dataverse

Esta API se basa en Microsoft Dataverse (antes Common Data Service). Toda la interacción RESTful con esta API se realiza a través de la API web Microsoft Dataverse, que utiliza OData. Esta API es un subconjunto de la API web de Dataverse. La API web de Dataverse define características como autenticación, SLA, lotes, control de concurrencia y manejo de errores.

Para obtener más información general acerca de la API web de Microsoft Dataverse, consulte:

- [¿Qué es Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)
- [Utilizar la API web de Microsoft Dataverse](/powerapps/developer/data-platform/webapi/overview)
- [Guía de desarrollador de Microsoft Dataverse](/powerapps/developer/data-platform)

Esta documentación incluye detalles y orientación para desarrolladores sobre el uso de la API web de Dataverse, incluidos los siguientes temas:

- [Autenticarse en Microsoft Dataverse con la API web](/powerapps/developer/data-platform/webapi/authenticate-web-api)
- [Realizar operaciones usando la API web](/powerapps/developer/data-platform/webapi/perform-operations-web-api)
- [Utilice Postman con la API web](/powerapps/developer/data-platform/webapi/use-postman-web-api)
- [Utilice el seguimiento de cambios para sincronizar datos con sistemas externos](/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems)

### <a name="virtual-tables-for-human-resources-in-dataverse"></a>Tablas virtuales para Recursos Humanos en Dataverse

Los puntos de conexión de la API de integración de nóminas utilizan las capacidades de la plataforma de tabla virtual de Microsoft Dataverse. De forma predeterminada, las tablas virtuales y sus puntos de conexión de API asociados no se implementan para entornos de Recursos Humanos, lo que permite a las organizaciones determinar qué punto de conexión estarán expuestos para el entorno. Para utilizar la API, se deben generar las tablas virtuales para las entidades de Recursos Humanos para el entorno.

Para obtener información sobre la generación de tablas virtuales para la API, consulte [Configurar tablas virtuales de Dataverse](./hr-admin-integration-common-data-service-virtual-entities.md).

## <a name="data-model"></a>Modelo de datos

El siguiente diagrama ilustra las relaciones dentro de la API. Diversos tipos tienen claves extranjeras para otras entidades preexistentes en Recursos Humanos que no se ilustran aquí. Este documento proporciona información sobre las entidades específicas para los escenarios de integración de nóminas. Sin embargo, hay muchas otras entidades en la API web de Dataverse para Human Resources que también pueden ser relevantes para su integración. Algunas de estas entidades están referenciadas en relaciones de clave externa o propiedades de navegación.

![Modelo de datos de API de integración de nóminas](media/hr-admin-payroll-api-data-model.png)

## <a name="payroll-employee-and-related-entities"></a>Empleado de nómina y entidades relacionadas

Entidades:

- [Empleado con nómina](hr-admin-integration-payroll-api-payroll-employee.md)
- [Dirección del trabajador de la nómina](hr-admin-integration-payroll-api-payroll-worker-address.md)
- [Plan de compensación fija con nómina](hr-admin-integration-ats-api-recruiting-request-education.md)
- [Trabajo de puesto de nómina](hr-admin-integration-payroll-api-payroll-position-job.md)
- [Puesto de nómina](hr-admin-integration-payroll-api-payroll-position.md)

## <a name="see-also"></a>Consulte también

[Generar y revisar entidades de nómina](hr-admin-integration-payroll-api-generate-review-entities.md)<br>
[Configurar parámetros de Human Resources](hr-setup-parameters.md)<br>
[Configurar parámetros compartidos de Human Resources](hr-setup-shared-parameters.md)<br>
[¿Qué es Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Utilizar la API web de Microsoft Dataverse](/powerapps/developer/data-platform/webapi/overview)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]