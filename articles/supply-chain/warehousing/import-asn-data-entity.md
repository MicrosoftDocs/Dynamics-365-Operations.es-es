---
title: Importar ASN entrantes a través de la entidad de datos V3
description: Este artículo explica cómo administrar la importación de avisos de envío avanzados entrantes (ASN) a través de la entidad de datos Inbound ASN.
author: GalynaFedorova
ms.date: 05/11/2022
ms.topic: article
ms.search.form: WHSInboundASNV3Entity, WHSInboundASNEntity, DMFEntity
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2021-06-04
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 66ed258ebddaadb5a306f41dea3e439e9b5a7be3
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9065880"
---
# <a name="import-inbound-asns-through-the-v3-data-entity"></a>Importar ASN entrantes a través de la entidad de datos V3

[!include [banner](../../includes/banner.md)]

Los avisos de envío avanzados (ASN) le notifican sobre las entregas de proveedores. Ayudan al remitente a describir el contenido de un envío e información adicional sobre él, como los artículos y el embalaje.

Los ASN pueden ayudar a los trabajadores del almacén a saber qué llega y cuándo. Por lo tanto, pueden prepararse. Además, los trabajadores del almacén pueden usar ASN para hacer coincidir los detalles de un envío con la orden de compra relacionada que se creó anteriormente.

En este artículo se presenta una colección de escenarios que muestran, a través de ejemplos, cómo trabajar con asrchivos ASN.

> [!IMPORTANT]
> La importación *ASN entrante* se aplica solo a los artículos que están habilitados para procesos de gestión de almacenes (WMS). Antes de recibir un ASN, se debe registrar una orden de compra en el sistema contra el proveedor que envía ese ASN.

## <a name="inbound-asn-v3-entity"></a>Entidad entrante ASN V3

Importa los ASN entrantes mediante la entidad *ASN entrante V3* de datos compuestos. *ASN entrante V3* aprovecha las siguientes entidades:

- Encabezado de carga entrante
- Encabezado de envío entrante
- Estructuras de empaquetado de carga entrante
- Cajas de estructura de empaquetado de carga entrante
- Líneas de caja de estructura de empaquetado de carga entrante
- Líneas de estructura de empaquetado de carga entrante

La entidad *ASN entrante V3* de datos compuestos está pensada para escenarios de integración asincrónica donde se utilizan importaciones basadas en archivos XML.

## <a name="xml-format-for-importing-asns"></a>Formato XML para importar ASN

Microsoft Dynamics 365 Supply Chain Management admite el siguiente formato XML para importar ASN. Cada nodo del archivo XML representa un atributo de una entidad individual.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity>
        <WHSInboundShipmentHeaderEntity>
            <WHSInboundLoadPackingStructureEntity>
                <WHSInboundLoadPackingStructureCaseEntity>
                    <WHSInboundPackingStructureCaseLineV3Entity>
                    </WHSInboundPackingStructureCaseLineV3Entity>
                </WHSInboundLoadPackingStructureCaseEntity>
                <WHSInboundLoadPackingStructureLineV3Entity>
                </WHSInboundLoadPackingStructureLineV3Entity>
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

## <a name="examples"></a>Ejemplo

Las siguientes subsecciones proporcionan ejemplos de archivos de importación XML ASN para envíos de proveedores.

### <a name="example-1"></a>Ejemplo 1

El siguiente ejemplo muestra un archivo XML para importar envíos de proveedores para una orden de compra cuando no se incluyen detalles del caso.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity TRACTORNUMBER="0000101">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_01" VENDORADDRESSCOUNTRYREGIONID = "USA" VENDORADDRESSSTREET = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV3Entity PURCHASEORDERNUMBER="00000176" ITEMNUMBER="A0001" QUANTITY="1" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

### <a name="example-2"></a>Ejemplo 2

El siguiente ejemplo muestra un archivo XML para importar envíos de proveedores para una orden de compra cuando se incluyen detalles del caso.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity ESTIMATEDARRIVALDATETIME="2021-04-25T11:00:00+00:00">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="MVR_SNN_0004">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="MVR_SNN_0004" PACKEDTOTALQUANTITY="2.00">
                <WHSInboundLoadPackingStructureCaseEntity PARENTPACKINGSTRUCTURELICENSEPLATENUMBER="MVR_SNN_0004" LICENSEPLATENUMBER="MVR_SNN_0004A" PACKEDTOTALQUANTITY="2.00" />
                <WHSInboundLoadPackingStructureLine3Entity PURCHASEORDERNUMBER="00000175" ITEMNUMBER="A0001" PURCHASEORDERLINENUMBER="1" QUANTITY="2.00" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

### <a name="example-3"></a>Ejemplo 3

El siguiente ejemplo muestra un archivo XML para importar envíos de proveedores para varios pedidos de compra cuando se incluyen detalles del caso.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity TRACTORNUMBER="0000101">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_01" VENDORADDRESSCOUNTRYREGIONID = "USA" VendorAddressStreet = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV3Entity PURCHASEORDERNUMBER="00000176" ITEMNUMBER="A0001" QUANTITY="100" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_02" VENDORADDRESSCOUNTRYREGIONID = "USA" VendorAddressStreet = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV3Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="A0001" QUANTITY="200" UNITSYMBOL="ea" />
                <WHSInboundLoadPackingStructureLineV3Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="P0004" QUANTITY="300" UNITSYMBOL="ea" ITEMBATCHNUMBER="BN0001" />
            </WHSInboundLoadPackingStructureEntity>
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_002">
                <WHSInboundLoadPackingStructureCaseEntity LICENSEPLATENUMBER="LP_ASN_002_C01">
                    <WHSInboundLoadPackingStructureCaseLineV3Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="A0001" QUANTITY="400" UNITSYMBOL="ea" />
                </WHSInboundLoadPackingStructureCaseEntity>
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

## <a name="inspect-the-results-of-importing-an-asn-file"></a>Inspeccionar los resultados de la importación de un archivo ASN

Siga estos pasos para inspeccionar los resultados de la importación de un archivo ASN.

1. Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.
1. Busque y abra una carga que se creó como parte de una importación de ASN.
1. En la ficha desplegable **Carga**, debería ver los valores que se basan en el archivo XML.
1. En la ficha desplegable **Líneas de carga**, debería ver los números de orden de compra y los detalles del artículo que se basan en el archivo XML.
1. En el panel de acciones, en la pestaña **Enviar y recibir**, en el grupo **Recibir**, seleccione **Estructura de embalaje** para revisar la estructura de empaque de la carga.
1. En la ficha desplegable **Palés**, debería ver las placas de matrícula que se basan en el archivo XML.
1. En la ficha desplegable **Casos**, debería ver los casos que se basan en el archivo XML.
1. En la ficha desplegable **Artículos**, debería ver los artículos y las cantidades que se basan en el archivo XML.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
