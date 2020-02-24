---
title: Proyectos de contratación masiva
description: Los proyectos de contratación masiva permiten a los especialistas de recursos humanos crear varios puestos y contratar de forma eficaz a varios trabajadores para ellos.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMMassHireProject
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.custom: 7481
ms.assetid: 5f5eb271-76eb-4305-bd1c-5d171dafccc9
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 209449fe8541f0f6a474b0125cbe6b3c0287b6e9
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010436"
---
# <a name="mass-hire-projects"></a>Proyectos de contratación masiva



Los proyectos de contratación masiva permiten a los especialistas de recursos humanos crear varios puestos y contratar de forma eficaz a varios trabajadores para ellos.

## <a name="overview"></a>Visión general

Use proyectos de contratación masiva cuando contrate varios trabajadores al mismo tiempo, como cuando se realizan contrataciones para cumplir una demanda de temporada. Crear un proyecto de contratación masiva resulta útil porque puede crear registros del puesto, registros del trabajador y asignaciones del trabajador para los puestos al mismo tiempo. Al crear puestos para un proyecto de contratación masiva, puede especificar la información siguiente:

- El número de posiciones que desea crear
- El tipo de trabajador de las personas que contratará para que ocupen los puestos
- El departamento y el trabajo que están asociados con los puestos
- El valor equivalente a jornada completa del puesto

## <a name="example"></a>Ejemplo

En el verano, usted contrata normalmente a 15-20 estudiantes universitarios a tiempo parcial para suplir las vacantes de prácticas disponibles en su empresa. Este año, desea contratar cinco contables, cinco procesadores de pedidos y cinco cajeros. En lugar de crear cada registro del puesto y del trabajador de forma independiente, creará un proyecto de contratación masiva denominado “SummerInterns". Las fechas de inicio y finalización del proyecto se correlacionan con las fechas de inicio y finalización de las duraciones de los puestos que cree para el proyecto de contratación masiva.

En la página **Proyectos de contratación masiva**, seleccione el proyecto “SummerInterns” y haga clic en **Abrir proyecto**. En el proyecto de contratación masiva abierto, haga clic en **Crear puestos** y especifique la información acerca del puesto de contable. Puede indicar que desea que se creen cinco puestos de contable con la misma información para cada uno y, a continuación, hacer clic en Aceptar. Repita este proceso para los puestos de procesador de pedidos y para el cajero.

Después de seleccionar los estudiantes que ocuparán los puestos en prácticas, especificará la información relativa al puesto en **Detalles del puesto**. Una vez especificados todos los detalles del puesto, seleccione el puesto en la página Proyectos de contratación masiva y haga clic en **Contratación**. Se creará un registro de puesto para cada puesto, y se creará y se asignará un registro de trabajador a la posición correcta para cada persona que contrate.

## <a name="mass-hire-project-statuses"></a>Estados del proyecto de contratación masiva

Un proyecto de contratación masiva puede tener los siguientes estados.

- Creado
- Abierta
- Cerrado

En la página **Proyecto de contratación masiva**, haga clic en **Abrir proyecto** o en **Cerrar proyecto** para cambiar el estado de un proyecto de contratación masiva. La siguiente tabla describe lo que puede hacer con un proyecto en función de su estado.

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
<td>No puede agregar los puestos al proyecto. Para agregar los puestos al proyecto de contratación masiva, abra el proyecto de nuevo. Éste es el estado de los proyectos completados.
<blockquote>[!NOTE] Antes de cerrar un proyecto de contratación masiva, todos los puestos en el proyecto deben tener estado Creado o Cerrado.</blockquote>
</td>
</tr>
</tbody>
</table>
