---
title: Administración de concesión de comercialización
description: Este tema describe la administración de concesiones de comercialización para Dynamics 365 Supply Chain Management.
author: t-benebo
manager: tfehr
ms.date: 08/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: t-benebo
ms.search.validFrom: 2018-01-31
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 7fdcf8a7294d8c7579f35bc108bdd3804da9a837
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203259"
---
# <a name="trade-allowance-management"></a>Administración de concesión de comercialización

[!include [banner](../includes/banner.md)]

La administración de concesiones de comercialización ayuda a las empresas a administrar los programas de la promoción de ventas que proporcionan recompensas monetarias de pago por rendimiento a los clientes que llegan a los objetivos de rendimiento y volumen. Las capacidades de la función están diseñadas para las empresas que se centran en procesos completos de fomento de ganancias, desde el presupuesto de fondos de la promoción y la asignación, a la creación y el proceso de demandas, al procesamiento de pagos y al análisis de eficacia de la promoción.


Este artículo proporcionará una visión general amplia de las características de la gestión de concesión comercial y le familiarizará con el conjunto típico de tareas implicadas en administrar un programa de promoción de ventas. Se espera que varios tipos de usuarios que tienen responsabilidades operativas y de toma de decisiones utilicen esta funcionalidad para alcanzar sus objetivos respectivos:

- Asignando fondos discrecionales a las cuentas seleccionadas, y configurando acuerdos de concesión comercial para las promociones, en función de las facturaciones por uso y los pagos de suma total excepcionales (para un servicio acordado)
- Ejecutando los contratos negociados de la promoción con ventas en curso y generando demandas de facturación por uso
- Calcular, aprobar, y procesar las demandas generadas y, pasarlas a los clientes (Clientes) como deducciones de liquidación de pago
- Conciliando la pago incompleto del cliente con la deducción
- Seguir el uso del fondo promocional, y evaluar la rentabilidad y la eficacia del programa

## <a name="audience-and-purpose"></a>Público y propósito

La información de este documento está destinada a aquellos responsables de la toma de decisiones de las empresas, como gerentes de compras, directores financieros (CFO) y administradores contables, que tienen las responsabilidades siguientes:

- Presupuestos y asignación de fondos de nivel superior
- Planificación y análisis de promociones de ventas
- Administrar al personal que procesa demandas de facturación por uso, ejecutar los pagos basándose en eventos de marketing, y liquidar pagos anticipados y deducciones

Las personas de estos puestos buscan formas de conseguir estos objetivos:

- Mejor uso que los fondos promocionales de marketing.
- Adaptar con flexibilidad los diferentes tipos de programas de promoción y las concesiones.
- Reducir la carga administrativa y aquellos errores asociados al rendimiento de los procesos de supervisión y el procesamiento de reclamaciones.
- Mejorar las previsiones del flujo de efectivo mediante la acumulación de futuros pasivos.
- Obtener una base cuantificada para las negociaciones en curso y futuras sobre promociones con los clientes.

## <a name="promotional-fund-and-trade-allowance-agreement"></a>Acuerdo de concesión de comercialización y de fondos promocionales

Un acuerdo de concesión comercial es un programa de incentivo donde los premios monetarios de pago por rendimiento se ofrecen a los clientes que consiguen objetivos fijados de volumen o comportamiento. Los fondos promocionales son los gastos presupuestados. De esa manera, las campañas promocionales pueden ser capturadas.

### <a name="promotional-fund"></a>Fondo de promoción

Los fondos asignados a los acuerdos de concesión comercial se registran en la página **Fondos**. Para abrir la página **Fondos**, selecciona **Ventas y marketing** \> **Permisos comerciales** \> **Fondos** \> **Fondos**.

![Página de fondos](./media/trade-allowance-management-funds-page.png "Página de fondos")

En la página **Fondos**, puede ver los detalles de los fondos promocionales.

La ficha desplegable **General** muestra el período durante el cual el fondo es válido así como su importe presupuestado. Para asignar el fondo al acuerdo de la promoción, el campo **Estado** debe tener el valor **Aprobado**.

La ficha desplegable **Clientes** muestra la jerarquía del cliente. Para seleccionar los clientes a los que está destinado el fondo, arrástralos de modo que se encuentren en **Fondo de Clientes**. Esta ficha desplegable también muestra cómo el importe total del fondo se distribuye.

La ficha desplegable **Artículos** muestra los artículos que se incluyen en la promoción.

### <a name="trade-allowance-agreement"></a>Acuerdo de concesión de comercialización

Después de que la definición de fondo se active, el paso siguiente de la planificación de la promoción es registrar los contratos de la promoción (que se conocen como acuerdos de concesión comercial), asignar fondos, y definir los objetivos de rendimiento para cada evento de merchandising.

Los acuerdos de concesión comercial se registran en la página **Acuerdos de concesión comercial**. Para abrir la página **Acuerdos de concesión comercial**, seleccione **Ventas y marketing** \> **Permisos comerciales** \> **Acuerdos de concesión comercial**.

![Página de acuerdos de concesión de comercialización](./media/trade-allowance-management-agreements-page.png "Página de acuerdos de concesión de comercialización")

#### <a name="header"></a>Encabezado

Seleccione **Encabezado** para cambiar a la vista de encabezado.

En la ficha desplegable **General**, los campos **Orden a** y **Orden de** definen el período en que el acuerdo es válido. El estado de aprobación **Aprobado interno** para el acuerdo indica que el acuerdo todavía no es válido y no se puede aplicar durante el procesamiento de pedido de ventas.

La sección **Análisis** de la ficha desplegable **General** contiene campos importantes que definen las cantidades y los costes que se usan para la evaluación de la promoción:

- El campo **Unidades base** especifica la cantidad de productos que se deben vender a los clientes seleccionados antes de que se aplique la promoción.
- El valor **Cantidad de envío calculada** se calcula en función del valor **porcentaje de incremento**, que es un aumento planificado objetivo para esta promoción.
- El campo **Coste de concesión de comercialización** se calcula en función de las cantidades de los distintos eventos del acuerdo de concesión comercial.

En la ficha desplegable **Clientes**, en la lista situada a la izquierda, puede seleccionar y ver los grupos de clientes, que se configuran como jerarquías predefinidas. A continuación puede seleccionar toda la jerarquía o cuentas específicas como destinos del acuerdo de concesión.

En la ficha desplegable **Artículos**, como en la ficha desplegable **Artículos** de la página **Fondos**, los productos se agregan al acuerdo para asociar sus ventas a la concesión que se acordó.

En la ficha desplegable **Fondos**, se pueden ver los fondos de promoción asociados a este contrato. También puede ver la asignación de costes del evento del contrato. Una asignación de costes del evento del 100 por ciento significa que esta promoción se financiará exclusivamente desde un fondo. Como alternativa, se puede crear un acuerdo de la promoción en varios fondos, y se puede utilizar una asignación del porcentaje igual o diferenciada.

#### <a name="lines"></a>Líneas

A continuación, seleccione **Líneas** para cambiar a la vista Líneas.

La pestaña **Eventos de marketing** muestra los tipos de eventos que cubre un acuerdo. Hay tres tipos: pago por uso, suma total y descuento en factura.

Cuando selecciona el evento de marketing y después selecciona la pestaña **Importes**, los detalles del evento se encuentran.

![Líneas de acuerdo de concesión de comercialización](./media/trade-allowance-management-agreements-lines.png "Líneas de acuerdo de concesión de comercialización")

En la sección **Líneas de concesión de comercialización** , especifique los intervalos de cantidad o importe que el cliente debe conseguir para que las definicones obtengan las recompensas.

En el caso de un evento de marketing del tipo **Facturación por uso**, la sección superior la pestaña **Importes** define las reglas de aplicación, generación y pago de la facturación por uso. Por ejemplo, las reglas pueden especificar las siguientes condiciones para la demanda de facturación por uso:

- Se basa en la fecha de creación del pedido de ventas (el valor **Tipo de la fecha de cálculo** es **Creado**).
- Se calcula basándose en el importe de la línea de pedido de ventas antes de los descuentos, no el importe neto, que incluye descuentos (el valor **Procedente de** es **Bruto**).
- Se basa en el volumen de los productos vendidos, no en el importe (el valor **Tipo de salto de línea de devolución** es **Cantidad**).
- Se calcula por período de un mes (el valor **Acumular ventas por** es **Mes**). 
- Se liquida como deducción, no usando A/P (el valor **Tipo de pago** es **Deducciones de clientes**).

En el caso de un evento de marketing del tipo **Suma total**, la pestaña **Importes** muestra la cantidad que se pagará al cliente en forma de deducción cuando el cliente alcance un rendimiento específico. Un estado de aprobación **abierto** indica que la suma total aún no se ha abonado.

Para aplicar el acuerdo a los pedidos de ventas que cumplen las condiciones de acuerdo, el estado del contrato debe ser **Confirmado**. 

## <a name="perform-sales-under-the-planned-merchandising-event-and-generate-bill-back-claims"></a>Realice las ventas en evento de marketing planificado y genere las demandas de facturación por uso

Al crear un pedido de ventas que tenga líneas que satisfagan los requisitos del acuerdo, puede ver la información relacionada en la página **pedido de ventas** seleccionando **Línea de pedido de ventas** \> **Visión** \> **Detalles de precio**.

En la página **Detalles de precio**, en la ficha desplegable **Devoluciones**, el vendedor puede ver una facturación por uso de un acuerdo de concesión comercial (se muestra el identificador del programa de devoluciones) y el importe total que se aplica a la línea. Este importe también se muestra en el campo **Importe de devolución** que está en la sección **Estimación de margen** de la página **Detalles del precio**.

Cuando se registra la factura de ventas, se genera una demanda de facturación por uso correspondiente para cada línea de factura.

> [!NOTE]
> Para ver la página **Detalles de precio**, en la página **Parámetros de clientes**, en la pestaña **Precios**, seleccione la casilla de verificación **Habilitar detalles del precio**. I

## <a name="process-claims-and-pass-them-as-deductions-to-ar"></a>Procese las demandas y páselas como deducciones a Clientes

Los siguientes pasos del proceso para administrar las facturas por uso consisten en revisar, calcular, y aprobar las demandas y, a continuación, convertirlas en deducciones.

El área de trabajo de facturación por uso es el lugar donde el propietario del acuerdo de la promoción periódicamente revisa y procesa las demandas que se generan. También es donde el administrador de Clientes convierte las demandas aprobadas en deducciones o pagos periódicos, en función del método de pago para la demanda.

En la página **Área de trabajo de facturación por uso**, puede revisar las líneas de la demanda. Si las demandas se encuentran en estado **Para volver a calcular**, se deben volver a calcular para cualquier efecto acumulativo.

### <a name="recalculate-claims"></a>Recalcular las demandas

Para recalcular las demandas, en el panel de acciones, seleccione **Acumular**. A continuación, en el cuadro de diálogo **Devoluciones acumuladas**, seleccione al cliente.

Como resultado del recálculo, el programa genera nuevas demandas para los importes para ajustar las demandas originales al importe por unidad. Una demanda de ajuste se genera para cada combinación única de un cliente, un artículo, una divisa, una unidad de medida, dimensiones de inventario, dimensiones financieras, y un grupo de impuestos. Estas demandas de ajuste tienen la misma referencia al número de pedido de ventas y número de factura que las demandas que se están ajustando (es decir, las demandas creadas originalmente del documento de ventas). A diferencia de la demanda original, la demanda del ajuste no tiene valores en los campos que describen los importes y la cantidad de la línea de pedido de ventas original.

Una vez que el recálculo se completa, el estado de las notificaciones cambia a **Calculado**. Para aprobar las demandas, en el panel de acciones, seleccione **Aprobar**.

### <a name="process-claims-and-pass-them-to-ar"></a>Procese las demandas y páselas a Clientes

Las demandas están listas para el procesamiento de Clientes. Para procesarlas, en el panel de acciones, seleccione **proceso**. 

Al procesar las demandas, el estado ha cambiado a **Marcar** e indica que un registro de diario (el diario que se registra es el diario de acumulación de devoluciones, como se especifica en los parámetros de A/R) ha hecho que los eventos siguientes aparezcan: 

- Las demandas se han transferido al saldo del cliente temporal como deducciones.
- La cuenta de acumulación de devoluciones se ha abonado para representar el pasivo de futuros del cliente.
- La cuenta de gastos de la devolución se ha abonado para reconocer el coste que se incurrió en relación con las ventas.

Para completar el proceso, el administrativo de Clientes debe ahora gestionar las deducciones de acumulación transfiriéndolas al saldo de los clientes como nota de crédito (pasivo). 

Para iniciar la tarea, en el panel de acciones de la página **Cliente**, seleccione **Cobrar** \> **Liquidar transacciones**. A continuación, en la página **Liquidar transacciones**, seleccione **Funciones** \> **Programa de facturación por uso**. Esta página de devoluciones muestra todas las demandas de facturación por uso que se procesaron anteriormente.

Si desea crear una nota de abono, seleccione la casilla de verificación **Marcar** para todas las líneas y, a continuación, seleccione **Funciones** \> **Crear nota de abono**.

Al crear la nota de abono, se registra un diario. (El diario que se registra es el diario de consumo de clientes, como se especifica en los parámetros de Clientes.) Como consecuencia, el importe real de pasivo (crédito) se ha movido al saldo del cliente. Financieramente esta situación implica que los eventos siguientes han aparecido:

- Se ha abonado la cuenta de clientes del cliente.
- Se ha cargado la cuenta de acumulación de devoluciones.

Para aprobar un evento de comercialización del tipo **Suma total**, seleccione el evento en la página **Acuerdos de concesión comercialización** y, a continuación, en la pestaña **importe**, seleccione **aprobar**.

## <a name="settle-the-deduction-that-is-due-and-the-customer-short-pay-by-using-the-deduction-workbench"></a>Liquide la deducción que vence y el pago anticipado del cliente mediante el área de trabajo de deducciones

Con frecuencia, adelantándose a los anticipos, los clientes eligen pagar anticipos de facturas seleccionadas. Para evitar problemas de conciliación de pagos en el futuro, el administrativo de Clientes registra esos anticipos como deducciones cuando registra los pagos reales del cliente. A continuación, en el área de trabajo de deducciones, dichas deducciones de clientes se pueden realizar fácilmente con los importes debidos de la empresa.

Para registrar un pago anticipado de un cliente en el diario de pagos, seleccione **clientes** \> **Pagos** \> **Diario de pagos**, y cree un nuevo diario de pagos. A continuación, en el panel de acciones, seleccione **Deducciones**. En la página **Deducción**, puede crear y realizar un seguimiento del importe que se pagó por anticipado.

El administrador de cobro es responsable ahora de liquidar entre sí la transacción de nota de abono abierta y la transacción de facturación por anticipado en el área de trabajo de la deducción.

Para gestionar deducciones, seleccione **Ventas y marketing** \> **Permisos comerciales** \> **Deducciones** \> **Área de trabajo de deducciones**. La sección superior de la página contiene las líneas que representan los pagos anticipados del cliente. En la sección inferior de la página se ven las transacciones de crédito abiertas de clientes. 

Para liquidar la deducción con la transacción abierta, marque la línea de deducciones y, a continuación, en la ficha Transacciones abiertas, marque la línea. En el panel de acciones, haga clic en Mantener > Asignar.

Ahora el estado de las demandas de origen es **completado**.

## <a name="analyze-the-effectiveness-of-the-promotion-and-fund-consumption"></a>Analizar la eficacia de la promoción y el consumo de fondos

Para obtener una visión general de las estadísticas básicas del programa y el uso de fondos, puede usar varios informes y visiones analíticas disponibles en administración de concesión comercial.

En la página **Actividad de concesión de comercialización** , la pestaña **Visión general** muestra los detalles principales del acuerdo de concesión comercial. Las otras fichas muestran más detalles específicos acerca de los documentos asociados, los pagos, y otros eventos relacionados con el programa.

La pestaña **Resumen** muestra la cantidad total de productos que se han vendido en promoción, el importe de ventas que se ha facturado, y las facturaciones por uso y sumas totales que se han pagado.

La pestaña **Créditos de facturación por uso** contiene los detalles de facturaciones por uso individuales que se han abonado al cliente.

Para obtener una visión general más analítica de las distintas medidas de rendimiento para la promoción, puede usar la vista de análisis. Para ir a la vista de análisis, haga clic en **Ventas y marketing** \> **Concesiones comerciales** \> **Acuerdos de concesión comercial**. En el panel de acciones, haga clic en la ficha **Análisis**.  

Para obtener una visión general más analítica de las distintas medidas de rendimiento para la promoción, puede usar la vista de análisis. Para ir a la vista de análisis, haga clic en **Ventas y marketing** \> **Concesiones comerciales** \> **Acuerdos de concesión comercial**. En el panel de acciones, haga clic en la ficha **Análisis**. 

