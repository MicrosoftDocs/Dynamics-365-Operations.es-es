---
title: Visión general del control presupuestario
description: Este artículo presenta el control presupuestario y proporciona información para ayudarle a configurar el control presupuestario en Microsoft Dynamics 365 Finance de manera que pueda gestionar los recursos financieros.
author: ShylaThompson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetControlConfiguration
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 60493
ms.assetid: be964167-43bc-431d-9adb-48bff32d68d5
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 464fd211eb5417265f8c737b23456769137a7c13
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772683"
---
# <a name="budget-control-overview"></a>Visión general del control presupuestario

[!include [banner](../includes/banner.md)]

Este artículo presenta el control presupuestario y proporciona información para ayudarle a configurar el control presupuestario de manera que pueda gestionar los recursos financieros.

<a name="overview"></a>Visión general
--------

El control presupuestario admite la administración de los recursos financieros de una organización a través del plan de cuentas, los flujos de trabajo, los grupos de usuarios, los documentos de origen y los diarios, el cálculo configurable de los fondos disponibles, los ciclos presupuestarios y los umbrales. Cuando los controles están vigentes, una organización puede planear, medir, gestionar y realizar una previsión de sus recursos financieros en su ejercicio. 

Una vez se hayan aprobado los presupuestos en Microsoft Dynamics 365 Finance, puede usar planes presupuestarios para generar asientos de registro presupuestario para registrar el presupuesto de gastos para una organización. También puede crear o importar asientos de registro presupuestario desde un programa de terceros en lugar de usar la funcionalidad de planificación presupuestaria. 

Los gastos se pueden registrar mediante cuentas principales y dimensiones financieras. Puede configurar el control del gasto total para cumplir las directivas y los requisitos de la organización agrupando combinaciones de dimensiones financieras y cuentas principales. 

El gráfico siguiente muestra el lugar del control presupuestario en las etapas de un ciclo presupuestario normal.

[![Ciclo de presupuesto típico](./media/budgetingcycle-300x198.png)](./media/budgetingcycle.png) 

Puede configurar el control presupuestario de acuerdo con varios factores:

-   **Dimensiones financieras**: ¿qué dimensiones financieras se deben usar para los informes de presupuesto y de los valores reales y ¿qué dimensiones financieras son necesarias para controlar el presupuesto? ¿Hay combinaciones de dimensiones específicas o cuentas principales que requieren una atención concreta? Por ejemplo, ¿hay un requisito de seguimiento del presupuesto para los valores reales por centro de coste y programa? ¿Requieren los gastos de viajes una atención especial?
-   **Tiempo**: ¿Qué período de tiempo (período fiscal, período fiscal hasta la fecha, etc.) se usará para evaluar los fondos presupuestarios disponibles?
-   **Documentos de origen** – ¿Qué documentos de origen se deben evaluar para el control presupuestario? ¿¿Los documentos se debe evaluar por línea o por documento?
-   **Cálculo de fondos disponibles**: ¿Se deben considerar los documentos como las solicitudes de compra (pre-reserva de gasto) y los pedidos de compra (reservas de gastos) en el cálculo de los fondos disponibles? ¿Se deben considerar los documentos con estado de borrador en el cálculo?
-   **Permiso de anulación**: ¿Quién tiene permiso para superar el presupuesto disponible?

El control presupuestario se integra plenamente con la aplicación. Por tanto, puede evaluar el presupuesto disponible tanto para las compras planificadas como para las compras reales. Los informes y las consultas de presupuesto están disponibles. Por tanto, los usuarios pueden evaluar el presupuesto a lo largo del ciclo presupuestario y, a continuación, puede realizar ajustes necesarios, en forma de transferencias o revisiones presupuestarias. Un director de presupuestos también puede exportar el presupuesto y los valores reales en Microsoft Excel para analizar mejor y realizar la previsión según sea necesario.

## <a name="configuring-budget-control"></a>Configuración del control presupuestario
### <a name="budget-cycle-time-span"></a>Intervalo de tiempo del ciclo presupuestario

Tras la configuración de la gestión presupuestaria básica, puede definir la hora o los períodos de inicio y fin para la gestión presupuestaria y el control presupuestario en la página **Intervalo de tiempo del ciclo presupuestario**. Los ciclos presupuestarios a menudo se corresponden con los calendarios fiscales pero pueden abarcar ejercicios.

Los siguientes pasos de la configuración se completan en las diversas pestañas de la página **Configuración de control presupuestario**.

### <a name="define-parameters"></a>Definir parámetros

De acuerdo con las dimensiones financieras habilitadas para el presupuesto, puede usar todas las dimensiones financieras o un subconjunto de las mismas para el control presupuestario. 

Además, puede especificar el intervalo de tiempo predeterminado (por ejemplo, **Ejercicio**, **Ejercicio hasta la fecha**, **Período fiscal** o **Trimestral**) para el que se llevará a cabo el control presupuestario en el intervalo de tiempo del ciclo presupuestario relacionado. También puede especificar un director de presupuestos predeterminado y el umbral que se usa para notificar a los usuarios cuando se ha alcanzado el umbral. Los valores de estos campos se usarán como valores predeterminados en cualquier nueva regla de control presupuestario o grupo presupuestario que se cree. Sin embargo, los valores predeterminados se pueden cambiar para las reglas o los grupos individuales. 

Las maneras en que se crean y se registran los presupuestos en el registro presupuestario ayudan a determinar el intervalo de tiempo que se selecciona al evaluar los fondos presupuestarios disponibles. Si se desarrolla y se usa un importe anualizado para una combinación de valores de dimensión, pueden tener sentido un enfoque de ejercicio o de ejercicio hasta la fecha. Sin embargo, si una organización que crea presupuestos por período fiscal o lo asigna a períodos fiscales desea un control más detallado, pueden que deseen considerar intervalos de tiempo trimestrales o de período hasta la fecha fiscales. 

Además, la cultura de una organización en relación con los presupuestos y el control presupuestario también ayuda a definir la configuración.

### <a name="over-budget-permissions"></a>Permisos de presupuesto excedido

A continuación, en la pestaña **Permisos de presupuesto excedido**, puede especificar grupos de usuarios. También puede especificar si los usuarios que son miembros de un grupo tienen permiso para superar el presupuesto. Puede evitar que los usuarios superen el presupuesto más allá del umbral de presupuesto que se estableció en la página **Parámetros presupuestarios** o puede evitar que superen el presupuesto en cualquier importe, independientemente del umbral. En función de cómo sea de proactiva la gestión de una organización de su gasto, estos permisos pueden ayudarle a gestionar sus recursos financieros. 

### <a name="budget-funds-available"></a>Fondos presupuestarios disponibles

A continuación, en la pestaña **Fondos presupuestarios disponibles**, puede definir la fórmula que se usa para calcular los fondos presupuestarios disponibles. En función de como sea de conservadora la gestión de una organización de sus recursos financieros, o en función de las normas o a los requisitos del sector, el cálculo puede incluir el borrador o los documentos no registrados. 

> [!NOTE] 
> Si este cálculo se modifica durante el ciclo presupuestario, los cambios no afectarán a los documentos que pasaron anteriormente las comprobaciones de control presupuestario y que se registraron o completaron.

### <a name="documents-and-journals"></a>Documentos y diarios

A continuación, en la pestaña **Documentos y diarios**, puede seleccionar qué documentos de origen y diarios estarán sujetos a comprobaciones de control presupuestario y si las comprobaciones se producirán en el nivel de la entrada de línea o para el documento completo. 

Los documentos de origen que se seleccionen deben coincidir con las casillas para los saldos que se incluyen en el cálculo de los fondos presupuestarios disponibles. Por ejemplo, si ha seleccionado **Reservas de presupuesto para reservas de gasto**, debe seleccionar la opción **Pedidos de compra**. Al realizar una comprobación presupuestaria con los importes y las cuentas de una línea de compra, se asigna a la reserva la categoría de control presupuestario **Reserva de gasto**. Al realizar una comprobación presupuestaria con los importes y las cuentas de una solicitud de compra, la categoría de control presupuestario que se asigna a la reserva es **Pre-reserva de gasto**. 

Si se incluyen **Reservas de presupuesto para reservas de gasto** y/o **Reservas de presupuesto para pre-reservas de gasto** en el cálculo de los fondos presupuestarios disponibles y se deben reflejar a través de los registros en la contabilidad general, debe habilitar el compromiso contable asumido en la página **Parámetros de Contabilidad general**.  

### <a name="assign-budget-models"></a>Asignar modelos presupuestarios

A continuación, en la pestaña **Asignar modelos presupuestarios**, asigne modelos presupuestarios a intervalos de tiempo del ciclo presupuestario que se debe incluir en el control presupuestario.

### <a name="define-budget-control-rules"></a>Definir reglas de control presupuestario

A continuación, en la página **Definir reglas de control presupuestario**, debe crear reglas específicas basadas en dimensiones financieras habilitadas con control presupuestario. Por ejemplo, si el enfoque se basa en el gasto o el intervalo de gastos para un departamento, puede usar la configuración de esta pestaña para definir y evaluar esos gastos. Puede definir distintos umbrales para cada regla de control presupuestario. 

> [!Important]
> El control presupuestario se habilitará para cualquier cuenta principal del tipo **Pérdidas y ganancias**, **Gasto**, **Ingresos, Balance de situación, Recursos propios** o **Activo**. Si esta pestaña contiene una regla con criterios vacíos, el control presupuestario se habilitará para **todas** las combinaciones de dimensiones financieras que incluyen las cuentas principales de esos tipos. Por lo tanto, asegúrese de que crea reglas de control presupuestario que definan solo los intervalos de combinaciones de dimensiones financieras donde es importante que el control presupuestario esté activado.  

### <a name="select-main-accounts"></a>Seleccionar cuentas principales

Si la opción **Cuenta principal** no está seleccionada como dimensión de control presupuestario en la página **Definir parámetros**, pero se están gestionando los gastos específicos, puede seleccionar esos gastos en la pestaña **Seleccionar cuentas principales**. Si la **cuenta principal** se selecciona como una dimensión de control presupuestario, no es necesaria ninguna entrada.  

### <a name="define-budget-groups"></a>Definir grupos presupuestarios

A continuación, en la pestaña **Definir grupos presupuestarios**, puede definir opcionalmente combinaciones únicas de dimensiones financieras en las que los recursos presupuestarios se agrupan para la comprobación presupuestaria secundaria. Puede crear un registro único que incluya toda la organización o definir varios grupos para representar departamentos o centros de costes individuales.  

### <a name="define-message-levels"></a>Definir niveles de mensaje

Si se deben suprimir los mensajes de advertencia de control presupuestario para cualquier grupo de usuarios, puede especificar dichos grupos en la página **Definir niveles de mensaje**. Los miembros de los grupos de usuarios continuarán recibiendo mensajes de error cuando superen los fondos de presupuesto disponibles, en función de los permisos de presupuesto excedido.

### <a name="activate-budget-control"></a>Activar control presupuestario

Una vez se haya configurado el control presupuestario, puede activarlo en la pestaña **Activar control presupuestario**. La versión de borrador será efectiva.
> [!Important]
> Una vez el control presupuestario esté activado y activo, y una vez se registren las transacciones, no se debe desactivar a mediados de año. Cuando se desactiva el control presupuestario, no se registran las actividades para fines de control presupuestario y ya no se realizan las comprobaciones presupuestarias. Por tanto, es posible que los documentos que ya se han registrado no reflejen correctamente saldos o importes de liberación en consultas e informes relacionados con el control presupuestario. Entre estos se incluyen las estadísticas de control presupuestario para cualquier documento y diario descendente o de ajuste. 

Además, tenga en cuenta que las transacciones, incluidos los asientos de registro presupuestario, que se han registrado antes de que se active el control presupuestario no se consideran para el control presupuestario. Por tanto, es una buena idea activar el control presupuestario solo al principio de un nuevo ciclo presupuestario. Asegúrese de que las entradas de registro presupuestario que contienen saldos presupuestarios iniciales para control presupuestario actualizan sus saldos presupuestarios solo después de que se active el control presupuestario. Se comprobará cualquier documento abierto (por ejemplo, un pedido de compra) para fondos presupuestarios disponibles y obtendrá una reserva de presupuesto para control presupuestario cuando el usuario desencadene manualmente una comprobación de control presupuestario en el documento.

## <a name="using-budget-control"></a>Uso de control presupuestario
Una vez que se activa el control presupuestario, los usuarios recibirán mensajes de error y advertencia del control presupuestario en los documentos y los diarios configurados para el control presupuestario. Recuerde que puede configurar el control presupuestario para poder advertir a los usuarios cuando superan los fondos presupuestarios, pero pueden continuar confirmando o registrando la transacción. Los usuarios pueden ver los detalles de las comprobaciones presupuestarias con error en la página **Errores y advertencias del control presupuestario**.   

En esta página, los usuarios pueden explorar la página **Estadísticas de control presupuestario por periodo** para ver los detalles de disponibilidad y las reservas para una combinación de dimensión de control de presupuesto seleccionada. Los usuarios también pueden explorar la página **Estadísticas de control presupuestario** para ver la disponibilidad de presupuesto para todas las combinaciones de dimensiones financieras que se usan en el control presupuestario. 

Si se activa el control presupuestario para los pedidos de compra, el director de presupuestos puede usar el espacio de trabajo **Presupuestos y previsiones contables** para revisar la cola de todos los pedidos de compra que tienen errores y advertencias de comprobación presupuestaria. Si el director de presupuestos tiene permisos de presupuesto excedido configurados, puede confirmar los pedidos de compra directamente en el espacio de trabajo.    
