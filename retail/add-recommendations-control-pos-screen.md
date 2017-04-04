---
title: "Agregar un control de las recomendaciones a la página de la transacción en un dispositivo de PDV"
description: "Este tema describe cómo agregar un control de las recomendaciones a proteger la transacción en un dispositivo de (POS) de punto de venta mediante el diseñador de pantalla en Microsoft Dynamics 365 para las operaciones."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 2377b1639a3c95fe6bba4754c4069cc12043e3d3
ms.lasthandoff: 03/31/2017


---

# <a name="add-a-recommendations-control-to-the-transaction-page-on-a-pos-device"></a>Agregar un control de las recomendaciones a la página de la transacción en un dispositivo de PDV

Este tema describe cómo agregar un control de las recomendaciones a proteger la transacción en un dispositivo de (POS) de punto de venta mediante el diseñador de pantalla en Microsoft Dynamics 365 para las operaciones.

Puede mostrar recomendaciones del producto en el dispositivo de PDV cuando se usa el Microsoft Dynamics 365 para las operaciones. es el *Recommendations* artículos que el cliente puede ser interesado en función de su historial de compra, los artículos de la lista de solicitudes, y los artículos que compraron otros clientes en línea y en Tiendas de físicas. Para mostrar recomendaciones del producto, debe agregar un control a proteger la transacción mediante el diseñador de visualización.

## <a name="open-layout-designer"></a>Diseñador de diseño abierto
1.  ** Va al por menor y comercio ** &gt; ** el canal configurar ** &gt; ** Configuración de PDV ** &gt; ** PDV ** &gt; ** los diseños de Pantalla **.
2.  Use el filtro rápido para encontrar en la pantalla a la que desea agregar el control. Por ejemplo, filtro en ** identificador de diseño de pantalla ** campo mediante un valor de “F2CP16: los 9M”.
3.  En la lista, busque y seleccione el registro deseado. Por ejemplo, “Name seleccione: F2CP16: identificador de los 9M Screen Layout: F2CP16: los 9M”.
4.  Haga clic en ** diseñador **.
5.  Siga los indicadores para iniciar al diseñador. Cuando se le solicite para las credenciales, especifique las mismas credenciales que estén en usar cuando arrancaron al diseñador ** los diseños de Pantalla ** de la página.
6.  Cuando se inicia sesión, una página similar a la siguiente aparece. El diseño se diferente en función de las personalizaciones creadas para su tienda.

![screenlayout-pic-1 [] (. /media/screenlayout-pic-1.png])(. /media/screenlayout-pic-1.png) Elija una opción de visualización
-----------------------

Existen dos opciones de configuraciones disponibles. Elija la opción que funciona mejor para su tienda, y siga las instrucciones restantes de acabar de configurar el control. Las dos opciones son:
-   Las recomendaciones siempre son visibles.
-   A ** recomendaciones ** ficha aparece en la cuadrícula a la derecha de la pantalla.

#### <a name="to-make-recommendations-always-visible"></a>Para hacer recomendaciones siempre visible

1.  Disminuir el alto del espacio de los detalles de las líneas de transacción de modo que el mismo alto que el panel cliente a la izquierda. [] (. /media/pic-2.png![) [] (screenlayout-pic-2. /media/screenlayout-pic-2.png])(. /media/screenlayout-pic-2.png)
2.  En el menú a la izquierda, arrastrar y soltar el control de las recomendaciones entre al área de los detalles de la línea de transacción y en la parte inferior de la cuadrícula de botones en el centro de visualización de la transacción. Cambiar tamaño del control de modo que está dentro de ese espacio. [] (. /media/pic-3.png![) [] (screenlayout-pic-3. /media/screenlayout-pic-3.png])(. /media/screenlayout-pic-3.png)
3.  Hace clic en ** X ** para guardar y salir de diseñador.
4.  En Dynamics 365 para las operaciones **, vaya al por menor y comercio ** &gt; ** el TI al por menor ** &gt; ** las programaciones de distribución **.
5.  En la lista, seleccione ** 1090 registros **.
6.  Haga clic en ejecución ** ahora **.

#### <a name="to-add-a-recommendations-tab-to-the-button-grid-on-the-right-side-of-the-screen"></a>Para agregar una ficha de las recomendaciones a la cuadrícula de botones a la derecha de la pantalla

1.  Haga clic con el botón secundario en el espacio vacío por debajo de la ficha última en la cuadrícula de botones encuentra a la derecha de la página.
2.  Haga clic en ** personalice **.![pic-5 [] (. /media/pic-5.png])(. /media/pic-5.png)
3.  Haga clic en ** nueva ** ficha.
4.  Obtener una nueva ficha que acaba de agregar. Es posible que tenga que desplazarse hacia abajo.
5.  En ** ** el contenido desplegable, seleccione ** productos recomendados **. ![pic-6 [] (. /media/pic-6.png])(. /media/pic-6.png)
6.  En ** etiqueta ** el campo, escriba un nombre para la ficha de las recomendaciones. Por ejemplo, escriba “productos recomendados”.
7.  En ** imagen ** campo, seleccione la imagen que aparezcan en la ficha.
8.  Click **OK**. La nueva ficha aparece en la cuadrícula de botones.
9.  Hace clic en ** X ** para guardar y salir de diseñador.
10. En Dynamics 365 para las operaciones **, vaya al por menor y comercio ** &gt; ** el TI al por menor ** &gt; ** las programaciones de distribución **.
11. En la lista, seleccione ** 1090 registros **.
12. Haga clic en ejecución ** ahora **.


<a name="see-also"></a>Consulte también
--------

Información general [] personalizada de las recomendaciones del producto (personalized-product-recommendations.md)


