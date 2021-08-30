---
title: Listo para pagar
description: Este tema muestra cómo marcar a un empleado como listo para pagar Dynamics 365 Human Resources.
author: marcelbf
ms.date: 07/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-07-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 70b3f31db459fe021caf08fe09b2e44a597294d1992ee16a69efd8745941a4bd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732426"
---
# <a name="ready-to-pay"></a>Listo para pagar

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [preview feature](./includes/preview-feature.md)]

> [!NOTE]
> Si desea marcar a un empleado como listo para pagar, primero debe habilitar la característica **(Vista previa) integración de nómina** en la gestión de funciones. Para obtener más información sobre la habilitación de características en vista previa, consulte [Administrar características](hr-admin-manage-features.md).

Esta función permite a los profesionales de recursos humanos comprender qué empleados están listos para el procesamiento de nómina y cuáles requieren acción antes de ser consumidos por un proveedor de nómina externo.

## <a name="mark-employee-as-ready-to-pay"></a>Marcar al empleado como listo para pagar

Recopilar y validar la información de los empleados puede llevar mucho tiempo y puede generar errores. Al proporcionar una forma para que los profesionales de recursos humanos revisen y actualicen fácilmente la información de los empleados, Dynamics 365 Human Resources ayuda a reducir el tiempo de preparación para procesar la nómina.

Para marcar un empleado como listo para pagar:

1. Abra **Administración de compensaciones**. Hay dos mosaicos en el espacio de trabajo 
    - **Empleados que están listos para pagar**
    - **Empleados que no están dispuestos a pagar**
    ![Espacio de trabajo de gestión de compensaciones.](./media/hr-ready-to-pay-1-workspace.png)

2. Selecciona el mosaico **Empleados que no están listos para pagar**.

3. Seleccione los empleados a validar. En la **Ficha nómina**, en el grupo **Listo para pagar**, seleccione **Validar**.
    ![Validar a los empleados.](./media/hr-ready-to-pay-2-validate.png)

4. Para revisar los resultados, en la **Ficha nómina**, en el grupo **Listo para pagar**, seleccione **Resultados**.

## <a name="validation"></a>Validación

Antes de marcar a un empleado como listo para pagar, el sistema realizará una validación básica de la integridad del perfil.

![Validar los resultados.](./media/hr-ready-to-pay-3-results.png)

La siguiente tabla ofrece información acerca de cada una de las validaciones que se realizan. 

| Validación | Detalles |
| --- | --- |
| Parámetro de propósito de la dirección | Validar si el parámetro **Usar direcciones de nómina con propósito** está activado. |
| Dirección de nómina | Valida si el perfil de trabajador tiene al menos una dirección con el propósito "Lugar de residencia de nómina" o "Lugar de trabajo de nómina", y solo hay una dirección por propósito. |
| Empleo | Verifique si el trabajador tiene al menos un empleo (actual, anterior o futuro). |
| Número de identificación | Valida si el parámetro "Usar tipos de identificación en el procesamiento de nómina" es sí, y si el tipo de identificación indicado en el parámetro se completa en el perfil del trabajador. |
| Nombre y apellidos | Valida si el perfil del trabajador es válido, comprobando si los campos **Nombre** y **Apellido** están rellenados.|
| Trabajo | Verifique si el trabajador tiene un puesto asignado. |
| Fecha de nacimiento | Valida si el perfil del trabajador es válido, comprobando si el campo **Fecha de nacimiento** está rellenado. |
| Compensación | Verifique si el trabajador está inscrito en un plan de compensación fijo. |

Si una de estas validaciones falla, no puede marcar al empleado como listo para pagar.

Si el campo **Listo para pagar** es **No**, esto es una indicación de que debe realizar una acción para asegurarse de que el perfil de trabajador esté completo. Esto no impedirá que los datos queden expuestos en ninguna entidad de datos. 

## <a name="known-issues"></a>Problemas conocidos

- Debes deshabilitar la función **Entrada de empleados simplificada** en la gestión de funciones. Los mosaicos en el espacio de trabajo de administración de compensación no funcionarán correctamente si usa esta función.
- En el formulario del trabajador, la **Ficha nómina** y el grupo **Listo para pagar** están disponibles para cualquier rol de usuario. 

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración de nóminas](hr-admin-integration-payroll-api-introduction.md)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
