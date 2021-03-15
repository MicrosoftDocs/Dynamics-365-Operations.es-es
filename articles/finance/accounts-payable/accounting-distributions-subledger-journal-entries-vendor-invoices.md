---
title: Distribuciones contables y movimientos del diario contable de las facturas de proveedores
description: Las distribuciones contables se usan para definir cómo un importe se justificará, por ejemplo, cómo se justificarán los gastos, impuestos o cargos en la factura de un proveedor. Cada importe que se debe justificar cuando se registre en el diario la factura de proveedor tendrá una o varias distribuciones contables.
author: abruer
manager: AnnBe
ms.date: 08/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendEditInvoice
audience: Application User
ms.reviewer: roschlom
ms.custom: 26891
ms.assetid: 93dc608a-b5b4-4ec3-83c2-618e3d80a583
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: da15f27c7fef6367eacc83271419b633c0cbb245
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5012297"
---
# <a name="accounting-distributions-and-journal-entries-for-vendor-invoices"></a>Distribuciones contables y movimientos del diario contable de las facturas de proveedores

[!include [banner](../includes/banner.md)]

Las distribuciones contables se usan para definir cómo un importe se justificará, por ejemplo, cómo se justificarán los gastos, impuestos o cargos en la factura de un proveedor. Cada importe que se debe justificar cuando se registre en el diario la factura de proveedor tendrá una o varias distribuciones contables. 

<a name="accounting-distributions"></a>Distribuciones contables 
-------------------------

Puede usar los siguientes botones de la página Factura de proveedor para ver y para modificar probablemente las distribuciones contables de cada importe de la factura de proveedor.
-   **Distribuir importes**: permite ver y modificar las distribuciones contables de una línea individual y todas las líneas secundarias, como impuestos o gastos. También puede ver y modificar distribuciones contables para la línea secundaria directamente desde la página Transacciones de impuestos o la página Transacciones de gastos.
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
<li>El campo Cuenta principal cuando está seleccionado Gasto de compra para el producto en la página Registro.</li>
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
<li>El campo Cuenta principal cuando está seleccionado Gasto de compra para gasto en la página Registro.</li>
</ol></td>
<td><ol>
<li>Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</li>
<li>Si la cuenta principal es una cuenta de asignación, use el valor predeterminado de la definición de cuenta de asignación.</li>
<li>Use los valores de la dimensión financiera predeterminados en la factura de proveedor.</li>
<li>Use los valores de dimensión financiera predeterminados de la línea de factura de proveedor.</li>
<li>Use los valores de la dimensión financiera predeterminados de la cuenta principal en la página Plan contable.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Activo fijo</td>
<td><ol>
<li>La distribución contable para la línea de pedido de compra, si la línea de factura de proveedor hace referencia a una línea de pedido de compra.</li>
<li>Si Adquisición está seleccionado en el campo Tipo de transacción del formulario Factura de proveedor, el campo Cuenta principal cuando Adquisición está seleccionado en la página Perfiles de contabilización de activos fijos.</li>
<li>Si Ajuste de adquisición está seleccionado en el campo Tipo de transacción, el campo Cuenta principal cuando Ajuste de adquisición está seleccionado en la página Perfiles de contabilización de activos fijos.</li>
</ol></td>
<td><ol>
<li>Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</li>
<li>Use los valores de dimensión financiera predeterminados de la línea de factura de proveedor.</li>
<li>Use los valores de la dimensión financiera predeterminados de la cuenta principal en la página Plan contable.</li>
</ol></td>
</tr>
<tr class="even">
<td>Proyecto definido en la línea de factura de proveedor</td>
<td><ol>
<li>Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución contable de la línea de pedido de compra.</li>
<li>Si Saldo está seleccionado en el campo Registrar costes - Artículo en la página Grupos de proyectos, el campo Cuenta principal cuando Coste está seleccionado en la página Configuración de registro.</li>
<li>Si Pérdidas y ganancias está seleccionado en el campo Registrar costes - Artículo en la página Grupos de proyectos, el campo Cuenta principal cuando Coste - artículo está seleccionado en la página Configuración de registro.</li>
</ol></td>
<td><ol>
<li>Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Descuento de línea</td>
<td><ol>
<li>Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución contable de la línea de pedido de compra.</li>
<li>El campo Cuenta principal cuando Descuento se selecciona en la página Registro.</li>
<li>Si una cuenta principal para un descuento no se define en el perfil de registro, la distribución contable del precio total de la línea de pedido de compra.</li>
</ol></td>
<td><ol>
<li>Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución contable para la línea de pedido de compra.</li>
<li>Use las dimensiones financieras de las distribuciones contables para el precio total de la línea de factura de proveedor.</li>
<li>Use los valores de dimensión financiera predeterminados para la línea de factura de proveedor.</li>
<li>Use los valores de la dimensión financiera predeterminados de la cuenta principal en la página Plan contable.</li>
</ol></td>
</tr>
<tr class="even">
<td>Cargo de compra, que se especifica en la ficha Precio y descuento de la línea de pedido de compra</td>
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
<li>Si Cuenta contable está seleccionado en el campo Tipo de débito en el formulario Código de gastos, el campo Cuenta de débito en la página Código de gastos.</li>
<li>Si se selecciona Artículo en el campo Tipo de débito del formulario Código de gastos, la distribución contable para el precio total de la línea de pedido de compra.</li>
<li>Si Cliente/Proveedor contable está seleccionado en el campo Tipo de débito en el formulario Código de gastos, el campo Cuenta de crédito en la página Código de gastos.</li>
</ol></td>
<td><ol>
<li>Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</li>
<li>Use las dimensiones financieras de las distribuciones contables para el precio total de la línea de factura de proveedor.</li>
<li>Use los valores de dimensión financiera predeterminados de la línea de factura de proveedor.</li>
<li>Use los valores de la dimensión financiera predeterminados de la cuenta principal en la página Plan contable.</li>
</ol></td>
</tr>
<tr class="even">
<td>Impuestos, con la siguiente condición:
<ul>
<li>La opción Aplicar reglas impositivas de EE. UU. está seleccionada en la página Parámetros de contabilidad general.</li>
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
<li>La opción Aplicar reglas impositivas de EE. UU. está sin seleccionar en la página Parámetros de contabilidad general.</li>
<li>El campo IVA de importación para el grupo de impuestos no está seleccionado en la página Grupos de impuestos.</li>
</ul></td>
<td><ol>
<li>Si el importe de impuestos es recuperable, el campo Impuestos soportados en la página Grupos de registro.</li>
<li>Si el importe de impuestos no puede recuperarse, el precio total o la distribución contable para el cargo.</li>
</ol></td>
<td><ol>
<li>Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</li>
<li>Use las dimensiones financieras del precio total o de las distribuciones contables para el cargo en la línea de factura de proveedor.</li>
<li>Use los valores de dimensión financiera predeterminados de la línea de factura de proveedor.</li>
<li>Use los valores de la dimensión financiera predeterminados de la cuenta principal en la página Plan contable.</li>
</ol></td>
</tr>
<tr class="even">
<td>Impuestos, con las siguientes condiciones:
<ul>
<li>La opción Aplicar reglas impositivas de EE. UU. está sin seleccionar en la página Parámetros de contabilidad general.</li>
<li>El campo IVA de importación para el grupo de impuestos está seleccionado en la página Grupos de impuestos.</li>
</ul></td>
<td><ol>
<li>Si el importe de impuestos es recuperable, el campo Impuestos soportados en la página Grupos de registro.</li>
<li>Si el importe de impuestos no es recuperable, el campo Utilizar gasto de impuesto en la página Grupos de registro.</li>
</ol></td>
<td><ol>
<li>Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</li>
<li>Use las dimensiones financieras del precio total o de las distribuciones contables para el cargo en la línea de factura de proveedor.</li>
<li>Use los valores de dimensión financiera predeterminados de la línea de factura de proveedor.</li>
<li>Use los valores de la dimensión financiera predeterminados de la cuenta principal en la página Plan contable.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Cargo de encabezado</td>
<td><ol>
<li>Si Cuenta contable está seleccionado en el campo Tipo de débito en el formulario Código de gastos, el campo Cuenta de débito en la página Código de gastos.</li>
<li>Si Cliente/Proveedor contable está seleccionado en el campo Tipo de débito en el formulario Código de gastos, el campo Cuenta de crédito en la página Código de gastos.</li>
</ol></td>
<td><ol>
<li>Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</li>
<li>Si la cuenta principal es una cuenta de asignación, use el valor predeterminado de la definición de cuenta de asignación.</li>
<li>Use los valores de la plantilla predeterminada de la dimensión financiera del encabezado de la factura de proveedor.</li>
<li>Use los valores de dimensión financiera predeterminados de la línea de factura de proveedor.</li>
<li>Use los valores de la dimensión financiera predeterminados de la cuenta principal en la página Plan contable.</li>
</ol></td>
</tr>
<tr class="even">
<td>Descuento de encabezado</td>
<td><ol>
<li>El campo Cuenta principal para el tipo de registro Descuento de factura de proveedor en la página Cuentas para transacciones automáticas.</li>
</ol></td>
<td><ol>
<li>Si la línea de factura hace referencia a una línea de pedido de compra, use la distribución de la cuenta para la línea de pedido de compra.</li>
<li>Use las dimensiones financieras de las distribuciones contables para el precio total de la línea de factura de proveedor.</li>
<li>Use los valores de dimensión financiera predeterminados de la línea de factura de proveedor.</li>
<li>Use los valores de la dimensión financiera predeterminados de la cuenta principal en la página Plan contable.</li>
</ol></td>
</tr>
</tbody>
</table>


<a name="distributing-taxes"></a>Distribución de impuestos
------------------

Las distribuciones contables para los impuestos no se pueden crear hasta que se calculen los impuestos. Para calcular los impuestos, debe completar una de las tareas que se describen a continuación en la página Factura de proveedor:
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