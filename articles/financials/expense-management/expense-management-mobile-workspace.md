---
title: "Espacio de trabajo móvil de gestión de gastos"
description: "Este tema proporciona información acerca del espacio de trabajo móvil de gestión de gastos. Este espacio de trabajo permite a los usuarios capturar y cargar un recibo, de modo que puedan adjuntarlo a un informe de gastos posteriormente. Los usuarios también pueden crear rápidamente una línea de gastos mediante un recibo vinculado, y crear y gestionar sus informes de gastos."
author: KimANelson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: knelson
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 6e64337f19600b18320550d91c134949c33af7b0
ms.openlocfilehash: bbbe37330e16a079b817dfe04f4a47f046263e88
ms.contentlocale: es-es
ms.lasthandoff: 12/01/2017

---

# <a name="expense-management-mobile-workspace"></a>Espacio de trabajo móvil de gestión de gastos

[!include[banner](../includes/banner.md)]

Este tema proporciona información acerca del espacio de trabajo móvil de **gestión de gastos**. Este espacio de trabajo permite a los usuarios capturar y cargar un recibo, de modo que puedan adjuntarlo a un informe de gastos posteriormente. Los usuarios también pueden crear rápidamente una línea de gastos mediante un recibo vinculado, y crear y gestionar sus informes de gastos. Además, los aprobadores pueden usar el espacio de trabajo móvil **Gestión de gastos** para ver los informes de gastos que se les asignan, y aprobar o rechazar los informes de gastos.


Este espacio de trabajo móvil se debe usar con la aplicación móvil Microsoft Dynamics 365 for Unified Operations.


## <a name="overview"></a>Información general

Muchas organizaciones requieren que se adjunte al informe de gastos que presenta el empleado para el reembolso, una copia de los recibos relacionados con el viaje o la empresa. El espacio de trabajo móvil **Gestión de gastos** permite a los usuarios crear rápidamente nuevas líneas de gastos en el dispositivo móvil de su elección mediante una foto vinculada a un recibo. Como alternativa, los usuarios pueden capturar una foto del recibo y después adjuntarla más tarde al informe de gastos. Los empleados también pueden crear y administrar sus informes de gastos, y después enviarlos para su aprobación y reembolso usando el dispositivo móvil.


En concreto, el espacio de trabajo móvil **Gestión de gastos** permite a los usuarios realizar las tareas siguientes:

- Tomar una foto de un recibo, y cargarla en Microsoft Dynamics 365 for Finance and Operations, Enterprise edition. Entonces puede vincular esa foto a un informe de gastos más tarde.
- Cargar un archivo como un recibo capturado. Entonces puede vincular ese archivo a un informe de gastos más tarde.
- Crear una nueva línea de gastos mediante un recibo vinculado. Puede agregar el artículo de línea a un informe de gastos más tarde, y enviarlo para su aprobación y reembolso.

Si utiliza Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, también puede utilizar las características siguientes:

- Crear un nuevo informe de gastos.
- Vincular transacciones de tarjeta de crédito y otros gastos anteriormente creados a un informe de gastos.
- Crear gastos nuevos para un informe de gastos.
- Vincular un recibo a cualquier gasto de un informe de gastos, tomando una foto del recibo o cargando un archivo como recibo capturado.
- En función de la directiva de gastos de la empresa, agregar la lista de invitados a un gasto.
- En función de la directiva de gastos de la empresa, detallar los gastos.
- Enviar el informe de gastos para su aprobación y reembolso.
- Aprobar o rechazar informes de gastos para los que es un aprobador asignado.

## <a name="prerequisites"></a>Requisitos previos
Los requisitos previos varían en función de la versión de Microsoft Dynamics 365 que se haya implementado para su organización.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition"></a>Requisitos previos si usa Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 
Si Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition se ha implementado para su organización, el administrador del sistema debe publicar el espacio de trabajo móvil **Gestión de gastos**. Para obtener instrucciones, consulte [Publicar un espacio de trabajo móvil](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Requisitos previos si usa Microsoft Dynamics 365 for Operations versión 1611 con actualización de plataforma 3 o posterior
Si se ha implementado Microsoft Dynamics 365 for Operations versión 1611 con actualización de plataforma 3 o posterior para su organización, el administrador del sistema debe cumplir los requisitos previos siguientes. 

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
<td>Implementar 4019015 KB.</td>
<td>Administrador del sistema</td>
<td>KB 4019015 es una actualización o una revisión de metadatos X++ que contiene el espacio de trabajo móvil <strong>Gestión de gastos</strong>. Para implementar KB 4019015, el administrador del sistema debe seguir estos pasos.
<ol>
<li><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Descargar la revisión de metadatos en Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Instalar la revisión de metadatos</a>.</li>
<li><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Crear un paquete desplegable</a> que contenga los modelos <strong>ApplicationSuite</strong> y <strong>ExpenseMobile</strong> y luego cargar el paquete desplegable en LCS.</li>
<li><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Aplicar el paquete implementable</a>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Publique el espacio de trabajo móvil de <strong>gestión de gastos</strong>.</td>
<td>Administrador del sistema</td>
<td>Consulte <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publicar un espacio de trabajo móvil</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-dynamics-365-for-operations-mobile-app"></a>Descargue e instale la aplicación móvil Dynamics 365 for Operations
Descargue e instale la aplicación móvil Dynamics 365 for Unified Operations:

- [Para teléfonos Android](https://go.microsoft.com/fwlink/?linkid=850662)
- [Para iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Iniciar sesión en la aplicación móvil
1. Inicie la aplicación en su dispositivo móvil.
2. Escriba la URL de Dynamics 365.
4. La primera vez que se inicie sesión, se le solicitará su nombre de usuario y contraseña. Escriba sus credenciales.
5. Tras iniciar sesión, se mostrarán los espacios de trabajo disponibles para su empresa. Tenga en cuenta que si el administrador del sistema publica un nuevo espacio de trabajo más tarde, tendrá que actualizar la lista de espacios de trabajo móviles.


[![Toque la pantalla para actualizar](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="capture-a-receipt-by-using-the-expense-management-mobile-workspace"></a>Obtener un recibo mediante el espacio de trabajo móvil de gestión de gastos

1. En su dispositivo móvil, abra el espacio de trabajo **Gestión de gastos**.
2. Seleccione **Capturar recibo**.
3. Seleccione **Sacar una foto** o **Seleccionar imagen**.
4. Siga uno de estos pasos:

    - Si seleccionó **Sacar una foto**, siga estos pasos:

        1. El sistema lo llevará a la cámara del dispositivo móvil, para que pueda realizar una foto del recibo. Cuando haya terminado de realizar una foto, seleccione **Aceptar** para aceptar la foto.
        2. Opcional: Especifique un nombre para la foto, y escriba una nota.

    - Si seleccionó **Seleccionar imagen**, siga estos pasos:

        1. Seleccione una imagen en la lista.
        2. Opcional: Especifique un nombre para la imagen y escriba una nota.

5. Seleccione **Listo**.

## <a name="quickly-enter-expenses-by-using-the-expense-management-mobile-workspace"></a>Especifique rápidamente los gastos usando el espacio de trabajo móvil de gestión de gastos
1. En su dispositivo móvil, abra el espacio de trabajo **Gestión de gastos**.
2. Seleccione **Entrada rápida del gasto**.
3. Seleccione la categoría del gasto. Verá una lista de las categorías de gastos que se cargan en su aplicación para su uso sin conexión. Hay 50 artículos cargados de forma predeterminada, pero un desarrollador puede cambiar este número. Para obtener más información, los desarrolladores deben ver [Plataforma móvil](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Si la categoría no está en la lista, seleccione **Buscar** para realizar una búsqueda en línea. Busque por categoría de gastos, o cambie a buscar por tipo de gastos.
4. Especifique la fecha de la transacción del gasto.
5. Opcional: Especifique el comerciante del gasto.
6. Especifique el importe del gasto.
7. Seleccione la divisa del gasto. Verá una lista de los códigos de divisa que se cargan en su aplicación para su uso sin conexión. De forma predeterminada, hay 400 divisas cargadas, pero un desarrollador puede cambiar este número. Para obtener más información, los desarrolladores deben ver [Plataforma móvil](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Si la divisa no está en la lista, seleccione **Buscar** para realizar una búsqueda en línea. Busque por divisa, o cambie a buscar por nombre.
8. Seleccione **Sacar una foto** o **Seleccionar imagen**.
9. Siga uno de estos pasos:

    - Si seleccionó **Sacar foto**, el sistema lo llevará a la cámara del dispositivo móvil para que pueda realizar una foto del recibo. Cuando haya terminado de realizar una foto, seleccione **Aceptar** para aceptar la foto.
    - Si seleccionó **Seleccionar imagen**, seleccione una imagen de la lista.

10. Seleccione **Listo**.

## <a name="approve-an-expense-report-by-using-the-expense-management-mobile-workspace-if-you-use-the-july-2017-update"></a>Apruebe un informe de gastos mediante el espacio de trabajo móvil de gestión de gastos (si utiliza la actualización de julio de 2017)
1. En su dispositivo móvil, abra el espacio de trabajo **Gestión de gastos**.
2. **Aprobaciones de gastos** muestra el número de informes de gastos que se le han asignado para su aprobación. El número se actualiza aproximadamente cada 30 minutos. Seleccione **Aprobaciones de gastos**.

    Se muestra la lista de informes de gastos que se le han asignado para su aprobación.
    
3. Seleccione un informe de gastos para ver sus detalles de gastos.
4. Seleccione un gasto para ver sus detalles. La información que se muestra para un gasto incluye cualquier recibo, invitado y detalle.
5. De nuevo en la página **Informe de gastos** , seleccione aprobar o rechazar el informe de gastos.
6. Escriba un comentario para la acción de aprobación.
7. Seleccione **Listo**.

## <a name="create-a-new-expense-report-and-submit-it-for-approval-by-using-the-expense-management-mobile-workspace-if-you-use-the-july-2017-update"></a>Cree un informe de gastos nuevo y envíelo para su aprobación usando el espacio de trabajo móvil de gestión de gastos (si utiliza la actualización de julio de 2017)
1. En su dispositivo móvil, abra el espacio de trabajo **Gestión de gastos**.
2. Seleccione **Entrada de gasto**.
3. Seleccione **Nuevo informe**, o seleccione un informe de gastos existente en la lista.
4. Para los nuevos informes de gastos, especifique el propósito y la información adicional que esté disponible. Esta información varía, en función de la manera en que está configurada la gestión de gastos para su empresa.
5. Seleccione **Listo**.
6. Para agregar gastos existentes, como transacciones de tarjeta de crédito, al informe de gastos, seleccione **Vincular**.
7. Seleccione uno o varios gastos en la lista.
8. Seleccione **Listo**.
9. Para agregar un nuevo gasto al informe de gastos, seleccione **Gasto nuevo**.
10. Seleccione la categoría del gasto. Verá una lista de las categorías de gastos que se cargan en su aplicación para su uso sin conexión. Hay 50 artículos cargados de forma predeterminada, pero un desarrollador puede cambiar este número. Para obtener más información, los desarrolladores deben ver [Plataforma móvil](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Si la categoría no está en la lista, seleccione **Buscar** para realizar una búsqueda en línea. Busque por categoría de gastos, o cambie a buscar por tipo de gastos.
11. Opcional: Especifique el comerciante del gasto.
12. Especifique la fecha de la transacción del gasto.
13. Especifique el importe del gasto.
14. Seleccione la divisa del gasto. Verá una lista de los códigos de divisa que se cargan en su aplicación para su uso sin conexión. De forma predeterminada, hay 400 divisas cargadas, pero un desarrollador puede cambiar este número. Para obtener más información, los desarrolladores deben ver [Plataforma móvil](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Si la divisa no está en la lista, seleccione **Buscar** para realizar una búsqueda en línea. Busque por divisa, o cambie a buscar por nombre.
15. Seleccione **Listo**.
16. Para agregar más detalles al gasto, seleccione **Agregar más detalles**. Los campos disponibles dependen de la configuración de la gestión de gastos para su empresa.
17. Si la política de empresa requiere un recibo para el gasto, seleccione **Recibos** y siga estos pasos:

    1. Seleccione **Capturar recibo** o **Adjuntar recibo**.
    2. Siga uno de estos pasos:

        - Si seleccionó **Capturar recibo**, siga estos pasos:

            1. Seleccione **Sacar una foto** o **Seleccionar imagen**.
            2. Siga uno de estos pasos:

                - Si seleccionó **Sacar una foto**, siga estos pasos:

                    1. El sistema lo llevará a la cámara del dispositivo móvil, para que pueda realizar una foto del recibo. Cuando haya terminado de realizar una foto, seleccione **Aceptar** para aceptar la foto.
                    2. Opcional: Especifique un nombre para la foto, y escriba una nota.

                - Si seleccionó **Seleccionar imagen**, siga estos pasos:

                    1. Seleccione una imagen en la lista.
                    2. Opcional: Especifique un nombre para la imagen y escriba una nota.

            3.  Seleccione **Listo**.

        - Si seleccionó **Adjuntar recibo**, siga estos pasos:

            1.  Seleccione una o varias imágenes en la lista.
            2.  Seleccione **Listo**.

    3. Seleccione el botón **Atrás** para volver a los detalles del gasto.

18. Si la política de empresa requiere invitados para el gasto, seleccione **Invitados** y siga estos pasos:

    1. Seleccione **Invitado**, **Invitados anteriores**, o **Compañeros**.
    2. Siga uno de estos pasos:

        - Si seleccionó **Invitado**, siga estos pasos:

            1. Introduzca el nombre del invitado.
            2. Opcional: Especifique la organización o el país del invitado.
            3. Opcional: Indique el cargo del invitado.
            4. Seleccione **Listo**.

        - Si seleccionó **Invitados anteriores**, siga estos pasos:

            1. Seleccione uno o varios invitados anteriores en la lista. Ve una lista de invitados anteriores que ha agregado a los informes de gastos anteriores que se cargan en su aplicación para usarlos sin conexión. Hay 50 artículos cargados de forma predeterminada, pero un desarrollador puede cambiar este número. Para obtener más información, los desarrolladores deben ver [Plataforma móvil](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Si su invitado anterior no está en la lista, seleccione **Buscar** para realizar una búsqueda en línea. Busque por su nombre, o cambie a la búsqueda por organización, país o cargo.
            2. Seleccione **Listo**.

        - Si seleccionó **Compañeros**, siga estos pasos:

            1. Seleccione uno o varios compañeros en la lista. Verá una lista de los compañeros que están cargados en su aplicación para su uso sin conexión. Hay 50 artículos cargados de forma predeterminada, pero un desarrollador puede cambiar este número. Para obtener más información, los desarrolladores deben ver [Plataforma móvil](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Si su compañero no está en la lista, seleccione **Buscar** para realizar una búsqueda en línea. Busque por su nombre, o cambie a la búsqueda por empresa o cargo.
            2. Seleccione **Listo**.

    3. Seleccione el botón **Atrás** para volver a los detalles del gasto.

19. Si la política de empresa requiere que el gasto se detalle, seleccione **Detallar** y siga estos pasos:

    1. Seleccione la primera fecha que quiera detallar.
    2. Seleccione **Agregar detalle**.
    3. Seleccione la subcategoría de detalle de gasto. Verá una lista de las subcategorías de gastos que se cargan en su aplicación para su uso sin conexión. Hay 50 artículos cargados de forma predeterminada, pero un desarrollador puede cambiar este número. Para obtener más información, los desarrolladores deben ver [Plataforma móvil](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Si su subcategoría no está en la lista, seleccione **Buscar** para realizar una búsqueda en línea. Busque por nombre de subcategoría de gastos.
    4. Escriba el importe de la transacción para el detalle.
    5. Edite la fecha de transacción si se requiere.
    6. Seleccione **Listo**.
    7. Repita los pasos anteriores hasta que haya terminado de agregar todos los detalles de la fecha seleccionada.
    8. Para días adicionales, puede seleccionar **Copiar al siguiente día** para copiar los detalles en el día siguiente. De manera alternativa, puede seleccionar la fecha para detallar y agregar detalles tal y como lo hizo para la primera fecha.
    9. Una vez que haya terminado de detallar el gasto, seleccione el botón **Atrás** para volver a los detalles del gasto.

20. Seleccione el botón **Atrás** para volver a la página **Informe de gastos**.
21. Repita los pasos anteriores hasta que haya terminado de agregar todos los gastos.
22. Seleccione **Enviar**.
23. Escriba un comentario para el aprobador.
24. Seleccione **Listo**.

