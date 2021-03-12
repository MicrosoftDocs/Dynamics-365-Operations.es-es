---
title: Calendarios fiscales, ejercicios y períodos
description: En este artículo se describen los calendarios fiscales, los ejercicios y los períodos y cómo usarlos para entidades jurídicas, activos fijos y gestión presupuestaria.
author: aprilolson
manager: AnnBe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FiscalCalendars
audience: Application User
ms.reviewer: roschlom
ms.custom: 25851
ms.assetid: a968a5e5-585e-4389-aa4e-c885a7e23413
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f40dc7227d8ee9ccc45336e9b8968937ef5f6092
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995349"
---
# <a name="fiscal-calendars-fiscal-years-and-periods"></a>Calendarios fiscales, ejercicios y períodos

[!include [banner](../includes/banner.md)]

En este artículo se describen los calendarios fiscales, los ejercicios y los períodos y cómo usarlos para entidades jurídicas, activos fijos y gestión presupuestaria.

Los calendarios fiscales proporcionan un marco para las actividades financieras de una organización. Cada calendario fiscal contiene uno o más años fiscales y cada ejercicio contiene varios períodos. Los calendarios fiscales se pueden basar en un año natural del 1 de enero al 31 de diciembre o en cualquier fecha que seleccione. Por ejemplo, algunas organizaciones seleccionan un calendario fiscal que comienza el 1 de julio de un año y finaliza el 30 de junio del año siguiente. 

No hay ningún límite en el número de calendarios fiscales que se pueden crear ni tampoco en el número de años fiscales que se pueden crear para un calendario fiscal. Cada calendario fiscal es independiente de la organización y lo pueden usar varias entidades jurídicas de la organización. Por ejemplo, una organización tiene ocho departamentos y cada departamento es una entidad jurídica independiente. Cinco de ellos comparten el mismo calendario fiscal y tres utilizan calendarios fiscales distintos. Puede crear un calendario fiscal para las cinco entidades jurídicas que compartan el mismo calendario fiscal y, a continuación, crear calendarios fiscales independientes para las demás entidades jurídicas.

## <a name="create-fiscal-calendars-fiscal-years-and-periods"></a>Crear calendarios y años fiscales, y períodos
Puede crear y eliminar calendarios, ejercicios y períodos fiscales en la página Calendarios fiscales. También puede dividir los períodos existentes y crear períodos de cierre que se pueden utilizar para cerrar un ejercicio. 

Se usan los períodos de cierre para separar las transacciones del libro mayor que se generan al cerrar un ejercicio. Cuando las transacciones de cierre se encuentran en un período fiscal, resulta más fácil crear informes financieros que incluyan o excluyan diferentes tipos de entradas de cierre. Si un ejercicio se divide en 12 períodos fiscales, el período de cierre suele ser el período número 13. No obstante, se puede crear un período de cierre a partir de cualquier período cuyo estado sea Abierto. 

Al crear un período de cierre, seleccione un período cuyo estado sea Abierto y que contenga las fechas que desee usar. El nuevo período de cierre copiará las fechas inicial y final del período existente. El período original seguirá existiendo. Por ejemplo, selecciona Período 12, que es el último período del ejercicio y cuenta con las fechas comprendidas entre el 1 y el 31 de agosto. Especifica un nombre para el período de cierre, como Cierre. Tras la creación del nuevo período de cierre, dispondrá del período original y del período de cierre. Ambos cuentan con las fechas comprendidas entre el 1 y el 31 de agosto.

## <a name="select-fiscal-calendars-for-ledgers-fixed-assets-and-budget-cycles"></a>Seleccionar los calendarios fiscales para los ciclos presupuestarios, activos fijos y para la contabilidad
Los calendarios fiscales se usan con la depreciación de activos fijos, transacciones financieras y ciclos presupuestarios. Una vez creado un año fiscal, puede utilizarlo para distintos fines. Puede seleccionar un calendario fiscal para un libro de activo fijo para convertirlo en un calendario de activos fijos. Puede seleccionar un calendario fiscal para un libro mayor para convertirlo en un calendario contable. También puede seleccionar un calendario fiscal para un ciclo de presupuesto para convertirlo en un calendario de presupuesto. Puede utilizar el mismo calendario fiscal para todo esto.

### <a name="select-a-fiscal-calendar-for-your-legal-entity"></a>Seleccionar un calendario fiscal para la entidad jurídica

Seleccione el calendario fiscal que desea utilizar para el libro mayor en la entidad jurídica del formulario Libro mayor. Es necesario seleccionar un calendario fiscal en la página Libro mayor para cada entidad jurídica. Tras seleccionar un calendario fiscal, puede establecer permisos y estados de períodos en la página Calendario contable para cualquier período que forme parte de un ejercicio.

### <a name="select-a-fiscal-calendar-for-fixed-assets"></a>Seleccionar un calendario fiscal para los activos fijos

Puede seleccionar un calendario fiscal para un libro de activo fijo que vayan a utilizar los activos fijos que usan el libro seleccionado. Puede seleccionar cualquier calendario fiscal definido en la página Calendarios fiscales.

### <a name="define-budget-cycle-time-spans"></a>Definir intervalos de tiempo del ciclo presupuestario

Los ciclos de presupuesto hacen referencia al tiempo durante el que se usa un presupuesto. Los ciclos de presupuesto pueden incluir una parte del ejercicio o varios años fiscales, como el ciclo de presupuesto bienal de dos años o un el ciclo de presupuesto trienal de tres años. El intervalo de tiempo del ciclo presupuestario define el número de períodos que se incluyen en el ciclo de presupuesto. Para especificar el intervalo de tiempo del ciclo presupuestario, use la página Intervalos de tiempo del ciclo presupuestario.

## <a name="maintain-periods-for-your-organization"></a>Mantener períodos para la organización
Puede utilizar la página Calendario contable para ver los detalles del calendario, los ejercicios y los períodos fiscales que utiliza su organización. También puede modificar el estado de los períodos y seleccionar qué usuarios pueden registrar transacciones contables en los períodos. Por ejemplo, al inicio de un nuevo período, es posible que desee que un grupo de usuarios terminen de registrar las transacciones financieras en el período previo mientras otros grupos trabajan únicamente en el nuevo período.





