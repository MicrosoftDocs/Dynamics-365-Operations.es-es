---
title: Habilitar ADLS en un entorno de Dynamics 365 Commerce
description: Este tema explica cómo habilitar y probar Azure Data Lake Storage (ADLS) para un entorno de Dynamics 365 Commerce, que es un requisito previo para habilitar las recomendaciones de productos.
author: bebeale
manager: AnnBe
ms.date: 03/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 553e1512ba72559923403eef741ce08222172a09
ms.sourcegitcommit: 1e7e7c4bc197b0a42e4d53d2a54600a2fb125b69
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2020
ms.locfileid: "3127776"
---
# <a name="enable-adls-in-a-dynamics-365-commerce-environment"></a>Habilitar ADLS en un entorno de Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Este tema explica cómo habilitar y probar Azure Data Lake Storage (ADLS) para un entorno de Dynamics 365 Commerce, que es un requisito previo para habilitar las recomendaciones de productos.

## <a name="overview"></a>Visión general

En la solución Dynamics 365 Commerce, toda la información de productos y transacciones se rastrea en el almacén de entidades del entorno. Para hacer que estos datos sean accesibles a otros servicios de Dynamics 365, como análisis de datos, inteligencia empresarial y recomendaciones personalizadas, es necesario conectar el entorno a una solución Gen 2 (ADLS) Azure Data Lake Storage del cliente.

A medida que ADLS se configura en un entorno, todos los datos necesarios se reflejan desde el almacén de entidades mientras se protegen y están bajo el control del cliente.

Si las recomendaciones del producto o las recomendaciones personalizadas también están habilitadas en el entorno, la pila de recomendaciones del producto tendrá acceso a la carpeta dedicada de ADLS para recuperar los datos del cliente y calcular las recomendaciones a partir de ahí.

## <a name="prerequisites"></a>Requisitos previos

Los clientes deben tener ADLS configurado en una suscripción de Azure que posean. Este tema no cubre la compra de una suscripción de Azure ni la configuración de una cuenta de almacenamiento habilitada para ADLS.

Para obtener más información acerca de ADLS, consulte la [documentación oficial de ADLS](https://azure.microsoft.com/pricing/details/storage/data-lake).
  
## <a name="configuration-steps"></a>Pasos de configuración

Esta sección cubre los pasos de configuración necesarios para habilitar ADLS en un entorno.

### <a name="enable-adls-in-the-environment"></a>Habilitar ADLS en el entorno

1. Inicie sesión en el portal de back office del entorno.
1. Busque **Parámetros del sistema** y navegar a la pestaña **Conexiones de datos**. 
1. Establezca **Habilitar la integración de Data Lake** en **Sí**.
1. Establezca **Actualización por goteo de Data Lake** en **Sí**.
1. Especifique la siguiente información necesaria:
    1. **Id. de aplicación** // **Secreto de la aplicación** // **Nombre DNS** - Necesario para conectarse a KeyVault, donde se almacena el secreto ADLS.
    1. **Nombre de secreto** - El nombre secreto almacenado en KeyVault que se usa para autenticarse con ADLS.
1. Guarde sus cambios en la esquina superior izquierda de la página.

En la imagen siguiente se muestra un ejemplo de configuración de ADLS.

![Ejemplo de configuración de ADLS](./media/exampleADLSConfig1.png)

### <a name="test-the-adls-connection"></a>Probar la conexión ADLS

1. Pruebe la conexión con KeyVault utilizando el vínculo **Prueba de Azure Key Vault**.
1. Pruebe la conexión con ADLS utilizando el vínculo **Probar Azure Storage**.

> [!NOTE]
> Si las pruebas fallan, verifique que toda la información de KeyVault agregada anteriormente sea correcta, luego inténtelo nuevamente.

Una vez que las pruebas de conexión sean exitosas, debe habilitar la actualización automática para el almacén de entidades.

Para habilitar la actualización automática para el almacén de entidades, siga estos pasos.

1. Busque **Almacén de entidades**.
1. En la lista de la izquierda, navegue hasta **Ventas al por menor** y seleccione **Editar**.
1. Asegúrese de que **Actualización automática habilitada** se establece en **Sí**, seleccione **Actualizar** y luego seleccione **Guardar**.

La siguiente imagen muestra un ejemplo de almacén de entidades con la actualización automática habilitada.

![Ejemplo de almacén de entidades con actualización automática habilitada](./media/exampleADLSConfig2.png)

ADLS ahora está configurado para el entorno. 

Si aún no se ha completado, siga los pasos para [habilitar las recomendaciones de productos y la personalización](enable-product-recommendations.md) para el entorno.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de recomendaciones de producto](product-recommendations.md)

[Habilitar recomendaciones de producto](enable-product-recommendations.md)

[Habilitar recomendaciones personalizadas](personalized-recommendations.md)

[Cancelar recomendaciones personalizadas](personalization-gdpr.md)

[Agregar listas de recomendaciones de producto a un sitio de comercio electrónico](add-reco-list-to-page.md)

[Agregar recomendaciones de producto en PDV](product.md)

[Agregar recomendaciones a la pantalla de transacción](add-recommendations-control-pos-screen.md)

[Ajuste los resultados de las recomendaciones AI-ML](modify-product-recommendation-results.md)

[Crear manualmente recomendaciones curadas](create-editorial-recommendation-lists.md)

[Crear recomendaciones con datos de demostración](product-recommendations-demo-data.md)

[Preguntas más frecuentes de recomendaciones de producto](faq-recommendations.md)


