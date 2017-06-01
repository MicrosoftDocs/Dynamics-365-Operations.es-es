---
title: "Espacio de trabajo móvil de control de costes"
description: "Este tema proporciona información acerca del espacio de trabajo móvil de control de costes, que está disponible para la aplicación móvil Microsoft Dynamics 365 for Operations. Este espacio de trabajo permite a los administradores de un centro de coste ver información acerca del rendimiento del centro de coste en cualquier momento y cualquier lugar."
author: YuyuScheller
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 267114
ms.assetid: 612f2988-b2b9-420d-9825-40b99dc0e204
ms.search.region: global
ms.author: yuyus
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 09383c24b0dd2ad61a836f6c8dc97f4389915772
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="cost-controlling-mobile-workspace"></a>Espacio de trabajo móvil de control de costes

[!include[banner](../includes/banner.md)]


Este tema proporciona información acerca del espacio de trabajo móvil de control de costes, que está disponible para la aplicación móvil Microsoft Dynamics 365 for Operations. Este espacio de trabajo permite a los administradores de un centro de coste ver información acerca del rendimiento del centro de coste en cualquier momento y cualquier lugar. 

<a name="overview-of-the-cost-controlling-mobile-workspace"></a>Visión general del espacio de trabajo móvil de control de costes
-------------------------------------------------

El espacio de trabajo móvil **Control de costes** proporciona una vista inmediata del rendimiento actual de los centros de costes al comparar los costes reales con los costes presupuestados. Puede explorar en profundidad los estados de los elementos de coste individuales. 

Por ejemplo, un empleado recibe una invitación para una conferencia internacional, pero la organización debe cubrir todos los gastos de viajes. El empleado pregunta a su director si puede asistir a la conferencia. El director abre rápidamente el espacio de trabajo móvil de **control de costes** en su teléfono móvil para ver si dispone de presupuesto para que el empleado asista a la conferencia.

### <a name="data-security"></a>Seguridad de los datos

Los datos del espacio de trabajo móvil **Control de costes** están protegidos mediante credenciales de usuario. Los directores de los centros de coste pueden ver solo los datos de su propio centro de coste. La seguridad de nivel de acceso se administra en el módulo **Contabilidad de costes**. 

Los contables de coste definen la configuración del espacio de trabajo móvil **Control de costes** en el módulo **Contabilidad de costes**. Una vez que se haya publicado el espacio de trabajo en la aplicación móvil Microsoft Dynamics 365 for Operations, el espacio está disponible en la aplicación. Por lo tanto, todos los administradores de centro de coste de la organización pueden ver los datos en el mismo formato.

### <a name="actions-views-and-links"></a>Acciones, vistas y vínculos

El espacio de trabajo móvil **Control de costes** para la aplicación Microsoft Dynamics 365 for Operations proporciona las siguientes acciones, vistas y vínculos:

-   **Acciones:**
    -   Use **Seleccionar configuración** para seleccionar un diseño.
    -   Use **Seleccionar objeto de coste** para seleccionar los centros de coste donde se filtrarán los datos. **Nota:** Los centros de coste que aparecen en la lista depende del acceso que se otorga en el módulo **Contabilidad de costes** .
-   **Vistas:** Según las acciones que se seleccionen y lo que se configure en el módulo **Contabilidad de costes**, puede visualizar la siguiente información en las tarjetas.
    -   Valor real frente a presupuesto (período actual)
    -   Valor real frente a presupuesto revisado (período actual)
    -   Valor real frente a presupuesto (período anterior)
    -   Valor real frente a presupuesto revisado (período anterior)
    -   Valor real frente a presupuesto (año hasta la fecha)
    -   Valor real frente a presupuesto revisado (año hasta la fecha)

    Los importes siguientes se muestran en cada tarjeta: real, presupuesto, desviación, y desviación en %.
-   **Vínculos:**
    -   Detalles para el período actual
    -   Detalles para el período anterior
    -   Detalles para año hasta la fecha

    Al seleccionar un vínculo, una tarjeta se muestra por cada artículo de coste. Los importes siguientes se muestran en todas las tarjetas: real, presupuesto, desviación de presupuesto, % de desviación de presupuesto, presupuesto revisado, desviación de presupuesto revisado y % de desviación de presupuesto revisado. 
    
    [![Tarjeta para un elemento de coste ](./media/cost-controlling.png)](./media/cost-controlling.png)

## <a name="prerequisites"></a>Requisitos previos
Para poder usar el espacio de trabajo móvil **Control de costes** , asegúrese de que el administrador del sistema tenga los requisitos previos siguientes en vigor.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Requisito previo</th>
<th>Función</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Dynamics 365 for Operations versión 1611 con actualización de plataforma 3 o posterior debe estar implementado.</td>
<td>Administrador del sistema</td>
<td>Si todavía no tiene Dynamics 365 for Operations implementado en su organización, el administrador del sistema debería ver <a href="/dynamics365/operations/dev-itpro/deployment/deploy-demo-environment">Implementar un entorno de demostración de Microsoft Dynamics 365 for Operations</a>.</td>
</tr>
<tr class="even">
<td>KB 4013633 debe implementarse.</td>
<td>Administrador del sistema</td>
<td>KB 4013633 (una revisión de metadatos o actualización de X++) contiene cuatro áreas de trabajo móviles para la gestión de cadenas de suministro. Para implementar KB 4013633, el administrador del sistema debe seguir estos pasos:
<ol>
<li>Descargar KB 4013633 de Microsoft Dynamics Lifecycle Services (LCS).</li>
<li><a href="/dynamics365/operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Instalar la revisión de metadatos</a>.</li>
<li><a href="/dynamics365/operations/dev-itpro/deployment/create-apply-deployable-package">Crear un paquete desplegable</a> que contenga el modelo <strong>SCMMobile</strong> y luego cargar el paquete desplegable en LCS.</li>
<li><a href="/dynamics365/operations/dev-itpro/deployment/apply-deployable-package-system">Aplicar el paquete desplegable</a> a su sistema Dynamics 365 for Operations.</li>
</ol></td>
</tr>
<tr class="odd">
<td>El espacio de trabajo móvil <strong>Control de costes</strong> debe estar publicado en la aplicación móvil Dynamics 365 for Operations.</td>
<td>Administrador del sistema</td>
<td><ol>
<li>Inicie Dynamics 365 for Operations en su explorador.</li>
<li>En la página <strong>Parámetros del sistema</strong>, seleccione <strong>Gestionar espacios de trabajo móviles</strong>.</li>
<li>Seleccione el espacio de trabajo <strong>Visión general del objeto de coste</strong>.</li>
<li>Haga clic en <strong>Publicar espacio de trabajo móvil</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-dynamics-365-for-operations-mobile-app"></a>Descargue e instale la aplicación móvil Dynamics 365 for Operations
Descargue e instale la aplicación móvil Microsoft Dynamics 365 for Operations desde la tienda de aplicaciones móviles.

-   Para Android: [Dynamics 365 for Operations en Google Play Store](https://play.google.com/store/apps/details?id=com.microsoft.dynamics365.operations.mobile)
-   Para iPhone: [Dynamics 365 for Operations en la tienda de aplicaciones de iTunes](https://itunes.apple.com/us/app/dynamics-365-for-operations/id1180836730?mt=8)

## <a name="sign-in-to-the-dynamics-365-for-operations-mobile-app"></a>Inicie sesión en la aplicación móvil Dynamics 365 for Operations
1.  Inicie la aplicación en su dispositivo móvil.
2.  Entre en la URL de Dynamics 365 for Operations.
3.  Escriba la empresa en la que va a iniciar sesión. Por ejemplo, escriba **USMF**.
4.  La primera vez que inicia sesión, se le pedirá el nombre de usuario y la contraseña de su cuenta Dynamics 365 for Operations. Escriba sus credenciales.
5.  Tras iniciar sesión, verá los espacios de trabajo disponibles para su empresa. Tenga en cuenta que si el administrador del sistema más adelante publica un nuevo espacio de trabajo, puede tocar la pantalla para actualizar la lista de espacios de trabajo móviles. 

    [![Toque la pantalla para actualizar](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-the-performance-of-your-cost-center-by-using-the-cost-controlling-mobile-workspace"></a>Visualizar el rendimiento del centro de coste según el espacio de trabajo móvil de control de costes
1.  En el dispositivo móvil, seleccione el espacio de trabajo **Control de costes**.
2.  Seleccione **Control de objeto de coste**.
3.  Seleccione **Acciones**.
4.  Seleccione **Seleccionar configuración** para seleccionar un diseño de control de costes.
5.  Seleccione **Listo**.
6.  Seleccione **Acciones**.
7.  Seleccione **Seleccionar objeto de coste** para seleccionar los centros de costes a los que se le ha concedido acceso.
8.  Seleccione **Listo**.
9.  Visualice el rendimiento general de su centro de coste.
10. Seleccione el vínculo **Detalles para el período actual** .
11. Visualice el rendimiento de los elementos de coste individuales.
12. También puede buscar elementos de coste específicos.





