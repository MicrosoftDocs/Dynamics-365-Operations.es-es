---
title: Preguntas frecuentes sobre la publicación
description: Este tema enumera las preguntas frecuentes sobre cómo poner en marcha un proyecto de implementación de Dynamics 365 Human Resources.
author: rachel-profitt
manager: tfehr
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cbf00f7428c9b1852a5bf54fd7e30a3bddc1a31e
ms.sourcegitcommit: 0e60df840688932795b9c8f8fd45d98f5ab6ba8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668954"
---
# <a name="go-live-faq"></a>Preguntas frecuentes sobre la publicación 

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema enumera las preguntas frecuentes sobre cómo poner en marcha un proyecto de implementación de Dynamics 365 Human Resources. 

## <a name="when-can-i-configure-and-request-my-production-environment"></a>¿Cuándo puedo configurar y solicitar mi entorno de producción? 

Normalmente, un entorno de producción se implementa cuando cumple con los siguientes criterios:

- Se ha completado el código de todas las personalizaciones.
- Se ha completado la prueba de aceptación de usuarios (UAT).
- El cliente ha aprobado la solución.
- No hay problemas que impidan la puesta en marcha. 

Cuando los clientes cualificados se encuentren en esta etapa, el equipo de Microsoft FastTrack trabajará con el equipo del proyecto para realizar una evaluación de puesta en marcha. 

## <a name="what-are-the-prerequisites-to-deploying-a-production-environment"></a>¿Cuáles son los requisitos previos para implementar un entorno de producción? 

Para obtener una lista de requisitos previos, consulte [Prepararse para la puesta en marcha](hr-admin-go-live-prepare.md). 

## <a name="what-is-a-go-live-assessment"></a>¿Qué es una evaluación de puesta en marcha?  

La evaluación de puesta en marcha es parte del [programa Microsoft FastTrack](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/fasttrack-dynamics-365-overview). Durante esta revisión, un arquitecto de soluciones evalúa si un proyecto de implementación está listo para su transferencia y puesta en marcha. Esta revisión es obligatoria para todos los proyectos de implementación para los que se quiera solicitar la puesta en marcha en un entorno de producción. 

## <a name="our-sandbox-environments-are-deployed-in-the-central-us-datacenter-we-want-our-production-environments-to-be-deployed-in-the-west-us-datacenter-can-i-select-west-us-as-the-datacenter-in-my-production-configuration"></a>Nuestros entornos de espacio aislado se implementan en el centro de datos de EE. UU. Central. Queremos que nuestros entornos de producción se implementen en el centro de datos del Oeste de EE. UU. ¿Puedo seleccionar el Este de EE. UU. como centro de datos en mi configuración de producción? 

LCS no le impide seleccionar un centro de datos diferente al implementar un entorno de Recursos Humanos, pero le recomendamos encarecidamente que no seleccione un centro de datos diferente.  

Si desea que su entorno de producción esté en el centro de datos del Oeste de EE. UU., primero debe volver a implementar sus entornos de espacio aislado en el centro de datos del Oeste de EE. UU., probarlos y aprobarlos. 

Para obtener información sobre cómo seleccionar el centro de datos correcto, consulte [Requisitos de red](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/system-requirements#network-requirements). 

## <a name="what-level-of-access-do-i-have-to-the-azure-resources-for-my-human-resources-environments"></a>¿Qué nivel de acceso tengo a los recursos de Azure para mis entornos de Human Resources?  

El acceso a los entornos de Human Resources es limitado. No puede acceder a la máquina virtual (VM) ni a Microsoft Internet Information Services (IIS). Tampoco puede acceder a la base de datos a través de Microsoft SQL Server Management Studio. 

Aunque no puede se acceder a los recursos de Azure ni al entorno de Dynamics 365 Human Resources directamente, existen otras características que puede utilizar para acceder a sus datos:

- Puede implementar una base de datos de Azure SQL en su propio inquilino de Azure y usar la característica Usar su propia base de datos (BYOD) para sincronizar los datos. Para obtener más información, consulte [Usar su propia base de datos (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database).

- Puedes usar la integración de Common Data Service para sincronizar entidades de selección en la base de datos de Common Data Service. Para obtener más información, consulte [Entidades de Common Data Service](hr-developer-entities.md). 

## <a name="how-often-is-my-production-database-backed-up"></a>¿Con qué frecuencia se realiza una copia de seguridad de mi base de datos de producción? 

Las bases de datos se protegen mediante copias de seguridad automáticas que se realizan con las siguientes frecuencias:

| Tipo de copia de seguridad | Frecuencia |
| --- | --- |
| Copia de seguridad completa de base de datos | Semanal |
| Copia de seguridad diferencia de base de datos | Cada 12-24 horas |
| Copia de seguridad de registro de transacciones | Cada 5-10 minutos |

Microsoft conserva suficientes copias de seguridad para permitir la Restauración a un momento dado (PITR) de los últimos 14 días. 

Para obtener más información sobre copias de seguridad, consulte  [Obtener información sobre las copias de seguridad automáticas de SQL Database](https://docs.microsoft.com/azure/azure-sql/database/automated-backups-overview?tabs=single-database). 

## <a name="can-i-request-a-copy-of-the-backup-of-my-production-database"></a>¿Puedo solicitar una copia de la copia de seguridad de mi base de datos de producción? 

Nº Puede enviar una solicitud de servicio de actualización de base de datos para copiar su entorno de producción en su entorno de espacio aislado. Puede implementar una base de datos de Azure SQL en su propio inquilino de Azure y usar la característica BYOD para sincronizar los datos de su entorno de producción. Para obtener más información, consulte [Usar su propia base de datos (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database). 

## <a name="how-do-i-move-my-sandbox-environment-to-production-for-go-live"></a>¿Cómo paso mi entorno de espacio aislado a producción para la puesta en marcha? 

Como no está disponible una característica de copia para pasar de un entorno de espacio aislado a un entorno de producción, debe usar paquetes de datos para mover datos a su entorno de producción.  

Recomendamos mantener una lista clara de entidades configuradas en el espacio aislado durante todo el proyecto. A continuación, pruebe el proceso de transferencia y migración de los paquetes de datos necesarios para la puesta en marcha. Debe mover manualmente los paquetes de datos al entorno de producción cuando esté listo para la puesta en marcha. 

## <a name="what-should-i-do-if-my-production-environment-is-down"></a>¿Qué hago si mi entorno de producción no funciona? 

Para notificar una interrupción del entorno de producción, siga el proceso descrito en  [Notificar una interrupción de la producción](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/report-production-outage). 

 ## <a name="see-also"></a>Consulte también

 [Prepararse para la publicación](hr-admin-go-live-prepare.md)
