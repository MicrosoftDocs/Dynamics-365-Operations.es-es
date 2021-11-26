---
title: Proyectos de contratación masiva
description: Este tema describe los proyectos de contratación masiva, que permiten a los especialistas de recursos humanos crear varios puestos y contratar de forma eficaz a varios trabajadores para ellos.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMMassHireProject, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7481
ms.assetid: 5f5eb271-76eb-4305-bd1c-5d171dafccc9
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6e0a8bba2227136995542d08f4b3f1e9d6d48ad5
ms.sourcegitcommit: e91a1797192fd9bc4048b445bb5c1ad5d333d87d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2021
ms.locfileid: "7728694"
---
# <a name="mass-hire-projects"></a>Proyectos de contratación masiva

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Los proyectos de contratación masiva permiten a los especialistas de recursos humanos crear varios puestos y contratar de forma eficaz a varios trabajadores para ellos.

## <a name="overview"></a>Visión general

Use proyectos de contratación masiva cuando contrate varios trabajadores al mismo tiempo, como cuando se realizan contrataciones para cumplir una demanda de temporada. Crear un proyecto de contratación masiva resulta útil porque puede crear registros del puesto, registros del trabajador y asignaciones del trabajador para los puestos al mismo tiempo. Al crear puestos para un proyecto de contratación masiva, puede especificar la información siguiente:

- El número de posiciones que desea crear
- El tipo de trabajador de las personas que contratará para que ocupen los puestos
- El departamento y el trabajo que están asociados con los puestos
- El valor equivalente a jornada completa del puesto

## <a name="example"></a>Ejemplo

En el verano, usted contrata normalmente a 15-20 estudiantes universitarios a tiempo parcial para suplir las vacantes de prácticas disponibles en su empresa. Este año, desea contratar cinco contables, cinco procesadores de pedidos y cinco cajeros. En lugar de crear cada registro del puesto y del trabajador de forma independiente, creará un proyecto de contratación masiva denominado “SummerInterns". Las fechas de inicio y finalización del proyecto se correlacionan con las fechas de inicio y finalización de las duraciones de los puestos que cree para el proyecto de contratación masiva.

En la página **Proyectos de contratación masiva**, seleccione el proyecto **SummerInterns** y haga clic en **Abrir proyecto**. En el proyecto de contratación masiva abierto, seleccione **Crear puestos** y especifique la información acerca del puesto de contable. Puede indicar que desea que se creen cinco puestos de contable y que se debe usar la misma información para cada uno. A continuación seleccione **Aceptar**. Repita este proceso para los puestos de procesador de pedidos y para el cajero.

Después de seleccionar los estudiantes que ocuparán los puestos en prácticas, especificará la información relativa al puesto en los detalles del puesto. Una vez especificados todos los detalles del puesto, seleccione el puesto en la página **Proyectos de contratación masiva** y seleccione **Contratación**. Se creará un registro de puesto para cada puesto, y se creará y se asignará un registro de trabajador a la posición correcta para cada persona que contrate.

## <a name="mass-hire-project-statuses"></a>Estados del proyecto de contratación masiva

Un proyecto de contratación masiva puede tener los siguientes estados.

- Creada
- Pendiente
- Cerrado

En la página **Proyecto de contratación masiva**, seleccione **Abrir proyecto** o **Cerrar proyecto** para cambiar el estado de un proyecto de contratación masiva. La siguiente tabla describe lo que puede hacer con un proyecto en función de su estado.

<table>
<thead>
<tr>
<th>Estado</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr>
<td>Creado</td>
<td>Puede crear y modificar la información, pero no puede crear posiciones para el proyecto. Éste es el estado predeterminado para los proyectos nuevos.</td>
</tr>
<tr>
<td>Abierta</td>
<td>Puede modificar los detalles del proyecto, crear los puestos del proyecto de contratación masiva y contratar a las personas para los puestos. Éste es el estado de los proyectos activos.</td>
</tr>
<tr>
<td>Cerrado</td>
<td><p>No puede agregar los puestos al proyecto. Para agregar los puestos al proyecto de contratación masiva, abra el proyecto de nuevo. Éste es el estado de los proyectos completados.</p>
<p><strong>Nota:</strong> Antes de cerrar un proyecto de contratación masiva, todos los puestos en el proyecto deben tener estado <b>Creado</b> o <b>Cerrado</b>.</p>
</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
