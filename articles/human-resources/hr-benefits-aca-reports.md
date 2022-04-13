---
title: Generar informes de la Ley de atención sanitaria asequible (ACA)
description: Los informes de la Ley de Cuidado de salud asequible (ACA) generan los formularios 1095-B y 1095-C para respaldar la parte de la **Orden del empresario** de la Ley del Cuidado de salud asequible.
author: twheeloc
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 6682a98bb7241060b035e7da1396ec8f8973bf09
ms.sourcegitcommit: d67f7edaf1a50077c2a7dd105e774f86fc586495
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2022
ms.locfileid: "8534164"
---
# <a name="generate-aca-reports"></a>Generar informes ACA


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Los informes de la Ley de Cuidado de salud asequible (ACA) generan los formularios 1095-B y 1095-C para respaldar la parte de la **Orden del empresario** de la Ley del Cuidado de salud asequible.

> [!NOTE]
> Los informes de ACA solo están habilitados para entidades jurídicas de los Estados Unidos.

## <a name="getting-started"></a>Introducción

Para rastrear la información de los formularios 1095-B y 1095-C, primero debe crear uno o más grupos de cobertura de Cuidado de salud asequible. Los grupos de cobertura de Cuidado de salud asequible indican:

- La oferta de cobertura para un empleado
- La cuota del empleado de la prima mensual de menor coste, si el coste es superior al umbral de pobreza federal
- El puerto seguro que utiliza el empresario, si corresponde

Los grupos de cobertura de Cuidado de Salud Asequible permiten administrar la información para estos campos sin cambiar cada registro de empleado en el que las condiciones sean las mismas. Puede asignar fácilmente grupos de cobertura de Cuidado de salud asequible a uno o más empleados mediante la funcionalidad de **Asignación masiva** de la página.

## <a name="maintaining-multiple-versions-of-a-coverage-group"></a>Mantener varias versiones de un grupo de cobertura

Puede mantener varias versiones de cualquier grupo de cobertura. Esta funcionalidad le permite realizar cambios sin tener que crear un grupo nuevo y reasignar empleados a dicho grupo. 

Una vez que creados los grupos de cobertura de ACA, puede asignarlos en masa a los empleados con la opción **Asignación masiva**. También puede indicar individualmente si desea rastrear y notificar información de ACA, y asignar un empleado a un grupo de cobertura de Cuidado de salud asequible.

No es necesario realizar un seguimiento de alguna información sobre la cobertura de la ACA, como la de los empleados a tiempo parcial. En este caso, establezca el campo **Cobertura del informe** en **No**. Aunque debe asignar cada empleado con información de ACA rastreable a un grupo de cobertura de Cuidado de salud asequible, puede cambiar las siguientes opciones para meses con valores diferentes:

- **Oferta de cobertura**
- **Parte de coste del empleado**
- **Safe Harbor**

Para especificar excepciones para cualquier grupo de cobertura de Cuidado de salud asequible, seleccione el vínculo **Cobertura de cuidado de salud asequible** en la página **Detalles del trabajador** que está bajo la sección **Información adicional** en la pestaña **Empleo**.

## <a name="reporting-health-care-coverage"></a>Notificar cobertura de cuidad cuidado de salud

Además del seguimiento, qué pasaría si alguna cobertura de seguro médico se ofreciera a empleados a jornada completa, si el empresario ofrece cobertura patrocinada por él mismo a los empleados inscritos (independientemente de si su estado es de empleo es a jornada completa o a tiempo parcial), será necesario notificar información adicional en el 1095-C. Cada empleado (incluidos los dependientes) cubierto por los planes de prestaciones patrocinados por el empresario deben incluirse en el informe durante los meses que estuvieron bajo cobertura. 

Puede indicar si cada plan de prestaciones debe notificarse activando la casilla **Se informa para Ley de Cuidado de salud asequible**.

Además, si los empleados han elegido tener a cualquiera de sus dependientes cubiertos con la prestación, puede indicar las fechas en las que estuvo cubierto el dependiente para cada empleado en la página **Mantener prestaciones**. Para indicar que el dependiente estará cubierto con la prestación, seleccione el botón **Editar** en el panel de acciones de la ficha desplegable **Dependientes**.

En la página **Administrador de fechas de la cobertura del dependiente**, puede indicar las fechas en el la prestación cubría al dependiente. Al especificar las fechas en esta página se selecciona automáticamente la casilla de verificación **Cubierto** en la página **Mantener beneficios** .

## <a name="generate-1095-b-and-1095-c-forms"></a>Generar los formularios 1095-B y 1095-C

También puede generar los formularios 1095-B y 1095-C desde el producto y distribuirlos a cada uno de sus empleados. El sistema también puede generar formularios 1095-C y archivos de transmisión del IRS 1094-C electrónicamente.  

Al generar el formulario 1095-C, especifique el ejercicio fiscal adecuado e indique si deben enmascararse los números de seguridad social. Si está imprimiendo formularios 1095-C para más de 500 empleados, recibirá más de un archivo PDF. Está recomendado aumentar el **Tamaño máximo de archivo** en la ventana **Parámetros de la administración de documentos** a 150 MB.

## <a name="viewing-information"></a>Ver la información

Puede usar la página **Cobertura de cuidado de salud asequible del trabajador** para consultar qué empleados se han asignado a cada grupo de cobertura, qué empleados no necesitan incluirse en un informe y qué empleados no están sin asignar.

Si alguno de los valores predeterminados del grupo de cobertura de Cuidado de salud asequible se han anulado, aparecerá un asterisco junto al valor que se cambió. Si los valores para los 12 meses son iguales y no se han reemplazado, el valor se imprimirá en la columna **Todos los 12 meses**.

También puede utilizar la ventana de consulta para comprender qué empleados han sido marcados como empleados de los que no hay que informar según la ACA. No tiene hacer un seguimiento de si se les ofreció cobertura ni emitirles un 1095-C al final del año. Seleccione **No se informa para Ley de Cuidado de salud asequible** en el campo **Filtrado por** para generar una lista de todos los empleados que no recibirán un 1095-C.

Además de ver una lista de empleados de los que no se informa para Ley de Cuidado de salud asequible, también puede ver los empleados que están sin asignar (el campo **Cobertura del informe de la Ley de Cuidado de salud asequible** está vacío) o que se hayan asignado a un grupo de la Ley de Cuidado de salud asequible que venció para el año seleccionado en el campo **Año**.

Puede exportar las listas de empleados generadas mediante cualquiera de las opciones de filtrado a Excel.

Si tiene que informar sobre las personas cubiertas porque proporciona cobertura autoasegurada, puede ver los dependientes cubiertos por los planes de prestaciones marcados como **Se informa para Ley de Cuidado de salud asequible**. Seleccione **Ver cobertura de dependientes** en el panel de acciones.

> [!NOTE]
> En la ventana de consulta solo se muestran planes de prestaciones marcados como **Se informa para Ley de Cuidado de salud asequible**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
