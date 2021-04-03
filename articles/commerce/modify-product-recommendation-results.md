---
title: Ajustar resultados de recomendaciones de producto basadas en AI-ML
description: Este tema explica cómo ajustar los resultados de recomendaciones de productos según la inteligencia artificial-aprendizaje automático (AI-ML) para tu negocio.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: b9e370faed7feb0640959a9fcc4b608f18f9ffc1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263955"
---
# <a name="adjust-ai-ml-based-product-recommendation-results"></a>Ajustar resultados de recomendaciones de producto basadas en AI-ML


[!include [banner](includes/banner.md)]

En este tema se explica cómo ajustar los resultados de recomendaciones de productos mediante técnicas de inteligencia artificial-aprendizaje automático (AI-ML) para su empresa. 

Tras habilitar las recomendaciones de productos, entrarán en vigor las configuraciones predeterminadas; estos parámetros funcionarán ya que pueden funcionar para muchas necesidades. Es mejor planificar pasar algún tiempo evaluando si los resultados se ajustan al movimiento de venta de los productos. Sugerimos evaluar los resultados durante varios días antes de cambiar los parámetros según sea necesario antes de probar de nuevo. 

## <a name="understanding-recommendation-list-parameters"></a>Descripción de los parámetros de la lista de recomendaciones

Antes de cambiar los parámetros, descubra cómo afectarán a los resultados siguientes.

### <a name="trending-product-list"></a>Lista de productos "Tendencias"

La lista de productos "Tendencias" tiene dos parámetros que se pueden cambiar:

![Parámetros predeterminados de lista "Tendencias" de ejemplo](./media/exampletrendingparameters.png)

1. **Incluir nuevos productos desde los últimos X días**: los productos que se han agregado dentro del número de días especificados antes de la fecha actual se pueden usar en los candidatos de productos seleccionados. El valor predeterminado de la imagen sugiere que los productos con una antigüedad de 180 días se pueden usar en la lista de productos de tendencias.
1. **Incluir ventas de los últimos X días**: las transacciones de ventas que se han producido dentro del número de días especificados antes de la fecha actual se pueden usar para pedir productos. El valor predeterminado anterior sugiere que todas las compras realizadas de un producto en los últimos 30 días se utilizarían para determinar la posición del producto en la lista de productos de tendencias. 

### <a name="best-selling-product-list"></a>Lista de productos "Más vendidos"

Según su empresa, la lista "Más vendidos" puede llevar diferentes resultados a las tendencias, aunque ambos usen datos de transacción para pedir productos. Dado que Más vendidos no tiene límite según la fecha de selección, Más vendidos todavía puede resaltar los productos más antiguos y muy populares que puedan haberse quitado de la lista de tendencias. 

La lista de productos "Más vendidos" tiene un parámetro que se puede cambiar:

![Parámetro predeterminado de lista Más vendidos de ejemplo](./media/examplebestsellingparameters.PNG)

1. **Incluir ventas de los últimos X días**: las transacciones de ventas que se han producido dentro del número de días especificados antes de la fecha actual se pueden usar para pedir productos. El valor predeterminado anterior sugiere que todas las compras realizadas de un producto en los últimos 30 días se utilizarían para determinar la posición del producto en la lista de productos Más vendidos. 

## <a name="manually-add-or-remove-products-from-recommendation-lists"></a>Agregar o quitar productos de listas de recomendación

### <a name="for-new-trending-or-best-selling-lists"></a>Para lista "Nuevos", "Tendencias" o "Más vendidos"

1.  Vaya a **Retail y Commerce** > **Recomendaciones de producto** > **Parámetros de recomendaciones**.
1.  En la lista de parámetros compartidos, seleccione **Listas de recomendaciones**.
1.  Seleccione la lista desde la que agregar o quitar productos.
1.  Para agregar productos a la tabla, seleccione **Agregar línea**. 
1.  En la columna Producto, busque un producto por **Nombre** o **Número de producto**.

    ![Ejemplo de búsqueda de un producto en la lista Nuevo producto](./media/examplenewlistconfiguration1.png)

1.  En la columna Tipo de línea, seleccione una de dos opciones:
    -   **Incluir**: fuerza un producto a la parte delantera de la lista
    -   **Excluir** hace que un producto no aparezca en la lista.
    
    ![Ejemplo de inclusión o exclusión de un producto de la lista Nuevo producto](./media/examplenewlistconfiguration2.png)

1.  Al cambiar el **Orden de visualización** se cambiará el orden en que los productos marcados con **incluir** aparecerán en la lista.
    - Si dos productos tienen el mismo valor de **orden de visualización**, el orden final de estos dos resultados puede ser diferente de la oficina administrativa.
1.  Para quitar productos de la tabla: seleccione la línea que desee quitar y seleccione **Eliminar**.


### <a name="for-people-also-like-or-frequently-bought-together-lists"></a>Para las listas "A la gente también le gustó" o "Los usuarios que compraron esto también compraron"

En el contexto de las listas "Los usuarios que compraron esto también compraron" o "A la gente también le gustó", se utiliza el aprendizaje automático para analizar patrones de compra de consumo para recomendar productos relacionados comprados habitualmente juntos para un producto único de inicialización. 
 
Un *producto de inicialización* es el producto para el que desea generar resultados. En el contexto de ajustar manualmente listas de recomendaciones, agrega o elimina resultados para este producto. 

Siga estos pasos para agregar o eliminar manualmente los resultados para un producto de inicialización:
1.  Seleccione el **Producto de inicialización**. 
1.  En la columna **Producto**, busque un producto por **Nombre** o **Número de producto.**
![Ejemplo de buscar un producto en la lista Los usuarios que compraron esto también compraron](./media/exampleFBTlistconfiguration1.png)
1. En la columna **Tipo de línea**, seleccione una de dos opciones:
    - **Incluir**: fuerza un producto a la parte delantera de la lista
    - **Excluir** hace que un producto no aparezca en la lista.     
![Ejemplo de incluir o excluir un producto en la lista Los usuarios que compraron esto también compraron](./media/exampleFBTlistconfiguration2.png)
1.  Para quitar productos de la tabla: seleccione la línea que desee quitar y seleccione Eliminar.


## <a name="additional-resources"></a>Recursos adicionales

[Visión general de recomendaciones de producto](product-recommendations.md)

[Habilitar Azure Data Lake Storage en un entorno Dynamics 365 Commerce](enable-adls-environment.md)

[Habilitar recomendaciones de producto](enable-product-recommendations.md)

[Habilitar recomendaciones personalizadas](personalized-recommendations.md)

[Cancelar recomendaciones personalizadas](personalization-gdpr.md)

[Habilitar recomendaciones de "comprar looks similares"](shop-similar-looks.md)

[Agregar recomendaciones de producto en PDV](product.md)

[Agregar recomendaciones a la pantalla de transacción](add-recommendations-control-pos-screen.md)

[Crear manualmente recomendaciones curadas](create-editorial-recommendation-lists.md)

[Crear recomendaciones con datos de demostración](product-recommendations-demo-data.md)

[Preguntas más frecuentes de recomendaciones de producto](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]