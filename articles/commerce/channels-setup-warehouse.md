---
title: Configurar un almacén
description: En este tema se describe cómo configurar un almacén para utilizarlo con un nuevo canal en Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 772c7584549b30a34e371a7911131edc01214ed8
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477643"
---
# <a name="warehouse-set-up"></a>Configuración de almacén

[!include [banner](includes/banner.md)]

En este tema se describe cómo configurar un almacén para utilizarlo con un nuevo canal en Microsoft Dynamics 365 Commerce.

Cada canal de Commerce requiere que se le asocie un almacén configurado. Los siguientes procedimientos proporcionan la configuración mínima requerida para configurar un almacén para un canal de Commerce. Para obtener más información sobre la configuración del almacén, consulte la [Visión general de la gestión de almacenes](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json).

## <a name="configure-a-warehouse-site"></a>Configurar un sitio de almacén

Antes de configurar un almacén, debe configurar un sitio de almacén.

Para configurar un sitio de almacén, siga estos pasos.

1. En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de canal \> Sitios**.
1. En el panel de acciones, seleccione **Nueva**.
1. En el campo **Sitio**, escriba un valor.
1. En el campo **Nombre**, escriba un valor.
1. En la sección **General**, establezca la **Zona horaria** apropiada.
1. En la sección **Direcciones**, escriba una dirección.
1. En el panel de acciones, seleccione **Guardar**.

La siguiente imagen muestra un ejemplo de sitio de almacén.

![Ejemplo de sitio de almacén](media/warehouse-site.png)

## <a name="set-up-a-warehouse"></a>Configurar un almacén

Para configurar un almacén, siga estos pasos.

1. En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de canal \> Almacenes**.
1. En el panel de acciones, seleccione **Nueva**.
1. En el campo **Almacén**, especifique o seleccione un valor.  Si se trata de una asignación 1:1 a una tienda, considere la posibilidad de usar el nombre de la tienda o el nombre de un centro de distribución regional.
1. En el campo **Nombre**, escriba un valor.
1. En la lista desplegable **Sitio**, seleccione el sitio de almacén creado previamente.
1. En el campo **Tipo**, seleccione **Predeterminado**.
    - Si desea establecer un **Almacén de cuarentena**, primero deberá seguir estos pasos para crear un almacén adicional donde se establezca **Tipo** en **Cuarentena**.
    - Si desea establecer un **Almacén de tránsito**, primero debe seguir estos pasos para crear un almacén adicional donde se establezca **Tipo** en **Tránsito**.
1. En el panel de acciones, seleccione **Guardar**.

## <a name="set-up-inventory-aisles"></a>Configurar pasillos de inventario

Para configurar pasillos de inventario, siga estos pasos.

1. En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de canal \> Configuración de la ubicación \> Pasillos de inventario**.
1. En el panel de acciones, seleccione **Nueva**.
1. En la lista desplegable **Almacén**, seleccione el almacén creado previamente.
1. En el campo **Pasillo**, especifique un nombre (por ejemplo, "Predet").
1. En el campo **Nombre**, escriba un nombre (por ejemplo, "Pasillo predeterminado").
1. En el panel de acciones, seleccione **Guardar**.

## <a name="set-up-warehouse-inventory-locations"></a>Configurar ubicaciones de inventario de almacén

Para configurar ubicaciones de inventario de almacén para inventario estándar, dañado o devuelto, siga estos pasos.

1. En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de canal \> Almacenes**.
1. Seleccione el almacén que creó previamente.
1. En el panel de acciones, seleccione **Editar**.
1. En el panel de acciones, seleccione **Almacén** y, a continuación, seleccione **Ubicación del inventario**.
1. En el panel de acciones, seleccione **Nueva**. La opción predeterminada de la lista desplegable **Almacén** debe ser su nuevo almacén.
    1. En el cuadro **Pasillo**, introduzca el nombre del pasillo que especificó anteriormente. 
    1. Establezca **Actualización manual** en **Sí**.
    1. En el cuadro **Ubicación**, introduzca el nombre del almacén.
    1. En el panel de acciones, seleccione **Guardar**.
 1. En el panel de acciones, seleccione **Nueva**.  La opción predeterminada de la lista desplegable **Almacén** debe ser su nuevo almacén.
    1. En el cuadro **Pasillo**, introduzca el nombre del pasillo que especificó anteriormente.  
    1. Establezca **Actualización manual** en **Sí**.
    1. En el cuadro **Ubicación**, introduzca "Dañado".
    1. En el panel de acciones, seleccione **Guardar**.
 1. En el panel de acciones, seleccione **Nueva**.  La opción predeterminada de la lista desplegable **Almacén** debe ser su nuevo almacén.
    1. En el cuadro **Pasillo**, introduzca el nombre del pasillo que especificó anteriormente. 
    1. Establezca **Actualización manual** en **Sí**.
    1. En el cuadro **Ubicación**, introduzca "Devolución".
    1. En el panel de acciones, seleccione **Guardar**.
    
La siguiente imagen muestra una configuración de ubicación de inventario de almacén en San Francisco.

![Ejemplo de configuración de ubicación de inventario](media/warehouse-inventory-locations.png)
    
## <a name="complete-warehouse-setup"></a>Configuración de almacén completo

Para completar la configuración de almacén, siga estos pasos.

1. En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de canal \> Almacenes**.
1. Seleccione el almacén que creó previamente.
1. En el panel de acciones, seleccione **Editar**.
1. En **Módulo de gestión de inventario y almacenes**:
    1. Establezca **Ubicación predeterminada de la recepción** en la ubicación predeterminada que se creó previamente.
    1. Establezca **Ubicación predeterminada de emisión** en la ubicación predeterminada que se creó previamente.
1. En la sección **Direcciones**, introduzca una dirección de almacén.
1. En la sección **Venta minorista**: 
    1. En el cuadro **Ubicación de devolución predeterminada**, introduzca la ubicación de devoluciones que creó previamente.
    1. Establezca **Tienda** en **Sí**.
    1. Establezca **Peso** en **1,00**. 
    1. En el cuadro **Dimensiones de almacenamiento**, introduzca la ubicación predeterminada que creó previamente.
1. En la sección **Almacén**, establezca **Inventario físico negativo** en **Sí**.
1. En el panel de acciones, seleccione **Guardar**.

La siguiente imagen muestra los detalles de un almacén configurado.

![Ejemplo de almacén configurado](media/warehouse-sample.png)

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de la gestión de almacenes](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json)

[Resumen de canales](channels-overview.md)

[Requisitos previos de configuración de canales](channels-prerequisites.md)

[Configurar un canal comercial](channel-setup-retail.md)
    
[Configurar un canal en línea](channel-setup-online.md)

[Configurar un canal de centro de llamadas](channel-setup-callcenter.md)







[!INCLUDE[footer-include](../includes/footer-banner.md)]
