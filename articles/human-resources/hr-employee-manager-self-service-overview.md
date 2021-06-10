---
title: Resumen de autoservicio para empleados y gerentes
description: Este artículo proporciona una descripción general del espacio de trabajo de autoservicio para empleados y gerentes.
author: andreabichsel
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 09efb52a76be8ee458135b013b577666a56953f7
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052130"
---
# <a name="employee-and-manager-self-service-overview"></a>Resumen de autoservicio para empleados y gerentes

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artículo proporciona una descripción general del espacio de trabajo de autoservicio para empleados y gerentes.

## <a name="edit-personal-details"></a>Editar detalles personales

Si necesita agregar o cambiar información personal, consulte [Editar información personal](hr-employee-manager-self-service-edit-personal-information.md).

## <a name="user-not-assigned-to-a-worker-record"></a>Usuario no asignado a un registro de trabajador

Si no ha vinculado a su usuario a un registro **Trabajador** de la página **Usuarios**, aparecerá el siguiente mensaje:

**Su Id. de usuario no está asociado a su registro de empleado en el sistema. No podrá ver ni actualizar su información hasta que lo esté. Póngase en contacto con su administrador o equipo de soporte técnico para obtener ayuda.**

Para asociar un usuario con un registro de **Trabajador**, vaya a **Usuarios** y seleccione el usuario. Seleccione **Editar**, agregue el trabajador correspondiente en el campo **Persona** del formulario, y seleccione **Guardar**. Ahora debería tener acceso al autoservicio para empleados.

## <a name="security-requirements-for-employee-and-manager-self-service"></a>Requisitos de seguridad para el autoservicio de empleados y gerentes

Eel autoservicio de empleados y gerentes requiere dos roles de seguridad:

- Los empleados requieren el rol de empleado.
- Los gerentes requieren los roles de empleado y gerente.

>[!NOTE]
>También puede usar roles personalizados para acceder al autoservicio de empleados y gerentes siempre que se les haya otorgado acceso a los espacios de trabajo Empleado y Gerente.<br>
>El acceso del gerente a la información de los empleados se basa en la jerarquía de línea de posición actual definida en Human Resources.

## <a name="employee-self-service"></a>Autoservicio para empleados

La pestaña **Mi informacion** muestra la siguiente información para el autoservicio del empleado.  

### <a name="summary"></a>Resumen

**Elementos de trabajo asignados a mí** muestra todas las aprobaciones y elementos de flujo de trabajo asignados al empleado. Puede configurar los elementos del flujo de trabajo para enviar correos electrónicos al usuario.

**Cuestionarios asignados a mi** muestra todos los cuestionarios programados asignados directamente al empleado o grupo.

**Directorio de la empresa** permite a los empleados buscar información relacionada con individuos en la organización. La información de contacto público está disponible para todos los empleados. El directorio de la compañía está restringido a la compañía en la que el empleado ha iniciado sesión.

**Calendario del equipo** muestra la información del calendario de su equipo. Para más información, consulte [Ver calendarios de equipo y empresa](hr-employee-self-service-calendar.md).

### <a name="my-career-information"></a>Información de mi profesión

La sección **Mi información laboral** del autoservicio para empleados contiene tarjetas relacionadas con Bajas y Ausencias, Gestión del rendimiento, Competencias, Beneficios, Tareas y Adjuntos.

La tarjeta **Balanza de tiempo libre** muestra los saldos de cualquier plan inscrito. Esta tarjeta pronostica su saldo en función de su método de acumulación. Puede introducir y enviar solicitudes de tiempo libre, que luego pasarán por un proceso de aprobación del flujo de trabajo. Para obtener más información acerca de la administración de Baja y de ausencia, consulte [Vista general de bajas y de ausencias](hr-leave-and-absence-overview.md).

La tarjeta **Tareas** muestra las tareas que se le asignaron y le permite verlas y administrarlas.

La tarjeta **Próximo curso registrado** muestra el próximo curso para el que está registrado. Puede ver y registrarse en cualquier curso abierto. Todos los cursos que están abiertos para registrarse tienen un estado de **Empezado** y permiten que los empleados se registren automáticamente en esta tarjeta. Dependiendo de la configuración de su organización, el registro de su curso podría pasar por un proceso de aprobación.

La tarjeta **Certificados** muestra el certificado y la fecha de vencimiento del certificado que vence más cercano a la fecha actual. Puede actualizar, agregar o eliminar certificados. Dependiendo de la configuración de su organización, las actualizaciones de certificados podrían pasar por un proceso de aprobación.

La tarjeta **Próxima revisión programada** muestra su próxima evaluación de rendimiento. Puede comenzar una nueva revisión desde esta tarjeta. Su gerente o representante de Recursos Humanos también puede iniciar revisiones. Dependiendo de la configuración de su organización, es posible que también pueda ver, actualizar y enviar revisiones de salida de esta tarjeta.

Puede gestionar sus objetivos con la tarjeta **Metas de rendimiento**. Esta tarjeta muestra el número de objetivos que tienes en cada estado (**No empezado**, **A tiempo** y **Necesita mejorar**). Puede crear, actualizar y eliminar objetivos, dependiendo de la seguridad asignada basada en roles. Si lo desea, puede agregar nuevos objetivos desde grupos o plantillas. Los gerentes y recursos humanos también pueden crear objetivos en nombre de los empleados y determinar qué tan detallado será cada objetivo. Los gerentes y empleados pueden colaborar en objetivos y actualizar actividades, mediciones y estados. También puede incluir archivos adjuntos.

Puede ver sus habilidades existentes en la tarjeta **Habilidades**. Puede actualizar habilidades, agregar nuevas o eliminar cualquiera que ya no sea relevante. Dependiendo de la configuración de su organización, los cambios a sus habilidades podrían pasar por un proceso de aprobación.

Puede ver su compensación actual a través de la tarjeta **Compensación**. Seleccione **Mostrar** para ver su pago anual y el monto del último aumento. Si trabaja en más de una compañía, cada cantidad anual se muestra en la tarjeta. Para ver su historial de compensación detallado, seleccione el monto del salario anual para abrir el formulario **Historial de compensación fijo y variable**. La compensación futura no se muestra en este formulario. Si tiene más de un empleo, puede cambiar de compañía dentro de este formulario para ver su historial de compensación sin iniciar sesión en cada compañía.

Ver y administrar documentos con la tarjeta **Adjuntos**. Puedes gestionar todos los adjuntos **Externos**. Tanto Recursos Humanos como los empleados pueden agregar archivos adjuntos a través del autoservicio del empleado o el fromulario **Trabajador**. Los archivos adjuntos se establecen en **Externo** por defecto.

### <a name="additional-information"></a>Información adicional

Esta sección proporciona enlaces a otras áreas de autoservicio para empleados, similares a la sección **Mi información profesional**.

Regístrese para obtener beneficios a través del enlace **Beneficios**. Para obtener más información acerca de la gestión de Beneficios, consulte [Visión general de los beneficios](hr-benefits-management-overview.md)

En **Rendimiento** puede elegir **Diarios de rendimiento** para crear entradas de diario de rendimiento para usar tanto en objetivos de rendimiento como en revisiones. Puede elegir **Enviar comentarios** para proporcionar comentarios a otros empleados dentro de su organización. Dependiendo de la configuración de su organización, los correos electrónicos pueden enviarse al destinatario, al remitente y a los administradores. Puede enviar comentarios a todos los empleados de la organización. El envío de comentarios no está restringido por la empresa.

En **Competencias**, puede hacer cambios a **Cursos**, **Educación**, **Puestos de confianza** y **Experiencia profesional**. Dependiendo de la configuración de su organización, las actualizaciones de estas competencias podrían pasar por un proceso de aprobación.

Puede ver los detalles del trabajo en **Organización**. Los detalles del trabajo incluyen habilidades, certificados y áreas de responsabilidad para su puesto principal. También puede ver cualquier equipo prestado que le hayan prestado. Dependiendo de la configuración de su organización, los cambios a su equipo prestado podrían pasar por un proceso de aprobación.

En **Cuestionario** puede ver cuestionarios completados. También puede ver cuestionarios de toda la empresa que no se han completado. Puede elegir completar un cuestionario en cualquier momento. El autor del cuestionario puede determinar el plazo y para quién es aplicable el cuestionario.

Puede configurar enlaces definidos por el usuario en **Parámetros de recursos humanos**. Por ejemplo, puede definir enlaces a declaraciones de pago, documentación de fin de año o soluciones externas. Estos enlaces se muestran en la parte inferior de esta sección, pero puede moverlos mediante la personalización.

También puede crear pestañas adicionales incrustando Power Apps dentro del espacio de trabajo de autoservicio para empleados. Use el menú **Configuración** para personalizar la página con cualquier Power Apps. En el menú **Configuración**, puede optar por agregar una Power App, completar los detalles e insertar la aplicación. Por defecto, Power Apps aparece como la primera pestaña de la secuencia. Puede cambiar el orden usando la personalización estándar.

## <a name="my-team"></a>Mi equipo

La pestaña **Mi equipo** muestra la siguiente información para el autoservicio del gerente. Solo los gerentes pueden acceder a la pestaña **Mi equipo**.

### <a name="personnel-actions"></a>Acciones del personal

Las acciones del personal se muestran según las opciones de configuración dentro de **Parámetros compartidos de recursos humanos** y **Parámetros de recursos humanos**. Cuando está habilitado para **Trabajadores**, las acciones de personal habilitan nuevas opciones de menú, que incluyen:

- **Solicitar nuevo empleado**
- **Solicitar nuevo contratista**
- **Solicitar reasignación de trabajador**
- **Solicitar baja**
- **Solicitar cambio de compensación**

Puede configurar estas opciones para pasar por un flujo de trabajo de revisión y aprobación opcional.

Habilitar **Posicionar acciones** activa las siguientes opciones:

- **Solicitar nuevo puesto**
- **Solicitar cambio en los detalles del puesto**

También puede configurar estas opciones para pasar por un flujo de trabajo de revisión y aprobación opcional.

### <a name="summary"></a>Resumen

La información en la sección **Resumen** depende de las opciones que Recursos Humanos haya seleccionado en **Parámetros de recursos humanos**. En la pestaña **Autoservicio de gerente** de la página **Parámetros de recursos humanos**, puede configurar opciones para mostrar registros que caducan y posiciones abiertas. Habilitar estas opciones determina lo que los administradores pueden ver en la sección **Resumen**.

Puede configurar los siguientes mosaicos para administradores:

- **Certificados que expiran de mi equipo**
- **Números de identificación que expiran de mi equipo**
- **Períodos de prueba que expiran de mi equipo**
- **Filtrados que expiran de mi equipo**
- **Pruebas que expiran de mi equipo**
- **Posiciones abiertas para informes directos y / o extendidos**
- **Solicitudes de tiempo libre pendientes para mi equipo**
- **Evaluación de aptitudes del equipo**
- **Análisis de lagunas de aptitudes**
- **Diarios de rendimiento del equipo**
- **Objetivos de rendimiento del equipo**
- **Revisiones de rendimiento del equipo**
- **Trabajadores con fin del empleo**

Puede configurar las siguientes opciones para que los gerentes realicen cambios o agreguen solicitudes de licencia en nombre de sus informes directos:

- Certificados
- Cursos
- Artículos de préstamo
- Aptitudes
- Solicitudes de bajas y ausencias

### <a name="my-team-information"></a>Información de mi equipo

La información de mi equipo permite a los gerentes ver y actualizar informes directos y extendidos. Para acceder a informes extendidos, seleccione el empleado que tiene instrucciones y luego elija **Ver equipo** en la tarjeta. Todas las mismas opciones se aplican a los informes extendidos como informes directos. 

#### <a name="summary-tab"></a>Pestaña Resumen

La pestaña **Resumen** proporciona una vista rápida de sus informes directos. Si un informe directo también tiene trabajadores que le informan, la tarjeta muestra el número de informes directos en la sección superior, junto con el botón **Ver equipo**. Las opciones sobre cada tarjeta se aplican al empleado seleccionado. Por ejemplo, si desea introducir una solicitud de licencia en nombre de un empleado, seleccione el empleado y luego elija **Solicitar tiempo libre** encima de las tarjetas. 

Si selecciona el botón **Detalles** después de seleccionar un empleado, se muestran las siguientes opciones:

- **Certificados**
- **Compensación**
- **Cursos**
- **Revisiones**
- **Licencias**
- **Artículos prestados**
- **Objetivos de desempeño**
- **Cursos registrados**
- **Aptitudes**
- **Enviar comentarios**

Dependiendo de la configuración de su organización, puede hacer cambios o solo ver.

#### <a name="position-tab"></a>Pestaña Puesto

La pestaña **Puestos** proporciona una vista resumida de los empleados en su puesto principal. El nombre, título y departamento aparece en el encabezado de cada tarjeta. Esta tarjeta incluye:

- **Fecha de antigüedad** - Se muestra desde la sección de resumen del trabajador del formulario del trabajador
- **Años de servicio** - Calculado en base a la fecha de inicio de empleo del empleado
- **Número de puestos anteriores** - Según el historial de puestos, al seleccionar este número se abre la vista detallada de todos los puestos ocupados anteriormente
- **Fecha de nacimiento** - El mes y el día de la fecha de nacimiento del empleado

Puede ver datos de puesto para informes directos y extendidos.

#### <a name="compensation-tab"></a>Pestaña Compensación

La pestaña **Compensación** muestra el salario anual del empleado. Se muestra un identificador de empresa debajo del importe del salario. Si un empleado tiene más de un empleo y le pagan varias entidades legales, el empleado tendrá múltiples planes de compensación. Para ver todos los planes de compensación en las entidades jurídicas sin cambiar de empresa, debe habilitar la compensación cruzada en **Recursos humanos> Parámetros compartidos > Acceso avanzado > Habilitar compensación entre empresas**.

Para ver el historial de compensación, seleccione el monto del salario para abrir el formulario **Detalles**. Solo los registros de compensación variable y fija actuales e históricos se muestran en el formulario **Compensación**. Si un empleado tiene más de un empleo, puede cambiar de empresa para ver el historial de compensación de cada empresa o habilitar la compensación entre empresas en los parámetros compartidos de Recursos humanos para ver todos los planes de compensación.

Puede ver la compensación para informes directos y extendidos.

#### <a name="leave-and-absence-tab"></a>Pestaña permisos y ausencias

La pestaña **Permisos y ausencias** muestra los saldos superiores para los empleados que tienen actividad. Para tomar medidas o ver una lista completa de actividades, seleccione **Detalles** y luego seleccione **Tiempo libre**. En el formulario **Tiempo libre**, puede ver saldos, solicitudes, tiempo libre aprobado y saldos de pronóstico para ayudar a los empleados a administrar mejor el tiempo. Dependiendo de la configuración de su organización, también puede solicitar tiempo libre para sus informes directos y extendidos.

#### <a name="performance-goals-tab"></a>Pestaña Objetivos de rendimiento

La pestaña **Objetivos de rendimiento** resume los objetivos de rendimiento por estado. Seleccione un número para un estado o seleccione objetivos de rendimiento en **Detalles** para ver todos los objetivos de un empleado. Los gerentes y empleados pueden actualizar los objetivos según sea necesario durante la duración del objetivo.

Los gerentes pueden ver todos los objetivos de su equipo a través del mosaico **Objetivos de rendimiento del equipo** en la sección **Resumen** de **Mi equipo**.

#### <a name="reviews-tab"></a>Pestaña Comentarios

La pestaña **Comentarios** resume los comentarios que el empleado tiene en cada estado: **En progreso**, **Listo para revisar** y **Revisión final**. Para acceder a la revisión de un empleado, seleccione el botón **Detalles** y luego seleccione opiniones para colaborar. Según dónde se encuentra una revisión dentro del proceso de flujo de trabajo, puede ver si la revisión está disponible para actualizar. 

Puede ver todos los comentarios para su equipo a través del mosaico **Comentarios de rendimiento del equipo** en la sección **Resumen** de **Mi equipo**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]