---
title: "Créditos y cobros en Clientes"
description: "La información de los cobros de clientes se gestiona en una vista central con la página Cobros de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. Los administradores de crédito y cobros pueden usar esta vista central para gestionar los cobros. Los agentes de cobros pueden comenzar el proceso de cobro por las listas de clientes que se generan mediante criterios de cobro predefinidos o por la página Clientes."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustAgingSnapshot, CustBankAccounts, CustCollections, CustCollectionsActivitiesListPage, CustCollectionsAgent, CustCollectionsCaseListPage, CustCollectionsPool, CustCollectionsPoolsListPage, CustTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 3061
ms.assetid: fd851520-8d93-434b-845b-be127d6ac3a6
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: a071d3151fbcc9e29bd138b096b34b88bc405a4f
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="credit-and-collections-in-accounts-receivable"></a>Créditos y cobros en Clientes

[!include[banner](../includes/banner.md)]


La información de los cobros de clientes se gestiona en una vista central con la página Cobros de Finance and Operations. Los administradores de crédito y cobros pueden usar esta vista central para gestionar los cobros. Los agentes de cobros pueden comenzar el proceso de cobro por las listas de clientes que se generan mediante criterios de cobro predefinidos o por la página Clientes.

Antes de comenzar a configurar cobros o a trabajar con éstos, debe comprender los siguientes conceptos:
-   Las instantáneas de vencimiento de los clientes contienen información sobre saldos vencidos en un momento determinado.
-   Las secciones de clientes de cobros le ayudan a organizar su trabajo.
-   Los agentes de cobros tienen sus propias secciones de clientes.
-   En las páginas de lista, se organizan los clientes, las actividades y los casos de cobros.
-   Toda la información de cobros de un cliente se encuentra en una página, desde donde puede responder.
-   Condonar, restablecer o invertir interés y cuotas, todo se puede hacer en un paso.
-   Se pueden crear transacciones de cancelación en un paso.
-   Se pueden procesar pagos de fondos insuficientes (NSF) en un paso.

En las siguientes secciones, se describe cada concepto.

## <a name="customer-aging-snapshots"></a>Instantáneas de vencimientos de clientes
Una instantánea de vencimientos contiene los saldos vencidos calculados en un momento determinado. Esta información aparece en la página de lista Saldos vencidos y en la página Cobros. Es necesario crear una instantánea de vencimientos para poder visualizar información en las páginas de lista Cobros. 

Para cada cliente, las instantáneas de vencimientos contienen un encabezado de instantánea de vencimientos y los registros de detalle que corresponden a cada período de vencimiento en la definición de período de vencimiento. 

El encabezado de instantánea de vencimientos contiene el importe vencido total, el límite de crédito, el importe del albarán, el importe del pedido de ventas, el número de transacciones con conflicto y el importe total de las transacciones con conflicto para la cuenta de cliente. Todas las transacciones del cliente se incluyen al calcular estos importes. El importe vencido total, el límite de crédito, el importe del albarán y el importe del pedido de ventas aparecen en el cuadro informativo Información crediticia de la página Cobros. 

Para cada período de vencimiento de la definición de período de vencimiento, se crea un registro de detalle de la instantánea de vencimientos. Cada registro de detalles de las instantáneas de vencimiento contiene el id. del período de vencimiento y el importe total de las transacciones con las fechas del período de vencimiento. Las transacciones tienen asignado un período de vencimiento, como 30 días pasados desde el vencimiento. La fecha está relacionada con la fecha de Vencimiento a partir de especificada al crear la instantánea de vencimientos. Esta información se muestra en la página de lista Saldos vencidos y en el cuadro informativo Saldos vencidos de la página Cobros.

## <a name="collections-customer-pools"></a> Secciones de cobros de clientes
Las secciones de clientes son consultas que definen un grupo de registros de cliente que se pueden mostrar y gestionar para cobros o procesos de vencimiento. Use las secciones de clientes para filtrar información en las páginas Saldos vencidos, Actividades de cobros y Casos de cobros. También se usan las secciones de clientes para filtrar las cuentas de cliente que se incluyen al crear instantáneas de vencimientos.

## <a name="collections-agents"></a>Agentes de cobros
De forma predeterminada, los usuarios de Microsoft Dynamics 365 for Finance and Operations pueden ver toda la información de los clientes en las páginas de listas de cobros. Puede usar los registros de agente de cobros para determinar las secciones de clientes disponibles para filtrar la información de las páginas de listas de cobros y en la página Cobros. 

El agente de cobros es una persona que trabaja con clientes para asegurarse de que los pagos se cobran a tiempo. En Finance and Operations, los agentes de cobros son trabajadores asignados a usuarios en la página Configuración de usuario.

## <a name="collections-list-pages"></a> Páginas de listas Cobros 
En las siguientes páginas de lista, se le ayuda a organizar la información de cobros.
-   Saldos vencidos: las columnas de la página de la lista muestran los saldos de los clientes y los importes vencidos por período de vencimiento. Esta información se almacena como una instantánea de vencimientos. Los períodos de vencimiento se determinan por la definición de período de vencimiento que se use. La definición del período de vencimiento se toma de la sección de clientes, si se ha especificado una para la consulta de secciones. Si la sección no tiene definición de período de vencimiento, se usará la definición de período de vencimiento predeterminada que se haya especificado en la página Parámetros de clientes. Si no se especifica ninguna definición de período de vencimiento predeterminada, se usa la primera definición de período de vencimiento de la página Definiciones de período de vencimiento.
-   Actividades de cobros: en las columnas de la página de lista, se muestran las actividades identificadas como actividades de cobros. Estas actividades se crean mediante el uso de la página Cobros. Use actividades para realizar un seguimiento del trabajo que realiza en relación con los cobros.
-   Casos de cobros: en las columnas de la página de lista, se muestra información de los casos que tengan una categoría de caso cuyo tipo de caso sea Cobros.

> [!NOTE]
> Es necesario crear una instantánea de vencimientos antes de que pueda visualizar información en estas páginas de lista. Sólo se muestra información para aquellos clientes para los que se haya creado una instantánea de vencimientos. Los registros que se muestran en la página de lista pueden estar más filtrados, por ejemplo:
<li>De forma predeterminada, un usuario de Finance and Operations tiene acceso a todos los clientes que dispongan de una instantánea de vencimientos.</li>
<li>Si existen secciones de clientes, es necesario configurar un usuario como agente de cobros para que pueda usar las secciones para filtrar información de páginas de listas de cobros. El acceso a esta información está limitado a los clientes incluidos en la sección de clientes seleccionada.</li>
<li>Si un usuario está configurado como agente de cobros, sólo estarán disponibles en la página de lista las secciones seleccionadas para dicho agente de cobros. Si se ha seleccionado Permitir que el agente vea todas las secciones de clientes en la página Agente de cobros para el agente de cobros, todas las secciones quedan disponibles para dicho agente.</li>


## <a name="collections-page"></a> Página Cobros
Use la página Cobros para ver, administrar y actuar en la información de cobros, actividades y casos de un cliente. 

En el panel superior, se muestran los casos del cliente seleccionado. En el panel intermedio se muestran las transacciones del cliente. En el panel inferior, se muestran las actividades del cliente. Puede crear casos de cobros para realizar seguimientos de la información de cobros de una o varias transacciones y actividades. La información que aparece en la parte superior y en los paneles inferiores se puede filtrar por caso. 

En los cuadros informativos, se muestran los saldos vencidos y la información de límite de crédito para el cliente seleccionado. Esta información se almacena en la instantánea de vencimientos. En caso necesario, puede actualizar la instantánea de vencimientos con información actual. 

El panel de acciones contiene los botones que muestran información relacionada para el cliente, el caso, la transacción o la actividad seleccionada. También puede realizar acciones comunes, como cambiar el estado de cobros de una transacción, enviar mensajes de correo electrónico por medio de la integración con su proveedor de correo electrónico, realizar reembolsos a clientes, procesar pagos NSF y cancelar saldos incobrables.

## <a name="waive-reinstate-or-reverse-interest-and-fees"></a> Condonar, restablecer o revertir interés y cuotas
Puede renunciar, restablecer o invertir notas de interés completas, o las cuotas e intereses de la transacción que forman parte de las notas de interés. Puede hacerlo desde la ficha Cobrar en el panel de acciones de la página de lista Todos los clientes al hacer clic en Nota de interés, Interés de transacción o Cuota. 

Estos ajustes sólo afectan a las notas de interés, así como a los intereses y cuotas incluidos en éstos. Realice los pasos descritos en la sección “Crear transacciones de cancelación en un paso” para cancelar todos los cargos que debe un cliente.

Para obtener más información, consulte [Crear un código de interés con un intervalo](tasks/create-interest-code-range.md) y [Interés del proceso](tasks/process-interest.md). 

## <a name="create-writeoff-transactions"></a>Creación de transacciones de cancelación
Puede cancelar deudas incorrectas haciendo clic en Cancelar en el formulario Cobros y en las páginas de listas Saldos vencidos, Clientes y Facturas de cliente abiertas. 

Al cancelar transacciones para un cliente, todas las transacciones del cliente se marcan automáticamente para liquidación. El importe que se cancela depende del importe neto de las transacciones marcadas. La transacción de cancelación se crea en un diario general, que puede contener hasta tres tipos de líneas de diario.

-   El primer tipo de línea de diario contiene la entrada de cancelación del cliente. Si las transacciones marcadas contienen varias combinaciones de códigos de divisa, dimensiones y perfiles de registro, se crea una línea de diario independiente para cada combinación.
-   El segundo tipo de línea de diario contiene la entrada de cancelación del libro mayor. Si las transacciones marcadas contienen varias combinaciones de códigos de divisa, dimensiones y perfiles de registro, se crea una línea de diario independiente para cada combinación.
-   El tercer tipo de línea del diario contiene información de cancelación del libro mayor para los impuestos sobre las ventas. Esta línea de diario se crea solo si se ha seleccionado Impuestos independientes en la página Parámetros de clientes. Si las transacciones marcadas contienen varias combinaciones de cuentas a pagar de impuestos sobre las ventas, dimensiones y códigos de impuestos sobre las ventas, se crea una línea de diario independiente para cada combinación.

La transacción de cancelación se crea en la divisa de la transacción.

Para obtener más información, consulte [Crear un diario de cancelación para un cliente](tasks/create-write-off-journal-customer.md).

<a name="process-not-sufficient-funds-nsf-payments"></a>Procesamiento de pagos de fondos insuficientes (NSF)  
--------------------------------------------

Puede procesar pagos NSF haciendo clic en Pago NSF en la página Cobros. Al hacer clic en este botón, se cancela el pago. Si se aplica una cuota NSF para el cliente, se creará una transacción de cargos en un diario de pagos. El importe de la cuota se basa en la configuración de los cargos automáticos. Los cargos automáticos que se aplican para los pagos NSF se especifican en función del grupo de cargos seleccionado en la página Cuentas bancarias de la cuenta bancaria afectada.






