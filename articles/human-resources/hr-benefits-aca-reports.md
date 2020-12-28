---
title: Generar informes de la Ley de Cuidado de Salud Asequible (ACA)
description: La funcionalidad está disponible para ayudar a los empleados que necesiten llevar un seguimiento de la información notificada en los formularios 1095-B y 1095-C como respaldo de la parte de la orden del empresario de la Ley de Cuidado de Salud Asequible. Recuerde que esta funcionalidad solo se habilita en entidades jurídicas de los Estados Unidos.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 3555be3067db459625df9f9b0ac6b78fc2715289
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420421"
---
# <a name="generate-affordable-care-act-aca-reports"></a>Generar informes de la Ley de Cuidado de Salud Asequible (ACA)

La funcionalidad está disponible para ayudar a los empleados que necesiten llevar un seguimiento de la información notificada en los formularios 1095-B y 1095-C como respaldo de la parte de la **orden del empresario** de la Ley de Cuidado de Salud Asequible. Recuerde que esta funcionalidad solo se habilita en entidades jurídicas de los Estados Unidos.

## <a name="getting-started"></a>Introducción
Al iniciar el seguimiento de la información para realizar la notificación en los formularios 1095-B y 1095-C, debe crear primero uno o más grupos de cobertura de Cuidado de Salud Asequible. Estos grupos de cobertura de Cuidado de Salud Asequible se utilizan para indicar la propuesta de cobertura que se proporcionó a un empleado, la cuota del empleado de la prima mensual de menor coste (si el coste es superior al umbral de pobreza federal), así como el puerto seguro que usa el empresario, si procede. Mediante los grupos de la Ley de Cuidado de Salud Asequible se puede administrar la información para estos campos sin la necesidad pasar por cada registro de empleado donde las condiciones sean las mismas. Además, los grupos de cobertura de Cuidad de Salud Asequible se asignan fácilmente a uno o más empleados mediante la funcionalidad de asignación masiva en la página.

## <a name="maintaining-multiple-versions-of-a-coverage-group"></a>Mantener varias versiones de un grupo de cobertura
Puede mantener varias versiones de cualquier grupo de cobertura, lo que permite que realice los cambios que conservan la información actual del grupo sin tener que crear un nuevo grupo y reasignarle empleados cuando cambia algo en la organización o en los beneficios que se ofrecen. 

Después de crear los grupos de cobertura de Cuidado de Salud Asequible que necesita, puede elegir asignar de forma masiva los grupos a los empleados mediante la funcionalidad **Asignación masiva** en la página o bien, puede ir a cada empleado e indicar si la información de Ley de Cuidado de Salud Asequible necesita supervisarse y notificarla para ese empleado, así como asignar al empleado a un grupo de cobertura de Cuidado de Salud Asequible.

Si la información de la cobertura cuidado de salud asequible no necesita supervisarle ni notificarse con respecto a un empleado, por ejemplo si son empleados a tiempo parcial, el campo **Notificar cobertura** se puede establecer en No. Aunque cada empleado para el que se debe supervisar la información de la Ley de Cuidado de Salud Asequible debe estar asignado a un grupo de cobertura de cuidado de salud asequible, puede seguir cambiando las opciones **Oferta de cobertura**, **Parte del coste a cargo del empleado** y **Puerto seguro** para cualquier mes o meses que necesiten diferentes valores a los especificados en el grupo de cobertura de Cuidado de Salud Asequible.

Para especificar excepciones para cualquier grupo de cobertura de Cuidado de Salud Asequible, haga clic en el vínculo Cobertura de Cuidado de Salud Asequible en la página de detalles del trabajador que está bajo la sección de información adicional en la ficha Empleo.

## <a name="reporting-health-care-coverage"></a>Notificar cobertura de cuidad cuidado de salud
Además del seguimiento, qué pasaría si alguna cobertura de seguro médico se ofreciera a un empleado a jornada completa, si el empresario ofrece cobertura patrocinada por él mismo a los empleados inscritos (independientemente de si su estado es de empleo es a jornada completa o a tiempo parcial), será necesario notificar información adicional en el 1095-C. Cada empleado (incluidos los dependientes) cubierto por los planes de prestaciones patrocinados por el empresario deben incluirse en el informe durante los meses que estuvieron bajo cobertura. 

Puede indicar si cada plan de prestaciones debe notificarse seleccionando la casilla de verificación **Se informa para Ley de Cuidado de Salud Asequible**.

Además, si los empleados han elegido tener cualquiera de sus dependientes cubiertos bajo prestación puede indicar las fechas en las que estuvo cubierto el dependiente para cada empleado en la página Mantener beneficios. Para indicar que el dependiente estará cubierto con la prestación, elija el botón Editar en el panel de acciones de la FastTab Dependientes.

En la página **Administrador de fechas de la cobertura del dependiente**, puede indicar las fechas en el la prestación cubría al dependiente. Al especificar las fechas en esta página se selecciona automáticamente la casilla de verificación **Cubierto** en la página **Mantener beneficios** .

## <a name="generate-1095b-and-1095c-forms"></a>Generar los formularios 1095B y 1095C
También puede generar los formularios 109-B y 1095-C en el producto y los distribuirlos a cada uno de sus empleados. Si se generan electrónicamente el 1095-C y los archivos de transmisión 1094-C correspondientes que se pueden utilizar la presentación a la Agencia tributaria, también puede ser generado por el sistema.  

Al generar el formulario 1095-C, especifique el ejercicio fiscal adecuado e indique si deben enmascararse los números de seguridad sociales. Si está imprimiendo formularios 1095-C para más de 500 empleados, recibirá más de un archivo PDF. Está recomendado aumentar el **Tamaño máximo de archivo** en la ventana **Parámetros de la administración de documentos** a 150 MB.

## <a name="viewing-information"></a>Ver la información
Puede usar la página **Cobertura de cuidado de salud asequible del trabajador** para consultar qué empleados se han asignado a cada grupo de cobertura, qué empleados no necesitan incluirse en un informe y qué empleados no están sin asignar.

Si alguno de los valores predeterminados del grupo de cobertura de Cuidado de Salud Asequible se han anulado, aparecerá un asterisco junto al valor que se cambió. Si los valores para los 12 meses son iguales y no se han reemplazado, el valor se imprimirá en la columna **Todos los 12 meses**.

También puede usar la ventana de consultas para saber qué empleados se marcaron como que no se informan para Ley de Cuidado de Salud Asequible, lo que implica que no necesitará supervisar si se les ofreció cobertura y que no deberá emitirles un 1095-C al final del año. Si selecciona **No se informa para Ley de Cuidado de Salud Asequible** en el campo **Filtrar por** , puede generar una lista de todos los empleados que se han marcado para no recibir un 1095-C.

Además de ver una lista de empleados que no se informa para Ley de Cuidado de Salud Asequible, también puede ver los empleados que están sin asignar (el campo **Cobertura del informe de la Ley de Cuidado de Salud Asequible** está vacío) o que se hayan asignado a un grupo de la Ley de Cuidado de Salud Asequible que venció para el año seleccionado en el campo **Año**.

Puede exportar las listas de empleados generadas mediante cualquiera de las opciones de filtrado a Excel.

Si necesita informar a personas cubiertas porque como un empresario ofrece cobertura por sí mismo, también puede ver los dependientes cubiertos en los planes de prestaciones que se marcaron como **Se informa para Ley de Cuidado de Salud Asequible** seleccionando la acción dependiente de cobertura Ver dependiente en la franja del panel de acciones.

**Nota:** Solo las prestaciones cuyo se haya marcado como plan **Se informa para Ley de Cuidado de Salud Asequible** se mostrará en la ventana de consultas.
