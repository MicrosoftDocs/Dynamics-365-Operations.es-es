---
title: Agregar recomendaciones a la pantalla de transacción
description: Este tema describe cómo agregar un control de recomendaciones a la pantalla de transacción en un dispositivo de punto de venta (PDV) mediante el diseñador de pantalla en Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: af2450b27106325a86f6db68f9791637694cda63
ms.sourcegitcommit: 8905d7a7a010e451c5435086480f66650ec54926
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "3665089"
---
# <a name="add-recommendations-to-the-transaction-screen"></a>Agregar recomendaciones a la pantalla de transacción

[!include [banner](includes/banner.md)]


Este tema describe cómo agregar un control de recomendaciones a la pantalla de transacción en un dispositivo de punto de venta (PDV) mediante el diseñador de pantalla en Microsoft Dynamics 365 Commerce. Para obtener más información sobre recomendaciones del producto, lea [recomendaciones del producto en la documentación de PDV](product.md).


Puede mostrar recomendaciones del producto en el dispositivo de PDV cuando utilice Commerce. Para mostrar recomendaciones del producto, debe agregar un control a la pantalla de transacción mediante el diseñador de pantalla. 

## <a name="open-layout-designer"></a>Abra el Diseñador

1. Vaya a **Retail y Commerce** &gt; **Configuración de canal** &gt; **Configuración de PDV** &gt; **PDV** &gt; **Diseños de pantalla**.
2. Utilice el filtro rápido para buscar la pantallla a la que desea agregar el control. Por ejemplo, filtro el campo **Id. de diseño de pantalla** usando un valor de **F2CP16:9M**.
3. En la lista, busque y seleccione el registro deseado. Por ejemplo, seleccione **Nombre: F2CP16:9M Id. de diseño de pantalla: F2CP16:9M**.
4. Haga clic en **Diseñador**.
5. Siga las instrucciones para iniciar al diseñador. Cuando se le soliciten las credenciales, introduzca las mismas credenciales que utilizó cuando se inició el Diseñador desde la página **Diseños de pantalla**.
6. Cuando inicie sesión, aparece una página similar a la siguiente. El diseño variará en función de las personalizaciones que se crearon para su tienda.


    [![Diseñador](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)

## <a name="choose-a-display-option"></a>Elija una opción de visualización

Hay dos opciones de configuración disponibles: Elija la opción que mejor se ajuste a su tienda y siga las instrucciones restantes para finalizar la configuración del control. Las dos opciones son:

- Las recomendaciones siempre están visibles.
- Aparece una pestaña de **Recomendaciones** en la cuadrícula del lado derecho de la pantalla.

### <a name="make-recommendations-always-visible"></a>Hacer que las recomendaciones estén siempre visibles


1. Reduzca la altura del área de detalles de las líneas de transacción de manera que tenga la misma altura que el panel de cliente a la izquierda.


    [![La altura del espacio de los detalles de las líneas de transacción se ha reducido](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)

2. En el menú de la izquierda, arrastre y suelte el control de recomendaciones entre el área de detalles de la línea de transacción y la cuadrícula de botones en la parte inferior central de la pantalla de transición. Cambie el control de modo que se ajuste a ese espacio.

    [![Se han agreado al diseño las recomendaciones de control](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)


3. Haga clic en la **X** para guardar y salir del Diseñador.
4. En Commerce, vaya a **Retail y Commerce** &gt; **TI de Retail y Commerce** &gt; **Programaciones de distribución**.
5. En la lista, seleccione **1090, Cajas registradoras**.
6. Haga clic en **Ejecutar ahora**.


### <a name="add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a>Agregue una pestaña de Recomendaciones a la cuadrícula de botones en el lado derecho de la pantalla

1. Haga clic con el botón secundario en el espacio vacío por debajo de la última pestaña en la cuadrícula de botones que se encuentra en el lado derecho de la página.

2. Haga clic en **personalizar**.

    [![Personalización - Pestaña de control del cuadro de diálogo](./media/pic-5.png)](./media/pic-5.png)

3. Haga clic en **Nueva pestaña**.
4. Encuentre la nueva pestaña que acaba de agregar. Es posible que tenga que desplazarse hacia abajo.
5. En la lista desplegable **Contenido**, seleccione **Productos recomendados**.

    [![Seleccionando productos recomendados en el campo contenidos](./media/pic-6.png)](./media/pic-6.png)

6. En el campo **Etiqueta** , escriba un nombre para la pestaña de recomendaciones. Por ejemplo, escriba "Productos recomendados".
7. En el campo **Imagen**, seleccione la imagen que desea que aparezca en la pestaña.
8. Haga clic en **Aceptar**. La nueva pestaña aparece en la cuadrícula de botones.
9. Haga clic en la **X** para guardar y salir del Diseñador.
10. En Commerce, vaya a **Retail y Commerce** &gt; **TI de Retail y Commerce** &gt; **Programaciones de distribución**.
11. En la lista, seleccione **1090, Cajas registradoras**.
12. Haga clic en **Ejecutar ahora**.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de recomendaciones de producto](product-recommendations.md)

[Habilitar Azure Data Lake Storage en un entorno Dynamics 365 Commerce](enable-adls-environment.md)

[Habilitar recomendaciones de producto](enable-product-recommendations.md)

[Habilitar recomendaciones personalizadas](personalized-recommendations.md)

[Cancelar recomendaciones personalizadas](personalization-gdpr.md)

[Habilitar recomendaciones de "comprar looks similares"](shop-similar-looks.md)

[Agregar recomendaciones de producto en PDV](product.md)

[Ajuste los resultados de las recomendaciones AI-ML](modify-product-recommendation-results.md)

[Crear manualmente recomendaciones curadas](create-editorial-recommendation-lists.md)

[Crear recomendaciones con datos de demostración](product-recommendations-demo-data.md)

[Preguntas más frecuentes de recomendaciones de producto](faq-recommendations.md)
