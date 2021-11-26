---
title: Configurar parámetros de Human Resources
description: Este tema explica cómo configurar parámetros específicos de la empresa en Dynamics 365 Human Resources.
author: twheeloc
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fd9bb907f95ba4c368871a470ca9b2bc807646ee
ms.sourcegitcommit: 7e0e2a266d9a9473df72e207554d9bd150e17ce3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2021
ms.locfileid: "7771444"
---
# <a name="configure-human-resources-parameters"></a>Configurar parámetros de Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

La configuración de algunos parámetros de Recursos Humanos se comparten entre empresas, mientras que la configuración de otros parámetros son específicos de la empresa. Este tema explica cómo configurar parámetros de recursos humanos específicos de la empresa.

Se usan dos páginas para definir los parámetros de recursos humanos. Para los parámetros que se comparten entre las empresas, se usa la página **Parámetros compartidos de recursos humanos**. Para los parámetros que son específicos de la empresa (es decir, los ajustes se aplican a una sola empresa), se usa la página **Parámetros de recursos humanos**.

![Ir a Parámetros de recursos humanos.](./media/hr-employee-self-service-human-resources-parameters.png)

En la página **Parámetros de recursos humanos**, los ajustes se dividen en seis pestañas:

- **General**
- **Contratación** (esta pestaña no se incluye en Dynamics 365 Human Resources)
- **Compensación**
- **Secuencias numéricas**
- **FMLA (Ley de permiso por motivos familiares y médicos)**
- **Autoservicio para empleados**
- **Autoservicio para directores**
- **Administración de prestaciones**
- **Bajas y ausencias**
- **Métodos de pago**

Cada pestaña contiene información que pertenece a una sola empresa.

## <a name="general"></a>General

Los ajustes en la pestaña **General** definen el aspecto de la información acerca de ausencia, lesión y enfermedad, y los nuevos trabajadores. Los ajustes de esta pestaña también definen algunas entradas predeterminadas que aparecen mientras trabaja. Específicamente, esta pestaña le permite:

- Seleccionar un color para aplicarlo a transacciones de ausencia abiertas.
- Especificar la hoja de estilo que se utilizará para los informes.
- Habilitar la integración entre los cursos de formación y el registro de ausencias.
- Seleccionar el código de ausencia que se utiliza para controlar esta integración
- Indicar cuánto tiempo se deben conservar los incidentes de casos de lesiones y enfermedades
- Especificar el número de identificación predeterminado que se muestra cuando se contrata a un nuevo trabajador.
- Especifique la fecha que se utiliza para calcular los años de servicio. 

![Pestaña General.](./media/hr-setup-parameters-general.png)

## <a name="recruitment"></a>Contratación

Los ajustes en la pestaña **Reclutamiento** definen los tipos de documentos utilizados para la correspondencia enviada automáticamente a los solicitantes. También puede indicar el proyecto de contratación utilizado para solicitudes no solicitadas.

El período definido en **Vencimiento del proyecto de contratación** determina los proyectos de contratación que se incluyen en el título **Proyectos en vencimiento** en el espacio de trabajo **Gestión de contratación**. El período definido para la advertencia del plazo de solicitud se usa para mostrar los proyectos de contratación que se están acercando al plazo de la solicitud en el mosaico **Se acerca el plazo de la solicitud** en el espacio de trabajo **Contratación**.

Para obtener más información sobre la contratación, consulte [Reclutar candidatos para el trabajo](hr-personnel-recruit.md).

## <a name="compensation"></a>Compensación

En Dynamics 365 Finance, los ajustes en la pestaña **Compensación** definen si los usuarios deben confirmar que desean guardar la información de un plan fijo o de compensación variable. Si activa la casilla **Habilitar guardar la validación**, cuando los usuarios cierren una página relacionada con la compensación, reciben un mensaje que les pregunta si desean guardar el registro. Algunas páginas en la gestión de Compensación no permiten a los usuarios eliminar la información. Al preguntar al usuario que verifique que desea guardar información, podría ser capaz de limitar el importe de información que se guarda pero, por otro lado, no se podrá eliminar posteriormente. Si la casilla **Habilitar guardar validación** se desactiva, los registros se guardan inmediatamente, probablemente antes de que el usuario esté listo. Si se usa la gestión de Rendimiento, la pestaña **Compensación** también le permite seleccionar un modelo de tasación para usarlo en lugar del modelo que está asignado a los planes de compensación al evaluar el rendimiento.

En Human Resources, puede utilizar la pesetaña **Compensación** para elegir restringir el acceso a los planes de compensación y establecer una moneda predeterminada.

Para obtener más información acerca de los panes de compensación, consulte [Información general de planes de compensación](hr-compensation-overview.md).

![Pestaña Compensación.](./media/hr-setup-parameters-compensation.png)

## <a name="number-sequences"></a>Secuencias numéricas

Los ajustes en la pestaña **Secuencia numérica** determinan las secuencias utilizadas para asignar automáticamente ID a elementos en Recursos Humanos, como:

- Aplicaciones
- Registros de ausencias
- Resultados de proceso de compensación
- Números de caso
- Cursos
- Programas del curso

Para mantener las referencias y los códigos de la secuencia numérica, use la página de lista **Secuencias numéricas** (seleccione **Administración de la organización > Secuencias numéricas > Secuencias numéricas**).

Para obtener más información, consulte [Información general de secuencias numéricas](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).

> [!NOTE]
> El número de horas que se trabaja no puede superar 1250, y la duración del empleo no puede superar 12 meses. Estos valores máximos están de acuerdo con la legislación federal en los Estados Unidos.

![Ficha Secuencias numéricas.](./media/hr-setup-parameters-number-sequences.png)

## <a name="fmla"></a>FMLA

En la pestaña FMLA, establece los requisitos de elegibilidad de FMLA y las horas de derecho de FMLA. Para más información, consulte [Configurar parámetros de bajas y ausencias](hr-leave-and-absence-parameters.md).

![Ficha FMLA.](./media/hr-setup-parameters-fmla.png)

## <a name="employee-self-service"></a>Autoservicio para empleados

Los ajustes en la pestaña **Autoservicio para los empleados** afectan la apariencia del **Autoservicio para los empleados** para los empleados. En esta pestaña, puede realizar las siguientes tareas:

- Introducir un nombre para el espacio de trabajo **Autoservicio para el empleado**
- Seleccione qué información puede ingresar un gerente para los empleados
- Agregue enlaces útiles para los empleados
- Restrinja a los empleados para que no agreguen o editen los detalles de los contactos comerciales. Para más información, vea [Restringir la edición de información personal](hr-employee-self-service-restrict-editing.md).

Para obtener más información sobre cómo configurar **Autoservicio para empleados**, consulte [Descripción general del autoservicio para empleados y gerentes](hr-employee-manager-self-service-overview.md).

![Pestaña Autoservicio para empleados.](./media/hr-setup-parameters-employee-self-service.png)

## <a name="manager-self-service"></a>Autoservicio para directores

Los ajustes en la pestaña **Autoservicio para gerentes** afectan lo que ven los gerentes en el **Autoservicio de gerentes**. En esta pestaña, puede configurar las siguientes opciones:

- El rango de registros que caducan
- Los administradores de información pueden ver los registros que vencen
- Si los gerentes pueden ver las posiciones abiertas para informes extendidos
- Vistas de los trabajadores que salen
- Enlaces útiles para gerentes

Para obtener más información sobre cómo configurar **Autoservicio para gerentes**, consulte [Descripción general del autoservicio para empleados y gerentes](hr-employee-manager-self-service-overview.md).

![Pestaña Autoservicio para directores.](./media/hr-setup-parameters-manager-self-service.png)

## <a name="benefits-management"></a>Administración de prestaciones

En la pestaña **Administración de prestaciones**, puede configurar las opciones de correo electrónico para la administración de prestaciones. Para obtener más información sobre la configuración y el uso de la administración de prestaciones, consulte [Resumen de gestión de prestaciones](hr-benefits-management-overview.md).

![Pestaña Administración de prestaciones.](./media/hr-setup-parameters-benefits-management.png)

## <a name="leave-and-absence"></a>Bajas y ausencias

Para obtener más información acerca de la configuración y el uso de Bajas y ausencias, consulte [Vista general de bajas y de ausencias](hr-leave-and-absence-overview.md).

## <a name="payment-methods"></a>Métodos de pago

Sobre la pestaña **Métodos de pago**, puede seleccionar los métodos de pago admitidos por su organización. Para obtener más información acerca de la configuración de la compensación, consulte [Información general de planes de compensación](hr-compensation-overview.md).

![Ficha Métodos de pago.](./media/hr-setup-parameters-payment-methods.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
