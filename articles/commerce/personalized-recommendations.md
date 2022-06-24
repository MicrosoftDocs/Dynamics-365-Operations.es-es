---
title: Habilitar recomendaciones de productos personalizadas
description: Este artículo describe cómo realizar recomendaciones de productos personalizadas disponibles para clientes en Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 08/18/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d2be5e59d51e183863da9c82d4ff733e830b8b69
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8864873"
---
# <a name="enable-personalized-recommendations"></a>Habilitar recomendaciones personalizadas

[!include [banner](includes/banner.md)]

Este artículo describe cómo realizar recomendaciones de productos personalizadas disponibles para clientes en Microsoft Dynamics 365 Commerce.

En Dynamics 365 Commerce, los minoristas pueden hacer que estén disponibles recomendaciones de productos personalizadas (lo que también se conoce como personalización). De esta manera, se pueden incorporar recomendaciones personalizadas en la experiencia del cliente en línea y en el punto de venta (PDV). Cuando se activa la funcionalidad de personalización, el sistema puede asociar la compra de un usuario y la información del producto para generar recomendaciones de productos individualizadas.

## <a name="personalization-prerequisites"></a>Requisitos previos de personalización

Antes de poner a disposición de los clientes las recomendaciones de productos personalizadas, tenga en cuenta que las recomendaciones de productos solo se admiten para los usuarios de Commerce que han migrado su almacenamiento a Azure Data Lake Store. Antes de que los clientes puedan recibir recomendaciones personalizadas de productos, los minoristas deben [activar las recomendaciones de productos](enable-product-recommendations.md).

> [!NOTE]
> Al activar recomendaciones de productos, también activa la personalización. Sin embargo, si desactiva la personalización, no desactiva los demás tipos de recomendaciones de productos.

Para obtener más información acerca de las listas de recomendaciones de productos, consulte la [Información general sobre las recomendaciones del producto](product-recommendations.md).

## <a name="turn-on-personalization"></a>Desactivar la personalización

Para activar la personalización, siga estos pasos.

1. En la central de Commerce, busque **Gestión de funciones**.
1. Seleccione **Todas** para ver una lista de funciones disponibles. 
1. En el cuadro de búsqueda, introduzca **Recomendaciones**.
1. Seleccione la característica **Recomendaciones de productos personalizados**.
1. En el panel de propiedades **Recomendaciones de productos personalizados**, seleccione **Habilitar ahora**.

![Activación de la personalización.](./media/FeatureManagement_Personalized.PNG)

> [!NOTE]
> Cuando activa la personalización, se inicia el proceso de generar listas de recomendaciones de productos personalizadas. Es posible que se requiera hasta un día antes de que estas listas estén disponibles y visibles en línea y en el PDV.

## <a name="personalized-lists"></a>Listas personalizadas

Además de permitir la personalización de las listas generadas por máquina existentes, el servicio de recomendaciones permite la personalización de la experiencia de detección de productos tanto en línea como en el PDV.

Después de que se active la personalización, los minoristas pueden mostrar a los compradores listas personalizadas de "Picking para usted" o listas de "Recomendado para el cliente" en los terminales del PDV. Además, los minoristas pueden aplicar la personalización a las listas de recomendaciones de productos existentes y proporcionar experiencias de exclusión voluntaria del Reglamento general de protección de datos (RGPD) para usuarios autenticados. Si desactiva la personalización, también desactiva estas características.

### <a name="online-picks-for-you-lists"></a>Listas en línea de "Picking para usted"

Una lista de "Picking para usted" es una lista de inteligencia artificial-aprendizaje automático (AI-ML) que muestra a un usuario autenticado una lista personalizada de productos sugeridos. Esta lista se basa en el historial de compras omnicanal del usuario. Las recomendaciones personalizadas se actualizan dinámicamente a medida que el usuario realiza más compras. Este tipo de lista también admite el filtrado de categorías, para que los minoristas puedan mostrar las mejores opciones, en función de las jerarquías de navegación.

Antes de que la lista "Picking para usted" pueda aparecer en cualquier página de comercio electrónico, se deben cumplir los siguientes requisitos de usuario:

- Los usuarios deben haber iniciado sesión. Los usuarios anónimos no verán recomendaciones personalizadas.
- Los usuarios deben tener al menos una compra en su cuenta.
- Los usuarios deben optar por recibir recomendaciones personalizadas.

La siguiente ilustración muestra un ejemplo de una lista de "Picking para usted" en la página de una tienda en línea.

![Listas en línea de Picking para usted.](./media/picksforyou.png)

### <a name="recommended-for-customer-lists-at-the-pos"></a>Listas de "Recomendado para el cliente" en el PDV

Para mejorar la experiencia de la relación con los clientes, los minoristas pueden personalizar las páginas de detalles de clientes existentes agregando una lista contextual "Recomendado para el cliente".

La siguiente ilustración muestra un ejemplo de una lista de "Recomendado para el cliente" en un terminal del PDV.

![Lista Recomendado para el cliente en el PDV.](./media/picksonpos.png)

## <a name="apply-personalization-to-existing-recommendation-lists"></a>Aplicar personalización a listas de recomendaciones existentes

Los minoristas pueden aplicar la personalización a listas de recomendaciones existentes, como "Nuevo", "Tendencias", "Más vendidos", "A la gente también le gustó" y "Los usuarios que compraron este artículo también compraron". Cuando se aplica la personalización a las listas existentes, los elementos que compró previamente un usuario que haya iniciado sesión se eliminan de esas listas. Tanto para usuarios anónimos como para usuarios que optaron por no recibir recomendaciones personalizadas, se muestran versiones predeterminadas de las listas existentes. Por lo tanto, los minoristas no tienen que mantener manualmente experiencias de página independientes.

Por ejemplo, un usuario que haya iniciado sesión ya compró el reloj negro y las botas de trabajo marrones que aparecen en la lista "Tendencias - predeterminado" en la siguiente ilustración. Por lo tanto, el usuario verá nuevos productos en lugar de esos, como se muestra en la lista "Tendencias - personalizado".

![Aplicación de la personalización.](./media/applypersonalization.png)

Para aplicar la personalización a una lista de recomendaciones existente en el generador de sitios de comercio electrónico, siga estos pasos.

1. Abra una página de generador de sitios de comercio electrónico existente que contenga un módulo de colección de productos.
1. En el panel de navegación de la izquierda, seleccione el módulo de colección de productos.
1. En el panel de navegación de la derecha, debajo de **Productos**, seleccione la lista.
1. En el cuadro de diálogo **Seleccionar la configuración de la lista de productos**, debajo de **Tipo**, seleccione el tipo de lista.
1. Selecciona la casilla **Aplicar personalización** y luego elija **Aceptar**.

    ![Aplicación de la personalización a una lista de tendencias.](./media/ApplyPersonalizationToTrending.PNG)

1. Guarde la página, termine de editarla y publíquela. Una vez publicada la página, los usuarios que hayan iniciado sesión verán listas de tendencias personalizadas.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de recomendaciones de producto](product-recommendations.md)

[Habilitar Azure Data Lake Storage en un entorno Dynamics 365 Commerce](enable-adls-environment.md)

[Habilitar recomendaciones de producto](enable-product-recommendations.md)

[Habilitar recomendaciones de "comprar looks similares"](shop-similar-looks.md)

[Cancelar recomendaciones personalizadas](personalization-gdpr.md)

[Agregar recomendaciones de producto en PDV](product.md)

[Agregar recomendaciones a la pantalla de transacción](add-recommendations-control-pos-screen.md)

[Ajuste los resultados de las recomendaciones AI-ML](modify-product-recommendation-results.md)

[Crear manualmente recomendaciones curadas](create-editorial-recommendation-lists.md)

[Crear recomendaciones con datos de demostración](product-recommendations-demo-data.md)

[Preguntas más frecuentes de recomendaciones de producto](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
