---
title: Información general de intrastat
description: Este artículo proporciona información acerca de los informes de Intrastat para comercio de bienes y, en algunos casos, servicios entre países y regiones de la Unión Europea (UE).
author: EvgenyPopovMBS
ms.date: 01/13/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: Intrastat
audience: Application User
ms.reviewer: kfend
ms.custom:
- "28581"
- intro-internal
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 9360f97506ac7bdf67bb2f1b296f01b6ed49b39f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894785"
---
# <a name="intrastat-overview"></a>Información general de intrastat

[!include [banner](../includes/banner.md)]

Este artículo proporciona información acerca de los informes de Intrastat para comercio de bienes y, en algunos casos, servicios entre países y regiones de la Unión Europea (UE). Este artículo también proporciona una visión general del proceso de informes y describe la configuración y los requisitos previos necesarios.

Intrastat es el sistema de recopilación de información y generación de estadísticas sobre comercio de bienes entre países y regiones de la Unión Europea (UE). Siempre que un producto cruce la frontera de otro país o región de la UE. hace falta presentar un informe Intrastat. En varios países y regiones, los informes Intrastat también son obligatorios para los servicios. Los informes Intrastat pueden incluir elementos necesarios y opcionales. Los elementos siguientes son obligatorios: el número de IVA de la parte responsable de proporcionar información, el período de referencia, el flujo (recepción o distribución), el código de mercancía de ocho dígitos, el estado miembro socio (estado miembro de envío en recepción y el estado miembro de destino en distribución), el valor de las mercancías, la cantidad de las mercancías (masa neta y unidad suplementaria) y la naturaleza de la transacción. Los países y regiones también pueden recopilar elementos opcionales bajo distintas condiciones. Algunos elementos opcionales son el país o la región de origen, las condiciones de entrega, el modo de transporte, un código de mercancía más detallado que el CN8, la región de origen en distribución y la región de destino en llegadas, el procedimiento estadístico, el valor estadístico, una descripción de las mercancías y el puerto o el aeropuerto de carga y descarga.

## <a name="overview-of-the-intrastat-reporting-process"></a>Visión general del proceso de informes Intrastat
En las secciones siguientes se describe el flujo de información general en los informes Intrastat.

### <a name="enter-a-transaction-that-crosses-the-border-of-another-eu-countryregion"></a>Especificación de transacción transfronteriza a otro país o región de la UE

Una factura de cliente, una factura de texto libre, una factura de compra, una factura de proyecto, un albarán del cliente, una recepción de producto del proveedor o un pedido de transferencia se transfiere al diario de Intrastat si el tipo de país o región de destino (en distribuciones) o de envío (en llegadas) es **UE**. Esta función se ha ampliado para Microsoft Dynamics 365 for Operations (1611) y permite especificar una dirección de embarque para una transacción de comercio intracomunitario. Si una dirección de embarque difiere de una dirección empresarial del proveedor (o la dirección empresarial del cliente para el pedido de devolución), los informes Intrastat operarán con esta información. Al crear un pedido de ventas, una factura de servicios, un pedido de compra, una factura de proveedor, una factura de proyecto o un pedido de transferencia, algunos campos relacionados con comercio exterior tienen valores predeterminados en el encabezado del documento o en la línea. El código de transacción predeterminado se toma del campo correspondiente en la página **Parámetros de comercio exterior**. El código de mercancía predeterminado, el país o la región de origen y el estado o la provincia se toman del artículo. Puede cambiar los valores predeterminados y también puede completar otra información de comercio exterior: las estadísticas procedimiento, método de transporte y puerto.

### <a name="use-the-intrastat-journal-to-generate-information-about-trade-among-eu-countriesregions"></a>Utilice el diario de Intrastat para generar información sobre el comercio entre los países y regiones de la UE.

Para fines estadísticos, se genera información sobre el comercio entre países y regiones de la UE cada mes. Puede transferir transacciones desde una factura de texto libre, una factura de cliente, un albarán de cliente, una factura de proveedor, un albarán de proveedor, una factura de proyecto o un pedido de transferencia, según los criterios de transferencia que se hayan configurado en la página **Parámetros de comercio exterior**. También puede especificar transacciones manualmente. Puede actualizar manualmente las transacciones transferidas en el diario de Intrastat, si se requieren actualizaciones. En determinadas condiciones configuradas en la página **Compresión de Intrastat**, puede comprimir las transacciones en el diario de Intrastat. Algunos países y regiones le permiten aplicar un pequeño umbral de transacción. A continuación puede informar de transacciones por debajo de dicho umbral bajo el código de mercancía especificado. Puede actualizar el código de mercancía en las correspondientes líneas del diario de Intrastat, en el ajuste **Límite mínimo** de la página **Parámetros de comercio exterior**. También puede comprimir esas transacciones, según el ajuste **Compresión de Intrastat**. Puede validar la finalización de las transacciones en el diario de Intrastat, según el ajuste **Comprobar configuración** en la página **Parámetros de comercio exterior**. Se puede validar la cumplimentación de los datos en los campos correspondientes: país o región, estado o provincia, peso, código de mercancía, código de transacción, unidad adicional, puerto, origen, términos de entrega, método de transporte y número de identificación fiscal (NIF). Las transacciones que no se hayan completado se marcarán como no válidas.

### <a name="use-the-intrastat-journal-to-report-information-about-trade-among-eu-countriesregions"></a>Utilice el diario de Intrastat para informar sobre el comercio entre los países y regiones de la UE.

Para fines estadísticos, se informa sobre el comercio entre países y regiones de la UE cada mes. Puede imprimir el informe Intrastat, según los ajustes **Asignación de formato de informe** en la página **Parámetros de comercio exterior**. También puede generar un archivo electrónico según los ajustes **Asignación de formato de archivo** en la página **Parámetros de comercio exterior**. Para obtener más información acerca de los informes Intrastat, incluidos los requisitos previos necesarios, consulte las grabaciones de tareas de informes Intrastat.

  - Generar una declaración de Intrastat de la UE,
  - Transferir transacciones a Intrastat,
  - Especificación de una dirección de embarque para una transacción intracomunitaria.

## <a name="prerequisites"></a>Requisitos previos
La tabla siguiente muestra los requisitos previos para los informes Intrastat.

|  Requisito previo  |  Descripción  |
|-------------------------|-------------------------|
| Configuración de dirección | Configure códigos ISO (organización internacional para la estandarización) para los países y regiones. |
| Entidad jurídica | Configure números de identificación fiscal (NIF) para importación y exportación, la extensión del número de sucursal de importación o exportación y el código de Intrastat asignado a la entidad jurídica. |
| Jerarquía de categorías de productos (jerarquía de ventas, jerarquía de compras) | Asigne los códigos de mercancías de Intrastat a los nodos de categorías en la ficha **Códigos de mercancía** de la página **Jerarquía de categoría**. Cuando se asigna un código de mercancía a un nodo de categoría principal, dicho código se aplica a todos los nodos de categorías secundarias. Los códigos de mercancía seleccionados estarán disponibles en la vista **Seleccionado** al seleccionar un código de mercancía en los detalles de los productos y en el pedido de ventas, el pedido de compra y las líneas de pedido de transferencia. |
| Detalles de producto emitido | Configure los siguientes datos de comercio exterior para los productos emitidos:<ul><li>**Código de mercancía**: seleccione un código en la lista de mercancías seleccionadas recuperadas de las categorías de productos asignadas o en la lista completa de códigos de mercancías de Intrastat.</li><li>**Porcentaje de gastos estadístico**</li><li>**País/región de origen**: seleccione el país o la región predeterminado donde se obtiene o se producen las mercancías.</li><li>**Comunidad autónoma/provincia de origen/destino**: seleccione la comunidad autónoma o la provincia de destino predeterminados para las llegadas y la comunidad autónoma o la provincia de origen para distribuciones.</li><li>**Peso neto en kg**</li><li>**Excluir**: habilite este parámetro para no transferir transacciones con este producto a Intrastat</li></ul> |
| Empresas cliente | Configure la dirección de entrega del cliente en el país o la región de la UE. |
| Proveedores | Configure la dirección del proveedor en el país o la región de la UE. |
| Cargos varios | Configure el código de gastos varios que incluir en el importe de la factura, el importe estadístico, o ambos. En la página **Códigos de gastos**, en la ficha **Comercio exterior**, active **Valor de la factura de Intrastat** para incluir el importe de gastos en el valor de la factura, y active **Valor estadístico de Intrastat** para incluir el importe de gastos en el valor estadístico.</br>Para obtener más información, revise el ejemplo de [Códigos de transacción y cargos varios](#transaction-codes-and-miscellaneous-charges). |
| Informes electrónicos | Realice configuraciones de informes electrónicos para exportar los datos de Intrastat en un archivo electrónico con el formato requerido por las autoridades relevantes, y ver los datos de Intrastat en un formato sencillo y legible (por ejemplo, en Microsoft Excel). |
| Almacenes | Cuentas de proveedor asociadas con los códigos de almacén para rellenar el número de identificación fiscal al transferir el pedido de transferencia.</br>Para obtener más información, revise el ejemplo de [Pedido de transferencia](#transfer-order).|

## <a name="setup"></a>Configurar
Las siguientes secciones describen los ajustes necesarios para los informes Intrastat.

### <a name="set-up-all-required-intrastat-related-lists"></a>Configuración de todas las listas relacionadas con Intrastat necesarias

|   Lista   |   Información adicional   |
|-------------------------|-------------------------|
| Códigos de mercancías | Configure una jerarquía de categorías de tipo **Código de mercancía** y especifique todos los códigos de mercancía en función de la lista de nomenclatura combinada. Para cada mercancía se configura la información siguiente:<ul><li>El nombre de la mercancía y su código.</li><li>El nombre descriptivo y/o traducido.</li><li>Configuración para informar de unidades (suplementarias) adicionales en la pestaña **Comercio exterior**. Puede seleccionar la unidad adicional en la lista de la unidad. También puede especificar si el peso de las mercancías se debe notificar además de la unidad adicional seleccionada.</li></ul>Para obtener más información, revise el ejemplo de [Unidades adicionales](#additional-units).|
| Códigos de transacción | Configure la naturaleza de la transacción de acuerdo con los requisitos del país o la región. Para cada código de transacción que haya configurado, debe configurar las reglas para calcular los importes de factura y los importes estadísticos para pedidos de transferencia y pedidos de venta o compra.<ul><li>Para los pedidos de transferencia, configure una de las reglas siguientes para calcular los importes de factura y los importes estadísticos:<ul><li>**Vacío**: el importe será 0 (cero).</li><li>**Importe de coste financiero**: el importe será igual al coste financiero.</li><li>**Coste total**: el importe será igual al coste total de la transacción.</li><li>**Manual**: el importe será igual al importe que se especifique manualmente en la línea de pedido de transferencia.</li></ul></li><li>Para los pedidos de venta y de compra, configure una de las reglas siguientes para calcular los importes de factura y los importes estadísticos:<ul><li>**Vacío**: el importe será 0 (cero).</li><li>**Importe de factura**: el importe será igual al importe facturado para la mercancía.</li><li>**Importe base**: el importe será igual al importe que será facturado antes de aplicar descuentos.</li></ul></ul>Para obtener más información, revise el ejemplo de [Códigos de transacción y cargos varios](#transaction-codes-and-miscellaneous-charges). |
| Métodos de transporte | Configure el modo de transporte de acuerdo con los requisitos del país o la región. Para cada modo de entrega, puede configurar un método de transporte predeterminado en la ficha **Comercio exterior**. |
| Puertos | Configure el puerto o el aeropuerto de carga y descarga si esta información la recopila su país o región. |
| Procedimientos de estadísticas | Configure el procedimiento estadístico si esta información la recopila su país o región. |



### <a name="set-up-rules-for-compressing-intrastat-transactions"></a>Configuración de reglas para comprimir transacciones de Intrastat

En la página **Compresión de Intrastat**, puede seleccionar los campos que se usarán para la compresión. Todas las transacciones que tienen la misma combinación de valores para los campos seleccionados en el diario de Intrastat se comprimirán en una única transacción al ejecutar la función Comprimir en el diario de Intrastat.

### <a name="set-up-foreign-trade-parameters"></a>Configurar parámetros de comercio exterior

Use la página **Parámetros de comercio exterior** para configurar los parámetros en la tabla siguiente.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabulación</th>
<th>Parámetros</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>General</td>
<td><ul>
<li><strong>General</strong>: especifique la información siguiente:
<ul>
<li>El códigos de transacción predeterminados para los pedidos de ventas y de compra, las notas de abono y los pedidos de transferencia. El código de transacción que se configura para las notas de abono también se usa como el código para la devolución de mercancías físicas y se usa para devoluciones físicas de desviación frente a notas de abono de corrección. Las devoluciones de mercancías físicas se informan en la transferencia intrastat con una dirección diferente. La devolución de la llegada se informa como distribución y la devolución de la distribución se informa como llegada.</li>
<li>El empleado responsable de preparar los informes Intrastat.</li>
</ul></li>
<li><strong>Límite mínimo</strong>: especifique los ajustes para actualizar las transacciones que se encuentran por debajo del umbral:
<ul>
<li>El importe del umbral y el peso.</li>
<li>El código de mercancía que aplicar a las transacciones bajo el umbral.</li>
</ul></li>
<li><strong>Transferencia</strong>: especifique los criterios para transferir transacciones al diario de Intrastat. Puede especificar que las transacciones se transfieran solo cuando los artículos cumplan uno o todos los criterios siguientes:
<ul>
<li>Los artículos no son artículos de servicio.</li>
<li>Los artículos tienen un código de mercancía.</li>
<li>Los artículos tienen un peso.</li>
<li>Los artículos tienen unidades adicionales.</li>
</ul></li>
<li><strong>Comprobar configuración</strong>: especifique las reglas para validar si los datos de Intrastat se han completado. Puede seleccionar qué datos se validarán.</li>
<li><strong>Reglas de redondeo</strong>: especifique las opciones siguientes para redondear importes y pesos en los informes Intrastat:
<ul>
<li>La de regla de redondeo (precisión).</li>
<li>El método de redondeo: hacia arriba, hacia abajo o normal.</li>
<li>El número de decimales en importes y pesos.</li>
<li>Instrucciones para redondear pesos inferiores a 1 kilogramo (kg): hasta 1 kg, normal o sin redondeo.</li>
</ul></li>
<li><strong>Informes electrónicos</strong>: especifique referencias a configuraciones de informes electrónicos, de manera que pueda generar un archivo y un informe electrónico.</li>
<li><strong>Jerarquía de códigos de mercancías</strong>: especifique la jerarquía de categorías del tipo <strong>Código de mercancía</strong> que representa el código de mercancía Intrastat CN8.</li>
  <li> <strong>Tipo de cambio</strong> – De manera opcional, especifique un tipo de cambio que utilizará para notificar las transacciones de ventas y compras de intrastat en divisas extranjeras. Esto se utiliza si la tasa es diferente de la que se aplica al registrar la transacción.</li>  
</ul></td>
</tr>
<tr class="even">
<td>Información de contacto del agente</td>
<td>Especifique el nombre del agente, la dirección, el número de identificación fiscal (NIF), el número de teléfono y el número de fax.</td>
</tr>
<tr class="odd">
<td>Propiedades de país / región</td>
<td>Defina el país o región de la entidad jurídica actual en <strong>Nacional</strong>. Defina los países o regiones de la UE que participe en comercio de la UE con la entidad jurídica actual en <strong>UE</strong>. Para cada país o región, también debe identificar el código de país o región para comercio exterior.</td>
</tr>
<tr class="even">
<td>Secuencia numérica</td>
<td>Especifique la secuencia numérica para el diario de Intrastat.</td>
</tr>
</tbody>
</table>

## <a name="example"></a>Ejemplo

### <a name="transaction-codes-and-miscellaneous-charges"></a><a name= "transaction-codes-and-miscellaneous-charges"></a>Códigos de transacción y cargos varios

Este artículo cubre un escenario en el que una empresa en Alemania debe comprar productos de una empresa en Italia. Para realizar esta compra, la empresa alemana debe configurar nuevos códigos de transacción y configurar reglas de cálculo para el importe de la factura y el importe estadístico para esos códigos de transacción. Adicionalmente, cuando la empresa genera una factura, debe especificar los cargos varios y sus porcentajes. Esos valores se tendrán en cuenta cuando se calcule el valor estadístico.

Este escenario usa la entidad jurídica **DEMF**.

#### <a name="preliminary-setup"></a>Configuración preliminar

1. Vaya a **Administración de la organización** > **Organización** > **Entidades jurídicas** y seleccione **DEMF**.
2. En la ficha desplegable **Direcciones**, verifique que el campo **País o región** se ha establecido en **DEU (Alemania)**.
3. Vaya a **Proveedores** > **Proveedores** > **Todos los proveedores**.
4. En la cuadrícula, seleccione **DE-001**.
5. En la ficha desplegable **Dirección**, seleccione **Editar**.
6. En el cuadro de diálogo **Editar dirección**, en el campo **País/región**, seleccione **ITA**.
7. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.

#### <a name="set-up-transaction-codes"></a>Configurar códigos de transacción

1. Vaya a **Impuestos** > **Configurar** > **Comercio exterior** > **Códigos de transacción**.
2. En la cuadrícula, seleccione **11**. A continuación, seleccione **Eliminar** en el panel de acciones.
3. En el panel de acciones, haga clic en **Nueva**.
4. En la ficha desplegable **Códigos de transacción**, en el campo **Código** de **transacción**, escriba **11**.
5. En el campo **Nombre**, introduzca **Compra o ventas abiertas**.
6. En la sección **Ventas y compras**, en el campo **Importe de la factura**, seleccione **Importe de la factura**.
7. En el campo **Importe estadístico**, seleccione **Importe de la factura**.
8. En el panel Acciones, seleccione **Guardar**.

#### <a name="set-up-miscellaneous-charges"></a>Configuración de gastos varios

1. Vaya a **Proveedores** > **Configuración de cargos** > **Código de gastos**.
2. En la cuadrícula, seleccione **Flete**.
3. En el panel Acciones, seleccione **Editar**.
4. En la ficha desplegable **Comercio exterior**, establezca las opciones **Valor de la factura de intrastat** y **Valor estadístico de intrastat** a **Sí**.

#### <a name="set-up-foreign-trade-parameters"></a>Configurar parámetros de comercio exterior

1. Vaya a **Impuestos** > **Configuración** > **Comercio exterior** > **Parámetros de comercio exterior**.
2. En la pestaña **Intrastat**, en la ficha desplegable **General**, en el campo **Código de** **transacción**, seleccione **11**.
3. En la ficha desplegable **Jerarquía de códigos de mercancías**, compruebe que el campo **Jerarquía de categorías** está establecido como **Intrastat**.

#### <a name="create-a-purchase-order"></a>Crear un pedido de compra

1. Vaya a **Proveedores** > **Pedidos de compra** > **Todos los pedidos de compra**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el cuadro de diálogo **Crear pedido de compra**, en el campo **Cuenta de proveedor**, seleccione **DE-001**.
4. Seleccione **Aceptar**.
5. En la pestaña **Encabezado**, en la ficha desplegable **Comercio** **exterior**, compruebe que el campo **Código de transacción** está configurado en **11**.
6. En la pestaña **Líneas**, en la ficha desplegable **Líneas de pedido de compra**, en el campo **Número de artículo**, seleccione **D0003**. En el campo **Cantidad**, especifique **10**.
7. En la ficha desplegable **Detalles de línea**, en la pestaña **Comercio exterior**, en la sección **Comercio exterior**, asegúrese de que el campo **Código de transacción** se ha establecido automáticamente.
8. En la ficha desplegable **Líneas de pedido de compra**, en el menú **Finance**, en la sección **Gastos**, seleccione **Mantener gastos**.
9. En el campo **Código de gastos**, seleccione **FLETE**.
10. En el campo **Valor de gastos**, escriba **30**.
11. En el panel Acciones, seleccione **Guardar**. A continuación, cierre la página.
12. En el panel de acciones, en la ficha **Compra**, en el grupo **Acciones**, seleccione **Confirmar**.
13. En el panel de acciones, en la ficha **Factura**, en el grupo **Generar**, seleccione **Factura**.
14. En el panel de acciones, seleccione **Valor predeterminado de origen**. En el campo **Cantidad predeterminada para líneas**, seleccione **Cantidad pedida**. A continuación seleccione **Aceptar**.
15. En la ficha desplegable **Encabezado de factura de proveedor**, en la sección **Identificación de factura**, en el campo **Número**, escriba **00100**.
16. En la sección **Fechas de factura**, en el campo **Fecha de la factura**, seleccione **24/11/2021** (24 de noviembre de 2021).
17. En el panel de acciones, seleccione **Registrar** para registrar la factura.

### <a name="transfer-the-vendor-invoice-to-the-intrastat-journal"></a>Transferir la factura del proveedor al diario intrastat

1. Vaya a **Impuestos** > **Declaraciones** > **Comercio exterior** > **Intrastat**.
2. En el panel de acciones, seleccione **Transferir**.
3. En el cuadro de diálogo **Intrastat (Transferir)**, establezca la opción **Factura de proveedor** en **Sí**.
4. Seleccione **Aceptar** para transferir las transacciones y, a continuación, revise el diario de intrastat.

   ![Línea que representa el pedido de compra con los gastos varios en la página de Intrastat](media/intrastat_overview_1.png)

5. Revisa el pedido de compra en la pestaña **General**. Observe que el campo **Valor de la factura** muestra la suma de los campos **Importe de la factura** e **Importe de los gastos de la factura**, y el campo **Valor estadístico** muestra la suma de los campo **Importe estadístico** e **Importe de los gastos estadísticos**.

   ![Detalles del pedido de compra con gastos varios en la pestaña General de la página de Intrastat](media/intrastat_overview_2.png)

### <a name="transfer-order"></a>Pedido de transferencia

En este ejemplo, una empresa en Alemania debe trasladar dos unidades de mercancías desde un almacén en Alemania a un almacén en Italia. Los gastos a una tasa del 20 por ciento también deben especificarse para este producto para la contabilidad en el campo **Valor estadístico**. Este ejemplo usa la entidad jurídica **DEMF**.

#### <a name="preliminary-setup"></a>Configuración preliminar

1. Vaya a **Administración de la organización** > **Organización** > **Entidades jurídicas** y seleccione **DEMF**.
2. En la ficha desplegable **Direcciones**, verifique que el campo **País o región** se ha establecido en **DEU (Alemania)**.
3. Vaya a **Impuestos** > **Configuración** > **Comercio exterior** > **Parámetros de comercio exterior**.
4. En la ficha desplegable **Jerarquía de códigos de mercancías**, compruebe que el campo **Jerarquía de categorías** está establecido como **Intrastat**.
5. Vaya a **Proveedores** > **Proveedores** > **Todos los proveedores**.
6. En la cuadrícula, seleccione **DE-001**.
7. En la ficha desplegable **Dirección**, seleccione **Editar**.
8. En el cuadro de diálogo **Editar dirección**, en el campo **País/región**, seleccione **ITA**.
9. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.

#### <a name="set-up-transaction-codes"></a>Configurar códigos de transacción

1. Vaya a **Impuestos** > **Configurar** > **Comercio exterior** > **Códigos de transacción**.
2. En la cuadrícula, seleccione **11**. A continuación, seleccione **Eliminar** en el panel de acciones.
3. En el panel de acciones, haga clic en **Nueva**.
4. En la ficha desplegable **Códigos de transacción**, en el campo **Código** de **transacción**, escriba **11**.
5. En el campo **Nombre**, introduzca **Compra o ventas abiertas**.
6. En la sección **Pedido de transferencia**, en el campo **Importe de la factura**, seleccione **Coste total**.
7. En el campo **Importe estadístico**, seleccione **Coste total**.
8. En el panel Acciones, seleccione **Guardar**.
9. Vaya a **Impuestos** > **Configuración** > **Comercio exterior** > **Parámetros de comercio exterior**.
10. En la pestaña **Intrastat**, en la ficha desplegable **General**, en el campo **Pedido de transferencia**, seleccione **11**.

#### <a name="set-up-charges-for-an-item"></a>Configurar gastos para un artículo

1. Vaya a **Gestión de información de productos** > **Productos** > **Productos emitidos**.
2. En la cuadrícula, seleccione **D0001**.
3. En la ficha desplegable **Comercio exterior**, en la sección **Intrastat**, en el campo **Porcentaje de gastos**, introduzca **20**.

#### <a name="change-the-site-address"></a>Cambiar la dirección del sitio

1. Vaya a **Gestión de almacenes** > **Configurar** > **Almacén** > **Sitios**.
2. En la cuadrícula, seleccione **1**.
3. En la ficha desplegable **Direcciones**, seleccione **Editar**.
4. En el cuadro de diálogo **Editar dirección**, en el campo **País/región**, seleccione **DEU**.
5. Seleccione **Aceptar**.
6. En la cuadrícula, seleccione **2**.
7. En la ficha desplegable **Direcciones**, seleccione **Editar**.
8. En el cuadro de diálogo **Editar dirección**, en el campo **País/región**, seleccione **ITA**.
9. Seleccione **Aceptar**.
10. Vaya a **Gestión de almacenes** > **Configurar** > **Almacén** > **Almacenes**.
11. En la cuadrícula, seleccione **21**.
12. En la ficha desplegable **General**, en la sección **Referencia**, en el campo **Cuenta del proveedor**, seleccione **DE-001**.

#### <a name="create-a-transfer-order"></a>Creación de un pedido de transferencia

1. Vaya a **Gestión del inventario** > **Pedidos de salida** > **Orden de transferencia**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En la pestaña **Líneas**, en la ficha desplegable **Encabezado de pedido de transferencia**, en la sección **Descripción general**, en el campo **Desde almacén**, seleccione **11**. En el campo **Al almacén**, seleccione **21**.
4. En la pestaña **Líneas**, en la ficha desplegable **Líneas de pedido de transferencia**, seleccione **Agregar**.
5. En el campo **Código de artículo**, seleccione **D0001**. En el campo **Cantidad enviada**, especifique **2**.
6. En la ficha desplegable **Detalles de línea**, en la pestaña **Comercio exterior**, en la sección **Comercio exterior**, asegúrese de que el campo **Código de transacción** se ha establecido automáticamente.
7. En el panel de acciones, en la ficha **Enví**, en el grupo **Operaciones**, seleccione **Enviar pedido de transferencia**.
8. En el cuadro de diálogo **Envío**, en la pestaña **Descripción general**, en el campo **Actualizar**, seleccione **Todo**.
9. Seleccione **Aceptar** para enviar el pedido.
10. En el panel de acciones, en la pestaña **Recepción** del grupo **Operaciones**, seleccione **Recepción**.
11. En el cuadro de diálogo **Recepción**, en la pestaña **Descripción general**, en el campo **Actualizar**, seleccione **Todo**.
12. Seleccione **Aceptar** para enviar el pedido.

#### <a name="transfer-the-transfer-order-to-the-intrastat-journal"></a>Transferir el pedido de transferencia al diario intrastat

1. Vaya a **Impuestos** > **Declaraciones** > **Comercio exterior** > **Intrastat**.
2. En el panel de acciones, seleccione **Transferir**.
3. En el cuadro de diálogo **Intrastat (Transferencia)**, configure la opción **Pedido de transferencia** a **Sí** y todas las demás opciones a **No**.
4. Seleccione **Aceptar** para transferir las transacciones y, a continuación, revise el diario de intrastat.

   ![Línea que representa el pedido de transferencia en la página de Intrastat](media/intrastat_overview_3.png)

5.  Revise el pedido de transferencia en la pestaña **General**.

    Observe que los campos en las secciones **Valor de la factura** y **Valor estadístico** se configuran automáticamente. Los valores de los campos **Importe de la factura** e **Importe estadístico** se basan en la configuración de la página **Códigos de transacción**. El valor **20** en el campo **Porcentaje de gastos** es el valor que se establece en la página **Producto emitido**. El valor en el campo **Importe de los gastos estadísticos** es una expresión cuantitativa de los gastos (porque 107,24 es igual al 20 por ciento de 536,18). El valor del campo **Valor estadístico** es la suma de los valores de los campos **Importe estadístico** e **Importe de los gastos estadísticos**.

  ![Detalles del pedido de transferencia en la pestaña General de la página de Intrastat](media/intrastat_overview_4.png)

### <a name="additional-units"></a>Unidades adicionales

En este ejemplo, una empresa en Alemania debe comprar 10 unidades de bienes a una empresa en Italia. Además de los códigos de mercancías, se deben especificar unidades adicionales para las mismas. El ejemplo muestra cómo crear nuevas unidades de medida, asignar unidades adicionales al código de producto de Intrastat, registrar transacciones que tienen unidades adicionales y revisar el diario de Intrastat donde se establece el campo para las unidades adicionales.

#### <a name="preliminary-setup"></a>Configuración preliminar

1. Vaya a **Administración de la organización** > **Organización** > **Entidades jurídicas** y seleccione **DEMF**.
2. En la ficha desplegable **Direcciones**, verifique que el campo **País o región** se ha establecido en **DEU (Alemania)**.
3. Vaya a **Impuestos** > **Configuración** > **Comercio exterior** > **Parámetros de comercio exterior**.
4. En la pestaña **Intrastat**, en la ficha desplegable **General**, en el campo **Código de** **transacción**, seleccione **11**.
5. En la ficha desplegable **Jerarquía de códigos de mercancías**, compruebe que el campo **Jerarquía de categorías** está establecido como **Intrastat**.
6. Vaya a **Proveedores** > **Proveedores** > **Todos los proveedores**.
7. En la cuadrícula, seleccione **DE-001**.
8. En la ficha desplegable **Dirección**, seleccione **Editar**.
9. En el cuadro de diálogo **Editar dirección**, en el campo **País/región**, seleccione **ITA**.
10. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.

#### <a name="create-a-unit-of-measure"></a>Creación de una unidad de medida

1. Vaya a **Administración de la organización** > **Configuración** > **Unidades** > **Unidades**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el campo **Unidad**, introduzca un nombre para la unidad de medida. Para este ejemplo, escriba **GRM**.
4. En la ficha desplegable **General**, en la sección **Clasificación**, en el campo **Clase de unidad**, seleccione la propiedad que mide la unidad. Para este ejemplo, seleccione **Masa**.
5. En el campo **Sistema de unidades**, seleccione el sistema de medida al que pertenece la unidad. Por ejemplo, seleccione **Unidades métricas**.

#### <a name="set-up-unit-conversions"></a>Configurar conversiones de unidad

1. Vaya a **Administración de la organización** > **Configuración** > **Unidades** > **Conviersiones de unidad**.
2. En la pestaña **Conversiones entre clases**, seleccione **Nueva**.
3. En el cuadro de diálogo **Conversión de unidad**, en el campo **Producto**, seleccione **F00007**.
4. En el campo **Desde unidad**, seleccione **ea**.
5. En el campo **A la unidad**, seleccione **GRM**.
6. Verifique que la tasa de conversión sea **1 = 1**.
7. Seleccione **Aceptar**.
8. Vaya a **Gestión de información de productos** > **Productos** > **Productos emitidos**.
9. En la cuadrícula, seleccione **F00007**.
10. En la ficha desplegable **Administrar inventario**, en la sección **Inventario**, en el campo **Unidad**, seleccione **GRM**.
11. En el panel Acciones, seleccione **Guardar**.

#### <a name="set-up-product-information"></a>Configurar información de productos

1. Vaya a **Gestión de información de productos** > **Productos** > **Productos emitidos**.
2. En la cuadrícula, seleccione **F00007**.
3. En la ficha desplegable **Comercio exterior**, en la sección **Intrastat**, en el campo **Mercancía**, seleccione **920 20 34**.
4. En el panel Acciones, seleccione **Guardar**.

#### <a name="assign-the-additional-unit-to-an-intrastate-commodity-code"></a>Asigne la unidad adicional a un código de mercancía intraestatal

1. Vaya a **Gestión de información de productos** > **Configuración** > **Categorías y atributos** > **Jerarquías de categorías**.
2. En la lista, seleccione **Intrastat**.
3. En la cuadrícula, seleccione **Altavoz**.
4. En la ficha desplegable **Comercio exterior**, en el campo **Unidades adicionales**, seleccione **GRM**.
5. En el panel Acciones, seleccione **Guardar**.

   Para obtener más información, consulte [Administrar unidades de medida](../../supply-chain/pim/tasks/manage-unit-measure.md).

#### <a name="create-a-purchase-order"></a>Crear un pedido de compra

1. Vaya a **Proveedores** > **Pedidos de compra** > **Todos los pedidos de compra**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el cuadro de diálogo **Crear pedido de compra**, en el campo **Cuenta de proveedor**, seleccione **DE-001**.
4. Seleccione **Aceptar**.
5. En la pestaña **Encabezado**, en la ficha desplegable **Comercio** **exterior**, compruebe que el campo **Código de transacción** está configurado en **11**.
6. En la pestaña **Líneas**, en la ficha desplegable **Líneas de pedido de compra**, en el campo **Número de artículo**, seleccione **F00007**. En el campo **Cantidad**, especifique **10**.
7. En la ficha desplegable **Detalles de línea**, en la pestaña **Comercio exterior**, en la sección **Comercio exterior**, asegúrese de que los campos **Código de transacción** y **Mercancía** se han establecido automáticamente.
8. En el panel de acciones, en la ficha **Compra**, en el grupo **Acciones**, seleccione **Confirmar**.
9. En el panel de acciones, en la ficha **Factura**, en el grupo **Generar**, seleccione **Factura**.
10. En el panel de acciones, seleccione **Valor predeterminado de origen**. En el campo **Cantidad predeterminada para líneas**, seleccione **Cantidad pedida**. A continuación seleccione **Aceptar**.
11. En la ficha desplegable **Encabezado de factura de proveedor**, en la sección **Identificación de factura**, en el campo **Número**, escriba **VE-0010**.
12. En la sección **Fechas de factura**, en el campo **Fecha de la factura**, seleccione **05/10/2021** (5 de octubre de 2021).
13. En el panel de acciones, seleccione **Registrar** para registrar la factura.

#### <a name="transfer-the-vendor-invoice-to-the-intrastat-journal"></a>Transferir la factura del proveedor al diario intrastat

1. Vaya a **Impuestos** > **Declaraciones** > **Comercio exterior** > **Intrastat**.
2. En el panel de acciones, seleccione **Transferir**.
3. En el cuadro de diálogo **Intrastat (Transferir)**, establezca la opción **Factura de proveedor** en **Sí**.
4. Seleccione **Aceptar** para transferir las transacciones y, a continuación, revise el diario de intrastat.

   ![Línea que representa el pedido de compra en la página de Intrastat](media/intrastat_overview_5.png)

5. Revisa el pedido de compra en la pestaña **General**. Tenga en cuenta que los campo **Cantidad de unidades adicionales** y **Unidad adicional** en la sección **Unidad** se configuran automáticamente.

   ![Detalles del pedido de compra en la pestaña General de la página de Intrastat](media/intrastat_overview_6.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
