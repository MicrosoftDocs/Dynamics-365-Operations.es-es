---
title: Configuración de transportistas de envío
description: En este tema se muestra cómo configurar un transportista y definir detalles como el servicio, el modo de envío, la forma de pago de transporte, las restricciones de transporte y las tarifas de envío.
author: Henrikan
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSShippingCarrierCustomerAccount,TMSCarrier
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 38bf1f9f201e7f34e6a7ea76fbef399ba94caafa
ms.sourcegitcommit: 367e323bfcfe41976e5d8aa5f5e24a279909d8ac
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "8660390"
---
# <a name="set-up-shipping-carriers"></a>Configuración de transportistas de envío

[!include [banner](../../includes/banner.md)]

En este tema se muestra cómo configurar un transportista y definir detalles como el servicio, el modo de envío, la forma de pago de transporte, las restricciones de transporte y las tarifas de envío. El coordinador de transporte puede asignar a continuación un transportista a una carga de entrada o de salida.

## <a name="create-a-new-shipping-carrier"></a>Creación de un nuevo transportista de envío

1. Vaya a **Panel de navegación > Módulos > Administración de transporte > Configuración > Transportistas > Transportistas de envío**.
2. En el panel Acciones, seleccione **Nuevo**.
3. En el campo **Transportista de envío**, escriba un valor.
4. En el campo **Nombre**, escriba un valor.
5. En el campo **Modo**, seleccione una opción en el menú desplegable.

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a>Cumplimentación de la información general del transportista de envío

1. Alterne la expansión de la sección **Visión general**.
2. Marque o quite la marca de la casilla **Activar transportista de envío**.
3. En el campo **Cuenta del proveedor**, seleccione una opción en el menú desplegable. Seleccione la cuenta de proveedor a la que asignar el transportista.  
4. En el campo **Tipo de forma de pago de transporte**, seleccione una opción. Seleccione **Manual** para usar la página Forma de pago del transporte, o seleccione **EDI** para actualizar la forma de pago mediante EDI (Electronic Data Interchange).  
5. Marque o quite la marca de la casilla **Activar calificación de transportistas**.

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a>Creación de los servicios necesarios para el transportista de envío

1. Alterne la expansión de la sección **Servicios**.
2. Seleccione **Nuevo**.
3. En el campo **Servicio de transportista**, escriba un valor.
4. En el campo **Nombre**, escriba un valor.
5. En el campo **Id. de plantilla de carga** seleccione una plantilla de carga para asociarla con el servicio. La plantilla de carga define las medidas máximas para el peso y el volumen de una carga completa. Por ejemplo, la plantilla de carga puede representar el tamaño de un contenedor o de un camión. Los ID de plantilla de carga también se especifican en las plantillas de creación de carga y cuando se utiliza el [banco de trabajo de creación de carga](load-building-workbench.md), que le ayuda a aplicar estrategias de creación de carga para crear cargas. Como resultado, el sistema podrá hacer coincidir cada carga nueva con un servicio de transportista adecuado comparando los ID de plantilla de carga especificados.
6. En el campo **Método de transporte**, seleccione una opción en el menú desplegable.

## <a name="set-up-the-address-for-the-carrier-optional"></a>Configuración de la dirección del transportista (opcional)

1. Alterne la expansión de la sección **Direcciones**.
2. Seleccione **Nuevo**.
3. En el campo **Nombre o descripción**, escriba un valor.
4. En el campo **País/región**, seleccione una opción en el menú desplegable.
5. En el campo **Código postal**, seleccione una opción en el menú desplegable.
6. En el campo **Calle**, escriba un valor.
7. Seleccione **Aceptar**.

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a>Configuración del perfil de clasificación del transportista de envío

1. Alterne la expansión de la sección **Perfiles de clasificación**.
2. Seleccione **Nuevo**.
3. En el campo **Perfil de clasificación**, escriba un valor.
4. En el campo **Nombre**, escriba un valor.
5. En el campo **Sitio**, seleccione una opción en el menú desplegable.
6. En el campo **Almacén**, seleccione una opción en el menú desplegable.
7. En el campo **Motor de tarifas**, seleccione una opción en el menú desplegable. Seleccione el motor de tasas según el contrato que tenga con el transportista.  
8. En el campo **Tasa maestra**, seleccione una opción en el menú desplegable.
9. En el campo **Motor de tiempo de tránsito**, seleccione una opción en el menú desplegable.
10. Seleccione **Guardar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]