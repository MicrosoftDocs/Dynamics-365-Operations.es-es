---
title: Registrar llegadas y envíos para Intrastat
description: Este tema proporciona un ejemplo que muestra cómo registrar llegadas y envíos para Intrastat.
author: anasyash
ms.date: 8/23/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: ''
ms.openlocfilehash: 4ab4402740d199043519773b18732bdde9a0fb2f
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2022
ms.locfileid: "8724794"
---
# <a name="post-arrivals-and-dispatches-for-intrastat"></a>Registrar llegadas y envíos para Intrastat

[!include [banner](../includes/banner.md)]

Este tema proporciona un ejemplo que muestra cómo registrar llegadas y envíos para Intrastat. En el ejemplo se usa la entidad jurídica **ITCO**.

## <a name="setup"></a>Configurar

1. Importe la versión más reciente de las siguientes configuraciones de Informes electrónicos (ER):

    - Modelo intrastat
    - Informe intrastat
    - Intrastat (IT)

    Para obtener más información, consulte [Descargar las configuraciones de ER del repositorio global del servicio de configuración](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

2. En Microsoft Dynamics 365 Finance, defina las siguientes secuencias numéricas como continuas: **Gene\_397**, **Acco\_16403**, **Gene\_407** y **PUR\_UE**.

    1. Vaya a **Administración de la organización** > **Secuencias numéricas** > **Secuencias numéricas**.
    2. En la cuadrícula, seleccione uno de los códigos de secuencia numérica.
    3. En el panel Acciones, seleccione **Editar**.
    4. En la ficha desplegable **General**, en la sección **Configuración**, establezca la opción **Continua** en **Sí**.
    5. En el panel Acciones, seleccione **Guardar**.

3. Configure una dirección de almacén.

    1. Vaya a **Gestión de almacenes** &gt; **Configurar** &gt; **Almacén** &gt; **Almacenes**.
    2. En la lista, seleccione el almacén **11**.
    3. En la ficha desplegable **Dirección**, seleccione **Agregar**.
    4. En el cuadro de diálogo **Dirección** **nueva**, en el campo **Nombre** **o** **descripción**, escriba **Principal**.
    5. En el campo **País/región**, seleccione **ITA (Italia)**.
    6. En el campo **Ciudad** seleccione **Aprilia**.
    7. Seleccione **Aceptar**.

4. Configure los códigos de transacción.

    1. Vaya a **Impuestos** > **Configurar** > **Comercio exterior** > **Códigos de transacción**.
    2. Seleccione **Nuevo** y configure un código de transacción para transferencias de propiedad.

        - En el campo **Código de transacción**, introduzca **1**.
        - En el campo **Nombre**, escriba **Transferencia de propiedad**.

    3. Seleccione **Nuevo** y configure un código de transacción para devoluciones.

        - En el campo **Código de** **transacción**, introduzca **2**.
        - En el campo **Nombre**, introduzca **Devolución de bienes**.

5.  Configure parámetros de comercio exterior.

    1. Vaya a **Impuestos** > **Configuración** > **Comercio exterior** > **Parámetros de comercio exterior**.
    2. En la pestaña **Intrastat**, en la ficha desplegable **General**, en el campo **Código de** **transacción**, seleccione **1**.
    3. En el campo **Nota de crédito**, seleccione **2**.
    4. En el campo **Período de informe de ventas**, seleccione **Mensual**.
    5. En el campo **Período de informe de compras**, seleccione **Mensual**.
    6. En la ficha desplegable **Informes electrónicos**, en el campo **Asignación de formato de archivo**, seleccione **Intrastat (IT)**.
    7. En el campo **Asignación de formato de informe**, seleccione **Informe de Intrastat**.
    8. En la ficha desplegable **Jerarquía de códigos de bienes**, en el campo **Jerarquía de categorías**, seleccione **Intrastat**.
    9. En la ficha desplegable **Valor estadístico**, establezca la opción **Imprimir y exportar datos estadísticos** en **Sí**.
    10. En la pestaña **Propiedades de país/región**, asegúrese de que existan las siguientes líneas.

        | **Parte/país/región** | **Código Intrastat** | **Divisa** | **Tipo de país o región** |
        |--------------------------|--------------------|--------------|-------------------------|
        | ITA                      | IT                 | EUR          | Nacional                |
        | SMR                      | SM                 | EUR          | Nacional especial        |

    11. En la barra de herramientas, seleccione **Nuevo** para crear la línea siguiente.

        | **Parte/país/región** | **Código Intrastat** | **Divisa** | **Tipo de país o región** |
        |--------------------------|--------------------|--------------|-------------------------|
        | DNK                      | DK                 | Coronas danesas          | UE                      |

6. Configure los números de exención fiscal.

    1. Vaya a **Impuestos** > **Configuración** > **Impuestos** > **Números de identificación fiscal**.
    2. En el panel de acciones, seleccione **Nuevo** para crear las líneas siguientes.

        | **País/región** | **Número de identificación fiscal** | **Nombre de la empresa** |
        |--------------------|-----------------------|------------------|
        | DEU                | DE3456789012          | PROVEEDOR DE LA UE        |
        | DNK                | DK0987654321          | ER de cliente      |

7. Establezca la dirección del proveedor.

    1. Vaya a **Proveedores** &gt; **Proveedores** &gt; **Todos los proveedores**.
    2. En la cuadrícula, seleccione **Proveedor de la UE**.
    3. En la ficha desplegable **Direcciones**, seleccione **Agregar**.
    4. En el cuadro de diálogo **Dirección nueva**, en el campo **Nombre o descripción**, introduzca **Alemania**.
    5. En el campo **País/región**, seleccione **DEU**.
    6. Seleccione **Aceptar** para crear la nueva dirección.
    7. En la ficha desplegable **Factura y entrega**, en la sección **Impuesto de ventas**, en el campo **Número de identificación fiscal**, seleccione **Todos** y, a continuación, seleccione **DE1234567890**.
    8. En el panel Acciones, seleccione **Guardar**.

8. Establezca las direcciones de cliente.

    1. Vaya a **Clientes** > **Clientes** > **Todos los clientes**.
    2. En la cuadrícula, seleccione **ITCO-000001**.
    3. En la ficha desplegable **Direcciones**, seleccione **Editar**.
    4. En el cuadro de diálogo **Dirección nueva**, en el campo **Nombre o descripción**, introduzca **San Marino**.
    5. En el campo **País/región**, seleccione **SMR**.
    6. Seleccione **Aceptar** para crear la nueva dirección.
    7. En la ficha desplegable **Factura y entrega**, en la sección **Factura**, en el campo **Cuenta de facturación**, seleccione **ITCO-000001**.
    8. En el campo **Grupo de secuencias numéricas**, seleccione **IT\_VENDOM**.
    9. En el la panel de acciones, seleccione **Guardar** y después cierre la página.
    10. En la página **Todos los clientes**, en la cuadrícula, seleccione **ITCO-000002**.
    11. En la ficha desplegable **Direcciones**, seleccione **Agregar**.
    12. En el cuadro de diálogo **Dirección nueva**, en el campo **Nombre o descripción**, introduzca **Dinamarca**.
    13. En el campo **País/región**, seleccione **DNK**.
    14. Seleccione **Aceptar** para crear la nueva dirección.
    15. En la ficha desplegable **Datos demográficos de ventas**, en el campo **Divisa**, seleccione **DKK**.
    16. En la ficha desplegable **Factura y entrega**, en la sección **Impuesto de ventas**, en el campo **Grupo de impuestos**, seleccione **IT\_PUREU**.
    17. En el campo **Número de identificación fiscal**, seleccione **Todos** y, a continuación, seleccione **DK0987654321**.
    18. En el panel Acciones, seleccione **Guardar**.

9. Configure la jerarquía de categoría.

    1. Vaya a **Gestión de información de productos** > **Configuración** > **Categorías y atributos** > **Jerarquías de categorías**.
    2. En la cuadrícula, seleccione **Intrastat**.
    3. En el panel Acciones, seleccione **Nuevo nodo de categoría**.
    4. En el campo **Nombre**, especifique **Servicio**.
    5. En el campo **Código**, introduzca **123456**.
    6. En el panel Acciones, seleccione **Guardar**.

10. Configurar productos.

    1. Vaya a **Gestión de información de productos** > **Productos** > **Productos emitidos**.
    2. En la cuadrícula, seleccione **ITEM**.
    3. En la ficha desplegable **Compra**, en la sección **Administración**, en el campo **Proveedor**, seleccione **ITCO-000001**.
    4. En la ficha desplegable **Comercio exterior**, en la sección **Intrastat**, en el campo **Mercancía**, seleccione **Orador \[100 200 30\]**.
    5. En la sección **Origen**, en el campo **País o región**, seleccione **DEU**.
    6. En el campo **Estado/provincia**, seleccione **BE**.
    7. En la ficha desplegable **Administrar inventario**, en la sección **Medidas netas**, en el campo **Peso neto**, introduzca **5**.
    8. En el panel Acciones, seleccione **Guardar**.
    9. En la página **Productos emitidos**, en la cuadrícula, seleccione **Elemento de servicio**.
    10. En la ficha desplegable **Comercio exterior**, en la sección **Intrastat**, en el campo **Mercancía**, seleccione **Servicio \[123456\]**.
    11. En el panel Acciones, seleccione **Guardar**.

11. Configure los métodos de transporte.

    1. Vaya a **Impuestos** > **Configurar** > **Comercio exterior** > **Método de transporte**.
    2. En el panel de acciones, seleccione **Nuevo** para crear los siguientes métodos de transporte.

        | **Transporte** | **Descripción** |
        |---------------|-----------------|
        | 1             | Carretera            |
        | 2             | Transporte aéreo             |

12. Configure un modo de entrega.

    1. Vaya a **Adquisiciones y abastecimiento** > **Configuración** > **Distribución** > **Modos de entrega**.
    2. En el panel de acciones, haga clic en **Nueva**.
    3. En el campo **Modo de entrega**, escriba **1**.
    4. En el campo **Descripción**, escriba **Camión**.
    5. En la ficha desplegable **Comercio exterior**, en el campo **Transporte**, seleccione **1 Carretera**.
    6. En el panel Acciones, seleccione **Guardar**.

13. Configure las condiciones de entrega.

    1. Vaya a **Proveedores** > **Configuración** > **Condiciones de entrega**.
    2. En la lista, seleccione **CFR**.
    3. En la ficha desplegable **General**, en el campo **Código intrastat**, escriba **1**.

## <a name="post-arrivals-for-intrastat"></a>Registrar llegadas para Intrastat

### <a name="purchase-goods-by-using-a-purchase-order"></a>Comprar mercancías mediante un pedido de compra

Esta parte del ejemplo muestra cómo utilizar un pedido de compra para comprar mercancías (artículos) de países de la Unión Europea (UE).

1. Vaya a **Proveedores** > **Pedidos de compra** > **Todos los pedidos de compra**.
2.  En el panel de acciones, haga clic en **Nueva**.
3.  En el cuadro de diálogo **Crear pedido de compra**, en el campo **Cuenta de proveedor**, seleccione **Proveedor de la UE**.
4.  En la ficha desplegable **Administración**, en el campo **Idioma**, seleccione **it**.
5.  Seleccione **Aceptar**.
6.  En la vista **Encabezado**, en la ficha desplegable **Comercio** **exterior**, compruebe que el campo **Código de transacción** está configurado en **1**.
7.  Compruebe que el campo **País de origen/destino** está establecido en **RM**.
8.  En la ficha desplegable **Entrega**, en la sección **Entrega**, en el campo **Modo de entrega**, seleccione **1**.
9.  En el campo **Condiciones de entrega**, seleccione **CFR**.
10. En la vista **Líneas**, en la ficha desplegable **Líneas de pedido de compra**, en el campo **Número de artículo**, seleccione **Artículo**.
11. En el campo **Sitio**, seleccione **1**.
12. En el campo **Almacén**, seleccione **11**.
13. En el campo **Cantidad**, especifique **10**.
14. En el campo **Precio unitario**, escriba **100**.
15. En la pestaña **Configuración**, en la sección **Impuestos**, en el campo **Grupo de impuestos de artículos**, seleccione **22%EU**.
16. En el panel de acciones, en la ficha **Compra**, en el grupo **Acciones**, seleccione **Confirmar**.
17. En el panel de acciones, en la ficha **Factura**, en el grupo **Generar**, seleccione **Factura**.
18. En el panel de acciones, seleccione **Valor predeterminado de origen**.
19. En el campo **Cantidad predeterminada para líneas**, seleccione **Cantidad pedida** y, a continuación, seleccione **Aceptar**.
20. En la ficha desplegable **Encabezado de factura de proveedor**, en la sección **Identificación de factura**, en el campo **Número**, escriba **0001**.
21. En la sección **Fechas de factura**, en el campo **Fecha de la factura**, seleccione **9/7/2021**.
22. En el panel de acciones, seleccione **Registrar** para registrar la factura.

### <a name="purchase-services-by-using-a-vendor-invoice"></a>Adquirir servicios mediante una factura de proveedor

Esta parte del ejemplo muestra cómo utilizar una factura de proveedor para comprar servicios de países de la Unión Europea (UE).

1. Vaya a **Proveedores** > **Facturas** > **Diario de facturas**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el campo **Nombre**, seleccione **VEND\_EUINV**.
4. En el panel de acciones, seleccione **Líneas**.
5. En el campo **Fecha**, escriba **9/7/2021**.
6. En el campo **Tipo de cuenta**, seleccione **Proveedor**.
7. En el campo **Cuenta**, seleccione **Proveedor de la UE**.
8. En el campo **Fecha de la factura**, seleccione **9/7/2021**.
9. En el campo **Factura**, introduzca **ITA-0004**.
10. En el campo **Crédito**, especifique **120000**.
11. En el campo **Tipo de** **cuenta de contrapartida**, seleccione **Libro mayor**.
12. En el campo **Tipo de cuenta de contrapartida**, seleccione **110130**.
13. En el campo **Grupo de impuestos**, seleccione **IT\_PUREU**.
14. En el campo **Grupo de impuestos de artículos**, seleccione **22%EU**.
15. En la pestaña **Comercio exterior**, siga estos pasos:

    1. En el campo **Código de transacción**, seleccione **1**.
    2. En el campo **Transporte**, seleccione **2 Aire**.
    3. En el campo **Mercancía**, seleccione **Servicio \[123456\]**.
    4. En el campo **País/región**, seleccione **ITA**.
    5. En el campo **Estado/provincia**, seleccione **LAZ**.
    6. En el campo **País de origen/destino**, seleccione **LT**.


16. En el panel de acciones, seleccione **Registrar**.
17. Cree una declaración de Intrastat para las llegadas.

    1. Vaya a **Impuestos** > **Declaraciones** > **Comercio exterior** > **Intrastat**.
    2. En el panel de acciones, seleccione **Transferir**.
    3. En el cuadro de diálogo **Intrastat (Transferir)**, establezca la opción **Factura de proveedor** en **Sí**.
    4. Seleccione **Aceptar** para transferir las transacciones y, a continuación, revise el diario de intrastat.

   ![Página del diario de Intrastat, pestaña Información general.](media/ita_intrastat_journal_vendor_invoice.png)

18. Revisa el pedido de compra en la pestaña **General**.

    ![Detalles de línea del diario de Intrastat para pedido de compra](media/ita_intrastat_journal_purchase_order_line_details.png)

19. Revisa la factura de proveedor en la pestaña **General**.

    ![Detalles de línea del diario de Intrastat para factura de proveedor](media/ita_intrastat_journal_vendor_invoice_line_details.png)

20. Genere el informe de intrastat para llegadas.

    1. En el panel de acciones, seleccione **Salida** > **Informe**.
    2. En el cuadro de diálogo **Informe de Intrastat**, en la sección **Fecha**, en el campo **Fecha de inicio**, seleccione **7/1/2021**.
    3. En el campo **Fecha final**, seleccione **31/7/2021**.
    4. En la sección **Opciones de exportación**, establezca las opciones **Generar archivo** y **Generar informe** en **Sí**.
    5. En el campo **Nombre de archivo**, introduzca **Archivo de llegadas**.
    6. En el campo **Nombre de archivo del informe**, introduzca **Informe de llegadas**.
    7. En el campo **Dirección**, seleccione **Llegadas**.
    8. En el campo **Número de referencia**, escriba **123456**.
    9. Seleccione **Aceptar** para generar el informe Intrastat y el archivo Intrastat, y revisarlos.

    En la ilustración siguiente se muestra un ejemplo de un informe de intrastat.

    ![Informe de llegadas de intrastat.](media/ita_intrastat_arrivals_report.png)

    En la ilustración siguiente se muestra un ejemplo de un archivo de intrastat.

    ![Archivo de llegadas de intrastat.](media/ita_intrastat_arrivals_file.png)

## <a name="post-dispatches-for-intrastat"></a>Registrar envíos para Intrastat

### <a name="sell-goods-by-using-a-sales-order"></a>Vender mercancías mediante un pedido de ventas

Esta parte del ejemplo muestra cómo utilizar un pedido de ventas para vender mercancías (artículos) a países de la Unión Europea (UE).

1. Vaya a **Clientes** > **Pedidos** > **Todos los pedidos de ventas**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el cuadro de diálogo **Crear pedido de ventas**, en el campo **Cuenta de cliente**, seleccione **ITCO-000002**.
4. Seleccione **Aceptar**.
5. En la vista **Encabezado**, en la ficha desplegable **Entrega**, en la sección **Información de detalles de entrega**, en el campo **Modo de entrega**, seleccione **1 Camión**.
6. En el campo **Condiciones de entrega**, seleccione **CFR**.
7. En la vista **Líneas**, en la ficha desplegable **Líneas de pedido de ventas**, en el campo **Número de artículo**, seleccione **ITEM**.
8. En el campo **Cantidad**, especifique **50**.
9. En el campo **Sitio**, seleccione **1**.
10. En el campo **Almacén**, seleccione **11**.
11. En el campo **Precio unitario**, escriba **250**.
12. En la ficha desplegable **Detalles de línea**, en la pestaña **Configuración**, en la sección **Impuestos**, en el campo **Grupo de impuestos de artículos**, seleccione **22%EU**.
13. En el panel Acciones, seleccione **Guardar**.
14. En el panel de acciones, en la pestaña **Factura**, en el grupo **Generar**, seleccione **Factura** para crear la factura del pedido.
15. En el cuadro de diálogo **Registro de factura**, en la ficha desplegable **Parámetros**, en la sección **Parámetro**, en el campo **Cantidad**, seleccione **Todos**.
16. En la ficha desplegable **Configuración**, en el campo **Fecha de la** **factura**, seleccione **9/7/2021**.
17. Seleccione **Aceptar**.
18. Revisar las líneas de diario en el diario de intrastat.

    1. Vaya a **Impuestos** > **Declaraciones** > **Comercio exterior** > **Intrastat**.
    2. En el panel de acciones, seleccione **Transferir**.
    3. En el cuadro de diálogo **Intrastat (Transferir)**, establezca la opción **Factura de cliente** en **Sí**.
    4. Seleccione **Aceptar** para transferir las transacciones y, a continuación, revise el diario de intrastat. La transacción de la nota de crédito está marcada como una corrección y tiene un importe de factura negativo.

        ![Página del diario de intrastat](media/ita_intrastat_journal_sales_order.png)

        ![Detalles de línea del diario de intrastat para pedido de ventas](media/ita_intrastat_journal_sales_order_line_details.png)

### <a name="return-goods-by-using-a-credit-note"></a>Devolver productos mediante una nota de crédito

Esta parte del ejemplo muestra cómo utilizar una nota de crédito para devolver mercancías (artículos) de países de la Unión Europea (UE).

1. Vaya a **Clientes** > **Pedidos** > **Todos los pedidos de ventas**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el cuadro de diálogo **Crear pedido de ventas**, en el campo **Cuenta de cliente**, seleccione **ITCO-000002**.
4. Seleccione **Aceptar**.
5. En la vista **Encabezado**, en la ficha desplegable **Entrega**, en la sección **Información de detalles de entrega**, en el campo **Modo de entrega**, seleccione **1 Camión**.
6. En el campo **Condiciones de entrega**, seleccione **CFR**.
7. En la ficha desplegable **Comercio exterior**, en el campo **Código de transacción**, seleccione **2**.
8. En la pestaña **Líneas**, en la ficha desplegable **Líneas de pedido de ventas**, en el campo **Número de artículo**, seleccione **ITEM**.
9. En el campo **Cantidad**, especifique **-10**.
10. En el campo **Sitio**, seleccione **1**.
11. En el campo **Almacén**, seleccione **11**.
12. En el campo **Precio unitario**, escriba **250**.
13. En la ficha desplegable **Detalles de línea**, en la pestaña **Configuración**, en la sección **Impuestos**, en el campo **Grupo de impuestos de artículos**, seleccione **22%EU**.
14. En la sección **Pedido devuelto**, en el campo **Id. de devolución de lote**, seleccione el lote que creó anteriormente.
15. En el panel Acciones, seleccione **Guardar**.
16. En el panel de acciones, en la pestaña **Factura**, en el grupo **Generar**, seleccione **Factura** para crear la factura del pedido.
17. En la ficha desplegable **Parámetros**, en la sección **Parámetro**, en el campo **Cantidad**, seleccione **Todo**.
18. En el cuadro de diálogo **Registro de factura**, en la ficha desplegable **Configuración**, en el campo **Fecha de la** **factura**, seleccione **9/7/2021**.
19. Seleccione **Aceptar** para registrar la factura.
20. Revisar las líneas de diario en el diario de intrastat.

    1. Vaya a **Impuestos** > **Declaraciones** > **Comercio exterior** > **Intrastat**.
    2. En el panel de acciones, seleccione **Transferir**.
    3. En el cuadro de diálogo **Intrastat (Transferir)**, establezca la opción **Factura de cliente** en **Sí**.
    4. Seleccione **Aceptar** para transferir las transacciones y, a continuación, revise el diario de intrastat. La transacción de la nota de crédito está marcada como una corrección y tiene un importe de factura negativo.

    ![Nota de crédito del diario de intrastat](media/ita_intrastat_journal_credit_note.png)

    ![Detalles de línea del diario de intrastat para nota de crédito](media/ita_intrastat_journal_credit_note_line_details.png)

### <a name="sell-goods-to-san-marino-by-using-a-sales-order"></a>Vender mercancías a San Marino mediante un pedido de ventas

Esta parte del ejemplo muestra cómo utilizar un pedido de ventas para comprar mercancías (artículos) a San Marino.

1. Vaya a **Clientes** > **Pedidos** > **Todos los pedidos de ventas**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el cuadro de diálogo **Crear pedido de ventas**, en el campo **Cuenta de cliente**, seleccione **ITCO-000001**.
4. Seleccione **Aceptar**.
5. En la vista **Encabezado**, en la ficha desplegable **Entrega**, en la sección **Información de detalles de entrega**, en el campo **Modo de entrega**, seleccione **1**.
6. En el campo **Condiciones de entrega**, seleccione **CFR**.
7. En la pestaña **Líneas**, en la ficha desplegable **Líneas de pedido de ventas**, en el campo **Número de artículo**, seleccione **ITEM**.
8. En el campo **Cantidad**, especifique **30**.
9. En el campo **Sitio**, seleccione **1**.
10. En el campo **Almacén**, seleccione **11**.
11. En el campo **Precio unitario**, escriba **200**.
12. En el panel Acciones, seleccione **Guardar**.
13. En el panel de acciones, en la pestaña **Factura**, en el grupo **Generar**, seleccione **Factura** para crear la factura del pedido.
14. En la ficha desplegable **Parámetros**, en la sección **Parámetro**, en el campo **Cantidad**, seleccione **Todo**.
15. En el cuadro de diálogo **Registro de factura**, en la ficha desplegable **Configuración**, en el campo **Fecha de la** **factura**, seleccione **9/7/2021**.
16. Seleccione **Aceptar** para registrar la factura.
17. Revisar las líneas de diario en el diario de intrastat.

    1. Vaya a **Impuestos** > **Declaraciones** > **Comercio exterior** > **Intrastat**.
    2. En el panel de acciones, seleccione **Transferir**.
    3. En el cuadro de diálogo **Intrastat (Transferir)**, establezca la opción **Factura de cliente** en **Sí**.
    4. Seleccione **Aceptar** para transferir las transacciones y, a continuación, revise el diario de intrastat.

   ![Diario de intrastat para San Marino](media/ita_intrastat_journal_sales_order_san_marino.png)

   ![Detalles de línea del diario de intrastat para San Marino](media/ita_intrastat_journal_sales_order_san_marino_line_details.png)

18. Cree una declaración de intrastat para envíos.

    1. Vaya a **Impuestos** &gt; **Declaraciones** &gt; **Comercio exterior** &gt; **Intrastat**.
    2. En el panel de acciones, seleccione **Salida** &gt; **Informe**.
    3. En el cuadro de diálogo **Informe de Intrastat**, en la sección **Fecha**, en el campo **Fecha de inicio**, seleccione **7/1/2021**.
    4. En el campo **Fecha final**, seleccione **31/7/2021**.
    5. En la sección **Opciones de exportación**, establezca las opciones **Generar archivo** y **Generar informe** en **Sí**.
    6. En el campo **Nombre de archivo**, introduzca **Archivo de envíos**.
    7. En el campo **Nombre de archivo del informe**, introduzca **Informe de envíos**.
    8. En el campo **Dirección**, seleccione **Envíos**.
    9. En el campo **Número de referencia**, escriba **98754**.
    10. Seleccione **Aceptar** para generar el informe de intrastat y el archivo de intrastat, y revisarlos.

        En la ilustración siguiente se muestra un ejemplo de un informe de intrastat impreso.

        ![Informe intrastat](media/ita_intrastat_report_for_dispatches.png)

        En la ilustración siguiente se muestra un ejemplo de un archivo de intrastat impreso.

        ![Archivo de intrastat para envíos](media/ita_intrastat_file_for_dispatches.png)
