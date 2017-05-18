---
title: intrastat
description: "Este artículo proporciona información acerca de los informes de Intrastat para comercio de bienes y, en algunos casos, servicios entre países y regiones de la Unión Europea (UE). Proporciona una visión general del proceso de informes y describe la configuración y los requisitos previos necesarios."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: Intrastat
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 28581
ms.assetid: 7d53a168-1827-48b8-99f8-b1e77efd3dff
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 3b8a13205f0a001cc911e1475139f34f5b51af8c
ms.contentlocale: es-es
ms.lasthandoff: 04/25/2017


---

# <a name="intrastat"></a>intrastat

[!include[banner](../includes/banner.md)]


Este artículo proporciona información acerca de los informes de Intrastat para comercio de bienes y, en algunos casos, servicios entre países y regiones de la Unión Europea (UE). Proporciona una visión general del proceso de informes y describe la configuración y los requisitos previos necesarios.

Intrastat es el sistema de recopilación de información y generación de estadísticas sobre comercio de bienes entre países y regiones de la Unión Europea (UE). Siempre que un producto cruce la frontera de otro país o región de la UE. hace falta presentar un informe Intrastat. En varios países y regiones, los informes Intrastat también son obligatorios para los servicios. Los informes Intrastat pueden incluir elementos necesarios y opcionales. Los elementos siguientes son obligatorios: el número de IVA de la parte responsable de proporcionar información, el período de referencia, el flujo (recepción o distribución), el código de mercancía de ocho dígitos, el estado miembro socio (estado miembro de envío en recepción y el estado miembro de destino en distribución), el valor de las mercancías, la cantidad de las mercancías (masa neta y unidad suplementaria) y la naturaleza de la transacción. Los países y regiones también pueden recopilar elementos opcionales bajo distintas condiciones. Algunos elementos opcionales son el país o la región de origen, las condiciones de entrega, el modo de transporte, un código de mercancía más detallado que el CN8, la región de origen en distribución y la región de destino en llegadas, el procedimiento estadístico, el valor estadístico, una descripción de las mercancías y el puerto o el aeropuerto de carga y descarga.

## <a name="overview-of-the-intrastat-reporting-process"></a>Visión general del proceso de informes Intrastat
En las secciones siguientes se describe el flujo de información general en los informes Intrastat.

### <a name="1-enter-a-transaction-that-crosses-the-border-of-another-eu-countryregion"></a>1. Especificación de transacción transfronteriza a otro país o región de la UE

Una factura de cliente, una factura de texto libre, una factura de compra, una factura de proyecto, un albarán del cliente, una recepción de producto del proveedor o un pedido de transferencia se transfiere al diario de Intrastat si el tipo de país o región de destino (en distribuciones) o de envío (en llegadas) es **UE**. Esta función se ha ampliado para Microsoft Dynamics 365 for Operations versión 1611 y permite especificar una dirección de embarque para una transacción de comercio intracomunitario. Si una dirección de embarque difiere de una dirección empresarial del proveedor (o la dirección empresarial del cliente para el pedido de devolución), los informes Intrastat operarán con esta información. Al crear un pedido de ventas, una factura de servicios, un pedido de compra, una factura de proveedor, una factura de proyecto o un pedido de transferencia, algunos campos relacionados con comercio exterior tienen valores predeterminados en el encabezado del documento o en la línea. El código de transacción predeterminado se toma del campo correspondiente en la página **Parámetros de comercio exterior**. El código de mercancía predeterminado, el país o la región de origen y el estado o la provincia se toman del artículo. Puede cambiar los valores predeterminados y también puede completar otra información de comercio exterior: las estadísticas procedimiento, método de transporte y puerto.

### <a name="2-use-the-intrastat-journal-to-generate-information-about-trade-among-eu-countriesregions"></a>2. Utilice el diario de Intrastat para generar información sobre el comercio entre los países y regiones de la UE.

Para fines estadísticos, se genera información sobre el comercio entre países y regiones de la UE cada mes. Puede transferir transacciones desde una factura de texto libre, una factura de cliente, un albarán de cliente, una factura de proveedor, un albarán de proveedor, una factura de proyecto o un pedido de transferencia, según los criterios de transferencia que se hayan configurado en la página **Parámetros de comercio exterior**. También puede especificar transacciones manualmente. Puede actualizar manualmente las transacciones transferidas en el diario de Intrastat, si se requieren actualizaciones. En determinadas condiciones configuradas en la página **Compresión de Intrastat**, puede comprimir las transacciones en el diario de Intrastat. Algunos países y regiones le permiten aplicar un pequeño umbral de transacción. A continuación puede informar de transacciones por debajo de dicho umbral bajo el código de mercancía especificado. Puede actualizar el código de mercancía en las correspondientes líneas del diario de Intrastat, en el ajuste **Límite mínimo** de la página **Parámetros de comercio exterior**. También puede comprimir esas transacciones, según el ajuste **Compresión de Intrastat**. Puede validar la finalización de las transacciones en el diario de Intrastat, según el ajuste **Comprobar configuración** en la página **Parámetros de comercio exterior**. Se puede validar la cumplimentación de los datos en los campos correspondientes: país o región, estado o provincia, peso, código de mercancía, código de transacción, unidad adicional, puerto, origen, términos de entrega, método de transporte y número de identificación fiscal (NIF). Las transacciones que no se hayan completado se marcarán como no válidas.

### <a name="3-use-the-intrastat-journal-to-report-information-about-trade-among-eu-countriesregions"></a>3. Utilice el diario de Intrastat para informar sobre el comercio entre los países y regiones de la UE.

Para fines estadísticos, se informa sobre el comercio entre países y regiones de la UE cada mes. Puede imprimir el informe Intrastat, según los ajustes **Asignación de formato de informe** en la página **Parámetros de comercio exterior**. También puede generar un archivo electrónico según los ajustes **Asignación de formato de archivo** en la página **Parámetros de comercio exterior**. Para obtener más información acerca de los informes Intrastat, incluidos los requisitos previos necesarios, consulte las grabaciones de tareas de informes Intrastat.

-   Generar una declaración de Intrastat de la UE,
-   Transferir transacciones a Intrastat,
-   Especificación de una dirección de embarque para una transacción intracomunitaria.

## <a name="prerequisites"></a>Requisitos previos
La tabla siguiente muestra los requisitos previos para los informes Intrastat.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Requisito previo</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Configuración de dirección</td>
<td>Configure códigos ISO (organización internacional para la estandarización) para los países y regiones.</td>
</tr>
<tr class="even">
<td>Entidad jurídica</td>
<td>Configure números de identificación fiscal (NIF) para importación y exportación, la extensión del número de sucursal de importación o exportación y el código de Intrastat asignado a la entidad jurídica.</td>
</tr>
<tr class="odd">
<td>Jerarquía de categorías de productos (jerarquía de ventas, jerarquía de compras)</td>
<td>Asigne los códigos de mercancías de Intrastat a los nodos de categorías en la ficha <strong>Códigos de mercancía</strong> de la página <strong>Jerarquía de categoría</strong>. Cuando se asigna un código de mercancía a un nodo de categoría principal, dicho código se aplica a todos los nodos de categorías secundarias. Los códigos de mercancía seleccionados estarán disponibles en la vista <strong>Seleccionado</strong> al seleccionar un código de mercancía en los detalles de los productos emitidos y en el pedido de ventas, el pedido de compra y las líneas de pedido de transferencia.</td>
</tr>
<tr class="even">
<td>Detalles de producto emitido</td>
<td>Configure los siguientes datos de comercio exterior para los productos emitidos:
<ul>
<li><strong>Código de mercancía</strong>: seleccione un código en la lista de mercancías seleccionadas recuperadas de las categorías de productos asignadas o en la lista completa de códigos de mercancías de Intrastat.</li>
<li><strong>Porcentaje de gastos estadístico</strong></li>
<li><strong>País/región de origen</strong>: seleccione el país o la región predeterminado donde se obtiene o se producen las mercancías.</li>
<li><strong>Comunidad autónoma/provincia de origen/destino</strong>: seleccione la comunidad autónoma o la provincia de destino predeterminados para las llegadas y la comunidad autónoma o la provincia de origen para distribuciones.</li>
<li><strong>Peso neto en kg</strong></li>
</ul></td>
</tr>
<tr class="odd">
<td>Clientes</td>
<td>Configure la dirección de entrega del cliente en el país o la región de la UE.</td>
</tr>
<tr class="even">
<td>Proveedores</td>
<td>Configure la dirección del proveedor en el país o la región de la UE.</td>
</tr>
<tr class="odd">
<td>Cargos varios</td>
<td>Configure el código de gastos varios que incluir en el importe de la factura, el importe estadístico, o ambos. En la página <strong>Códigos de gastos</strong>, en la ficha <strong>Comercio exterior</strong>, active <strong>Valor de la factura de Intrastat</strong> para incluir el importe de gastos en el valor de la factura, y active <strong>Valor estadístico de Intrastat</strong> para incluir el importe de gastos en el valor estadístico.</td>
</tr>
<tr class="even">
<td>Informes electrónicos</td>
<td>Realice configuraciones de informes electrónicos para exportar los datos de Intrastat en un archivo electrónico con el formato requerido por las autoridades relevantes, y ver los datos de Intrastat en un formato sencillo y legible (por ejemplo, en Microsoft Excel).</td>
</tr>
</tbody>
</table>

## <a name="setup"></a>Configuración
Las siguientes secciones describen los ajustes necesarios para los informes Intrastat.

### <a name="set-up-all-required-intrastat-related-lists"></a>Configuración de todas las listas relacionadas con Intrastat necesarias

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Lista</th>
<th>Información adicional</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Códigos de mercancías</td>
<td>Configure una jerarquía de categorías de tipo <strong>Código de mercancía</strong> y especifique todos los códigos de mercancía en función de la lista de nomenclatura combinada. Para cada mercancía se configura la información siguiente:
<ul>
<li>El nombre de la mercancía y su código.</li>
<li>El nombre descriptivo y/o traducido.</li>
<li>Ajustes para informar de unidades adicionales (suplementarias) en la ficha <strong>Comercio exterior</strong>. Puede seleccionar la unidad adicional en la lista de unidades. También puede especificar si el peso de las mercancías se debe notificar además de la unidad adicional seleccionada.</li>
</ul></td>
</tr>
<tr class="even">
<td>Códigos de transacción</td>
<td>Configure la naturaleza de la transacción de acuerdo con los requisitos del país o la región. Para cada código de transacción que haya configurado, debe configurar las reglas para calcular los importes de factura y los importes estadísticos para pedidos de transferencia y pedidos de venta o compra.
<ul>
<li>Para los pedidos de transferencia, configure una de las reglas siguientes para calcular los importes de factura y los importes estadísticos:
<ul>
<li><strong>Vacío</strong>: el importe será 0 (cero).</li>
<li><strong>Importe de coste financiero</strong>: el importe será igual al coste financiero.</li>
<li><strong>Coste total</strong>: el importe será igual al coste total de la transacción.</li>
<li><strong>Manual</strong>: el importe será igual al importe que se especifique manualmente en la línea de pedido de transferencia.</li>
</ul></li>
<li>Para los pedidos de venta y de compra, configure una de las reglas siguientes para calcular los importes de factura y los importes estadísticos:
<ul>
<li><strong>Vacío</strong>: el importe será 0 (cero).</li>
<li><strong>Importe de factura</strong>: el importe será igual al importe facturado para la mercancía.</li>
<li><strong>Importe base</strong>: el importe será igual al importe que será facturado antes de aplicar descuentos.</li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td>Métodos de transporte</td>
<td>Configure el modo de transporte de acuerdo con los requisitos del país o la región. Para cada modo de entrega, puede configurar un método de transporte predeterminado en la ficha <strong>Comercio exterior</strong>.</td>
</tr>
<tr class="even">
<td>Puertos</td>
<td>Configure el puerto o el aeropuerto de carga y descarga si esta información la recopila su país o región.</td>
</tr>
<tr class="odd">
<td>Procedimientos de estadísticas</td>
<td>Configure el procedimiento estadístico si esta información la recopila su país o región.</td>
</tr>
</tbody>
</table>

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
<li>El códigos de transacción predeterminados para los pedidos de ventas y de compra, las notas de abono y los pedidos de transferencia. El código de transacción que se configura para las notas de abono también se usa como el código para la devolución de mercancías físicas y se usa para devoluciones físicas de desviación frente a notas de abono de corrección.</li>
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
</ul></td>
</tr>
<tr class="even">
<td>Información de contacto del agente</td>
<td>Especifique el nombre del agente, la dirección, el número de identificación fiscal (NIF), el número de teléfono y el número de fax.</td>
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

 




