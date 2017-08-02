---
title: "Espacio de trabajo móvil de gestión de gastos"
description: "Este tema proporciona información acerca del espacio de trabajo móvil de gestión de gastos que está disponible para la aplicación móvil Microsoft Dynamics 365 for Finance and Operations. Este espacio de trabajo permite a los usuarios capturar y cargar un recibo, de modo que puedan adjuntarlo a un informe de gastos posteriormente. El espacio de trabajo móvil también permite a los usuarios crear rápidamente una línea de gastos mediante un recibo vinculado."
author: annbe
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: end user, IT Pro
ms.reviewer: annbe
ms.search.scope: Operations
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: annbe
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 0e52d1c5dde7f79c4a8ac5ac2d9c3b25bba9c2cd
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017


---

# <a name="expense-management-mobile-workspace"></a>Espacio de trabajo móvil de gestión de gastos

[!include[banner](../includes/banner.md)]


Este tema proporciona información acerca del espacio de trabajo móvil de gestión de gastos que está disponible para la aplicación móvil Microsoft Dynamics 365 for Finance and Operations. Este espacio de trabajo permite a los usuarios capturar y cargar un recibo, de modo que puedan adjuntarlo a un informe de gastos posteriormente. El espacio de trabajo móvil también permite a los usuarios crear rápidamente una línea de gastos mediante un recibo vinculado.

<a name="overview-of-the-expense-management-mobile-workspace"></a>Visión general del espacio de trabajo móvil de gestión de gastos
---------------------------------------------------

Muchas organizaciones requieren que se adjunte al informe de gastos que presenta el empleado para el reembolso, una copia de los recibos relacionados con el viaje o la empresa. El espacio de trabajo móvil **Gestión de gastos** permite a los usuarios crear rápidamente nuevas líneas de gastos en el dispositivo móvil de su elección mediante una foto vinculada a un recibo. Como alternativa, los usuarios pueden capturar una foto del recibo y después adjuntarla más tarde al informe de gastos. Específicamente, el espacio de trabajo móvil **Gestión de gastos** habilita al usuario para:

-   Tomar una foto de un recibo, y cargarla en Microsoft Dynamics 365 for Finance and Operations. Un usuario puede entonces vincular esa foto a un informe de gastos posteriormente.
-   Cargar un archivo como un recibo capturado. Un usuario puede entonces vincular ese archivo a un informe de gastos posteriormente.
-   Crear una nueva línea de gastos mediante un recibo vinculado. Un usuario puede entonces agregar el artículo de línea a un informe de gastos más tarde, y enviarlo para su aprobación y reembolso.

Las secciones restantes de este tema explican cómo implementar y usar el espacio de trabajo móvil **Gestión de gastos**.

## <a name="prerequisites"></a>Requisitos previos
Para poder implementar el espacio de trabajo móvil **Gestión de gastos** , asegúrese de que el administrador del sistema haya completado los requisitos previos siguientes.

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
<td>Microsoft Dynamics 365 for Operations versión 1611 con actualización de plataforma 3 o posterior debe estar implementado.</td>
<td>Administrador del sistema</td>
<td>Si todavía no tiene Finance and Operations implementado en su organización, el administrador del sistema debería ver <a href="/dynamics365/unified-operations/dev-itpro/deployment/deploy-demo-environment">Implementar un entorno de demostración de Microsoft Dynamics 365 for Finance and Operations</a>.</td>
</tr>
<tr class="even">
<td>KB 4019015 debe implementarse.</td>
<td>Administrador del sistema</td>
<td>KB 4019015 (una revisión de metadatos o actualización de X++) contiene cuatro áreas de trabajo móviles para la gestión de cadenas de suministro. Para implementar KB 4019015, el administrador del sistema debe seguir estos pasos:
<ol>
<li>Descargar KB 4019015 de Microsoft Dynamics Lifecycle Services (LCS).</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Instalar la revisión de metadatos</a>.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/deployment/create-apply-deployable-package">Crear un paquete desplegable</a> que contenga el modelo <strong>ApplicationSuite</strong> y <strong>ExpenseMobile</strong> y luego cargar el paquete desplegable en LCS.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/deployment/apply-deployable-package-system">Aplicar el paquete desplegable</a> a su sistema Finance and Operations.</li>
</ol></td>
</tr>
<tr class="odd">
<td>El espacio de trabajo móvil <strong>Gestión de gastos</strong> debe estar publicado en la aplicación móvil Finance and Operations.</td>
<td>Administrador del sistema</td>
<td><ol>
<li>Inicie Finance and Operations en su explorador.</li>
<li>En la página <strong>Parámetros del sistema</strong>, seleccione <strong>Gestionar espacios de trabajo móviles</strong>.</li>
<li>Seleccione el espacio de trabajo <strong>Gestión de gastos</strong>.</li>
<li>Haga clic en <strong>Publicar espacio de trabajo móvil</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-finance-and-operations-mobile-app"></a>Descargue e instale la aplicación móvil Finance and Operations.
Descargue e instale la aplicación móvil Finance and Operations desde la tienda de aplicaciones móviles.

-   Para Android: [Finance and Operations en Google Play Store](https://play.google.com/store/apps/details?id=com.microsoft.dynamics365.operations.mobile)
-   Para iPhone: [Finance and Operations en la tienda de aplicaciones de iTunes](https://itunes.apple.com/us/app/dynamics-365-for-operations/id1180836730?mt=8)

## <a name="sign-in-to-the-finance-and-operations-mobile-app"></a>Iniciar sesión en la aplicación móvil Finance and Operations
1.  Inicie la aplicación en su dispositivo móvil.
2.  Indique la dirección URL de Finance and Operations
3.  Escriba la empresa en la que va a iniciar sesión. Por ejemplo, escriba **USMF**.
4.  La primera vez que inicia sesión, se le pedirá el nombre de usuario y la contraseña de su cuenta de Finance and Operations. Escriba sus credenciales.
5.  Tras iniciar sesión, verá los espacios de trabajo disponibles para su empresa. Tenga en cuenta que si el administrador del sistema publica un nuevo espacio de trabajo más tarde, puede tocar la pantalla para actualizar la lista de espacios de trabajo móviles. 

[![Toque la pantalla para actualizar](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="capture-a-receipt-by-using-the-expense-management-mobile-workspace"></a>Obtener un recibo mediante el espacio de trabajo móvil de gestión de gastos
1.  En el dispositivo móvil, seleccione el espacio de trabajo **Gestión de gastos**.
2.  Seleccione **Capturar recibo**.
3.  Seleccione **Sacar una foto** o **Seleccionar imagen**.
4.  Si seleccionó **Sacar una foto**, siga estos pasos:
    1.  El sistema lo llevará a la cámara del dispositivo móvil, para que pueda realizar una foto del recibo. Cuando haya terminado de realizar una foto, haga clic en **Aceptar** para aceptar la foto.
    2.  Opcional: Especifique un nombre para la foto, y escriba una nota.

     **O bien:** si seleccionó **Seleccionar imagen**, siga estos pasos:
    1.  Seleccione una imagen en la lista.
    2.  Opcional: Especifique un nombre para la imagen y escriba una nota.

5.  Seleccione **Listo**.

## <a name="quick-expense-entry-by-using-the-expense-management-mobile-workspace"></a>Entrada rápida del gasto usando el espacio de trabajo móvil de gestión de gastos
1.  En el dispositivo móvil, seleccione el espacio de trabajo **Gestión de gastos**.
2.  Seleccione **Entrada rápida del gasto**.
3.  Seleccione la categoría del gasto. Verá una lista de las categorías de gastos que se cargan en su aplicación para su uso sin conexión. Hay hasta 50 artículos cargados de forma predeterminada, pero un desarrollador puede cambiar este número. Para obtener más información, los desarrolladores deben ver [Plataforma móvil de Finance and Operations](/dynamics365/unified-operations/dev-itpro/mobile-apps/mobile-platform). Si su categoría no está en la lista, seleccione **Buscar** para realizar una búsqueda en Finance and Operations. Busque por categoría de gastos, o cambie a buscar por tipo de gastos.
4.  Especifique la fecha de la transacción del gasto.
5.  Opcional: Especifique el comerciante del gasto.
6.  Especifique el importe del gasto.
7.  Seleccione la divisa del gasto. Verá una lista de los códigos de divisa que se cargan en su aplicación para su uso sin conexión. Hay hasta 400 divisas cargadas de forma predeterminada, pero un desarrollador puede cambiar este número. Para obtener más información, los desarrolladores deben ver [Plataforma móvil de Finance and Operations](/dynamics365/unified-operations/dev-itpro/mobile-apps/mobile-platform). Si su divisa no está en la lista, seleccione **Buscar** para realizar una búsqueda en Finance and Operations. Busque por divisa, o cambie a buscar por nombre.
8.  Seleccione **Sacar una foto** o **Seleccionar imagen**.
9.  Si seleccionó **Sacar foto**, el sistema lo llevará a la cámara del dispositivo móvil para que pueda realizar una foto del recibo. Cuando haya terminado de realizar una foto, haga clic en **Aceptar** para aceptar la foto.  o si seleccionó **Seleccionar imagen**, seleccione una imagen de la lista.
10. Seleccione **Listo**.






