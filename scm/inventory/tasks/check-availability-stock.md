---
title: Comprobar la disponibilidad de existencias
description: "Este procedimiento le muestra cómo comprobar el inventario disponible y el inventario físico disponible para un número de artículo concreto."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: 62338fe11c30781f264e626fad835a2ba9dca837
ms.contentlocale: es-es
ms.lasthandoff: 09/12/2017

---
# Comprobar la disponibilidad de existencias

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento le muestra cómo comprobar el inventario disponible y el inventario físico disponible para un número de artículo concreto. También se muestra cómo obtener la información de suministro relacionada con un artículo. El inventario físico disponible es el inventario disponible que se tiene a mano, es decir, se ha comprado, recibido y registrado. El inventario disponible incluye el inventario disponible que se tiene a mano, pero también el inventario pedido y que se espera pero aún no se ha recibido o registrado. Puede revisar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos. Si está usando USMF, puede utilizar los valores del ejemplo mostrados. Estas tareas las realizará normalmente un trabajador del almacén.


## Comprobar el inventario disponible de un artículo
1. Vaya a Gestión de inventario > Consultas e informes > Inventario disponible.
2. Seleccione la fila Número de artículo.
    * Para consultar el inventario disponible por número de artículo, seleccione la fila donde Tabla está establecido en Inventario disponible y Campo está establecido en Número de artículo.  
3. En el campo Criterios, seleccione el artículo que desea consultar.
    * Si utiliza a la empresa de datos de prueba USMF, puede seleccionar "M9201".  
4. Haga clic en Aceptar
5. Haga clic en Dimensiones.
    * La ficha Dimensiones permite seleccionar cuánto detalle desea ver sobre su inventario disponible. Si necesita los datos relacionados con la reserva, debe mostrar todas las dimensiones de inventario para los artículos que usan los procesos avanzados de almacén (WHS).  
6. Haga clic en Aceptar
7. En el panel de acciones, haga clic en Información relacionada.
    * Si no ve esto, es posible que tenga que hacer clic en los puntos suspensivos (…) para ver opciones adicionales del panel de acciones.  
8. Haga clic en Visión general de suministros.
    * La ficha Visión general de suministros proporciona la información para un artículo específico, como la cantidad disponible, el plazo y la información del proveedor.  
9. Expanda la sección Disponible.
10. Expanda la sección Proveedores.
11. Cierre la página.
12. Cierre la página.

## Comprobar el inventario físico disponible
1. Vaya a Gestión de almacén > Consultas e informes > Inventario físico disponible.
2. En el campo Código de artículo, escriba un valor.
    * Puede utilizar los campos Sitio y Almacén para filtrar la lista de artículos.  
3. Actualice la página.
4. Haga clic en Mostrar dimensiones.
    * La ficha Mostrar dimensiones permite seleccionar cuánto detalle desea ver sobre su inventario disponible.  
5. Haga clic en Aceptar
6. Cierre la página.

## Comprobar el inventario disponible por ubicación
1. Vaya a Gestión de almacén > Consultas e informes > Inventario disponible por ubicación.
2. En el campo Almacén, escriba un valor.
    * Si utiliza a la empresa de datos de prueba USMF, puede usar “51".  
3. Actualice la página.
4. Haga clic en Mostrar dimensiones.
5. Haga clic en Aceptar
6. Cierre la página.

