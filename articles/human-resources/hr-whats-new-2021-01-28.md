---
title: Novedades y cambios en Dynamics 365 Human Resources del 28 de enero de 2021
description: Este tema describe las características nuevas o modificadas en Microsoft Dynamics 365 Human Resources para el 28 de julio de 2021.
author: marcelbf
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 36509cc5663073fd1e3b7f41a600c7816bfbdff6
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791254"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-january-28-2021"></a>Novedades y cambios en Dynamics 365 Human Resources del 28 de enero de 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe las características que son nuevas, han cambiado o estarán disponibles próximamente en Dynamics 365 Human Resources.

Para obtener más información sobre el proceso de actualización y la programación, consulte [Proceso de actualización](hr-admin-setup-update-process.md).

Para obtener más información sobre las nuevas características y sus fechas de disponibilidad general previstas, consulte [Visión general del primer lanzamiento de versiones de Dynamics 365 Human Resources en 2021](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>En este lanzamiento

Esta versión incluye las características nuevas y correcciones de errores siguientes. Los cambios se aplican al número de compilación 8.1.3906.

### <a name="new-features"></a>Nuevas características

Las siguientes características estarán disponible de forma generalizada en esta versión.

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Integrar códigos de motivo de prestaciones en el espacio de trabajo **Administración de personal** | -- | [Configurar códigos de motivos](hr-benefits-setup-reason-codes.md) |

### <a name="bug-fixes"></a>Correcciones de errores

En esta versión se incluyen las siguientes correcciones de errores.

> [!NOTE]
> Nuestro objetivo es hacer llegar esta información lo antes posible. Puede que haya actualizaciones de este tema para incluir correcciones de errores que se incluyeron en la compilación después de la publicación inicial del tema.


| Número del problema | Emitir |  Descripción |
| --- | --- | --- |
| 539456 | El calendario muestra el tipo de licencia en texto flotante cuando el parámetro **Mostrar solo ausencia sin detalles** está habilitado. | Cuando la opción **Mostrar solo ausencia sin detalles** está habilitada, la fecha de la solicitud se muestra al pasar el mouse. |
| 528907 | Otorgar acceso a una entidad jurídica en el rol de empleado da como resultado que los responsables no puedan ver la actividad del saldo de licencias para los empleados en el área **Mi equipo** del autoservicio de empleados. |Ahora, establecer esta opción permite a los responsables seguir viendo la actividad del saldo de licencias. |
| 526280 | Error de permisos en HcmWorkerEntity, HcmEmployeeEntity y HcmContractorEntity. | Los usuarios que no tenían una función de administrador del sistema no podían exportar las entidades enumeradas a causa de un error de permisos en el campo NationalityCountryRegion. Los usuarios seguirán necesitando los siguientes privilegios para exportar esta información: HcmWorkerEntityMaintain, HcmWorkerEntityView, HcmEmployeeEntityMaintain, HcmEmployeeEntityMaintain, HcmEmployeeEntityView, HcmContractorEntityMaintain y HCMContractorEntityView. |
| 542147 | Los campos **Número de cuenta bancaria** y **Número de ruta** son obligatorios al agregar una cuenta bancaria a través del autoservicio para empleados. | Hemos corregido el error por el que los empleados debían introducir los campos **Número de cuenta bancaria** y **Número de ruta** al agregar los detalles de la cuenta bancaria. Estos campos ya no son obligatorios al guardar nueva información de cuenta bancaria. |
| 543641 | El código postal no se completa en los informes electrónicos. | Se corrigió un error por que hacía que el código postal no se rellenara en el informe de ACA para los códigos de cobertura de L a Q. |
| 545402 | Agregue un cambio de ruta al archivo UserBranding.js para eliminar los errores 404. | El usuario ya no debería ver errores 404 en la consola. |

## <a name="in-preview"></a>En vista previa   

La siguientes características nuevas se incluyen como versión preliminar. Para obtener más información acerca cómo activar o desactivar características, consulte [Administrar características](hr-admin-manage-features.md).

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Aplicación Human Resources en Microsoft Teams | [Experiencia de bajas y ausencias de empleados en Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Aplicación Human Resources en Teams](https://go.microsoft.com/fwlink/?linkid=2127841)<br>[Administrar solicitudes de bajas en Teams](hr-teams-leave-app.md) |
| Visión transversal de la licencia para responsables | [Visión transversal de la licencia de empleado para responsables](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Configurar parámetros de bajas y ausencias](https://docs.microsoft.com/dynamics365/human-resources/hr-leave-and-absence-parameters) |

## <a name="coming-soon"></a>Próximamente

| Característica | Detalles |
| --- | --- |
| Confirmación por correo electrónico para inscripción en prestaciones | Esta característica proporcionará la opción de enviar un correo electrónico de confirmación a los empleados cuando comprueben las experiencia de inscripción de prestaciones en el autoservicio para empleados. Esta característica estará disponible el 1 de febrero. Para obtener más información, consulte [Configurar parámetros de Administración de prestaciones por empresa](hr-benefits-setup-parameters-per-company.md). |
| Las aptitudes introducidas por un director para sus empleados se pueden aprobar automáticamente mediante un flujo de trabajo | Próximamente. |

Para obtener una lista completa de las características previstas y sus lanzamientos programados, consulte [Visión general del primer lanzamiento de versiones de Dynamics 365 Human Resources en 2021](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="terminology-updates-for-microsoft-dataverse"></a>Actualizaciones de terminología para Microsoft Dataverse

Desde noviembre de 2020, el nombre de Common Data Service pasa a ser [Microsoft Dataverse](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro). Vea el [anuncio oficial](https://powerapps.microsoft.com/blog/reshape-the-future-of-work-with-microsoft-dataverse-for-teams-now-generally-available/) en el blog de Power Apps para obtener más información. Además de este cambio de nombre, se ha actualizado parte de la terminología de Dataverse. Por ejemplo, *entidad* es ahora *tabla* y *campo* es ahora *columna*. Para más información, consulte [Actualizaciones de terminología](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro#terminology-updates).

En esta versión, se ha actualizado la terminología relacionada con la integración de Dynamics 365 Human Resources con Dataverse en toda la aplicación para reflejar estos cambios. Por ejemplo, el formulario **Integración de Common Data Service** es ahora **Integración de Microsoft Dataverse**.

Para obtener más información sobre la integración de Dynamics 365 Human Resources con Microsoft Dataverse, consulte [Configurar la integración de Microsoft Dataverse](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service) y [Configurar las tablas virtuales de Microsoft Dataverse](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general del primer lanzamiento de versiones de Dynamics 365 Human Resources en 2021](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]