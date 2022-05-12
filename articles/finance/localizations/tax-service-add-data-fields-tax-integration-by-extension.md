---
title: Agregar campos de datos en la integración fiscal mediante el uso de extensiones
description: Este tema explica cómo usar las extensiones X++ para agregar campos de datos en la integración de impuestos.
author: qire
ms.date: 04/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 79b51812eac354072ebf2a0ef6fe8d39610c6385
ms.sourcegitcommit: 9e1129d30fc4491b82942a3243e6d580f3af0a29
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "8649112"
---
# <a name="add-data-fields-in-the-tax-integration-by-using-extension"></a>Agregar campos de datos en la integración fiscal mediante el uso una extensión

[!include [banner](../includes/banner.md)]


Este tema explica cómo usar las extensiones X++ para agregar campos de datos en la integración de impuestos. Estos campos se pueden ampliar al modelo de datos fiscales del servicio fiscal y se pueden utilizar para determinar códigos fiscales. Para más información, consulte [Agregar campos de datos en configuraciones de impuestos](tax-service-add-data-fields-tax-configurations.md).

## <a name="data-model"></a>Modelo de datos

Los datos del modelo de datos los transportan objetos y los implementan clases.

Esta es una lista de los objetos principales:

* AxClass/TaxIntegration **Document** Object
* AxClass/TaxIntegration **Line** Object
* AxClass/TaxIntegration **TaxLine** Object

La siguiente ilustración muestra cómo se relacionan estos objetos.

[![Relación de objeto de modelo de datos.](./media/tax-service-customize-image1.png)](./media/tax-service-customize-image1.png)

Un objeto **Documento** puede contener muchos objetos **Línea**. Cada objeto contiene metadatos para el servicio de impuestos.

- `TaxIntegrationDocumentObject` tiene metadatos `originAddress`, que contienen información sobre la dirección de origen, y metadatos `includingTax`, que indican si el importe de la línea incluye el impuesto.
- `TaxIntegrationLineObject` tiene metadatos `itemId`, `quantity` y `categoryId`.

> [!NOTE]
> `TaxIntegrationLineObject` también implementa objetos **Cargo**.

## <a name="integration-flow"></a>Flujo de integración

Los datos del flujo los manipulan las actividades.

### <a name="key-activities"></a>Actividades clave

* AxClass/TaxIntegration **Calculation** ActivityOnDocument
* AxClass/TaxIntegration **CurrencyExchange** ActivityOnDocument
* AxClass/TaxIntegration **DataPersistence** ActivityOnDocument
* AxClass/TaxIntegration **DataRetrieval** ActivityOnDocument
* AxClass/TaxIntegration **SettingRetrieval** ActivityOnDocument

Las actividades se ejecutan en el siguiente orden:

1. Recuperación de opciones
2. Recuperación de datos
3. Servicio de cálculo
4. Cambio de divisa
5. Persistencia de datos

Por ejemplo, extienda **Recuperación de datos** antes de **Servicio de cálculo**.

#### <a name="data-retrieval-activities"></a>Actividades de recuperación de datos

Las actividades de **Recuperación de datos** recuperan datos de la base de datos. Hay adaptadores para diferentes transacciones disponibles para recuperar datos de diferentes tablas de transacciones:

- AxClass/TaxIntegration **PurchTable** DataRetrieval
- AxClass/TaxIntegration **PurchParmTable** DataRetrieval
- AxClass/TaxIntegration **PurchREQTable** DataRetrieval
- AxClass/TaxIntegration **PurchRFQTable** DataRetrieval
- AxClass/TaxIntegration **VendInvoiceInfoTable** DataRetrieval
- AxClass/TaxIntegration **SalesTable** DataRetrieval
- AxClass/TaxIntegration **SalesParm** DataRetrieval

En estas actividades de **Recuperación de datos**, los datos se copian de la base de datos a `TaxIntegrationDocumentObject` y `TaxIntegrationLineObject`. Debido a que todas estas actividades extienden la misma clase de plantilla abstracta, tienen métodos comunes.

#### <a name="calculation-service-activities"></a>Cálculo de actividades de servicio

La actividad **Servicio de cálculo** es el vínculo entre el servicio fiscal y la integración fiscal. Esta actividad se encarga de las siguientes funciones:

1. Construir la solicitud.
2. Contabilizar la solicitud en el servicio de impuestos.
3. Obtener la respuesta del servicio de impuestos.
4. Analizar la respuesta.

Un campo de datos que agregue a la solicitud se publicará junto con otros metadatos. 

## <a name="extension-implementation"></a>Implementación de extensión

Esta sección proporciona pasos detallados que explican cómo implementar la extensión. Utiliza las dimensiones financieras **Centro de coste** y **Proyecto** como ejemplos.

### <a name="step-1-add-the-data-variable-in-the-object-class"></a>Paso 1. Agregue la variable de datos en la clase de objeto

La clase de objeto contiene la variable de datos y los métodos de acceder y fijar valores para los datos. Agregue el campo de datos a `TaxIntegrationDocumentObject` o `TaxIntegrationLineObject`, dependiendo del nivel del campo. El siguiente ejemplo usa el nivel de línea y el nombre del archivo es `TaxIntegrationLineObject_Extension.xpp`.

> [!NOTE]
> Si el campo de datos que está agregando está en el nivel del documento, cambie el nombre del archivo a `TaxIntegrationDocumentObject_Extension.xpp`.

```X++
[ExtensionOf(classStr(TaxIntegrationLineObject))]
final class TaxIntegrationLineObject_Extension
{
    private OMOperatingUnitNumber costCenter;
    private ProjId projectId;

    /// <summary>
    /// Gets a costCenter.
    /// </summary>
    /// <returns>The cost center.</returns>
    public final OMOperatingUnitNumber getCostCenter()
    {
        return this.costCenter;
    }

    /// <summary>
    /// Sets the cost center.
    /// </summary>
    /// <param name = "_value">The cost center.</param>
    public final void setCostCenter(OMOperatingUnitNumber _value)
    {
        this.costCenter = _value;
    }

    /// <summary>
    /// Gets a project ID.
    /// </summary>
    /// <returns>The project ID.</returns>
    public final ProjId getProjectId()
    {
        return this.projectId;
    }

    /// <summary>
    /// Sets the project ID.
    /// </summary>
    /// <param name = "_value">The project ID.</param>
    public final void setProjectId(ProjId _value)
    {
        this.projectId = _value;
    }
}
```

**Centro de coste** y **Proyecto** se agregan como variables privadas. Cree métodos de acceso y fijación para que estos campos de datos manipulen los datos.

### <a name="step-2-retrieve-data-from-the-database"></a>Paso 2. Recuperar datos de la base de datos

Especifique la transacción y amplíe las clases de adaptador adecuadas para recuperar los datos. Por ejemplo, si usa una transacción **Pedido de compra**, debe extender `TaxIntegrationPurchTableDataRetrieval` y `TaxIntegrationVendInvoiceInfoTableDataRetrieval`. 

> [!NOTE]
> `TaxIntegrationPurchParmTableDataRetrieval` se hereda de `TaxIntegrationPurchTableDataRetrieval`. No debe cambiarse a menos que la lógica de las tablas `purchTable` y `purchParmTable` difiera.

Si el campo de datos debe agregarse para todas las transacciones, extienda todas las clases `DataRetrieval`.

Dado que todas las actividades de **Recuperación de datos** extienden la misma clase de plantilla, las estructuras de clase, las variables y los métodos son similares.

```X++
protected TaxIntegrationDocumentObject document;

/// <summary>
/// Copies to the document.
/// </summary>
protected abstract void copyToDocument()
{
    // It is recommended to implement as:
    //
    // this.copyToDocumentByDefault();
    // this.copyToDocumentFromHeaderTable();
    // this.copyAddressToDocument();
}
 
/// <summary>
/// Copies to the current line of the document.
/// </summary>
/// <param name = "_line">The current line of the document.</param>
protected abstract void copyToLine(TaxIntegrationLineObject _line)
{
    // It is recommended to implement as:
    //
    // this.copyToLineByDefault(_line);
    // this.copyToLineFromLineTable(_line);
    // this.copyQuantityAndTransactionAmountToLine(_line);
    // this.copyAddressToLine(_line);
    // this.copyToLineFromHeaderTable(_line);
}
```

El siguiente ejemplo muestra la estructura básica cuando se utiliza la tabla `PurchTable`.

```X++
public class TaxIntegrationPurchTableDataRetrieval extends TaxIntegrationAbstractDataRetrievalTemplate
{
    protected PurchTable purchTable;
    protected PurchLine purchLine;

    // Query builder methods
    [Replaceable]
    protected SysDaQueryObject getDocumentQueryObject()
    [Replaceable]
    protected SysDaQueryObject getLineQueryObject()
    [Replaceable]
    protected SysDaQueryObject getDocumentChargeQueryObject()
    [Replaceable]
    protected SysDaQueryObject getLineChargeQueryObject()

    // Data retrieval methods
    protected void copyToDocument()
    protected void copyToDocumentFromHeaderTable()
    protected void copyToLine(TaxIntegrationLineObject _line)
    protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
    ...
}
```

Cuando se llama al método `CopyToDocument` el búfer `this.purchTable` ya existe. El propósito de este método es copiar todos los datos requeridos desde `this.purchTable` hasta el objeto `document`, mediante el método de fijación que se creó en la clase `DocumentObject`.

Asimismo, ya existe un búfer `this.purchLine` en el método `CopyToLine`. El propósito de este método es copiar todos los datos requeridos desde `this.purchLine` hasta el objeto `_line`, mediante el método de fijación que se creó en la clase `LineObject`.

El enfoque más sencillo es ampliar los métodos `CopyToDocument` y `CopyToLine`. Sin embargo, se recomienda probar primero los métodos `copyToDocumentFromHeaderTable` y `copyToLineFromLineTable`. Si no funcionan como necesita, implemente su propio método y llámelo en `CopyToDocument` y `CopyToLine`. Hay tres situaciones comunes en las que puede utilizar este enfoque:

- El campo requerido está en `PurchTable` o `PurchLine`. En esta situación, puede extender `copyToDocumentFromHeaderTable` y `copyToLineFromLineTable`. Aquí está el código de ejemplo.

    ```X++
    /// <summary>
    /// Copies to the current line of the document from.
    /// </summary>
    /// <param name = "_line">The current line of the document.</param>
    protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
    {
        next copyToLineFromLineTable(_line);
        // if we already added XXX in TaxIntegrationLineObject
        _line.setXXX(this.purchLine.XXX);
    }
    ```

- Los datos requeridos no están en la tabla predeterminada de la transacción. Sin embargo, existen algunas relaciones de unión con la tabla predeterminada y el campo es obligatorio en la mayoría de las líneas. En esta situación, reemplace `getDocumentQueryObject` o `getLineObject` para consultar la tabla por relación de unión. En el siguiente ejemplo, el campo **Entregar ahora** está integrado con el pedido de ventas a nivel de línea.

    ```X++
    public class TaxIntegrationSalesTableDataRetrieval
    {
        protected MCRSalesLineDropShipment mcrSalesLineDropShipment;

        /// <summary>
        /// Gets the query for the lines of the document.
        /// </summary>
        /// <returns>The query for the lines of the document</returns>
        [Replaceable]
        protected SysDaQueryObject getLineQueryObject()
        {
            return SysDaQueryObjectBuilder::from(this.salesLine)
                .where(this.salesLine, fieldStr(SalesLine, SalesId)).isEqualToLiteral(this.salesTable.SalesId)
                .outerJoin(this.mcrSalesLineDropShipment)
                .where(this.mcrSalesLineDropShipment, fieldStr(MCRSalesLineDropShipment, SalesLine)).isEqualTo(this.salesLine, fieldStr(SalesLine, RecId))
                .toSysDaQueryObject();
        }
    }
    ```

    En este ejemplo, se declara un búfer `mcrSalesLineDropShipment` y la consulta se define en `getLineQueryObject`. La consulta usa la relación `MCRSalesLineDropShipment.SalesLine == SalesLine.RecId`. Mientras se extiende en esta situación, puede reemplazar `getLineQueryObject` con su propio objeto de consulta construido. No obstante, tenga en cuenta los puntos siguientes:

    * Como el valor de retorno del método `getLineQueryObject` es `SysDaQueryObject`, debe construir este objeto utilizando el enfoque SysDa.
    * No se puede eliminar la tabla existente.

- Los datos requeridos están relacionados con la tabla de transacciones por una relación de unión complicada, o la relación no es uno a uno (1:1) sino uno a muchos (1:N). En esta situación, las cosas se complican un poco. Esta situación se aplica al ejemplo de las dimensiones financieras. 

    En esta situación, puede implementar su propio método para recuperar los datos. Aquí está el código de muestra, en el archivo `TaxIntegrationPurchTableDataRetrieval_Extension.xpp`.

    ```X++
    [ExtensionOf(classStr(TaxIntegrationPurchTableDataRetrieval))]
    final class TaxIntegrationPurchTableDataRetrieval_Extension
    {
        private const str CostCenterKey = 'CostCenter';
        private const str ProjectKey = 'Project';

        /// <summary>
        /// Copies to the current line of the document from.
        /// </summary>
        /// <param name = "_line">The current line of the document.</param>
        protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
        {
            Map dimensionAttributeMap = this.getDimensionAttributeMapByDefaultDimension(this.purchline.DefaultDimension);
            if (dimensionAttributeMap.exists(CostCenterKey))
            {
                _line.setCostCenter(dimensionAttributeMap.lookup(CostCenterKey));
            }
            if (dimensionAttributeMap.exists(ProjectKey))
            {
                _line.setProjectId(dimensionAttributeMap.lookup(ProjectKey));
            }
            next copyToLineFromLineTable(_line);
        }
        private Map getDimensionAttributeMapByDefaultDimension(RefRecId _defaultDimension)
        {
            DimensionAttribute dimensionAttribute;
            DimensionAttributeValue dimensionAttributeValue;
            DimensionAttributeValueSetItem dimensionAttributeValueSetItem;
            Map ret = new Map(Types::String, Types::String);

            select Name, RecId from dimensionAttribute
                join dimensionAttributeValue
                    where dimensionAttributeValue.dimensionAttribute == dimensionAttribute.RecId
                join DimensionAttributeValueSetItem
                    where DimensionAttributeValueSetItem.DimensionAttributeValue == DimensionAttributeValue.RecId
                        && DimensionAttributeValueSetItem.DimensionAttributeValueSet == _defaultDimension;

            while(dimensionAttribute.RecId)
            {
                ret.insert(dimensionAttribute.Name, dimensionAttributeValue.DisplayValue);
                next dimensionAttribute;
            }
            return ret;
        }
    }
    ```

### <a name="step-3-add-data-to-the-request"></a>Paso 3. Agregar datos a la solicitud

Extienda el método `copyToTaxableDocumentHeaderWrapperFromTaxIntegrationDocumentObject` o `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` para agregar datos a la solicitud. Aquí está el código de muestra, en el archivo `TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp`.

```X++
[ExtensionOf(classStr(TaxIntegrationCalculationActivityOnDocument_CalculationService))]
final static class TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension
{
    // Define the field name in the request
    private const str IOCostCenter = 'Cost Center';
    private const str IOProject = 'Project';
    // private const str IOEnumExample = 'Enum Example';

    /// <summary>
    /// Copies to <c>TaxableDocumentLineWrapper</c> from <c>TaxIntegrationLineObject</c> by line.
    /// </summary>
    /// <param name = "_destination"><c>TaxableDocumentLineWrapper</c>.</param>
    /// <param name = "_source"><c>TaxIntegrationLineObject</c>.</param>
    protected static void copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(Microsoft.Dynamics.TaxCalculation.ApiContracts.TaxableDocumentLineWrapper _destination, TaxIntegrationLineObject _source)
    {
        next copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(_destination, _source);
        // Set the field we need to integrated for tax service
        _destination.SetField(IOCostCenter, _source.getCostCenter());
        _destination.SetField(IOProject, _source.getProjectId());

        // If the field to be extended is an enum type, use enum2Symbol to convert an enum variable exampleEnum of ExampleEnumType to a string
        // _destination.SetField(IOEnumExample, enum2Symbol(enumNum(ExampleEnumType), _source.getExampleEnum()));
    }
}
```

En este código, `_destination` es el objeto contenedor que se utiliza para generar la solicitud, y `_source` es el objeto `TaxIntegrationLineObject`.

> [!NOTE]
> Defina el nombre del campo que se utiliza en la solicitud como **private const str**. La cadena debe ser exactamente igual que el nombre del nodo (no la etiqueta) agregado en el tema [Agregar campos de datos en configuraciones de impuestos](tax-service-add-data-fields-tax-configurations.md).
> 
> Establezca el campo en el método **copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine** usando el método **SetField**. El tipo de datos del segundo parámetro debe ser **cadena**. Si el tipo de datos no es **cadena**, conviértalo en cadena.
> Si el tipo de datos es X++ **tipo de enumeración**, le recomendamos que utilice el método **enum2Symbol** para convertir el valor de enumeración en una cadena. El valor de enumeración agregado en la configuración de impuestos debe ser exactamente el mismo que el nombre de enumeración. La siguiente es una lista de diferencias entre el valor de enumeración, la etiqueta y el nombre.
> 
>   - El nombre de enumeración es un nombre simbólico en el código. **enum2Symbol()** puede convertir el valor de enumeración a su nombre.
>   - El valor de la enumeración es un entero.
>   - La etiqueta de la enumeración puede ser diferente en los idiomas preferidos. **enum2Str()** puede convertir el valor de enumeración a su etiqueta.

## <a name="model-dependency"></a>Dependencia del modelo

Para compilar correctamente el proyecto, agregue los siguientes modelos de referencia a las dependencias del modelo:

- ApplicationPlatform
- ApplicationSuite
- Motor de impuestos
- Dimensiones, si se utiliza la dimensión financiera
- Otros modelos necesarios referenciados en el código

## <a name="validation"></a>Validación

Después de completar los pasos anteriores, puede validar sus cambios.

1. En finanzas, vaya a **Proveedores** y agregue **&debug=vs%2CconfirmExit&** a la URL. Por ejemplo, https://usnconeboxax1aos.cloud.onebox.dynamics.com/?cmp=DEMF&mi=PurchTableListPage&debug=vs%2CconfirmExit&. El **&** final es esencial.
2. Abra la página **Pedido de compra** y seleccione **Nuevo** para crear un pedido de compra.
3. Establezca el valor para el campo personalizado y luego seleccione **Impuesto de ventas**. Un archivo de solución de problemas con prefijo, **TaxServiceTroubleshootingLog**, se descarga automáticamente. Este archivo contiene la información de la transacción enviada al Servicio de cálculo de impuestos. 
4. Compruebe si el campo personalizado añadido está presente en la sección **Entrada de cálculo del servicio de impuestos JSON** y si su valor es correcto. Si el valor no es correcto, vuelva a comprobar los pasos de este documento.

Archivo de ejemplo:

```
===Tax service calculation input JSON:===
{
  "TaxableDocument": {
    "Header": [
      {
        "Lines": [
          {
            "Line Type": "Normal",
            "Item Code": "",
            "Item Type": "Item",
            "Quantity": 0.0,
            "Amount": 1000.0,
            "Currency": "EUR",
            "Transaction Date": "2022-1-26T00:00:00",
            ...
            /// The new fields added at line level
            "Cost Center": "003",
            "Project": "Proj-123"
          }
        ],
        "Amount include tax": true,
        "Business Process": "Journal",
        "Currency": "",
        "Vendor Account": "DE-001",
        "Vendor Invoice Account": "DE-001",
        ...
        // The new fields added at header level, no new fields in this example
        ...
      }
    ]
  },
}
...
```

## <a name="appendix"></a>Apéndice

Este apéndice muestra el código de muestra completo para la integración de dimensiones financieras, **Centro de cose** y **Proyecto**, a nivel de línea.

### <a name="taxintegrationlineobject_extensionxpp"></a>TaxIntegrationLineObject_Extension.xpp

```X++
[ExtensionOf(classStr(TaxIntegrationLineObject))]
final class TaxIntegrationLineObject_Extension
{
    private OMOperatingUnitNumber costCenter;
    private ProjId projectId;

    /// <summary>
    /// Gets a costCenter.
    /// </summary>
    /// <returns>The cost center.</returns>
    public final OMOperatingUnitNumber getCostCenter()
    {
        return this.costCenter;
    }

    /// <summary>
    /// Sets the cost center.
    /// </summary>
    /// <param name = "_value">The cost center.</param>
    public final void setCostCenter(OMOperatingUnitNumber _value)
    {
        this.costCenter = _value;
    }

    /// <summary>
    /// Gets a project ID.
    /// </summary>
    /// <returns>The project ID.</returns>
    public final ProjId getProjectId()
    {
        return this.projectId;
    }

    /// <summary>
    /// Sets the project ID.
    /// </summary>
    /// <param name = "_value">The project ID.</param>
    public final void setProjectId(ProjId _value)
    {
        this.projectId = _value;
    }
}
```

### <a name="taxintegrationpurchtabledataretrieval_extensionxpp"></a>TaxIntegrationPurchTableDataRetrieval_Extension.xpp

```X++
[ExtensionOf(classStr(TaxIntegrationPurchTableDataRetrieval))]
final class TaxIntegrationPurchTableDataRetrieval_Extension
{
    private const str CostCenterKey = 'CostCenter';
    private const str ProjectKey = 'Project';

    /// <summary>
    /// Copies to the current line of the document from.
    /// </summary>
    /// <param name = "_line">The current line of the document.</param>
    protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
    {
        Map dimensionAttributeMap = this.getDimensionAttributeMapByDefaultDimension(this.purchline.DefaultDimension);
        if (dimensionAttributeMap.exists(CostCenterKey))
        {
            _line.setCostCenter(dimensionAttributeMap.lookup(CostCenterKey));
        }
        if (dimensionAttributeMap.exists(ProjectKey))
        {
            _line.setProjectId(dimensionAttributeMap.lookup(ProjectKey));
        }
        next copyToLineFromLineTable(_line);
    }
    private Map getDimensionAttributeMapByDefaultDimension(RefRecId _defaultDimension)
    {
        DimensionAttribute dimensionAttribute;
        DimensionAttributeValue dimensionAttributeValue;
        DimensionAttributeValueSetItem dimensionAttributeValueSetItem;
        Map ret = new Map(Types::String, Types::String);
        select Name, RecId from dimensionAttribute
            join dimensionAttributeValue
                where dimensionAttributeValue.dimensionAttribute == dimensionAttribute.RecId
            join DimensionAttributeValueSetItem
                where DimensionAttributeValueSetItem.DimensionAttributeValue == DimensionAttributeValue.RecId
                    && DimensionAttributeValueSetItem.DimensionAttributeValueSet == _defaultDimension;
        while(dimensionAttribute.RecId)
        {
            ret.insert(dimensionAttribute.Name, dimensionAttributeValue.DisplayValue);
            next dimensionAttribute;
        }
        return ret;
    }
}
```

### <a name="taxintegrationcalculationactivityondocument_calculationservice_extensionxpp"></a>TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp

```X++
[ExtensionOf(classStr(TaxIntegrationCalculationActivityOnDocument_CalculationService))]
final static class TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension
{
    // Define the field name in the request
    private const str IOCostCenter = 'Cost Center';
    private const str IOProject = 'Project';

    /// <summary>
    /// Copies to <c>TaxableDocumentLineWrapper</c> from <c>TaxIntegrationLineObject</c> by line.
    /// </summary>
    /// <param name = "_destination"><c>TaxableDocumentLineWrapper</c>.</param>
    /// <param name = "_source"><c>TaxIntegrationLineObject</c>.</param>
    protected static void copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(Microsoft.Dynamics.TaxCalculation.ApiContracts.TaxableDocumentLineWrapper _destination, TaxIntegrationLineObject _source)
    {
        next copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(_destination, _source);
        // Set the field we need to integrated for tax service
        _destination.SetField(IOCostCenter, _source.getCostCenter());
        _destination.SetField(IOProject, _source.getProjectId());
    }
}
```
