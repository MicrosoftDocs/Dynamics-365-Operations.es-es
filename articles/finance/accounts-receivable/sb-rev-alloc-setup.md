---
title: Configurar la asignación de ingresos de varios elementos
description: Este tema describe cómo configurar los parámetros para la asignación de ingresos de elementos múltiples en la facturación de suscripción.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: e422b16d1c4505b2837bb282918ecada902b806e
ms.sourcegitcommit: 23588e66e25c05e989f3212ac519d7016820430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2022
ms.locfileid: "8566368"
---
# <a name="set-up-multiple-element-revenue-allocation"></a>Configurar la asignación de ingresos de varios elementos

La asignación de ingresos de elementos múltiples le permite configurar diferentes plantillas que se utilizan para calcular y asignar ingresos en varios elementos. Esta funcionalidad puede ayudarle a cumplir con el Tema 606 de la Codificación de Normas de Contabilidad (ASC 606) y/o la Norma Internacional de Información Financiera 15 (IFRS 15).

## <a name="multiple-element-revenue-allocation-parameters"></a>Parámetros de asignación de ingresos de varios elementos

Utilice la página **Parámetros de asignación de ingresos de elementos múltiples** para configurar los parámetros para la asignación de ingresos de elementos múltiples.

### <a name="standalone-selling-price-origin"></a>Origen de precio de venta individual

El campo **Origen del precio de venta independiente** determina de dónde proviene el precio de venta independiente. Puede actualizar el valor en la página **Precio de venta independiente del artículo** y en la transacción. Están disponibles las siguientes opciones.

| Opción | Description |
|--------|-------------|
| Importe | El precio de venta independiente es una cantidad que usted especifica que es mayor que 0 (cero). El importe se convierte entre las monedas funcional y de origen, según sea necesario. |
| Precio de venta base | El precio de venta independiente coincide con el precio de venta base del artículo. |
| Precio de la factura | El precio de venta independiente coincide con el precio de factura del artículo. |
| Porcentaje del artículo | El precio de venta independiente se especifica como un valor porcentual y se calcula en función del precio del artículo. Si seleccione esta opción, especifique el porcentaje predeterminado. |
| Asignar cantidad residual | <p>El origen del precio de venta independiente se calcula como *Valor total del contrato del artículo principal*: *precio de venta independiente total de artículos secundarios*:</p><ul><li>El *Valor total del contrato del artículo primario* es el importe neto o facturado.</li><li>El *Precio de venta independiente total de artículos secundarios* es la suma del precio de venta independiente extendido o del contrato de todos los artículos secundarios, excepto el artículo secundario que utiliza este origen de precio de venta independiente.</li></ul><p>Si la cantidad calculada es un valor negativo, la cantidad se establece en 0 (cero).</p><p>**Nota:** esta opción se puede seleccionar solo para un artículo secundario en la división de ingresos.</p> |
| Ninguna | El origen del precio de venta independiente se basa en los artículos secundarios. Esta opción se aplica a los artículos que se definen como artículos primarios en una plantilla de división de ingresos. Si la casilla **División de ingresos** está seleccionada, esta opción se selecciona automáticamente y la configuración no se puede cambiar. |
| Porcentaje de precio de factura primaria | El origen del precio de venta independiente es un porcentaje del precio de factura del artículo primario. Puede cambiar el valor predeterminado. Esta opción solo está disponible para artículos secundarios en una plantilla de división de ingresos. |
| Porcentaje de precio estándar primario | El origen del precio de venta independiente es un porcentaje del precio estándar del artículo primario. Puede cambiar el valor predeterminado. Esta opción solo está disponible para artículos secundarios en una plantilla de división de ingresos. Es la opción predeterminada para elementos secundarios. Cuando la opción para un artículo secundario se cambia de **Porcentaje del precio estándar principal** a **Porcentaje del precio de la factura primaria**, o de **Porcentaje del precio de la factura primaria** a **Porcentaje del precio estándar primario**, los valores calculados también se actualizan. |

### <a name="account-for-revenue-allocation-rounding-differences"></a>Cuenta para diferencias de redondeo de asignación de ingresos

El campo **Cuenta para diferencias de redondeo de asignación de ingresos** especifica la cuenta que se utiliza para registrar cualquier ajuste de redondeo a un importe de ingresos del contrato. Está disponible cuando se utiliza la facturación de contratos periódicos.

## <a name="item-standalone-selling-price"></a>Precio de venta individual de artículo

Utilice la página **Precio de venta independiente del artículo** para especificar el origen y el precio de venta independiente de un artículo. Los valores que se especifican en esta página se utilizan como valores predeterminados en la página **Asignación de ingresos** en la asignación de ingresos de elementos múltiples y la facturación de contratos periódicos.

### <a name="specify-item-standalone-selling-price"></a>Especificar el precio de venta independiente del artículo

Para especificar el precio independiente de un artículo, siga estos pasos.

1. En la página **Precio de venta independiente del artículo**, en el campo **Origen del precio de venta independiente**, seleccione el origen del precio de venta independiente.
2. Siga uno de estos pasos, según el valor seleccionado en el campo **Origen del precio de venta independiente**:

    * Si seleccionó **Porcentaje de artículo**, especifique el porcentaje en el campo **Porcentaje**.
    * Si seleccionó **Importe**, especifique el importe en el campo **Precio de venta independiente**.

2. Para cada elemento que desee agregar a la lista, seleccione **Agregar**.
3. En el campo **Código de artículo**, seleccione el código de artículo. En el campo **Relación de artículo**, seleccione la relación de artículo. Para artículos donde no esté seleccionada la casilla **División de ingresos**, la combinación seleccionada de un código de artículo y una relación de artículo debe ser única.
4. Cambie el valor predeterminado del campo **Origen del precio de venta independiente**, **Precio de venta independiente** o **Porcentaje** según sea necesario.
5. Para cada elemento primario que desee agregar a la lista, seleccione **Agregar**.
6. En el campo **Código de artículo**, seleccione el código de artículo. En el campo **Relación de artículo**, seleccione la relación de artículo.
7. Seleccione la casilla **División de ingresos**.
8. En el campo **Relación de artículo**, seleccione la relación de artículo. La lista se actualiza con el elemento primario y todos los elementos secundarios.
9. Para el elemento secundario, cambie el valor predeterminado del campo **Origen del precio de venta independiente**, **Porcentaje del precio estándar principal**, **Porcentaje del precio de la factura primaria** o **Asignar cantidad residual** conforme necesite.
10. Para agregar varios artículos a la vez, seleccione **Agregar artículos**.
11. Actualice la consulta para seleccionar el rango de elementos que desea agregar.
12. Seleccione **Aceptar**, revise la lista de elementos que agregó y seleccione **Aceptar**.

### <a name="fields"></a>Campos

La página **Precio de venta independiente del artículo** contiene los siguientes campos.

| Campo | Description |
|-------|-------------|
| Origen de precio de venta individual | <p>Seleccione el origen del precio de venta independiente:</p><ul><li>**Importe**: el precio de venta independiente es un importe que usted especifica que es mayor que 0 (cero). El importe se convierte entre las monedas funcional y de origen, según sea necesario.</li><li>**Precio de venta base**: el precio de venta independiente coincide con el precio de venta base del artículo.</li><li>**Precio de factura**: el precio de venta independiente coincide con el precio de factura del artículo.</li><li>**Porcentaje del artículo**: el precio de venta independiente se especifica como un valor porcentual y se calcula en función del precio del artículo. Si seleccione esta opción, especifique el porcentaje predeterminado.</li></ul>**Importe residual asignado**: el origen del precio de venta independiente se calcula como *Valor total del contrato del artículo principal* o *Precio de venta independiente total de artículos secundarios*:</p><ul><li>El *Valor total del contrato del artículo primario* es el importe neto o facturado.</li><li>El *Precio de venta independiente total de artículos secundarios* es la suma del precio de venta independiente extendido o del contrato de todos los artículos secundarios, excepto el artículo secundario que utiliza este origen de precio de venta independiente.</li></ul><p>Si la cantidad calculada es un valor negativo, la cantidad se establece en 0 (cero).</p><p>**Nota:** esta opción se puede seleccionar solo para un artículo secundario en la división de ingresos.</p></li><li>**Ninguno**: el origen del precio de venta independiente se basa en los artículos secundarios. Esta opción se aplica a los artículos que se definen como artículos primarios en una plantilla de división de ingresos. Si la casilla **División de ingresos** está seleccionada, esta opción se selecciona automáticamente y la configuración no se puede cambiar.</li><li>**Porcentaje del precio de la factura primaria**: el origen del precio de venta independiente es un porcentaje del precio de factura del artículo primario. Puede cambiar el valor predeterminado. Esta opción solo está disponible para artículos secundarios en una plantilla de división de ingresos.</li><li>**Porcentaje del precio estándar primario**: el origen del precio de venta independiente es un porcentaje del precio estándar del artículo primario. Puede cambiar el valor predeterminado. Esta opción solo está disponible para artículos secundarios en una plantilla de división de ingresos. Es la opción predeterminada para elementos secundarios. Cuando la opción para un artículo secundario se cambia de **Porcentaje del precio estándar principal** a **Porcentaje del precio de la factura primaria**, o de **Porcentaje del precio de la factura primaria** a **Porcentaje del precio estándar primario**, los valores calculados también se actualizan.</li></ul> |
| Precio de venta individual | Especifique el precio de venta independiente del artículo: Este campo está disponible cuando el campo **Origen del precio de venta independiente** se establece en **Importe**. |
| Porcentaje | Especifique el porcentaje del pecio de venta independiente. Este campo está disponible cuando el campo **Origen del precio de venta independiente** se establece en **Porcentaje de artículo**, **Porcentaje del precio de la factura primaria** o **Porcentaje del precio estándar primario**. |
| División de ingresos | <p>Especifique si una línea utiliza la división de ingresos:</p><ul><li>**Seleccionado**: solo los artículos para los que se ha configurado una plantilla de división de ingresos se pueden seleccionar en el campo **Relación de artículo**. Puede seleccionar esta casilla solo para los artículos principales de una plantilla de división de ingresos.</li><li>**Borrado**: el artículo es un artículo estándar que no utiliza división de ingresos.</li></ul> |
| Relación | Un símbolo indica si el artículo es un artículo primario o secundario en una división de ingresos. |
| Código de artículo | <p>Seleccione el código de artículo: **Tabla** o **Grupo**.</p><p>Si la casilla **División de ingresos** está seleccionada, este campo se establece en **Tabla** y el valor no se puede cambiar.</p> |
| Relación de artículos | <p>Seleccione un número de artículo.</p><p>Si la casilla **División de ingresos** está seleccionada, solo los artículos que son artículos primarios para los que se ha configurado una plantilla de división de ingresos están disponibles para la selección. Si se selecciona el artículo principal, la lista se actualiza automáticamente con los artículos secundarios de ese artículo primario.</p> |
| Artículo primario | Para el artículo primario, este campo muestra el número de artículo. Para artículos secundarios en una división de ingresos, muestra el número de artículo del artículo primario. |

## <a name="mea-templates"></a>Plantillas de MEA

Utilice la página **Plantillas MEA** para crear y editar los id. de plantilla de disposición de elementos múltiples (MEA). Estos id. se utilizan en la página **Asignación de ingresos** para agrupar elementos entre sí.

### <a name="create-a-template"></a>Crear una plantilla

Para configurar una plantilla MEA, siga estos pasos.

1. En la página **Plantillas MEA**, seleccione **Nueva**.
1. En el campo **Id. de plantilla MEA**, especifique un id. único.
1. En el campo **Descripción**, escriba una descripción.
1. En el campo **Cuenta de ingresos aplazados del contrato** seleccione la cuenta que desea usar para los asientos de diario cuando se crea una factura de contrato MEA. Este campo está disponible cuando la facturación de contratos periódicos está habilitada y se utiliza.
1. Seleccione **Guardar**.
