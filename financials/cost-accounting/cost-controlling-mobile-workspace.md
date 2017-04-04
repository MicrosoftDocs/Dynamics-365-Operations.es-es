---
title: "Coste controlar el área de trabajo móvil para Microsoft Dynamics 365 para la aplicación de operaciones"
description: "Con el coste supervisión del área de trabajo móvil, administradores de centro de coste pueden ver el rendimiento de centro de coste en cualquier momento y cualquier lugar."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-01-12 16 - 53 - 04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267114
ms.assetid: 84740472-494f-444c-9b74-f83b7342fd25
ms.search.region: global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: 8136efb1d2669c39fcc0f80b60e80ecae983d5d8
ms.lasthandoff: 03/31/2017


---

# <a name="cost-controlling-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Coste controlar el área de trabajo móvil para Microsoft Dynamics 365 para la aplicación de operaciones

Con el coste supervisión del área de trabajo móvil, administradores de centro de coste pueden ver el rendimiento de centro de coste en cualquier momento y cualquier lugar. 

<a name="prerequisites"></a>Requisitos previos
-------------

| Requisito previo                                                         | Descripción                                                                                                                                                                   |
|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Lea sobre el Microsoft Dynamics 365 para la plataforma de móvil de las operaciones | [365 Dinámica para la plataforma] móvil de las operaciones (/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                                              |
| Dinámica 365 para las operaciones                                          | Asegúrese de que utiliza un entorno con Microsoft Dynamics 365 para la versión 1611 de las operaciones y Microsoft Dynamics para la plataforma de las operaciones actualiza 3 (noviembre de 2016). |
| Sustitución 3215650 KB                                                    | Instale el reemplazo para habilitar las áreas de trabajo que se proporcionan en Microsoft Dynamics 365 para las operaciones.                                                                       |
| Dispositivo móvil que tiene Dynamics 365 para la aplicación de las operaciones instalada | Descargue Dynamics 365 para la aplicación de las operaciones de la tienda móvil de la aplicación.                                                                                                      |

## <a name="introduction"></a>Introducción
El coste que controla el área de trabajo móvil proporciona una vista inmediata del rendimiento actual de centros de coste comparando los costes reales en comparación con los costes presupuestados. Puede explorar en profundidad los estados de elementos de coste individuales.

### <a name="example"></a>Ejemplo

Un empleado recibe una invitación para una Conferencia internacional. La organización que tendrá cubrir todos los gastos de viajes. El empleado solicita su la si podrá asistir a la conferencia. El administrador abre rápidamente el coste que controla el área de trabajo en su móvil teléfono móvil para consultar si esa tiene presupuesto del empleado assista a la conferencia.

### <a name="data-security"></a>Seguridad de los datos

Los datos del coste que controla el área de trabajo se garantiza mediante las credenciales del usuario. Se permite un administrador de centro de coste sólo ver los datos para su propio centro de coste. La seguridad de nivel de acceso se administra en el módulo de contabilidad de costes. Los contables de coste definen el coste que controlan la configuración móvil del área de trabajo en el módulo de contabilidad de costes. Una vez que el área de trabajo se publique en Microsoft Dynamics 365 para la aplicación de operaciones, está disponible en Dynamics 365 para de la aplicación móvil de las operaciones. Esto garantiza que todos los administradores de centro de coste en la organización miren datos en el mismo formato.

### <a name="actions-views-and-links"></a>Acciones, vistas, y vínculos

El coste que controla el área de trabajo móvil para Dynamics 365 para la aplicación de las operaciones ofrece las acciones, las visiones, y los vínculos siguientes:

-   Acciones  
    -   Seleccione ** ** configuraciones para seleccionar un diseño.
    -   Seleccione ** objetos de coste ** para seleccionar los centros de coste en los que desea filtrar datos. ** Nota: ** La lista se muestra como el acceso concedido al módulo de contabilidad de costes.

<!-- -->

-   Según qué la opción está seleccionada en ** las acciones ** y qué se configura en el módulo de contabilidad de costes, puede ver la siguiente información en las tarjetas. Tenga en cuenta que el importe se mostrará en el mismo formato: Real, presupuesto, desviación, y desviación %. 
    -   Real frente a presupuesto (el período actual)
    -   Real frente al presupuesto revisado (período actual)
    -   Real frente a presupuesto (el período anterior)
    -   Real frente al presupuesto revisado (período anterior)
    -   Real frente al presupuesto (Año hasta la fecha)
    -   Real frente al presupuesto revisado (Año hasta la fecha)

<!-- -->

-   Vínculos
    -   Detalles del período actual.
    -   Detalles del período anterior.
    -   Detalles por Año hasta la fecha.

Cuando selecciona uno de los vínculos, una tarjeta por artículo de coste se muestra. El importe en las tarjetas se muestra en el formato siguiente: Real, presupuesto, desviación de presupuesto, desviación de presupuesto, % revisó el presupuesto, la desviación de presupuesto revisada, y la desviación de presupuesto revisada %.  [![coste que controla] (. /media/cost-controlling.png])(. /media/cost-controlling.png)

## <a name="get-started"></a>Introducción
Siga estos pasos para iniciarse mediante la aplicación móvil de control de costes del dispositivo móvil.

1.  En su tienda móvil de la aplicación, y descarga el instalar Microsoft Dynamics 365 para la aplicación de las operaciones.
2.  Iniciar la aplicación del dispositivo.
3.  Especifique la dirección URL de Dynamics 365.
4.  Especifique la empresa para iniciar sesión en. Por ejemplo, escriba USMF ** **.
5.  La primera vez que se iniciar sesión, se le solicitará el nombre de usuario y la contraseña para su Microsoft Dynamics 365 para la cuenta de operaciones. Especifique sus. Tras en firme, verá las áreas de trabajo disponibles para su empresa.

Para ver Áreas de trabajo en su aplicación móvil, primero debe publicar las áreas de trabajo deseadas a Dynamics 365 para la aplicación de las operaciones.

1.  Dinámica 365 de inicio de las operaciones.
2.  Retroceda ** Administración del sistema ** &gt; ** la configuración ** &gt; ** los parámetros del sistema **.
3.  Seleccione ** gestionar la aplicación móvil **.
4.  Seleccione el área de trabajo ** el control de coste ** para publicar en esta plataforma móvil.
5.  Seleccione ** publique el área de trabajo **.
6.  Actualización del dispositivo para ver las áreas de trabajo publicadas.

## <a name="view-the-performance-of-your-cost-center"></a>Permite ver el rendimiento del centro de coste
1.  En el dispositivo móvil, seleccione ** el control de coste ** el área de trabajo.
2.  ** Seleccione el control de objeto de coste **.
3.  Haga clic en ** ** acciones.
4.  Haga clic en ** configuración seleccione ** para seleccionar un coste que controla el diseño.
5.  Click **Done**.
6.  Haga clic en ** ** acciones.
7.  Haga clic en ** objeto seleccione de coste ** para seleccionar los centros de coste a los que le han concedido el acceso.
8.  Click **Done**.
9.  Vea el rendimiento general de su centro de coste.
10. Haga clic en ** detalles del período actual **.
11. Permite ver el rendimiento de los artículos de costes individuales.
12. También puede buscar artículos de coste específicos.



