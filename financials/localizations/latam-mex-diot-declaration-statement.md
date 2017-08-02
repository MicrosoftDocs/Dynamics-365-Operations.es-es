---
title: "Informe de declaración DIOT"
description: "En este tema se proporciona información acerca del informe de declaración DIOT para México."
author: sndray
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DIOTDeclarationConcept_MX, DIOTDeclarationTaxCode_MX, VendTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 79334
ms.assetid: 0cdb4da3-dca8-4e31-8fd5-8a1f785b5104
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: e2a8b09e7e333f2e2f7a63cc190ae52d7e822a9e
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017


---

# <a name="diot-declaration-statement"></a>Informe de declaración DIOT

[!include[banner](../includes/banner.md)]


En este tema se proporciona información acerca del informe de declaración DIOT para México.

El informe de la declaración DIOT (declaración informativa de operaciones con proveedores) se usa para informar de transacciones de proveedores a las autoridades fiscales mexicanas (Servicio de Administración Tributaria \[SAT\]). Puede que tenga que hacerlo si está sujeto a impuestos sobre el valor añadido (IVA). El informe de la declaración DIOT es un archivo de texto. Puede generar este archivo en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition y, a continuación, importarlo en la herramienta de validación y entrega del gobierno. Los informes consolidados y detallados también se generan para fines de control. El informe incluye transacciones que se generaron de los pedidos de compra, los diarios de registro de facturas, los diarios de aprobación de facturas y los diarios de facturas. También incluye las transacciones de proveedor que se generaron del módulo **Proyecto**. Además, puede incluir transacciones abiertas o transacciones liquidadas.

## <a name="prerequisites"></a>Requisitos previos
Debe completar la configuración siguiente para poder generar el archivo de texto de DIOT o informes relacionados:

1.  Especifique los números o los id. de registro de impuestos para la entidad jurídica.
2.  Permite especificar información de impuestos para proveedores.

## <a name="tax-information-for-unmanaged-vendors"></a>Información de impuestos para proveedores no administrados
Los proveedores no administrados son proveedores que no tienen sus detalles registrados como cuentas de proveedor en Finance and Operations. Cuando se registra una transacción de compra para este tipo de proveedor, puede seleccionar cualquier cuenta contable diferente de la cuenta de proveedor. Dado que todas las transacciones de compras se incluyen en el informe de la declaración DIOT, las transacciones de compras para los proveedores no administrados también requieren los id. de impuestos (RFC o CURP), el tipo de operación y otra información adicional. Para los proveedores habituales, puede definir información adicional en la página **Proveedores**. Sin embargo, no puede hacerlo para proveedores no administrados. Para capturar la información fiscal necesaria para proveedores no administrados, puede especificar información adicional en el nivel de la transacción en las siguientes transacciones de diario cuando no se identifique la cuenta de proveedor:

-   Diario de facturas
-   Registro de facturas
-   Diario de gastos

Para definir códigos de impuestos para que los campos de información adicional estén disponibles para un proveedor no administrados en transacciones de diario, debe especificar un código de impuestos que se ha configurado para permitir información adicional en el diario.

## <a name="diot-report-configuration"></a>Configuración de informe DIOT
En esta sección se describe cómo definir los conceptos y vincular los códigos de impuestos que se requieren para generar el informe de la declaración DIOT. En Finance and Operations, un concepto representa los importes de transacción de compras que se agrupan en distintos porcentajes de IVA, según lo especificado por las autoridades fiscales de México. En el archivo de texto de DIOT, los importes totales se agrupan para cada proveedor, en función de los conceptos definidos anteriormente. Estos conceptos se notifican en las columnas 8 al 22 del formato de diseño de DIOT. Las demás columnas del informe se rellenan automáticamente en función de la información del proveedor como RFC, tipo de operación y otros datos relacionados.

### <a name="example-of-concepts"></a>Ejemplo de conceptos

| Id. de concepto | Descripción del concepto                               | Posición de columna en el archivo de texto (número de pedido) |
|------------|---------------------------------------------------|-------------------------------------------------|
| 1          | El importe base de las compras con el 16 % de IVA (liquidado) | 8                                               |
| 2          | El importe base de las compras con el 15 % de IVA (liquidado) | 9                                               |
| 3          | Importe de IVA no recuperable del 16 % o el 15 %          | 10                                              |

Puede crear nuevos conceptos en la página **Declaración DIOT**. Sin embargo, solo puede crear 15 conceptos. El primer concepto debe ser el número de pedido 8 y el último debe ser el número de pedido 22. Puede empezar a crear los conceptos con otro pedido, pero debe completar todos (del 8 al 22) para evitar incoherencias en la herramienta de validación del gobierno. Para cada concepto, debe especificar un tipo de columna. Especifique un tipo de columna de **Ninguno** si se ha quedado en desuso la columna. Algunas columnas ya no se aplican y se deben notifica con un importe **0,00**. Si la casilla no está activada, el informe de declaración DIOT muestra el importe neto completo o el importe de impuestos. Además, para cada columna, puede indicar el porcentaje no deducible del importe neto o el importe de impuestos que se muestra en el informe de declaración DIOT.

#### <a name="example"></a>Ejemplo

Si el importe neto o el importe de impuestos es 10000.00 pesos, y el porcentaje del importe no deducible es el 30 por ciento, el informe muestra solo el 30 por ciento de 10.000,00 pesos, o 3.000,00 pesos. Use el botón **Código de impuestos** para vincular uno o más códigos de impuestos a un concepto.

## <a name="generate-the-diot-declaration-statement"></a>Generar el informe de declaración DIOT
Para generar el informe de declaración DIOT, haga clic en **Impuestos** &gt; **Declaraciones** &gt; **Impuestos** &gt; **Generar la DIOT**. Debe especificar o seleccionar la siguiente información.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Campo</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Periodo de liquidación no realizado</td>
<td>Seleccione un período de liquidación no realizado. Este es el período que se usa en la configuración de códigos de impuestos para impuestos condicionales.</td>
</tr>
<tr class="even">
<td>Periodo de liquidación realizado</td>
<td>Seleccione el período de liquidación realizado. Este es el período que se usa en la configuración de códigos de impuestos.</td>
</tr>
<tr class="odd">
<td>Fecha inicial</td>
<td>Seleccione el período.</td>
</tr>
<tr class="even">
<td>Tipo de informe de DIOT</td>
<td>Seleccione <strong>Consolidado</strong> o <strong>Detallado</strong>.</td>
</tr>
<tr class="odd">
<td>Incluir transacciones</td>
<td>Seleccione las opciones disponibles:
<ul>
<li><strong>No realizado</strong>: incluya solo las transacciones de compras no realizadas (las transacciones que no se liquidaron ni crearon en el período).</li>
<li><strong>Realizado</strong>: incluya solo las transacciones de compras realizadas (las transacciones que se liquidaron en el período).</li>
<li>Ambos</li>
</ul></td>
</tr>
<tr class="even">
<td>Generar archivo</td>
<td>Seleccione <strong>Sí</strong> para generar el archivo de texto.</td>
</tr>
<tr class="odd">
<td>Porcentaje de operaciones de proveedores globales</td>
<td>Escriba un porcentaje del importe de la transacción de proveedor total, según el cual el proveedor se identifica como un proveedor <strong>Global</strong> o <strong>Local</strong>. Sin embargo, en la página <strong>Proveedores</strong>, en la ficha desplegable <strong>Factura y entrega</strong>, se debe especificar <strong>15: proveedor nacional/global</strong> para el proveedor en el campo <strong>Tipo de proveedor</strong>.</td>
</tr>
<tr class="even">
<td>Límite superior</td>
<td>Especifique el importe del umbral superior para el proveedor global. Para un proveedor global, el importe del pago total que se debe declarar es inferior o igual al valor de este campo. Para un proveedor nacional, el importe del pago total que se debe declarar es superior al valor de este campo.</td>
</tr>
</tbody>
</table>

En el informe de declaración DIOT, los importes tienen signos positivos o negativas, en función del tipo de importe que se especifica para la transacción de compras. Consulte la tabla siguiente.

| Tipo de importe en la transacción de compra      | Signo mostrado en el DIOT |
|----------------------------------------------|----------------------------|
| Importe de crédito                                | Signo más (+)              |
| Importe de débito                                 | Signo menos (–)             |
| Importe de crédito con importe de impuestos positivo | Signo más (+)              |
| Importe de crédito con importe de impuestos negativo | Signo menos (–)             |
| Importe de débito con importe de impuestos positivo  | Signo menos (–)             |
| Importe de débito con importe de impuestos negativo  | Signo más (+)              |






