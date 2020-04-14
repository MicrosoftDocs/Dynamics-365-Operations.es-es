---
title: Configuración de transportistas de envío
description: En este tema se muestra cómo configurar un transportista y definir detalles como el servicio, el modo de envío, la forma de pago de transporte, las restricciones de transporte y las tarifas de envío.
author: ShylaThompson
manager: AnnBe
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bb39d58336e7f867e19d7ba6d9f801200de5a0aa
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148564"
---
# <a name="set-up-shipping-carriers"></a>Configuración de transportistas de envío

[!include [banner](../../includes/banner.md)]

En este tema se muestra cómo configurar un transportista y definir detalles como el servicio, el modo de envío, la forma de pago de transporte, las restricciones de transporte y las tarifas de envío. El coordinador de transporte puede asignar a continuación un transportista a una carga de entrada o de salida.


## <a name="create-a-new-shipping-carrier"></a>Creación de un nuevo transportista de envío
1. Vaya a **Panel de navegación > Módulos > Administración de transporte > Configuración > Transportistas > Transportistas de envío**.
2. Seleccione **Nueva** en el panel de acciones.
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
5. En el campo **Método de transporte**, seleccione una opción en el menú desplegable.

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

