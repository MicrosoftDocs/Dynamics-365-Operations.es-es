---
title: Extractos electrónicos de cuenta contable
description: Este artículo explica cómo configurar y generar los archivos XML de contabilidad general que todas las empresas de México debe presentar a las autoridades fiscales mexicanas (SAT) de manera mensual.
author: AdamTrukawka
ms.date: 12/07/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Mexico
ms.author: atrukawk
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 265314
ms.assetid: b4a95c26-a49d-4a1d-bf70-90f457df2ddf
ms.search.form: ERSolutionTable, LedgerConsolidateAccountGroup, LedgerJournalTable, LedgerJournalTransVendInvoice, LedgerParameters, MainAccount, MainAccountConsolidateAccount, VendEditInvoice, VendPaymMode, VendTransInvoicePool
ms.openlocfilehash: 0279cce2d47d45f3b32493f1a35d2cd98fc77870
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278178"
---
# <a name="electronic-ledger-accounting-statements"></a>Extractos electrónicos de cuenta contable

[!include [banner](../includes/banner.md)]

Este artículo explica cómo configurar y generar los archivos XML de contabilidad general que todas las empresas de México debe presentar a las autoridades fiscales mexicanas (SAT) de manera mensual.

Todas las empresas de México deben informar de los extractos de cuenta contable a las autoridades fiscales mexicanas (Servicio de Administración Tributaria \[SAT\]) todos los meses. El anexo 24 de la Resolución de Diversos Impuestos requiere que envíe los archivos XML de contabilidad general. Puede generar los siguientes archivos XML por empresa:

-   Plan contable
-   Saldo de comprobación mensual
-   Transacciones de diario, junto con las transacciones de subcontabilidad relacionadas (Comprobante Fiscal Digital a través de Internet \[CFDI\], Comprobante Fiscal Digital \[CFD\] y otras operaciones)
-   Cuenta contable auxiliar

Esta función solo está disponible cuando el país o la región de la empresa se define como MEX. 

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

- **Cuenta principal primaria:** la etiqueta **&lt;SubCtaDe&gt;** del archivo XML se usa para especificar la cuenta del nivel anterior. En este caso, usamos un campo de país o región de **Cuenta principal** en la configuración del plan de cuentas.
- **Nivel de cuenta:** la etiqueta **&lt;Nivel&gt;** del archivo XML se usa para especificar el nivel del grupo de cuentas del gobierno. Localizamos la funcionalidad del campo **Grupo de cuentas de consolidación** en **Cuentas de consolidación adicionales** para especificar el nivel del grupo de cuentas del gobierno.
- **Indicador de débito o crédito:** la etiqueta **&lt;Natur&gt;** del archivo XML se usa para especificar el indicador de débito y crédito de la cuenta principal. Se han definido las siguientes reglas:
  - **Débito D**
    -   Tipo de cuenta principal = Coste, Activo
    -   Tipo de cuenta principal: Si Pérdidas/ganancias y Propuesta Debe/Haber = Débito
    -   Tipo de cuenta principal: Si Saldo y Propuesta Debe/Haber = Débito
    -   Tipo de cuenta principal: Si Pérdidas/ganancias y Propuesta Debe/Haber = En blanco
    -   Tipo de cuenta principal: Si Saldo y Propuesta Debe/Haber = En blanco
  - **Crédito A**
    -   Tipo de cuenta: Ingresos, Pasivo
    -   Tipo de cuenta AX: Si Pérdidas/ganancias y Propuesta Debe/Haber = Crédito
    -   Tipo de cuenta AX: Si Saldo y Propuesta Debe/Haber = Crédito
- **Importe de totales en todos los niveles:** Configure el valor de **Totales** en el plan de cuentas para habilitar la generación de un archivo XML Saldo de comprobación mensual que incluye los importes de los totales relacionados en todos los niveles de la jerarquía.

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

Esta característica se basa en la configuración de informes electrónicos (ER), donde cada formato de archivo XML se define con el diseñador de modelos y formatos para informes electrónicos. 

Necesita descargar las últimas versiones siguientes de los modelos y formatos de configuraciones de ER de la **biblioteca de activos compartidos de LCS**
1.  Modelo electrónico de cuenta contable MX
2.  Libro mayor auxiliar XML MX (formato)
3.  Plan de cuentas XML MX (formato)
4.  Diario XML MX (formato)
5.  Saldo de comprobación XML MX (formato)

A continuación, deberá importar los archivos anteriores a Dynamics 365 Finance. 

1. **Administración de la organización > Informes electrónicos > Configuraciones**
2. **Exchange > Carga desde archivo XML** y **Aceptar** para confirmar. Necesita repetir esta acción para cada archivo XML.


Después de que el depósito se actualice en el entorno con los archivos que acaba de cargar, debe identificar estos formatos en los parámetros de contabilidad general. Haga clic en los parámetros **Contabilidad general** &gt; **Configuración de contabilidad** &gt; **Contabilidad general** y, a continuación, en el grupo de campos **Asignación de informes electrónicos**, seleccione el formato que desea utilizar para generar los archivos XML.

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


## <a name="produce-mexican-electronic-ledger-accounting-report-mx-00020"></a>Producir el informe electrónico de contabilidad de libro mayor del producto mexicano (MX-00020)

Esta tarea le muestra todos los pasos necesarios para configurar la generación de archivos XML electrónicos de cuenta contable mediante la herramienta de informes electrónicos. Necesita descargar la versión más alta del modelo y las configuraciones de ER de las configuraciones de biblioteca- GER compartidas de LCS.

-   Modelo: Modelo de cuenta contable electrónica (MX) 
-   Archivo de formato: Plan de cuentas XML (MX)
-   Archivo de formato: Saldo de comprobación XML (MX) Saldo de comprobación mensual
-   Archivo de formato: Diarios XML (MX). Transacciones de diario, junto con las transacciones de subcontabilidad relacionadas (Comprobante Fiscal Digital a través de Internet \[CFDI\], Comprobante Fiscal Digital \[CFD\] y otras operaciones)
-   Archivo de formato: Libro mayor auxiliar XML (MX) 


### <a name="import-a-configuration-including-xml-formats"></a>Importación de una configuración con formatos XML
1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
2. En la lista Proveedores de configuración, haga clic en Definir como activo en el cuadro de proveedor de Microsoft.
    * Si el proveedor de Microsoft ya es el proveedor activo, puede omitir este paso.  
3. Haga clic en Configuraciones de informes.
4. Haga clic en Exchange y seleccione la opción Cargar desde un archivo XML
5. Seleccione y examine el archivo del modelo de XML descargado previamente desde LCS y haga clic en Aceptar para confirmar
6. Repita los pasos 4 y 5 para importar el resto de formatos de archivo XML
    * Podrá ver un (1) modelo y los cuatro (4) formatos XML que importó anteriormente.  

### <a name="configure-general-ledger-parameters-for-electronic-reporting-mapping"></a>Configuración de parámetros de contabilidad general para asignar informes electrónicos
1. Vaya a Contabilidad general > Configuración de contabilidad > Parámetros de Contabilidad general.
2. En el campo Saldo de comprobación, haga clic en el botón desplegable para abrir la búsqueda.
3. En la lista, seleccione el formato XML de saldo de comprobación.
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. En el campo Libro mayor auxiliar, haga clic en el botón desplegable para abrir la búsqueda.
6. En la lista, seleccione el formato XML de libro mayor auxiliar.
7. En el campo Movimientos contables, haga clic en el botón desplegable para abrir la búsqueda.
8. En la lista, seleccione el formato XML para diarios.
9. En la lista, haga clic en el vínculo de la fila seleccionada.
10. En el campo Plan contable, haga clic en el botón desplegable para abrir la búsqueda.
11. En la lista, seleccione el formato XML para plan de cuentas.
12. Haga clic en Guardar.

### <a name="generate-xml-files"></a>Generación de archivos XML
1. Vaya Contabilidad general > Consultas e informes > Informes de contabilidad > Extracto electrónico de cuenta contable.
2. En el campo Grupo de cuentas de consolidación de SAT, haga clic en el botón desplegable para abrir la búsqueda.
3. En la lista, busque y seleccione el registro deseado.
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. En el campo Período, especifique una fecha.
6. Active o desactive la opción Saldo de comprobación.
    * Esta opción genera los archivos XML del plan contable y el saldo de comprobación.  
7. Active o desactive la casilla Movimientos contables.
8. Active o desactive la casilla Libro mayor auxiliar.
9. En el campo Tipo de solicitud, seleccione una opción.
10. En el campo Número de pedido, escriba un valor.
11. Haga clic en Aceptar.


## <a name="additional-resources"></a>Recursos adicionales

- [Versión 3.3 del diseño CFDI](latam-mex-cfdi-3-3.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
