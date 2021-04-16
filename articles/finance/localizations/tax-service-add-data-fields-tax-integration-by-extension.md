---
title: Agregar campos de datos en la integración fiscal mediante el uso de extensiones
description: Este tema explica cómo usar las extensiones X++ para agregar campos de datos en la integración de impuestos.
author: qire
ms.date: 03/26/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: fdf112bbdd5245d19ab1d07cfcf94c58bf8208c5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830349"
---
# <a name="add-data-fields-in-the-tax-integration-by-using-extension"></a><span data-ttu-id="ecb55-103">Agregar campos de datos en la integración fiscal mediante el uso una extensión</span><span class="sxs-lookup"><span data-stu-id="ecb55-103">Add data fields in the tax integration by using extension</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="ecb55-104">Este tema explica cómo usar las extensiones X++ para agregar campos de datos en la integración de impuestos.</span><span class="sxs-lookup"><span data-stu-id="ecb55-104">This topic explains how to use X++ extensions to add data fields in the tax integration.</span></span> <span data-ttu-id="ecb55-105">Estos campos se pueden ampliar al modelo de datos fiscales del servicio fiscal y se pueden utilizar para determinar códigos fiscales.</span><span class="sxs-lookup"><span data-stu-id="ecb55-105">These fields can be extended to the tax data model of the tax service and used to determine tax codes.</span></span> <span data-ttu-id="ecb55-106">Para más información, consulte [Agregar campos de datos en configuraciones de impuestos](tax-service-add-data-fields-tax-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="ecb55-106">For more information, see [Add data fields in tax configurations](tax-service-add-data-fields-tax-configurations.md).</span></span>

## <a name="data-model"></a><span data-ttu-id="ecb55-107">Modelo de datos</span><span class="sxs-lookup"><span data-stu-id="ecb55-107">Data model</span></span>

<span data-ttu-id="ecb55-108">Los datos del modelo de datos los transportan objetos y los implementan clases.</span><span class="sxs-lookup"><span data-stu-id="ecb55-108">The data in the data model is carried by objects and implemented by classes.</span></span>

<span data-ttu-id="ecb55-109">Esta es una lista de los objetos principales:</span><span class="sxs-lookup"><span data-stu-id="ecb55-109">Here is a list of the major objects:</span></span>

* <span data-ttu-id="ecb55-110">AxClass/TaxIntegration **Document** Object</span><span class="sxs-lookup"><span data-stu-id="ecb55-110">AxClass/TaxIntegration **Document** Object</span></span>
* <span data-ttu-id="ecb55-111">AxClass/TaxIntegration **Line** Object</span><span class="sxs-lookup"><span data-stu-id="ecb55-111">AxClass/TaxIntegration **Line** Object</span></span>
* <span data-ttu-id="ecb55-112">AxClass/TaxIntegration **TaxLine** Object</span><span class="sxs-lookup"><span data-stu-id="ecb55-112">AxClass/TaxIntegration **TaxLine** Object</span></span>

<span data-ttu-id="ecb55-113">La siguiente ilustración muestra cómo se relacionan estos objetos.</span><span class="sxs-lookup"><span data-stu-id="ecb55-113">The following illustration shows how these objects are related.</span></span>

<span data-ttu-id="ecb55-114">[![Relación de objeto de modelo de datos](./media/tax-service-customize-image1.png)](./media/tax-service-customize-image1.png)</span><span class="sxs-lookup"><span data-stu-id="ecb55-114">[![Data model object relationship](./media/tax-service-customize-image1.png)](./media/tax-service-customize-image1.png)</span></span>

<span data-ttu-id="ecb55-115">Un objeto **Documento** puede contener muchos objetos **Línea**.</span><span class="sxs-lookup"><span data-stu-id="ecb55-115">A **Document** object can contain many **Line** objects.</span></span> <span data-ttu-id="ecb55-116">Cada objeto contiene metadatos para el servicio de impuestos.</span><span class="sxs-lookup"><span data-stu-id="ecb55-116">Each object contains metadata for the tax service.</span></span>

- <span data-ttu-id="ecb55-117">`TaxIntegrationDocumentObject` tiene metadatos `originAddress`, que contienen información sobre la dirección de origen, y metadatos `includingTax`, que indican si el importe de la línea incluye el impuesto.</span><span class="sxs-lookup"><span data-stu-id="ecb55-117">`TaxIntegrationDocumentObject` has `originAddress` metadata, which contains information about the source address, and `includingTax` metadata, which indicates whether the line amount includes sales tax.</span></span>
- <span data-ttu-id="ecb55-118">`TaxIntegrationLineObject` tiene metadatos `itemId`, `quantity` y `categoryId`.</span><span class="sxs-lookup"><span data-stu-id="ecb55-118">`TaxIntegrationLineObject` has `itemId`, `quantity`, and `categoryId` metadata.</span></span>

> [!NOTE]
> <span data-ttu-id="ecb55-119">`TaxIntegrationLineObject` también implementa objetos **Cargo**.</span><span class="sxs-lookup"><span data-stu-id="ecb55-119">`TaxIntegrationLineObject` also implements **Charge** objects.</span></span>

## <a name="integration-flow"></a><span data-ttu-id="ecb55-120">Flujo de integración</span><span class="sxs-lookup"><span data-stu-id="ecb55-120">Integration flow</span></span>

<span data-ttu-id="ecb55-121">Los datos del flujo los manipulan las actividades.</span><span class="sxs-lookup"><span data-stu-id="ecb55-121">The data in the flow is manipulated by activities.</span></span>

### <a name="key-activities"></a><span data-ttu-id="ecb55-122">Actividades clave</span><span class="sxs-lookup"><span data-stu-id="ecb55-122">Key activities</span></span>

* <span data-ttu-id="ecb55-123">AxClass/TaxIntegration **Calculation** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="ecb55-123">AxClass/TaxIntegration **Calculation** ActivityOnDocument</span></span>
* <span data-ttu-id="ecb55-124">AxClass/TaxIntegration **CurrencyExchange** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="ecb55-124">AxClass/TaxIntegration **CurrencyExchange** ActivityOnDocument</span></span>
* <span data-ttu-id="ecb55-125">AxClass/TaxIntegration **DataPersistence** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="ecb55-125">AxClass/TaxIntegration **DataPersistence** ActivityOnDocument</span></span>
* <span data-ttu-id="ecb55-126">AxClass/TaxIntegration **DataRetrieval** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="ecb55-126">AxClass/TaxIntegration **DataRetrieval** ActivityOnDocument</span></span>
* <span data-ttu-id="ecb55-127">AxClass/TaxIntegration **SettingRetrieval** ActivityOnDocument</span><span class="sxs-lookup"><span data-stu-id="ecb55-127">AxClass/TaxIntegration **SettingRetrieval** ActivityOnDocument</span></span>

<span data-ttu-id="ecb55-128">Las actividades se ejecutan en el siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="ecb55-128">Activities are run in the following order:</span></span>

1. <span data-ttu-id="ecb55-129">Recuperación de opciones</span><span class="sxs-lookup"><span data-stu-id="ecb55-129">Setting Retrieval</span></span>
2. <span data-ttu-id="ecb55-130">Recuperación de datos</span><span class="sxs-lookup"><span data-stu-id="ecb55-130">Data Retrieval</span></span>
3. <span data-ttu-id="ecb55-131">Servicio de cálculo</span><span class="sxs-lookup"><span data-stu-id="ecb55-131">Calculation Service</span></span>
4. <span data-ttu-id="ecb55-132">Cambio de divisa</span><span class="sxs-lookup"><span data-stu-id="ecb55-132">Currency Exchange</span></span>
5. <span data-ttu-id="ecb55-133">Persistencia de datos</span><span class="sxs-lookup"><span data-stu-id="ecb55-133">Data Persistence</span></span>

<span data-ttu-id="ecb55-134">Por ejemplo, extienda **Recuperación de datos** antes de **Servicio de cálculo**.</span><span class="sxs-lookup"><span data-stu-id="ecb55-134">For example, extend **Data Retrieval** before **Calculation Service**.</span></span>

#### <a name="data-retrieval-activities"></a><span data-ttu-id="ecb55-135">Actividades de recuperación de datos</span><span class="sxs-lookup"><span data-stu-id="ecb55-135">Data Retrieval activities</span></span>

<span data-ttu-id="ecb55-136">Las actividades de **Recuperación de datos** recuperan datos de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="ecb55-136">**Data Retrieval** activities retrieve data from the database.</span></span> <span data-ttu-id="ecb55-137">Hay adaptadores para diferentes transacciones disponibles para recuperar datos de diferentes tablas de transacciones:</span><span class="sxs-lookup"><span data-stu-id="ecb55-137">Adapters for different transactions are available to retrieve data from different transaction tables:</span></span>

- <span data-ttu-id="ecb55-138">AxClass/TaxIntegration **PurchTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="ecb55-138">AxClass/TaxIntegration **PurchTable** DataRetrieval</span></span>
- <span data-ttu-id="ecb55-139">AxClass/TaxIntegration **PurchParmTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="ecb55-139">AxClass/TaxIntegration **PurchParmTable** DataRetrieval</span></span>
- <span data-ttu-id="ecb55-140">AxClass/TaxIntegration **PurchREQTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="ecb55-140">AxClass/TaxIntegration **PurchREQTable** DataRetrieval</span></span>
- <span data-ttu-id="ecb55-141">AxClass/TaxIntegration **PurchRFQTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="ecb55-141">AxClass/TaxIntegration **PurchRFQTable** DataRetrieval</span></span>
- <span data-ttu-id="ecb55-142">AxClass/TaxIntegration **VendInvoiceInfoTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="ecb55-142">AxClass/TaxIntegration **VendInvoiceInfoTable** DataRetrieval</span></span>
- <span data-ttu-id="ecb55-143">AxClass/TaxIntegration **SalesTable** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="ecb55-143">AxClass/TaxIntegration **SalesTable** DataRetrieval</span></span>
- <span data-ttu-id="ecb55-144">AxClass/TaxIntegration **SalesParm** DataRetrieval</span><span class="sxs-lookup"><span data-stu-id="ecb55-144">AxClass/TaxIntegration **SalesParm** DataRetrieval</span></span>

<span data-ttu-id="ecb55-145">En estas actividades de **Recuperación de datos**, los datos se copian de la base de datos a `TaxIntegrationDocumentObject` y `TaxIntegrationLineObject`.</span><span class="sxs-lookup"><span data-stu-id="ecb55-145">In these **Data Retrieval** activities, data is copied from the database to `TaxIntegrationDocumentObject` and `TaxIntegrationLineObject`.</span></span> <span data-ttu-id="ecb55-146">Debido a que todas estas actividades extienden la misma clase de plantilla abstracta, tienen métodos comunes.</span><span class="sxs-lookup"><span data-stu-id="ecb55-146">Because all these activities extend the same abstract template class, they have common methods.</span></span>

#### <a name="calculation-service-activities"></a><span data-ttu-id="ecb55-147">Cálculo de actividades de servicio</span><span class="sxs-lookup"><span data-stu-id="ecb55-147">Calculation Service activities</span></span>

<span data-ttu-id="ecb55-148">La actividad **Servicio de cálculo** es el vínculo entre el servicio fiscal y la integración fiscal.</span><span class="sxs-lookup"><span data-stu-id="ecb55-148">The **Calculation Service** activity is the link between the tax service and the tax integration.</span></span> <span data-ttu-id="ecb55-149">Esta actividad se encarga de las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="ecb55-149">This activity is responsible for the following functions:</span></span>

1. <span data-ttu-id="ecb55-150">Construir la solicitud.</span><span class="sxs-lookup"><span data-stu-id="ecb55-150">Construct the request.</span></span>
2. <span data-ttu-id="ecb55-151">Contabilizar la solicitud en el servicio de impuestos.</span><span class="sxs-lookup"><span data-stu-id="ecb55-151">Post the request to the tax service.</span></span>
3. <span data-ttu-id="ecb55-152">Obtener la respuesta del servicio de impuestos.</span><span class="sxs-lookup"><span data-stu-id="ecb55-152">Get the response from the tax service.</span></span>
4. <span data-ttu-id="ecb55-153">Analizar la respuesta.</span><span class="sxs-lookup"><span data-stu-id="ecb55-153">Parse the response.</span></span>

<span data-ttu-id="ecb55-154">Un campo de datos que agregue a la solicitud se publicará junto con otros metadatos.</span><span class="sxs-lookup"><span data-stu-id="ecb55-154">A data field that you add to the request will be posted together with other metadata.</span></span> 

## <a name="extension-implementation"></a><span data-ttu-id="ecb55-155">Implementación de extensión</span><span class="sxs-lookup"><span data-stu-id="ecb55-155">Extension implementation</span></span>

<span data-ttu-id="ecb55-156">Esta sección proporciona pasos detallados que explican cómo implementar la extensión.</span><span class="sxs-lookup"><span data-stu-id="ecb55-156">This section provides detailed steps that explain how to implement the extension.</span></span> <span data-ttu-id="ecb55-157">Utiliza las dimensiones financieras **Centro de coste** y **Proyecto** como ejemplos.</span><span class="sxs-lookup"><span data-stu-id="ecb55-157">It uses the **Cost center** and **Project** financial dimensions as examples.</span></span>

### <a name="step-1-add-the-data-variable-in-the-object-class"></a><span data-ttu-id="ecb55-158">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="ecb55-158">Step 1.</span></span> <span data-ttu-id="ecb55-159">Agregue la variable de datos en la clase de objeto</span><span class="sxs-lookup"><span data-stu-id="ecb55-159">Add the data variable in the object class</span></span>

<span data-ttu-id="ecb55-160">La clase de objeto contiene la variable de datos y los métodos de acceder y fijar valores para los datos.</span><span class="sxs-lookup"><span data-stu-id="ecb55-160">The object class contains the data variable and getter/setter methods for the data.</span></span> <span data-ttu-id="ecb55-161">Agregue el campo de datos a `TaxIntegrationDocumentObject` o `TaxIntegrationLineObject`, dependiendo del nivel del campo.</span><span class="sxs-lookup"><span data-stu-id="ecb55-161">Add the data field to either `TaxIntegrationDocumentObject` or `TaxIntegrationLineObject`, depending on the level of the field.</span></span> <span data-ttu-id="ecb55-162">El siguiente ejemplo usa el nivel de línea y el nombre del archivo es `TaxIntegrationLineObject_Extension.xpp`.</span><span class="sxs-lookup"><span data-stu-id="ecb55-162">The following example uses the line level, and the file name is `TaxIntegrationLineObject_Extension.xpp`.</span></span>

> [!NOTE]
> <span data-ttu-id="ecb55-163">Si el campo de datos que está agregando está en el nivel del documento, cambie el nombre del archivo a `TaxIntegrationDocumentObject_Extension.xpp`.</span><span class="sxs-lookup"><span data-stu-id="ecb55-163">If the data field that you're adding is at the document level, change the file name to `TaxIntegrationDocumentObject_Extension.xpp`.</span></span>

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

<span data-ttu-id="ecb55-164">**Centro de coste** y **Proyecto** se agregan como variables privadas.</span><span class="sxs-lookup"><span data-stu-id="ecb55-164">**Cost center** and **Project** are added as private variables.</span></span> <span data-ttu-id="ecb55-165">Cree métodos de acceso y fijación para que estos campos de datos manipulen los datos.</span><span class="sxs-lookup"><span data-stu-id="ecb55-165">Create getter and setter methods for these data fields to manipulate the data.</span></span>

### <a name="step-2-retrieve-data-from-the-database"></a><span data-ttu-id="ecb55-166">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="ecb55-166">Step 2.</span></span> <span data-ttu-id="ecb55-167">Recuperar datos de la base de datos</span><span class="sxs-lookup"><span data-stu-id="ecb55-167">Retrieve data from the database</span></span>

<span data-ttu-id="ecb55-168">Especifique la transacción y amplíe las clases de adaptador adecuadas para recuperar los datos.</span><span class="sxs-lookup"><span data-stu-id="ecb55-168">Specify the transaction, and extend the appropriate adapter classes to retrieve the data.</span></span> <span data-ttu-id="ecb55-169">Por ejemplo, si usa una transacción **Pedido de compra**, debe extender `TaxIntegrationPurchTableDataRetrieval` y `TaxIntegrationVendInvoiceInfoTableDataRetrieval`.</span><span class="sxs-lookup"><span data-stu-id="ecb55-169">For example, if you use a **Purchase order** transaction, you must extend `TaxIntegrationPurchTableDataRetrieval` and `TaxIntegrationVendInvoiceInfoTableDataRetrieval`.</span></span> 

> [!NOTE]
> <span data-ttu-id="ecb55-170">`TaxIntegrationPurchParmTableDataRetrieval` se hereda de `TaxIntegrationPurchTableDataRetrieval`.</span><span class="sxs-lookup"><span data-stu-id="ecb55-170">`TaxIntegrationPurchParmTableDataRetrieval` is inherited from `TaxIntegrationPurchTableDataRetrieval`.</span></span> <span data-ttu-id="ecb55-171">No debe cambiarse a menos que la lógica de las tablas `purchTable` y `purchParmTable` difiera.</span><span class="sxs-lookup"><span data-stu-id="ecb55-171">It should not be changed unless the logic of the `purchTable` and `purchParmTable` tables differs.</span></span>

<span data-ttu-id="ecb55-172">Si el campo de datos debe agregarse para todas las transacciones, extienda todas las clases `DataRetrieval`.</span><span class="sxs-lookup"><span data-stu-id="ecb55-172">If the data field should be added for all transactions, extend all `DataRetrieval` classes.</span></span>

<span data-ttu-id="ecb55-173">Dado que todas las actividades de **Recuperación de datos** extienden la misma clase de plantilla, las estructuras de clase, las variables y los métodos son similares.</span><span class="sxs-lookup"><span data-stu-id="ecb55-173">Because all **Data Retrieval** activities extend the same template class, the class structures, variables, and methods are similar.</span></span>

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

<span data-ttu-id="ecb55-174">El siguiente ejemplo muestra la estructura básica cuando se utiliza la tabla `PurchTable`.</span><span class="sxs-lookup"><span data-stu-id="ecb55-174">The following example shows the basic structure when the `PurchTable` table is used.</span></span>

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

<span data-ttu-id="ecb55-175">Cuando se llama al método `CopyToDocument` el búfer `this.purchTable` ya existe.</span><span class="sxs-lookup"><span data-stu-id="ecb55-175">When the `CopyToDocument` method is called, the `this.purchTable` buffer already exists.</span></span> <span data-ttu-id="ecb55-176">El propósito de este método es copiar todos los datos requeridos desde `this.purchTable` hasta el objeto `document`, mediante el método de fijación que se creó en la clase `DocumentObject`.</span><span class="sxs-lookup"><span data-stu-id="ecb55-176">The purpose of this method is to copy all the required data from `this.purchTable` to the `document` object by using the setter method that was created in the `DocumentObject` class.</span></span>

<span data-ttu-id="ecb55-177">Asimismo, ya existe un búfer `this.purchLine` en el método `CopyToLine`.</span><span class="sxs-lookup"><span data-stu-id="ecb55-177">Likewise, a `this.purchLine` buffer already exists in the `CopyToLine` method.</span></span> <span data-ttu-id="ecb55-178">El propósito de este método es copiar todos los datos requeridos desde `this.purchLine` hasta el objeto `_line`, mediante el método de fijación que se creó en la clase `LineObject`.</span><span class="sxs-lookup"><span data-stu-id="ecb55-178">The purpose of this method is to copy all the required data from `this.purchLine` to the `_line` object by using the setter method that was created in the `LineObject` class.</span></span>

<span data-ttu-id="ecb55-179">El enfoque más sencillo es ampliar los métodos `CopyToDocument` y `CopyToLine`.</span><span class="sxs-lookup"><span data-stu-id="ecb55-179">The most straightforward approach is to extend the `CopyToDocument` and `CopyToLine` methods.</span></span> <span data-ttu-id="ecb55-180">Sin embargo, se recomienda probar primero los métodos `copyToDocumentFromHeaderTable` y `copyToLineFromLineTable`.</span><span class="sxs-lookup"><span data-stu-id="ecb55-180">However, we recommend that you try the `copyToDocumentFromHeaderTable` and `copyToLineFromLineTable` methods first.</span></span> <span data-ttu-id="ecb55-181">Si no funcionan como necesita, implemente su propio método y llámelo en `CopyToDocument` y `CopyToLine`.</span><span class="sxs-lookup"><span data-stu-id="ecb55-181">If they don't work as you require, implement your own method, and call it in `CopyToDocument` and `CopyToLine`.</span></span> <span data-ttu-id="ecb55-182">Hay tres situaciones comunes en las que puede utilizar este enfoque:</span><span class="sxs-lookup"><span data-stu-id="ecb55-182">There are three common situations where you might use this approach:</span></span>

- <span data-ttu-id="ecb55-183">El campo requerido está en `PurchTable` o `PurchLine`.</span><span class="sxs-lookup"><span data-stu-id="ecb55-183">The required field is in `PurchTable` or `PurchLine`.</span></span> <span data-ttu-id="ecb55-184">En esta situación, puede extender `copyToDocumentFromHeaderTable` y `copyToLineFromLineTable`.</span><span class="sxs-lookup"><span data-stu-id="ecb55-184">In this situation, you can extend `copyToDocumentFromHeaderTable` and `copyToLineFromLineTable`.</span></span> <span data-ttu-id="ecb55-185">Aquí está el código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ecb55-185">Here is the sample code.</span></span>

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

- <span data-ttu-id="ecb55-186">Los datos requeridos no están en la tabla predeterminada de la transacción.</span><span class="sxs-lookup"><span data-stu-id="ecb55-186">The required data isn't in the default table of the transaction.</span></span> <span data-ttu-id="ecb55-187">Sin embargo, existen algunas relaciones de unión con la tabla predeterminada y el campo es obligatorio en la mayoría de las líneas.</span><span class="sxs-lookup"><span data-stu-id="ecb55-187">However, there are some join relationships with the default table, and the field is required on most lines.</span></span> <span data-ttu-id="ecb55-188">En esta situación, reemplace `getDocumentQueryObject` o `getLineObject` para consultar la tabla por relación de unión.</span><span class="sxs-lookup"><span data-stu-id="ecb55-188">In this situation, replace `getDocumentQueryObject` or `getLineObject` to query the table by join relationship.</span></span> <span data-ttu-id="ecb55-189">En el siguiente ejemplo, el campo **Entregar ahora** está integrado con el pedido de ventas a nivel de línea.</span><span class="sxs-lookup"><span data-stu-id="ecb55-189">In the following example, the **Deliver Now** field is integrated with the sales order at the line level.</span></span>

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

    <span data-ttu-id="ecb55-190">En este ejemplo, se declara un búfer `mcrSalesLineDropShipment` y la consulta se define en `getLineQueryObject`.</span><span class="sxs-lookup"><span data-stu-id="ecb55-190">In this example, a `mcrSalesLineDropShipment` buffer is declared, and the query is defined in `getLineQueryObject`.</span></span> <span data-ttu-id="ecb55-191">La consulta usa la relación `MCRSalesLineDropShipment.SalesLine == SalesLine.RecId`.</span><span class="sxs-lookup"><span data-stu-id="ecb55-191">The query uses the relationship `MCRSalesLineDropShipment.SalesLine == SalesLine.RecId`.</span></span> <span data-ttu-id="ecb55-192">Mientras se extiende en esta situación, puede reemplazar `getLineQueryObject` con su propio objeto de consulta construido.</span><span class="sxs-lookup"><span data-stu-id="ecb55-192">While you're extending in this situation, you can replace `getLineQueryObject` with your own constructed query object.</span></span> <span data-ttu-id="ecb55-193">No obstante, tenga en cuenta los puntos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ecb55-193">However, note the following points:</span></span>

    * <span data-ttu-id="ecb55-194">Como el valor de retorno del método `getLineQueryObject` es `SysDaQueryObject`, debe construir este objeto utilizando el enfoque SysDa.</span><span class="sxs-lookup"><span data-stu-id="ecb55-194">Because the return value of the `getLineQueryObject` method is `SysDaQueryObject`, you must construct this object by using the SysDa approach.</span></span>
    * <span data-ttu-id="ecb55-195">No se puede eliminar la tabla existente.</span><span class="sxs-lookup"><span data-stu-id="ecb55-195">Can't remove existed table.</span></span>

- <span data-ttu-id="ecb55-196">Los datos requeridos están relacionados con la tabla de transacciones por una relación de unión complicada, o la relación no es uno a uno (1:1) sino uno a muchos (1:N).</span><span class="sxs-lookup"><span data-stu-id="ecb55-196">The required data is related to the transaction table by a complicated join relationship, or the relation isn't one to one (1:1) but one to many (1:N).</span></span> <span data-ttu-id="ecb55-197">En esta situación, las cosas se complican un poco.</span><span class="sxs-lookup"><span data-stu-id="ecb55-197">In this situation, things become a little complicated.</span></span> <span data-ttu-id="ecb55-198">Esta situación se aplica al ejemplo de las dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="ecb55-198">This situation applies to the example of financial dimensions.</span></span> 

    <span data-ttu-id="ecb55-199">En esta situación, puede implementar su propio método para recuperar los datos.</span><span class="sxs-lookup"><span data-stu-id="ecb55-199">In this situation, you can implement your own method to retrieve the data.</span></span> <span data-ttu-id="ecb55-200">Aquí está el código de muestra, en el archivo `TaxIntegrationPurchTableDataRetrieval_Extension.xpp`.</span><span class="sxs-lookup"><span data-stu-id="ecb55-200">Here is the sample code in the `TaxIntegrationPurchTableDataRetrieval_Extension.xpp` file.</span></span>

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

### <a name="step-3-add-data-to-the-request"></a><span data-ttu-id="ecb55-201">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="ecb55-201">Step 3.</span></span> <span data-ttu-id="ecb55-202">Agregar datos a la solicitud</span><span class="sxs-lookup"><span data-stu-id="ecb55-202">Add data to the request</span></span>

<span data-ttu-id="ecb55-203">Extienda el método `copyToTaxableDocumentHeaderWrapperFromTaxIntegrationDocumentObject` o `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` para agregar datos a la solicitud.</span><span class="sxs-lookup"><span data-stu-id="ecb55-203">Extend the `copyToTaxableDocumentHeaderWrapperFromTaxIntegrationDocumentObject` or `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` method to add data to the request.</span></span> <span data-ttu-id="ecb55-204">Aquí está el código de muestra, en el archivo `TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp`.</span><span class="sxs-lookup"><span data-stu-id="ecb55-204">Here is the sample code in the `TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp` file.</span></span>

```X++
[ExtensionOf(classStr(TaxIntegrationCalculationActivityOnDocument_CalculationService))]
final static class TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension
{
    // Define key for the form in post request
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

<span data-ttu-id="ecb55-205">En este código, `_destination` es el objeto contenedor que se utiliza para generar la solicitud de registro, y `_source` es el objeto `TaxIntegrationLineObject`.</span><span class="sxs-lookup"><span data-stu-id="ecb55-205">In this code, `_destination` is the wrapper object that is used to generate the post request, and `_source` is the `TaxIntegrationLineObject` object.</span></span> 

> [!NOTE]
> * <span data-ttu-id="ecb55-206">Defina la clave que se utiliza en el formulario de solicitud como `private const str`.</span><span class="sxs-lookup"><span data-stu-id="ecb55-206">Define the key that is used in the request form as `private const str`.</span></span>
> * <span data-ttu-id="ecb55-207">Establezca el campo en el método `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` usando el método `SetField`.</span><span class="sxs-lookup"><span data-stu-id="ecb55-207">Set the field in the `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` method by using the `SetField` method.</span></span> <span data-ttu-id="ecb55-208">El tipo de datos del segundo parámetro debe ser `string`.</span><span class="sxs-lookup"><span data-stu-id="ecb55-208">The data type of the second parameter should be `string`.</span></span> <span data-ttu-id="ecb55-209">Si el tipo de datos no es `string`, conviértalo a `string`.</span><span class="sxs-lookup"><span data-stu-id="ecb55-209">If the data type isn't `string`, convert it to `string`.</span></span>

## <a name="appendix"></a><span data-ttu-id="ecb55-210">Apéndice</span><span class="sxs-lookup"><span data-stu-id="ecb55-210">Appendix</span></span>

<span data-ttu-id="ecb55-211">Este apéndice muestra el código de muestra completo para la integración de dimensiones financieras (**Centro de cose** y **Proyecto**) a nivel de línea.</span><span class="sxs-lookup"><span data-stu-id="ecb55-211">This appendix shows the complete sample code for the integration of financial dimensions (**Cost center** and **Project**) at the line level.</span></span>

### <a name="taxintegrationlineobject_extensionxpp"></a><span data-ttu-id="ecb55-212">TaxIntegrationLineObject_Extension.xpp</span><span class="sxs-lookup"><span data-stu-id="ecb55-212">TaxIntegrationLineObject_Extension.xpp</span></span>

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

### <a name="taxintegrationpurchtabledataretrieval_extensionxpp"></a><span data-ttu-id="ecb55-213">TaxIntegrationPurchTableDataRetrieval_Extension.xpp</span><span class="sxs-lookup"><span data-stu-id="ecb55-213">TaxIntegrationPurchTableDataRetrieval_Extension.xpp</span></span>

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

### <a name="taxintegrationcalculationactivityondocument_calculationservice_extensionxpp"></a><span data-ttu-id="ecb55-214">TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp</span><span class="sxs-lookup"><span data-stu-id="ecb55-214">TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp</span></span>

```X++
[ExtensionOf(classStr(TaxIntegrationCalculationActivityOnDocument_CalculationService))]
final static class TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension
{
    // Define key for the form in post request
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
