---
title: Novedades o cambios en Dynamics 365 Talent (9 de julio de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 07/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-07-09
ms.dyn365.ops.version: Talent
ms.openlocfilehash: feb39966d98fa7bde9a6bfad26b07fbd224da59b
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528048"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-july-9-2019"></a>Novedades o cambios en Dynamics 365 Talent (9 de julio de 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Cambios en Attract

Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Attract.

### <a name="coming-soon-in-attract"></a>Muy pronto en Attract

#### <a name="job-approvals-appear-on-the-home-page"></a>Aprobaciones de trabajos que aparecen en la página principal

Las Aprobaciones aparecen en una sección **Aprobaciones** en el panel de información. Los aprobadores pueden revisar sus aprobaciones en **Asignada a usted**, que muestra el id. de trabajo, el cargo, otros aprobadores y la fecha en la que se asignó el trabajo. Los usuarios que envían un trabajo para su aprobación pueden revisar los trabajos en **Solicitado por usted**, que muestra los aprobadores que aún deben aprobar el trabajo enviado.

## <a name="changes-in-onboard"></a>Cambios en Onboard

Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Cambios en Core HR

Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2374.

### <a name="platform-update-28-for-finance-and-operations"></a>Platform update 28 para Finance and Operations

Para obtener más información acerca de la Platform update 28 para Finance and Operations, consulte [Características de vista previa en Dynamics 365 Finance and Operations platform update 28 (julio de 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-28).

### <a name="entity-support-for-custom-fields-in-common-data-service"></a>Soporte de entidad para campos personalizados en Common Data Service 

Las entidades siguientes admiten campos personalizados: 

- **Plan de compensación fija**
- **Configurar puntos de referencia de compensación**
- **Línea de configuración de puntos de referencia de compensación**
- **Código de ganancia de nómina**
- **Período de pago**
- **Evento de compensación fija**
- **Cuadrícula de compensación**

Para ver todas las entidades actualizadas en Talent:

1. Seleccione **Administración del sistema**, seleccione **Vínculos**, y después seleccione **Configuración de Common Data Service**.
2. Seleccione el menú desplegable **Nombre de entidad de CDS**. Todas las entidades enumeradas se encuentran en la última versión. 

###  <a name="full-name-added-to-worker-entity-in-common-data-service"></a>Nombre completo agregado a la entidad del trabajador en Common Data Service

El campo **Nombre completo** se ha agregado a la entidad **Trabajador**.

### <a name="full-time-equivalent-higher-than-10"></a>Equivalente a jornada completa más alto de 1.0

Una advertencia muestra ahora si un valor superior a 1.0 se especifica para un empleado a tiempo completo en un puesto. 

### <a name="a-warning-no-longer-displays-on-the-worker-page-when-there-is-no-future-dated-employment"></a>Una advertencia ya no se muestra en la página del trabajador cuando no hay empleo con fecha en el futuro

Ya no recibirá un mensaje que indique que existe un empleo futuro al navegar a la página **Trabajador** de la lista **Empleados que salen** en el espacio de trabajo **Administración de personal**. 

### <a name="unable-to-delete-a-business-process-in-talent"></a>No se puede eliminar un proceso empresarial en Talent

Ahora puede eliminar procesos empresariales en el espacio de trabajo **Proceso empresarial**.

### <a name="leave-balance-no-longer-displays-zero-for-plans-with-no-accruals-when-using-balance-as-of-accrual-period"></a>El saldo de licencia ya no muestra cero para los planes sin acumulaciones al utilizar el saldo a partir de período de acumulación

Los planes que se configuran sin acumulaciones ahora podrán mostrar un saldo.

## <a name="in-preview"></a>En vista previa

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Las características de la vista previa solo están habilitado en instancias de espacio aislado

Al aprovisionar una nueva instancia de Talent, puede especificar si el tipo de instancia es **Producción** o **Espacio aislado**. Las instancias del tipo **Espacio aislado** permiten la prueba temprana de nuevas características. Todas las instancias existentes de Talent se actualizarán el tipo de instancia de **Producción**. Si desea que una de las instancias existentes se actualicen al tipo de instancia de **Espacio aislado**, contacte con el [Soporte](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) para iniciar la solicitud de cambio.

Para obtener más información sobre cómo se publican los cambios, consulte [Aprovisionar Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="restrict-leave-types-in-time-off-requests"></a>Limitar los tipos de baja en las solicitudes de tiempo de indisponibilidad

Las organizaciones pueden proporcionar muchos tipos diferentes de bajas a los empleados. Sin embargo, puede que no sea adecuado que los empleados envíen solicitudes de tiempo de indisponibilidad para algunos tipos de baja. En su lugar, RR. HH. puede administrar estos tipos de baja. En esta versión, puede configurar qué tipos de baja permiten que los empleados pueden enviar solicitudes de tiempo de indisponibilidad. 

## <a name="coming-soon-in-core-hr"></a>Próximamente en Core HR

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Ver información ampliada para el rendimiento en autoservicio para directores

Una nueva opción permitirá a los directores ver el rendimiento tanto de los informes directos como de sus informes ampliados. Actualmente, los administradores de línea pueden asignar y actualizar objetivos de rendimiento y emitir nuevos revisiones, que sus empleados gestionan en conjunto. Además, los administradores directos y sus empleados pueden mantener y actualizar diarios de rendimiento a fin de garantizar que el proceso de evaluación del rendimiento se desarrolla correctamente. Cuando se implementa este cambio, los administradores podrán ver y mantener la información relacionada con el rendimiento en los informes ampliados además de sus informes directos. 

### <a name="entities-supporting-custom-fields"></a>Entidades que admiten campos personalizados

Se habilitarán las entidades siguientes para los campos personalizados en Common Data Service: 

- **Tipo de baja**
- **Cuenta bancaria del trabajador**
- **Calendario de trabajo**
