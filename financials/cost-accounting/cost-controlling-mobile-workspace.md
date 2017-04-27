---
title: "Espacio de trabajo móvil de control de costes para la aplicación Microsoft Dynamics 365 for Operations"
description: "Con el espacio de trabajo móvil de control de costes, los administradores de centro de coste pueden ver el rendimiento de centro de coste en cualquier momento y en cualquier lugar."
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

# <a name="cost-controlling-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Espacio de trabajo móvil de control de costes para la aplicación Microsoft Dynamics 365 for Operations

Con el espacio de trabajo móvil de control de costes, los administradores de centro de coste pueden ver el rendimiento de centro de coste en cualquier momento y en cualquier lugar. 

<a name="prerequisites"></a>Requisitos previos
-------------

| Requisito previo                                                         | Descripción                                                                                                                                                                   |
|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Obtenga información sobre la plataforma móvil de Microsoft Dynamics 365 for Operations | [Plataforma móvil de Microsoft Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                                              |
| Dynamics 365 for Operations                                          | Compruebe que utiliza un entorno que tiene la versión 1611 de Microsoft Dynamics 365 for Operations y la actualización 3 de la plataforma de Microsoft Dynamics for Operations (noviembre de 2016). |
| Revisión 3215650 KB                                                    | Instale la revisión para habilitar los espacios de trabajo provistos en Microsoft Dynamics 365 for Operations.                                                                       |
| Dispositivo móvil que tiene instalada la aplicación Dynamics 365 for Operations | Descargue la aplicación Dynamics 365 for Operations desde su tienda de aplicaciones móviles.                                                                                                      |

## <a name="introduction"></a>Introducción
El espacio de trabajo móvil de control de costes proporciona una vista inmediata del rendimiento actual de los centros de costes al comparar los costes reales con los costes presupuestados. Puede explorar en profundidad los estados de los elementos de coste individuales.

### <a name="example"></a>Ejemplo

Un empleado recibe una invitación a una conferencia internacional. La organización tendrá cubrir todos los gastos del viaje. El empleado pregunta a su director si puede asistir a la conferencia. El director abre rápidamente el espacio de trabajo móvil de control de costes en su teléfono móvil para ver si dispone de presupuesto para que el empleado asista a la conferencia.

### <a name="data-security"></a>Seguridad de los datos

Los datos del espacio de trabajo de control de costes están protegidos mediante credenciales de usuario. Solo se permite a un administrador de centro de coste que vea los datos de su propio centro de coste. La seguridad de nivel de acceso se administra en el módulo Contabilidad de costes. Los contables de coste definen la configuración del espacio de trabajo móvil de control de costes en el módulo Contabilidad de costes. Una vez que se publica el espacio de trabajo en la aplicación Microsoft Dynamics 365 for Operations, este está disponible en la aplicación móvil Dynamics 365 for Operations. Esto garantiza que todos los administradores de centro de coste en la organización consultan los datos en el mismo formato.

### <a name="actions-views-and-links"></a>Acciones, vistas y vínculos

El espacio de trabajo móvil de control de costes para la aplicación Microsoft Dynamics 365 for Operations proporciona las siguientes acciones, vistas y vínculos:

-   Acciones  
    -   Seleccione **Configuraciones** para seleccionar un diseño.
    -   Seleccione **Objetos de coste** para seleccionar los centros de coste en los que desea filtrar datos. **Nota:** La lista se muestra según el acceso concedido en el módulo Contabilidad de costes.

<!-- -->

-   Según la opción que se seleccione en **Acciones** y lo que se configure en el módulo Contabilidad de costes, puede visualizar la siguiente información en las tarjetas. Tenga en cuenta que el importe se muestra en el mismo formato: real, presupuesto, desviación y % de desviación. 
    -   Valor real frente a presupuesto (período actual)
    -   Valor real frente a presupuesto revisado (período actual)
    -   Valor real frente a presupuesto (período anterior)
    -   Valor real frente a presupuesto revisado (período anterior)
    -   Valor real frente a presupuesto (año hasta la fecha)
    -   Valor real frente a presupuesto revisado (año hasta la fecha)

<!-- -->

-   Vínculos
    -   Detalles para el período actual.
    -   Detalles para el período anterior.
    -   Detalles para año hasta la fecha.

Cuando selecciona uno de los vínculos, aparece una tarjeta por elemento de coste. El importe en las tarjetas se muestra en el siguiente formato: real, presupuesto, desviación de presupuesto, % de desviación de presupuesto, presupuesto revisado, desviación de presupuesto revisado y % de desviación de presupuesto revisado.  [![cost-controlling](./media/cost-controlling.png)](./media/cost-controlling.png)

## <a name="get-started"></a>Introducción
Siga estos pasos para comenzar a usar la aplicación móvil de control de costes en su dispositivo móvil.

1.  En su tienda de aplicaciones móviles, descargue e instale la aplicación Microsoft Dynamics 365 for Operations.
2.  Inicie la aplicación en su dispositivo.
3.  Escriba la URL de Dynamics 365.
4.  Escriba la empresa en la que va a iniciar sesión. Por ejemplo, escriba **USMF**.
5.  La primera vez que inicia sesión, se le pediré el nombre de usuario y la contraseña de su cuenta Microsoft Dynamics 365 for Operations. Escriba sus credenciales. Tras iniciar sesión, verá los espacios de trabajo disponibles para su empresa.

Para ver los espacios de trabajo en su aplicación móvil, primero debe publicar los espacios de trabajo deseados para la aplicación Dynamics 365 for Operations.

1.  Inicie Dynamics 365 for Operations.
2.  Vaya a **Administración del sistema** &gt; **Configurar** &gt; **parámetros del sistema**.
3.  Seleccionar **Administrar aplicación móvil**.
4.  Seleccione el espacio de trabajo **Control de costes** que desea publicar en la plataforma móvil.
5.  Seleccione **Publicar área de trabajo**.
6.  Actualice su dispositivo para ver los espacios de trabajo publicados.

## <a name="view-the-performance-of-your-cost-center"></a>Visualice el rendimiento de su centro de coste.
1.  En el dispositivo móvil, seleccione el espacio de trabajo **Control de costes**.
2.  Seleccione **Control de objeto de coste**.
3.  Haga clic en **Acciones**.
4.  Haga clic en **Seleccionar configuración** para seleccionar un diseño de control de costes.
5.  Haga clic en **Listo**.
6.  Haga clic en **Acciones**.
7.  Haga clic en **Seleccionar objeto de coste** para seleccionar los centros de costes a los que le han concedido acceso.
8.  Haga clic en **Listo**.
9.  Visualice el rendimiento general de su centro de coste.
10. Haga clic en **Detalles para el período actual**.
11. Visualice el rendimiento de los elementos de coste individuales.
12. También puede buscar elementos de coste específicos.



