---
title: "Visión general de recomendaciones de productos personalizados"
description: "Este tema tiene información sobre las recomendaciones de productos de Dynamics 365 for Retail que se pueden mostrar en el dispositivo de punto de venta (PDV)."
author: ashishmsft
manager: AnnBe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Operations, Core
ms.custom: 259664
ms.assetid: 5dd8db08-cd96-4f7e-9e65-b05ca815d580
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 64f0a9a44b97a9980f8d1b76ff158f1ac9cbc114
ms.openlocfilehash: 942d6225a46b108ea39d3b8e4376b644c128ae6d
ms.contentlocale: es-es
ms.lasthandoff: 11/15/2017

---

# <a name="personalized-product-recommendations-overview"></a>Visión general de recomendaciones de productos personalizados

[!include[banner](includes/banner.md)]


> [!NOTE]
> Esta característica está disponible en las topologías de implementación (alta disponibilidad) de espacio aislado y producción. 

En Dynamics 365 for Retail, las recomendaciones de productos se pueden visualizar en el dispositivo de punto de venta (PDV). Las recomendaciones son artículos que pueden interesar al cliente en función de su historial de compra, los artículos de su lista de deseos y los artículos que compraron otros clientes en línea y en tiendas de físicas. Para minoristas con grandes catálogos, las recomendaciones ayudan al cliente con el descubrimiento de productos. Al mostrar productos orientados a los intereses y hábitos de compra de un cliente, las recomendaciones de productos pueden ayudar a los minoristas con las ventas verticales y cruzadas, y a mejorar la retención de clientes. En Dynamics 365 for Retail, las recomendaciones de productos son impulsadas por servicios cognitivos y el aprendizaje automático de Microsoft Azure.


<a name="scenarios"></a>Situaciones
---------

Las recomendaciones de productos se habilitan para los siguientes escenarios de PDV. Están disponibles en PDV en la nube o en PDV moderno (MPOS).

1.  En la página **Detalles del producto**:

-   Si un empleado de tienda visita una página de **Detalles del producto** a la hora de buscar transacciones anteriores a través de distintos canales, el motor de recomendación sugiere artículos adicionales que es probable que se adquieran de forma conjunta.
-   Si el empleado de tienda agrega un cliente a la transacción y luego visita a página de **Detalles del producto**, el motor de recomendación proporciona recomendaciones personalizadas mediante el historial de transacción del cliente.

[![proddetails](./media/proddetails.png)](./media/proddetails.png)

2.  En la página **Transacción**:

-   El motor de recomendación sugiere los artículos en base a la lista completa de artículos en la cesta.
-   Si el empleado de tienda agrega un cliente a la transacción, el motor de recomendación proporciona recomendaciones personales mediante el historial de transacción del cliente y la lista de artículos en la cesta.

> [!NOTE]
> Para mostrar recomendaciones en la página **Transacción**, el minorista tiene que actualizar el diseño de la pantalla en Dynamics 365 for Retail. El control **Recomendaciones** debe quitarse de la página **Transacción**. [![transactionscreenmultipleproductslargemessengersbag-5](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)](./media/transactionscreenmultipleproductslargemessengersbag-5.jpg)

3.  En la página **Detalles del cliente**:
    -   El motor de recomendación sugiere los artículos en base al id. de usuario y los artículos en la lista de deseos del cliente.

[![customerdetailsrecommendations](./media/customerdetailsrecommendations.png)](./media/customerdetailsrecommendations.png)

## <a name="configure-dynamics-365-for-retail-to-enable-pos-recommendations"></a>Configure Dynamics 365 for Retail para habilitar las recomendaciones de PDV
Para configurar las recomendaciones de productos, tiene que hacer lo siguiente.

1.  Asegúrese de que ha seleccionado la **Entidad jurídica** correcta.
2.  Vaya a **Almacén de entidades**, seleccione **Ventas minoristas** y, a continuación haga clic en **Actualizar**. Esto utilizará los datos de demostración (o sus datos) de la base de datos operativa y los moverá al almacén de entidades.
3.  Opcional: para mostrar recomendaciones en la pantalla de transacción, vaya a **Diseño de pantalla**, elija su diseño de pantalla, inicie el **Diseñador de pantalla** y quite el control de **recomendaciones** cuando sea necesario.

4.  Vaya a **Parámetros de ventas al por menor** seleccione **Aprendizaje automático** y seleccione **Sí** en **Habilitar recomendaciones de PDV**.
5.  Para ver recomendaciones sobre el PDV, ejecute el trabajo de configuración global **1110**. Para reflejar los cambios realizados en el diseñador de pantalla del PVD, ejecute el trabajo de configuración de canal **1070**.

## <a name="how-does-it-work"></a>[]()¿Cómo funciona?
Al actualizar la entidad **Almacén de entidades**, tienen lugar las siguientes acciones.

-   Los datos en el formato requerido por los servicios cognitivos se extraen de la base de datos operativa Dynamics 365 for Retail y se envían al almacén de entidades.
-   Azure Data Factory (ADF) utiliza los datos para filtrarlos mediante secuencias de comandos de Hive como parte de las actividades de ADF. Los datos filtrados se guardan en un almacenamiento de blobs.
-   La API de servicio cognitivos utilizan los datos de almacenamiento de blobs para preparar a un modelo de recomendación.

Al activar **Habilitar recomendaciones del permiso** y ejecutar los trabajos de configuración, tienen lugar las siguientes acciones.

-   Las credenciales del modelo y la id. se seleccionan desde la API y se guardan en la base de datos operativa de Dynamics 365 for Retail, en el web.config para AOS y también en el Retail Server.
-   Las credenciales del modelo y el id. se ponen a disposición de CRT para que se puedan aplicar llamadas para recomendaciones de productos desde el PDV en la nube y el MPOS en modo en línea.


<a name="see-also"></a>Consulte también
--------

[Agregue un control de recomendaciones a la página de transacción en un dispositivo de PDV](add-recommendations-control-pos-screen.md)




