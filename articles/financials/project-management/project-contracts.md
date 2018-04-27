---
title: Contratos de proyecto
description: "Este tema describe y proporciona ejemplos de contratos de proyecto que puede crear para diversos tipos de proyectos y fuentes de financiación, y cómo puede administrar contratos y clientes de proyecto de facturación en Microsoft Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjProjectContractsListPage, ProjProjectsListPage
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 23561
ms.assetid: bfd18d9b-d9a6-4e21-bc95-bf4af45f617f
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: e46393b9ac8797bf12cca12099d177980b75ba38
ms.contentlocale: es-es
ms.lasthandoff: 03/26/2018

---

# <a name="project-contracts"></a>Contratos de proyecto

[!INCLUDE [banner](../includes/banner.md)]

Este artículo describe y proporciona ejemplos de contratos de proyecto que puede crear para diversos tipos de proyectos y fuentes de financiación, y cómo puede administrar contratos y clientes de proyecto de facturación en Microsoft Dynamics 365 for Finance and Operations.

El tipo de proyecto que cree para un contrato de proyecto determinará el método de facturación usado para los clientes del proyecto. Puede cambiar un contrato de proyecto y el proyecto relacionado, pero no puede cambiar el tipo de proyecto. 

Al utilizar el contrato del proyecto, puede facturar uno o varios proyectos al mismo tiempo. El contrato de proyecto también ayuda a garantizar un procedimiento de facturación coherente para cada subproyecto de una estructura de proyectos. 

Cada proyecto que se facturará se debe asociar a un contrato de proyecto. La configuración para un contrato de proyecto se aplica a todos los proyectos y subproyectos asociados a ese contrato de proyecto. 

En un contrato de proyecto se puede especificar una o más fuentes de financiación. Por tanto, puede dividir la facturación entre varios proveedores de fondos, configurar los límites de financiación para que la factura a las fuentes de financiación no incluyan importes superiores a los especificados y configurar reglas de financiación para el cargo de gastos.

## <a name="funding-for-project-contracts"></a>Financiación para contratos de proyecto
Algunos contratos de proyecto especifican que varias partes comparten las responsabilidad de la financiación de los costes del proyecto. A continuación se incluyen algunos ejemplos:

-   Un cliente grande que tiene varias divisiones solicita que la financiación de un proyecto se divida por división.
-   La empresa comparte los costes de un gran proyecto con una organización externa.
-   Un proyecto de carretera está cofinanciado por dos municipios.
-   Un proyecto de puente está financiado por una concesión del gobierno y una corporación privada.

En Finance and Operations, puede dividir la facturación de una sola transacción o un proyecto completo entre varios clientes, concesiones u organizaciones. 

En proyectos con varios proveedores de fondos, todas las partes que contribuyen a la financiación de un proyecto de financiación avanzada se denominan fuentes de financiación. Después de definir un cliente, organización o concesión como fuente de financiación, se puede asignar a una o varias reglas de financiación. Las reglas de financiación contienen los criterios que determinan cómo se asignan gastos a las distintas fuentes de financiación de un proyecto. 

Dado que los artículos mantenidos en existencias, como los que aparecen en las solicitudes de compra y los pedidos de compra, no se pueden dividir, el importe del coste no se puede dividir entre varias fuentes de financiación en el momento de la distribución. Por lo tanto, el valor de la fuente de financiación es 0 (cero) hasta que se registra la emisión de inventario. Al registrarse, el importe de coste se distribuye de acuerdo con las reglas de distribución contable del proyecto.

A continuación se muestran algunos pasos que puede llevar a cabo para facilitar la división de la facturación entre varias fuentes de financiación:

-   Especifique que todas las transacciones de un proyecto usen la misma divisa de ventas que el contrato de proyecto.
-   Defina los límites de financiación para que ninguna fuente de financiación reciba facturas por un importe superior al especificado para un proyecto.
-   Configure reglas y límites de financiación para cada trabajador, artículo, categoría, grupo de categorías y tipos de transacción (o para todos los tipos de transacción).
-   Seleccione fechas de inicio y fin opcionales para definir el período en que es válida la regla de financiación.
-   Especifique el porcentaje del que es responsable cada fuente de financiación.
-   Indique la fuente de financiación responsable de las diferencias de redondeo causadas por los cálculos de asignación de financiación.
-   Configure reglas que determinen cómo se facturan los costes de proyecto a clientes externos y se cobran a organizaciones internas.
-   Registre las transacciones en una cuenta de financiación en espera hasta que pueda obtener financiación adicional o hasta que decida asumir los costes internamente.

Para determinar el grupo de impuestos que se asociará a una transacción, se busca el proyecto para una asignación de grupos de impuestos. Si no se han realizado asignaciones de grupos de impuestos a nivel de proyecto, se busca el contrato del proyecto.

### <a name="example-multiple-funding-sources-simple"></a>Ejemplo: Varias fuentes de financiación (simple)

En la siguiente tabla encontrará escenarios para la administración de asignación de financiación entre fuentes de financiación múltiples. Estos escenarios se basan en las siguientes suposiciones:

-   La configuración de prioridad se factoriza en la asignación de fondos antes de que se apliquen otros criterios de reglas de financiación.
-   No se ha especificado ningún intervalo de fechas para definir el periodo d en que la regla de financiación es válida.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Situación</strong></td>
<td><strong>Fuente de financiación </strong></td>
<td><strong>Porcentaje de asignación </strong></td>
<td><strong>Prioridad de asignación </strong></td>
</tr>
<tr class="even">
<td>Desea asignar los costes a una fuente de financiación hasta que se agoten los fondos, asignar los costes a una segunda fuente de financiación hasta que se agoten los fondos y, por último, asignar los costes pendientes a una tercera fuente de financiación.</td>
<td><ul>
<li>Fuente de financiación 1</li>
<li>Fuente de financiación 2</li>
<li>Fuente de financiación 3</li>
</ul></td>
<td><ul>
<li>100 %</li>
<li>100 %</li>
<li>100 %</li>
</ul></td>
<td><ul>
<li>1</li>
<li>2</li>
<li>3</li>
</ul></td>
</tr>
<tr class="odd">
<td>Desea asignar el 75% de los costes a una fuente de financiación y el 25% a una segunda fuente de financiación. Cuando cualquiera de esas fuentes de financiación se agote, desea pagar los costes pendientes de una tercera fuente de financiación.</td>
<td><ul>
<li>Fuente de financiación 1</li>
<li>Fuente de financiación 2</li>
<li>Fuente de financiación 3</li>
</ul></td>
<td><ul>
<li>75 %</li>
<li>25 %</li>
<li>100 %</li>
</ul></td>
<td><ul>
<li>1</li>
<li>1</li>
<li>2</li>
</ul></td>
</tr>
<tr class="even">
<td>Desea asignar el 75% de los costes a una fuente de financiación y el 25% a una segunda fuente de financiación. Cuando se agote cualquiera de esas fuentes de financiación, desea dividir los costes pendientes entre una tercera y una cuarta fuente de financiación.</td>
<td><ul>
<li>Fuente de financiación 1</li>
<li>Fuente de financiación 2</li>
<li>Fuente de financiación 3</li>
<li>Fuente de financiación 4</li>
</ul></td>
<td><ul>
<li>75 %</li>
<li>25%</li>
<li>50 %</li>
<li>50 %</li>
</ul></td>
<td><ul>
<li>1</li>
<li>1</li>
<li>2</li>
<li>2</li>
</ul></td>
</tr>
<tr class="odd">
<td>Desea asignar el primer 25% de costes a una fuente de financiación y el resto a otra segunda fuente de financiación.</td>
<td><ul>
<li>Fuente de financiación 1</li>
<li>Fuente de financiación 2</li>
</ul></td>
<td><ul>
<li>25 %</li>
<li>100 %</li>
</ul></td>
<td><ul>
<li>1</li>
<li>2</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="example-multiple-funding-sources-complex"></a>Ejemplo: Varias fuentes de financiación (complejo)

Dispone de tres fuentes de financiación que desea usar en el siguiente orden:

1.  Use la fuente de financiación 2 y la fuente de financiación 3 de manera igualitaria hasta que se agote la fuente de financiación 2.
2.  Continúe usando la fuente de financiación 3 hasta que se agote.
3.  Use la fuente de financiación 1 hasta que se agote la fuente de financiación 3.

Para cumplir con este objetivo, debe hacer lo siguiente:

-   Configure los límites de financiación para la fuente de financiación 2 y la fuente de financiación 3, para los importes respectivos.
-   Cree las siguientes reglas de financiación:
    -   Regla 1 (prioridad 1): asigne el 50% de las transacciones a la fuente de financiación 2 y el 50% a la fuente de financiación 3.
    -   Regla 2 (prioridad 2): asigne el 100% de las transacciones a la fuente de financiación 3.
    -   Regla 3 (prioridad 3): asigne el 100% de las transacciones a la fuente de financiación 1.

Esta configuración funciona porque las transacciones se comprueban comparándolos con las reglas y los límites para determinar si cualquiera de ellos se aplican a la transacción. Si no hay ninguna regla ni ningún límite específico que se aplique a la transacción, la regla Todas las transacciones se aplicará. La regla Todas las transacciones coincide con todas las transacciones. 

Si se encuentra una regla que coincida con una transacción, se aplicará primero el porcentaje que se ha asignado en dicha regla, pero solo después de que se comprueben las coincidencias comparándolas con los límites configurados. Si se ha alcanzado un límite, y se han agotado los fondos de una fuente de financiación, se descarta la regla de financiación que está asociada con el límite de financiación, y el programa comprobará la siguiente regla que se aplicará. 

En algunos casos, solo se puede asignar una transacción bajo una regla. Esto puede suceder porque se ha alcanzado un límite cuando se asigna la transacción. En este caso, solo se asigna una cantidad determinada según dicha regla, como el 50% a cada fuente de financiación. Este es el caso de la regla 1, que se describe anteriormente en esta sección. El resto se asignará según la siguiente regla de la secuencia. 

En la siguiente tabla se examina este escenario con más detalle.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Foco </strong></td>
<td><strong>Detalles</strong></td>
</tr>
<tr class="even">
<td>Reglas de financiación</td>
<td><ul>
<li>Regla 1 (prioridad 1): todas las transacciones. Asigne la fuente de financiación 2 al 50% y la fuente de financiación 3 al 50%.</li>
<li>Regla 2 (prioridad 2): todas las transacciones. Asigne la fuente de financiación 3 al 100%.</li>
<li>Regla 3 (prioridad 2): todas las transacciones. Asigne la fuente de financiación 1 al 100%.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Límite de financiación</td>
<td><ul>
<li>Límite de la fuente de financiación 1 = 10.000,00</li>
<li>Límite de la fuente de financiación 2 = 500,00</li>
<li>Límite de la fuente de financiación 3 = 750,00</li>
</ul></td>
</tr>
<tr class="even">
<td>Transacción 1</td>
<td><strong>Importe de la transacción:</strong> 100,00<strong> Financiación:</strong> la transacción se paga según la regla 1 solo, porque la transacción se paga en su totalidad después de que se aplique la regla 1. La transacción se financia de manera igualitaria entre la fuente de financiación 2 y la fuente de financiación 3.
<ul>
<li>Fuente de financiación 2: 50,00</li>
<li>Fuente de financiación 3: 50,00</li>
</ul></td>
</tr>
<tr class="odd">
<td>Transacción 2</td>
<td><strong>Importe de la transacción:</strong> 5,000.00<strong>Financiación:</strong> la transacción se paga en función de las tres reglas. <strong>Regla 1</strong>
<ul>
<li>Fuente de financiación 2: 450,00</li>
<li>Fuente de financiación 3: 450,00</li>
</ul>
<strong>Regla 2</strong>
<ul>
<li>Fuente de financiación 3: 250,00 (= 750,00 – 50,00 – 450,00)</li>
</ul>
<strong>Regla 3</strong>
<ul>
<li>Fuente de financiación 1: 3850,00 (= 5000,00 – 450,00 – 450,00 – 250,00)</li>
</ul></td>
</tr>
<tr class="even">
<td>Fondos totales que se distribuyen para cada fuente de financiación</td>
<td><ul>
<li>Fuente de financiación 1: 3.850,00</li>
<li>Fuente de financiación 2: 500,00</li>
<li>Fuente de financiación 3: 750,00</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="billing-rules"></a>Reglas de facturación
En el contrato de un proyecto que se negocia con el cliente, se define cómo y cuándo se podrá facturar al cliente por el trabajo realizado en un proyecto. Una vez haya configurado el contrato de proyecto y el proyecto, podrá configurar las reglas de facturación para dicho proyecto. Las reglas de facturación se basan en los términos de proyecto que se especifican en el contrato de proyecto. Las reglas de facturación que puede crear dependen de las condiciones del contrato de proyecto y del tipo de proyecto, tal como el tiempo y el material o el precio fijo, que se asocia a la regla de facturación. Puede crear más de una regla de facturación para un contrato de proyecto. También puede asignar una regla de facturación a varios proyectos asociados al mismo contrato de proyecto y tener condiciones similares de facturación. 

Puede configurar los tipos de reglas de facturación siguientes:

-   **Unidad de entrega**: facturar al cliente una vez completada una unidad de entrega. Defina las unidades de entrega en el contrato.
-   **Progreso**: facturar al cliente una vez completado un porcentaje determinado del proyecto. Puede configurar una regla de facturación para calcular automáticamente el porcentaje de trabajo completado, o puede calcular manualmente el porcentaje de trabajo completado y el importe que se facturará al cliente.
-   **Hito**: facturar a un cliente el importe completo de un hito de proyecto una vez se haya alcanzado el hito.
-   **Cuota**: facturar a un cliente por servicios más una cuota administrativa, que es normalmente un porcentaje del coste de los servicios.
-   **Tiempo y material**: facturar a un cliente el valor del tiempo y de los materiales que se usan en un proyecto.

Para todos los tipos de reglas de facturación, puede especificar un porcentaje de retención que se deduce de las facturas de cliente hasta que el proyecto alcance una etapa acordada. El porcentaje de retención del pago se especifica en el contrato de proyecto. El importe se calcula basándose en, y se resta del, el valor total de las líneas en una factura de cliente. 

Para las reglas de facturación **Tiempo y material** y **Progreso**, puede asignar categorías imputables. Las categorías imputables indican las transacciones que se deben incluir en las facturas de cliente. 

Cuando esté preparado para facturar al cliente, el importe que se facturará del proyecto se calcula en función de las reglas de facturación y se genera una propuesta de factura de proyecto. 

En las secciones siguientes se proporcionan ejemplos que muestran cómo configurar y gestionar reglas de facturación para un proyecto.

### <a name="example-create-a-billing-rule-that-is-based-on-the-number-of-units-delivered"></a>Ejemplo: Creación de una regla de facturación que se basa en el número de unidades entregadas

Su organización llega a un acuerdo para proporcionar un total de cinco sesiones de formación a los empleados de un cliente a un coste de 10.000 por sesión de formación. Su organización factura al cliente tras cada sesión de formación. 

Al configurar las reglas de facturación para el contrato, usa los siguientes valores:

-   La unidad de entrega es una sesión de formación.
-   El precio unitario es de 10.000 USD por sesión.
-   El número total de unidades es de cinco sesiones de formación.

Una vez completada una sesión de formación, puede crear una factura de 10.000 € por la primera unidad entregada y enviar la factura al cliente.

### <a name="example-create-a-billing-rule-that-is-based-on-a-specified-percentage-of-project-completion-manual-calculation"></a>Ejemplo: Creación de una regla de facturación que se basa en un porcentaje específico de finalización del proyecto (cálculo manual)

Su organización, una empresa de asesoría de software, llega a un acuerdo con un cliente para encargarse de parte del desarrollo de un producto. Su organización acepta entregar el código de software durante un período de seis meses. El cliente acepta pagar a su organización un total de 100.000 USD por el trabajo. Puede crear una regla de facturación para facturar al cliente según el porcentaje de trabajo completado del proyecto según se especifica en el contrato.

-   Al final del primer mes, se reúne con el cliente para determinar el porcentaje de trabajo completado. Una vez que su empresa y el cliente revisen el proyecto, su empresa decide que el proyecto está completado en un 15 %.
-   Crea una factura por 15.000 (15 % de 100.000) y se la envía al cliente.

### <a name="example-create-a-billing-rule-that-is-based-on-a-specified-percentage-of-project-completion-automatic-calculation"></a>Ejemplo: Creación de una regla de facturación que se basa en un porcentaje específico de finalización del proyecto (cálculo automático)

Su organización, una empresa de desarrollo de software, acuerda desarrollar un paquete de contabilidad de nóminas para un cliente por 30.000. El cliente acepta pagar a su organización según el porcentaje de trabajo completado. Se estima que los costes del proyecto son de 20.000 USD. El contrato del proyecto determina las categorías de trabajo para que su empresa usa en el proceso de facturación. Se configuran reglas de facturación que calculan automáticamente los importes de las facturas por el porcentaje de trabajo completado en cada categoría. Configura un presupuesto para cada categoría:

-   **Desarrollo**: coste de 15.000 e ingresos de 20.000.
-   **Instalación**: coste de 5.000 e ingresos de 10.000.

Al facturar al cliente por primera vez, el importe de la factura se calcula automáticamente según la siguiente información:

-   Después de un mes, el trabajador del proyecto envía una hoja de horas del proyecto. El coste de las horas del trabajador es de 5.000 USD por el desarrollo y de 1.000 USD por la instalación. El trabajo de desarrollo está completado en un 33 % (5.000 del coste real/15.000 del coste presupuestario) y el trabajo de instalación está completado en un 20 % (1.000 del coste real/5.000 USD del coste presupuestario).
-   El importe de la factura de 8.667 se calcula automáticamente (33 de 20.000 más el 20 por ciento de 10.000).
-   Crea una factura por 8.667 y se la envía al cliente.

### <a name="example-create-a-billing-rule-that-is-based-on-agreed-upon-milestones"></a>Ejemplo: Creación de una regla de facturación que se basa en hitos acordados

Su organización, una empresa de asesoría administrativa, acuerda llevar a cabo una investigación de mercado para un producto de consumo que el cliente quiere vender. El cliente acepta usar sus servicios durante tres meses, comenzando en marzo, y acuerda pagar a su organización 50.000 USD. El proyecto tiene tres hitos:

-   Hito 1: recopilar datos de consumidores, 31 de marzo
-   Hito 2: analizar datos de consumidores, 30 de abril
-   Hito 3: presentar una propuesta de viabilidad del producto, 31 de mayo.

El cliente acepta pagar a su organización 10.000 por el primer hito y 20.000 por el segundo hito y 20.000 por el tercer hito. 

Al configurar el contrato de proyecto, acepta facturar al cliente según los hitos completados. La configuración de las reglas de facturación incluye los pasos siguientes:

-   Definir los hitos del proyecto.
-   Defina el importe que se debe facturar al cliente cuando se complete cada hito.

Al completar el primer hito el 31 de marzo, márquelo como completado y, a continuación, cree una factura por 10.000 y envíela al cliente. No se puede crear una factura para un hito hasta que haya marcado el hito como completado.

### <a name="example-create-a-billing-rule-that-is-based-on-services-plus-a-management-fee"></a>Ejemplo: Creación de una regla de facturación basada en servicios más una cuota administrativa

Su organización, una empresa de asesoría administrativa, acuerda llevar a cabo una investigación de mercado para evaluar la viabilidad que el cliente, una empresa minorista, está desarrollando. Las condiciones del acuerdo especifican que proporcionará los servicios de sus tres mejores asesores administrativos, que llevará a cabo la investigación según tiempo y material. El cliente acepta pagar 100 USD por hora por los asesores, más un 10% adicional de cuota administrativa por las horas de asesoría que se cargan al proyecto. 

Cuando configure el contrato de proyecto, cree una regla de facturación para agregar un 10% en concepto de cuota de administración por las horas de asesoría que se carguen al proyecto. 

Al crear una factura para el cliente, se factura un 10% de cuota administrativa más el coste de las horas de asesoría. Por ejemplo, si los tres asesores trabajaron un total de 200 horas en el proyecto, se crea una factura por 22.000 basada en el siguiente cálculo:

-   200 horas a 100 USD por hora = 20.000 USD
-   Comisión de gestión del 10 por ciento = 2.000
-   Importe total de la factura = 22.000

Si las cuotas son gravables a un cliente y selecciona un grupo de impuestos en el contrato del proyecto, el grupo de impuestos se especificará automáticamente en una regla de facturación de cuotas.

### <a name="example-create-a-billing-rule-for-the-value-of-time-and-materials"></a>Ejemplo: Creación de una regla de facturación para el valor del tiempo y el material

Su organización, una empresa de consultoría de software, acuerda proporcionar cinco asesores técnicos para trabajar en un proyecto de desarrollo de software para un cliente durante los próximos seis meses. El cliente acepta pagar 150 por cada hora de asesoría, además del coste de los suministros de oficina. Su organización envía una factura al cliente al final de cada mes. 

Al configurar el contrato de proyecto, acepta cobrar cada vez del cliente por el tiempo y el material dedicado al proyecto. Cree una regla de facturación que incluya la siguiente información:

-   El período de del contrato es de seis meses.
-   El tiempo de asesoría se calcula con una tasa de 150 por hora.
-   Los suministros de oficina se facturan al precio de coste y el coste total del proyecto no debe superar la cantidad de 10.000.
-   Su empresa crea una factura de cliente al final de cada mes natural durante el proyecto.

Durante el primer mes, los asesores registran un total de 800 horas dedicadas al proyecto. El coste de los suministros de oficina que se cargan al proyecto es 2.000. Por tanto, al final del mes, se crea una factura de 122.000, calculada en base a 800 horas a 150 por hora más 2.000 en suministros de oficina.




