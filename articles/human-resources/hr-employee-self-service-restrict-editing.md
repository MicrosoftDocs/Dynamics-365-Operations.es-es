---
title: Restringir la edición de información personal
description: Restrinja a los empleados para que no editen los detalles de los contactos en Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d4785232dbb21c5f8a800497fb0cfd3c64dea2d8
ms.sourcegitcommit: 45d10d0c25b3ec585323709bb97ba1895b500429
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "5503045"
---
# <a name="restrict-editing-of-personal-information"></a>Restringir la edición de información personal

[!include [applies to](../includes/applies-to-hr.md)]
[!include [preview feature](./includes/preview-feature.md)]

Este tema describe cómo restringir que los empleados editen los detalles de contacto en Dynamics 365 Human Resources. Es posible que desee evitar que los empleados editen ciertos detalles de contacto, como la ubicación de su empresa o la dirección de correo electrónico.

> [!NOTE]
> Para utilizar esta función, primero debe habilitar **(Vista previa) Impedir que los empleados agreguen o editen la dirección y la información de contacto para fines seleccionados** en Gestión de funciones. Para obtener más información sobre la habilitación de características en vista previa, consulte [Administrar características](hr-admin-manage-features.md).<br><br>![Habilitar característica de vista previa](./media/hr-employee-self-service-restrict-enable.png)

## <a name="choose-the-information-an-employee-can-add-or-edit"></a>Elija la información que un empleado puede agregar o editar

1. En Human Resources, seleccione **Gestión de personal**, seleccione **Vínculos** y luego seleccione **Parámetros de recursos humanos**.

   ![Ir a Parámetros de recursos humanos](./media/hr-employee-self-service-human-resources-parameters.png)

2. Sobre la página **Parámetros de recursos humanos**, seleccione la pestaña **Autoservicio para los empleados**.

   ![Seleccione Autoservicio para empleados](./media/hr-employee-self-service-tab.png)

3. Sobre la pestaña **Autoservicio para los empleados**, desmarque toda la información en la sección **Dirección e información de contacto** que no desea que los empleados agreguen o editen. En este ejemplo, hemos desmarcado la información de contacto de **Negocio**.

   ![Restringir la edición de la información de contacto comercial](./media/hr-employee-self-service-restrict-business.png)

4. Seleccione **Guardar**.

   ![Guardar cambios](./media/hr-employee-self-service-restrict-save.png)

## <a name="employee-experience"></a>Experiencia del empleado

Una vez que haya restringido a los empleados para que no agreguen o editen detalles de contacto, pueden ver la información, pero no pueden cambiarla.

En este ejemplo, donde los empleados no pueden editar datos de contacto de **Negocio**, aún pueden ver la información en el autoservicio del empleado:

![Ver detalles de contacto comercial](./media/hr-employee-self-service-restrict-view.png)

Sin embargo, cuando seleccionan los datos de contacto de la empresa, el panel **Editar dirección** aparece como de solo lectura y no pueden cambiar ninguno de los campos.

![Los datos de contacto de la empresa se muestran como de solo lectura](./media/hr-employee-self-service-restrict-read-only.png)

Además, si seleccionan **Agregar** para agregar una nueva dirección, no pueden seleccionar **Negocio** desde el cuadro desplegable **Objetivo**.

![El empleado no puede agregar una dirección comercial](./media/hr-employee-self-service-restrict-add.png)

Los empleados obtienen la misma experiencia cuando seleccionan **Detalles de contacto** en la página **Informacion personal** y agregan una nueva dirección. El cuadro desplegable **Objetivo** solo muestra los tipos de información que pueden agregar. 

![El empleado no puede seleccionar Negocio en el menú desplegable Propósito](./media/hr-employee-self-service-restrict-purpose.png)

**Detalles de contacto** ahora muestra **Objetivo** en la cuadrícula.

![El propósito se muestra en la cuadrícula de detalles de contacto](./media/hr-employee-self-service-restrict-purpose-grid.png)

## <a name="see-also"></a>Consulte también

[Visión general del autoservicio para empleado y director](hr-employee-manager-self-service-overview.md)<br>
[Configurar parámetros de Human Resources](hr-setup-parameters.md)<br>
[Editar información personal](hr-employee-manager-self-service-edit-personal-information.md)