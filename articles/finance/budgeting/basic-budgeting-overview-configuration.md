---
title: Visión general de Gestión presupuestaria
description: Casi todas las empresas que utilizan la funcionalidad de Financials en Microsoft Dynamics 365 Finance tendrán que poder crear informes de valores presupuestados frente a reales. En este artículo se explica la configuración mínima necesaria para crear presupuestos en finanzas y operaciones o cargarlos desde un programa de terceros.
author: panolte
ms.date: 04/29/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetParameters
audience: Application User
ms.reviewer: kfend
ms.custom:
- "60113"
- intro-internal
ms.assetid: 28a9793e-d376-47af-a345-69046bad17df
ms.search.region: global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 380afc399a050215bb2d7b1e5ddb20088226f654
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9068972"
---
# <a name="budgeting-overview"></a>Visión general de la gestión presupuestaria

[!include [banner](../includes/banner.md)]

Casi todas las empresas que utilizan la funcionalidad de Financials en Microsoft Dynamics 365 Finance tendrán que poder crear informes de valores presupuestados frente a reales. En este artículo se explica la configuración mínima necesaria para crear presupuestos en finanzas y operaciones o cargarlos desde un programa de terceros.

## <a name="overview"></a>Información general

El presupuesto aprobado para una entidad jurídica se mantiene en un documento que se conoce como un *asiento de registro presupuestario* Las líneas de un documento de asiento de registro presupuestario se conocen como entradas de *cuenta de presupuesto* y contienen información de dimensión financiera, fechas y los importes de presupuesto aprobados. El documento del asiento de registro presupuestario se integra con los informes financieros básicos y las páginas de consulta donde los importes reales del libro mayor se comparan con los importes presupuestarios. 

Hay varios métodos para crear asientos de registro presupuestario:

-   Especificar manualmente la información del documento en la página **Asientos de registro presupuestario**.
-   Use la plantilla de Microsoft Excel que puede abrir haciendo clic en el botón **Abrir en Excel** en la página **Asientos de registro presupuestario**.
-   Use la entidad de datos **Asientos contables presupuestarios** en la gestión de datos para importar asientos de registro presupuestario. Debe considerar usar este método y activar el parámetro **Procesamiento basado en conjuntos** cuando tiene que importar muchos asientos contables presupuestarios en el sistema.
-   Si la empresa usa la funcionalidad de planificación presupuestaria para preparar datos de presupuesto, puede usar el proceso periódico **Generar el asiento de registro presupuestario**.

El asiento de registro presupuestario se considera completado cuando se han actualizado los saldos presupuestarios. En la página **Asientos de registro presupuestario**, haga clic en **Actualizar saldos presupuestarios** para un asiento de registro presupuestario seleccionado o varios asientos. Tras actualizar los saldos presupuestarios, el estado del asiento de registro presupuestario cambia a **Completado**. El asiento de registro presupuestario completado no se puede abrir de nuevo para editar. Por lo tanto, si los datos presupuestarios se deben ajustar, debe crear un nuevo asiento de registro presupuestario en lugar de corregir los datos en el asiento de registro presupuestario completado.

## <a name="configuration"></a>Configuración
Cuando configura el presupuesto, inicie en la pagina **Parámetros de gestión presupuestaria**. En esta página, debe definir el diario de presupuesto, la secuencia numérica para los asientos de registro presupuestario y el comportamiento predeterminado en los espacios de trabajo.

A continuación, si hay directivas que rigen la aprobación de asientos de registro presupuestario, en función del tipo de presupuesto (por ejemplo, las transferencias o las revisiones), debe crear flujos de trabajo del asiento de registro presupuestario en la página **Flujos de trabajo de gestión presupuestaria**. Si hay situaciones en que las transferencias se pueden permitir sin necesidad de aprobación de flujo de trabajo, puede definir reglas de transferencia presupuestaria para admitir las situaciones. 

En la página **Dimensiones de la gestión presupuestaria**, debe seleccionar las dimensiones financieras que se usan para la gestión presupuestaria, en función de las dimensiones que se usan en el plan contable. Se pueden seleccionar todas las dimensiones financieras o un subconjunto para la gestión presupuestaria.

Defina un *modelo presupuestario* que corresponda a todos o a algunos presupuestos. Puede usar un único modelo presupuestario para todos los asientos de registro presupuestario. Como alternativa, puede crear modelos independientes basados en el tipo de presupuesto, la ubicación geográfica o algún otro modo en que un presupuesto puede ser clasificado. 

> [!NOTE] 
> Si se usa el control presupuestario, solo puede asociar un modelo presupuestario a un intervalo de tiempo del ciclo presupuestario concreto. 

Cree *códigos de presupuesto* que identifiquen el tipo de transacciones de presupuesto para registrar y cualquier flujo de trabajo relacionado. Los códigos de presupuesto pueden admitir los tipos de presupuesto siguientes:

-   Presupuesto original
-   Transferir
-   Revisión
-   Reserva de gasto
-   Pre-reserva de gasto
-   Presupuesto transferible

Los códigos presupuestarios le permiten tener una traza de auditoría de las modificaciones aprobadas del presupuesto a través del proceso del ciclo presupuestario. Si un flujo de trabajo está asociado a un código presupuestario, el flujo de trabajo estará activado para todos los asientos de registro presupuestario que usen dicho código presupuestario, y los pasos del flujo de trabajo se deben completar antes de que el asiento de registro presupuestario pueda alcanzar la fase de **Completado**.  

También puede configurar *reglas de transferencia presupuestaria*. Para usar reglas de transferencia presupuestaria, seleccione **Usar reglas para las transferencias presupuestarias** en la página **Parámetros presupuestarios**. Cuando se usan las reglas de transferencia presupuestaria, si un usuario crea un documento mediante un código presupuestario de tipo **Transferencia**, los saldos presupuestarios no se actualizarán si se infringen las reglas de transferencia presupuestaria. Por ejemplo, puede habilitar los documentos de transferencia presupuestaria en que el presupuesto de gastos se transfiere entre las cuentas principales para el departamento de ventas y marketing, pero puede prohibir que el presupuesto se transfiera a dicho departamento o desde el mismo a menos que la aprobación de flujo de trabajo se haya concedido para dicho tipo de asiento contable de presupuesto.

La funcionalidad que se introdujo en la versión 10.0.7 de Microsoft Dynamics 365 Finance (enero de 2020) agregó capacidad y flexibilidad para entradas de registro presupuestarias. Para permitir estas mejoras, vaya al espacio de trabajo **Administración de características** y seleccione **Asientos de registro presupuestario solo para cantidad** o **Valor predeterminado de entradas de registro presupuestario de tipo de importe**.

La característica **Asientos de registro presupuestario solo para cantidad** solo le permite registrar un asiento del registro de presupuestos con importes de solo cantidad. Por ejemplo, podría registrar un asiento de presupuesto con una cantidad de 32 y un precio de cero, lo que da lugar a un importe de cero. Puede usar esta cantidad en el contexto de un informe financiero para determinar un precio por cantidad. Tenga en cuenta que no se actualizó ninguna consulta o informe como parte de esta característica; la característica solo permite registrar un importe de cero.

La característica **Valor predeterminado de entradas de registro presupuestario de tipo de importe** permite que el tipo de importe predeterminado dentro de una entrada del registro presupuestario sea un tipo de importe distinto de gastos. La línea de entrada del registro presupuestario ahora se establecerá como predeterminada para gastos cuando el tipo de cuenta principal sea de gastos; se establecerá como predeterminada para ingresos cuando el tipo de cuenta principal sea de ingresos; y se establecerá como predeterminada para gastos para el resto de tipos de cuenta.

## <a name="using-workspaces-and-inquiry-pages-to-track-budget-vs-actuals"></a>Usar los espacios de trabajo y las páginas de consulta para realizar un seguimiento del presupuesto frente a gastos reales
El administrador de presupuestos puede revisar el estado actual de un presupuesto en el espacio de trabajo **Presupuestos contables y previsiones**. Las pestañas **Gastos sobre presupuesto** y **Ingresos bajo presupuesto** proporcionan una vista rápida de las combinaciones de dimensiones financieras en que los objetivos de presupuesto no se están resolviendo ni se están acercando al umbral. Puede personalizar el porcentaje del umbral del presupuesto y los conjuntos de dimensiones financieras que se usan en esas fichas haciendo clic en **Configurar mi espacio de trabajo**. Puede hacer clic en **Directores de unidad** en para ver qué trabajadores son los responsables de las combinaciones de dimensiones financieras específicas que están activadas en esas fichas. Por ejemplo, si observa que el presupuesto de gastos del departamento de operaciones está pasando el umbral de presupuesto, puede encontrar fácilmente y ponerse en contacto con el director de departamento de operaciones para hablar del problema. 

> [!NOTE] 
> El campo **Director de departamento** en la página **Unidades de organización** determina qué directores admiten combinaciones de dimensiones financieras específicas. Haga clic en **Ver más** en la parte inferior de la ficha para abrir la página de consulta **Presupuesto frente a gastos reales** para obtener más información sobre importes presupuestarios con importes reales. 

La página de consulta **Presupuesto frente a gastos reales** le permite explorar los detalles presupuestarios con los importes reales. Seleccione una línea en la página de consulta, y haga clic en **Saldos del período** para ver el presupuesto y los importes reales en los períodos fiscales. La página **Asientos contables presupuestarios** ofrece detalles del importe presupuestario en asientos de registro presupuestario. La página **Entradas del diario general** abre las transacciones contables que se incluyen en el importe calculado **Gastos reales**. 

Una empresa que está utilizando la funcionalidad de planificación presupuestaria puede crear y usar *previsiones presupuestarias* en el espacio de trabajo **Presupuestos contables y previsiones**.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]

