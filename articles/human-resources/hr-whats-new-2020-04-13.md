---
title: Novedades y cambios en Dynamics 365 Human Resources (13 de abril de 2020)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 13 de abril de 2020.
author: andreabichsel
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-04-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d9219e3f2da4d398ed7e8bb27337835d42403925
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8692818"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-13-2020"></a>Novedades y cambios en Dynamics 365 Human Resources (13 de abril de 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Este artículo describe las características que son nuevas o que se han cambiado en Dynamics 365 Human Resources. Los cambios se aplican al número de compilación 8.1.3136. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en (LCS) para su referencia.

## <a name="new-production-release-cadence"></a>Nueva cadencia de lanzamiento de producción

Con la versión de esta semana, la cadencia de lanzamiento de Human Resources cambia de una actualización semanal a una actualización quincenal. Para garantizar la alineación con prácticas de implementación seguras y mantener altos estándares de estabilidad y fiabilidad en el servicio, el proceso de implementación de actualizaciones del servicio en todas las regiones es ahora una implementación de dos semanas. Pruebas y supervisiones adicionales verifican la implementación exitosa en cada etapa del proceso. Para obtener más información sobre la cadencia de lanzamiento, vea [Proceso de actualización](hr-admin-setup-update-process.md).

## <a name="rounding-precision-field-isnt-editable-after-specifying-a-rounding-type-435616"></a>El campo de precisión de redondeo no se puede editar después de especificar un tipo de redondeo (435616)

Con este cambio, el campo **Precisión de redondeo** ahora está disponible después de actualizar el campo **Tipo de redondeo**.

## <a name="cant-edit-leave-enrollment-end-date-when-the-leave-plan-doesnt-have-accrual-periods-413628"></a>No se puede editar la fecha de finalización de la inscripción de licencia cuando el plan de licencia no tiene períodos de acumulación (413628)

Ahora puede editar la fecha de finalización de la inscripción sin obtener el error "Se debe completar la base de la fecha de acumulación de campo".

## <a name="employment-entity-doesnt-sync-to-dataverse-430834"></a>La entidad de empleo no se sincroniza con Dataverse (430834)

Este cambio corrige un problema en el que los datos de empleo no se sincronizaban con Dataverse después de agregar dimensiones financieras. 

## <a name="remove-multi-parenting-for-work-calendar-time-interval-entity-431775"></a>Eliminar la crianza múltiple para la entidad de intervalo de tiempo del calendario laboral (431775)

Este cambio elimina la crianza múltiple para la entidad de **Intervalo de tiempo del calendario laboral**.

## <a name="filter-with-cast-function-doesnt-work-on-odata-call-position-worker-assignment-entity-431699"></a>El filtro con función CAST no funciona en la llamada de OData a la entidad Asignar puesto de trabajador (431699)

Esta actualización incluye un cambio para permitir el filtro con la función CAST dentro de OData para la entidad **Asignar puesto de trabajador**.

## <a name="in-preview"></a>En vista previa

## <a name="leave-suspension"></a>Dejar suspensión

Puede suspender la baja y la ausencia en Human Resources para un empleado. La suspensión de la baja detiene las acumulaciones de baja para los tipos de baja seleccionados. Si la suspensión ocurre después de que se ha procesado una acumulación, la suspensión de la licencia crea un ajuste prorrateado al saldo de licencia del empleado. Para obtener más información, consulte [Suspender baja](hr-leave-and-absence-suspend-leave.md).

## <a name="carry-forward-rules"></a>Transferir reglas

Puede especificar un tipo de transferencia de baja para transferir saldos en los que los ajustes de transferencia se traspasan. Por ejemplo, si un empleado adelanta 10 días, puede elegir un tipo de baja diferente para esos 10 días. Para más información, ver [Configurar tipos de baja y ausencia](hr-leave-and-absence-types.md).

## <a name="known-issues"></a>Problemas conocidos

## <a name="employment-details-entity"></a>Entidad Detalles de empleo

La entidad **Detalles de empleo** ha sido actualizada con los siguientes campos:

- **Frecuencia de pago**
- **Id. de categoría laboral**
- **Tipo de empleo**
- **Id. de tipo de empleo**
- **Estado de la prestación de empleo**

Los datos de configuración para estos campos dependen de que la gestión de prestaciones esté habilitada en el espacio de trabajo **Gestión de funciones**. No complete ni actualice estos campos en la entidad **Detalle de empleo**, porque provocará errores durante la importación.

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>La vista previa SharePoint no funciona en algunos entornos

Si la vista previa del documento para documentos almacenados en SharePoint no funciona, intente el siguiente procedimiento:

1. Verifique que la cuenta de usuario administrador tenga un correo electrónico asociado con el registro de usuario. Puede ver esta información en la página **Usuario**. Si el correo electrónico no está configurado, debe agregar el correo electrónico y el proveedor con el complemento OData Excel. Por defecto, la dirección de correo electrónico no está presente en el diseño de Excel. Deberá editar el diseño de Excel, agregar todos los campos, aplicar y actualizar. Una vez que haya completado esos pasos, puede actualizar la cuenta de administrador.

2. Una vez que la cuenta de administrador tenga una cuenta de correo electrónico asociada, inicie sesión en Human Resources con credenciales de administrador.

3. Acceda a un archivo adjunto en SharePoint para comenzar la vista previa del documento.

4. Inicie sesión con otra cuenta de usuario que tenga acceso a los archivos adjuntos y verifique que la vista previa funcione como se esperaba.

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]