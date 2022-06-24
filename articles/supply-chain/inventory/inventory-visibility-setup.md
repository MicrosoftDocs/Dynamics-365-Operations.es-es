---
title: Instalar el complemento de visibilidad de inventario
description: Este artículo describe cómo instalar el complemento de visibilidad de inventario para Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: ce81ed2ed79bfe5c7fff9724e14af150817af11f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895710"
---
# <a name="install-and-set-up-inventory-visibility"></a>Instalar y configurar Inventory Visibility

[!include [banner](../includes/banner.md)]

Este artículo describe cómo instalar el complemento de visibilidad de inventario para Microsoft Dynamics 365 Supply Chain Management.

Debe usar Microsoft Dynamics Lifecycle Services (LCS) para instalar el complemento de visibilidad de inventario. LCS es un portal de colaboración que proporciona un entorno y un conjunto de servicios actualizados periódicamente que le ayudan a gestionar el ciclo de vida de la aplicación de sus aplicaciones de Finance and Operations. Para obtener más información, consulte [Recursos de Lifecycle Services](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

> [!TIP]
> Le recomendamos que se una al grupo de usuarios del complemento Visibilidad de inventario, donde puede encontrar guías útiles, obtener nuestras últimas actualizaciones y publicar cualquier pregunta que pueda tener sobre el uso de Visibilidad de inventario. Para unirse, envíe un correo electrónico al equipo de productos de Visibilidad de inventario a [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) e incluya su identificador de entorno de Supply Chain Management.

## <a name="inventory-visibility-prerequisites"></a>Requisitos previos Visibilidad de inventario

Para poder instalar el complemento de visibilidad de inventario, debe completar las siguientes tareas:

- Obtenga un proyecto de implementación de LCS con al menos un entorno implementado.
- Asegúrese de que se hayan completado los requisitos previos para configurar complementos. Para obtener más información sobre estos requisitos previos, consulte [Información general sobre los complementos](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). La visibilidad de inventario no requiere vinculación de escritura dual.

> [!NOTE]
> Los países y regiones admitidos actualmente incluyen Canadá (CCA, ECA), Estados Unidos (WUS, EUS), la Unión Europea (NEU, WEU), Reino Unido (SUK, WUK) y Australia (EAU, SEAU), Japón (EJP, WJP) y Brasil (SBR, SCUS).

Si tiene alguna pregunta sobre estos requisitos previos, contacte con el equipo de productos de visibilidad de inventario en [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com).

## <a name="install-the-inventory-visibility-add-in"></a><a name="install-add-in"></a>Instalar el complemento de visibilidad de inventario

Antes de instalar el complemento, registre una solicitud y agregue un secreto de cliente a Azure Active Directory (Azure AD) en su suscripción de Azure. Para obtener instrucciones, consulte [Registrar una solicitud](/azure/active-directory/develop/quickstart-register-app) y [Agregar un secreto de cliente](/azure/active-directory/develop/quickstart-register-app#add-a-certificate). Asegúrese de anotar los valores de **Id. de la aplicación (cliente)**, **Secreto del cliente** e **Id. de inquilino**, porque los necesitará más adelante.

> [!IMPORTANT]
> Si tiene más de un entorno LCS, cree una aplicación de Azure AD diferente para cada uno de ellos. Si usa el mismo ID de aplicación y el mismo ID de inquilino para instalar el complemento de visibilidad de inventario para diferentes entornos, se producirá un problema de token para los entornos más antiguos. De este modo, solo será válida la último instalación.

Después de registrar una solicitud y agregar un secreto de cliente en Azure AD, siga estos pasos para instalar el complemento de visibilidad de inventario.

1. Inicie sesión en [LCS](https://lcs.dynamics.com/Logon/Index).
1. En la página de inicio, seleccione el proyecto donde se implementa su entorno.
1. En la página del proyecto, seleccione el entorno donde desea instalar el complemento.
1. En la página del entorno, desplácese hacia abajo hasta que encuentre la sección **Complementos de entorno** en la sección **Integración de Power Platform**. Allí, puede encontrar el  nombre del entorno de Dataverse. Confirme que el nombre del entorno de Dataverse es el que desea utilizar para la visibilidad del inventario.

    > [!NOTE]
    > Actualmente, solo se admiten entornos de Dataverse creados mediante LCS. Si su entorno de Dataverse se creó de otra forma (por ejemplo, usando el Centro de administración de Power Apps) y si está vinculado a su entorno de Supply Chain Management, primero debe comunicarse con el equipo de productos de Visibilidad de inventario en [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) para solucionar el problema de asignación. Luego podrá instalar Visibilidad de inventario.

1. En la sección **Complementos de entorno**, seleccione **Instalar un nuevo complemento**.

    ![Página de entorno en LCS](media/inventory-visibility-environment.png "Página de entorno en LCS")

1. Seleccione el vínculo **Instalar un nuevo complemento**. Se abre una lista de complementos disponibles.
1. En la lista, seleccione **Visibilidad de inventario**.
1. Establezca los siguientes campos para su entorno:

    - **Id. de la aplicación de AAD (cliente)** – Introduzca el Id. de la aplicación de Azure AD que creó y anotó anteriormente.
    - **Id. del inquilino de AAD** – Introduzca el Id. del inquilino que anotó anteriormente.

    ![Configurar la página de complemento](media/inventory-visibility-setup.png "Configurar la página de complemento")

1. Acepte los términos y condiciones seleccionando la casilla de verificación **Términos y condiciones**.
1. Seleccione **Instalar**. El estado del complemento se muestra como **Instalando**. Cuando se complete la instalación, actualice la página. El estado debería cambiar a **Instalado**.
1. En Dataverse, seleccione la sección **Aplicaciones** en la navegación de la izquierda y verifique que **Visibilidad de inventario** Power Apps se instala correctamente. Si la sección **Aplicaciones** no exsite, póngase en contacto con el equipo de productos de Visibilidad del inventario en [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com).

> [!NOTE]
> Si tarda más de una hora en instalarse desde la página de LCS, es probable que su cuenta de usuario no tenga permiso para instalar soluciones en el entorno de Dataverse. Siga estos pasos para solucionar el problema:
>
> 1. Cancele el proceso de instalación del complemento de visibilidad de inventario desde la página LCS.
> 1. Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com) y asegúrese de que la cuenta de usuario que desea usar para instalar el complemento tenga la licencia de "Plan de Dynamics 365 Unified Operations" asignada. Asigne la licencia si es necesario.
> 1. Inicie sesión en el [Centro de administración de Power Platform](https://admin.powerplatform.microsoft.com) utilizando la cuenta de usuario correspondiente. A continuación, instale el complemento de visibilidad de inventario siguiendo estos pasos:
>     1. Seleccione el entorno donde desea instalar el complemento.
>     1. Seleccione **Aplicaciones de Dynamics 365**.
>     1. Seleccione **Instalar aplicación**.
>     1. Seleccione **Visibilidad de inventario**
>
> 1. Una vez finalizada la instalación, vuelva a la página de LCS e intente volver a instalar el complemento **Visibilidad de inventario**.

## <a name="uninstall-the-inventory-visibility-add-in"></a><a name="uninstall-add-in"></a>Desinstalar el complemento de visibilidad de inventario

Para desinstalar el complemento de visibilidad de inventario, seleccione **Desinstalar** en la página LCS. El proceso de desinstalación finaliza el complemento de visibilidad de inventario, anula el registro del complemento de LCS y elimina los datos temporales almacenados en la caché de datos del complemento de visibilidad de inventario. Sin embargo, los datos de inventario principal que se almacenan en su suscripción de Dataverse no se eliminan.

Para desinstalar los datos de inventario almacenados en su suscripción de Dataverse, abra [Power Apps](https://make.powerapps.com), seleccione **Entorno** en la barra de navegación y seleccione el entorno de Dataverse que está vinculado con su entorno LCS. Luego vaya a **Soluciones** y elimine las siguientes cinco soluciones en este orden:

1. Anclar la solución para la aplicación Inventory Visibility en soluciones de Dynamics 365
1. Solución de aplicaciones de Dynamics 365 FNO SCM Inventory Visibility
1. Configuración del servicio de inventario
1. Visibilidad de inventario independiente
1. Solución básica de Dynamics 365 FNO SCM Inventory Visibility

Después de eliminar estas soluciones, también se eliminarán los datos almacenados en tablas.

## <a name="set-up-inventory-visibility-in-supply-chain-management"></a><a name="setup-dynamics-scm"></a>Configurar la visibilidad del inventario en Supply Chain Management

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a>Implementar el paquete de integración de visibilidad de inventario

Si está ejecutando Supply Chain Management versión 10.0.17 o anterior, comuníquese con el equipo de soporte a bordo de Inventory Visibility en [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) para obtener el archivo del paquete. Luego implemente el paquete en LCS.

> [!NOTE]
> Si se produce un error de discrepancia de versión durante la implementación, debe importar manualmente el proyecto X ++ a su entorno de desarrollo. Luego, cree el paquete implementable en su entorno de desarrollo e impleméntelo en su entorno de producción.
>
> El código se incluye con Supply Chain Management versión 10.0.18. Si está ejecutando esa versión o una posterior, la implementación no es necesaria.

Asegúrese de que las siguientes funciones estén activadas en su entorno de Supply Chain Management. (De forma predeterminada, están activadas).

| Descripción de la característica | Versión de código | Alternar clase |
|---|---|---|
| Habilitar o deshabilitar el uso de dimensiones de inventario en la tabla InventSum      | 10.0.11 | InventUseDimOfInventSumToggle      |
| Habilitar o deshabilitar el uso de dimensiones de inventario en la tabla InventSumDelta | 10.0.12 | InventUseDimOfInventSumDeltaToggle |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a>Configurar integración de Visibilidad de inventario

Una vez que haya instalado el complemento, prepare su sistema de Supply Chain Management para trabajar con él siguiendo estos pasos.

1. En Supply Chain Management, abra el espacio de trabajo **[Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** y active las caracterísicas siguientes:
    - *Integración de Visibilidad de inventario*: necesaria.
    - *Integración de visibilidad de inventario con compensación de reserva* - Recomendado pero opcional. Requiere la versión 10.0.22 o posterior. Para obtener más información, consulte [Reservas de Visibilidad de inventario](inventory-visibility-reservations.md).

1. Vaya a **Gestión del inventario \> Configuración \> Parámetros de integración de Visibilidad de inventario**.
1. Abra la pestaña **General** y realice los siguientes ajustes:
    - **Punto final de visibilidad de inventario** - Ingrese la URL del entorno en el que está ejecutando Visibilidad de inventario. Para obtener más información, consulte [Buscar el punto de conexión de servicio](inventory-visibility-configuration.md#get-service-endpoint).
    - **Número máximo de registros en una sola solicitud** - Establezca el número máximo de registros para incluir en una sola solicitud. Debe ingresar un número entero positivo menor o igual que 1000. El valor predeterminado es 512. Recomendamos encarecidamente mantener el valor predeterminado a menos que haya recibido asesoramiento del soporte técnico de Microsoft o esté seguro de que necesita cambiarlo.

1. Si habilitó la función opcional *Integración de visibilidad de inventario con compensación de reserva*, abra la pestña **Compensación de reserva** y realice los siguientes ajustes:
    - **Habilitar compensación de reserva** - Ajustado a *Sí* para habilitar esta funcionalidad.
    - **Modificador de compensación de reserva** - Seleccione el estado de la transacción de inventario que compensará las reservas realizadas en Visibilidad de inventario. Esta configuración determina la etapa de procesamiento del pedido que desencadena las compensaciones. La etapa se rastrea por el estado de la transacción de inventario del pedido. Elija una opción de las siguientes:
        - *En orden* - Para el estado *En la transacción*, un pedido enviará una solicitud de compensación cuando se cree. La cantidad de compensación será la cantidad del pedido creado.
        - *Reserva* – Para el estado *Transacción de reserva solicitada*, un pedido enviará una solicitud de compensación cuando esté reservado, recogido, publicado en el albarán o facturado. La solicitud se disparará solo una vez, para el primer paso cuando se produzca el proceso mencionado. La cantidad de compensación será la cantidad a partir de la cual cambió el estado de la transacción de inventario de *En orden* a *Reservado ordenado* (o estado posterior) en la línea de pedido correspondiente.

1. Ir **Gestión del inventario \> Periódico \> Integración de visibilidad de inventario** y habilite el trabajo. Todos los eventos de cambio de inventario de Supply Chain Management ahora se publicarán en Visibilidad de inventario.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
