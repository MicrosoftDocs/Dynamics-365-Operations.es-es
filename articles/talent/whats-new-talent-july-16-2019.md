---
title: Novedades o cambios en Dynamics 365 Talent (16 de julio de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 07/16/2019
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
ms.search.validFrom: 2019-07-16
ms.dyn365.ops.version: Talent
ms.openlocfilehash: cd7f288e5c1015f4266db527adfcd62a5dbbc95f
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528109"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-july-16-2019"></a>Novedades o cambios en Dynamics 365 Talent (16 de julio de 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Cambios en Attract
Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Attract.

### <a name="coming-soon-in-attract"></a>Muy pronto en Attract
#### <a name="job-approvals-appear-on-the-home-page"></a>Aprobaciones de trabajos que aparecen en la página principal

Las Aprobaciones aparecen en una sección **Aprobaciones** en el panel de información. Los aprobadores pueden revisar sus aprobaciones en **Asignada a usted**, que muestra el id. de trabajo, el cargo, otros aprobadores y la fecha en la que se asignó el trabajo. Los usuarios que envían un trabajo para su aprobación pueden revisar los trabajos en **Solicitado por usted**, que muestra los aprobadores que aún deben aprobar el trabajo enviado.

## <a name="changes-in-onboard"></a>Cambios en Onboard
Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Cambios en Core HR
Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2390.

### <a name="common-data-service-entities-that-now-support-custom-fields"></a>Entidades de Common Data Service que ahora admiten campos personalizados

- BusinessProcessCalendar                     
- BusinessProcessGroupAssignment         
- BusinessProcessStage                          
- BusinessProcessTemplateHeader          
- BusinessProcessTemplateTask            
- HcmBenefitOption                              
- HcmBenefitType                                  
- HcmCompensationGrid                            
- HcmCompensationLevel                          
- HcmCompensationPayFrequency                 
- HcmCompensationReferencePointSetup        
- HcmCompensationReferencePointSetupLine 
- HcmCompensationRegion                     
- HcmCompFixedPlanTable                     
- HcmEmployment                                
- HcmEthnicOrigin                                
- HcmFixedCompensationEvent                 
- HcmJob                                           
- HcmJobFunction
- HcmJobType
- HcmLanguageCode
- HcmPayrollCalculationFrequency
- HcmPosition
- HcmPositionType
- HcmSkillType
- HcmVeteranStatus
- HcmWorkCalendarHoliday
- HcmWorkCalendarHolidayLine
- HcmWorker
- HcmWorkerPersonalDetail
- LeaveType
- OMDepartment
- OMLegalEntity
- PayCycle
- PayPeriod
- PayrollBenefitCalculationRate
- PayrollBenefitCalculationRateDetail
- PayrollEarningCode

### <a name="unable-to-see-goals-and-reviews-in-manager-self-service"></a>No se pueden ver los objetivos y las revisiones en autoservicio de administrador

Los cambios de esta semana ahora permiten mostrar y editar objetivos y revisiones para los administradores de nivel de omisión en autoservicio de administrador.

### <a name="goal-form-cannot-be-closed-after-a-user-edits-any-goal-field"></a>El formulario del objetivo no puede cerrarse después de que un usuario edite cualquier campo del objetivo

Este lanzamiento corrige un problema donde el formulario de objetivo no se cerraba al seleccionar **Cerrar**.

### <a name="creating-new-goals-and-saving-displays-error"></a>Creación de nuevos objetivos y guardar visualizaciones de pantalla

Este lanzamiento corrige un problema al guardar objetivos en autoservicio de empleado y director.

### <a name="unable-to-add-a-field-to-position-details"></a>No se puede agregar un campo a los detalles del puesto 

Con esta versión, los campos personalizados son ahora admitidos en los detalles del puesto de trabajo.
 
### <a name="unable-to-set-up-expiring-date-on-the-earning-code-through-data-management"></a>No se puede configurar la fecha de caducidad en el código de ganancia a través de la gestión de datos

Los cambios ahora permiten establecer fechas de vencimiento en los códigos de ganancias en la administración de datos.

### <a name="new-custom-fields-dont-sync-quickly-enough"></a>Los nuevos campos personalizados no se sincronizan con la velocidad suficiente

El rendimiento de la sincronización de campos personalizados con Common Data Service ha mejorado con el lanzamiento de esta semana.

### <a name="entity-export-to-database-jobs-fail-with-error-message-format-of-the-initialization-string-does-not-conform-to-specification-starting-at-index-0"></a>Error de exportación de la entidad a los trabajos de la base de datos con el mensaje de error: "El formato de la cadena de inicialización no se ajusta a la especificación que comienza con el índice 0.”

Este lanzamiento corrige el problema en la están fallando los trabajos por lotes de la base de datos. Para actualizar manualmente:

1. Vaya a **Administración de datos**.
2. Seleccione **Configurar exportación de entidad a la base de datos**.
3. Vuelva a escribir la cadena de conexión a la base de datos de destino y seleccione **Guardar**.

### <a name="smtp-email-configuration-suddenly-fails-with-error-message-the-smtp-server-requires-a-secure-connection-or-the-client-was-not-authenticated"></a>Error repentino de la configuración de correo electrónico de SMTP con el mensaje de error: “El servidor SMTP requiere una conexión segura o el cliente no se autenticó”.

Este lanzamiento corrige una configuración de correo electrónico de SMTP que genera un error repentinamente. Para actualizar manualmente:

1. Vaya a **Administración del sistema**.
2. Seleccione **parámetros de correo electrónico**.
3. Seleccione **Configuración de SMTP**. 
4. Vuelva a escribir el nombre de usuario y la contraseña utilizados para el servidor SMTP y seleccione **Guardar**.

## <a name="in-preview"></a>En vista previa

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Las características de la vista previa solo están habilitado en instancias de espacio aislado

Al aprovisionar una nueva instancia de Talent, puede especificar si el tipo de instancia es **Producción** o **Espacio aislado**. Las instancias del tipo **Espacio aislado** permiten la prueba temprana de nuevas características. Todas las instancias existentes de Talent se actualizarán el tipo de instancia de **Producción**. Si desea que una de las instancias existentes se actualicen al tipo de instancia de **Espacio aislado**, contacte con el [Soporte](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) para iniciar la solicitud de cambio.

Para obtener más información sobre cómo se publican los cambios, consulte [Aprovisionar Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="restrict-leave-types-in-time-off-requests"></a>Limitar los tipos de baja en las solicitudes de tiempo de indisponibilidad

Las organizaciones pueden proporcionar muchos tipos diferentes de bajas a los empleados. Sin embargo, puede que no sea adecuado que los empleados envíen solicitudes de tiempo de indisponibilidad para algunos tipos de baja. En su lugar, RR. HH. puede administrar estos tipos de baja. En esta versión, puede configurar qué tipos de baja permiten que los empleados pueden enviar solicitudes de tiempo de indisponibilidad. 

### <a name="view-performance-information-for-direct-and-extended-reports-in-manager-self-service"></a>Ver la información de rendimiento para los informes directos y ampliados en autoservicio para directores

Una nueva opción permitirá a los directores ver el rendimiento tanto de los informes directos como de sus informes ampliados. Actualmente, los administradores de línea pueden asignar y actualizar objetivos de rendimiento y emitir nuevos revisiones. Además, los administradores directos y sus empleados pueden mantener y actualizar diarios de rendimiento a fin de garantizar que el proceso de evaluación del rendimiento se desarrolla correctamente. Cuando se implementa este cambio, los administradores podrán ver y mantener la información relacionada con el rendimiento en los informes ampliados además de sus informes directos.
