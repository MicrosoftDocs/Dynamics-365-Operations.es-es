--- 
title: "Configuración de transportistas de envío"
description: "Este procedimiento muestra cómo configurar un transportista y definir detalles como el servicio, el modo de envío, la forma de pago de transporte, las restricciones de transporte y las tarifas de envío."
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e27be049bebd63c9266029b8981874417a9f0a8c
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-shipping-carriers"></a>Configuración de transportistas de envío

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo configurar un transportista y definir detalles como el servicio, el modo de envío, la forma de pago de transporte, las restricciones de transporte y las tarifas de envío. El coordinador de transporte puede asignar a continuación un transportista a una carga de entrada o de salida.


## <a name="create-a-new-shipping-carrier"></a>Creación de un nuevo transportista de envío
1. Vaya a Administración de transporte > Configuración > Transportistas > Transportistas de envío.
2. Haga clic en Nuevo.
3. En el campo Transportista de envío, escriba un valor.
4. En el campo Nombre, escriba un valor.
5. En el campo Modo, haga clic en el botón desplegable para abrir la búsqueda.
6. En la lista, busque y seleccione el registro deseado.
7. En la lista, haga clic en el vínculo de la fila seleccionada.

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a>Cumplimentación de la información general del transportista de envío
1. Expanda la sección Visión general.
2. Marque o quite la marca de la casilla Activar transportista de envío.
3. En el campo Proveedor, haga clic en el botón desplegable para abrir la búsqueda.
    * Seleccione la cuenta de proveedor a la que asignar el transportista.  
4. En la lista, busque y seleccione el registro deseado.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
6. En el campo Tipo de forma de pago de transporte, seleccione una opción.
    * Seleccione Manual para usar la página del formulario Forma de pago del transporte, o seleccione EDI para actualizar la forma de pago mediante EDI (Electronic Data Interchange).  
7. Marque o quite la marca de la casilla Activar calificación de transportistas.

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a>Creación de los servicios necesarios para el transportista de envío
1. Expanda la sección Servicios.
2. Haga clic en Nuevo.
3. En la lista, marque la fila seleccionada.
4. En el campo Servicio de transportista, escriba un valor.
5. En el campo Nombre, escriba un valor.
6. En el campo Método de transporte, haga clic en el botón desplegable para abrir la búsqueda.
7. En la lista, busque y seleccione el registro deseado.
8. En la lista, haga clic en el vínculo de la fila seleccionada.

## <a name="set-up-the-address-for-the-carrier-optional"></a>Configuración de la dirección del transportista (opcional)
1. Alterne la expansión de la sección Direcciones.
2. Haga clic en Nuevo.
3. En el campo Nombre o descripción, escriba un valor.
4. En el campo País o región, haga clic en el botón desplegable para abrir la búsqueda.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
6. En el campo Código postal, haga clic en el botón desplegable para abrir la búsqueda.
7. En la lista, busque y seleccione el registro deseado.
8. En la lista, haga clic en el vínculo de la fila seleccionada.
9. En el campo Calle, escriba un valor.
10. Haga clic en Aceptar

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a>Configuración del perfil de clasificación del transportista de envío
1. Expanda la sección Perfiles de clasificación.
2. Haga clic en Nuevo.
3. En la lista, marque la fila seleccionada.
4. En el campo Perfil de clasificación, escriba un valor.
5. En el campo Nombre, escriba un valor.
6. En el campo Sitio, haga clic en el botón desplegable para abrir la búsqueda.
7. En la lista, busque y seleccione el registro deseado.
8. En la lista, haga clic en el vínculo de la fila seleccionada.
9. En el campo Almacén, haga clic en el botón desplegable para abrir la búsqueda.
10. En la lista, busque y seleccione el registro deseado.
11. En la lista, haga clic en el vínculo de la fila seleccionada.
12. En el campo Motor de tasas, haga clic en el botón desplegable para abrir la búsqueda.
    * Seleccione el motor de tasas según el contrato que tenga con el transportista.  
13. En la lista, busque y seleccione el registro deseado.
14. En la lista, haga clic en el vínculo de la fila seleccionada.
15. En el campo Tasa maestra, haga clic en el botón desplegable para abrir la búsqueda.
16. En la lista, busque y seleccione el registro deseado.
17. En la lista, haga clic en el vínculo de la fila seleccionada.
18. En el campo Motor de tiempo de tránsito, haga clic en el botón desplegable para abrir la búsqueda.
19. En la lista, haga clic en el vínculo de la fila seleccionada.
20. Haga clic en Guardar.


