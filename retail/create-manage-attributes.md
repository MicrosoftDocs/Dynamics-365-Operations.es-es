---
title: Permite crear y gestionar atributos
description: "Este artículo describe atributos en Microsoft Dynamics 365 for Operations. Los atributos le permiten describir un producto y sus características a través de campos definidos por el usuario."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 16461
ms.assetid: 2b85491c-f830-4e79-a2cb-681b7ced6988
ms.search.region: global
ms.search.industry: Retail
ms.author: prabhup
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6b1f91f863c8da35362ebb3036e76aa10d95ba65
ms.openlocfilehash: a5c45bb0b9ed10c989a3222a751df3f454b14a0b
ms.contentlocale: es-es
ms.lasthandoff: 04/26/2017


---

# <a name="create-and-manage-attributes"></a>Permite crear y gestionar atributos

[!include[banner](includes/banner.md)]


Este artículo describe atributos en Microsoft Dynamics 365 for Operations. Los atributos le permiten describir un producto y sus características a través de campos definidos por el usuario.

Los atributos le permiten describir un producto y sus características a través de campos definidos por el usuario. Por ejemplo, puede especificar el tamaño de la memoria del producto y la capacidad del disco duro, e indicar si el producto es compatible con las estrellas de energía. Los atributos se pueden asociar con las distintas entidades minoristas, como categorías de productos y canales de venta minorista, y se pueden definir valores predeterminados. Los productos heredan sus atributos y los valores predeterminados para dichos atributos cuando se asocian a las categorías de productos o canales de venta minorista. Los valores predeterminados se pueden anular en el nivel de producto individual, en el nivel del canal de venta minorista o en un catálogo de venta minorista.

#### <a name="examples"></a>Ejemplo

| Categoría   | Atributo                | Valores permitidos          | Valor predeterminado |
|------------|--------------------------|-----------------------------|---------------|
| Televisión y vídeo | Marca                    | Cualquier valor de Marca válido       | Ninguna          |
| Televisión         | Tamaño de pantalla              | 20" – 80"                     | Ninguna          |
| Televisión         | Resolución vertical      | 480i, 720p, 1080i o 1080p | 1080p         |
| Televisión         | Intervalo de actualización de la pantalla      | 60hz120hz o 240hz       | 60hz          |
| Televisión         | Entradas HDMI              | 0 – 10                        | 3             |
| Televisión         | Entradas DVI               | 0 – 10                        | 1             |
| Televisión         | Entradas compuestas         | 0 – 10                        | 2             |
| Televisión         | Entradas del componente         | 0 – 10                        | 1             |
| LCD        | Preparada para 3D                 | Sí o No                   | Sí           |
| LCD        | Habilitada para 3D               | Sí o No                   | No            |
| Plasma     | Temporalidad de operación desde      | 32–110 grados              | 32            |
| Plasma     | Temporalidad de operación hasta        | 32–110 grados              | 100           |
| Proyección | Garantía de tubo de proyección | 612 o 18 meses         | 12            |
| Proyección | #  de tubos de proyección    | 1 – 5                         | 3             |


## <a name="attribute-type"></a>Tipo de atributo
  [![copia-de-atributos-fijos](./media/attributes-fixed-copy.png)](./media/attributes-fixed-copy.png) 
  
Los atributos se basan en tipos de atributo. Los tipos de atributo identifican el tipo de datos que se pueden introducir para un atributo específico. Actualmente, Microsoft Dynamics 365 for Operations admite los tipos de atributo siguientes:

-   **Moneda:** este tipo de atributo admite valores de divisa. Puede estar limitado (es decir, puede admitir un intervalo de valores) o se puede dejar abierto.
-   **DateTime:** este tipo de atributo admite valores de fecha y hora. Puede estar limitado (es decir, puede admitir un intervalo de valores) o se puede dejar abierto.
-   **Decimal:** este tipo de atributo admite los valores numéricos que incluyen decimales. También admite unidades de medida. Puede estar limitado (es decir, puede admitir un intervalo de valores) o se puede dejar abierto.
-   **Número entero:** este tipo de atributo admite valores numéricos. También admite unidades de medida. Puede estar limitado (es decir, puede admitir un intervalo de valores) o se puede dejar abierto.
-   **Texto:** este tipo de atributo admite valores de texto. También admite un sistema predefinido de valores posibles (numeración).
-   **Boolean**: este tipo de atributo admite valores binarios (**verdadero**/**falso**).
-   **Referencia**.

## <a name="attribute"></a>Atributo
  [![createandmanageattribute-8](./media/createandmanageattribute-8.png)](./media/createandmanageattribute-8.png) Además del nombre, el nombre descriptivo, la descripción y el texto de ayuda, uno o más de los siguientes tipos de información se pueden capturar para un atributo:

-   Valor predeterminado
-   El atributo metadatos, como metadatos que indican si el atributo puede ser buscado, se refinado o clasificado

## <a name="attribute-group"></a>Grupo de atributos
  [![createandmanageattribute-10](./media/createandmanageattribute-10.png)](./media/createandmanageattribute-10.png) Después de que se hayan definido los atributos, se pueden agrupar en grupos de atributos. Los grupos de atributos proporcionan agrupaciones de atributos individuales y se pueden asignar a las categorías de venta minorista o a los canales de venta minorista.

## <a name="assigning-attribute-groups-to-retail-categories"></a>Asignar grupos de atributos a las categorías de venta minorista
  [![createandmanageattribute-12](./media/createandmanageattribute-12.png)](./media/createandmanageattribute-12.png) Uno o más grupos de atributos se pueden asociar con nodos de categoría en la jerarquía de categoría de productos de venta minorista. Cuando se han clasificado los productos, heredan los atributos incluidos en los grupos de atributos.

## <a name="assigning-attribute-groups-to-retail-stores"></a>Asignar grupos de atributos a las tiendas de venta minorista
  [![createandmanageattribute-13-1024x576](./media/createandmanageattribute-13-1024x576.png)](./media/createandmanageattribute-13-1024x576.png) Uno o más grupos de atributos se pueden asociar con tiendas de venta minorista en la jerarquía de categoría de tiendas de venta minorista. Cuando se han enriquecido los productos para tiendas de enta minorista concretas, heredan los atributos incluidos en los grupos de atributos.

## <a name="overriding-attribute-values"></a>Anular valores de atributos
### <a name="at-the-product-level"></a>En el nivel de productos

  [![createandmanageattribute-14-1024x576](./media/createandmanageattribute-14-1024x576.png)](./media/createandmanageattribute-14-1024x576.png) Los valores predeterminados de atributos se pueden anular en el nivel de producto (es decir, para productos individuales).

### <a name="in-a-retail-catalog"></a>En un catálogo comercial

  [![createandmanageattribute-2](./media/createandmanageattribute-2.png)](./media/createandmanageattribute-2.png) Los valores predeterminados de atributos se pueden anular para los productos individuales en los catálogos específicos que se dirigen a los canales de venta minorista específicos.

### <a name="at-the-retail-channel-level"></a>En el nivel de canal comercial

  [![createandmanageattribute-1](./media/createandmanageattribute-1.jpg)](./media/createandmanageattribute-1.jpg) Los valores predeterminados de atributos se pueden anular para los productos individuales en los catálogos específicos que se dirigen a los canales de venta minorista específicos.




