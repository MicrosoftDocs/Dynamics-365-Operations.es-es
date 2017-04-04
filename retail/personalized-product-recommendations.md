---
title: "Visión general de personalizada recomendaciones del producto"
description: "En Dynamics 365 para las operaciones, las recomendaciones de producto se pueden enviar a punto de dispositivo (POS) de la venta. Las recomendaciones son artículos que el cliente puede estar interesado en función de su historial de compra, los artículos de la lista de solicitudes, y los artículos que compraron otros clientes en línea y en Tiendas de físicas. Para los minoristas con los catálogos tamaño, las recomendaciones ayudan al cliente con descubrimiento del producto. Presentar los productos mediante los intereses de un cliente y los hábitos de compra, las recomendaciones de producto pueden ayudar a minoristas con que desea venta y venta cruzada, y pueden ampliar la retención de cliente. En Dynamics 365 para las operaciones, las recomendaciones del producto son accionadas por el lugar cognoscitivo de servicios y de equipo de Microsoft Azure."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: af1f4ba1ed5efe0e35d08d37d09e7ada4a4c1b7a
ms.lasthandoff: 03/31/2017


---

# <a name="personalized-product-recommendations-overview"></a>Visión general de personalizada recomendaciones del producto

En Dynamics 365 para las operaciones, las recomendaciones de producto se pueden enviar a punto de dispositivo (POS) de la venta. Las recomendaciones son artículos que el cliente puede estar interesado en función de su historial de compra, los artículos de la lista de solicitudes, y los artículos que compraron otros clientes en línea y en Tiendas de físicas. Para los minoristas con los catálogos tamaño, las recomendaciones ayudan al cliente con descubrimiento del producto. Presentar los productos mediante los intereses de un cliente y los hábitos de compra, las recomendaciones de producto pueden ayudar a minoristas con que desea venta y venta cruzada, y pueden ampliar la retención de cliente. En Dynamics 365 para las operaciones, las recomendaciones del producto son accionadas por el lugar cognoscitivo de servicios y de equipo de Microsoft Azure.

<a name="scenarios"></a>Situaciones
---------

Las recomendaciones del producto se habilitan para los siguientes escenarios de Retail POS. Son disponibles en la nube Retail POS o PDV moderno (MPOS).

1.  En ** detalles del producto ** la página:

-   Si un socio de la tienda a visita ** detalles del producto ** página a la hora de revisar transacciones anteriores a través de distintos canales, el motor de recomendación sugiere artículos adicionales que es probable que se adquieran conjuntamente.
-   Si el socio de la tienda agrega un cliente a la transacción y después visita a ** detalles del producto ** página, el motor de recomendación proporciona recomendaciones personalizadas mediante el historial de la transacción del cliente.

[proddetails de![] (. /media/proddetails.png])(. /media/proddetails.png)

2.  En ** transacción ** la página:

-   El motor de recomendación sugiere los artículos basados en la lista completa de artículos en la cesta.
-   Si el socio de la tienda agrega un cliente a la transacción, el motor de recomendación proporciona recomendaciones personales mediante el historial de la transacción del cliente y la lista de artículos en la cesta.

** Nota ** mostrar recomendaciones sobre ** transacción ** la página, minoristas el pedido o el diseño de pantalla en Dynamics 365 para las operaciones. ** Recomendaciones ** el control deben quitarse en ** transacción ** a la página. ![transactionscreenmultipleproductslargemessengersbag-5 [] (. /media/transactionscreenmultipleproductslargemessengersbag-5.jpg])(. /media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

3.  En ** Detalles del cliente ** la página:
    -   El motor de recomendación sugiere artículos en función del Id. de usuario y los artículos de la lista de solicitudes del cliente.

[customerdetailsrecommendations de![] (. /media/customerdetailsrecommendations.png])(. /media/customerdetailsrecommendations.png)

## <a name="configure-dynamics-365-for-operations-to-enable-pos-recommendations"></a>Los Dynamics 365 para que las operaciones habiliten las recomendaciones de PDV
Para configurar recomendaciones del producto, debe hacer lo siguiente.

1.  Asegúrese de que ha seleccionado el correcto ** entidad jurídica **.
2.  Desplácese ** entidad almacenada **, seleccione ** venta minorista **, y haga clic en ** ** actualización. ** ** Esto utilizará los datos de prueba (o sus datos) de la base de datos operativa y los moverá al almacén de la entidad.
3.  Opcional: Para mostrar recomendaciones sobre la visualización de la transacción, vaya ** diseño de pantalla, ** eligen su diseño de pantalla, se inicie ** diseñador de Pantalla **, ** ** y después quitan ** control de las recomendaciones ** donde necesario.
4.  Ir ** los parámetros de ventas **, seleccione Equipo- ** aprendiendo **, seleccione ** en Sí ** ** habilite las recomendaciones de PDV **.
5.  Para ver recomendaciones sobre el PDV, trabajo global de la configuración de la ejecución ** ** 1110. Para reflejar cambios creado al diseñador de pantalla de Retail POS, trabajo de la configuración del canal de la ejecución ** ** 1070.

## <a name="how-does-it-work"></a>¿[] () cómo funciona?
Al actualizar ** entidad almacenada ** la entidad, las siguientes acciones tienen lugar.

-   Los datos en el formato requerido por los servicios cognoscitivos la información de Dynamics 365 para la base de datos operativa de las operaciones y enviado al almacén de la entidad.
-   Los datos usa Azure Data Factory (ADF) para limpiar los datos mediante los scripts de una instancia como parte de las actividades de ADF. Los datos limpiado se almacena en almacenamiento del objeto binario.
-   Los datos de almacenamiento del objeto binario que usan los servicios cognoscitivos API para preparar a un modelo de recomendación.

Al activar ** recomendaciones del permiso ** y ejecuta los trabajos de configuración, las siguientes acciones tienen lugar.

-   Las credenciales de modelo y el identificador se API de recogida y se almacenan en Dynamics 365 para la base de datos operativa de operaciones, en el web.config para el AOS, y también en el servidor al por menor.
-   Las credenciales de modelo y el identificador se colocan a disposición CRT para poder honrar las llamadas para las recomendaciones de productos de la nube PDV y MPOS en modo conectado.


<a name="see-also"></a>Consulte también
--------

[Agregar un control de las recomendaciones a la página de la transacción en un dispositivo de PDV] (add-recommendations-control-pos-screen.md)


