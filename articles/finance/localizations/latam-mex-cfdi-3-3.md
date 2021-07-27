---
title: Versión 3.3 del diseño CFDI
description: Este tema proporciona información sobre la versión 3.3 del diseño Comprobante Fiscal Digital por Internet (CFDI) para México.
author: sndray
ms.date: 10/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, VendParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2017-12-01
ms.openlocfilehash: 4dec8d083b3bf9d75a9747130e80211ed265f682
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6359697"
---
# <a name="cfdi-layout-version-33"></a>Versión 3.3 del diseño CFDI

[!include [banner](../includes/banner.md)]

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
    
#### <a name="cfdi-foreign-trade-parameters"></a>Parámetros de comercio exterior CFDI

Si su organización usa las facturas electrónicas para el negocio de comercio exterior (CFDI), habilite la siguiente información en el área de comercio exterior de CFDI de la página **Parámetros de factura electrónica**:

- **Tipo de operación:** Seleccionar **Exportar**.
- **Versión de CFDI:** Seleccione la versión 1.1.
- **Divisa de notificación:** Seleccione el código de divisa que representa el dólar estadounidense, ya que el complemento extranjero debe expresarse en esta divisa.
- **Archivo de esquema XML del comercio exterior de CFDI:** Seleccione la ruta y el archivo de esquema para validar el complemento del comercio exterior de CFDI.
- **Marcar:** Este campo para especificar el marcado de las situaciones en las que no identifican el producto o servicio como código de artículo Dynamics 365 Finance.

#### <a name="cfdi-withholding-parameters"></a>Parámetros de retención de CFDI
Si su organización utiliza documentos de retención de facturas electrónicas que son validadas y certificadas por un proveedor de servicios de firma digital de terceros (PAC), habilite la facturación electrónica mediante los campos del área **Retención CFDI** y **Secuencias numéricas** de la página **Parámetros de factura electrónica**.

- **Habilitar retención CFDI:** Seleccione **Sí** para habilitar la generación de retención CFDI.
- **Archivo XSLT de CDFI:** ruta y archivo de esquema para validar el documento de retención de CFDI.
- **Algoritmo de codificación de CFDI:** SHA-256.
- **Archivo XML de esquema CFDI:** ruta y archivo de esquema para validar el documento de retención de CFDI.
- **Enviar correo:** Seleccionar **Sí** para activar la acción para enviar mensajes de correo electrónico con el archivo XML de retención de CFDI adjunto.
- **Identificador de correo electrónico:** Seleccione la plantilla del identificador de correo electrónico.
- **Secuencias numéricas:** Seleccione el código de secuencia numérica utilizado para los diarios de retención.

## <a name="sat-catalogs"></a>Catálogos SAT

<table>
<thead>
<tr>
<th>Catálogo SAT</th>
<th>Asignación de Dynamics 365 Finance</th>
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
<td>c_Moneda</td>
<td>Esta información se identifica mediante el valor <strong>Código de divisa</strong> que se configura en Finance.

El gobierno define la variación del tipo de cambio que se permite. Este valor debe configurarse en <strong>Contabilidad general</strong> &gt; <strong>Configuración</strong> &gt; <strong>Divisas</strong> &gt; <strong>Facturas electrónicas</strong>. Puede especificar el valor <strong>Límite de variación de tipo de cambio</strong> por divisa.</td>
</tr>
<tr>
<td>c_NumPedimentoAduana</td>
<td>Se utiliza la información existente en el campo <strong>Número personalizado</strong> en la línea de transacción de la factura de ventas.</td>
</tr>
<tr>
<td>c_Pais</td>
<td>Esta información se identifica mediante el valor <strong>Código de país</strong> que se configura en Finance.</td>
</tr>
<tr>
<td>c_PatenteAduanal</td>
<td>No aplicable</td>
</tr>
<tr>
<td>c_RegimenFiscal</td>
<td>Seleccione <strong>Administración de la organización</strong> &gt; <strong>Configuración</strong> &gt; <strong>Factura electrónica</strong> &gt; <strong>Clasificaciones SAT</strong> &gt; <strong>Régimen de impuestos</strong> para especificar la lista de clasificaciones de régimen de impuestos definidas por el gobierno. Puede especificar la siguiente información: la clasificación de códigos SAT, la descripción, la versión vigente y la fecha de vencimiento.

Una vez que se cree o se actualice la lista, puede asignar la clasificación relacionada en los datos maestros siguientes:
<ul>
<li>Selecciones <strong>Administración de la organización</strong> &gt; <strong>Configuración</strong> &gt; <strong>Organización</strong> &gt; <strong>Entidades jurídicas</strong> &gt; <strong>Registro de impuestos</strong>. A continuación, puede seleccionar el régimen de impuestos.</li>
</ul>
</td>
</tr>
<tr>
<td>c_TasaCuota</td>
<td>Esta información se determina mediante el valor <strong>Tipo de impuesto</strong> en la configuración del código de impuestos.</td>
</tr>
<tr>
<td>c_TipodeComprobante</td>
<td>Esta información se determina por el tipo de transacción de la factura de ventas. Se admiten los siguientes tipos para esta función:
<ul>
<li>Entrante</li>
<li>Saliente</li>
<li>Pago</li>
</ul>
</td>
</tr>
<tr>
<td>c_TipoFactor</td>
<td>Esta información se determina mediante el valor <strong>Tipo de impuesto</strong> en la configuración del código de impuestos.

La configuración del código de impuestos identifica el tipo <strong>Exento</strong> como <strong>índice de impuestos = 0.00</strong> y <strong>tipo de impuestos = IVA</strong>. Identifica el tipo <strong>TASA</strong> como <strong>tasa fiscal &lt;&gt; 0.00</strong>.</td>
</tr>
<tr>
<td>c_TipoRelacion</td>
<td>Se ha implementado la nueva funcionalidad de referencia CFDI que permite a los usuarios identificar los distintos tipos de relaciones entre los documentos de CFDI. Algunos de estos tipos de relación se asignan automáticamente. Los usuarios pueden seleccionar manualmente otros tipos de relación en escenarios específicos.</td>
</tr>
<tr>    
<td>c_Incoterm</td>
<td><strong>Administración de la organización > Configuración > Factura electrónica > Clasificaciones SAT > Incoterm</strong> para introducir la lista de clasificaciones de incoterm definidas por el gobierno. El usuario podrá introducir la siguiente información: la clasificación de códigos SAT, la descripción, la versión vigente y la fecha de vencimiento. Una vez que se cree o se actualice la lista, el usuario puede asignar la clasificación relacionada en los datos maestros siguientes:
<ul>
<li>Parámetros de facturas electrónicas en clasificaciones predeterminadas. Se usa para la factura de proyecto y propuestas que no se generan de pedidos de ventas.
    <li><strong>Información del producto > Productos emitidos > General > Facturas electrónicas</strong></li>
    <li><strong>Efectos a cobrar de la cuenta > Pedidos de ventas y devoluciones </strong> > Encabezado de los pedidos de ventas</strong></li>
    <li><strong>Cobros de la cuenta > Factura de servicios > Encabezado de todas las facturas de servicios</strong> </li>
</ul>
</tr>
<tr>
<td> c_TipoOperation</td>
<td> El único valor disponible es <strong>Exportacion</strong> (exportación), que se selecciona desde la página <strong>Parámetros de factura electrónica</strong>. </td>
</tr>
<tr>
    <td>c_Brand </td>
    <td><strong>Administración de información de producto > Configuración > Marca</strong>, para especificar el código de marcado. El usuario podrá especificar el código y la descripción de marcado. </td>
</tr>
<tr>
    <td> c_FraccionArancelaria </td>
    <td> <strong>Administración de la organización > Configuración > Factura electrónica > Clasificaciones SAT > Fracción de tarifa</strong> para introducir la lista de clasificaciones de fracción de tarifa definidas por el gobierno. El usuario podrá introducir la siguiente información: la clasificación de códigos SAT, la descripción, la versión vigente y la fecha de vencimiento. Una vez que se cree o se actualice la lista, el usuario podrá seleccionar la fracción de la tarifa en el nivel de línea en una línea de pedido de ventas, una línea de factura de servicios, y una factura de proyecto. </td>
</tr>
<tr>
    <td> c_UnidadAduana </td>
    <td> <strong>Administración de la organización > Configuración > Factura electrónica > Clasificaciones SAT > Unidad de medida personalizada</strong>, para especificar la lista personalizada de clasificaciones de unidad de medida definidas por el gobierno. El usuario podrá introducir la siguiente información: la clasificación de códigos SAT, la descripción, la versión vigente y la fecha de vencimiento. Una vez que se cree o se actualice la lista, el usuario podrá seleccionar la unidad de medida personalizada en el nivel de línea en una línea de pedido de ventas, una línea de factura de servicios, y una factura de proyecto. </td>
</tr>
<tr>,
<td> c_Retenciones </> <td> <strong> Administración de la organización > Configuración > Factura electrónica > Clasificaciones SAT > Tipo de retención</strong> para introducir las clasificaciones de tipo de retención definidas por el gobierno. El usuario podrá especificar la siguiente información: Código, descripción, y el tipo de de complemento que la retención CFDI va a producir. </td>
</tr>
<tr>
    <td>c_TipoContribuyenteSujetoRetencio </> <td> Esta clasificación se incluye en <strong>Datos maestros de proveedor > factura y entrega </strong>, donde el usuario podrá seleccionar el tipo de contribuyente que estará sujeto a la retención. </td>
</tr>

</tbody>
</table>

## <a name="cfdi-reference"></a>Referencia CFDI

Los usuarios deben poder hacer referencia a una o varias facturas CFDI relacionadas en escenarios específicos. Por ejemplo, es posible que un cliente devuelva un artículo si recibió el incorrecto o si era defectuoso. A continuación, debe crear un pedido de devolución, identificar la factura de ventas original que se envió, e identificar el tipo de relación (**cTipoRelacion**) definido por el gobierno. En este caso, la relación es **03: Devolución de mercancías**.

Antes de registrar una factura de ventas, puede hacer referencia a la factura CFDI relacionada seleccionando **Registrar > Configuración > Referencia CFDI**.

Puede seleccionar la lista de facturas CFDI disponible que se han aprobado, o puede introducir la siguiente información:

- Identificador único universal (UUID)
- Tipo de relación

Cuando se genera un complemento de pago de CFDI, esta funcionalidad también está disponible en **Diarios de pagos > Referencia CFDI**. 

La siguiente información describe cómo se genera un complemento de pago de CFDI cuando se obtiene el pago de un cliente y se aplica a un documento existente de factura CFDI.

Los complementos de pago CFDI se generan del diario de pagos y del proceso de liquidación bajo las siguientes condiciones:

- El diario de pago se liquida con una o más facturas.
- La liquidación del diario se liquida con una o más facturas.
- En la definición del nombre del diario, el tipo de diario se establece en **Pago de cliente**.

Una vez registrado el pago del diario o la liquidación del diario, el proceso por lotes de exportación/importación se ejecuta para obtener la aprobación relacionada de PAC (software de terceros).

Se requiere la siguiente información adicional para el pago de diarios, en función del método de pago que se seleccione:

- Una cuenta principal de contrapartida.
- Una cuenta bancaria de un cliente tercero.
- Una cuenta bancaria de cliente del Registro Federal de Contribuyentes (RFC). Se ha agregado un nuevo campo a la página **Cuenta bancaria de cliente** para cumplir los requisitos legales establecidos por las autoridades fiscales.

En función de la solicitud de un cliente, puede usar la consulta de la factura electrónica CFDI para ver, enviar por correo electrónico, exportar o imprimir un complemento de pago de CFDI que se generó anteriormente. Seleccione **Clientes > Consultas e informes > CFDI (facturas electrónicas)** y, a continuación, seleccione la pestaña **Pago**. La factura electrónica CFDI impresa incluye un código de barras bidimensional de acuerdo con el formato para códigos de respuesta rápida (códigos QR) que se describe en la norma 18004 de la Organización Internacional de Normalización (ISO)/Comisión Electrotécnica Internacional (IEC).

## <a name="customer-advance-payments"></a>Anticipos del cliente

Esta sección describe el procesamiento y la configuración de un anticipo del cliente para poder generar y emitir una factura electrónica CFDI. Según la definición del gobierno, debe seguirse un procedimiento específico cuando se obtengan anticipos de clientes.

1. **Anticipo de CFDI:** se emite una factura electrónica al cliente para el importe del anticipo que se recibió.
2. **Factura CFDI:** una vez que se realice la operación y se aplique el anticipo, la empresa debe emitir la factura CFDI de la operación y los detalles del UUID del anticipo de CFDI que se emitió en el paso 1.
3. **Inversión del anticipo de CFDI:** se emite una factura electrónica para invertir el anticipo que se aplicó.

![Proceso de pago avanzado.](./media/mex-advance-payments-cfdi.png "Diagrama que muestra el proceso de pago por adelantado")

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

## <a name="cfdi-foreign-trade"></a>Comercio exterior CFDI
Al registrar un pedido de ventas, una factura de servicios, una nota de abono, un pedido de devolución, una factura de proyecto, o un pedido de ventas de proyecto como diseño electrónico 3.3 de la factura CFDI de un cliente extranjero, puede generar el complemento 1.1 de comercio exterior introducir la información necesaria siguiente para generar el complemento. 

### <a name="sales-order-header"></a>Encabezado de pedidos de ventas

- **Propósito**: Seleccione la opción P01. Si no selecciona esta opción, obtendrá un rechazo de servicios de PAC.
- **Incoterm**: Seleccione el código de incoterm definido por el gobierno en el cIncoterm del catálogo.
- **Comercio exterior**: Seleccione este campo para generar el complemento del comercio exterior de CFDI.
- **Certificado de origen**: La selección que realice depende de los acuerdos de libre comercio del gobierno mexicano con otros países:

    - **No marcado (0)**: No se requiere ningún certificado
    - **Marcado (1)**: Se requiere un certificado 

- **Certificado**: El número de certificado si el certificado de origen se ha definido como (1) marcado.

    
> [!NOTE]
> El **Número de registro** y los campos **Dirección fiscal** se utilizan para registrar un albarán de CFDI con el complemento extranjero. Consulte el albarán de CFDI para la función extranjera del complemento.

### <a name="line"></a>Línea

 - **Factura electrónica CFDI**:
   - Entrega
   - Ejemplos
   - Fracción de la cuota: Seleccione el código de la fracción de la cuota define el gobierno en el catálogo cFraccionArancelaria.
   - Unidad de medida personalizada: Seleccione el código de la unidad de medida personalizada definida por el gobierno en el catálogo cUnidadAduana.
   
- **Marcar**: Seleccione la marca relacionada. Esta información se usa como valor predeterminado de la información de producto en caso de pedido de ventas y de parámetros de factura electrónica cuando se usa la factura de servicios y el proyecto.

- **Producto**: Dimensiones de seguimiento > Número de serie: Información obligatoria para especificar el número de serie de mercancías. 
    
Tras completar toda la información necesaria, debe seguir con el proceso habitual de la generación de la factura de CFDI 3.3. Consulte la función del diseño de factura de 3.3 CFDI que se liberó más recientemente.

## <a name="cfdi-packing-slip"></a>Albarán CFDI

El albarán de CFDI (Traslado) conocido anteriormente como Carta de Porte, es un documento electrónico (CFDI) en el que se declaran todas las mercancías cuando se transportan de un sitio a otro y se requieren por el transportista para proteger las mercancías.

El documento de albarán de CFDI se genera de los puntos de entrada siguientes:
- **Pedido de ventas > Albarán para clientes**. 
- **Pedido de transferencia > Registrado desde sitios diferentes.** Las transferencias entre el mismo sitio no generarán un albarán de CFDI, ya que este requisito es obligatorio cuando la mercancía se transfieren entre ubicaciones distintas.

Además, los usuarios podrán completar las acciones siguientes cuando el albarán de CFDI fue emitido y aprobado por el PAC:
- Cancelar manualmente un albarán de CFDI.
- Permite ver y exportar un archivo XML generado.
- Imprimir el albarán CFDI en formato PDF.
- Envíe por correo electrónico una versión imprimible del albarán de CFDI.

### <a name="customer-master-data"></a>Datos maestros de clientes

Realice los pasos siguientes para generar un albarán de CFDI desde la página **Cliente**.
 1. Seleccione **Cobros de la cuenta > Cliente > Todos los clientes**, y seleccione un registro de cliente. 
 2. En el registro de cliente, en el panel de acciones, seleccione **Factura y entrega > Factura electrónica**.
 3. Establezca la opción **Habilitar el albarán de CFDI** según sea necesario. El valor predeterminado para esta opción está en **Pedido de ventas > Paquete y selección > Albarán**.
 
### <a name="sales-order-packing-slip"></a>Albarán del pedido de ventas
 
Realice los pasos siguientes para generar un documento de albarán de CFDI desde la página un pedido de ventas.

1. Crear y confirmar un pedido de ventas.
2. En la página **Pedido de ventas**, en el panel de acciones, seleccione **Seleccionar y empaquetar > Albarán**.
3. Seleccione la opción **Habilitar CFDI** para generar un albarán de CFDI.
4. Seleccione **Aceptar** para generar el albarán.
5. Seleccione **Cobros de la cuenta > Periódico > CFDI - Factura electrónica >Proceso de exportar/importar factura electrónica**, para solicitar la marca digital y emitir para el albarán CFDI XML del proveedor de servicios de PAC.
6. Seleccione **Cobros de la cuenta > Consulta > Diarios > CFDI (factura electrónica)** para revisar el estado del albarán de CFDI.
7. Seleccione la pestaña **Albarán** para ver el estado de albarán de CFDI.
8. Ver, enviar por correo electrónico, exportar, o imprimir un albarán de CFDI. El albarán impreso de CFDI incluye un código de barras bidimensional de acuerdo con el formato de código QR (código de respuesta rápida) descrito por el estándar ISO/IEC18004.

> [!NOTE]
> Un albarán del complemento CFDI de comercio exterior no se admite para un albarán de pedido de ventas. Sin embargo se admite en la factura de CFDI para el comercio exterior.

### <a name="transfer-orders"></a>Pedidos de transferencia

Realice los pasos siguientes para generar el documento de albarán de CFDI para los artículos que se encuentran en tránsito a partir de un sitio a otro.

1. Seleccione **Gestión del inventario > Periódico > Transferir pedidos**.
2. Crear un pedido de transferencia, y seleccione almacén de origen y destino.
3. Agregar artículos relacionados y la cantidad de artículos que desea registrar.
4. En el panel de acciones, seleccione **Registrar > Transferencia de envío**.
5. Seleccione **Editar líneas** y seleccione el envío.
6. Seleccione **Habilitar CFDI** para generar el albarán.

> [!NOTE]
> Los documentos de albarán de CFDI sólo se generan de pedidos de transferencia entre distintos sitios. Si los almacenes de origen y destino pertenecen al mismo sitio, la opción de Habilitar CFDI no se habilita porque el albarán de CFDI no se requiere entre los mismos sitios.

7. Seleccione **Cobros de la cuenta > Periódico > CFDI - Factura electrónica >Proceso de exportar/importar factura electrónica**, para solicitar la marca digital y emitir para el albarán CFDI XML del proveedor de servicios de PAC.
8. Para ver el estado del albarán de CFDI, seleccione **Cobros de la cuenta > Consulta > Diarios > CFDI (factura electrónica)**.
9. Seleccione la pestaña **Transferir pedido** para revisar el estado de albarán de CFDI.
10. Ver, enviar por correo electrónico, exportar, o imprimir el albarán de CFDI. El albarán impreso de CFDI incluye un código de barras bidimensional de acuerdo con el formato de código QR (código de respuesta rápida) descrito por el estándar ISO/IEC18004.
 
## <a name="cfdi-withholding"></a>Retención CFDI
 
El documento de retención de CFDI es un certificado de retención electrónico establecido por las autoridades fiscales en México (SAT) y se aplica para los pagos de proveedor cuando se aplican las retenciones de impuestos de ISR y de IVA.

El documento de retención de CFDI incluye toda la información que considera necesaria el gobierno incluidos los detalles de la empresa, las cuentas de proveedor, y el importe de retenciones de impuestos relacionados.

Los documentos de retención del CFDI se generarán de las transacciones de impuestos donde los códigos de impuestos **IVA** y **ISR** se definen como negativa en los puntos de entrada de transacciones siguientes:

- Factura de compra
- Facturas de proveedor (sin PC)
- Registro de facturas
- Diario de facturas
- Transacción de diario en el área **Contabilidad general** cuando la cuenta de proveedor está presente

La retención tipo se usa el valor predeterminado de la cuenta del proveedor y el usuario puede modificar la retención escrita durante el proceso de registro de la transacción.

### <a name="periodic-process"></a>Proceso periódico
Un documento de retención de CFDI se genera desde **Proveedores > Periódico > CFDI > Generar retención CFDI**.
El usuario puede seleccionar la cuenta de proveedor y el **Mes/año** de y a.

Cuando se confirma el proceso, se generan los documentos de retención de CFDI y debe comenzar el proceso para solicitar la marca digital al proveedor de servicios de PAC seleccionando **Proveedores > Periódico > CFDI > proceso de retención de exportación/importación CFDI**.

Los complementos específicos se generan para los tipos de retención siguientes:

- **Interés (16):** Información adicional que se requiere durante el registro de la transacción como:  

    - La transacción pertenece al sistema financiero.
    - Interés cobrado en el período/año actual.
    - Los intereses pertenecen a operaciones financieras derivadas.
    - Interés nominal real, e importes de interés de la pérdida.
    
- **Pagos extranjeros (18):** Información adicional que se debe configurar en los datos del maestro de proveedores cuando proveedor extranjero RFC del representante legal en México.

> [!NOTE]
> Otros complementos no se admiten actualmente.

### <a name="inquire-cfdi-withholding-documents"></a>Consultar los documentos de retención de CFDI

Después de que el documento de retención de CFDI se emita al PAC, puede ver el estado y completar acciones relacionados seleccionando **Proveedores > Consulta > Diarios > Diario de retención de CFDI**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]