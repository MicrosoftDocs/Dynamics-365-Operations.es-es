---
title: Importar ASN entrantes a través de la entidad de datos V2
description: Este tema explica cómo administrar la importación de avisos de envío avanzados entrantes (ASN) a través de la entidad de datos Inbound ASN V2.
author: GalynaFedorova
ms.date: 05/31/2021
ms.topic: article
ms.search.form: WHSInboundASNV2Entity, WHSInboundASNEntity
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-04
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 470cc0c39f211a5d0f106c4c6e193867388e2b53
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249165"
---
# <a name="import-inbound-asns-through-the-v2-data-entity"></a><span data-ttu-id="e912d-103">Importar ASN entrantes a través de la entidad de datos V2</span><span class="sxs-lookup"><span data-stu-id="e912d-103">Import inbound ASNs through the V2 data entity</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e912d-104">Los avisos de envío avanzados (ASN) le notifican sobre las entregas de proveedores.</span><span class="sxs-lookup"><span data-stu-id="e912d-104">Advanced shipping notices (ASNs) notify you about vendor deliveries.</span></span> <span data-ttu-id="e912d-105">Ayudan al remitente a describir el contenido de un envío e información adicional sobre él, como los artículos y el embalaje.</span><span class="sxs-lookup"><span data-stu-id="e912d-105">They help the sender describe the contents of a shipment and additional information about it, such as the items and packaging.</span></span>

<span data-ttu-id="e912d-106">Los ASN pueden ayudar a los trabajadores del almacén a saber qué llega y cuándo.</span><span class="sxs-lookup"><span data-stu-id="e912d-106">ASNs can help warehouse workers learn what is arriving when.</span></span> <span data-ttu-id="e912d-107">Por lo tanto, pueden prepararse.</span><span class="sxs-lookup"><span data-stu-id="e912d-107">Therefore, they can prepare.</span></span> <span data-ttu-id="e912d-108">Además, los trabajadores del almacén pueden usar ASN para hacer coincidir los detalles de un envío con la orden de compra relacionada que se creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e912d-108">In addition, warehouse workers can use ASNs to match the details of a shipment to the related purchase order that was previously created.</span></span>

<span data-ttu-id="e912d-109">En este tema se presenta una colección de escenarios que muestran, a través de ejemplos, cómo trabajar con asrchivos ASN.</span><span class="sxs-lookup"><span data-stu-id="e912d-109">This topic presents a collection of scenarios that show, through examples, how to work with ASN files.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e912d-110">La importación *ASN entrante* se aplica solo a los artículos que están habilitados para la gestión avanzada de almacenes (WMS).</span><span class="sxs-lookup"><span data-stu-id="e912d-110">*Inbound ASN* import applies only to items that are enabled for advanced warehouse management (WMS).</span></span> <span data-ttu-id="e912d-111">Antes de recibir un ASN, se debe registrar una orden de compra en el sistema contra el proveedor que envía ese ASN.</span><span class="sxs-lookup"><span data-stu-id="e912d-111">Before you receive an ASN, a purchase order must be registered in the system against the vendor who is sending that ASN.</span></span>

## <a name="inbound-asn-v2-entity"></a><span data-ttu-id="e912d-112">Entidad entrante ASN V2</span><span class="sxs-lookup"><span data-stu-id="e912d-112">Inbound ASN V2 entity</span></span>

<span data-ttu-id="e912d-113">Importa los ASN entrantes mediante la entidad *ASN entrante V2* de datos compuestos.</span><span class="sxs-lookup"><span data-stu-id="e912d-113">You import inbound ASNs by using the *Inbound ASN V2* composite data entity.</span></span> <span data-ttu-id="e912d-114">*ASN entrante V2* aprovecha las siguientes entidades:</span><span class="sxs-lookup"><span data-stu-id="e912d-114">*Inbound ASN V2* takes advantage of the following entities:</span></span>

- <span data-ttu-id="e912d-115">Encabezado de carga entrante</span><span class="sxs-lookup"><span data-stu-id="e912d-115">Inbound load header</span></span>
- <span data-ttu-id="e912d-116">Encabezado de envío entrante</span><span class="sxs-lookup"><span data-stu-id="e912d-116">Inbound shipment header</span></span>
- <span data-ttu-id="e912d-117">Estructuras de empaquetado de carga entrante</span><span class="sxs-lookup"><span data-stu-id="e912d-117">Inbound load packing structures</span></span>
- <span data-ttu-id="e912d-118">Cajas de estructura de empaquetado de carga entrante</span><span class="sxs-lookup"><span data-stu-id="e912d-118">Inbound load packing structure cases</span></span>
- <span data-ttu-id="e912d-119">Líneas de caja de estructura de empaquetado de carga entrante</span><span class="sxs-lookup"><span data-stu-id="e912d-119">Inbound load packing structure case lines</span></span>
- <span data-ttu-id="e912d-120">Líneas de estructura de empaquetado de carga entrante</span><span class="sxs-lookup"><span data-stu-id="e912d-120">Inbound load packing structure lines</span></span>

<span data-ttu-id="e912d-121">La entidad *ASN entrante V2* de datos compuestos está pensada para escenarios de integración asincrónica donde se utilizan importaciones basadas en archivos XML.</span><span class="sxs-lookup"><span data-stu-id="e912d-121">The *Inbound ASN V2* composite data entity is intended for asynchronous integration scenarios where XML file–based imports are used.</span></span>

## <a name="xml-format-for-importing-asns"></a><span data-ttu-id="e912d-122">Formato XML para importar ASN</span><span class="sxs-lookup"><span data-stu-id="e912d-122">XML format for importing ASNs</span></span>

<span data-ttu-id="e912d-123">Microsoft Dynamics 365 Supply Chain Management admite el siguiente formato XML para importar ASN.</span><span class="sxs-lookup"><span data-stu-id="e912d-123">Microsoft Dynamics 365 Supply Chain Management supports the following XML format for importing ASNs.</span></span> <span data-ttu-id="e912d-124">Cada nodo del archivo XML representa un atributo de una entidad individual.</span><span class="sxs-lookup"><span data-stu-id="e912d-124">Each node in the XML file represents an attribute from an individual entity.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity>
        <WHSInboundShipmentHeaderEntity>
            <WHSInboundLoadPackingStructureEntity>
                <WHSInboundLoadPackingStructureCaseEntity>
                    <WHSInboundPackingStructureCaseLineV2Entity>
                    </WHSInboundPackingStructureCaseLineV2Entity>
                </WHSInboundLoadPackingStructureCaseEntity>
                <WHSInboundLoadPackingStructureLineV2Entity>
                </WHSInboundLoadPackingStructureLineV2Entity>
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

## <a name="examples"></a><span data-ttu-id="e912d-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e912d-125">Examples</span></span>

<span data-ttu-id="e912d-126">Las siguientes subsecciones proporcionan ejemplos de archivos de importación XML ASN para envíos de proveedores.</span><span class="sxs-lookup"><span data-stu-id="e912d-126">The following subsections provide examples of ASN XML import files for vendor shipments.</span></span>

### <a name="example-1"></a><span data-ttu-id="e912d-127">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="e912d-127">Example 1</span></span>

<span data-ttu-id="e912d-128">El siguiente ejemplo muestra un archivo XML para importar envíos de proveedores para una orden de compra cuando no se incluyen detalles del caso.</span><span class="sxs-lookup"><span data-stu-id="e912d-128">The following example shows an XML file for importing vendor shipments for one purchase order when no case details are included.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity TRACTORNUMBER="0000101">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_01" VENDORADDRESSCOUNTRYREGIONID = "USA" VENDORADDRESSSTREET = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000176" ITEMNUMBER="A0001" QUANTITY="1" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

### <a name="example-2"></a><span data-ttu-id="e912d-129">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="e912d-129">Example 2</span></span>

<span data-ttu-id="e912d-130">El siguiente ejemplo muestra un archivo XML para importar envíos de proveedores para una orden de compra cuando se incluyen detalles del caso.</span><span class="sxs-lookup"><span data-stu-id="e912d-130">The following example shows an XML file for importing vendor shipments for one purchase order when case details are included.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity ESTIMATEDARRIVALDATETIME="2021-04-25T11:00:00+00:00">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="MVR_SNN_0004">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="MVR_SNN_0004" PACKEDTOTALQUANTITY="2.00">
                <WHSInboundLoadPackingStructureCaseEntity PARENTPACKINGSTRUCTURELICENSEPLATENUMBER="MVR_SNN_0004" LICENSEPLATENUMBER="MVR_SNN_0004A" PACKEDTOTALQUANTITY="2.00" />
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000175" ITEMNUMBER="A0001" PURCHASEORDERLINENUMBER="1" QUANTITY="2.00" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

### <a name="example-3"></a><span data-ttu-id="e912d-131">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="e912d-131">Example 3</span></span>

<span data-ttu-id="e912d-132">El siguiente ejemplo muestra un archivo XML para importar envíos de proveedores para varios pedidos de compra cuando se incluyen detalles del caso.</span><span class="sxs-lookup"><span data-stu-id="e912d-132">The following example shows an XML file for importing vendor shipments for multiple purchase orders when case details are included.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity TRACTORNUMBER="0000101">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_01" VENDORADDRESSCOUNTRYREGIONID = "USA" VendorAddressStreet = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000176" ITEMNUMBER="A0001" QUANTITY="100" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_02" VENDORADDRESSCOUNTRYREGIONID = "USA" VendorAddressStreet = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="A0001" QUANTITY="200" UNITSYMBOL="ea" />
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="P0004" QUANTITY="300" UNITSYMBOL="ea" ITEMBATCHNUMBER="BN0001" />
            </WHSInboundLoadPackingStructureEntity>
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_002">
                <WHSInboundLoadPackingStructureCaseEntity LICENSEPLATENUMBER="LP_ASN_002_C01">
                    <WHSInboundLoadPackingStructureCaseLineV2Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="A0001" QUANTITY="400" UNITSYMBOL="ea" />
                </WHSInboundLoadPackingStructureCaseEntity>
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

## <a name="inspect-the-results-of-importing-an-asn-file"></a><span data-ttu-id="e912d-133">Inspeccionar los resultados de la importación de un archivo ASN</span><span class="sxs-lookup"><span data-stu-id="e912d-133">Inspect the results of importing an ASN file</span></span>

<span data-ttu-id="e912d-134">Siga estos pasos para inspeccionar los resultados de la importación de un archivo ASN.</span><span class="sxs-lookup"><span data-stu-id="e912d-134">Follow these steps to inspect the results of importing an ASN file.</span></span>

1. <span data-ttu-id="e912d-135">Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.</span><span class="sxs-lookup"><span data-stu-id="e912d-135">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="e912d-136">Busque y abra una carga que se creó como parte de una importación de ASN.</span><span class="sxs-lookup"><span data-stu-id="e912d-136">Find and open a load that was created as part of an ASN import.</span></span>
1. <span data-ttu-id="e912d-137">En la ficha desplegable **Carga**, debería ver los valores que se basan en el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="e912d-137">On the **Load** FastTab, you should see values that are based on the XML file.</span></span>
1. <span data-ttu-id="e912d-138">En la ficha desplegable **Líneas de carga**, debería ver los números de orden de compra y los detalles del artículo que se basan en el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="e912d-138">On the **Load lines** FastTab, you should see purchase order numbers and item details that are based on the XML file.</span></span>
1. <span data-ttu-id="e912d-139">En el panel de acciones, en la pestaña **Enviar y recibir**, en el grupo **Recibir**, seleccione **Estructura de embalaje** para revisar la estructura de empaque de la carga.</span><span class="sxs-lookup"><span data-stu-id="e912d-139">On the Action Pane, on the **Ship and receive** tab, in the **Receive** group, select **Packing structure** to review the packing structure of the load.</span></span>
1. <span data-ttu-id="e912d-140">En la ficha desplegable **Palés**, debería ver las placas de matrícula que se basan en el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="e912d-140">On the **Pallets** FastTab, you should see license plates that are based on the XML file.</span></span>
1. <span data-ttu-id="e912d-141">En la ficha desplegable **Casos**, debería ver los casos que se basan en el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="e912d-141">On the **Cases** FastTab, you should see cases that are based on the XML file.</span></span>
1. <span data-ttu-id="e912d-142">En la ficha desplegable **Artículos**, debería ver los artículos y las cantidades que se basan en el archivo XML.</span><span class="sxs-lookup"><span data-stu-id="e912d-142">On the **Items** FastTab, you should see items and quantities that are based on the XML file.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
