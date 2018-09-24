---
title: "Gestión de proyectos y contabilidad"
description: "La funcionalidad de gestión de proyectos y contabilidad se puede usar en varias industrias para proporcionar un servicio, producir un producto o lograr un resultado."
author: KimANelson
manager: AnnBe
ms.date: 01/10/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjTable; ProjProjectManagementWorkspace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: e927e45511c5e6c232457a76b2d1fab160fe0f5a
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---

# <a name="project-management-and-accounting"></a>Gestión de proyectos y contabilidad

[!include [banner](../includes/banner.md)]

La funcionalidad de gestión de proyectos y contabilidad se puede usar en varias industrias para proporcionar un servicio, producir un producto o lograr un resultado.  

Un proyecto es un grupo de actividades diseñado para proporcionar un servicio, producir un producto o lograr un resultado. Los proyectos consumen recursos y generan resultados financieros en forma de ingresos o activos

## <a name="projects-across-industries"></a>Proyectos entre sectores
La funcionalidad de contabilidad y administración de proyectos se puede usar en varios sectores, como se muestra en la siguiente ilustración.

[![Proyectos entre sectores](./media/projects-accross-industries.jpg)](./media/projects-accross-industries.jpg) 

En un centro de llamadas, se puede usar un ticket para describir el conjunto de acciones que se requieren para resolver una llamada. Las empresas de asesoría, como las agencias de publicidad o las organizaciones de asesoría técnica o de administración, hacen referencia a sus actividades como proyectos. En marketing, una campaña representa un conjunto de trabajos que se deben entregar. En la fabricación basada en proyectos, un pedido de producción está relacionado con el trabajo diverso que se debe realizar para producir algunos bienes terminados. Cualquiera que sea el nombre que se use para ellos, estos proyectos constan de recursos, programaciones y costes, y la funcionalidad de contabilidad y administración de proyectos de Microsoft Dynamics 365 for Finance and Operations puede ayudar con la planificación, la ejecución y el análisis de estos proyectos.

## <a name="project-phases"></a>Fases del proyecto
Aunque el siguiente flujo de proceso está dirigido hacia los proyectos externos, o los proyectos que se completan para uno o más clientes, la funcionalidad también se aplica a proyectos internos, de solo coste. 

![3 etapas de un proyecto](./media/3-stages-of-a-project.png) 

Como se muestra en la ilustración anterior, la contabilidad y la gestión de proyectos se puede dividir en tres fases:

1.  Iniciar
2.  Ejecutar
3.  Analizar

## <a name="initiate-the-project"></a>Iniciar el proyecto
Durante el inicio del proyecto, se producen varios procesos clave. Puede usar un presupuesto de proyecto para comunicar la mano de obra, los gastos y los materiales estimados al cliente. Puede registrar los términos de facturación, los límites y los acuerdos en un contrato de proyecto. Puede usar una estructura de descomposición del trabajo (WBS) para planificar y estimar el trabajo. Puede configurar previsiones y presupuestos para guiar la ejecución del proyecto. En el ejemplo siguiente se muestra la estructura de un proyecto.[![estructura de proyecto](./media/project-structure1.jpg)](./media/project-structure1.jpg)  

### <a name="create-project-quotations"></a>Crear presupuestos de proyecto

En la fase inicial de ventas de un proyecto, los presupuestos del proyecto le permiten proporcionar al cliente una oferta no vinculante. Un presupuesto puede incluir elementos como los artículos y los servicios que se van a presupuestar, la información básica de contacto, los acuerdos y descuentos comerciales especiales, así como posibles impuestos y suplementos.

También puede emitir una carta de garantía para una transacción de presupuesto de proyecto entre su organización y el cliente. Una vez creado el presupuesto de proyecto, puede crear la solicitud de la carta de garantía para el cliente y enviarla al banco. Una vez que el banco ha aprobado la solicitud, la carta de garantía se emite al cliente. 

Para obtener más información, consulte [Presupuestos de proyecto](project-quotations.md).

### <a name="create-project-contracts"></a>Crear contratos de proyectos

Cuando formaliza un contrato con un cliente o una fuente de financiación para completar un proyecto, debe crear un contracto de proyecto. A continuación, cuando cree el proyecto, debe asignarlo al contrato correspondiente. El tipo de proyecto que cree para un contrato de proyecto determinará el método de facturación usado para los clientes del proyecto. Puede modificar un contrato de proyecto y el proyecto relacionado, pero no puede cambiar el tipo de proyecto. Para obtener más información acerca de los tipos de proyectos, consulte la sección "Creación de proyectos”.

Para obtener más información acerca de los contratos de proyecto, vea [Contratos de proyecto](project-contracts.md).

### <a name="create-work-breakdown-structures"></a>Crear estructuras de descomposición del trabajo

El nivel de detalle de una WBS depende del nivel de precisión que se requiere en las estimaciones y el nivel de seguimiento que se requiere frente a las estimaciones. Los proyectos que tienen muy baja tolerancia para los desvíos en la programación o el coste normalmente requieren una WBS más detallado y también requieren seguimiento diligente del coste y del progreso del trabajo en relación con la WBS. 

Para obtener más información, vea [Estructuras de descomposición del trabajo](work-breakdown-structures.md).

### <a name="create-project-forecasts-and-budgets"></a>Crear las previsiones y presupuestos del proyecto

Puede usar la previsión si su organización tiene una perspectiva operativa y se centra en los ingresos y costes derivados de transacciones específicas. Sin embargo, si su organización se centra en mayor medida en los importes financieros, puede usar la gestión presupuestaria. Cada método tiene sus propias ventajas. Para obtener más información, consulte [Previsiones y presupuestos del proyecto](project-forecasts-budgets.md).

### <a name="create-projects"></a>Crear proyectos

Puede crear seis tipos de proyectos en Microsoft Dynamics 365 for Finance and Operations. Cada tipo de proyecto se configura de manera diferente para costes y reconocimiento de ingresos. El tipo de proyecto que seleccione dependerá del objetivo del proyecto. En la tabla siguiente se describe el uso habitual de cada tipo de proyecto.
                                                                                                            
<table>
  <tr>
    <td>Tipo de proyecto</th>
    <td>Descripción</th>
  </tr>
  <tr>
    <td>Tiempo y material</td>
    <td>En los proyectos de tiempo y material, se factura al cliente por todos los costes en los que incurra en un proyecto. Se incluyen los costes por horas, gastos, artículos y cuotas.</td>
  </tr>
  <tr>
    <td>Precio fijo</td>
    <td>En proyectos de precio fijo, las facturas constan de transacciones a cuenta. Un Proyecto de precio fijo se factura según una programación de facturación que se basa en un contrato de proyecto. El ingreso para un Proyecto de precio fijo se puede calcular y registrar en el proyecto mediante el método de porcentaje completado. Como alternativa, los ingresos se pueden calcular y registrar una vez completado el proyecto, con el método de contrato completado. Las empresas pueden a menudo beneficiarse de utilizar el valor del trabajo en proceso (WIP) para calcular el grado de finalización de un proyecto o grupo de proyectos.</td>
  </tr>
  <tr>
    <td>Inversión</td>
    <td>Los proyectos de inversión son los proyectos que no producen ganancias inmediatas. Normalmente se usan para proyectos internos a largo plazo en los que se deberán capitalizar los costes. Solo se pueden registrar los costes por artículos, horas y gastos para un proyecto de inversión. A los costes de un proyecto de inversión se les realiza un seguimiento y se controlan mediante la función de estimación. Los proyectos de inversión se pueden configurar con un capitalización máxima opcional. A medida que un proyecto de inversión progrese, deberá registrar los costes en las cuentas de trabajo en curso, donde se reservan los costes hasta que se complete el proyecto. Cuando se elimina el proyecto, deberá transferir el valor de trabajo en curso a un activo fijo, a una cuenta contable, o a un nuevo proyecto. <br></br> <strong>NOTA:</strong> las transacciones en proyectos de inversión no se muestran en la página <strong>Registrar costes<strong>, <strong>Acumular ingresos</strong> o <strong>Crear propuestas de facturas</strong>.</td>
  </tr>
  <tr>
    <td>Proyecto de coste</td>
    <td>Al igual que los proyectos de inversión, los proyectos de coste por lo general se usan para realizar el seguimiento de los proyectos internos, y solo se pueden registrar las horas, los gastos y los artículos para ellos. Sin embargo, la duración de los proyectos de coste es normalmente más corta que la de los proyectos de inversión. Además, a diferencia de los proyectos de inversión, los proyectos de coste no se pueden capitalizar en las cuentas de balance general. En su lugar, las transacciones de proyecto se registran solo en las cuentas de ganancias y pérdidas. <br></br> <strong>NOTA:</strong> Las transacciones en proyectos de coste no se reflejan en la página <strong>Registrar costes</strong>, <strong>Acumular ingresos</strong> o <strong>Crear propuestas de facturas</strong>. Dado que los proyectos de coste suelen realizar un seguimiento de los proyectos internos, no suelen estar asociados a una cuenta de cliente. Sin embargo, si su configuración requiere la creación de requisitos de artículos para pedidos de compra, debe asociar el proyecto de coste a un cliente. Esta asociación es necesaria porque los requisitos de artículos se administran como líneas de pedidos de ventas y el sistema necesita que se especifique un cliente. Sin embargo, esta configuración no provocará que se creen automáticamente los requisitos de artículos automáticamente a partir de un pedido de compra. Para los proyectos de coste, se omite el ajuste <strong>Crear requisito de artículo</strong>. Si necesita un requisito de artículo en un proyecto de coste, puede crear uno manualmente, siempre que haya un cliente asociado al proyecto.</td>
  </tr>
  <tr>
    <td>Interno</td>
    <td>Los proyectos internos se usan para realizar seguimientos de los costes de un proyecto que sea interno en su organización. Los proyectos internos pueden proporcionar una herramienta de planificación para administrar el consumo del recurso. <br></br><strong>NOTA:<strong> las transacciones en proyectos internos no se reflejan en la página <strong>Acumular ingresos</strong> o <strong>Crear propuestas de facturas</strong>.</td>
  </tr>
  <tr>
    <td>Hora</td>
    <td>Los proyectos de tiempo se usan para realizar el seguimiento del tiempo asociado con actividades no imputables y no productivas, como un proyecto para realizar un seguimiento del tiempo de baja por enfermedad de los trabajadores. Las transacciones en los proyectos de tiempo no se registran en el libro mayor. En su lugar, se incluyen en los informes de utilización del trabajador. En este caso, solo se podrán registrar las transacciones por horas en los proyectos de tiempo. Usa un diario o una hoja de horas de horas para registrar estas horas en el proyecto. Una vez se registran las horas, aparecen como transacciones de proyecto pero no tienen transacciones de asiento correspondientes. <br></br><strong>NOTA:</strong> Las transacciones en proyectos de tiempo no se reflejan en la página <strong>Registrar costes</strong>, <strong>Acumular ingresos</strong> o <strong>Crear propuestas de facturas</strong>.</td>
  </tr>
</table>


### <a name="assign-workers-categories-and-resources"></a>Asignar trabajadores, categorías y recursos

Puede programar recursos de trabajador en función de los requisitos y la programación de un proyecto, o en las aptitudes y la disponibilidad de trabajadores. Las capacidades de programación de recursos permiten la implementación de los trabajadores de la organización de manera efectiva y eficiente. Puede encontrar rápidamente a los trabajadores más cualificados para están disponibles para trabajar en su proyecto. También puede ver fácilmente cómo esos trabajadores se pueden usar de manera más eficaz durante el transcurso del proyecto. 

Estas son algunas de las maneras que puede usar la funcionalidad de programación de recursos:

-   Usar la información acerca de los atributos de un trabajador, tales como los estudios, las aptitudes, las certificaciones y la experiencia en proyectos, para adaptarlo a los requisitos de un proyecto.
-   Usar la información acerca del calendario y la disponibilidad de un trabajador para ajustar su programación al calendario del proyecto.
-   Revisar la capacidad de cada trabajador y determinar cómo esta se emplea. Por ejemplo, si se hace un uso deficiente de un trabajador, este podría asignarse a un proyecto que se ajuste a su disponibilidad y sus atributos.
-   Revisar la disponibilidad de un trabajador para asegurarse de que no se presenten conflictos con el calendario de las asignaciones del trabajador.
-   Revisar la información acerca del uso de los trabajadores en una vista resumida (por ejemplo, por departamento o por trabajador) o en una vista detallada (por ejemplo, por trabajadores de un departamento o por detalle semanal de cada trabajador).
-   Modificar las asignaciones de recursos para diversas unidades de tiempo, tales como día, semana o mes, para optimizar el uso que se hace de los trabajadores.

## <a name="execute-the-project"></a>Ejecutar el proyecto
Durante la ejecución de proyectos, los miembros del equipo o los directores registran el trabajo y los gastos en que se incurre, usando hojas de horas, informes de gastos y otros documentos empresariales. Los directores de proyecto tienen herramientas que les permiten supervisar el consumo de importes presupuestados para el proyecto. Los directores de proyecto también pueden pedir, seleccionar o adquirir materiales para proyectos mediante pedidos de compra y otros documentos empresariales. Las facturas se preparan y se aprueban, de manera que se pueda facturar a los clientes por el trabajo en curso. Por último, los ingresos se reconocen durante este proceso para afectar a las operaciones financieras de la organización.

### <a name="manage-work-breakdown-structures"></a>Administrar estructuras de descomposición del trabajo

Una WBS es una descripción del trabajo que se completará para un proyecto. Una WBS es una jerarquía de tareas. Representa no solo el trabajo para cada tarea, sino también el tamaño, el coste y la duración de tarea. 

Para obtener más información, vea [Estructuras de descomposición del trabajo](work-breakdown-structures.md).

### <a name="manage-project-forecasts-and-budgets"></a>Gestionar presupuestos y previsiones de proyecto

Hay dos formas de gestionar y controlar los proyectos: las previsiones y los presupuestos de proyecto. Puede usar la previsión si su organización tiene una perspectiva operativa y se centra en los ingresos y costes derivados de transacciones específicas. Sin embargo, si su organización se centra en mayor medida en los importes financieros, puede usar la gestión presupuestaria.

Para obtener más información, consulte [Previsiones y presupuestos del proyecto](project-forecasts-budgets.md).

### <a name="create-production-orders"></a>Crear órdenes de producción

Un pedido de producción relacionado con el proyecto se puede vincular con un requisito de artículo o un pedido de ventas usando el método de artículo consumido o de artículo finalizado. Además, si el pedido de producción se creó manualmente, no existe un vínculo entre el pedido de producción y el pedido de ventas o el requisito del artículo (ningún vínculo al pedido). Sin embargo, si el pedido de producción se creó automáticamente para satisfacer un pedido de ventas o un requisito de artículo, existe un vínculo entre el pedido de producción y el pedido de ventas o el requisito del artículo (vínculo al pedido). 

Según las combinaciones de estos factores, utilice uno de los métodos siguientes:

- **Artículo finalizado/vínculo al pedido**: vincule el proyecto a un pedido de ventas o un requisito de artículo. Al usar este método, se registrarán los costes reales del proyecto cuando se facture el pedido de ventas o cuando se actualice el albarán para el requisito de artículo. El coste se registrará como artículo finalizado.
- **Artículo finalizado/sin vínculo al pedido**: no podrá registrar los costes reales hasta que el ciclo de producción para un artículo tenga el estado **Terminado**. El coste del artículo terminado se registra como transacción única.
- **Artículo consumido/vínculo al pedido**: vincule el proyecto a un requisito de artículo. Mediante este método, se podrán ver los costes reales del proyecto cuando la producción tenga el estado **Iniciado** o se haya notificado como terminado. Los costes se registrarán como múltiples transacciones de artículo del proyecto para materias primas y horas consumidas para la producción. Cuando se actualice el albarán para el requisito de artículo, no se registrarán costes del proyecto. También puede definir el nivel de la jerarquía de la lista de materiales (L. MAT) en la que se siguen los proyectos de la producción.
- *<strong><em>Artículo consumido/sin vínculo al pedido</em></strong>* – vincule el proyecto a un requisito de artículo. Mediante este método, se podrán ver los costes reales del proyecto cuando la producción tenga el estado <strong>Iniciado</strong> o se haya notificado como terminado. Los costes se registrarán como múltiples transacciones de artículo del proyecto para materias primas y horas consumidas para la producción. También puede definir el nivel de la jerarquía de la lista de materiales en la que se siguen los proyectos de la producción.

### <a name="procure-products-and-services"></a>Adquirir productos y servicios

La compra y venta de artículos constituyen actividades fundamentales en muchos negocios centrados en proyectos.

#### <a name="purchase-orders-for-projects"></a>Pedidos de compra para proyectos

La finalidad del pedido de compra determina cuándo se consume el pedido de compra y, por tanto, cuándo se cargan los artículos en un proyecto.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Método</th>
<th>Propósito</th>
<th>Consumo de artículos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Cree un pedido de compra directamente.</td>
<td>Artículos de compra de un proveedor externo para consumo en un proyecto. Puede crear el pedido de compra de las siguientes formas:
<ul>
<li>Desde el propio proyecto. En este caso, el proyecto ya está definido para el pedido de compra.</li>
<li>Desplazándose hasta el pedido de compra del proyecto. Debe seleccionar tanto el proveedor como el proyecto para el que se creará el pedido de compra.</li>
</ul></td>
<td>Los artículos se consumen al actualizar la factura del proveedor.</td>
</tr>
<tr class="even">
<td>Cree un pedido de venta a partir de un pedido de ventas.</td>
<td>Los artículos de compra cuando crea un pedido de ventas a partir de un proyecto.</td>
<td>Los artículos se consumen al facturar el pedido de ventas al cliente.</td>
</tr>
<tr class="odd">
<td>Cree un pedido de compra a partir de un artículo requerido.</td>
<td>Los artículos de compra al crear un requisito de artículo a partir de un proyecto.</td>
<td>Los artículos se consumen al actualizar el requisito de artículo.</td>
</tr>
</tbody>
</table>

#### <a name="sales-orders-for-projects"></a>Pedidos de ventas para proyectos

En Gestión de proyectos y contabilidad, puede registrar el consumo de artículos de varias formas. Puede vender artículos o artículos de compra de un proyecto o reservar artículos para un proyecto. 

Puede solicitar artículos del inventario de la empresa para consumo en un proyecto. También puede comprar artículos de un proveedor externo. Se pueden consumir artículos de todos los tipos de proyectos excepto de los proyectos de tiempo. 

El modo en que se solicitan los artículos depende de la ubicación desde la que se soliciten:

-   Para pedir artículos del inventario de la empresa, debe especificar el pedido como un requisito de artículo. Si utiliza la página **Requisitos de artículos**, puede configurar el requisito de manera que reciba artículos como entregas parciales. Por tanto, puede posponer el consumo de una cantidad de los artículos hasta que se necesiten los artículos.
-   Para pedir artículos a un proveedor externo, debe crear el pedido como un pedido de compra en la página **Pedido de compra**.

> [!NOTE] 
> El albarán de un pedido de ventas relacionado con el proyecto no se puede cancelar si los artículos se han marcado para el embalaje. 

En la siguiente tabla, se muestran los métodos para pedir artículos y el modo de consumo de los artículos.

| Método            | Propósito                                                                                                                                                        | Consumo de transacciones de artículos                                                                                                                  |
|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| Pedido de ventas       | Permite especificar una transacción directamente en un proyecto de tiempo y material.                                                                                                   | Las transacciones de artículos se consumen al registrar la factura del cliente.                                                                               |
| Diario de inventario | Especificar y mantener rápidamente registros de artículos. Si, por ejemplo, desea especificar un requisito de artículo de una lista impresa, puede aplicarse el diario de inventario. | Las transacciones de artículos se consumen al registrar el diario.                                                                                        |
| Requisito de artículo  | Especifique los artículos que no se consumirán inmediatamente. Este método permite que los usuarios realicen un seguimiento del número de artículos que se ha consumido en un único registro de requisitos de artículos.    | Las transacciones de artículos se consumen cuando se actualiza el albarán. Es decir, el requisito de artículo se crea al registrar el albarán. |
| Pedidos de compra   | Se especifican las transacciones en una de tres ubicaciones, en función del método de compra.                                                                              | Las transacciones de artículos se consumen cuando se actualiza el albarán o cuando se factura al cliente o proveedor.                                      |

### <a name="process-project-invoices"></a>Procesar las facturas del proyecto

El tipo de proyecto determina el procedimiento de facturación que se debe aplicar. Solo se pueden facturar los dos tipos de proyecto externo (Tiempo y material y Precio fijo). Los proyectos de tiempo y material y los proyectos de precio fijo están siempre vinculados a un contrato de proyecto. 

Antes de crear una factura de cliente para un proyecto, puede crear una factura preliminar o una propuesta de factura. En una propuesta de factura, puede seleccionar transacciones de proyecto para incluirlas en una factura de proyecto. A continuación, puede revisar los detalles de la factura antes de registrar la factura del proyecto y enviarla al cliente o a otra fuente de financiación. 


Para obtener más información acerca de cómo procesar facturas de proyectos, consulte [Facturación del proyecto](../accounts-payable/project-invoicing.md).


### <a name="calculate-the-cost-to-complete-a-project"></a>Calcular el coste para completar un proyecto

Al crear una estimación, puede elegir el método que se usa para calcular el coste para completar el proyecto. Seleccione un método en el campo **Método de coste para completar** de la página **Crear estimación**. El método de coste seleccionado se aplica por separado a cada línea de coste de la estimación. Mientras que una línea tiene un estado de **Creado**, puede cambiar el método que se le aplica en la página **Estimación de coste**. 

La tabla siguiente describe los métodos para calcular el coste para completar un proyecto.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Método</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Coste total – Real</td>
<td>Los costes estimados se deben especificar manualmente. Cuando se complete la columna <strong>Coste total</strong> o <strong>Cantidad total</strong> en la página <strong>Estimación de coste </strong>, los costes reales se restan de los totales especificados por el usuario. El resultado es el coste para completar el proyecto. Normalmente, el progreso de los costes no se sigue en función, por ejemplo, del número de comidas y estancias de hotel que se registran en cada período. En su lugar, suele basarse en una comparación con el importe total de las horas estimadas. Este planteamiento no necesita un modelo de previsión y el coste o la cantidad total se puede cambiar manualmente. Cuando se especifica un valor en la columna <strong>Coste total</strong> o <strong>Cantidad total</strong>, Finance and Operations compara este valor con las transacciones reales que se han registrado en el período y, a continuación, disminuye el valor de la columna <strong>Cantidad para completar</strong> o <strong>Coste para completar</strong>.</td>
</tr>
<tr class="even">
<td>Presupuesto total - Real</td>
<td>Los costes reales se comparan con el modelo de previsión que seleccione para determinar el coste. Este método utiliza un modelo presupuestario de totales que incluye transacciones previstas. Para obtener una vista más precisa del proyecto, puede ajustar el modelo presupuestario mientras el proyecto está en curso. Si debe ajustar la programación, siga este proceso general:
<ol>
<li>Copie las transacciones de previsión en otro modelo de previsión.</li>
<li>Compare las transacciones de previsión con las transacciones reales.</li>
<li>Mantenga, reduzca o actualice las estimaciones para el siguiente período.</li>
</ol>
Finance and Operations no disminuye automáticamente las estimaciones previstas. Por tanto, es buena idea mantener un modelo de previsión original en el proyecto de precio fijo para establecer una base para comparación una vez completado el proyecto. 
<br></br> <strong>NOTA:</strong> Al seleccionar este método, use al menos dos modelos de previsión. Un modelo debe contener la previsión original. Para el otro modelo, debe copiar las transacciones de previsión de otro modelo. Este método solo es válido para proyectos de precios fijos e inversión.</td>
</tr>
<tr class="odd">
<td>Presupuesto restante</td>
<td>Este método usa un modelo presupuestario restante hasta calcular al coste que completa el proyecto. Al utilizar este método, los costes reales y los importes previstos en el modelo presupuestario restante se agregan conjuntamente. El resultado es un coste total. Antes de utilizar este método, se debe configurar un modelo presupuestario restante para deducir las transacciones basadas en las transacciones reales registrados en el programa. En la página <strong>Modelos de previsión</strong>, asegúrese de que los campos están marcados en el grupo <strong>Reducción automática de previsiones</strong>. Normalmente, un presupuesto restante se copia de uno original. A medida que se especifiquen las transacciones, las transacciones del presupuesto restante se reducirán. Conforme progrese el proyecto, si se determina que el presupuesto restante se debe ajustar, carga transacciones de previsión de gastos al presupuesto restante. <br></br> <strong>NOTA:</strong> Este método solo puede aplicarse si el modelo de previsión está vinculado a la estimación.</td>
</tr>
<tr class="even">
<td>Como estimación anterior</td>
<td>Se aplica el mismo método de estimación que se usó en el período anterior. Este método necesitará un modelo de previsión si el período anterior así lo requería.</td>
</tr>
<tr class="odd">
<td>Establecer coste para completar en cero</td>
<td>Este método se suele usar antes de que se elimine el proyecto de estimación. Este método coincide las estimaciones totales con las transacciones reales que se han registrado y desactiva la columna <strong>Coste para completar</strong>. El porcentaje de finalización resultante es siempre del cien por cien. El campo <strong>Previsión</strong> no está seleccionado para cada línea de coste creada y la estimación total se copia de la estimación de coste anterior. El consumo real del período de estimación se deduce del coste para completar el proyecto. Este método no requiere un modelo de previsión.</td>
</tr>
<tr class="even">
<td>Desde plantilla de coste</td>
<td>Se aplica el coste para completar configurado en la plantilla de costes asociado al proyecto de estimación seleccionado.</td>
</tr>
</tbody>
</table>

## <a name="analyze-the-project"></a>Analizar el proyecto
En su nivel más básico, un proyecto se usa para agrupar transacciones que registran costes y, a continuación, registra estos costes en la contabilidad general. 

Normalmente, estas transacciones son el resultado de documentos empresariales, como hojas de horas, informes de gastos, facturas de proveedor o transacciones de inventario. El ciclo de vida de un proyecto se inicia normalmente con estimaciones, previsiones y presupuestos que ayudan a planificar y anticipan el trabajo y el impacto financiero del proyecto. Al analizar un proyecto, puede evaluar no solo las transacciones que tuvieron lugar durante el proyecto, sino también la precisión de sus estimaciones y previsiones, las tasas de utilización de los miembros del equipo del proyecto y el éxito total del proyecto.

### <a name="analyze-cash-flow"></a>Analizar el flujo de efectivo

La supervisión del flujo de efectivo permite revisar el flujo de efectivo previsto y el real de un proyecto. Puede revisar los flujos de efectivo mientras un proyecto está en curso o puede ver los flujos de efectivo de un proyecto completado. 

La supervisión de los flujos de efectivo le permite evaluar un proyecto individual, utilizar los informes para ver varios proyectos y transferir los flujos de efectivo del proyecto a las previsiones de flujo de efectivo en la contabilidad general.

#### <a name="cash-inflow-forecasting"></a>Previsiones de flujos de efectivo entrantes

En función de la configuración, puede prever los flujos de entrada para un proyecto seleccionado. Por ejemplo, si la fecha de proyecto es el 5 de marzo de 2012 y la factura se emite el 31 de marzo de 2012, esta es la manera en que puede realizar la previsión de la fecha de vencimiento y de la fecha de pago de ventas esperada:

-   **Fecha del proyecto:** 5 de marzo de 2012.
-   **Fecha de la factura:** 31 de marzo de 2012. Esta fecha se determina en función de la frecuencia de facturación. Para este ejemplo, se establece la frecuencia de facturación al mes actual. Por tanto, todas las transacciones que se registran en el mes de marzo se facturan el último día del mes.
-   **Fecha de vencimiento:** 14 de abril de 2012. Esta fecha se determina según las condiciones de pago que se establecieron para el proyecto. Para este ejemplo, seleccionó condiciones de pago de 14 días. Por lo tanto, se agregaron 14 días a la fecha de la factura del envío en una fecha de vencimiento de 14 de abril de 2012.
-   **Fecha esperada de pago de ventas:** 27 de abril de 2012. Esta fecha se calcula agregando el número de días en el campo **Días de almacenaje generales** de la página **Parámetros de gestión de proyectos y contabilidad** al número de días del campo **Días de almacenaje individual** de la página **Contratos de proyecto** y, a continuación, agregando el total al número de días del campo **Fecha de vencimiento**. Por ejemplo, ha especificado **3** en el campo **Días de almacenaje generales** y **10** en el campo **Días de almacenaje individual**. Por lo tanto, se agregaron 13 días a la fecha de vencimiento del envío en una fecha esperada de pago de ventas de 27 de abril de 2012.

Los días de almacenaje general pueden sustituir los días de almacenaje o agregarse a los días de almacenaje individuales:

-   Para usar los días de almacenaje general como sustitución para los días de almacenaje individuales, especifique el número promedio de días entre la fecha de vencimiento y la fecha de pago real para los clientes.
-   Para agregar los días de almacenaje general a los días de almacenaje individual, en el campo **Días de almacenaje generales**, especifique la estimación del número de días entre el día en que el cliente envía el pago y el día en que su organización lo recibe.

Configure los días de almacenaje individuales en el contrato del proyecto. Los días se calculan según la fecha de vencimiento de la factura de ventas y la experiencia de la organización con un patrón de pago del cliente.

#### <a name="actual-cash-inflow"></a>Flujo de entrada de efectivo real

El flujo de entrada de efectivo real se parece a la previsión, pero puede comenzar sus cálculos a partir de la fecha de la primera factura. Este es un ejemplo:

-   **Fecha de la factura:** 2 de marzo de 2012.
-   **Fecha de vencimiento:** 16 de marzo de 2012. Las condiciones de pago se establecen en 14 días.
-   **Fecha esperada de pago de ventas:** 29 de mazo de 2012. Este cálculo incluye tres días de almacenaje general y 10 los días de almacenaje.

#### <a name="cost-forecasting"></a>Previsión de costes

De acuerdo con los días que se definen, la fecha de pago de costes puede diferir de la fecha del proyecto. En este caso, la fecha de pago de coste se calcula sumando el número de días a partir de la fecha del proyecto al número de días en las condiciones de pago. 

Por ejemplo, la fecha de proyecto de la transacción es el 5 de marzo de 2012 y se establecen las siguientes condiciones de pago:

-   **Horas:** Mes actual (**M**)
-   **Gastos:** 14 días (**D14**)
-   **Artículos:** 30 días (**D30**)

De acuerdo con esta configuración, esta es la fecha de pago de costes para cada tipo de transacción:

-   **Horas:** 31 de marzo de 2012, el último día del mes seleccionado.
-   **Gastos:** 19 de marzo de 2012, que es 14 días después de la fecha de la transacción.
-   **Artículos:** 4 de marzo de 2012, que es 30 días después de la fecha de la transacción.

> [!NOTE] 
> La fecha de vencimiento para el pedido de compra se basa en la transacción de proveedor en el momento de creación del pedido de compra del proyecto. La fecha de vencimiento no se determina por la configuración predeterminada. 

La fecha de pago de los costes no se calcula en días de almacenaje. Cuando se completa un proyecto y toda la gestión de costes y facturación, tanto los costes como las ventas se registrarán en las cuentas de ganancias y pérdidas. 

Cuando se completan todas las ventas y facturas de proveedor, puede ver la relación entre los campos en la página **Flujo de efectivo** y los campos de la página **Informes de proyecto**.

:::row:::
    :::column:::
        #### Cash flow page
        - Cash inflows 
        - Cash outflows
        - Net cash flows
    :::column-end:::
    :::column:::
        #### Project statements page
        - Revenue
        - Total cost
        - Gross margin
    :::column-end:::
:::row-end:::

### <a name="review-costs"></a>Revisar los costes

Puede supervisar los costes en los que incurre su organización durante un proyecto en la página **Control de costes**. Comparar los costes presupuestados originales para el proyecto con los costes reales actuales y los gastos comprometidos, puede determinar si el proyecto está en seguimiento, por encima del presupuesto o por debajo del presupuesto. 

> [!NOTE] 
> Cuando se usa la página **Control de costes** para ver el estado actual de los costes del proyecto, use los modelos de previsión seleccionados para presupuestos originales y restantes. Si selecciona otros modelos de previsión al calcular costes, los resultados del cálculo no serán precisos.

#### <a name="viewing-the-remaining-budgeted-amounts"></a>Ver los importes presupuestados pendientes

Si está seleccionada la opción **Presupuesto restante** como el método de control de costes en la página **Parámetros de gestión de proyectos y contabilidad**, la página **Control de costes** calcula los costes que no se han registrado como reales o marcado como comprometidos. Específicamente, los importes de la pestaña **General** en el panel inferior de la página **Control de costes** se calculan de las siguientes formas:

-   **Coste real**: importe total que se ha dedicado al proyecto para la línea de costes seleccionada. El importe del coste real se calcula en la página **Actualizaciones de contabilidad**.
-   **Gasto comprometido**: el importe adicional de gastos que la entidad jurídica se ha comprometido a pagar. Los importes de gasto comprometido específicos se calculan en la página **Gastos comprometidos**.
-   **Presupuesto restante**: el importe presupuestado original que aún está disponible para la línea de coste seleccionada. El importe presupuestario restante se calcula en la página **Vista previa de contabilidad general**.
-   **Coste total**: la suma de los importes del coste real, el coste comprometido y el presupuesto restante.

En la página **Control de costes**, en la pestaña **Desviación**, puede ver una comparación de los costes previstos totales con el presupuesto original. Esta comparación muestra las diferencias entre estos importes. Por lo tanto, puede ver dónde no coinciden los datos. Los importes de desviación se calculan del siguiente modo:

-   **Presupuesto original**: el importe que se presupuestó originalmente para la línea de coste seleccionada. El importe presupuestario original se calcula en la página **Vista previa de contabilidad general**.
-   **Coste total**: la suma del coste real, el gasto comprometido y el presupuesto restante, tal como se informó en la pestaña **General**.
-   **Desviación**: la diferencia entre el coste total y el presupuesto original.
-   **Desviación según cantidad**: la diferencia total entre el presupuesto original previsto y el total previsto. Esta diferencia se puede expresar matemáticamente como (Cantidad prevista total) x (Precio medio original - Precio medio total). Este cálculo solo se aplica a las horas del proyecto.
-   **Desviación según precio**: la diferencia total entre el presupuesto original previsto y el total previsto. Esta diferencia se puede expresar matemáticamente como (Precio previsto original) x (Cantidad prevista original - Cantidad prevista total). Este cálculo solo se aplica a las horas del proyecto.

#### <a name="viewing-the-total-budgeted-amounts"></a>Visualización de los importes presupuestados totales

Si la opción **Presupuesto total** está seleccionada como el método de control de costes en la página **Parámetros de gestión de proyectos y contabilidad**, la página **Control de costes** calcula los costes reales y los costes totales del proyecto para ayudarle a detectar las diferencias entre los dos. Específicamente, en la página **Control de costes**, los importes de las columnas del panel inferior de la pestaña **General** se calculan de las siguientes formas:

-   **Coste presupuestado total**: el importe presupuestado total para la línea de costes seleccionada.
-   **Coste real**: el importe total de costes en los que se ha incurrido durante el proyecto hasta la fecha para las líneas de coste seleccionadas.
-   **Gasto comprometido**: el importe total que ha estado comprometido para la línea de coste seleccionada.
-   **Desviación**: la diferencia entre la suma de los costes reales y gastos comprometidos y el coste total. La desviación muestra si los costes adicionales se deben especificar para el presupuesto total.

En la página **Control de costes**, en la pestaña **Desviación**, puede ver la diferencia entre el presupuesto total y el presupuesto original mirando los campos siguientes:

-   **Presupuesto original**: el importe que se presupuestó originalmente para la línea de coste. El presupuesto original se calcula en la página **Vista previa de contabilidad general**.
-   **Coste presupuestado total**: el coste total que se presupuestó originalmente para la línea de coste. El coste presupuestado total se calcula en la página **Vista previa de contabilidad general**.
-   **Desviación**: la desviación para la línea de coste. Este importe se calcula restando el coste total del presupuesto original.
-   **Desviación según cantidad**: la diferencia total entre el presupuesto original y el presupuesto total. Este importe se calcula restando las horas del presupuesto total de las horas del presupuesto original y multiplicando luego la diferencia por el precio de coste presupuestado original. Esta diferencia se puede expresar matemáticamente como (Precio de coste presupuestado original) × (Horas del presupuesto original – Horas del presupuesto total). Este cálculo solo se aplica a las horas del proyecto.
-   **Desviación según precio**: este importe se calcula restando las horas del presupuesto total de las horas del presupuesto original y multiplicando la diferencia por el número total de horas consumidas. Esta diferencia se puede expresar matemáticamente como (Horas consumidas totales) x (Horas del presupuesto original – Horas del presupuesto total). Este cálculo solo se aplica a las horas del proyecto.

### <a name="analyze-utilization"></a>Analizar la utilización

La tasa de utilización es el porcentaje de tiempo en que un trabajador realiza trabajo facturable o trabajo productivo en un período de trabajo específico. Las horas facturables son las horas del trabajador que se pueden cargar a un cliente específico. 

Una tasa de utilización de un trabajador se calcula dividiendo el número de horas facturables por el número de horas laborables en un período específico. Por ejemplo, si un trabajador tiene 30 horas facturables en un período, y el número de horas laborables en el mismo período de tiempo es 40, la tasa de utilización del trabajador es del 75 por ciento. 

Al calcular la tasa de utilización de un trabajador, puede calcular la tasa facturable o el índice de eficacia:

-   **Tasa facturable**: la diferencia entre las horas facturables y las horas no facturables o las horas de norma.
-   **Índice de eficacia**: la diferencia entre las horas productivas y las horas no productivas u horas de norma. Las horas productivas son las horas que el trabajador dedica a contribuir para un proyecto específico. Las horas productivas se facturan normalmente a los clientes, excepto en el caso de los proyectos internos. Las horas no productivas nunca se facturan a un cliente.

Las tasas de utilización se calculan según la página **Utilización de horas**. Los cálculos se basan en preferencias predeterminadas. Estas preferencias también especifican la manera en que se calculan las horas asignando **Utilización** o **Carga** a cada tipo de proyecto. Esto se aplica a cálculos de tarifas facturables y cálculos de índice de eficacia.

-   **Utilización**: las horas notificadas para el tipo de proyecto seleccionado siempre se consideran para utilización de eficacia o facturable.
-   **Carga**: las horas notificadas para el tipo de proyecto seleccionado siempre se consideran para utilización sin eficacia o no facturable.
-   **Según propiedad de línea**: las propiedades de línea de una transacción de horas en particular determinan si las horas se toman en consideración para facturar o para la utilización de eficacia.
-   **No incluidos**: las horas no se incluyen en el cálculo de utilización de eficacia o facturable.

En la página **Utilización de horas**, junto con el porcentaje total de la tasa de utilización para un trabajador o un proyecto, puede ver el número de horas que se usaron para los cálculos de la tasa de utilización para cada uno de los siguientes tipos de hora:

-   **Horas no incluidas**: estas horas no se incluyen en la tasa de utilización de horas.
-   **Horas incluidas**: estas horas se calculan agregando las horas de utilización y las horas de carga. Estas horas se incluyen en la tasa de utilización.
-   **Horas no facturables**: si está calculando una tasa facturable, estas horas son iguales que las horas no imputables. Si está calculando un índice de eficacia, estas horas son iguales que las horas no productivas.
-   **Horas de utilización**: si está calculando una tasa facturable, estas horas son iguales que las horas imputables. Si está calculando un índice de eficacia, estas horas son iguales que las horas productivas.

Al calcular la tasa de utilización para un trabajador, puede usar horas de norma o las horas incluidas. Si usa horas incluidas, debe asegurarse de que los trabajadores registran todo su horario de trabajo para los períodos de la hoja de horas, ya que el cálculo se expresa como un porcentaje de las horas que se especifican. Al calcular la tasa de utilización de horas para un proyecto, un contrato de proyecto, un registro de clientes o una categoría, debe usar las horas incluidas para el cálculo.

### <a name="review-project-statements"></a>Revisar informes del proyecto

Puede crear un informe del proyecto para ver una instantánea rápida del progreso de un proyecto. Cuando ejecute un informe del proyecto, puede especificar los criterios que se usarán para calcular el informe haciendo selecciones en la pestaña **General** de la página **Informes de proyecto**. Puede seleccionar para incluir o excluir la siguiente información:

-   Tipos de proyectos
-   Tipos de transacciones
-   Fecha del proyecto/fecha contable
-   Datos

Después de que se calcule el informe, podrá ver la siguiente información sobre las distintas pestañas en la página **Informes de proyecto**:

-   **General**: información general sobre la estructura básica de pérdidas y ganancias del proyecto.
-   **Pérdidas y ganancias**: información acerca de los ingresos acumulados.
-   **Trabajo en curso**: información sobre los saldos de cuenta de trabajo en curso.
-   **Consumo**: información acerca del consumo de horas, de artículos, de gastos, y de transacciones de nóminas.
-   **Factura**: información acerca de facturas y facturación a cuenta.
-   **Tasa horaria**: las tarifas por hora registradas en las cuentas de ingresos y de costes.

