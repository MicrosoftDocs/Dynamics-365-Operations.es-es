---
title: Listo para pagar
description: Este tema muestra cómo marcar a un empleado como listo para pagar Dynamics 365 Human Resources.
author: marcelbf
ms.date: 08/25/2021
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
ms.openlocfilehash: 80bba5446eb7a87d96a7da4ae856cb5ca114ce52
ms.sourcegitcommit: 24e20b3b96834b23311f1bf5dbab28baf3323728
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483791"
---
# <a name="ready-to-pay"></a>Listo para pagar

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [preview feature](./includes/preview-feature.md)]

> [!NOTE]
> Si desea marcar a un empleado como listo para pagar, primero debe habilitar la característica **(Vista previa) integración de nómina** en la administración de características. Para obtener más información sobre la habilitación de características en vista previa, consulte [Administrar características](hr-admin-manage-features.md).

Esta característica permite a los profesionales de recursos humanos comprender qué empleados están listos para el procesamiento de nómina y cuáles requieren acción antes de ser consumidos por un proveedor de nómina externo.

## <a name="mark-employee-as-ready-to-pay"></a>Marcar al empleado como listo para pagar

Recopilar y validar la información de los empleados puede llevar mucho tiempo y puede generar errores. Al proporcionar una forma para que los profesionales de recursos humanos revisen y actualicen fácilmente la información de los empleados, Dynamics 365 Human Resources ayuda a reducir el tiempo de preparación para procesar la nómina.

Para marcar un empleado como listo para pagar:

1. Abra **Administración de compensaciones**. Hay dos mosaicos en el espacio de trabajo: 
    - **Empleados que están listos para pagar**
    - **Empleados que no están dispuestos a pagar**
    ![Espacio de trabajo de gestión de compensaciones.](./media/hr-ready-to-pay-1-workspace.png)

2. Selecciona el mosaico **Empleados que no están listos para pagar**.

3. Seleccione los empleados a validar. En la **Ficha nómina**, en el grupo **Listo para pagar**, seleccione **Validar**.
    ![Validar a los empleados.](./media/hr-ready-to-pay-2-validate.png)

4. Para revisar los resultados, en la **Ficha nómina**, en el grupo **Listo para pagar**, seleccione **Resultados**.

## <a name="validation"></a>Validación

Antes de marcar a un empleado como listo para pagarle, se validará si está completo el perfil del empleado.

![Validar los resultados.](./media/hr-ready-to-pay-3-results.png)

| Validación | Detalles |
| --- | --- |
| **Parámetro de propósito de la dirección** | Validar que esté seleccionado el parámetro **Usar finalidad de direcciones de nómina**. |
| **Dirección de nómina** | Confirma si el perfil de trabajador tiene al menos una dirección con la finalidad **Lugar de residencia de nómina** o **Lugar de trabajo de nómina**, y solo hay una dirección por finalidad. |
| **Empleo** | Confirma que el trabajador tiene al menos un empleo (actual, anterior o futuro). |
| **Número de identificación** | Confirma si el campo **Usar tipos de identificación en el procesamiento de nómina** tiene calor **Sí** en la página **Parámetros de recursos humanos** y si el tipo de identificación indicado en el parámetro se completa en el perfil del trabajador. |
| **Nombre y apellidos** | Confirma que los campos **Nombre** y **Apellido** están rellenos.|
| **Posición** | Confirma si el trabajador tiene un puesto asignado. |
| **Fecha de nacimiento** | Confirma que el campo **Cumpleaños** está lleno. |
| **Compensación** | Confirma que el trabajador está inscrito en un plan de compensación fija. |

Si una de estas validaciones falla, no puede marcar al empleado como listo para pagar.

Si el campo **Listo para pagar** es **No**, esto es una indicación de que debe realizar una acción para asegurarse de que el perfil de trabajador esté completo. Esto no impedirá que los datos queden expuestos en ninguna entidad de datos. 

## <a name="known-issues"></a>Problemas conocidos

- Debes deshabilitar la función **Entrada de empleados simplificada** en la administración de características. Los mosaicos en el espacio de trabajo de administración de compensación no funcionarán correctamente si usa esta función.
- En la página **Trabajador**, la **Pestaña Nómina** y el grupo **Listo para pagar** están disponibles para cualquier rol de usuario. 

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración de nóminas](hr-admin-integration-payroll-api-introduction.md)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
