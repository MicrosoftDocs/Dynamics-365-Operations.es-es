---
title: Integración de acuerdos de servicio y proyectos
description: Cuando se trabaja con acuerdos de servicio y líneas de acuerdo de servicio, se usan los datos configurados en las áreas de administración de proyectos y contabilidad.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9a19a138cceb7db08216e1151eb92442691bc58d
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3202339"
---
# <a name="integration-for-service-agreements-and-projects"></a>Integración de acuerdos de servicio y proyectos 

[!include [banner](../includes/banner.md)]


Cuando se trabaja con acuerdos de servicio y líneas de acuerdo de servicio, se usan los datos configurados en las siguientes áreas en **Gestión de proyectos y contabilidad**.

## <a name="project-prices"></a>Precios de proyecto

El coste y el precio de ventas de una transacción de acuerdo de servicio derivan de la configuración del precio de coste que se aplica al proyecto asociado con el acuerdo de servicio. El coste y los precios de ventas se pueden configurar por proyecto, empleado y categoría. 

## <a name="project-validation"></a>Validación de proyecto

Los proyectos, empleados y categorías disponibles para la selección de una línea de acuerdo de servicio se pueden limitar mediante la configuración de la validación en **Gestión de proyectos y contabilidad**. Mediante la configuración de validación, se pueden combinar empleados, proyectos y categorías para el acceso de control. 

## <a name="project-line-properties"></a>Propiedades de la línea de proyecto

Automáticamente se especifica una propiedad de línea para una línea de acuerdo de servicio.

Las propiedades de línea se crean en el formulario **Propiedades de línea** en **Gestión de proyectos y contabilidad**. La propiedad de línea especificada en un acuerdo de servicio se asocia al proyecto seleccionado para el acuerdo de servicio y, consecuentemente, la línea de acuerdo de servicio la hereda. 

## <a name="default-offset-accounts"></a>Cuentas de contrapartida predeterminadas

Si se especifica una transacción de gastos, automáticamente se seleccionará una cuenta de contrapartida de gastos predeterminada para esa transacción. La cuenta de gastos predeterminada se configura para el proyecto asociado al acuerdo de servicio actual.

## <a name="project-categories"></a>Categorías de proyecto

Las categorías disponibles para las líneas de acuerdo de servicio se configuran en el formulario **Categorías de proyecto** en **Gestión de proyectos y contabilidad**. 

> [!NOTE]
> <P>Las categorías con la casilla de verificación <STRONG>Activo en los diarios</STRONG> activada en la ficha <STRONG>Proyecto</STRONG> del formulario <STRONG>Categorías de proyecto</STRONG>, están disponibles para la selección. Sin embargo, si se ha activado la casilla de verificación <STRONG>Categorías inactivas</STRONG> en la ficha <STRONG>Diarios</STRONG> del formulario <STRONG>Parámetros de gestión de proyectos y contabilidad</STRONG>, todas las categorías estarán disponibles para la selección.</P>

## <a name="project-parameters"></a>Parámetros del proyecto

Si el campo **Trabajadores terminados** en la pestaña **Diarios** en el formulario **Gestión de proyectos y contabilidad** está activado, se podrán seleccionar empleados inactivos además de empleados activos en los formularios **Acuerdos de servicio** y **Pedidos de servicio**.

Asimismo, se pueden habilitar los campos **Hora inicial** y **Hora final** en la ficha **Proyecto** en el formulario **Pedidos de servicio**, para especificar horas de inicio y de fin en las líneas de pedido de servicio.

## <a name="enable-the-starting-and-ending-time-feature-for-service-orders"></a>Habilitar la función de horas de inicio y fin para pedidos de servicio

1.  Haga clic en **Gestión de proyectos y contabilidad** \> **Configurar** \> **Parámetros de gestión de proyectos y contabilidad**.

2.  Haga clic en la pestaña **Diarios** , y seleccione la casilla de verificación **Mostrar horas de inicio y fin**.

3.  Haga clic en **Gestión de proyectos y contabilidad** \> **Configuración** \> **Diarios** \> **Nombres de diarios**.

4.  Seleccione el nombre del diario asociado con el pedido de servicio.

5.  Haga clic en la pestaña **General** , y seleccione la casilla de verificación **Mostrar horas de inicio y fin**.


> [!NOTE]
> <P>Seleccione el nombre del diario para el pedido de servicio en el campo <STRONG>Hora</STRONG> de la ficha <STRONG>Diarios</STRONG> del formulario <STRONG>Parámetros de la gestión de servicio</STRONG>.</P>





