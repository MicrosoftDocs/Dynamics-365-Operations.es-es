---
title: Agregue un control de recomendaciones a la pantalla de transacción en dispositivos de PDV
description: Este tema describe cómo agregar un control de recomendaciones a la pantalla de transacción en un dispositivo de punto de venta (PDV) mediante el diseñador de pantalla en Microsoft Dynamics 365 for Retail.
author: ashishmsft
manager: AnnBe
ms.date: 02/05/2018
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
ms.openlocfilehash: 213b47422a5e31c2cfc2d173b8c7d9efdecc7568
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "320452"
---
# <a name="add-a-recommendations-control-to-the-transaction-screen-on-pos-devices"></a>Agregue un control de recomendaciones a la pantalla de transacción en dispositivos de PDV

[!include [banner](includes/banner.md)]

> [!NOTE]
> Estamos retirando la versión actual del servicio de recomendación de productos ya que rediseñamos esta función con un algoritmo mejor y capacidades más nuevas orientadas a la venta minorista. Para obtener más información, consulte [Funciones retiradas u obsoletas](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/migration-upgrade/deprecated-features).

Este tema describe cómo agregar un control de recomendaciones a la pantalla de transacción en un dispositivo de punto de venta (PDV) mediante el diseñador de pantalla en Microsoft Dynamics 365 for Retail.

Puede mostrar recomendaciones del producto en el dispositivo de PDV cuando utilice Microsoft Dynamics 365 for Retail. Las *Recomendaciones* son artículos que pueden interesar a su cliente en función de su historial de compra, los artículos de su lista de deseos y los artículos que compraron otros clientes en línea y en tiendas de físicas. Para mostrar recomendaciones del producto, debe agregar un control a la pantalla de transacción mediante el diseñador de pantalla.

## <a name="open-layout-designer"></a>Abra el Diseñador

1. Vaya a **Venta minorista** &gt; **Configuración de canal** &gt; **Configuración de PDV** &gt; **PDV** &gt; **Diseños de pantalla**.
2. Utilice el filtro rápido para buscar la pantallla a la que desea agregar el control. Por ejemplo, filtro el campo **Id. de diseño de pantalla** usando un valor de ‘F2CP16:9M’.
3. En la lista, busque y seleccione el registro deseado. Por ejemplo, seleccione ‘Nombre: F2CP16:9M Id. de diseño de pantalla: F2CP16:9M’.
4. Haga clic en **Diseñador**.
5. Siga las instrucciones para iniciar al diseñador. Cuando se le soliciten las credenciales, introduzca las mismas credenciales que utilizó cuando se inició el Diseñador desde la página **Diseños de pantalla**.
6. Cuando inicie sesión, aparece una página similar a la siguiente. El diseño variará en función de las personalizaciones que se crearon para su tienda.

    [![screenlayout-pic-1](./media/screenlayout-pic-1.png)](./media/screenlayout-pic-1.png)

## <a name="choose-a-display-option"></a>Elija una opción de visualización

Hay dos opciones de configuración disponibles: Elija la opción que mejor se ajuste a su tienda y siga las instrucciones restantes para finalizar la configuración del control. Las dos opciones son:

- Las recomendaciones siempre están visibles.
- Aparece una pestaña de **Recomendaciones** en la cuadrícula del lado derecho de la pantalla.

### <a name="make-recommendations-always-visible"></a>Hacer que las recomendaciones estén siempre visibles

1. Reduzca la altura del área de detalles de las líneas de transacción de manera que tenga la misma altura que el panel de cliente a la izquierda.

    [![screenlayout-pic-2](./media/screenlayout-pic-2.png)](./media/screenlayout-pic-2.png)

2. En el menú de la izquierda, arrastre y suelte el control de recomendaciones entre el área de detalles de la línea de transacción y la cuadrícula de botones en la parte inferior central de la pantalla de transición. Cambie el control de modo que se ajuste a ese espacio.

    [![screenlayout-pic-3](./media/screenlayout-pic-3.png)](./media/screenlayout-pic-3.png)

3. Haga clic en la **X** para guardar y salir del Diseñador.
4. En Dynamics 365 for Retail Vaya a **Retail** &gt; **Retail TI** &gt; **Programación de distribución**.
5. En la lista, seleccione  **1090, Cajas registradoras**.
6. Haga clic en **Ejecutar ahora**.

### <a name="add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a>Agregue una pestaña de Recomendaciones a la cuadrícula de botones en el lado derecho de la pantalla

1. Haga clic con el botón secundario en el espacio vacío por debajo de la última pestaña en la cuadrícula de botones que se encuentra en el lado derecho de la página.
2. Haga clic en  **personalizar**.

    [![pic-5](./media/pic-5.png)](./media/pic-5.png)

3. Haga clic en **Nueva pestaña**.
4. Encuentre la nueva pestaña que acaba de agregar. Es posible que tenga que desplazarse hacia abajo.
5. En la lista desplegable **Contenido**, seleccione **Productos recomendados**.

    [![pic-6](./media/pic-6.png)](./media/pic-6.png)

6. En el campo **Etiqueta** , escriba un nombre para la pestaña de recomendaciones. Por ejemplo, escriba "Productos recomendados".
7. En el campo **Imagen**, seleccione la imagen que desea que aparezca en la pestaña.
8. Haga clic en **Aceptar**. La nueva pestaña aparece en la cuadrícula de botones.
9. Haga clic en la **X** para guardar y salir del Diseñador.
10. En Dynamics 365 for Retail Vaya a **Retail** &gt; **Retail TI** &gt; **Programación de distribución**.
11. En la lista, seleccione  **1090 Cajas registradoras**.
12. Haga clic en **Ejecutar ahora**.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de recomendaciones de productos personalizados](personalized-product-recommendations.md)
