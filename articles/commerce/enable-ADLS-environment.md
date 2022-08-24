---
title: Habilitar Azure Data Lake Storage en un entorno de Dynamics 365 Commerce
description: Este artículo proporciona instrucciones sobre cómo conectar una slución Azure Data Lake Storage Gen 2 para el almacén de entidades del entorno de Dynamics 365 Commerce. Este es un paso obligatorio antes de habilitar las recomendaciones de productos.
author: bebeale
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail, eCommerce
ms.search.form: ''
ms.openlocfilehash: d7995e826a838796f714ced2f30220201a157f93
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9284755"
---
# <a name="enable-azure-data-lake-storage-in-a-dynamics-365-commerce-environment"></a>Habilitar Azure Data Lake Storage en un entorno de Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Este artículo proporciona instrucciones sobre cómo conectar una slución Azure Data Lake Storage Gen2 para el almacén de entidades del entorno de Dynamics 365 Commerce. Este es un paso obligatorio antes de habilitar las recomendaciones de productos.

En la solución Dynamics 365 Commerce, los datos necesarios para calcular recomendaciones, productos y transacciones se agregan en la tienda Entity del entorno. Para hacer que estos datos sean accesibles a otros servicios de Dynamics 365, como análisis de datos, inteligencia empresarial y recomendaciones personalizadas, es necesario conectar el entorno a una solución de Azure Data Lake Storage Gen2 propiedad del cliente.

Una vez completados los pasos anteriores, todos los datos del cliente en la tienda Entity del entorno se reflejan automáticamente en la solución Azure Data Lake Storage Gen 2. Cuando las funciones de recomendaciones están habilitadas a través del espacio de trabajo de gestión de funciones en la sede de Commerce, la pila de recomendaciones tendrá acceso a la misma solución Azure Data Lake Storage Gen2.

Durante todo el proceso, los datos de los clientes permanecen protegidos y bajo su control.

## <a name="prerequisites"></a>Requisitos previos

Un almacén de entidades de Dynamics 365 Commerce del entorno debe estar conectado a una cuenta de Azure Data Lake Gen Storage Gen2 y los servicios que la acompañan.

Para obtener más información acerca de Azure Data Lake Storage Gen2 y cómo configurarlo, consulte la [Documentación oficial Gen2 de Azure Data Lake Storage](https://azure.microsoft.com/pricing/details/storage/data-lake).
  
## <a name="configuration-steps"></a>Pasos de configuración

Esta sección cubre los pasos de configuración necesarios para habilitar Azure Data Lake Storage Gen2 en un entorno en relación con las recomendaciones del producto.
Para obtener una descripción más detallada de los pasos necesarios para habilitar Azure Data Lake Storage Gen2, consulte [Hacer que el almacén de entidades esté disponible como Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md).

### <a name="enable-azure-data-lake-storage-in-the-environment"></a>Habilitar Azure Data Lake Storage en el entorno

1. Inicie sesión en el portal de back office del entorno.
1. Busque **Parámetros del sistema** y navegar a la pestaña **Conexiones de datos**. 
1. Establezca **Habilitar la integración de Data Lake** en **Sí**.
1. Especifique la siguiente información necesaria:
    1. **Id. de aplicación** // **Secreto de la aplicación** // **Nombre DNS**: necesario para conectarse a KeyVault, donde se almacena el secreto de Azure Data Lake Storage.
    1. **Nombre secreto**: nombre secreto almacenado en KeyVault que se usa para autenticarse con Azure Data Lake Storage.
1. Guarde sus cambios en la esquina superior izquierda de la página.

En la imagen siguiente se muestra un ejemplo de configuración de Azure Data Lake Storage.

![Ejemplo de configuración de Azure Data Lake Storage.](./media/exampleADLSConfig1.png)

### <a name="test-the-azure-data-lake-storage-connection"></a>Probar la conexión de Azure Data Lake Storage

1. Pruebe la conexión con KeyVault utilizando el vínculo **Prueba de Azure Key Vault**.
1. Pruebe la conexión con Azure Data Lake Storage utilizando el vínculo **Probar Azure Storage**.

> [!NOTE]
> Si alguna de las pruebas anteriores fallan, confirme que toda la información de KeyVault agregada anteriormente sea correcta y luego inténtelo nuevamente.

Una vez que las pruebas de conexión sean exitosas, debe habilitar la actualización automática para el almacén de entidades.

Para habilitar la actualización automática para el almacén de entidades, siga estos pasos.

1. Busque **Almacén de entidades**.
1. En la lista de la izquierda, navegue hasta **Ventas al por menor** y seleccione **Editar**.
1. Asegúrese de que **Actualización automática habilitada** se establece en **Sí**, seleccione **Actualizar** y luego seleccione **Guardar**.

La siguiente imagen muestra un ejemplo de almacén de entidades con la actualización automática habilitada.

![Ejemplo de almacén de entidades con actualización automática habilitada.](./media/exampleADLSConfig2.png)

Azure Data Lake Storage ya está configurado para el entorno. 

Si aún no se ha completado, siga los pasos para [habilitar las recomendaciones de productos y la personalización](enable-product-recommendations.md) para el entorno.

## <a name="additional-resources"></a>Recursos adicionales

[Hacer que un almacén de entidades esté disponible como un Data Lake](../fin-ops-core/dev-itpro/data-entities/entity-store-data-lake.md)

[Visión general de recomendaciones de producto](product-recommendations.md)

[Habilitar recomendaciones de producto](enable-product-recommendations.md)

[Habilitar recomendaciones personalizadas](personalized-recommendations.md)

[Cancelar recomendaciones personalizadas](personalization-gdpr.md)

[Habilitar recomendaciones de "comprar looks similares"](shop-similar-looks.md)

[Agregar recomendaciones de producto en PDV](product.md)

[Agregar recomendaciones a la pantalla de transacción](add-recommendations-control-pos-screen.md)

[Ajuste los resultados de las recomendaciones AI-ML](modify-product-recommendation-results.md)

[Crear manualmente recomendaciones curadas](create-editorial-recommendation-lists.md)

[Crear recomendaciones con datos de demostración](product-recommendations-demo-data.md)

[Preguntas más frecuentes de recomendaciones de producto](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
