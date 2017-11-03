---
title: "Extractos electrónicos de cuenta contable"
description: "Este artículo explica cómo configurar y generar la versión 1.1 de los archivos XML de contabilidad general que todas las empresas de México debe presentar a las autoridades fiscales mexicanas (SAT) de manera mensual."
author: sndray
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERSolutionTable, LedgerConsolidateAccountGroup, LedgerJournalTable, LedgerJournalTransVendInvoice, LedgerParameters, MainAccount, MainAccountConsolidateAccount, VendEditInvoice, VendPaymMode, VendTransInvoicePool
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 265314
ms.assetid: b4a95c26-a49d-4a1d-bf70-90f457df2ddf
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: a290f0455cd899df2d3f8bc1e9dc1e24179f2609
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="electronic-ledger-accounting-statements"></a>Extractos electrónicos de cuenta contable

[!include[banner](../includes/banner.md)]


Este artículo explica cómo configurar y generar la versión 1.1 de los archivos XML de contabilidad general que todas las empresas de México debe presentar a las autoridades fiscales mexicanas (SAT) de manera mensual.

Todas las empresas de México deben informar de los extractos de cuenta contable a las autoridades fiscales mexicanas (Servicio de Administración Tributaria \[SAT\]) todos los meses. El anexo 24 de la Resolución de Diversos Impuestos para 2015 requiere que envíe la versión 1.1 de los archivos XML de contabilidad general. Puede generar los siguientes archivos XML por empresa:

-   Plan contable
-   Saldo de comprobación mensual
-   Transacciones de diario, junto con las transacciones de subcontabilidad relacionadas (Comprobante Fiscal Digital a través de Internet \[CFDI\], Comprobante Fiscal Digital \[CFD\] y otras operaciones)
-   Cuenta contable auxiliar

Esta función solo está disponible cuando el país o la región de la empresa se define como MEX. 
> [!NOTE]
>  El gobierno también requiere un archivo XML auxiliar adicional (folios) que detalla todos los documentos fiscales (CFDI, CFD y otros). Este archivo no se incluye en la característica actual, puesto que esta información se incluye en el archivo XML Transacciones de diario, como se especifica en el Capítulo 2.8, sección 2.8.1.3 de la Resolución de Diversos Impuestos para 2015 (segunda sección) del 30 de diciembre de 2014. Para obtener más información, consulte <http://www.sat.gob.mx/fichas_tematicas/buzon_tributario/Documents/extracto_reglas.pdf>.

## <a name="prerequisites"></a>Requisitos previos
El siguiente proceso muestra los requisitos previos que se deben implementar antes de comenzar a generar los archivos XML que el SAT requiere. Los parámetros determinan la manera en que se exponen los datos en los archivos XML y se requieren todos ellos. Los parámetros que faltan pueden provocar incoherencias o validaciones incorrectas en la herramienta de validación del gobierno.

1.  Configurar parámetros de cuenta principal.
2.  Configurar una cuenta\_principal para identificar el nivel de cuenta.
3.  Configurar cuentas totales en todos los niveles.
4.  Configuración de un grupo de cuentas SAT.
5.  Crear un grupo de cuentas de consolidación para SAT.
6.  Asignar cuenta principal a cuentas de nivel y de grupo SAT.
7.  Configuración de métodos de pago y cuentas bancarias.
8.  Asignación de método de pago SAT.
9.  Asigne código de banco SAT en el campo número de ruta.

 

### <a name="chart-of-accounts"></a>Plan contable

Por requisitos del gobierno, el archivo XML Plan contable debe incluir información específica que debe configurar por adelantado para evitar incoherencias cuando se genera y se valida el archivo XML. Establezca los siguientes parámetros para configurar esta información:

-   **Cuenta principal primaria:** la etiqueta **&lt;SubCtaDe&gt;** del archivo XML se usa para especificar la cuenta del nivel anterior. En este caso, usamos un campo de país o región de **Cuenta principal** en la configuración del plan de cuentas.
-   **Nivel de cuenta:** la etiqueta **&lt;Nivel&gt;** del archivo XML se usa para especificar el nivel del grupo de cuentas del gobierno. Localizamos la funcionalidad del campo **Grupo de cuentas de consolidación** en **Cuentas de consolidación adicionales** para especificar el nivel del grupo de cuentas del gobierno.
-   **Indicador de débito o crédito:** la etiqueta **&lt;Natur&gt;** del archivo XML se usa para especificar el indicador de débito y crédito de la cuenta principal. Se han definido las siguientes reglas:
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

El archivo XML Gráfico del plan contable incluye una etiqueta **&lt;CodAgrup&gt;** que se usa para especificar el grupo de cuentas del gobierno relacionado para la cuenta notificada. El gobierno ha publicado una tabla en el portal gubernamental. Para cumplir este requisito, debe usar la funcionalidad de Grupos de cuentas de consolidación, que le permite configurar la asignación entre el plan de cuentas de la empresa y el grupo de la cuenta del gobierno. A continuación, cuando genere el informe, se le solicitará que indique qué grupo de cuentas consolidadas se usa para especificar la agrupación del gobierno.

### <a name="payment-methods"></a>Métodos de pago

En situaciones específicas, el gobierno puede solicitar que entregue un archivo XML Transacciones de diario que detalle todas las transacciones de contabilidad y el documento que las originó. Cuando estas transacciones estén relacionadas con pagos de proveedores, debe especificar el tipo de pago en el nodo **&lt;OtrMetododePago&gt;** y el atributo **&lt;MetPagPol&gt;** mediante una tabla específica que se publica por el gobierno. Haga clic en **Proveedores** &gt; **Configuración de pagos** &gt; **Formas de pago** y asigne el método de pago SAT al método de pago de la empresa.

### <a name="bank-transactions"></a>Transacciones bancarias

El archivo XML Transacciones de diario debe incluir todas las transacciones de transferencias bancarias que se registran en la contabilidad general donde se requiere alguna información adicional en un nodo específico **&lt;Transferencias&gt;** y se requieren sus atributos **&lt;BancoOriNal&gt;** y **&lt;BancoDestNal&gt;** para informar del código de banco gubernamental. Haga clic en **Gestión de efectivo y bancos** &gt; **Cuentas bancarias** y use el campo **Número de ruta** para configurar esta información.

### <a name="invoice-identification"></a>Identificación de factura

El archivo XML Transacciones de diario también requiere que identifique el número de factura cuando se emita y se reciba una factura. Según la legislación mexicana, este número de factura se puede representar de distintas maneras, en función de cómo se haya entregado la factura:

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

Esta característica se basa en la configuración de informes electrónicos (ER), donde cada formato de archivo XML se define con el diseñador de modelos y formatos para informes electrónicos. Use el tipo de configuración de repositorio **Recursos de AX** para importar estas configuraciones en la empresa actual y habilitar la generación de archivos XML. Haga clic en **Administración de la organización** &gt; **Espacios de trabajo** &gt; **Informes electrónicos** &gt; **Repositorios**.

Debe cargar los siguientes modelos y formatos de repositorio:

1.  Modelo electrónico de cuenta contable MX
2.  Libro mayor auxiliar XML MX (formato)
3.  Plan de cuentas XML MX (formato)
4.  Diario XML MX (formato)
5.  Saldo de comprobación XML MX (formato)

Después de que el depósito esté disponible en el entorno, debe identificar estos formatos en los parámetros de contabilidad general. Haga clic en los parámetros **Contabilidad general** &gt; **Configuración de contabilidad** &gt; **Contabilidad general** y, a continuación, en el grupo de campos **Asignación de informes electrónicos**, seleccione el formato que desea utilizar para generar los archivos XML.

## <a name="generate-electronic-ledger-accounting-files"></a>Generar archivos electrónicos de cuenta contable
Haga clic en **Contabilidad general** &gt; **Consulta e informes** &gt; **Informes de contabilidad** &gt; **Extracto electrónico de cuenta contable** para generar los archivos XML necesarios y descargarlos en el entorno. La tabla siguiente describe los parámetros que debe establecer.

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
<td><strong>Tipo de entrega</strong></td>
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






