---
title: "Versión 3.3 del diseño CFDI"
description: "Este tema proporciona información sobre la versión 3.3 del diseño Comprobante Fiscal Digital por Internet (CFDI) para México."
author: sndray
manager: AnnBe
ms.date: 01/03/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustPosting, VendParameters
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2017-12-01
ms.translationtype: HT
ms.sourcegitcommit: 95d5bf26c22238753586cf4a7aaf5c26f061a705
ms.openlocfilehash: 49e56b953b14aaf1c71caf2ab935e917f97fc4c5
ms.contentlocale: es-es
ms.lasthandoff: 02/23/2018

---

# <a name="cfdi-layout-version-33"></a>Versión 3.3 del diseño CFDI

[!include[banner](../includes/banner.md)]

## <a name="electronic-invoice-parameters"></a>Parámetros de facturas electrónicas

Si su organización utiliza facturas electrónicas que son validadas y certificadas por un proveedor de servicios de firma digital de terceros (PAC), habilite la facturación electrónica mediante los campos del área **CFDI** de la página **Parámetros de factura electrónica**.

Los siguientes cambios se introducen en la versión 3.3 del diseño Comprobante Fiscal Digital por Internet (CFDI):

- **Versión CFDI:** ahora está disponible la versión 3.3.
- **Algoritmo de codificación de CFDI:** SHA-256.
- **Archivo de esquema XML de pago de CFDI:** la ruta y el nombre del archivo de esquema que se usa para validar el complemento de pago de CFDI.
- **Límites del importe total:** especifica los límites del importe total de entrada y salida que requieren un número de confirmación.
- **Códigos de clasificación predeterminados del gobierno:**

    - **Código de producto SAT:** use esta clasificación para los escenarios donde no se identifica el código de artículo.
    - **Código de unidad SAT:** use esta clasificación para los escenarios donde no se identifica la unidad de medida.

## <a name="sat-catalogs"></a>Catálogos SAT

<table>
<thead>
<tr>
<th>Catálogo SAT</th>
<th>Asignación de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition</th>
</tr>
</thead>
<tbody>
<tr>
<td>cUsoCFDI</td>
<td>Seleccione <strong>Administración de la organización</strong> &gt; <strong>Configuración</strong> &gt; <strong>Factura electrónica</strong> &gt; <strong>Clasificaciones SAT</strong> &gt; <strong>Propósito de CFDI</strong> para especificar la lista de clasificaciones de propósito de CFDI definidas por el gobierno. Puede especificar la siguiente información: la clasificación de códigos de las autoridades fiscales mexicanas (SAT), la descripción, la versión vigente y la fecha de vencimiento.

Esta información debe especificarse en el campo <strong>Propósito de CFDI</strong> en el encabezado de transacción de la factura de ventas. También puede definir un propósito de CFDI predeterminado por cliente seleccionando <strong>Clientes</strong> y mediante la opción <strong>Factura y entrega</strong>.</td>
</tr>
<tr>
<td>c_Aduana</td>
<td>No aplicable</td>
</tr>
<tr>
<td>c_ClaveProdServ</td>
<td>Seleccione <strong>Administración de la organización</strong> &gt; <strong>Configuración</strong> &gt; <strong>Factura electrónica</strong> &gt; <strong>Clasificaciones SAT</strong> &gt; <strong>Producto y servicios</strong> para especificar la lista de clasificaciones de códigos de artículos definidas por el gobierno. Puede especificar la siguiente información: la clasificación de códigos SAT, la descripción, la versión vigente y la fecha de vencimiento.

Una vez que se cree o se actualice la lista, puede asignar la clasificación relacionada en los datos maestros siguientes:
<ul>
<li><strong>Parámetros de facturas electrónicas</strong> en clasificaciones predeterminadas</li>
<li><strong>Información del producto</strong> &gt; <strong>Productos emitidos</strong> &gt; <strong>General</strong> &gt; <strong>Facturas electrónicas</strong></li>
<li><strong>Clientes</strong> &gt; <strong>Configuración</strong> &gt; <strong>Gastos</strong> &gt; <strong>Código de gastos</strong></li>
</ul>
</td>
</tr>
<tr>
<td>c_ClaveUnidad</td>
<td>Seleccione <strong>Administración de la organización</strong> &gt; <strong>Configuración</strong> &gt; <strong>Factura electrónica</strong> &gt; <strong>Clasificaciones SAT</strong> &gt; <strong>Unidad de medida</strong> para especificar la lista de clasificaciones de unidad de medida definidas por el gobierno. Puede especificar la siguiente información: la clasificación de códigos SAT, la descripción, la versión vigente y la fecha de vencimiento.

Una vez que se cree o se actualice la lista, puede asignar la clasificación relacionada en los datos maestros siguientes:
<ul>
<li><strong>Administración de la organización</strong> &gt; <strong>Configuración</strong> &gt; <strong>Unidades</strong> &gt; <strong>Unidades</strong> &gt; <strong>Facturas electrónicas</strong></li>
</ul>
</td>
</tr>
<tr>
<td>c_CodigoPostal</td>
<td>Esta información se identifica mediante el código postal en el código de dirección del cliente, la empresa u otra dirección relacionada.</td>
</tr>
<tr>
<td>c_FormaPago</td>
<td>Se utiliza la información existente en <strong>Clientes</strong> &gt; <strong>Configuración</strong> &gt; <strong>Pago</strong> &gt; <strong>Forma de pago</strong> &gt; <strong>Pago SAT</strong>.</td>
</tr>
<tr>
<td>c_Impuesto</td>
<td>Esta información se determina mediante el valor <strong>Tipo de impuesto</strong> en la configuración del código de impuestos.</td>
</tr>
<tr>
<td>c_MetodoPago</td>
<td>Seleccione <strong>Administración de la organización</strong> &gt; <strong>Configuración</strong> &gt; <strong>Factura electrónica</strong> &gt; <strong>Clasificaciones SAT</strong> &gt; <strong>Forma de pago</strong> para especificar la lista de formas de pago definidas por el gobierno.

Esta información debe especificarse en el campo <strong>Tipo de pago</strong> en el encabezado de transacción de la factura de ventas. También puede definir el tipo de pago predeterminado por cliente seleccionando <strong>Clientes</strong> y mediante la opción <strong>Factura y entrega</strong>.</td>
</tr>
<tr>
<td>cMoneda</td>
<td>Esta información se identifica mediante el valor <strong>Código de divisa</strong> que se configura en Finance and Operations.

El gobierno define la variación del tipo de cambio que se permite. Este valor debe configurarse en <strong>Contabilidad general</strong> &gt; <strong>Configuración</strong> &gt; <strong>Divisas</strong> &gt; <strong>Facturas electrónicas</strong>. Puede especificar el valor <strong>Límite de variación de tipo de cambio</strong> por divisa.</td>
</tr>
<tr>
<td>c_NumPedimentoAduana</td>
<td>Se utiliza la información existente en el campo <strong>Número personalizado</strong> en la línea de transacción de la factura de ventas.</td>
</tr>
<tr>
<td>cPais</td>
<td>Esta información se identifica mediante el valor <strong>Código de país</strong> que se configura en Finance and Operations.</td>
</tr>
<tr>
<td>c_PatenteAduanal</td>
<td>No aplicable</td>
</tr>
<tr>
<td>cRegimenFiscal</td>
<td>Seleccione <strong>Administración de la organización</strong> &gt; <strong>Configuración</strong> &gt; <strong>Factura electrónica</strong> &gt; <strong>Clasificaciones SAT</strong> &gt; <strong>Régimen de impuestos</strong> para especificar la lista de clasificaciones de régimen de impuestos definidas por el gobierno. Puede especificar la siguiente información: la clasificación de códigos SAT, la descripción, la versión vigente y la fecha de vencimiento.

Una vez que se cree o se actualice la lista, puede asignar la clasificación relacionada en los datos maestros siguientes:
<ul>
<li>Selecciones <strong>Administración de la organización</strong> &gt; <strong>Configuración</strong> &gt; <strong>Organización</strong> &gt; <strong>Entidades jurídicas</strong> &gt; <strong>Registro de impuestos</strong>. A continuación, puede seleccionar el régimen de impuestos.</li>
</ul>
</td>
</tr>
<tr>
<td>cTasaCuota</td>
<td>Esta información se determina mediante el valor <strong>Tipo de impuesto</strong> en la configuración del código de impuestos.</td>
</tr>
<tr>
<td>cTipodeComprobante</td>
<td>Esta información se determina por el tipo de transacción de la factura de ventas. Se admiten los siguientes tipos para esta función:
<ul>
<li>Entrante</li>
<li>Saliente</li>
<li>Pago</li>
</ul>
</td>
</tr>
<tr>
<td>cTipoFactor</td>
<td>Esta información se determina mediante el valor <strong>Tipo de impuesto</strong> en la configuración del código de impuestos.

La configuración del código de impuestos identifica el tipo <strong>Exento</strong> como <strong>índice de impuestos = 0.00</strong> y <strong>tipo de impuestos = IVA</strong>. Identifica el tipo <strong>TASA</strong> como <strong>tasa fiscal &lt;&gt; 0.00</strong>.</td>
</tr>
<tr>
<td>cTipoRelacion</td>
<td>Se ha implementado la nueva funcionalidad de referencia CFDI que permite a los usuarios identificar los distintos tipos de relaciones entre los documentos de CFDI. Algunos de estos tipos de relación se asignan automáticamente. Los usuarios pueden seleccionar manualmente otros tipos de relación en escenarios específicos.</td>
</tr>
</tbody>
</table>

## <a name="cfdi-reference"></a>Referencia CFDI

Según el requisito legal, los usuarios deben poder hacer referencia a una o varias facturas CFDI relacionadas en escenarios específicos. Por ejemplo, es posible que un cliente devuelva artículos si recibió los artículos incorrectos o si un artículo era defectuoso. A continuación, debe crear un pedido de devolución, identificar la factura de ventas original que se envió, e identificar el tipo de relación (**cTipoRelacion**) definido por el gobierno. En este caso, la relación es **03: Devolución de mercancías**.

Antes de registrar una factura de ventas, puede hacer referencia a la factura CFDI relacionada en **Registrar** &gt; **Configuración** &gt; **Referencia CFDI**.

Puede seleccionar la lista de facturas CFDI disponible que se han aprobado, o puede introducir la siguiente información:

- Identificador único universal (UUID)
- Tipo de relación

Cuando se genera un complemento de pago de CFDI, esta funcionalidad también está disponible en **Diarios de pagos** &gt; **Referencia CFDI**. 

La siguiente información describe cómo se genera un complemento de pago de CFDI cuando se obtiene el pago de un cliente y se aplica a un documento existente de factura CFDI.

Los complementos de pago CFDI se generan del diario de pagos y del proceso de liquidación bajo las siguientes condiciones:

- El diario de pago se liquida con una o más facturas.
- La liquidación del diario se liquida con una o más facturas.
- En la definición del nombre del diario, el tipo de diario se establece en **Pago de cliente**.

Una vez registrado el pago del diario o la liquidación del diario, el proceso por lotes de exportación/importación se ejecuta para obtener la aprobación relacionada de PAC (software de terceros).

Se requiere la siguiente información adicional para el pago de diarios, en función del método de pago que se seleccione:

- Cuenta principal de contrapartida.
- Cuenta bancaria de cliente tercero.
- Cuenta bancaria de cliente del Registro Federal de Contribuyentes (RFC). Se ha agregado un nuevo campo a la página **Cuenta bancaria de cliente** para cumplir los requisitos legales establecidos por las autoridades fiscales.

En función de la solicitud de un cliente, puede usar la consulta de la factura electrónica CFDI para ver, enviar por correo electrónico, exportar o imprimir un complemento de pago de CFDI que se generó anteriormente. Selecione **Clientes** &gt; **Consultas e informes** &gt; **CFDI (facturas electrónicas)** y, a continuación, seleccione la pestaña **Pago**. La factura electrónica CFDI impresa incluye un código de barras bidimensional de acuerdo con el formato para códigos de respuesta rápida (códigos QR) que se describe en la norma 18004 de la Organización Internacional de Normalización (ISO)/Comisión Electrotécnica Internacional (IEC).

## <a name="customer-advance-payments"></a>Anticipos del cliente

Esta sección describe el procesamiento y la configuración de un anticipo del cliente para poder generar y emitir una factura electrónica CFDI. Según la definición del gobierno, debe seguirse un procedimiento específico cuando se obtengan anticipos de clientes.

1. **Anticipo de CFDI:** se emite una factura electrónica al cliente para el importe del anticipo que se recibió.
2. **Factura CFDI:** una vez que se realice la operación y se aplique el anticipo, la empresa debe emitir la factura CFDI de la operación y los detalles del UUID del anticipo de CFDI que se emitió en el paso 1.
3. **Inversión del anticipo de CFDI:** se emite una factura electrónica para invertir el anticipo que se aplicó.

![Proceso de anticipo](./media/mex-advance-payments-cfdi.png "Diagrama que muestra el proceso de anticipo")

## <a name="prerequisites"></a>Requisitos previos

Use la funcionalidad para asientos del diario de anticipos para emitir un anticipo de CFDI. Antes de poder enviar el anticipo, debe completar los siguientes requisitos previos.

1. Seleccione **Clientes** &gt; **Configuración** &gt; **Perfiles de contabilización del cliente**, y cree un perfil de contabilización para anticipos.
2. Seleccione **Clientes** &gt; **Configuración** &gt; **Parámetros de clientes** &gt; **Impuestos y contabilidad** &gt; **Pago**, y siga estos pasos:

    1. Seleccione el perfil de contabilización que creó anteriormente.
    2. Si los impuestos se calculan y se registran cuando se registra un asiento de diario de anticipo, seleccione la casilla de verificación **Impuestos sobre el asiento del diario de anticipos**.

## <a name="step-1-issue-a-cfdi-advance-payment"></a>Paso 1: Emitir un anticipo de CFDI

1. Seleccione **Clientes** &gt; **Diarios** &gt; **Pagos** &gt; **Diario de pagos** para crear el anticipo.
2. Especifique las líneas y la información relacionada. Incluya la forma de pago y los códigos de impuestos como corresponda.
3. En la pestaña **Pago** , seleccione la casilla de verificación **Asiento del diario de anticipos** .
4. Registre el anticipo.
5. Seleccione **Clientes** &gt; **Periódico** &gt; **Facturas electrónicas CFDI** &gt; **Proceso de exportar/importar factura electrónica** para solicitar el sello digital del anticipo de CFDI.
6. Seleccione **Clientes** &gt; **Consulta** &gt; **Diarios** &gt; **Facturas electrónicas FDI**, y seleccione la pestaña **Pago** para consultar el estado del anticipo de CFDI. Esta transacción se clasifica en el campo **Información del tipo de documento** como **Anticipo**.

    > [!NOTE]
    > Los siguientes criterios se utilizan para identificar las transacciones de anticipo de CFDI en el sistema:
    >
    > - El tipo de nombre del diario se establece en **Pago de cliente**.
    > - Se selecciona la casilla de verificación **Asiento del diario de anticipos**.
    > 
    > Cualquier transacción de pago que no cumpla estos criterios se considera un pago habitual.

## <a name="step-2-issue-a-cfdi-invoice-together-with-details-of-the-advance-payment-that-was-applied"></a>Paso 2: Emitir una factura CFDI junto con los detalles del anticipo que se aplicó

1. Cree una transacción de factura de ventas.
2. Antes de registrar la factura, puede establecer el anticipo que creó en el [Paso 1: Emitir un anticipo de CFDI](#step-1-issue-a-cfdi-advance-payment). Para liquidar el anticipo, utilice la opción **Liquidación de transacción abierta** .
3. En la página **Registrar**, puede verificar la factura CFDI a la que se hace referencia. La factura se crea automáticamente y el tipo de relación (**cTipoRelacion**) se establece en **07**.
4. Registre la factura de ventas.

    > [!NOTE]
    > A partir de la publicación, el gobierno no ha actualizado el esquema para habilitar que **cTipoRelacion** que se establezca en **07**. Si recibe un mensaje de error durante la validación de esquemas, puede seleccionar manualmente **01: Nota de abono** para resolver el problema.

## <a name="step-3-issue-a-cfdi-advance-payment-reverse"></a>Paso 3: Emitir una inversión de anticipo de CFDI

Una vez que la empresa emite una factura CFDI por el importe total de la operación, debe enviar una inversión de anticipo de CFDI (Egreso) para el anticipo que se liquidó. Esta inversión de anticipo de CFDI se genera automáticamente cuando recibe la aprobación de la factura CFDI que generó en el [Paso 2: Emitir una factura CFDI junto con los detalles del anticipo que se aplicó](#step-2-issue-a-cfdi-invoice-together-with-details-of-the-advance-payment-that-was-applied).

En función de la solicitud de un cliente, puede usar la consulta de la factura electrónica CFDI para ver, enviar por correo electrónico, exportar o imprimir un complemento de pago de CFDI que se generó anteriormente. Selecione **Clientes** &gt; **Consultas e informes** &gt; **CFDI (facturas electrónicas)** y, a continuación, seleccione la pestaña **Pago**. La factura electrónica CFDI impresa incluye un código de barras bidimensional de acuerdo con el formato para códigos QR que se describe en la norma 18004 ISO/IEC.

Los anticipos de CFDI se identifican mediante un tipo de documento de **Anticipo**.

## <a name="confirmation-number"></a>Número de confirmación

Se requiere el número de confirmación en una factura CFDI cuando el importe total de la factura o la variación de tipo de cambio se encuentre fuera de los límites que ha establecido el gobierno. En esta situación, puede especificar la confirmación necesaria de dos maneras:

- Si la empresa sabe que se han superado los límites, puede incluir el código de confirmación en el encabezado de transacción de la factura de ventas.
- Si recibe un rechazo de PAC porque se han superado los límites, puede establecer el código de confirmación para el proceso de aprobación en **Consulta de factura electrónica CFDI** &gt; **Funciones** &gt; **Establecer código de autorización y Volver a enviar**.

