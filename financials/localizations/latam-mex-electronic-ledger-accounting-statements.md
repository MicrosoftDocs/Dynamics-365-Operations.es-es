---
title: "Extractos electrónicos de cuenta contable"
description: "Este artículo explica cómo configurar y generar la versión 1.1 de los archivos XML de contabilidad general que todas las empresas de México debe presentar a las autoridades fiscales mexicanas (SAT) de manera mensual."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ERSolutionTable, LedgerConsolidateAccountGroup, LedgerJournalTable, LedgerJournalTransVendInvoice, LedgerParameters, MainAccount, MainAccountConsolidateAccount, VendEditInvoice, VendPaymMode, VendTransInvoicePool
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 265314
ms.assetid: b4a95c26-a49d-4a1d-bf70-90f457df2ddf
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 2e5090c11bc22d01516175152a115d3e74b74240
ms.lasthandoff: 03/31/2017


---

# <a name="electronic-ledger-accounting-statements"></a>Extractos electrónicos de cuenta contable

Este artículo explica cómo configurar y generar la versión 1.1 de los archivos XML de contabilidad general que todas las empresas de México debe presentar a las autoridades fiscales mexicanas (SAT) de manera mensual.

Son necesarios todas las empresas en México informar instrucciones de la contabilidad contable a las autoridades fiscales mexicanas (Servicio de Administración Tributaria \[\]SAT) todos los meses. El anexo 24 de la Resolución de Diversos Impuestos para 2015 requiere que envíe la versión 1.1 de los archivos XML de contabilidad general. Puede generar los siguientes archivos XML por empresa:

-   Plan contable
-   Saldo de comprobación mensual
-   Transacciones de diario, junto con las transacciones relacionadas del subdiario contable (Comprobante Digital fiscal través de Internet CFDI \[\], Comprobante Digital fiscal CFD \[,\]y otras operaciones)
-   Cuenta contable auxiliar

Esta función solo está disponible cuando el país o la región de la empresa se define como MEX. 
> [!NOTE]
>  El gobierno también requiere un archivo XML ayudante adicional (folios) que los detalles todos los documentos fiscales (CFDI, CFD, y otros). Este archivo no se incluye en la función actual, debido a que esta información se incluirá en el archivo XML de transacciones de diario, como se especifica en el capítulo 2.8, sección 2.8.1.3 de la resolución Varios de IRPF para 2015 (en segundo sección) de 30 de diciembre de 2014. Para obtener< más información, consulte http://www.sat.gob.mx/fichas_tematicas/buzon_tributario/Documents/extracto_reglas.pdf>.

## <a name="prerequisites"></a>Requisitos previos
El proceso siguiente muestra los requisitos previos que deben existir antes de comenzar a generar archivos XML que requiere el SAT. Los parámetros determinan cómo los datos se expuestos en los archivos XML, y se requieren todos. Los parámetros que faltan pueden provocar incoherencias o validaciones incorrectas en la herramienta de validación del gobierno.

1.  Configuración de parámetros de la cuenta principal.
2.  Configurar una cuenta principal\_para identificar el nivel de cuenta.
3.  Cuentas de instalación totales en todos los niveles.
4.  Grupo de cuentas de instalación del SAT.
5.  Crear grupo de cuentas de consolidación para el SAT.
6.  Cuenta principal a las cuentas del grupo y el nivel del SAT.
7.  Método de instalación de pagos y de cuentas bancarias.
8.  Método del SAT de la asignación de pagos.
9.  Código de banco del SAT de asignación en campo Número de ruta.

 

### <a name="chart-of-accounts"></a>Plan contable

Por requisitos del gobierno, el archivo XML Plan contable debe incluir información específica que debe configurar por adelantado para evitar incoherencias cuando se genera y se valida el archivo XML. Establezca los siguientes parámetros para configurar esta información:

-   ** Cuenta principal principal: ** **&lt;SubCtaDe&gt;** etiquetas en el archivo XML se utiliza para especificar la cuenta de nivel anterior. En este caso, usamos un campo de país o región de **Cuenta principal** en la configuración del plan de cuentas.
-   ** Cuenta nivel: ** **&lt;Nivel&gt;** etiquetas en el archivo XML se utiliza para especificar el nivel del grupo de cuentas del gobierno. Localizamos la funcionalidad del campo **Grupo de cuentas de consolidación** en **Cuentas de consolidación adicionales** para especificar el nivel del grupo de cuentas del gobierno.
-   ** Indicador de débito y crédito: ** **&lt;Natur&gt;** etiquetas en el archivo XML se utiliza para especificar el débito y el indicador de crédito de la cuenta principal. Se han definido las siguientes reglas:
    -   **Débito D**
        -   Tipo de cuenta principal = Coste, Activo
        -   Tipo de cuenta principal: Si Pérdidas/ganancias y Propuesta Debe/Haber = Débito
        -   Tipo de cuenta principal: Si Saldo y Propuesta Debe/Haber = Débito
        -   Tipo de cuenta principal: Si Pérdidas/ganancias y Propuesta Debe/Haber = En blanco
        -   Tipo de cuenta principal: Si Saldo y Propuesta Debe/Haber = En blanco
    -    **Crédito A**
        -   Tipo de cuenta: Ingresos, Pasivo
        -   Tipo de cuenta AX: Si Pérdidas/ganancias y Propuesta Debe/Haber = Crédito
        -   Tipo de cuenta AX: Si Saldo y Propuesta Debe/Haber = Crédito
-   **Importe de totales en todos los niveles:** Configure el valor de **Totales** en el plan de cuentas para habilitar la generación de un archivo XML Saldo de comprobación mensual que incluye los importes de los totales relacionados en todos los niveles de la jerarquía.

### <a name="sat-account-group"></a>Grupo de cuentas SAT

El gráfico del archivo XML de la cuenta incluye a CodAgrup&gt;**&lt;** etiqueta que se utilice para especificar el grupo de cuentas relacionada del gobierno de la cuenta designada. El gobierno ha publicado una tabla en el portal gubernamental. Para cumplir este requisito, debe usar la funcionalidad de grupos de cuentas de consolidación, que le permite configurar la asignación entre su gráfico de la empresa de la cuenta y el grupo de cuentas del gobierno. A continuación, cuando se genera el informe, se le pedirá que indicar que desea consolidó utilizan el grupo de cuentas para especificar la agrupación del gobierno.

### <a name="payment-methods"></a>Métodos de pago

En situaciones específicas, el gobierno puede solicitar que entregue un archivo XML Transacciones de diario que detalle todas las transacciones de contabilidad y el documento que las originó. Cuando estas transacciones están relacionadas con pagos de proveedores, debe especificar el tipo de pago en OtrMetododePago&gt;**&lt;** el nodo y **&lt;MetPagPol&gt;** de atributo mediante una tabla específica que es publicada por el gobierno. Haga clic ** proveedores ** &gt; ** pago configuradas ** &gt; ** las formas de pago, ** y asignar el método de pago del SAT a la forma de pago de la empresa.

### <a name="bank-transactions"></a>Transacciones bancarias

El archivo XML de la transacción de diario debe incluir todas las transacciones de transferencia bancaria registrarlos en la contabilidad general donde cierta información adicional se requieren en un nodo específico **&lt;Transferencias&gt;** y sus atributos **&lt;BancoOriNal&gt;** y **&lt;BancoDestNal&gt;** se requiere para informar al código bancario gubernamental. ** Haga clic en efectivo y bancos ** &gt; ** cuentas bancarias y **, utilice ** número de ruta ** el campo para configurar esta información.

### <a name="invoice-identification"></a>Identificación de factura

El archivo XML de la transacción de diario también requiere que se identifica el número de factura cuando se emite y se recibe una factura. Por la legislación mexicana, este número de factura se puede representar en distintas formas, en función de cómo la factura se ha entregado:

-   Factura normal (no electrónica). Debe incluir la **Serie** y el **Número de factura**.
-   CFD: Debe incluir el **UUID** de un CFD de factura electrónica.
-   CFDI: Debe incluir el **UUID** de un CFD de factura electrónica.

Los usuarios pueden incluir ahora esta información en las transacciones que se generan de las siguientes áreas:

-   Factura de compra
-   Factura de proveedor (pedido que no es de compra)
-   Registro de facturas
-   Diario de facturas
-   Aprobación de factura
-   Grupo de facturas

### <a name="electronic-reporting"></a>Informes electrónicos

Esta función se basa en la configuración electrónica de informes (ER), donde cada formato de archivo XML se define mediante el diseñador de modelo y el formato del informe de errores electrónico. Use el tipo de configuración de repositorio **Recursos de AX** para importar estas configuraciones en la empresa actual y habilitar la generación de archivos XML. ** Haga clic en Administración de organización ** &gt; ** áreas de trabajo ** &gt; ** informe de errores electrónico ** &gt; ** repositorios **.

Debe cargar los siguientes modelos y formatos de repositorio:

1.  Modelo electrónico de cuenta contable MX
2.  Libro mayor auxiliar XML MX (formato)
3.  Plan de cuentas XML MX (formato)
4.  Diario XML MX (formato)
5.  Saldo de comprobación XML MX (formato)

Después de que el depósito esté disponible en el entorno, debe identificar estos formatos en los parámetros de contabilidad general. Haga clic en ** contabilidad general ** &gt; ** configuración contable ** &gt; ** parámetros de contabilidad general ** y, a continuación, en ** asignación electrónica de informes ** el grupo de campos, seleccione el formato que desea utilizar para generar los archivos XML.

## <a name="generate-electronic-ledger-accounting-files"></a>Generar archivos electrónicos de cuenta contable
Haga clic en ** contabilidad general ** &gt; ** consultar y informa ** &gt; ** los informes de contabilidad ** &gt; ** instrucción de contabilidad electrónica de contabilidad ** generar archivos XML obligatorios y descargarlos al entorno. La tabla siguiente describe los parámetros que debe establecer.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Grupo de cuentas de consolidación de SAT</strong></td>
<td>Seleccione el grupo de cuentas de consolidación que haya configurado anteriormente para identificar el grupo de cuentas SAT.</td>
</tr>
<tr class="even">
<td><strong>Período</strong></td>
<td>Seleccione el período del informe. La fecha seleccionada incluirá todas las transacciones de contabilidad general para el mes seleccionado.</td>
</tr>
<tr class="odd">
<td><strong>Transacciones de cierre</strong></td>
<td>Este control deslizante indica si las transacciones de cierre se deben incluir como transacciones en el archivo XML Saldo de comprobación mensual. Cambie este control deslizante a <strong>No</strong> para excluir las transacciones de cierre del archivo XML Saldo de comprobación mensual.</td>
</tr>
<tr class="even">
<td><strong>Saldo de comprobación</strong></td>
<td>Active esta casilla para generar los archivos XML Plan de cuentas y Saldo de comprobación mensual para el período especificado.</td>
</tr>
<tr class="odd">
<td><strong>Tipo de entrega</strong> </td>
<td>Especifique el tipo de entrega:
<ul>
<li>Normal</li>
<li>Complementario</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Fecha de actualización</strong></td>
<td>Especifique la fecha actualizada de una entrega complementaria.</td>
</tr>
<tr class="odd">
<td><strong>Movimientos contables</strong></td>
<td>Este control deslizante indica si el archivo XML Transacciones de diario se genera para el período especificado.</td>
</tr>
<tr class="even">
<td><strong>Libro mayor auxiliar</strong></td>
<td>Este control deslizante indica si el archivo XML Libro mayor auxiliar se genera para el período especificado.</td>
</tr>
<tr class="odd">
<td><strong>Tipo de solicitud</strong></td>
<td>Seleccione esta opción para identificar el tipo de solicitud cuando el control deslizante <strong>Asientos contables</strong> o <strong>Libro mayor auxiliar</strong> está establecido en <strong>Sí</strong>.</td>
</tr>
<tr class="even">
<td><strong>Número de pedido</strong></td>
<td>Especifique el número de pedido que se ha asignado por la autoridad fiscal del gobierno, si el tipo de solicitud es <strong>Control</strong> o <strong>Control obligatorio</strong>.</td>
</tr>
<tr class="odd">
<td><strong>Número de proceso</strong></td>
<td>Especifique el número de proceso que se ha asignado por la autoridad fiscal del gobierno, si el tipo de solicitud es <strong>Devolución</strong> o <strong>Compensación</strong>.</td>
</tr>
</tbody>
</table>




