---
title: Generar informes de la Ley de Cuidado de salud asequible en la Administración de prestaciones
description: Estos temas describen cómo la Administración de prestaciones ayuda a rastrear la información notificada en el Formulario 1095-B y el Formulario 1095-C para la orden del empresario de la Ley de Cuidado de salud asequible (ACA).
author: andreabichsel
manager: tfehr
ms.date: 12/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 24df18f428e4ca14859bc34048a6bda5e03d1b2f
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464383"
---
# <a name="generate-aca-reports-in-benefits-management"></a>Genere informes de ACA en la administración de prestaciones

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

La Administración de prestaciones ayuda a rastrear la información notificada en el Formulario 1095-B y el Formulario 1095-C para la orden del empresario de la Ley de Cuidado de salud asequible (ACA). Al igual que la capacidad de los informes de ACA en el antiguo espacio de trabajo **Prestaciones**, esta funcionalidad solo se aplica a las entidades jurídicas de Estados Unidos.

Para usar esta funcionalidad, primero debe activar la **Administración avanzada de prestaciones**. Para obtener más información, incluidas advertencias importantes sobre la Administración de prestaciones, consulte [Habilitar o deshabilitar la Administración de prestaciones](hr-admin-manage-features.md#enable-or-disable-benefits-management).

> [!IMPORTANT]
> Solo puede utilizar los informes de ACA desde el espacio de trabajo **Administración de prestaciones** o el antiguo espacio de trabajo **Prestaciones**, pero no desde ambos. Por ejemplo, si cambió a Administración de prestaciones, los informes de ACA solo estarán disponibles en el espacio de trabajo **Administración de prestaciones**, no en el antiguo espacio de trabajo **Prestaciones**.
>
> Si cambia a Administración de prestaciones en la mitad de un año de inscripción, debe configurar correctamente los datos de los empleados para todo el año en Administración de prestaciones. De esta manera, se asegurará de recibir informes precisos durante todo el año.

## <a name="getting-started"></a>Introducción

Para rastrear la información de los formularios 1095, primero hay que crear uno o más grupos de cobertura de Cuidado de salud asequible. Estos grupos indican la siguiente información:

- La oferta de cobertura que se le brindó a un empleado
- La parte del empleado de la prima mensual de menor coste, si el coste es superior al umbral de pobreza federal
- El puerto seguro que utiliza el empresario, si corresponde

Los grupos de cobertura de Cuidado de salud asequible le ayudan a administrar esta información para varios registros de empleados que tienen las mismas condiciones. Puede asignar grupos fácilmente a uno o más empleados.

### <a name="create-or-edit-an-affordable-care-coverage-group"></a>Crear o editar un grupo de cobertura de Cuidado de salud asequible

1. En el espacio de trabajo **Administración de prestaciones**, seleccione **Grupo de cobertura de Cuidado de salud asequible**.

    ![Seleccionar un grupo de cobertura de Cuidado de salud asequible](./media/hr-benefits-management-aca-coverage-group.png)

2. Seleccione **Nuevo** para crear un nuevo grupo de cobertura de Cuidado de salud asequible o **Editar** para cambiar un grupo existente.

    ![Seleccionar Nuevo o Editar](./media/hr-benefits-management-aca-new.png)

3. Establezca los campos siguientes.

    | Campo | Descripción |
    |---|---|
    | Nombre | Escriba un nombre para el grupo. |
    | Descripción | Escriba una descripción del grupo. |
    | Oferta de cobertura | La cobertura que se ofrece a los empleados, su cónyuge o pareja, y sus dependientes. |
    | Parte de coste del empleado | El importe del que el empleado es responsable. |
    | Safe Harbor de la sección 4980H aplicable | El código 4980H de puerto seguro o ayuda para transición. |
    | Mes de inicio del plan | Seleccione el mes del calendario en el que comienza el año de su plan de prestaciones. |
    | Grupo válido desde | La primera fecha en la que este registro es válido. |
    | Grupo válido hasta | La última fecha en la que este registro es válido. Si no hay fecha de vencimiento, introduzca **Nunca**. |

    ![Crear un grupo de cobertura](./media/hr-benefits-management-aca-new-group.png)

4. Seleccione **Guardar**.

### <a name="assign-multiple-employees-to-an-affordable-care-coverage-group"></a>Asignar varios empleados a un grupo de cobertura de Cuidado de salud asequible

1. En el espacio de trabajo **Administración de prestaciones**, seleccione **Grupo de cobertura de Cuidado de salud asequible**.
2. Seleccione el grupo al que desea asignar empleados.
3. Seleccione **Asignación masiva**.

    ![Seleccionar asignación masiva](./media/hr-benefits-management-aca-mass-assignment.png)

4. Seleccione empleados de la lista y, a continuación, seleccione **Asignar**.

    ![Asignar empleados seleccionados a un grupo](./media/hr-benefits-management-aca-assign-coverage-group.png)

## <a name="maintain-multiple-versions-of-coverage-options"></a>Mantener varias versiones de opciones de cobertura

Puede mantener varias versiones de cualquier grupo de cobertura. Cuando algo cambia en su organización o las prestaciones que se ofrecen, puede mantener actualizada la información del grupo sin tener que crear un grupo nuevo y reasignar empleados a dicho grupo.

Una vez que haya creado grupos de cobertura de Cuidado de salud asequible, puede realizar una asignación masiva de empleados a estos grupos. También puede asignar empleados individualmente a grupos e indicar si se realiza un seguimiento y notificación de la información de ACA.

Si no tiene que hacer un seguimiento y notificación de la información de ACA para un empleado, puede establecer la opción **Notificar cobertura** en **No**. Por ejemplo, es posible que tenga empleados a tiempo parcial que no requieren informes de ACA.

### <a name="override-default-values-for-an-employee"></a>Reemplazar los valores predeterminados para un empleado

Para los empleados que están asignados a un grupo de cobertura de Cuidado de salud asequible, puede cambiar las siguientes opciones para cualquier mes que requiera valores diferentes:

- Oferta de cobertura
- Parte de coste del empleado
- Safe Harbor de la sección 4980H aplicable

> [!NOTE]
> Para los informes de ACA de 2020, debe notificar los códigos postales del trabajo y del hogar en el Formulario 1095-C. Los valores se rellenan automáticamente a partir de las ubicaciones activas actuales. Si alguna de las ubicaciones varió en algún momento del año, debe reemplazar el valor. El campo **Código postal** (línea 17) del informe 1095-C solo debe rellenarse si el código **Oferta de cobertura** contiene **1L** a **1Q**, como se indica a continuación:
>
> - **1L, 1M o 1N:** el código postal de la residencia principal
> - **1O, 1P, 1Q:** el código postal principal del trabajo

Para introducir excepciones para cualquier valor de un grupo de Cuidado de salud asequible, siga estos pasos.

1. En el espacio de trabajo **Administración de personal**, seleccione **Vínculos** y, a continuación, seleccione **Trabajadores**.
2. Seleccione el empleado en la lista.
3. En la pestaña **Empleo**, en la sección **Más información**, seleccione **Cobertura de Cuidado de salud asequible**.

    ![Cambiar las opciones de un empleado](./media/hr-benefits-management-aca-change-single-employee.png)

4. Seleccione **Editar**.
5. Para cada mes que requiera cambios, active la casilla **Sobrescribir la configuración predeterminada** y cambie los otros valores según sea necesario.

    ![Reemplazar los valores predeterminados](./media/hr-benefits-management-aca-override-default.png)

6. Seleccione **Guardar**.

## <a name="report-health-care-coverage"></a>Notificar cobertura de atención sanitaria

Debe realizar un seguimiento de cualquier cobertura de atención sanitaria autoasegurada y patrocinada por el empresario para los empleados de tiempo completo y parcial. Incluya a cada empleado, junto con sus dependientes, en el informe 1095-C para los meses en que estaban cubiertos.

Para indicar si se debe informar un plan de prestaciones, siga estos pasos.

1. En el espacio de trabajo **Administración de prestaciones**, seleccione **Planes de prestaciones**.
2. Seleccione el plan de beneficios del que va a informar.
3. Seleccione **Editar**.
4. Establezca la opción **Se informa por la Ley de Reportado Cuidado de salud asequible** en **Sí**.

    ![Notificar cobertura de cuidad cuidado de salud](./media/hr-benefits-management-aca-report-coverage.png)

5. Seleccione **Guardar**.

Si un empleado elige cobertura de atención médica para un dependiente, el período de cobertura del dependiente se determina por la fecha de inscripción o eliminación. Las fechas de cobertura para dependientes se calculan automáticamente según el período en el que el dependiente fue apto y estuvo activo en un plan durante el año de inscripción.

## <a name="generate-1095-b-and-1095-c-forms"></a>Generar los formularios 1095-B y 1095-C

Puede generar los formularios 1095-B y 1095-C de ACA y distribuirlos a cada uno de sus empleados. También puede generar electrónicamente el Formulario 1095-C y los archivos de transmisión 1094-C correspondientes para enviarlos a la agencia tributaria.

1. En el espacio de trabajo **Administración de prestaciones**, seleccione **Formulario 1095-B de ACA** o **Formulario 1095-C de ACA**.
2. Cambie los parámetros según sea necesario y, a continuación, seleccione **Aceptar**.

    > [!NOTE]
    > Si imprime formularios 1095-C para más de 500 empleados, recibirá más de un archivo PDF. Le recomendamos que aumente el valor del campo **Tamaño máximo de archivo en megabytes** en la página **Parámetros de la administración de documentos** a **150**. (Para abrir rápidamente esa página, puede usar el campo de búsqueda en la barra de navegación).
    >
    > ![Cambiar el tamaño máximo de archivo](./media/hr-benefits-management-aca-maximum-file-size.png)

3. Para comprobar el estado de los informes y verlos, utilice el campo de búsqueda en la barra de navegación para abrir la página **Trabajos de informes electrónicos**.

    ![Búsqueda de la página de trabajos de informes electrónicos](./media/hr-benefits-management-aca-search-electronic-reporting-jobs.png)

4. Seleccione el informe que desea ver y, a continuación, seleccione **Mostrar archivos**.

    ![Mostrar archivos](./media/hr-benefits-management-aca-show-files.png)

5. Seleccione **Abrir**.

    ![Abrir un archivo](./media/hr-benefits-management-aca-open-file.png)

6. En la barra de notificaciones que aparece en la parte inferior de la ventana del explorador, abra el archivo zip y seleccione el informe. Puede ver o imprimir el archivo PDF.

    ![Formulario 1095-C de ejemplo](./media/hr-benefits-management-aca-1095-c-form.png)

## <a name="view-aca-coverage-information"></a>Ver información de cobertura de ACA

La página **Cobertura de cuidado de salud asequible del trabajador** muestra la siguiente información:

- Empleados asignados a cada grupo de cobertura
- Empleados que no se tienen que incluir en un informe
- Empleados no asignados

Para ver esta información, siga estos pasos.

1. En el espacio de trabajo **Administración de prestaciones**, seleccione **Grupo de cobertura de cobertura de cuidado de salud asequible del trabajador**.
2. En el campo **Nombre del grupo**, seleccione un grupo.

    ![Ver la cobertura de ACA](./media/hr-benefits-management-aca-view-coverage.png)

Si alguno de los valores predeterminados del grupo de cobertura de Cuidado de salud asequible se han anulado, aparecerá un asterisco junto al valor que se cambió. Si los valores para los 12 meses son iguales y no se han reemplazado, el valor se imprimirá en la columna **Todos los 12 meses**.

Puede ver a los empleados que están marcados como empleados de los que no hay que informar según la ACA y que no requieren un Formulario 1095-C. En el campo **Filtrar por**, seleccione **No se informa para Ley de Cuidado de salud asequible**.

Puede ver los empleados que no están asignados a un grupo o que están asignados a un grupo caducado. En el campo **Filtrar por**, seleccione **Grupo sin asignar o caducado**.

### <a name="export-to-excel"></a>Exportar a Excel

Para exportar cualquiera de las listas a Microsoft Excel, siga estos pasos.

1. Seleccione el botón **Abrir en Microsoft Office**.
2. Seleccione **Tabla temporal de Human Resources de HCM para uso interno**.
3. Seleccione **Descargar**.

### <a name="view-aca-reportable-dependents"></a>Ver dependientes declarables según la ACA

Si tiene que informar sobre las personas cubiertas porque proporciona cobertura autoasegurada, puede ver los dependientes cubiertos por los planes de prestaciones marcados como **Se informa para Ley de Cuidado de salud asequible**. En el panel de acciones, seleccione **Ver cobertura de dependientes**.

![Ver la cobertura de dependientes](./media/hr-benefits-management-aca-view-dependent-coverage.png)

Se muestra la información de cobertura para los dependientes del empleado.

![Cobertura de dependientes](./media/hr-benefits-management-aca-dependents.png)

> [!NOTE]
> La página muestra solo los planes de prestaciones que están marcados como **Se informa para Ley de Cuidado de salud asequible**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]