---
title: Distribuciones contables y movimientos del diario contable de las facturas de proveedores
description: Las distribuciones contables se usan para definir cómo un importe se justificará, por ejemplo, cómo se justificarán los gastos, impuestos o cargos en la factura de un proveedor. Cada importe que se debe justificar cuando se registre en el diario la factura de proveedor tendrá una o varias distribuciones contables.
author: sunfzam
ms.date: 02/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendEditInvoice
audience: Application User
ms.reviewer: twheeloc
ms.custom: 26891
ms.assetid: 93dc608a-b5b4-4ec3-83c2-618e3d80a583
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f10ddf113f59da4800a97a48300ab1310bfb42dd
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2022
ms.locfileid: "8358190"
---
# <a name="accounting-distributions-and-journal-entries-for-vendor-invoices"></a>Distribuciones contables y movimientos del diario contable de las facturas de proveedores

[!include [banner](../includes/banner.md)]

Las distribuciones contables se usan para definir cómo un importe se justificará, por ejemplo, cómo se justificarán los gastos, impuestos o cargos en la factura de un proveedor. Cada importe que se debe justificar cuando se registre en el diario la factura de proveedor tendrá una o varias distribuciones contables. 

## <a name="accounting-distributions"></a>Distribuciones contables 

Puede usar los siguientes botones de la página Factura de proveedor para ver y para modificar probablemente las distribuciones contables de cada importe de la factura de proveedor.
-   **Distribuir importes**: permite ver y modificar las distribuciones contables de una línea individual y todas las líneas secundarias, como impuestos o gastos. También puede ver y modificar distribuciones contables para la línea secundaria directamente desde la página **Transacciones de impuestos** o la página **Transacciones de gastos**.
    -   Modifique los importes de encabezado de la factura del proveedor, como gastos o importes de redondeo de divisa.
    -   Modifique los importes de la línea de factura de proveedor.
-   **Ver distribuciones**: permite ver las distribuciones contables para todas las líneas del documento. No se pueden modificar las distribuciones contables desde esta vista.
    -   Permite ver los importes de línea y encabezado.

Si la factura de proveedor hace referencia a un pedido de compra, puede dividir y modificar distribuciones contables para las líneas que contienen un artículo que no sea se mantiene en existencias. Si la línea de factura de proveedor no hace referencia a una línea de pedido de compra, también puede eliminar una distribución contable. No puede dividir o eliminar líneas para gastos, impuestos y descuentos de línea. Puede modificar la cuenta contable, pero no puede cambiar los importes o porcentajes.
> [!NOTE]                                                                                                                                 
> Si la línea principal contiene un artículo no mantenido en existencias y se dividen las distribuciones contables, la línea secundaria se dividirá automáticamente para coincidir con las dimensiones financieras de la línea principal. Las distribuciones contables de la línea secundaria no se pueden dividir o eliminar adicionalmente, pero según la configuración de la línea secundaria, es posible que pueda modificar la cuenta contable para las distribuciones contables de la línea secundaria.

## <a name="distributing-amounts"></a>Distribución de importes
Cuando se especifica una factura de proveedor, cada importe se distribuirá del modo siguiente.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de línea de factura de proveedor</th>
<th>Orden de prioridad que determina desde dónde se muestra la cuenta principal</th>
<th>Orden de prioridad que determina que dimensión financiera se visualiza</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Producto mantenido en existencias</td>
<td><ol>
<li>La distribución contable para la línea de pedido de compra.</li>
<li>El campo <strong>Cuenta principal</strong> cuando está seleccionado Gasto de compra para el producto en la página <strong>Registro</strong>.</li>
</ol></td>
<td><ol>
<li>Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</li>
<li>Use los valores de la dimensión financiera predeterminados en la factura de proveedor.</li>
</ol></td>
</tr>
<tr class="even">
<td>Una categoría de compras o un producto que no se mantiene en existencias</td>
<td><ol>
<li>La distribución contable para la línea de pedido de compra, si la línea de factura de proveedor hace referencia a una línea de pedido de compra.</li>
<li>El campo <strong>Cuenta principal</strong> cuando está seleccionado Gasto de compra para gasto en la página <strong>Registro</strong>.</li>
</ol></td>
<td><ol>
<li>Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</li>
<li>Si la cuenta principal es una cuenta de asignación, use el valor predeterminado de la definición de cuenta de asignación.</li>
<li>Use los valores de la dimensión financiera predeterminados en la factura de proveedor.</li>
<li>Use los valores de dimensión financiera predeterminados de la línea de factura de proveedor.</li>
<li>Use los valores de la dimensión financiera predeterminados de la cuenta principal en la página <strong>Plan contable</strong>.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Activo fijo</td>
<td><ol>
<li>La distribución contable para la línea de pedido de compra, si la línea de factura de proveedor hace referencia a una línea de pedido de compra.</li>
<li>Si <strong>Adquisición</strong> está seleccionado en el campo <strong>Tipo de transacción</strong> de la página <strong>Factura de proveedor</strong>, el campo <strong>Cuenta principal</strong> cuando <strong>Adquisición</strong> está seleccionado en la página <strong>Perfiles de contabilización de activos fijos</strong>.</li>
<li>Si <strong>Ajuste de adquisición</strong> está seleccionado en el campo <strong>Tipo de transacción</strong>, el campo <strong>Cuenta principal</strong> cuando <strong>Ajuste de adquisición</strong> está seleccionado en la página <strong>Perfiles de contabilización de activos fijos</strong>.</li>
</ol></td>
<td><ol>
<li>Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</li>
<li>Use los valores de dimensión financiera predeterminados de la línea de factura de proveedor.</li>
<li>Use los valores de la dimensión financiera predeterminados de la cuenta principal en la página <strong>Plan contable</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Proyecto definido en la línea de factura de proveedor</td>
<td><ol>
<li>Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución contable de la línea de pedido de compra.</li>
<li>Si <strong>Saldo</strong> está seleccionado en el campo <strong>Registrar costes - Artículo</strong> en la página <strong>Grupos de proyectos</strong>, el campo <strong>Cuenta principal</strong> cuando <strong>Coste</strong> está seleccionado en la página <strong>Configuración de registro</strong>.</li>
<li>Si <strong>Pérdidas y ganancias</strong> está seleccionado en el campo <strong>Registrar costes - Artículo</strong> en la página <strong>Grupos de proyectos</strong>, el campo <strong>Cuenta principal</strong> cuando <strong>Coste - artículo</strong> está seleccionado en la página <strong>Configuración de registro</strong>.</li>
</ol></td>
<td><ol>
<li>Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Descuento de línea</td>
<td><ol>
<li>Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución contable de la línea de pedido de compra.</li>
<li>El campo <strong>Cuenta principal</strong> cuando <strong>Descuento</strong> se selecciona en la página <strong>Registro</strong>.</li>
<li>Si una cuenta principal para un descuento no se define en el perfil de registro, la distribución contable del precio total de la línea de pedido de compra.</li>
</ol></td>
<td><ol>
<li>Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución contable para la línea de pedido de compra.</li>
<li>Use las dimensiones financieras de las distribuciones contables para el precio total de la línea de factura de proveedor.</li>
<li>Use los valores de dimensión financiera predeterminados para la línea de factura de proveedor.</li>
<li>Use los valores de la dimensión financiera predeterminados de la cuenta principal en la página <strong>Plan contable</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Cargo de compra, que se especifica en la ficha <strong>Precio y descuento</strong> de la línea de pedido de compra</td>
<td><ol>
<li>Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución contable de la línea de pedido de compra.</li>
<li>La distribución contable del precio total de la línea de pedido de compra.</li>
</ol></td>
<td><ol>
<li>Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</li>
<li>Use las dimensiones financieras de las distribuciones contables para el precio total de la línea de factura de proveedor.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Gastos de línea</td>
<td><ol>
<li>Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución contable de la línea de pedido de compra.</li>
<li>Si <strong>Cuenta contable</strong> está seleccionado en el campo <strong>Tipo de débito</strong> en la página <strong>Código de gastos</strong>, el campo <strong>Cuenta de débito</strong> en la página <strong>Código de gastos</strong>.</li>
<li>Si se selecciona <strong>Artículo</strong> en el campo <strong>Tipo de débito</strong> de la página <strong>Código de gastos</strong>, la distribución contable para el precio total de la línea de pedido de compra.</li>
<li>Si <strong>Cliente/Proveedor</strong> contable está seleccionado en el campo <strong>Tipo de débito</strong> en la página <strong>Código de gastos</strong>, el campo <strong>Cuenta de crédito</strong> en la página <strong>Código de gastos</strong>.</li>
</ol></td>
<td><ol>
<li>Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</li>
<li>Use las dimensiones financieras de las distribuciones contables para el precio total de la línea de factura de proveedor.</li>
<li>Use los valores de dimensión financiera predeterminados de la línea de factura de proveedor.</li>
<li>Use los valores de la dimensión financiera predeterminados de la cuenta principal en la página <strong>Plan contable</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Impuestos, con la siguiente condición:
<ul>
<li>La opción <strong>Aplicar reglas impositivas de EE. UU.</strong> está seleccionada en la página <strong>Parámetros de contabilidad general</strong>.</li>
</ul></td>
<td><ol>
<li>Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución contable de la línea de pedido de compra.</li>
<li>La distribución contable del precio total o cargo.</li>
</ol></td>
<td><ol>
<li>Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</li>
<li>Use las dimensiones financieras de las distribuciones contables para el precio total de la línea de factura de proveedor.</li>
<li>Use los valores de dimensión financiera predeterminados de la línea de factura de proveedor.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Impuestos, con las siguientes condiciones:
<ul>
<li>La opción <strong>Aplicar reglas impositivas de EE. UU.</strong> está sin seleccionar en la página<strong> Parámetros de contabilidad general</strong>.</li>
<li>El campo <strong>IVA de importación</strong> para el grupo de impuestos no está seleccionado en la página <strong>Grupos de impuestos</strong>.</li>
</ul></td>
<td><ol>
<li>Si el importe de impuestos es recuperable, el campo <strong>Impuestos soportados</strong> en la página <strong>Grupos de registro</strong>.</li>
<li>Si el importe de impuestos no puede recuperarse, el precio total o la distribución contable para el cargo.</li>
</ol></td>
<td><ol>
<li>Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</li>
<li>Use las dimensiones financieras del precio total o de las distribuciones contables para el cargo en la línea de factura de proveedor.</li>
<li>Use los valores de dimensión financiera predeterminados de la línea de factura de proveedor.</li>
<li>Use los valores de la dimensión financiera predeterminados de la cuenta principal en la página <strong>Plan contable</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Impuestos, con las siguientes condiciones:
<ul>
<li>La opción Aplicar reglas impositivas de EE. UU. está sin seleccionar en la página <strong>Parámetros de contabilidad general</strong>.</li>
<li>El campo <strong>IVA de importación</strong> para el grupo de impuestos está seleccionado en la página <strong>Grupos de impuestos</strong>.</li>
</ul></td>
<td><ol>
<li>Si el importe de impuestos es recuperable, el campo <strong>Impuestos soportados</strong> en la página <strong>Grupos de registro</strong>.</li>
<li>Si el importe de impuestos no es recuperable, el campo <strong>Utilizar gasto de impuesto</strong> en la página <strong>Grupos de registro</strong>.</li>
</ol></td>
<td><ol>
<li>Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</li>
<li>Use las dimensiones financieras del precio total o de las distribuciones contables para el cargo en la línea de factura de proveedor.</li>
<li>Use los valores de dimensión financiera predeterminados de la línea de factura de proveedor.</li>
<li>Use los valores de la dimensión financiera predeterminados de la cuenta principal en la página <strong>Plan contable</strong>.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Cargo de encabezado</td>
<td><ol>
<li>Si <strong>Cuenta contable</strong> está seleccionado en el campo <strong>Tipo de débito</strong> en la página <strong>Código de gastos</strong>, el campo <strong>Cuenta de débito</strong> en la página <strong>Código de gastos</strong>.</li>
<li>Si <strong>Cliente/Proveedor</strong> contable está seleccionado en el campo <strong>Tipo de débito</strong> en la página <strong>Código de gastos</strong>, el campo <strong>Cuenta de crédito</strong> en la página <strong>Código de gastos</strong>.</li>
</ol></td>
<td><ol>
<li>Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</li>
<li>Si la cuenta principal es una cuenta de asignación, use el valor predeterminado de la definición de cuenta de asignación.</li>
<li>Use los valores de la plantilla predeterminada de la dimensión financiera del encabezado de la factura de proveedor.</li>
<li>Use los valores de dimensión financiera predeterminados de la línea de factura de proveedor.</li>
<li>Use los valores de la dimensión financiera predeterminados de la cuenta principal en la página <strong>Plan contable</strong>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Descuento de encabezado</td>
<td><ol>
<li>El campo <strong>Cuenta principal</strong> para el <strong>tipo de registro Descuento de factura de proveedor</strong> en la página <strong>Cuentas para transacciones automáticas</strong>.</li>
</ol></td>
<td><ol>
<li>Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</li>
<li>Use las dimensiones financieras de las distribuciones contables para el precio total de la línea de factura de proveedor.</li>
<li>Use los valores de dimensión financiera predeterminados de la línea de factura de proveedor.</li>
<li>Use los valores de la dimensión financiera predeterminados de la cuenta principal en la página <strong>Plan contable</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>


## <a name="distributing-taxes"></a>Distribución de impuestos

Las distribuciones contables para los impuestos no se pueden crear hasta que se calculen los impuestos. Para calcular los impuestos, debe completar una de las tareas que se describen a continuación en la página **Factura de proveedor**:
-   Ver el total de la factura.
-   Ver los impuestos.
-   Ver el subdiario contable.
-   Vea las distribuciones contables para la factura de proveedor completa.
-   Configuración de la factura de proveedor en espera.
-   Registre la factura de proveedor.

## <a name="subledger-journals-for-vendor-invoices"></a>Subdiarios contables para facturas de proveedor
Antes de registrar una factura de proveedor, puede ver el asiento contable completo de la factura, que incluye débitos y créditos, para comprobar que la factura se está registrando en las cuentas correctas. Esta visualización del asiento contable completo se denomina subdiario contable. 

Si el asiento del subdiario contable es incorrecto cuando obtiene la vista previa antes de registrar en el diario la factura de proveedor, no puede modificar el asiento del subdiario contable. En lugar de ello, se deber modificar las distribuciones contables o el perfil de registro. Las distribuciones contables se usan para definir un lado del asiento contable, el débito o el crédito. El asiento contable del subdiario contable de contrapartida se crea mediante perfiles de registro, por ejemplo, de cuenta de proveedor o impuestos.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
