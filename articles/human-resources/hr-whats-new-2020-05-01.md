---
title: Novedades y cambios en Dynamics 365 Human Resources (1 de mayo de 2020)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 1 de mayo de 2020.
author: andreabichsel
manager: tfehr
ms.date: 05/01/2020
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
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b7e41762e4283d5a4b0c9dd8359c5fb2bdabfc26
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "5127882"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-1-2020"></a>Novedades y cambios en Dynamics 365 Human Resources (1 de mayo de 2020)

Este artículo describe las características que son nuevas o que se han cambiado en Dynamics 365 Human Resources. Los cambios se aplican al número de compilación 8.1.3196. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en (LCS) para su referencia.

## <a name="new-performance-management-entities-available-in-data-management-framework-dmf"></a>Nuevas entidades de administración de rendimiento disponibles en el marco de gestión de datos (DMF)

Ahora están disponibles las siguientes entidades. Si no ve estas entidades en la lista de entidades, use la opción **Actualizar entidades** en **Parámetros del marco> Configuración de la entidad> Actualizar lista de entidades**.

- **Competencia de tratamiento**
- **Metas de tratamiento**
- **Medida de tratamiento**
- **Tema de tratamiento**
- **Diario de rendimiento**
- **Medida**
- **Medida de metas**

Adicionalmente, se añadieron **Puntuación total** y **Puntuación media** a la entidad **Discusión**.

## <a name="increase-length-of-leave-request-comments-275641"></a>Aumentar la duración de los comentarios de solicitud de baja (275641)

Los comentarios sobre las solicitudes de baja ahora permiten más de 100 caracteres.

## <a name="final-comments-on-reviews-dont-appear-when-the-manager-or-employee-is-signed-into-a-different-company-431688"></a>Los comentarios finales sobre las revisiones no aparecen cuando el gerente o el empleado inician sesión en una empresa diferente (431688)

Todos los comentarios aparecerán ahora al ver las reseñas.

## <a name="user-defined-links-arent-supported-on-new-worker-form-390374"></a>Los enlaces definidos por el usuario no son compatibles con el nuevo formulario Trabajador (390374)

Los enlaces definidos por el usuario ahora están habilitados en el formulario optimizado **Trabajador**.

## <a name="hcmratinglevelentity-causes-odata-api-crash-439476"></a>HcmRatingLevelEntity provoca el bloqueo de la API de OData (439476)

Este cambio corrige el bloqueo de la API. Un nombre duplicado llevaba en sí este error.

## <a name="in-preview"></a>En vista previa

## <a name="leave-suspension"></a>Dejar suspensión

Puede suspender la baja y la ausencia en Human Resources para un empleado. La suspensión de la baja detiene las acumulaciones de baja para los tipos de baja seleccionados. Si la suspensión ocurre después de que se ha procesado una acumulación, la suspensión de la licencia crea un ajuste prorrateado al saldo de licencia del empleado. Para obtener más información, consulte [Suspender baja](hr-leave-and-absence-suspend-leave.md).

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a>Actualizar la experiencia del usuario para indicar que la acumulación está suspendida (429550)

La experiencia del usuario ahora indica que la acumulación se ha suspendido para un plan.

## <a name="suspend-leave-accrual-for-specified-leave-types-272447"></a>Suspender la acumulación de bajas para los tipos de baja especificados (272447)

En este comunicado, RR. HH. puede crear una regla para suspender la acumulación de bajas para empleados con solicitudes de bajas introducidas para bajas no pagadas. La baja no remunerada puede ser un tipo, pero no tiene por qué serlo. Puede suspender cualquier baja basada en otro tipo de baja.

## <a name="dmf-entity-available-for-accrual-suspensions-429549"></a>Entidad DMF disponible para suspensiones acumuladas (429549)

Ahora está disponible una entidad DMF para suspensiones acumuladas.

## <a name="add-reason-code-to-accrual-suspensions-429547"></a>Agregar código de razón a las suspensiones acumuladas (429547)

Se han agregado códigos de motivo a la suspensión acumulada.

## <a name="begin-transitioning-from-human-resources-parameters-to-leave-and-absence-parameters"></a>Comenzar la transición desde los parámetros de Recursos Humanos a los parámetros de baja y ausencia

Esta versión comienza a combinar los parámetros de Recursos Humanos con los parámetros de Baja y ausencia.

## <a name="carry-forward-rules"></a>Transferir reglas

Puede especificar un tipo de transferencia de baja para transferir saldos en los que los ajustes de transferencia se traspasan. Por ejemplo, si un empleado adelanta 10 días, puede elegir un tipo de baja diferente para esos 10 días. Para más información, ver [Configurar tipos de baja y ausencia](hr-leave-and-absence-types.md).

## <a name="known-issues"></a>Problemas conocidos

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>La vista previa SharePoint no funciona en algunos entornos

Si la vista previa del documento para documentos almacenados en SharePoint no funciona, intente el siguiente procedimiento:

1. Verifique que la cuenta de usuario administrador tenga un correo electrónico asociado con el registro de usuario. Puede ver esta información en la página **Usuario**. Si el correo electrónico no está configurado, debe agregar el correo electrónico y el proveedor con el complemento OData Excel. Por defecto, la dirección de correo electrónico no está presente en el diseño de Excel. Deberá editar el diseño de Excel, agregar todos los campos, aplicar y actualizar. Una vez que haya completado esos pasos, puede actualizar la cuenta de administrador.

2. Una vez que la cuenta de administrador tenga una cuenta de correo electrónico asociada, inicie sesión en Human Resources con credenciales de administrador.

3. Acceda a un archivo adjunto en SharePoint para comenzar la vista previa del documento.

4. Inicie sesión con otra cuenta de usuario que tenga acceso a los archivos adjuntos y verifique que la vista previa funcione como se esperaba.

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)