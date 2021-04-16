---
title: Dimensiones de producto
description: 'Hay cinco dimensiones de producto: color, configuración, tamaño, estilo y versión. Combina dimensiones de producto en grupos de dimensiones y asigna grupos de dimensiones a productos maestros. Las combinaciones de dimensiones de producto determinan la manera en que se definen las variantes de producto.'
author: t-benebo
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle, EcoResVersionNameLookup, RetailStyleGroupTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: dc7c92287ff88fe46b5aa46e15f7af3344d11e3e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5820283"
---
# <a name="product-dimensions"></a>Dimensiones de producto

[!include [banner](../includes/banner.md)]

Hay cinco dimensiones de producto: color, configuración, tamaño, estilo y versión. Combina dimensiones de producto en grupos de dimensiones y asigna grupos de dimensiones a productos maestros. Las combinaciones de dimensiones de producto determinan la manera en que se definen las variantes de producto.

Las dimensiones de un producto son las características que permiten identificar una variante del producto. Puede utilizar combinaciones de dimensiones de producto para definir variantes de producto. Se debe definir al menos una dimensión del producto para un producto maestro si desea crear una variante del producto.

## <a name="product-variants"></a>Variantes de producto

Las variantes del producto también se conocen como artículos. Un artículo es un producto tangible, que no es igual que un servicio. También es posible definir un producto maestro con el tipo de servicio. Mediante el tipo de servicio, puede especificar las variantes del producto que incluyen servicios. Por ejemplo, puede especificar un producto maestro para el asesoramiento del trabajo y variantes del producto para el trabajo realizado por los asesores sénior y júnior.

## <a name="product-dimensions"></a>Dimensiones de producto

Se puede generar una variante del producto a partir de los valores de dimensión del producto.

Los valores de dimensión de producto para las dimensiones de tamaño, color y estilo se pueden crear en las siguientes ubicaciones:

- Página **Tamaño** (**Gestión de información de productos \> Configuración \> Grupos de dimensiones y variantes \> Tamaños**)
- Página **Color** (**Gestión de información de productos \> Configuración \> Grupos de dimensiones y variantes \> Colores**)
- Página **Estilo** (**Gestión de información de productos \> Configuración \> Grupos de dimensiones y variantes \> Estilos**)

Los valores de dimensión del producto para la dimensión de configuración se crean normalmente mediante el configurador de productos o el configurador basado en dimensiones. 

Las versiones del producto se suelen crear para versiones específicas a medida que el producto evoluciona durante su ciclo de vida. Las versiones de productos se tratan en detalle más adelante en este tema.

Las dimensiones del producto también se pueden crear y mantener en la página **Dimensiones de producto**, a la que se puede tener acceso desde las ubicaciones siguientes:

- Vaya a **Gestión de información de productos \> Productos \> Productos maestros**. En el panel de acciones, seleccione **Dimensiones de producto**.
- Vaya a **Gestión de información de productos \> Productos \> Todos los productos y productos maestros**. Seleccione un producto maestro. En el panel de acciones, seleccione **Dimensiones de producto**.
- Vaya a **Gestión de información de productos \> Productos emitidos**. Seleccione un producto maestro. En el panel de acciones, en la pestaña **Producto** del grupo **Producto maestro**, seleccione **Dimensiones de producto**.

El número de variantes que se pueden crear para un artículo está limitado por el número de posibles combinaciones de las dimensiones del producto.

> [!TIP]
> Al utilizar un producto en una línea de pedido, por ejemplo, seleccione las dimensiones del producto para identificar la variante del producto con la que desee trabajar.

## <a name="example"></a>Ejemplo

Una empresa vende pantalones vaqueros. El artículo, *Vaqueros*, utiliza las dimensiones de producto color y tamaño. Éstos se venden en tres colores distintos y seis tamaños distintos. Los colores son azul, negro y marrón. Los tamaños son XS, S, M, L, XL y XXL. No todas las tallas están disponibles en los tres colores. Si todas las combinaciones estuviesen disponibles, el resultado sería de 18 tipos de vaqueros distintos. Sin embargo, en este ejemplo solo se producen las nueve combinaciones siguientes de variantes del producto.

| Color | Tamaño |
|-------|------|
| Azul  | XS   |
| Azul  | S    |
| Azul  | M    |
| Negro | M    |
| Negro | L    |
| Negro | XL   |
| Marrón | L    |
| Marrón | XL   |
| Marrón | XXL  |

## <a name="the-version-product-dimension"></a>La dimensión de producto "versión"

La versión es una dimensión del producto que está destinada a ayudarlo a mantener y rastrear múltiples versiones de un producto a lo largo de la cadena de suministro. El seguimiento de versiones es esencial para el éxito de los fabricantes que operan en un mundo en el que los ciclos de vida de los productos se reducen constantemente, los requisitos de calidad y confiabilidad aumentan y el enfoque en la seguridad del producto es mayor.

Como dimensión estándar del producto, la versión se comportará de manera similar a las dimensiones del producto existente (tamaño, estilo, color y configuración). Por lo tanto, puede usarlo para otros fines además de rastrear versiones de productos.

### <a name="turn-on-the-version-dimension"></a><a name="enable-version-dim"></a>Activar la dimensión de versión

#### <a name="before-you-turn-on-the-version-dimension"></a>Para poder activar la dimensión de versión

Cuando activa la dimensión de versión, algunas funciones podrían romperse o dejar de funcionar como se esperaba si ha instalado otras soluciones que agregan personalizaciones a las dimensiones de inventario. Para que la dimensión de la versión sea completamente funcional, es posible que deba actualizar esas soluciones para que incluyan la dimensión de la versión en sus referencias a las dimensiones del inventario.

Cuando esté probando la compatibilidad de sus soluciones con la dimensión de la versión, busque los siguientes elementos:

1. **Funcionalidad:** lo más importante es que se debe evaluar cualquier personalización que involucre las dimensiones del inventario para garantizar que puedan funcionar junto con la dimensión de la versión.
1. **Referencias a las dimensiones del inventario:** busque referencias a las dimensiones del inventario (es decir, lugares donde se hace referencia explícita a las dimensiones). Las referencias a `InventDimId` deberían funcionar desde el primer momento, pero busque referencias de estilo o color. Por ejemplo, asegúrese de comprobar los siguientes elementos:

    - Llamadas a API en clases extendidas
    - Todas las referencias a dimensiones de inventario específicas en el código de extensión (este código debe incluir la dimensión de la versión junto con las dimensiones de estilo, color y tamaño).

1. **Referencias a llamadas a la API obsoletas:** al introducir la dimensión de versión, Microsoft ha tratado de hacer obsoletas la menor cantidad posible de API. Las pocas API que han quedado en desuso emitirán una advertencia cuando se active la clave de configuración **Dimensión de producto - versión**. Las llamadas a esas API deberán corregirse en las soluciones extendidas antes de activar la dimensión de versión en un sistema de producción. Estas son las API que han quedado en desuso específicamente por la dimensión de versión:

    - RetailTransactionServiceInventory::getProductRecordId
    - EcoResProductNumberIdentifiedProductVariantEntity::find
    - EGAISAlcoholProduction_RU::findByItemDim
    - PCVariantConfiguration::findByProductMasterAndDimensions

1. **Asignaciones:** si alguna asignación usa las dimensiones del inventario, hay que actualizar la asignación de relación correspondiente a estas asignaciones para que incluya la dimensión de la versión. En el modelo extendido o las extensiones de tabla, busque tablas en las que los campos incluyan dimensiones de inventario.
1. **Funcionalidad de Microsoft Dynamics 365 Commerce**: una vez activada, la dimensión de versión aparecerá en todo el código específico de Commerce en Dynamics 365 Supply Chain Management. Sin embargo, la dimensión de versión aún no es compatible con la base de datos de canal de Commerce ni con las aplicaciones de punto de venta (PDV) o de comercio electrónico. Estas aplicaciones específicas de Commerce no admitirán a los usuarios que vendan/envíen o devuelvan/reciban inventario por dimensión de versión. Las funciones de búsqueda de disponibilidad de inventario no discernirán el inventario por dimensión de versión en las aplicaciones de Commerce. Este comportamiento se parece al comportamiento actual de la dimensión de configuración en Commerce.

#### <a name="turn-on-the-version-dimension"></a>Activar la dimensión de versión

Para poder usar la dimensión de versión, debe estar activada en su sistema. Esta tarea requiere permisos de administrador.

1. Vaya a **Administración del sistema \> Espacios de trabajo \> Administración de características**.
1. Active la característica llamada *Versión de dimensión del producto*. (Para obtener más información, consulte [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)).
1. Coloque el sistema en [Modo de mantenimiento](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Vaya a **Administración del sistema \> Configuración \> Configuración de licencias**.
1. En la pestaña **Claves de configuración**, expanda **Comercio** y active la casilla **Dimensión de producto - versión**.
1. Desactive el [Modo de mantenimiento](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).

### <a name="areas-where-the-version-dimension-isnt-supported"></a>Áreas en las que no se admite la dimensión de versión

Las siguientes áreas no admiten la dimensión de versión (aún puede usar estas áreas, pero no podrá agregarles productos versionados [productos donde se usa la dimensión de versión]). Por ejemplo, no puede agregar un artículo versionado a un catálogo de proveedores. Esto se debe a que agregar productos con la dimensión de versión a estas áreas provocaría cambios importantes.

- Extracto mensual del objeto de coste
- Caché de extractos de objeto de costes
- Estadísticas de ventas de MCR por artículo
- Catálogos de proveedores
- EcoResProductDimensionGroupEntity

Además, las características de creación y procesamiento de pedidos de Commerce (por ejemplo, para pedidos de PDV, centro de llamadas y comercio electrónico) no admiten la dimensión de versión. No hay un plazo confirmado para mejorar los pedidos de Commerce con la incorporación de esta dimensión.

### <a name="functional-characteristics-of-the-version-dimension"></a>Características funcionales de la dimensión de versión

La dimensión de versión funciona como las demás dimensiones del producto. Sin embargo, debido a su naturaleza específica y a que está destinada a mantener y rastrear múltiples versiones de un producto, se comporta de manera ligeramente diferente. Estas son algunas de las diferencias y similitudes:

- **No hay un grupo de versiones.**

    Aunque el concepto de grupo existe para el tamaño, el color y el estilo (grupo de colores, grupo de tamaños y grupo de estilos), no existe el concepto de grupo de versiones. Los grupos permiten predefinir los valores aplicables de modo que cuando, por ejemplo, se asigna un grupo de colores a un producto, el producto puede usar todos los colores de ese grupo de colores. Este concepto no se aplica a la dimensión de versión, ya que las versiones de un producto no están predefinidas cuando se crea el producto. Las versiones se crean durante el ciclo de vida del producto, según sea necesario. Normalmente, si la forma, el ajuste y la función del producto siguen siendo los mismos, se crea una nueva versión en lugar de un producto nuevo.

- **Las sugerencias de variantes de productos funcionan como lo hacen actualmente.**

    Las sugerencias de variantes de producto crearán sugerencias para todos los valores de dimensión de versión, al igual que lo hacen para otras dimensiones. El proceso de creación y lanzamiento de productos con versiones es el mismo que para los productos que utilizan otras dimensiones. Al crear un producto con versiones, la primera versión (V1) se creará como una dimensión de producto y se lanzarán las variantes. A medida que el producto cambie y se necesite una nueva versión, se agregará el valor de la nueva versión (V2) y se lanzarán las variantes requeridas. No se espera que todas las versiones (V1, V2 y V3) se creen de antemano para el producto.

> [!IMPORTANT]
> Si activa y utiliza la dimensión de versión, algunas soluciones que hagan referencia a las dimensiones de inventario pueden dejar de funcionar como se esperaba. Para confirmar y solucionar estos problemas, póngase en contacto con el proveedor de software independiente (ISV) de las soluciones afectadas. Para más información, consulte [Habilitar la dimensión de versión](#enable-version-dim).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]