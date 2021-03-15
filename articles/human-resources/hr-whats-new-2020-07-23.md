---
title: Novedades o cambios en Dynamics 365 Human Resources (23 de julio de 2020)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 23 de julio de 2020.
author: andreabichsel
manager: tfehr
ms.date: 07/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-07-23
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f5e10d6d1dedfc251a1a00110b50c9096314d75b
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "5127530"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-23-2020"></a>Novedades o cambios en Dynamics 365 Human Resources (23 de julio de 2020)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Human Resources. Los cambios se aplican al número de compilación 8.1.3416. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en (LCS) para su referencia.

## <a name="deleting-financial-dimensions-on-a-position-doesnt-work-as-expected-445476"></a>Eliminar dimensiones financieras en una posición no funciona como se esperaba (445476)

Eliminar dimensiones de una posición ahora elimina esas mismas posiciones de Dataverse.

## <a name="positions-not-in-hierarchy-show-inactive-positions-397257"></a>Las posiciones que no están en la jerarquía muestran posiciones inactivas (397257)

Las posiciones que están inactivas (tienen una duración expirada), ya no se muestran en la jerarquía de posición como **Posiciones no en jerarquía**. 

## <a name="validation-occurring-between-leaveenrollmententity-and-hcmworkerentity-on-data-management-framework-dmf-import-causes-slow-data-loads-442324"></a>La validación que ocurre entre LeaveEnrollmentEntity y HcmWorkerEntity en la importación del marco de administración de datos (DMF) causa cargas de datos lentas (442324)

Los cambios en esta versión aumentan el rendimiento de **LeaveEnrollmentEntity**.

## <a name="unable-to-personalize-in-organization-administration-447490"></a>No se puede personalizar en la administración de la Organización (447490)

Con este cambio, ahora puede personalizar los enlaces en **Administración de la organización**.

## <a name="in-preview"></a>En vista previa

## <a name="mandatory-fields"></a>Campos obligatorios 

Ahora puede hacer que los campos sean obligatorios utilizando las capacidades de personalización de Human Resources. Esta característica requiere **Vistas guardadas**.

## <a name="human-resources-application-in-teams"></a>Aplicación Human Resources en Teams

Los empleados pueden ver y solicitar tiempo fuera del trabajo en Microsoft Teams. Pueden interactuar con un bot para crear solicitudes de baja. Para más información, consulte [Aplicación de recursos humanos en Teams](https://go.microsoft.com/fwlink/?linkid=2127841). 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>Entidades del marco de gestión de datos (DMF) para la gestión de ventajas
 
Las entidades de gestión de ventajas se están lanzando. Las entidades DMF le permite importar y exportar datos para configurar fácilmente la gestión de ventajas. Una plantilla de gestión de ventajas estará disponible para mover datos. La plantilla exporta e importa los datos de manera secuencial para respetar las dependencias de datos.

## <a name="buy-and-sell-leave"></a>Comprar y vender bajas 

Algunas organizaciones ofrecen un beneficio que permite a los empleados comprar o vender su baja. Este proceso a menudo se gestiona manualmente. Esta característica automatiza las políticas de gestión y las solicitudes del departamento de recursos humanos. Agiliza el proceso de gestión de bajas y ayuda a eliminar errores. Para obtener más información, consulte:

- [Gestionar directivas de compra y venta de bajas](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Comprar y vender bajas](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a>Acumulación de bajas para una sola compañía o plan único

Los clientes pueden procesar las acumulaciones para una sola compañía o un solo plan de bajas y ausencias. Esta capacidad proporciona transparencia para el proceso de acumulación para clientes con diferentes años de baja o directivas de acumulación de bajas. Para más información, consulte [Acumular bajas por empresa o por plan de licencia](hr-leave-and-absence-accrue.md).

## <a name="add-attachments-to-time-off-requests"></a>Agregar archivos adjuntos a las solicitudes de permisos

La capacidad de agregar archivos adjuntos a las solicitudes de baja aprobadas es crítica en el entorno actual de COVID-19. Los empleados ahora pueden agregar estos archivos adjuntos. También tienen más información sobre cómo se realizan las actualizaciones para las solicitudes de baja. Para más información, vea [Agregar un archivo adjunto a una solicitud existente](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).

## <a name="add-reason-code-to-accrual-suspensions"></a>Agregar código de razón a las suspensiones acumuladas 

Se han agregado códigos de motivo a la suspensión acumulada.

## <a name="carry-forward-rules"></a>Transferir reglas 

Puede especificar un tipo de transferencia de baja para transferir saldos en los que los ajustes de transferencia se traspasan. Por ejemplo, si un empleado adelanta 10 días, puede elegir un tipo de baja diferente para esos 10 días. Para más información, ver [Configurar tipos de baja y ausencia](hr-leave-and-absence-types.md).

## <a name="suspend-leave-accrual-for-specified-leave-types"></a>Suspender la acumulación de bajas para los tipos de baja especificados

Puede crear una regla para suspender la acumulación de bajas para empleados con solicitudes de bajas introducidas para bajas no pagadas. La baja no remunerada puede ser un tipo, pero no tiene por qué serlo. Puede suspender cualquier baja basada en otro tipo de baja.

## <a name="dmf-entity-available-for-accrual-suspensions"></a>Entidad DMF disponible para suspensiones acumuladas 

Ahora está disponible una entidad DMF para suspensiones acumuladas.

## <a name="coming-soon"></a>Próximamente

## <a name="checklist-entities-included-in-dataverse"></a>Lista de entidades incluidas en Dataverse

Las entidades de lista de verificación para los procesos Incorporación, Retirada, Transferencias y Empresa estarán disponibles pronto en Dataverse.

## <a name="platform-changes"></a>Cambios de plataforma

Actualización de la plataforma 10.0.12 (36)

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]