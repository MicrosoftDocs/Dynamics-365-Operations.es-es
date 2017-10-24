---
title: "Facturación de empresas vinculadas"
description: "Este artículo proporciona información y ejemplos acerca de la facturación de empresas vinculadas para los proyectos en Microsoft Dynamics 365 Finance and Operations, Enterprise Edition."
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 94153
ms.assetid: 33e98da7-01c1-4369-923d-aa1c8326cb80
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0e6eb4cb0192da40b4d064d955feb75b91f87bbb
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="intercompany-invoicing"></a>Facturación de empresas vinculadas

[!include[banner](../includes/banner.md)]


Este artículo proporciona información y ejemplos acerca de la facturación de empresas vinculadas para los proyectos en Microsoft Dynamics 365 Finance and Operations, Enterprise Edition.

Es posible que su organización tenga varias divisiones, filiales y otras entidades jurídicas que se transfieren productos y servicios entre sí para los proyectos. La entidad jurídica que proporciona el servicio o producto se denomina la *entidad jurídica prestadora* y la entidad jurídica que recibe el servicio o producto se llama la *entidad jurídica prestataria*. 

En la siguiente ilustración se muestra un escenario típico donde dos entidades jurídicas, SI FR (la entidad jurídica prestataria) y SI USA (la entidad jurídica prestadora) comparten recursos para entregar un proyecto para el cliente A. En este escenario, a SI FR se le contrata para entregar el trabajo al cliente A. 

[![Ejemplo de facturación de empresas vinculadas](./media/interco.invoicing-01.jpg)](./media/interco.invoicing-01.jpg) 

El objetivo es realizar un control de costes, reconocimiento de ingresos, impuestos y precio de transferencia para las transacciones de empresas vinculadas más flexibles y eficaces. Además, se proporcionan las siguientes capacidades:

-   Crear facturas de clientes para un proyecto en una entidad jurídica prestataria mediante hojas de horas de empresas vinculadas, gastos y facturas de proveedor en una entidad jurídica prestadora.
-   Admitir cálculos de impuestos y costes indirectos.
-   Aplazar el reconocimiento de ingresos en una entidad jurídica prestadora y cuando una entidad jurídica prestataria deba reconocer el coste.
-   Acumular ingresos de trabajo en curso en la entidad jurídica prestadora.
-   Establecer precios de transferencia que se pueden basar en varios modelos de precios. A continuación se incluyen algunos ejemplos:
    -   **Cantidad**: el importe que especifique en el campo **Precio** es el coste real por cantidad o unidad.
    -   **Importe de gastos**: el precio o coste por transacción más el importe de gastos que especifique en el campo **Precio**.
    -   **Porcentaje de gastos**: el precio de transferencia es el precio/coste por transacción multiplicado por el porcentaje de gastos que especifique en el campo **Precio**.
    -   **Porcentaje de precio de venta**: el porcentaje del precio de venta que se transfiere a la entidad jurídica prestadora.
    -   **Importe por debajo del precio de venta**: el importe que la entidad jurídica prestataria retiene del precio de venta antes de la transferencia a la entidad jurídica prestadora.
    -   **Coeficiente de contribución**: el número que especifique en el campo **Precio** es el coeficiente de contribución que se expresa como porcentaje del precio de ventas.

## <a name="example-1-set-up-parameters-for-intercompany-invoicing"></a>Ejemplo 1: configurar parámetros para la facturación de empresas vinculadas
En este ejemplo, USSI es una entidad jurídica prestadora y sus recursos notifican tiempo frente a la entidad jurídica prestataria, FRSI, que posee el contrato con el cliente final. Horas y los gastos que los empleados de USSI notifican se pueden incluir en la factura del proyecto que FRSI genera. Además, hay un tercer origen de transacciones que se pueden originar en la entidad jurídica prestadora (USSI en este ejemplo) cuando proporciona servicios de proveedores compartidos a filiales (como FRSI) y después pasa esos costos a proyectos dentro de esas filiales. Finance and Operations completa todos los cálculos de impuestos y documentos de facturas coincidentes. 

Para este ejemplo, FRSI debe ser un cliente de la entidad jurídica USSI y USSI debe ser un proveedor de la entidad jurídica FRSI. A continuación, puede configurar una relación entre empresas vinculadas entre las dos entidades jurídicas. En el siguiente procedimiento se muestra cómo configurar los parámetros para que ambas entidades jurídicas puedan participar en la facturación de empresas vinculadas.

1.  Configure FRSI como un cliente en la entidad jurídica USSI y USSI como un proveedor en la entidad jurídica FRSI. Existen tres puntos de entrada para los pasos necesarios para esta tarea.
    | Paso | Punto de entrada                                                                       | Descripción   |
    |------|-----------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | A    | En USSI, haga clic en **Clientes** &gt; **Clientes** &gt; **Todos los clientes**. | Crear un nuevo registro de cliente para FRSI y seleccione el grupo de clientes.                                                                                                                                                                                                                           |
    | mil millones    | En FRSI, haga clic en **Proveedores** &gt; **Proveedores** &gt; **Todos los proveedores**.        | Crear un nuevo registro de proveedor para USSI y seleccione el grupo de proveedores.                                                                                                                                                                                                                               |
    | C    | En FRSI, abra el registro de proveedor que acaba de crear.                            | En el panel de acciones, en la pestaña **General**, en el grupo **Configurar**, haga clic en **Empresas vinculadas**. En la página **Empresas vinculadas**, en la pestaña **Relación comercial**, establezca el control deslizante **Activo** en **Sí**. En el campo **Empresa cliente** , seleccione el registro del cliente que creó en el paso A. |

2.  Haga clic en **Gestión de proyectos y contabilidad** &gt; **Configuración** &gt; **Parámetros de contabilidad de gestión de proyectos** y, a continuación, haga clic en la pestaña **Empresas vinculadas**. La forma en que se configuran los parámetros depende de si usted es la entidad jurídica que recibe el préstamo o la entidad jurídica que otorga el préstamo.
    -   Si es la entidad jurídica prestataria, seleccione la categoría de compras que debe utilizarse para que coincida con las facturas de proveedor, que se generan automáticamente.
    -   Si es la préstamo entidad prestadora, para cada entidad prestataria, seleccione una categoría de proyecto predeterminada para cada tipo de transacción. Las categorías del proyecto se utilizan para la configuración de impuestos cuando la categoría facturada en las transacciones entre empresas vinculadas solo existe en la entidad jurídica prestataria. Puede acumular ingresos para transacciones de empresas vinculadas. Esta acumulación se realiza cuando se registran las transacciones y, a continuación, se invierte cuando se registra la factura de empresas vinculadas.

3.  Haga clic en **Administración de proyectos y contabilidad** &gt; **Configurar** &gt; **Precios** &gt; **Precio de transferencia**.
4.  Seleccione una moneda, el tipo de transacción y el modelo de precio de transferencia. La moneda que se usa en la factura es la moneda que se configura en el registro del cliente para la entidad jurídica prestataria en la entidad jurídica prestadora. La divisa se utiliza para conciliar entradas de la tabla de precios de transferencia.
5.  Haga clic en **Contabilidad general** &gt; **Configuración del registro** &gt; **Contabilidad de empresas vinculadas** y configure una relación para USSI y FRSI.

## <a name="example-2-create-and-post-an-intercompany-timesheet"></a>Ejemplo 2: crear y registrar una hoja de horas de empresas vinculadas
USSI, la entidad jurídica prestadora, debe crear y registrar la hoja de horas para un proyecto desde FRSI, la entidad jurídica prestataria. Existen dos puntos de entrada para los pasos necesarios para esta tarea.

| Paso | Punto de entrada                                                                       | Descripción                                                                                                                                                                                       |
|------|-----------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| A    | **Administración de proyectos y contabilidad** &gt; **Hojas de horas** &gt; **Todas las hojas de horas** | Cree una hoja de horas nueva. En la línea de la hoja de horas, en el campo **Entidad jurídica**, seleccione **FRSI**. En el campo **Id. de proyecto**, seleccione el proyecto en FRSI. Indique las hora para cada día de la semana. |
| mil millones    | Página **Hoja de horas**                                                                | Una vez que se ejecute el flujo de trabajo, registre la hoja de horas y anote el número de asiento.                                                                                                               |

## <a name="example-3-create-and-post-an-intercompany-vendor-invoice"></a>Ejemplo 3: crear y registrar una factura de proveedor de empresas vinculadas
USSI, la entidad jurídica prestadora, debe crear y registrar la factura de proveedor de empresas vinculadas para un proyecto desde FRSI, la entidad jurídica prestataria. Esta factura de proveedor representa los gastos y la mano de obra subcontratada que realizaron los proveedores y que USSI paga. Existen dos puntos de entrada para los pasos necesarios para esta tarea.

| Paso | Punto de entrada                                                                                      | Descripción                                                                                                                                                                                                                                                                          |
|------|--------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| A    | **Proveedores** &gt; **Facturas** &gt; **Facturas de proveedor abiertas** &gt; **Nueva factura de proveedor** | Cree una nueva factura de proveedor y especifique los servicios que se suministraron en nombre del proyecto de FRSI.                                                                                                                                                                                  |
| mil millones    | La página **Factura de proveedor**                                                                      | Introduzca las líneas que representan los servicios subcontratados en nombre de FRSI. En la ficha desplegable **Detalles de línea**, en la pestaña **Proyecto** para la línea de factura, en el campo **Empresa de proyecto**, escriba **FRSI**. Escriba la información correspondiente y del proyecto. A continuación, registre la factura de proveedor. |

## <a name="example-4-create-and-post-the-intercompany-invoice"></a>Ejemplo 4: crear y registrar la factura de empresas vinculadas
USSI, la entidad jurídica prestadora, debe crear y registrar la factura de empresas vinculadas. Existen dos puntos de entrada para los pasos necesarios para esta tarea.

| Paso | Punto de entrada                                                                                             | Descripción                                                                                                                                      |
|------|---------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| A    | **Gestión de proyectos y contabilidad** &gt; **Facturas del proyecto** &gt; **Factura de cliente de empresas vinculadas**  | Haga clic en **Nueva** para abrir la página **Crear factura de empresas vinculadas**.                                                                                  |
| mil millones    | **Gestión de proyectos y contabilidad** &gt; **Facturas del proyecto** &gt; **Facturas de cliente de empresas vinculadas** | En la página **Crear factura de empresas vinculadas**, especifique la entidad jurídica, la transacción que se debe incluir y, a continuación, haga clic en **Buscar**. |
| C    | **Gestión de proyectos y contabilidad** &gt; **Facturas del proyecto** &gt; **Facturas de cliente de empresas vinculadas** | Seleccione las transacciones para facturar o haga clic en **Seleccionar todo** para facturar todas las transacciones de la lista y, a continuación, haga clic en **Aceptar**.                  |
| D    | La página **Factura de empresa vinculada**                                                                       | Se muestra la propuesta de la factura de cliente de empresas vinculadas.                                                                                             |
| E    | La página **Factura de empresa vinculada**                                                                       | Haga clic en **Registrar**.                                                                                                                                  |

## <a name="example-5-post-the-vendor-invoice-and-invoice-the-customer"></a>Ejemplo 5: registrar la factura de proveedor y facturar al cliente
Cuando la entidad jurídica prestadora, USSI, registra la factura de cliente de empresas vinculadas, se crea un factura de proveedor pendiente de coincidencia en entidad jurídica prestataria, FRSI. Una vez se registra la factura de proveedor, FRSI también factura al cliente del proyecto por las horas que USSI especificó. Existen tres puntos de entrada para los pasos necesarios para esta tarea.

| Paso | Punto de entrada                                                                                        | Descripción                                                                                                             |
|------|----------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| A    | **Proveedores** &gt; **Facturas** &gt; **Facturas de proveedor pendientes**                            | Revise la factura para comprobar que los valores de la hoja de horas están incluidos y, a continuación, registre la factura de proveedor.                  |
| mil millones    | **Gestión de proyectos y contabilidad** &gt; **Facturas del proyecto** &gt; **Propuestas de factura de proyecto** | Crear una nueva factura de proyecto para el proyecto y compruebe que aparecen las transacciones de horas que se registraron.            |
| C    | La página **Factura del proyecto**                                                                       | Seleccione la factura del proyecto y, a continuación, haga clic en **Ver detalles** para revisar el coste y el importe de ventas. A continuación, registre la factura. |


Para obtener más información, consulte [Configurar la facturación de proyecto de empresas vinculadas](tasks/configure-intercompany-project-invoicing.md).



