---
title: Intrastat sueco
description: Este tema contiene información sobre los informes de Intrastat en Suecia.
author: anasyash
ms.date: 8/24/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: ''
ms.openlocfilehash: 1031b93950e44fe3b1b6254bf1503b4c09d6fd10
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2022
ms.locfileid: "8727409"
---
# <a name="swedish-intrastat"></a>Intrastat sueco

[!include[banner](../includes/banner.md)]

La página **Intrastat** se usa para generar y presentar información sobre el comercio entre los países de la Unión Europea (UE). La declaración Intrastat sueca contiene información sobre el comercio de mercancías para declarar.

La declaración Intrastat sueca incluye los siguientes campos:

   - Código ISO del país del partner
   - Código de transacción
   - Código de mercancía
   - Unidad adicional
   - Importancia
   - Importe de la factura

## <a name="set-up-intrastat"></a>Configurar Intrastat

Importe la versión más reciente de las siguientes configuraciones de Informes electrónicos (ER):

   - Modelo intrastat
   - Informe intrastat
   - Intrastat (SE)

Para obtener más información, consulte [Descargue las configuraciones de ER del repositorio global del servicio de configuración](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

## <a name="set-up-foreign-trade-parameters"></a>Configurar parámetros de comercio exterior

1. En Microsoft Dynamics 365 Finance, vaya a **Impuestos** > **Configuración** > **Parámetros de comercio exterior**.
2. En la pestaña **Intrastat**, en la ficha desplegable **Informes electrónicos**, en el campo **Asignación de formato de archivo**, seleccione **Intrastat (SE)**.
3. En el campo **Asignación de formato de informe**, seleccione **Informe Intrastat**.
4. En la ficha desplegable **Jerarquía de códigos de bienes**, en el campo **Jerarquía de categorías**, seleccione **Intrastat**.
5. En el campo **Codigo de transacción**, seleccione el código de transacción para transferencias de propiedad. Use este código para transacciones que provoquen transferencias de propiedad reales o planificadas a cambio de una compensación (financieras o de otro tipo). Úselo también para correcciones. Las empresas de Suecia utilizan códigos de transacción de un dígito.
6. En el campo **Nota de abono**, seleccione el código de transacción para la devolución de mercancías.
7. En la pestaña **Propiedades de país o región**, en el campo **País o región**, enumere todos los países o regiones con los que su organización hace negocios. Para cada país o región que forma parte de la UE, en el campo **Tipo de país o región**, seleccione **UE**, para que el país o la región aparezca en su informe de Intrastat.

## <a name="set-up-the-product-parameters-for-the-intrastat-declaration"></a>Configurar los parámetros del producto para la declaración de Intrastat

1. Vaya a **Gestión de información de productos** > **Productos** > **Productos emitidos**.
2. En la cuadrícula, seleccione un producto.
3. En la ficha desplegable **Comercio exterior**, en la sección **Intrastat**, en el campo **Mercancía**, seleccione el código de mercancía.
4. En la ficha desplegable **Administrar inventario**, en el campo **Peso neto**, introduzca el peso del producto en kilogramos.
5. Vaya a **Impuestos** > **Configuración** > **Comercio exterior** > **Compresión de Intrastat** y seleccione los campos que se deben comparar cuando se resume la información de Intrastat. Para el Intrastat sueco, seleccione los siguientes campos:

    - Código Intrastat de la mercancía
    - Código de transacción
    - Dirección
    - País/región
    - Corrección
    - Factura

## <a name="intrastat-transfer"></a>Transferencia intrastat

En la página **Intrastat**, en el panel de acciones, puede seleccionar **Transferir** para transferir automáticamente la información sobre el comercio intracomunitario de sus órdenes de venta, facturas de servicios, órdenes de compra, facturas de proveedores, recibos de productos de proveedores, facturas de proyectos y órdenes de transferencia. Solo se transferirán los documentos que tengan un país de la UE como país o región de destino (para envíos) o consignación (para llegadas).

Alternativamente, puede introducir transacciones manualmente seleccionando **Nuevo** en el Panel de acciones.

### <a name="generate-an-intrastat-report"></a>Genere un informe Intrastat

1. Vaya a **Impuestos** > **Declaraciones** > **Comercio exterior** > **Intrastat**.
2. En el panel de acciones, seleccione **Salida** > **Informe**.
3. En el cuadro de diálogo **Informe Intrastat**, establezca los campos siguientes.

    | Campo            | Descripción                                                                                                                         |
    |------------------|-------------------------------------------------------------------------------------------------------------------------------------|
    | Fecha de inicio        | Seleccione la fecha inicial del informe.                                                                                               |
    | Fecha de finalización          | Seleccione la fecha final del informe.                                                                                                 |
    | Generar archivo    | Establezca esta opción en **Sí** para generar un archivo .txt para el informe de Intrastat.                                                       |
    | Nombre de archivo        | Especifique el nombre del archivo .txt.                                                                                                    |
    | Generar informe  | Establezca esta opción en **Sí** para generar un archivo .xlsx para el informe de Intrastat.                                                     |
    | Nombre de archivo del informe | Especifique el nombre del archivo .xlsx.                                                                                                   |
    | Dirección        | Seleccione **Llegadas** para un informe sobre llegadas intracomunitarias. Seleccione **Envíos** para un informe sobre los envíos intracomunitarios. |

4. Seleccione **Aceptar** y revise los informes generados.

## <a name="example"></a>Ejemplo

Este ejemplo muestra cómo registrar llegadas y envíos para Intrastat. Usa la entidad jurídica **DEMF**.

### <a name="preliminary-setup"></a>Configuración preliminar

1. Vaya a **Administración de la organización** > **Organización** > **Entidades jurídicas** y seleccione la entidad jurídica **DEMF**.
2. En la ficha desplegable **Direcciones**, seleccione **Editar** y después, en el campo **País o región**, seleccione **SWE (Suecia)**.
3. Importe la versión más reciente de las siguientes configuraciones de ER:

    - Modelo intrastat
    - Informe intrastat
    - Intrastat (SE)

### <a name="create-transaction-codes"></a>Crear códigos de transacción

1. Vaya a **Impuestos** > **Configurar** > **Comercio exterior** > **Códigos de transacción**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el campo **Código de** **transacción**, introduzca **1**.
4. En el campo **Nombre**, introduzca **Transacciones normales**.
5. En el panel Acciones, seleccione **Guardar**.

### <a name="set-up-foreign-trade-parameters"></a>Configurar parámetros de comercio exterior

1. Vaya a **Impuestos** > **Configuración** > **Comercio exterior** > **Parámetros de comercio exterior**.
2. En la pestaña **Intrastat**, en la ficha desplegable **General**, en el campo **Código de** **transacción**, seleccione **1**.
3. En la ficha desplegable **Informes electrónicos**, en el campo **Asignación de formato de archivo**, seleccione **Intrastat (SE)**.
4. En el campo **Asignación de formato de informe**, seleccione **Informe de Intrastat**.
5. En la ficha desplegable **Jerarquía de códigos de mercancías**, en el campo **Jerarquía de categorías**, asegúrese de que **Intrastat** está seleccionado.
6. En la pestaña **Propiedades de país/región**, seleccione **Nueva**.
7. En el campo **País/región de tercero**, seleccione **SWE**.
8. En el campo **Tipo de país/región**, seleccione **Nacional**.
9. En el campo **País/región de tercero**, seleccione **DEU** y después, en el campo **Tipo de país/región**, seleccione **UE**.

### <a name="set-up-product-information"></a>Configurar información de productos

1. Vaya a **Gestión de información de productos** > **Productos** > **Productos emitidos**.
2. En la cuadrícula, seleccione **D0001**.
3. En la ficha desplegable **Comercio exterior**, en la sección **Intrastat**, en el campo **Mercancía**, seleccione **100 200 30**.
4. En la ficha desplegable **Administrar inventario**, en la sección **Medidas de peso**, en el campo **Peso neto**, introduzca **5**.
5. En el panel Acciones, seleccione **Guardar**.

### <a name="change-the-site-address"></a>Cambiar la dirección del sitio

1. Vaya a **Gestión de almacenes** > **Configurar** > **Almacén** > **Sitios**.
2. En la cuadrícula, seleccione **1**.
3. En la ficha desplegable **Direcciones**, seleccione **Editar**.
4. En el cuadro de diálogo **Editar dirección**, en el campo **País/región**, seleccione **SWE**.
5. Seleccione **Aceptar**.

### <a name="create-a-sales-order-with-an-eu-customer"></a>Crear un pedido de ventas con un cliente de la UE

1. Vaya a **Clientes** > **Pedidos** > **Todos los pedidos de ventas**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el cuadro de diálogo **Crear pedido de ventas**, en la ficha desplegable **Cliente**, en la sección **Cliente**, en el campo **Cuenta de cliente**, seleccione **DE-015**.
4. En la ficha desplegable **General**, en la sección **Dimensiones de almacenamiento**, en el campo **Sitio**, seleccione **1**.
5. En el campo **Almacén**, seleccione **11**.
6. Seleccione **Aceptar**.
7. En la pestaña **Líneas**, en la ficha desplegable **Líneas de pedido de ventas**, en el campo **Número de artículo**, seleccione **D0001**. En el campo **Cantidad**, especifique **10**.
8. En la ficha desplegable **Detalles de línea**, en la pestaña **Comercio exterior**, asegúrese de que los campos **Código de transacción** y **Mercancía** se han establecido automáticamente.
9. En el panel Acciones, seleccione **Guardar**.
10. En el panel de acciones, en la pestaña **Factura**, en la sección **Generar**, seleccione **Factura**.
11. En el cuadro de diálogo **Registro de factura**, en la ficha desplegable **Parámetros**, en la sección **Parámetro**, en el campo **Cantidad**, seleccione **Todos**.
12. Seleccione **Aceptar** para registrar la factura.

### <a name="transfer-the-transaction-to-the-intrastat-journal-and-review-the-result"></a>Transferir la transacción al diario de Intrastat y revisar el resultado

1. Vaya a **Impuestos** > **Declaraciones** > **Comercio exterior** > **Intrastat**.
2. En el panel de acciones, seleccione **Transferir**.
3. En el cuadro de diálogo **Intrastat (transferencia)**, en la sección **Parámetros**, configure la opción **Factura del cliente** a **Sí**.
4. Seleccione **Filtro**.
5. En el cuadro de diálogo **Filtro de Intrastat**, en la pestaña **Rango**, seleccione la primera línea y asegúrese de que el campo **Campo** esté establecido en **Fecha**.
6. En el campo **Criterio**, seleccione la fecha actual.
7. Seleccione **Aceptar** para cerrar el cuadro de diálogo **Filtro de Intrastat**.
8. Seleccione **Aceptar** para cerrar el cuadro de diálogo **Intrastat (Transferir)** y revise el resultado. La línea representa el pedido de ventas que creó antes.

    ![Líneas de diario de Intrastat para pedidos de ventas](media/swe_intrastat_journal_sales_order.png)

9. Seleccione la línea de transacción y luego seleccione la pestaña **General** para ver más detalles.

    ![Detalles de línea del diario de intrastat para pedido de ventas](media/swe_intrastat_journal_sales_order_line_details.png)

10. En el panel de acciones, seleccione **Salida** > **Informe**.
11. En el cuadro de diálogo **Informe Intrastat**, en la ficha desplegable **Parámetros**, en la sección **Fecha**, seleccione el mes del pedido de ventas que creó.
12. En la sección **Opciones de** **exportación**, establezca la opción **Generar archivo** en **Sí**. Después, en el campo **Nombre de archivo**, especifique el nombre necesario.
13. Establezca la opción **Generar informe** en **Sí**. Después, en el campo **Nombre de archivo del informe**, especifique el nombre necesario.
14. En el campo **Dirección**, seleccione **Envíos**.
15. Seleccione **Aceptar** y revise el informe en formato .txt que se genera. En la tabla siguiente se muestran los valores en el informe de ejemplo.

    | Código ISO del país del partner | Código de transacción | Código de mercancía | Unidad adicional | Importancia | Importe de la factura |
    |--------------------------|------------------|----------------|-----------------|--------|----------------|
    | IT                       | 1                | 10020030       | 0               | 50     | 3290           |

16. Revise el informe en formato Excel que se genera.

    ![Informe intrastat](media/swe_intrastat_report_for_dispatches.png)

### <a name="create-a-purchase-order"></a>Crear un pedido de compra

1. Vaya a **Proveedores** > **Pedidos de compra** > **Todos los pedidos de compra**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el cuadro de diálogo **Crear pedido de compra**, en el campo **Cuenta de proveedor**, seleccione **DE-001**.
4. Seleccione **Aceptar**.
5. En la pestaña **Encabezado**, en la ficha desplegable **Comercio** **exterior**, compruebe que el campo **Código de transacción** está configurado en **1**.
6. En la pestaña **Líneas**, en la ficha desplegable **Líneas de pedido de compra**, en el campo **Número de artículo**, seleccione **D0001**. Después, en el campo **Cantidad**, especifique **6**.
7. En el panel de acciones, en la ficha **Compra**, en el grupo **Acciones**, seleccione **Confirmar**.
8. En el panel de acciones, en la ficha **Factura**, en el grupo **Generar**, seleccione **Factura**.
9. En el panel de acciones, seleccione **Valor predeterminado de origen**. En el campo **Cantidad predeterminada para líneas**, seleccione **Cantidad pedida**. A continuación seleccione **Aceptar**.
10. En la ficha desplegable **Encabezado de factura de proveedor**, en la sección **Identificación de factura**, en el campo **Número**, escriba **0001**.
11. En el panel de acciones, seleccione **Registrar** para registrar la factura.

### <a name="create-an-intrastat-declaration-for-arrivals"></a>Crear una declaración de Intrastat para las llegadas

1. Vaya a **Impuestos** > **Declaraciones** > **Comercio exterior** > **Intrastat**.
2. En el panel de acciones, seleccione **Transferir**.
3. En el cuadro de diálogo **Intrastat (Transferir)**, establezca la opción **Factura de proveedor** en **Sí**.
4. Seleccione **Aceptar** para transferir las transacciones y, a continuación, revise el diario de intrastat.

    ![Diario de Intrastat para pedido de compra](media/swe_intrastat_journal_purchase_order.png)

5. Revisa el pedido de compra en la pestaña **General**.

    ![Detalles de línea del diario de Intrastat para pedido de compra](media/swe_intrastat_journal_purchase_order_line_details.png)

6. En el panel de acciones, seleccione **Salida** > **Informe**.
7. En el cuadro de diálogo **Informe Intrastat**, en la ficha desplegable **Parámetros**, en la sección **Fecha**, seleccione el mes del pedido de ventas que creó.
8. En la sección **Opciones de** **exportación**, establezca la opción **Generar archivo** en **Sí**. Después, en el campo **Nombre de archivo**, especifique el nombre necesario.
9. Establezca la opción **Generar informe** en **Sí**. Después, en el campo **Nombre de archivo del informe**, especifique el nombre necesario.
10. En el campo **Dirección**, seleccione **Llegadas**.
11. Seleccione **Aceptar** y revise el informe en formato .txt que se genera. En la tabla siguiente se muestran los valores en el informe de ejemplo.

    | Código ISO del país del partner | Código de transacción | Código de mercancía | Unidad adicional | Importancia | Importe de la factura |
    |--------------------------|------------------|----------------|-----------------|--------|----------------|
    | IT                       | 1                | 10020030       | 0               | 30     | 1714           |

12. Revise el informe en formato Excel que se genera.

    ![Informe de llegadas de Intrastat](media/swe_intrastat_arrivals_report.png)
