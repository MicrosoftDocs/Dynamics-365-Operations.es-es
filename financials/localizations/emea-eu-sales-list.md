---
title: Informes de listas de ventas de la UE
description: "Este artículo proporciona información acerca de los informes de listas de ventas de la Unión Europea (UE)."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 12811
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 06656fe519c82293d5a0eb2d48ae0f89ae0aef49
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="eu-sales-list-reporting"></a>Informes de listas de ventas de la UE

[!include[banner](../includes/banner.md)]


Este artículo proporciona información acerca de los informes de listas de ventas de la Unión Europea (UE).

<a name="eu-sales-list-reporting"></a>Informes de listas de ventas de la UE
-----------------------

Un proveedor que está suministrando mercancías o servicios intracomunitarios a empresas que se encuentran dentro de la Unión Europea (EU) debe enviar una declaración de suministros intracomunitarios (lista de ventas de la UE o ESL). El ESL debe ser enviado normalmente a las autoridades fiscales antes del último día del mes tras el período de calendario que cubre el ESL. El proveedor debe constatar el número de identificación fiscal (IVA) en el ESL y también debe constatar, por cliente, la siguiente información:

-   El número de identificación fiscal del cliente de la UE
-   El valor total de los suministros de mercancías y servicios intracomunitarios que se realizan al cliente de la UE en ese período. El proveedor también debe separar los suministros de mercancías generales de los suministros de comercio triangular. Una transacción de comercio triangular implica la entrega directa de mercancía del proveedor del proveedor al cliente cuando ambas partes están registradas en otros estados miembros de la unión europea.

Mediante el ESL, las autoridades fiscales de cada estado miembro de la Unión Europea puede comprobar si el IVA ha sido pagado por cada transacción intracomunitaria. La combinación de listados y devoluciones de IVA permite a los Estados Miembros de la Unión Europea intercambiar información sore el flujo de mercancías en la UE.

## <a name="overview-of-the-eu-sales-list-reporting-process"></a>Visión general del proceso de informes de la lista de ventas de la UE
Puede realizar las tareas siguientes para un informe de la lista de la UE:

-   Recopilar información acerca de transacciones de comercio intracomunitario. Una transacción de comercio intracomunitario puede ser una factura de ventas, una factura de servicios, una factura de proyecto o una factura de proveedor. Se identifica una transacción en función del país o región de la contrapartida. Las transacciones comerciales intracomunitarias de distintos tipos se recogen en la tabla de la lista de ventas de la UE, donde se representan en el formulario común. Cada registro de la tabla de ESL representa la transacción única y consta del identificador del IVA de una contrapartida y el valor total de las mercancías y servicios que se han suministrado.
-   (Opcional) Vista previa del informe **Lista de ventas de la UE**. Puede obtener una lista previa y validar el informe **Lista de ventas de la UE** para un período determinado en el formulario de un libro de Microsoft Excel.
-   Generar el informe **Lista de ventas de la UE**. El informe de la **Lista de ventas de la UE** se genera con el formato de archivo electrónico de un formato en particular que sea específico para cada estado miembro de la Unión Europea. En general, un informe de la **Lista de ventas de la UE** contiene información básica sobre la parte que notifica y los valores de los suministros de mercancías y servicios. La información se agrupa por país y el identificador del IVA de una contrapartida.
-   Cerrar el período de notificación de la lista de ventas de la UE. Después de generar el informe **Lista de ventas de la UE** y se enviarlo a las autoridades, puede marcar los registros de la tabla de ESL como **Cerrado**. Estas transacciones no se incluirán en los informes adicionales.

## <a name="prerequisites"></a>Requisitos previos
La tabla siguiente muestra los requisitos previos que deben cumplirse antes de comenzar.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Categoría</th>
<th>Requisito previo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Configuración:</strong> Entidad legal</td>
<td>La dirección principal de la entidad jurídica debe estar en un estado miembro de la Unión Europea. En la página <strong>Entidades legales</strong> (haga clic en <strong>Administración de organizaciones</strong> &gt; <strong>Organizaciones</strong> &gt; <strong>Entidades jurídicas</strong>), seleccione la entidad jurídica. En la ficha desplegable <strong>Direcciones</strong>, cree una dirección, seleccione un país o región y otros componentes de la dirección y marque la dirección como <strong>Principal</strong>. En la ficha desplegable <strong>Registrar impuestos</strong>, en el campo <strong>Número de registro de impuestos</strong>, especifique el número de registro de impuestos de la empresa.</td>
</tr>
<tr class="even">
<td><strong>Configuración:</strong> parámetros de identificación de exención de impuestos</td>
<td>Configure los parámetros de identificación fiscal en la página <strong>Parámetros de país o región</strong> (haga clic en <strong>Impuestos</strong> &gt; <strong>Configuración</strong> &gt; <strong>Impuestos</strong> &gt; <strong>Parámetros de país o región</strong>). Para cada país o región donde tiene contrapartidas, cree un registro en la página y especifique la información siguiente:
<ul>
<li><strong>País o región:</strong> seleccione un país o una región para asociarla con una identificación de exención fiscal.</li>
<li><strong>Impuestos:</strong> indique el número de identificación de exención de impuestos (es decir, el prefijo del número de identificación fiscal) para el país o la región seleccionada.</li>
<li><strong>Comprobar el número de exención de impuestos:</strong> seleccione esta casilla para validar la identificación de exención fiscal para el país o la región seleccionada.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Configuración: </strong>números de exención fiscal</td>
<td>Cree los números de identificación fiscal (NIF) para las contrapartidas en la página <strong>Números de identificación fiscal</strong> (haga clic en <strong>Impuestos</strong> &gt; <strong>Configuracion</strong> &gt; <strong>Impuestos</strong> &gt; <strong>Números de identificación fiscal</strong>). Para cada número de identificación fiscal (NIF), cree un registro en la página y especifique la información siguiente:
<ul>
<li><strong>País o región: </strong>–seleccione el país o la región de registro de impuestos de la contrapartida.</li>
<li><strong>número de identificación fiscal (NIF):</strong> indique el número de identificación fiscal (NIF) de la contrapartida.</li>
<li><strong>Nombre de la empresa:</strong> (Opcional) escriba el nombre de la contrapartida.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Configuración: </strong>Registro de impuestos de contrapartidas</td>
<td>Configure la información de registro de impuestos para las contrapartidas en la página <strong>Todos los clientes</strong> (haga clic en <strong>Ventas y marketing</strong> &gt; <strong>Clientes</strong> &gt; <strong>Todos los clientes</strong>, seleccione un registro de cliente y luego haga clic en la página <strong>Opciones</strong> &gt; <strong>Cambiar visualización</strong> &gt; <strong>Visualización de detalles</strong>) o la página <strong>Proveedores</strong> (haga clic en <strong>Adquisición y abastecimiento</strong> &gt; <strong>Proveedores</strong> &gt; <strong>Proveedores</strong>, seleccione un registro de proveedor y, a continuación, <strong>Opciones</strong> &gt; <strong>Cambiar visualización</strong> &gt; <strong>Visualización de detalles</strong>). En la ficha desplegable <strong>Factura y entrega</strong>, en el campo <strong>Número de identificación fiscal</strong>, seleccione el número de registro de impuestos.</td>
</tr>
<tr class="odd">
<td><strong>Configuración: </strong>impuestos</td>
<td>Configure los impuestos que se van a incluir en el informe <strong>Lista de ventas de la UE</strong> en la página <strong>Códigos de impuestos</strong> (haga clic en <strong>Impuestos</strong> &gt; <strong>Impuestos indirectos</strong> &gt; <strong>Impuestos</strong> &gt; <strong>Códigos de impuestos</strong>). En la ficha desplegable <strong>Configuración de informes</strong> para cada código de impuestos que se debe incluir en el informe, desactive la casilla <strong>Excluído</strong>. Configure los parámetros de impuestos para los artículos en la página <strong>Grupos de impuestos de artículos</strong> (haga clic en <strong>Impuestos</strong> &gt; <strong>Impuestos indirectos</strong> &gt; <strong>Impuestos</strong> &gt; <strong>Grupos de impuestos de artículos</strong>). Para cada grupo de impuestos de artículos, seleccione un valor en el campo <strong>Tipo de notificación</strong>. El valor que seleccione determina la columna de ESL del importe donde se incluirá el importe de línea.
<ul>
<li><strong>En blanco</strong>: el importe de la línea de impuestos se incluye en la columna <strong>Valor no asignado</strong>.</li>
<li><strong>Artículo</strong>: el importe de la línea de impuestos se incluye en la columna <strong>Valor de los artículos</strong>.</li>
<li><strong>Servicio</strong>: el importe de la línea de impuestos se incluye en la columna <strong>Valor de los servicios</strong>.</li>
<li><strong>Inversión</strong>: el importe de la línea de impuestos se incluye en la columna <strong>Valor de la inversión</strong>. Esta columna solo es relevante para Bélgica.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Configuración:</strong> configuraciones de informes de ESL</td>
<td>Importar o crear configuraciones de informes electrónicos para el ESL. Para obtener información sobre cómo crear y mantener configuraciones de notificaciones electrónicas, vea la documentación de notificaciones electrónicas.</td>
</tr>
<tr class="odd">
<td><strong>Configuración: </strong>parámetros generales</td>
<td>Configure los parámetros de notificación de ESL en la página <strong>Parámetros de comercio exterior</strong> (haga clic en <strong>Impuestos</strong> &gt; <strong>Configuración</strong> &gt; <strong>Comercio exterior</strong> &gt; <strong>Parámetros de comercio exterior</strong>). Especifique los parámetros siguientes:
<ul>
<li>Separador <strong>Lista de ventas de la UE</strong>:
<ul>
<li><strong>Notificar descuento por pronto pago</strong>: seleccione esta casilla si el descuento por pronto pago se incluye en el valor cuando una transacción se incluye en el ESL.</li>
<li><strong>Transferir compras</strong>: seleccione esta casilla para incluir compras en el ESL.</li>
<li><strong>Asignación de formato de archivo</strong>: seleccione el formato de notificación electrónica que se debe usar cuando un archivo electrónico se genera para el ESL.</li>
<li><strong>Asignación de formato de informe</strong>: seleccione el formato de notificación electrónica que se debe usar cuando un informe de vista previa se genera para el ESL.</li>
<li><strong>Regla de redondeo</strong>: especifique un número real que se usará para redondear. Los importes de ESL se redondearán a los múltiplos de este número.</li>
<li><strong>Método de redondeo</strong>: seleccione el método de redondeo que se usará cuando se redondean los importes de ESL (<strong>Normal</strong><strong>Bajo</strong> o <strong>Redondeo hacia arriba</strong>).</li>
<li><strong>Usar el valor mínimo</strong>: seleccione esta casilla si desea redondear los importes que sean inferiores a la <strong>Regla de redondeo</strong> al número de <strong>Regla de redondeo</strong>.</li>
<li><strong>Número de decimales</strong>: especifica el número de decimales que se muestra en importes de ESL (en los archivos electrónicos y en el informe <strong>Vista previa del ESL</strong>).</li>
</ul></li>
<li>Separador <strong>Parámetros de país o región</strong>: identifica los estados miembros de la UE. Para cada estado miembro de la UE, cree un registro en la página y especifique la información siguiente:
<ul>
<li><strong>País o región</strong>: seleccione un país o una región.</li>
<li><strong>Tipo de país o región</strong>: Si el valor <strong>País o región</strong> es el país o región en el que está registrada su empresa, seleccione <strong>Nacional</strong>. Si el valor <strong>País o región</strong> es un estado miembro de la UE distinto al país o región en el que está registrada su empresa, seleccione <strong>EU</strong>. Si el valor <strong>País o región</strong> no es un estado miembro de la UE, seleccione <strong>Otro país o región</strong>.</li>
</ul></li>
<li>Separador <strong>Secuencias numéricas</strong>: en la línea donde el valor <strong>Referencia</strong> es <strong>Lista de ventas de la UE</strong>, seleccione un código de secuencia numérica.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Transacciones relacionadas</strong></td>
<td><ul>
<li>Registre una venta a un cliente en otro estado miembro de la UE.</li>
<li>Registre una factura de servicios para un cliente en otro estado miembro de la UE.</li>
<li>Registre una factura de proyecto para un cliente en otro estado miembro de la UE.</li>
<li>Registre una factura de un proveedor para un cliente en otro estado miembro de la UE.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="working-with-the-esl"></a>Trabajo con el ESL
### <a name="collecting-information-about-intra-community-trade-transactions"></a>Recopilar información acerca de transacciones de comercio intracomunitario

Las transacciones de los siguientes tipos se pueden considerar las transacciones comerciales intracomunitario:

-   Facturas de ventas
-   Facturas de servicios
-   Facturas del proyecto
-   Facturas de proveedores

Una transacción se considera una transacción de comercio intracomunitario si la dirección de entrega de la transacción está en un estado miembros de la UE. Para dichos países o regiones, un registro debe existir en el separador **Parámetros de país o región** de la página **Parámetros de comercio exterior**, y el valor **Tipo de país o región** debe establecerse en **UE**. Las transacciones comerciales intracomunitarias se marcan en el campo **Código de lista**. Mediante este campo, también puede separar transacciones generales de comercio intracomunitario de transacciones comerciales triangulares. Puede recopilar información sobre transacciones comerciales intracomunitarias en la página **Lista de ventas de la UE** (haga clic en **Impuestos** &gt; **Declaraciones** &gt; **Comercio exterior** &gt; **Lista de ventas de la UE**) mediante la función **Transferencia**. Esta función le permite incluir las transacciones que tienen importes de los distintos tipos de informes (es decir, los artículos o servicios), según los grupos de impuestos de artículos que se especifican en las líneas de transacción. También puede aplicar otros filtros para definir las transacciones que se deben incluir. La función **Transferencia** crea un registro en la página **Lista de ventas de la UE** para cada transacción de comercio intracomunitario incluida, y se especifica un número de cuenta de contrapartida, un país o región, un número de identificación fiscal (NIF), el número de factura y una fecha, y los importes totales de líneas por tipo de notificación. También copia el valor **Código de lista** de la transacción. Puede cambiar manualmente el código de lista para una transacción en la página **Lista de ventas de la UE**. La función **Transferencia** crea registros donde el valor **Estado de notificación** está establecido en **Incluido**. Puede validar la información que se recopila en la página **Lista de ventas de la UE**mediante la función **Validar**.

### <a name="generating-the-eu-sales-list-report"></a>Generar el informe Lista de ventas de la UE

Puede generar un informe **Lista de ventas de la UE** mediante la función **Notificaciones**en la página **Lista de ventas de la UE**. La función le permite seleccionar un período de notificación y aplicar filtros para definir los registros de ESL que desea incluir. Además, puede especificar otros parámetros que son específicos de cada país o región. También puede elegir generar un informe de cliente potencial, un archivo electrónico o ambos. La función **Notificaciones**usa la configuración del informe y el formato de archivo que se especifican en la página **Parámetros de comercio exterior**. Un informe de **Lista de ventas de la UE** consta normalmente de líneas independientes que enumeran los importes totales de los suministros por país o región de contrapartida, el número de identificación fiscal (NIF) y el tipo de informe (las transacciones comerciales triangulares se incluyen). Después de generar un informe de **Lista de ventas de la UE** para un período específico, puede marcar los registros de ESL que se incluirán en el informe configurando el valor **Estado de notificación** a **Notificado**. Para establecer este estado, use la función **Marcar como notificado**en la página **Lista de ventas de la UE**.

### <a name="closing-the-eu-sales-list-reporting-period"></a>Cerrar el período de notificación de la lista de ventas de la UE

Cuando haya completado el proceso de notificación para un período específico (por ejemplo, cuando las autoridades fiscales han aceptado el informe **Lista de ventas de la UE**), puede marcar los registros de ESL en los que se incluirá el informe para el período configurando el valor **Estado de notificación** a **Cerrado**. Para establecer este estado, use la función **Marcar scomo cerrado**en la página **Lista de ventas de la UE**. Si invierte el cierre del período, puede marcar los registros de ESL configurando el valor **Estado de notificación** a **Incluido**. Estos registros pueden después incluirse en el informe **Lista de ventas de la UE** de nuevo. Para establecer este estado, use la función **Marcar como** **incluido**en la página **Lista de ventas de la UE**.




