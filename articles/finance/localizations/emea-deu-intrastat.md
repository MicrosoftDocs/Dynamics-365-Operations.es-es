---
title: Intrastat alemán
description: Este artículo contiene información sobre la declaración Intrastat en Alemania.
author: anasyash
ms.date: 09/09/2021
ms.topic: article
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: ''
ms.openlocfilehash: 9516a4516488282820659da141fe3ad33fbe3a9d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848475"
---
# <a name="german-intrastat"></a>Intrastat alemán

[!include [banner](../includes/banner.md)]

La página **Intrastat** se usa para generar y presentar información sobre el comercio entre los países de la Unión Europea (UE). La declaración Intrastat alemana contiene información sobre el comercio de mercancías para informar. El informe tiene el formato de las directrices de las autoridades alemanas que se presentan en la página [6.2 Declaraciones de archivos en formato INSTAT/XML](https://www-idev.destatis.de/idev/doc/intra_en/hilfe6_2.html).

La siguiente tabla muestra los campos que se incluyen en la declaración Intrastat alemana.

| Campos | Distribuciones | Llegadas |
|-------------------------|-------------------------|-------------------------|
| Periodo de referencia | X | X |
| Código de dirección | X | X |
| Moneda de la declaración Intrastat</br>**Nota:** Esta divisa es la <em>divisa de contabilidad</em>. | X | X |
| Código de mercancía | X | X |
| Nombre de la mercancía | X | X |
| Código de unidad suplementario | X | X |
| Estado miembro de envío/destino | X | X |
| Masa neta | X | X |
| Cantidad en unidades suplementarias | X | X |
| País de origen |  | X |
| Importe de la factura | X |  |
| Valor estadístico | X | X |
| Naturaleza de las transacciones | X | X |
| Modo de transporte | X | X |
| Código de región</br>**Nota:**</br><ul></br><li>Si el país o región de origen es Alemania y la factura es por envíos, se muestra un código Intrastat para el estado de origen.</li></br><li>Si el país o región de origen no es Alemania y la factura es por envíos, se muestra el código **99**.</li></br><li>Si la factura es por llegadas, se muestra un código Intrastat para el estado.</li></br></ul> | X | X |
| Código de puerto/aeropuerto/puerto interior | X | X |
| Condiciones de entrega | X | X |


## <a name="set-up-intrastat"></a>Configurar Intrastat

1. Configurar los códigos de la empresa.

    1. Vaya a **Administración de la organización** > **Organizaciones** > **Entidades jurídicas**.
    2. En la ficha desplegable **Comercio exterior y logística**, en la sección **Identificación**, en el campo **DVR**, introduzca el ID del acuerdo de intercambio. Este ID se incluirá en el informe.
    3. En el campo **Exportación de número de exención de IVA**, introduzca el número de impuesto sobre el valor agregado (IVA) de su empresa para la exportación.
    4. En el campo **Importación de número de exención de IVA**, introduzca el número de IVA de su empresa para la importación.
    5. En el campo **Código de Intrastat**, introduzca el código de Intrastat que está asignado a la entidad jurídica.
    6. En la ficha desplegable **Registrar impuestos**, en el campo **Número de registro de impuestos**, introduzca el número de registro de impuestos de su empresa.

    > [!NOTE]
    > Si genera un informe de Intrastat para afiliados, en el campo **Número de registro de impuestos**, introduzca el número de registro fiscal de su empresa matriz.

2. En [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index), en la biblioteca Activos compartidos, descargue las últimas versiones de las configuraciones de informes electrónicos (ER) para la declaración de Intrastat.

    - Modelo intrastat
    - Informe intrastat
    - INSTAT XML
    - INSTAT XML (DE)

3. Configurar parámetros de comercio exterior:

    1. En Dynamics 365 Finance, vaya a **Impuestos** > **Configuración** > **Parámetros de comercio exterior**.
    2. En la pestaña **Intrastat**, en la ficha desplegable **Informes electrónicos**, en el campo **Asignación de formato de archivo**, seleccione **Intrastat XML (DE)**.
    3. En el campo **Asignación de formato de informe**, seleccione **Informe Intrastat**.
    4. En la ficha desplegable **Jerarquía de códigos de bienes**, en el campo **Jerarquía de categorías**, seleccione **Intrastat**.
    5. En el campo **Codigo de transacción**, seleccione el código de transacción para transferencias de propiedad. Use este código para transacciones que provoquen transferencisa de propiedad reales o planificadas contra compensación (financieras o de otro tipo). Úselo también para correcciones.
    6. En el campo **Nota de abono**, seleccione el código de transacción para la devolución de mercancías.
    7. En el campo **Trabajador**, seleccione la persona de contacto para el informe Intrastat. Alternativamente, en la pestaña **Contacto**, introduzca o seleccione valores en los campos **Nombre**, **Teléfono**, **Fax**, **Correo electrónico** y **Dirección de Internet**. Estos campos se incluyen en el informe.
    8. En el campo **Autoridad**, seleccione la autoridad de Intrastat.
    9. Vaya a **Impuestos** > **Impuestos indirectoss** > **Impuesto de ventas** > **Autoridades de impuestos de ventas** e introduzca la siguiente información para la autoridad de Intrastat que seleccionó en el paso anterior:

       - Identificación de la autoridad
       - Dirección
       - Información de contacto

    10. En la pestaña **Propiedades de país o región**, en el campo **País o región**, enumere todos los países o regiones con los que su organización hace negocios. Para cada país o región, en el campo **Tipo de país o región**, seleccione **UE**, para que el país o región aparezcan en su informe de Intrastat.

4. Configurar códigos de región.

    1. Vaya a **Administración de la organización** > **Libreta de direcciones global** > **Direcciones** > **Configuración de direcciones**.
    2. En la pestaña **Provincia o estado**, en el campo **País o región**, seleccione **DEU** y luego seleccione **Aplicar filtro**.
    3. En la cuadrícula, seleccione el estado. Después, en el campo **Código de Intrastat**, especifique el código de Intrastat único.

5. Configure la dirección de origen de un producto.

    1. Vaya a **Gestión de información de productos** > **Productos** > **Productos publicados**.
    2. En la cuadrícula, seleccione el producto.
    3. En la ficha desplegable **Comercio exterior**, en la sección **Intrastat**, en el campo **País de origen**, seleccione **DEU**.

6. Vaya a **Impuestos** > **Configuración** > **Comercio Exterior** > **Compresión de Intrastat** y seleccione los campos que se deben comparar cuando se resume la información de Intrastat. Para el Intrastat alemán, seleccione los siguientes campos:

    - Código Intrastat de la mercancía
    - País/región
    - Corrección
    - Dirección
    - Condiciones de entrega
    - Factura
    - País/región de origen
    - Puerto
    - País/región de remitente
    - Estado del remitente
    - Procedimiento estadístico
    - Código de transacción
    - Transporte
    - Número de identificación fiscal

### <a name="intrastat-transfer"></a>Transferencia intrastat

En la página **Intrastat**, en el panel de acciones, puede seleccionar **Transferir** para transferir automáticamente la información sobre el comercio intracomunitario de sus órdenes de venta, facturas de servicios, órdenes de compra, facturas de proveedores, recibos de productos de proveedores **,** facturas de proyectos y órdenes de transferencia. Solo se transferirán los documentos que tengan un país de la UE como país o región de destino (para envíos) o consignación (para llegadas).

Alternativamente, puede introducir transacciones manualmente seleccionando **Nuevo** en el Panel de acciones.

### <a name="generate-an-intrastat-report"></a>Genere un informe Intrastat

1. Vaya a **Impuestos** > **Declaraciones** > **Comercio exterior** > **Intrastat**.
2. En el panel de acciones, seleccione **Salida** > **Informe**.
3. En el cuadro de diálogo **Informe Intrastat**, establezca los campos siguientes.

    | Campo | Descripción |
    |-------------------------|-------------------------|
    | Fecha de inicio | Seleccione la fecha inicial del informe. |
    | Fecha de finalización | Seleccione la fecha final del informe. |
    | Generar archivo | Establezca esta opción en **Sí** para generar un archivo .xml. |
    | Nombre de archivo | Deje este campo en blanco. El nombre del archivo se genera automáticamente y consta del valor de la etiqueta XML **&lt;sobreId&gt;** y la extensión del nombre del archivo **.xml**.</br>El valor **&lt;envelopeId&gt;** es una concatenación de los siguientes elementos, en este orden:</br><ol type="1"></br><li>El valor de la etiqueta **&lt;interchangeAgreementId&gt;**</li></br><li>Un guion (-)</li></br><li>El valor de la etiqueta **&lt;referencePeriod en AAAAMM&gt;**</li></br><li>Un guion (-)</li></br><li>El valor de la etiqueta **&lt;Sobre/DateTime/fecha en AAAAMMDD&gt;**</li></br><li>Un guion (-)</li></br><li>El valor de la etiqueta **&lt;Sobre/DateTime/hora en hhmm&gt;**</li></br></ol> |
    | Dirección | <ul></br><li>Seleccione **Llegadas** para informar sobre llegadas intracomunitarias.</li></br><li>Seleccione **Envíos** para informar sobre los envíos intracomunitarios.</li></br><li>Seleccione **Ambos** para informar sobre las llegadas y los envíos.</li></br></ul> |
    | NIF - CIF | Introduzca el número de registro que se utilizará para generar el código de identificación del remitente, si el número difiere del número de registro fiscal de la entidad jurídica. |


## <a name="example"></a>Ejemplo

Este ejemplo muestra cómo publicar llegadas y envíos para Intrastat. Usa la entidad jurídica **DEMF**.

1. En [LCS](https://lcs.dynamics.com/Logon/Index), en la Biblioteca de activos compartidos, descargue las últimas versiones de las configuraciones de ER para el siguiente formato de declaración de Intrastat:

    - Modelo intrastat
    - Informe intrastat
    - Intrastat XML
    - Intrastat XML (DE)

2. Cree códigos de transacción.

    1. Vaya a **Impuestos** > **Configurar** > **Comercio exterior** > **Códigos de transacción**.
    2. En el panel de acciones, haga clic en **Nueva**.
    3. En el campo **Código de** **transacción**, introduzca **21**.
    4. En el campo **Nombre**, introduzca **Devolución de bienes**.
    5. En el panel Acciones, seleccione **Guardar**.

3. Configure el número de identificación de la autoridad.

    1. Vaya a **Impuestos** > **Impuestos indirectos** > **Impuestos** > **Autoridades fiscales**.
    2. En la lista, seleccione **TA**.
    3. En el campo **Identificación de la autoridad**, introduzca **123**.

4. Configurar códigos de región.

    1. Vaya a **Administración de la organización** > **Libreta de direcciones global** > **Direcciones** > **Configuración de direcciones**.
    2. En la pestaña **Provincia o estado**, en el campo **País o región**, seleccione **DEU** y luego seleccione **Aplicar filtro**.
    3. En la cuadrícula, seleccione **BE** y luego, en el campo **Código de Intrastat**, introduzca **11**.
    4. En el panel Acciones, seleccione **Guardar**.

5. Configure parámetros de comercio exterior.

    1. Vaya a **Impuestos** > **Configuración** > **Comercio exterior** > **Parámetros de comercio exterior**.
    2. En la pestaña **Intrastat**, en la ficha desplegable **General**, en el campo **Código de** **transacción**, seleccione **11**.
    3. En el campo **Nota de crédito**, seleccione **21**.
    4. En el campo **Autoridad**, seleccione **TA**.
    5. En la ficha desplegable **Informes electrónicos**, en el campo **Asignación de formato de archivo**, seleccione **INSTAT XML (DE)**.
    6. En el campo **Asignación de formato de informe**, seleccione **Informe Intrastat**.
    7. En la ficha desplegable **Jerarquía de códigos de mercancías**, en el campo **Jerarquía de categorías**, asegúrese de que **Intrastat** está seleccionado.
    8. En la pestaña **Propiedades de país o región**, seleccione **Nueva**.
    9. En el campo **País o región de la parte**, seleccione **FRA**.
    10. En el campo **Tipo de país/región**, seleccione **EU**.

6. Asigne un código de mercancía a un producto y establezca el origen del producto. Los campos **Código de mercancía**, **País o región de origen** y **Estado de origen** se establecerán automáticamente en pedidos de venta y pedidos de compra cuando seleccione el producto.

    1. Vaya a **Gestión de información de productos** > **Productos** > **Productos publicados**.
    2. En la cuadrícula, seleccione **D0001**.
    3. En la ficha desplegable **Comercio exterior**, en la sección **Intrastat**, en el campo **Mercancía**, seleccione **920 20 34**.
    4. En la sección **Origen**, en el campo **País o región**, seleccione **DEU**.
    5. En la ficha desplegable **Administrar inventario**, en la sección **Medidas de peso**, en el campo **Peso neto**, introduzca **12**.
    6. En el panel Acciones, seleccione **Guardar**.

7. Asigne transporte a un modo de entrega. El código de transporte se establecerá automáticamente en los pedidos cuando seleccione el modo de entrega.

    1. Vaya a **Adquisiciones y abastecimiento** > **Configuración** > **Distribución** > **Modos de entrega**.
    2. En la lista, seleccione **10**.
    3. En la ficha desplegable **Comercio exterior**, en el campo **Transporte**, seleccione **01**.

8. Cree un pedido de ventas con un cliente de la UE.

    1. Vaya a **Clientes** > **Pedidos** > **Todos los pedidos de ventas**.
    2. En el panel de acciones, haga clic en **Nueva**.
    3. En el cuadro de diálogo **Crear pedido de ventas**, en la ficha desplegable **Cliente**, en la sección **Cliente**, en el campo **Cuenta de cliente**, seleccione **DE-012**.
    4. En la ficha desplegable **General**, en la sección **Dimensiones de almacenamiento**, en el campo **Sitio**, seleccione **1**.
    5. En el campo **Almacén**, seleccione **11**.
    6. Seleccione **Aceptar**.
    7. En la pestaña **Encabezado**, en la ficha desplegable **Comercio exterior**, en el campo **Puerto**, seleccione **53**.
    8. En el campo **Procedimiento estadístico**, seleccione **31710**.
    9.  En la pestaña **Líneas**, en la ficha desplegable **Líneas** **de pedido de ventas**, en el campo **Número de artículo**, seleccione **D0001**. En el campo **Cantidad**, especifique **10**.
    10. En la ficha desplegable **Detalles de la línea**, en la pestaña **Comercio exterior**, asegúrese de que los campos **Código de transacción**, **Transporte**, **Mercancía** y **País o región de origen** se establecen automáticamente.
    11. En el panel Acciones, seleccione **Guardar**.
    12. En el panel de acciones, en la pestaña **Factura**, en la sección **Generar**, seleccione **Factura**.
    13. En el cuadro de diálogo **Registro de factura**, en la ficha desplegable **Parámetros**, en la sección **Parámetro**, en el campo **Cantidad**, seleccione **Todos**.
    14. Seleccione **Aceptar** para registrar la factua.

9.  Transfiera la transacción al diario de Intrastat y revise el resultado.

    1. Vaya a **Impuestos** > **Declaraciones** > **Comercio exterior** > **Intrastat**.
    2. En el panel de acciones, seleccione **Transferir**.
    3. En el cuadro de diálogo **Intrastat (transferencia)**, en la sección **Parámetros**, configure la opción **Factura del cliente** a **Sí**.
    4. Seleccione **Filtro**.
    5. En el cuadro de diálogo **Filtro de Intrastat**, en la pestaña **Rango**, seleccione la primera línea y asegúrese de que el campo **Campo** esté establecido en **Fecha**.
    6. En el campo **Criterio**, seleccione la fecha actual.
    7. Seleccione **Aceptar** para cerrar el cuadro de diálogo **Filtro de Intrastat**.
    8. Seleccione **Aceptar** para cerrar el cuadro de diálogo **Intrastat (Transferir)** y revise el resultado. La línea representa el pedido de ventas que creó antes.

        ![Línea que representa el pedido de ventas en la página de Intrastat](media/intrastat_deu_1.png)

10. Seleccione la línea de transacción y luego seleccione la pestaña **General** para ver más detalles.

    ![Detalles del pedido de ventas en la pestaña General de la página de Intrastat](media/intrastat_deu_2.png)

11. Cree una nota de crédito usando un pedido de ventas.

    1. Vaya a **Clientes** > **Pedidos** > **Todos los pedidos de ventas**.
    2. En el panel de acciones, haga clic en **Nueva**.
    3. En el cuadro de diálogo **Crear pedido de ventas**, en la ficha desplegable **Cliente**, en la sección **Cliente**, en el campo **Cuenta de cliente**, seleccione **DE-012**.
    4. En la ficha desplegable **General**, en la sección **Dimensiones de almacenamiento**, en el campo **Sitio**, seleccione **1**.
    5. En el campo **Almacén**, seleccione **11**.
    6. En la pestaña **Encabezado**, en la ficha desplegable **Comercio exterior**, en el campo **Puerto**, seleccione **53**.
    7. En el campo **Procedimiento estadístico**, seleccione **31710**.
    8. En la pestaña **Líneas**, en la ficha desplegable **Líneas** **de pedido de ventas**, en el campo **Número de artículo**, seleccione **D0001**. En el campo **Cantidad**, especifique **-2**.
    9. En la ficha desplegable **Detalles de la línea**, en la pestaña **Comercio exterior**, en el campo **Código de transacción**, seleccione **21**.
    10. Asegúrese de que los campos **Transporte**, **Mercancía** y **País o región de origen** se establecen automáticamente.
    11. En el panel Acciones, seleccione **Guardar**.
    12. En el panel de acciones, en la pestaña **Factura**, en la sección **Generar**, seleccione **Factura**.
    13. En el cuadro de diálogo **Registro de factura**, en la ficha desplegable **Parámetros**, en la sección **Parámetro**, en el campo **Cantidad**, seleccione **Todos**.
    14. Seleccione **Aceptar** para registrar la factua.

12. Transfiera la transacción al diario de Intrastat y revise el resultado.

    1. Vaya a **Impuestos** > **Declaraciones** > **Comercio exterior** > **Intrastat**.
    2. En el panel de acciones, seleccione **Transferir**.
    3. En el cuadro de diálogo **Intrastat (transferencia)**, en la sección **Parámetros**, configure la opción **Factura del cliente** a **Sí**.
    4. Seleccione **Aceptar** para cerrar el cuadro de diálogo **Intrastat (Transferir)** y revisar el resultado. Una nueva línea donde el campo **Dirección** está establecido en **Llegadas** ha sido añadido.            
        Esta línea representa la devolución física de bienes.

        ![Línea para la devolución física de mercancías en la página de Intrastat](media/intrastat_deu_3.png)

13. Seleccione la línea de transacción y luego seleccione la pestaña **General** para ver más detalles.

    ![Detalles de la devolución física de mercancías en la pestaña General de la página de Intrastat](media/intrastat_deu_4.png)

14. Cree una corrección usando un pedido de ventas:

    1. Vaya a **Clientes** > **Pedidos** > **Todos los pedidos de ventas**.
    2. En el panel de acciones, haga clic en **Nueva**.
    3. En el cuadro de diálogo **Crear pedido de ventas**, en la ficha desplegable **Cliente**, en la sección **Cliente**, en el campo **Cuenta de cliente**, seleccione **DE-012**.
    4. En la ficha desplegable **General**, en la sección **Dimensiones de almacenamiento**, en el campo **Sitio**, seleccione **1**.
    5. En el campo **Almacén**, seleccione **11**.
    6. En la pestaña **Encabezado**, en la ficha desplegable **Comercio exterior**, en el campo **Puerto**, seleccione **53**.
    7. En el campo **Procedimiento estadístico**, seleccione **31710**.
    8. En la pestaña **Líneas**, en la ficha desplegable **Líneas** **de pedido de ventas**, en el campo **Número de artículo**, seleccione **D0001**. En el campo **Cantidad**, especifique **-3**.
    9. En la ficha desplegable **Detalles de la línea**, en la pestaña **Comercio exterior**, en el campo **Código de transacción**, seleccione **11**.
    10. Asegúrese de que los campos **Transporte**, **Mercancía** y **País o región de origen** se establecen automáticamente.
    11. En el panel Acciones, seleccione **Guardar**.
    12. Asegúrese de que el campo **Código de transacción** esté establecido en 11.
    13. En el panel de acciones, en la ficha **Factura**, en la sección **Generar**, seleccione **Factura**.
    14. En el cuadro de diálogo **Registro de factura**, en la ficha desplegable **Parámetros**, en la sección **Parámetro**, en el campo **Cantidad**, seleccione **Todos**.
    15. Seleccione **Aceptar** para registrar la factua.

15. Transfiera la transacción al diario de Intrastat y revise el resultado:

    1. Vaya a **Impuestos** > **Declaraciones** > **Comercio exterior** > **Intrastat**.
    2. En el panel de acciones, seleccione **Transferir**.
    3. En el cuadro de diálogo **Intrastat (transferencia)**, en la sección **Parámetros**, configure la opción **Factura del cliente** a **Sí**.
    4. Seleccione **Aceptar** para cerrar el cuadro de diálogo **Intrastat (Transferir)** y revisar el resultado. Una nueva línea donde aparece una marca de verificación en la columna **Corrección** se ha agregado.

        ![Línea para la corrección en la página de Intrastat](media/intrastat_deu_5.png)

16. Seleccione la línea de transacción y luego seleccione la pestaña **General** para ver más detalles.

    ![Detalles de la correción en la pestaña General de la página de Intrastat](media/intrastat_deu_6.png)

17. En el panel de acciones, seleccione **Salida** > **Informe**.
18. En el cuadro de diálogo **Informe Intrastat**, en la ficha desplegable **Parámetros**, en la sección **Fecha**, seleccione el mes del pedido de ventas que creó.
19. En la sección **Exportar** **opciones**, establezca la opción **Generar archivo** en **Sí**.
20. En el campo **Nombre del archivo**, especifique el nombre requerido.
21. Seleccione **Aceptar** y revise el informe que se genera. En la tabla siguiente se muestran los valores en el informe de ejemplo.

    | **Nombre**                  | **Factura de ventas**  |   **Corrección**   | **Factura rectificativa** |
    |---------------------------|--------------------|--------------------|-----------------|
    | declarationId             | 2021-07-D          | 2021-07-A          |                 |
    | referencePeriod           | 2021-07            | 2021-07            |                 |
    | PSIId                     | 11203/118/12345000 | 11203/118/12345000 |                 |
    | functionCode              | O                  | O                  |                 |
    | flowCode                  | B                  | C                  |                 |
    | CurrencyCode              | EUR                | EUR                |                 |
    | itemNumber                | 0000362            | 0000362            | 0000361         |
    | CN8Code                   | 9202034            | 9202034            | 9202034         |
    | goodsDescription          | Orador            | Orador            | Orador         |
    | MSConsDestCode            | FR                 | FR                 | FR              |
    | countryOfOriginCode       | \-                 | \-                 | DE              |
    | netMass                   | 120                | -36                | 24              |
    | invoicedAmount            | 3290               | -987               | \-              |
    | StatisticalValue          | 3290               | -987               | 658             |
    | natureOfTransactionACode  | 1                  | 1                  | 2               |
    | natureOfTransactionBCode  | 1                  | 1                  | 1               |
    | modeOfTransportCode       | 01                 | 01                 | 01              |
    | regionCode                | 11                 | 11                 | 11              |
    | portAirportInlandportCode | 53                 | 53                 | 53              |

