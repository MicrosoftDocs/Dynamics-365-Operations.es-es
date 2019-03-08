---
title: Espacio de trabajo móvil de control de costes
description: Este tema proporciona información sobre del espacio de trabajo móvil de Control de costes. Este espacio de trabajo permite a los administradores de un centro de coste ver información acerca del rendimiento del centro de coste en cualquier momento y cualquier lugar.
author: AndersGirke
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 267114
ms.assetid: 612f2988-b2b9-420d-9825-40b99dc0e204
ms.search.region: global
ms.author: aevengir
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: b6cdb69f32de2118e685c149605d50b78105c098
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "317577"
---
# <a name="cost-controlling-mobile-workspace"></a>Espacio de trabajo móvil de control de costes

[!include [banner](../includes/banner.md)]

Este tema proporciona información sobre del espacio de trabajo móvil de **Control de costes**. Este espacio de trabajo permite a los administradores de un centro de coste ver información acerca del rendimiento del centro de coste en cualquier momento y cualquier lugar.

Este espacio de trabajo móvil se debe usar con la aplicación Microsoft Dynamics 365 for Unified Operations mobile.

## <a name="overview"></a>Información general
El espacio de trabajo móvil **Control de costes** proporciona una vista inmediata del rendimiento actual de los centros de costes al comparar los costes reales con los costes presupuestados. Puede explorar en profundidad el estado de los elementos de coste individuales.

Por ejemplo, un empleado recibe una invitación para una conferencia internacional, pero la organización debe cubrir todos los gastos de viajes. El empleado pregunta a su director si puede asistir a la conferencia. El director abre rápidamente el espacio de trabajo móvil de **control de costes** en su teléfono móvil para ver si dispone de presupuesto para que el empleado asista a la conferencia.

### <a name="data-security"></a>Seguridad de los datos
Los datos del espacio de trabajo móvil **Control de costes** están protegidos mediante credenciales de usuario. Los directores de los centros de coste pueden ver solo los datos de su propio centro de coste. La seguridad de nivel de acceso se administra en el módulo **Contabilidad de costes**.

Los contables de coste definen la configuración del espacio de trabajo móvil **Control de costes** en el módulo **Contabilidad de costes**. Una vez que se haya publicado el espacio de trabajo en la aplicación móvil, el espacio está disponible en la aplicación. Por lo tanto, todos los administradores de centro de coste de la organización pueden ver los datos en el mismo formato.

### <a name="actions-views-and-links"></a>Acciones, vistas y vínculos
El espacio de trabajo móvil **Control costes** proporciona las acciones, las vistas y los vínculos siguientes:

-   **Acciones:**

    -   Use **Seleccionar configuración** para seleccionar un diseño.
    -   Use **Seleccionar objeto de coste** para seleccionar los centros de coste donde se filtrarán los datos.
    
        > [!NOTE]
        > Los centros de coste que aparecen en la lista depende del acceso que se otorga en el módulo **Contabilidad de costes**.

-   **Vistas:** Según las acciones que se seleccionen y lo que se configure en el módulo **Contabilidad de costes**, puede visualizar la siguiente información en las tarjetas:

    -   Real frente a presupuesto (periodo actual)
    -   Real frente a presupuesto revisado (periodo actual)
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
    
    [![Tarjeta para un elemento de coste ](./media/Cost-controlling.png)](./media/Cost-controlling.png)

## <a name="prerequisites"></a>Requisitos previos
Los requisitos previos varían, en función de la versión de Microsoft Dynamics 365 que se ha implementado para su organización.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations"></a>Requisitos previos si usa Microsoft Dynamics 365 for Finance and Operations
Si Microsoft Dynamics 365 for Finance and Operations se ha implementado para su organización, el administrador del sistema debe publicar el espacio de trabajo móvil **Control de costes**. Para obtener instrucciones, consulte [Publicar un espacio de trabajo móvil](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Los requisitos previos si usa Microsoft Dynamics 365 for Operations versión 1611 con la actualización de plataforma 3 o posterior
Si se ha implementado Microsoft Dynamics 365 for Operations versión 1611 con actualización de plataforma 3 o posterior en su organización, el administrador del sistema debe cumplir los requisitos siguientes.

<table>
<thead>
<tr class="header">
<th>Requisito previo</th>
<th>Función</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Implementar 4013633 KB.</td>
<td>Administrador del sistema</td>

<td>KB 4013633 es una sustitución de actualización o de metadatos X++ que contiene el espacio de trabajo móvil <strong>Control de costes</strong>. Para implementar KB 4013633, el administrador del sistema debe seguir estos pasos.
<ol>
<li><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Descargar la revisión de metadatos de Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Instalar la revisión de metadatos</a>.</li>
<li><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Crear un paquete desplegable</a> que contenga el modelo <strong>SCMMobile</strong> y luego cargar el paquete desplegable en LCS.</li>
<li><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Aplicar el paquete implementable</a>.</li>

</ol></td>
</tr>
<tr class="even">
<td>Publique el espacio de trabajo móvil <strong>Control de costes</strong>.</td>
<td>Administrador del sistema</td>
<td>Consulte <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publicar un espacio de trabajo móvil</a>.</td>
</tr>
</tbody>
</table>


## <a name="download-and-install-the-mobile-app"></a>Descargar e instalar la aplicación móvil
Descargue e instale la aplicación móvil Dynamics 365 for Unified Operations:

-   [Para teléfonos Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Para iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Iniciar sesión en la aplicación móvil

1.  Inicie la aplicación en su dispositivo móvil.
2.  Escriba la URL de Dynamics 365.
3.  La primera vez que se inicie sesión, se le solicitará su nombre de usuario y contraseña. Escriba sus credenciales.
4.  Tras iniciar sesión, se mostrarán los espacios de trabajo disponibles para su empresa. Tenga en cuenta que si el administrador del sistema publica un nuevo espacio de trabajo más tarde, tendrá que actualizar la lista de espacios de trabajo móviles.

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

