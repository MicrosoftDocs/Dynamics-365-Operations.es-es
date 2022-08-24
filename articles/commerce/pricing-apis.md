---
title: API de precios comerciales
description: Este artículo describe las distintas API de precios que proporciona el motor de precios de Microsoft Dynamics 365 Commerce.
author: boycez
ms.date: 08/10/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: boycez
ms.search.validFrom: 2022-07-15
ms.openlocfilehash: d694c44f6987fbf2a360869d2fb2a2fbaf0d2e4d
ms.sourcegitcommit: 924dbcdc6b03f6a7ae3a07378ec405fd15c7e359
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2022
ms.locfileid: "9294132"
---
# <a name="commerce-pricing-apis"></a>API de precios comerciales

[!include [banner](../includes/banner.md)]

Este artículo describe las distintas API de precios que proporciona el motor de precios de Microsoft Dynamics 365 Commerce.

El motor de precios de Dynamics 365 Commerce proporciona las siguientes API de servidores minoristas que pueden ser consumidas por aplicaciones externas para admitir varios escenarios de precios:

- **GetActivePrices** – Esta API obtiene el precio calculado de un producto, incluidos los descuentos simples.
- **CalculateSalesDocument** – Esta API calcula precios y descuentos para productos en cantidades determinadas si se compran juntos.
- **GetAvailablePromotions** – Esta API obtiene descuentos aplicables para productos en el carrito. 
- **AddCoupons** – Esta API agrega cupones a un carrito.
- **RemoveCoupons** – Esta API elimina cupones de un carrito.

Para obtener más información sobre cómo consumir las API de Retail Server en aplicaciones externas, consulte [Consumir API de servidores minoristas en aplicaciones externas](dev-itpro/consume-retail-server-api.md).

## <a name="getactiveprices"></a>GetActivePrices

La API *GetActivePrices* se introdujo en la versión 10.0.4 de Commerce. Esta API obtiene el precio calculado de un producto, incluidos los descuentos simples. No calcula los descuentos de varias líneas y asume que cada producto en una solicitud de API tiene una cantidad de 1. Esta API también puede tomar una lista de productos como entrada y consultar el precio de productos individuales de forma masiva.

La API *GetActivePrices* admite las funciones comerciales **Empleado**, **Cliente**, **Anónimo** y **Aplicación**.

El principal caso de uso para la API *GetActivePrices* es la página de detalles del producto (PDP), donde los minoristas desean mostrar el mejor precio para un producto, incluidos los descuentos efectivos.

La siguiente tabla muestra los parámetros de entrada para la API *GetActivePrices*.

| Name                                    | Nombre secundario | Tipo | Obligatorio/Opcional | Description |
|-----------------------------------------|----------|------|-------------------|-------------|
| projectDomain                           | | ProjectionDomain | Requerido | |
|                                         | ChannelId | long | Requerido | |
|                                         | CatalogId | long | Requerido | |
| productIds                              | | IEnumerable\<long\> | Requerido | La lista de productos para calcular los precios. |
| activeDate                              | | DateTimeOffset | Requerido | La fecha en que se calculan los precios. |
| customerId                              | | cadena | Opcional | Número de cuenta del cliente. |
| affiliationLoyaltyTiers                 | | IEnumerable\<AffiliationLoyaltyTier\> | Opcional | Los niveles de afiliación y fidelización. |
|                                         | AffiliationId | long | Requerido | Id. de afiliación. |
|                                         | LoyaltyTierId | long | Opcional | Id. de nivel de fidelización. |
| includeSimpleDiscountsInContextualPrice | | bool | Opcional | Establezca este parámetro en **verdadero** para incluir descuentos simples en el cálculo de precios. El valor predeterminado es **falso**. |
| includeVariantPriceRange                | | bool | Opcional | Establezca este parámetro en **verdadero** para obtener los precios mínimo y máximo entre todas las variantes para un producto maestro. El valor predeterminado es **falso**. |
| includeAttainablePricesAndDiscounts     | | bool | Opcional | Establezca este parámetro en **verdadero** para obtener precios y descuentos asequibles. El valor predeterminado es **falso**. |

**Cuerpo de solicitud de muestra**

```json
{
    "projectDomain": 
    {
        "ChannelId": 5637144592,
        "CatalogId": 0
    },
    "productIds": 
    [
        68719489871
    ],
    "activeDate": "2022-06-20T14:40:05.873+08:00",
    "includeSimpleDiscountsInContextualPrice": true,
    "includeVariantPriceRange": false
}
```

**Cuerpo de respuesta de muestra**

```json
{
    "value": 
    [
        {
            "ProductId": 68719489871,
            "ListingId": 68719489871,
            "BasePrice": 0,
            "TradeAgreementPrice": 0,
            "AdjustedPrice": 0,
            "MaxVariantPrice": 0,
            "MinVariantPrice": 0,
            "CustomerContextualPrice": 0,
            "DiscountAmount": 0,
            "CurrencyCode": "USD",
            "ItemId": "82000",
            "InventoryDimensionId": null,
            "UnitOfMeasure": "ea",
            "ValidFrom": "2022-06-20T01:40:05.873-05:00",
            "ProductLookupId": 0,
            "ChannelId": 5637144592,
            "CatalogId": 0,
            "SalesAgreementPrice": 0,
            "PriceSourceTypeValue": 1,
            "DiscountLines": [],
            "AttainablePriceLines": [],
        }
    ]
}
```

## <a name="calculatesalesdocument"></a>CalculateSalesDocument

La API *CalculateSalesDocument* se introdujo en la versión 10.0.25 de Commerce. Esta API calcula precios y descuentos para productos en cantidades determinadas si se compran juntos en un pedido. El cálculo de precios detrás de la API *CalculateSalesDocument* considera tanto los descuentos de una sola línea como los descuentos de varias líneas.

El principal caso de uso para la API *CalculateSalesDocument* es el cálculo de precios en escenarios donde el contexto completo del carrito no persiste (como cotizaciones de ventas). Los escenarios en el punto de venta (POS) y el comercio electrónico Commerce también pueden beneficiarse de este caso de uso. Un precio total más bajo cuando los artículos del carrito se calculan como un conjunto (por ejemplo, para paquetes discretos, productos vinculados o recomendados, o productos que ya se agregaron al carrito) podría persuadir a los clientes para que agreguen productos al carrito.

El modelo de datos tanto para la solicitud como para la respuesta de la API *CalculateSalesDocument* es **Carro**. Sin embargo, en el contexto de esta API, el modelo de datos se denomina **SalesDocument**. Debido a que la mayoría de las propiedades son opcionales y solo algunas de ellas afectan el cálculo de precios, en la siguiente tabla solo se muestran los campos relacionados con los precios. No recomendamos que ningún otro campo esté involucrado en la solicitud de API.

El alcance de la API *CalculateSalesDocument* es solo el cálculo de precios y descuentos. Los impuestos y cargos no están involucrados.

La siguiente tabla muestra los parámetros de entrada dentro del objeto que se llama **salesDocument**.

| Name             | Nombre secundario | Tipo | Obligatorio/Opcional | Description |
|------------------|----------|------|-------------------|-------------|
| Id.               | | cadena | Requerido | EL identificador del documento de ventas. |
| CartLines        | | IList\<CartLine\> | Opcional | La lista de líneas para calcular los precios y los descuentos. |
|                  | Id. de producto | long | Requerido en el alcance de CartLine | Id. de registro de producto. |
|                  | ItemId | cadena | Opcional | Identificador de artículo. Si se proporciona un valor, debe coincidir con el valor del parámetro **ProductId**. |
|                  | InventoryDimensionId | cadena | Opcional | Identificador de dimensión de inventario. Si se proporciona un valor, la combinación de los valores **ItemId** y **InventoryDimensionId** deben coincidir con el valor del parámetro **ProductId**. |
|                  | Quantity | decimal | Requerido en el alcance de CartLine | Cantidad del producto. |
|                  | UnitOfMeasureSymbol | cadena | Opcional | Unidad del producto. De manera predeterminada, si no se proporciona un valor, la API usa la unidad de venta del producto. |
| CustomerId       | | cadena | Opcional | Número de cuenta del cliente. |
| LoyaltyCardId    | | cadena | Opcional | Identificador de la tarjeta de fidelización. Cualquier cuenta de cliente que esté asociada con la tarjeta de fidelización debe coincidir con el valor del parámetro **CustomerId** (si se proporciona). La tarjeta de fidelización no se tendrá en cuenta si no se encuentra o su estado es **Bloqueado**. |
| AffiliationLines | | IList\<AffiliationLoyaltyTier\> | Opcional | Líneas del nivel de fidelización de la afiliación. Si los valores **CustomerId** y/o **LoyaltyCardId** se proporcionan, las líneas de nivel de fidelidad de afiliación correspondientes se fusionarán con las líneas que se proporcionan en el valor **AffiliationLines**. |
|                  | AffiliationId | long | Requerido en el alcance de AffiliationLoyaltyTier | Id. de registro de afiliación. |
|                  | LoyaltyTierId | long | Requerido en el alcance de AffiliationLoyaltyTier | Id. de registro del nivel de fidelización. |
|                  | AffiliationTypeValue | int | Requerido en el alcance de AffiliationLoyaltyTier | Un valor que indica si la línea de afiliación es del tipo **General** (**0**) o del tipo **Fidelización** (**1**). Si este parámetro se establece en **0**, la API toma el valor **AffiliationId** como el identificador e ignora el valor **LoyaltyTierId**. Si se establece en **1**, la API toma el valor **LoyaltyTierId** como el identificador e ignora el valor **AffiliationId**. |
|                  | ReasonCodeLines | Colección\<ReasonCodeLine\> | Requerido en el alcance de AffiliationLoyaltyTier | Líneas de código de motivo. Este parámetro no tiene efecto en el cálculo del precio, pero se requiere como parte del objeto **AffiliationLoyaltyTier**. |
|                  | CustomerId | cadena | Requerido en el alcance de AffiliationLoyaltyTier | Número de cuenta del cliente. |
| Vales          | | IList\<Coupon\> | Opcional | Los cupones que no sean aplicables (inactivos, caducados o no encontrados) no se tendrán en cuenta en el cálculo del precio. |
|                  | Código | cadena | Requerido en el alcance de Coupon | El código de vale. |
|                  | CodeId | cadena | Opcional | El identificador del código de vale. Si se proporciona un valor, debe coincidir con el valor del parámetro **Code**. |
|                  | DiscountOfferId | cadena | Opcional | El identificador del descuento. Si se proporciona un valor, debe coincidir con el valor del parámetro **Code**. |

**Cuerpo de solicitud de muestra**

```json
{
    "salesDocument": 
    {
        "Id": "CalculateSalesDocument",
        "CartLines": 
        [
            {
                "ProductId": 68719491408,
                "ItemId": "91003",
                "InventoryDimensionId": "",
                "Quantity": 1,
                "UnitOfMeasureSymbol": "ea"
            },
            {
                "ProductId": 68719493014,
                "Quantity": 2,
                "UnitOfMeasureSymbol": "ea"
            }
        ],
        "CustomerId": "3003",
        "AffiliationLines": 
        [
            {
                "AffiliationId": 68719476742,
                "LoyaltyTierId": 0,
                "AffiliationTypeValue": 0,
                "ReasonCodeLines": [],
                "CustomerId": null
            }
        ],
        "LoyaltyCardId": "55103",
        "Coupons": 
        [
            {
                "CodeId": "CODE-0005",
                "Code": "CPN0004",
                "DiscountOfferId": "ST100077"
            }
        ]
    }
}
```

Todo el objeto del carrito se devuelve como el cuerpo de la respuesta. Para consultar precios y descuentos, debes centrarte en los campos de la siguiente tabla.

| Name           | Nombre secundario | Tipo | Description |
|----------------|----------|------|--------------|
| NetPrice       | | decimal | El precio neto del documento de ventas completo antes de aplicar los descuentos. |
| DiscountAmount | | decimal | El importe total del descuento del documento de ventas completo. |
| TotalAmount    | | decimal | El importe total del documento de ventas completo. |
| CartLines      | | IList\<CartLine\> | Líneas calculadas que incluyen detalles de precios y descuentos. |
|                | Precio | decimal | Precio unitario del producto. |
|                | NetPrice | decimal | El precio neto de la línea antes de aplicar los descuentos (= *Precio* &times; *Cantidad*). |
|                | DiscountAmount | decimal | Importe de descuento. |
|                | TotalAmount | decimal | El resultado final del precio total de la línea. |
|                | PriceLines | IList\<PriceLine\> | Detalles del precio, incluida la fuente del precio (precio base, ajuste de precio o acuerdo comercial) y el importe. |
|                | DiscountLines | IList\<DiscountLine\> | Detalles del descuento. |

## <a name="getavailablepromotions"></a>GetAvailablePromotions 

Dado un carro que tiene varias líneas de carros, la API *GetAvailablePromotions* devuelve todos los descuentos aplicables para las líneas del carrito. 

El principal caso de uso para la API *GetAvailablePromotions* es la página del carrito, donde los minoristas quieren mostrar los descuentos aplicados o los cupones disponibles para el carrito actual.

La siguiente tabla muestra los parámetros de entrada para la API *GetAvailablePromotions*.

| Name        | Tipo | Obligatorio/Opcional | Description |
|-------------|------|-------------------|-------------|
| clave         | cadena | Requerido | El id. del carro. |
| cartLineIds | IEnumerable\<string\> | Opcional | Establezca este parámetro para devolver descuentos solo para las líneas de carrito seleccionadas. |

**Cuerpo de respuesta de muestra**

```json
{
    "value": 
    [
        {
            "LineId": "f495ffa507bc4f63a47a409cd8713dd7",
            "Promotion": {
                "OfferId": "ST100012",
                "OfferName": "Loyalty 5% off over $100",
                "PeriodicDiscountTypeValue": 4,
                "IsDiscountCodeRequired": false,
                "ValidationPeriodId": null,
                "AdditionalRestrictions": null,
                "Description": "All loyalty members get 5% with transaction total above $10 unless some exclusive or best price discounts are already applied on the transaction",
                "ValidFromDate": "2022-06-20T06:52:56.2460219Z",
                "ValidToDate": "2022-06-20T06:52:56.2460224Z",
                "CouponCodes": [],
                "ValidationPeriod": null
            }
        }
    ]
}
```

## <a name="addcoupons"></a>AddCoupons

La API *AddCoupons* admite agregar una lista de cupones a un carrito. Devuelve el objeto del carrito después de agregar los cupones.

La siguiente tabla muestra los parámetros de entrada para la API *AddCoupons*.

| Name                 | Tipo | Obligatorio/Opcional | Description |
|----------------------|------|-------------------|-------------|
| clave                  | cadena | Requerido | El id. del carro. |
| couponCodes          | IEnumerable\<string\> | Requerido | Códigos de vale para agregar al carrito. |
| isLegacyDiscountCode | bool | Opcional | Establezca este parámetro en **verdadero** para indicar que el vale es un código de descuento heredado. El valor predeterminado es **falso**. |

## <a name="removecoupons"></a>RemoveCoupons

La API *RemoveCoupons* admite la eliminación de una lista de cupones de un carrito. Devuelve el objeto del carrito después de quitar los cupones.

La siguiente tabla muestra los parámetros de entrada para la API *RemoveCoupons*.

| Name        | Tipo | Obligatorio/Opcional | Description |
|-------------|------|-------------------|-------------|
| clave         | cadena | Requerido | El id. del carro. |
| couponCodes | IEnumerable\<string\> | Requerido | Códigos de vale para quitar del carrito. |

[!INCLUDE[footer-include](../includes/footer-banner.md)]
