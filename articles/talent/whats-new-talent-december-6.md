---
title: Novedades y cambios en Dynamics 365 for Talent Core HR (6 de diciembre de 2018)
description: "Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent Core HR."
author: Darinkramer
manager: AnnBe
ms.date: 12/07/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-12-06
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: 09936c7161a7e303a0ada2f48ef3281b81a67295
ms.openlocfilehash: 6fae56d2feeec8e5c26fc86bdf89b8ab4c282144
ms.contentlocale: es-es
ms.lasthandoff: 12/10/2018

---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-december-6-2018"></a>Novedades y cambios en Dynamics 365 for Talent Core HR (6 de diciembre de 2018)

[!include [banner](includes/banner.md)]

**Compilación 8.1.2071**

Este tema describe las características que son nuevas o que se han cambiado en Core HR.


## <a name="platform-update-22"></a>Actualización de la plataforma 22

### <a name="export-up-to-1-million-rows-to-excel"></a>Exportar hasta 1 millón de filas a Excel

La característica exportación a Excel ahora se puede configurar para permitir a los usuarios que exporten hasta 1 millón de filas de una cuadrícula a Talent, un aumento sustancial respecto al límite anterior de 10.000 filas. 

### <a name="restyled-personalization-toolbar"></a>Barra de herramientas de personalización con un nuevo estilo

La barra de herramientas de personalización se ha cambiado en la actualización 22 de la plataforma, para ayudar a los usuarios a adaptar más fácilmente sus propias experiencia a Talent. Se realizaron los siguientes cambios: 

-  El nombre de cada herramienta de personalización ahora se muestra junto a un icono, que ayuda al usuario a reconocer rápidamente la herramienta que está interesado en utilizar.
-  La descripción para determinar cómo usar la herramienta actual ahora también se muestra, lo que ayuda al usuario a comprender cómo realizar las personalizaciones necesarias.  
-  La barra de herramientas completa de personalización se puede desplazar a través de la pantalla con la función de arrastrar y soltar en una región concreta en el extremo izquierdo de la barra de herramientas. Esto permite a los usuarios personalizar elementos que anteriormente quedaban oscurecidos por la barra de herramientas.   

### <a name="optimized-is-one-of-filtering-experience"></a>Optimizado es una experiencia de filtrado "es uno de"

El operador de filtro “es uno de” está disponible para la mayoría de los campos al usar las listas desplegables de Panel de filtro y de la cabecera de cuadrícula. Este operador permite que un usuario filtre un campo basándose en valores múltiples. Una nueva y mejorada experiencia para el operador “es uno de” está disponible en la actualización 22 de la plataforma. Para obtener más información, consulte [Optimizado es una experiencia de filtrado "es uno de"](https://docs.microsoft.com/business-applications-release-notes/October18/dynamics365-finance-operations/improved-isoneof-filtering).

### <a name="paste-lists-from-excel-into-filter-fields-with-the-is-one-of-operator"></a>Pegar listas de Excel en campos de filtro con el operador “es uno de”

Para algunas tareas, los usuarios pueden tener una lista de valores en Excel que quisieran usar para filtrar los datos en Talent. Por ejemplo, un usuario de Recurso Humanos puede haber identificado un conjunto de empleados de un informe que necesiten investigación adicional en el sistema, y sería ideal que este usuario pueda copiar la lista directamente desde Excel en un campo de filtro en Talent.

A partir de las actualización 22 de la plataforma, el operador "es uno de" del filtro de columnas de cuadrícula y el panel de filtros ahora reconoce las listas copiadas desde Excel para que se puedan pegar directamente en un campo de filtro. Esto incluye una recopilación de valores copiados de diferentes filas y columnas en Excel. Para obtener más información acerca de esta función, consulte [Pegar listas de Excel en campos de filtro con el operador “es uno de”](https://docs.microsoft.com/business-applications-release-notes/October18/dynamics365-finance-operations/paste-filter-lists-from-excel).

## <a name="in-preview"></a>En vista previa

### <a name="configure-uk-payroll-integration-between-talent-and-dayforce"></a>Configurar la integración de nóminas de Reino Unido entre Talent y Dayforce

La integración entre Microsoft Dynamics 365 for Talent y Ceridian Dayforce está disponible en la vista preliminar para el Reino Unido. Consulte el tema siguiente para obtener más información [Configurar la integración de nóminas entre Talent y Dayforce](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/configure-payroll-integration).

## <a name="coming-soon"></a>Próximamente

### <a name="leave-and-absence-future-leave-and-forecasting-leave-balances"></a>Baja y ausencia: Saldos futuros de licencia y de previsión de la licencia

Con los cambios creados para permitir que los empleados pronostiquen el tiempo libre y pidan futuras solicitudes de tiempo libre sin afectar a sus saldos actuales de tiempo libre, el modo en que el tiempo libre de los saldos se muestra también está cambiando. 

El saldo disponible presentado actualmente es la cantidad de tiempo libre disponible para solicitudes que incluyen acumulaciones hasta hoy y todas las solicitudes aprobadas de licencia hasta la finalización de tiempo. 

Cuando se lanza la capacidad de previsión, el saldo mostrado cambia para ser el saldo actual del tiempo libre incluidas las acumulaciones hasta hoy y las solicitudes hasta hoy. Los empleados y los administradores verán estos saldos actualizados en el autoservicio de empleado y director en la tarjeta **Licencias** y en la ventana **Saldos de licencias**. Los administradores de RR.HH. verán estos saldos actualizados en el espacio de trabajo **Personas** y en la ventana **Planes de licencia asignados** del empleado.

## <a name="other-changes"></a>Otros cambios 

### <a name="termination-code-is-not-populated-to-the-worker-position-assignment-record"></a>El código de la finalización no se rellena en el registro de asignación de puesto del trabajador

Se ha implementado un cambio que rellena el código de motivo en el registro de asignación de puesto durante el proceso de baja.

### <a name="validation-for-personnel-number-being-in-use-needs-additional-details"></a>Validación para el número de personal que se está usando necesita detalles adicionales

Se muestra información adicional cuando las secuencias numéricas están en uso, para comprender mejor los problemas cuando un nuevo número no puede ser producido.
 
### <a name="attachments-buttons-not-available-for-workers"></a>Los botones de archivos adjuntos no están disponibles para los trabajadores

Se han realizado cambios para corregir los archivos adjuntos. Al agregar nuevos archivos adjuntos a un trabajador, los botones **Nuevo** y **Editar** están disponibles ahora cuando los cuadros informativos están abiertos en la ventana del trabajador. 

## <a name="known-issues"></a>Problemas conocidos

### <a name="mapping-errors-in-the-integration-with-finance-and-operations"></a>Errores de asignación en la integración con Finance and Operations

Los siguiente problemas se han identificado en la plantilla actual para la integración de Talent con Finance and Operations. Una nueva plantilla se publicará pronto y se aplicará a todos los proyectos nuevos de integración que se creen. Para los proyectos existentes de integración, las equivalencias de tareas se pueden volver a calcular. Consulte la tabla siguiente para obtener las asignaciones actualizadas. 

>[!NOTE]
> La tarea de asignación de puestos de trabajo a la tarea principal de los puestos no integra los datos. Este es un problema que se está investigando actualmente. No hay solución en la asignación actual. 

La tarea Departamentos a la unidad operativa necesita actualizar las asignaciones siguientes.

| Campo de origen existente          | Nuevo campo de origen |
| -------------------------------|------------------|
| cdm_description (descripción)  | cdm_name (nombre)  |

También es necesario agregar una asignación adicional. Seleccione el último campo **Ninguno** para agregar la siguiente asignación.

| Campo de origen                   | Campo de destino    |
| -------------------------------|----------------------|
| cdm_description (descripción)  | NAMEALIAS (NAMEALIAS)|

Las asignaciones actualizadas deben tener la misma apariencia que lo siguiente.

![Tarea Departamentos a unidades operativas](./media/DepartmentMapping.png)


La tarea Trabajo a Detalle de trabajo necesita actualizar las asignaciones siguientes.

| Campo de origen existente          | Nuevo campo de origen                   |
| -------------------------------|------------------------------------|
| cdm_name (nombre)                | cdm_description (descripción)      |
| cdm_name (descripción)         | cdm_jobdescription (descripción del trabajo)|


Las asignaciones actualizadas deben tener la misma apariencia que lo siguiente.

![Tarea Trabajos a detalles del trabajo](./media/JobMapping.png)

La tarea Trabajadores a trabajo necesita actualizar las asignaciones siguientes.

| Campo de origen existente                 | Nuevo campo de origen                               |
| --------------------------------------|------------------------------------------------|
| cdm_emailaddress1 (dirección de correo electrónico 1)   | cdm_primaryemailaddress (dirección de correo electrónico principal) |
| cdm_telephone1 (teléfono 1)          | cdm_primarytelephone (teléfono principal)       |

La transformación del campo Género también debe actualizarse. Seleccione el tipo de mapa **fn** (función) para el género y actualice las asignaciones de valores siguientes.

| Valor CDS   | Valor Finance and Operations | | ------------|------------------ -----------| | 75440000    | Hombre                         | | 75440001    | Mujer                       | | 75440002    | Ninguno                         | | 75440003    | No específico                  |

Las asignaciones actualizadas deben tener la misma apariencia que lo siguiente.

![Tarea Trabajadores a Trabajador](./media/WorkerMapping.png)

![Transformación de campo de género](./media/WorkerTransform.png)


