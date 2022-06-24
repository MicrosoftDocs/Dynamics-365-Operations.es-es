---
title: Crear un nuevo plan de prestaciones
description: Este artículo le muestra cómo configurar planes de prestaciones en Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitPlanListPage, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7815657c4bf3f79d1a04333027cc51b496fe1820
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8909828"
---
# <a name="create-a-benefit-plan"></a>Crear planes de prestaciones


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artículo le muestra cómo configurar planes de prestaciones en Dynamics 365 Human Resources.

1. En el espacio de trabajo **Administración de prestaciones**, en **Planes**, seleccione **Planes de prestaciones**.

2. Seleccione **Nuevo**.

3. En la pestaña **General**, especifique valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- |
   | **Plan** | Un identificador único para el plan. |
   | **Descripción** | Una descripción del plan. |
   | **Tipo de plan** | Cuando crea un nuevo plan, debe especificar el tipo de plan. Un tipo de plan es una agrupación de alto nivel de tipos específicos de prestaciones. Cada tipo de plan especifica si un empleado puede inscribirse en diferentes planes de ese tipo, especifica si los contactos son beneficiarios o dependientes y define las opciones de cobertura. Puede crear nuevos tipos de planes personalizados para satisfacer las necesidades de sus ofertas de prestaciones. Los principales tipos de planes de prestaciones son: <ul><li>401K</li><li>ADD</li><li>Dental</li><li>Bienestar físico</li><li>FSA</li><li>Vida</li><li>LTD</li><li>Cobertura médica</li><li>PTO</li><li>STD</li><li>Visión</li></ul> |
   | **Código de tipo de plan** | El código del tipo de plan del tipo de plan. |
   | **Programa** | Especifica un programa para asignarlo opcionalmente al plan. |
   | **Agrupación de trabajos** | Especifica una agrupación para asignarla opcionalmente al plan. |
   | **Embarque maestro** | Especifica si el plan es el plan maestro de la agrupación a la que está asignado. |
   | **Fecha y hora de inicio de validez** | La fecha y la hora en las que empieza el plan. El valor predeterminado de la fecha actual del sistema. |
   | **Fecha y hora de fin de validez** | La fecha y la hora en las que finaliza el plan. El valor predeterminado es 12/31/2154, que significa nunca. |

4. En la pestaña **Configuración**, especifique valores para los siguientes campos, según el tipo de plan que esté creando:

   | Tipo de plan | Campo | Descripción |
   | --- | --- | --- |
   | Médico (médico, dental, de visión, HMO) | COBRA | Especifica si el plan es idóneo para COBRA (ley de reconciliación presupuestaria consolidada de autobús). |
   | Médico (médico, dental, de visión, HMO) | HIPAA | Especifica si el plan es idóneo para la HIPAA (ley de responsabilidad y portabilidad del seguro médico). |
   | Médico (médico, dental, de visión, HMO)<br><br>Otro (PTO, bienestar físico)<br><br>Otras<br><br>Incapacidad de larga duración<br><br>ADD (vida básica, vida voluntaria)<br><br>Ahorros (por ejemplo, 401(k))<br><br>FSA | Antes de impuestos elegible | Especifica si se pueden hacer contribuciones al plan antes de aplicar los impuestos. |
   | Médico (médico, dental, de visión, HMO)<br><br>Otro (PTO, bienestar físico)<br><br>Incapacidad de larga duración<br><br>ADD (vida básica, vida voluntaria)<br><br>Ahorros (por ejemplo, 401(k))<br><br>FSA | Después de impuestos aptos | Especifica si se pueden hacer contribuciones al plan después de aplicar los impuestos. |
   | Médico (médico, dental, de visión, HMO)<br><br>Otro (PTO, bienestar físico)<br><br>Incapacidad de larga duración<br><br>ADD (vida básica, vida voluntaria)<br><br>Ahorros (por ejemplo, 401(k))<br><br>FSA | Contribuyente | Especifica quién contribuye al plan: el empleado, el empleador o ambos. |
   | Incapacidad de larga duración<br><br>ADD (vida básica, vida voluntaria) | Cobertura mínima | El importe mínimo de cobertura de seguro necesario para el plan. |
   | Incapacidad de larga duración<br><br>ADD (vida básica, vida voluntaria) | Cobertura máxima | El importe máximo de cobertura de seguro necesario para el plan. |
   | Incapacidad de larga duración<br><br>ADD (vida básica, vida voluntaria) | Usar incrementos de cobertura | Especifica si se debe validar que el importe de la cobertura coincida con un importe incremental válido. |
   | Incapacidad de larga duración<br><br>ADD (vida básica, vida voluntaria) | Importe incremental | El importe incremental de cobertura de seguro para el plan. Por ejemplo, si el importe incremental es 1000, un empleado no puede tener 200 500 $ de seguro y necesitaría redondear a 201 000 $ o bajar a 200 000 $. |
   | Incapacidad de larga duración<br><br>ADD (vida básica, vida voluntaria) | Dirección incremental | Especifica la dirección en la que se debe redondear, hacia arriba o hacia abajo, si el importe de cobertura no satisface el valor del importe incremental. |
   | ADD (vida básica, vida voluntaria) | Prueba de asegurabilidad | Especifica si un empleado debe proporcionar pruebas de asegurabilidad. |
   | ADD (vida básica, vida voluntaria) | Importe | El importe en la divisa de contabilidad. Este campo sólo está activo si está activada la casilla de pruebas de asegurabilidad. |
   | Ahorros (por ejemplo, 401(k))<br><br>FSA | Contribución mínima anual | El importe mínimo de contribución necesario para el plan. |
   | Ahorros (por ejemplo, 401(k))<br><br>FSA | Contribución máxima anual | El importe máximo de contribución necesario para el plan. |
   | Ahorros (por ejemplo, 401(k)) | Importe anual máximo de la empresa | El importe máximo que un empleador puede contribuir a un plan de ahorro para empleados durante un periodo de prestaciones. Debe seleccionar la casilla de verificación Correspondencia con el empleador para usar este campo. |
   | Ahorros (por ejemplo, 401(k)) | Correspondiente a la empresa | Especifica si el empleador contribuye a un plan de ahorros del empleado. |
   | Ahorros (por ejemplo, 401(k)) | Porcentaje que la empresa igualará | El porcentaje de una contribución del empleado que el empleador igualará. |
   | Ahorros (por ejemplo, 401(k)) | Límite correspondiente a la empresa | El porcentaje máximo que igualará el empleador. Por ejemplo, si un empleador igualará el 100 % de las contribuciones de los empleados hasta el 6 % del salario del empleado, el límite de igualación del empleador es del 6 %. |

5. En la pestaña **Configuración**, especifique valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- |
   | **Permitir/continuar la inscripción** | Especifica si los empleados pueden inscribirse en el plan si cumplen con los requisitos de idoneidad.</br></br>Si se establece en No, el plan no estará disponible para los empleados cuando procese la idoneidad. |
   | **Inscribir automáticamente desde el año anterior** | Especifica si se debe inscribir automáticamente en el plan a un empleado apto si se inscribió durante el año anterior. |
   | **Inscripción automática de forma predeterminada** | Especifica si se selecciona el plan para la inscripción de forma predeterminada. El plan no es obligatorio, por lo que el empleado puede cambiar la selección predeterminada. |
   | **Cerrado para inscripciones nuevas** | Especifica si se debe restringir el plan solo a los empleados idóneos que se inscribieron en el plan en el año anterior. |
   | **Plan obligatorio** | Especifica si se inscriben automáticamente los empleados en el plan. Los empleados no pueden cambiar la selección de inscripción. |
   | **Fecha de inicio** | La fecha en que se creó el plan en la empresa. |
   | **Cuenta de proveedor** (proveedor de prestaciones) | El proveedor al que la empresa paga las bonificaciones del plan. |
   | **Nombre** (proveedor de prestaciones) | Nombre del proveedor. |
   | **Referencia de proveedor** (proveedor de prestaciones) | La referencia del proveedor para el plan. Por ejemplo, el número de plan de grupo de la empresa. |
   | **Referencia alternativa** (proveedor de prestaciones) | La referencia alternativa del proveedor para el plan. Por ejemplo, el número de cuenta de la empresa. |
   | **Divisa** (proveedor de prestaciones) | La divisa que se utiliza para pagar las bonificaciones al proveedor. |
   | **Cuenta de gastos** (proveedor de prestaciones) | La cuenta de contabilidad general que se usa como cuenta de gastos para las bonificaciones del plan. |
   | **Cuenta de proveedor** (administrador de prestaciones) | El proveedor al que la empresa paga para que administre el plan. Si el plan se administra automáticamente, deje este campo en blanco. |
   | **Nombre** (administrador de prestaciones) | El nombre del proveedor de administración de prestaciones. |
   | **Referencia de proveedor** (administrador de prestaciones) | La referencia del proveedor de administración para el plan. |
   | **Referencia alternativa** (administrador de prestaciones) | La referencia alternativa del proveedor de administración para el plan. |
   | **Divisa** (administrador de prestaciones) | La divisa que se utiliza para pagar al administrador de prestaciones. |
   | **Cuenta de gastos** (administrador de prestaciones) | La cuenta contabilidad general que se utiliza como cuenta de gastos para los costes asociados con la administración del plan. |

6. En la pestaña **Filtros**, filtre según sea necesario. Puede filtrar por los siguientes campos:

   - **Unidad de negocio**
   - **Departamento**
   - **Entidad jurídica**
   - **Ubicación**
   - **Posición**

7. En la pestaña **Reglas de idoneidad**, especifique valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- |
   | **Número de línea** | Número de línea de la regla de idoneidad. |
   | **Regla de idoneidad** | Una regla de idoneidad para aplicar al plan de beneficios. Esta regla de idoneidad se aplicará al tipo de acción correspondiente y se asociará con el periodo de espera de cobertura y las deducciones especificadas. |
   | **Tipo de acción** | La acción para aplicar la regla de idoneidad a: inscripción de prestaciones o vencimiento de prestaciones. |
   | **Período de espera de cobertura** | Un valor del formulario de periodos de espera. El periodo de espera de la cobertura determina la cantidad de días o meses que un empleado espera la cobertura de prestaciones o el vencimiento de las prestaciones según los criterios de la regla de idoneidad y el tipo de acción. |
   | **Período de espera de deducción** | Un valor del formulario de periodos de espera. La deducción del periodo de espera de la cobertura determina la cantidad de días o meses que un empleado espera las deducciones de su sueldo según los criterios de la regla de idoneidad y el tipo de acción. |

8. Seleccione **Guardar**.

## <a name="view-enrolled-workers"></a>Ver trabajadores inscritos

Puede ver los trabajadores que están inscritos al plan de prestaciones seleccionado.

1. En el espacio de trabajo **Administración de prestaciones**, en **Planes**, seleccione **Planes de prestaciones**.

2. En la pestaña **Prestaciones** de la barra de navegación, seleccione **Trabajadores inscritos**.

## <a name="attach-coverage-options"></a>Vincular opciones de cobertura

Puede agregar opciones de cobertura al plan de prestaciones seleccionado. Adjuntar opciones de cobertura junta la configuración de tarifa y deducción para una opción de cobertura.  Ejemplo: para un plan médico, el usuario seleccionaría una opción de cobertura familiar.  Luego tendrían que seleccionar la tarifa familiar para el plan asociado (establecido en la configuración de la tarifa) y la deducción para el plan asociado (establecido en la configuración de la tarifa). Proporciona el coste para el empleador y el empleado para una cobertura seleccionada. Luego repetiría el proceso para una cobertura de empleado 1 o cobertura de empleado.

1. En el espacio de trabajo **Administración de prestaciones**, en **Planes**, seleccione **Planes de prestaciones**.

2. En la pestaña **Prestaciones** de la barra de navegación, seleccione **Adjuntar opciones de cobertura**.

## <a name="override-eligibility-rules"></a>Anulación de reglas de idoneidad

Puede agregar trabajadores a un plan como excepciones a las reglas de idoneidad. Cada trabajador que agregue será idóneo para el plan de prestaciones.

1. En el espacio de trabajo **Administración de prestaciones**, en **Planes**, seleccione **Planes de prestaciones**.

2. En la pestaña **Prestaciones** de la barra de navegación, seleccione **Anular regla de idoneidad**.

## <a name="view-attached-periods"></a>Ver los periodos adjuntos

Puede ver una lista de los periodos de prestaciones disponibles.

1. En el espacio de trabajo **Administración de prestaciones**, en **Planes**, seleccione **Planes de prestaciones**.

2. Seleccione la pestaña **Periodos** en la barra de navegación.

## <a name="view-plan-description"></a>Ver descripción del plan

Puede proporcionar una descripción del plan para ayudar a los empleados con sus selecciones de prestaciones. La descripción del plan que introduzca aquí se muestra en el autoservicio del empleado al pasar el ratón sobre el plan en la lista de opciones de cobertura.

1. En el espacio de trabajo **Administración de prestaciones**, en **Planes**, seleccione **Planes de prestaciones**.

2. En la pestaña **Prestaciones** de la barra de navegación, seleccione **Descripción del plan**.

## <a name="view-flex-credit-programs"></a>Ver programas de crédito flexible

1. En el espacio de trabajo **Administración de prestaciones**, en **Planes**, seleccione **Planes de prestaciones**.

2. En la pestaña **Prestaciones** de la barra de navegación, seleccione **Programas de crédito flexible**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
