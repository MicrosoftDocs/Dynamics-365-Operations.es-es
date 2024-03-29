---
title: Instalar el complemento de visibilidad de inventario
description: Este artículo describe cómo instalar el complemento de visibilidad de inventario para Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: c08568b14d7f5c79a1d3609107a88f905498ce2b
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762791"
---
# <a name="install-and-set-up-inventory-visibility"></a>Instalar y configurar Inventory Visibility

[!include [banner](../includes/banner.md)]

Este artículo describe cómo instalar el complemento de visibilidad de inventario para Microsoft Dynamics 365 Supply Chain Management.

Debe usar [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/v2) para instalar el complemento de visibilidad de inventario. Lifecycle Services es un portal de colaboración que proporciona un entorno y un conjunto de servicios actualizados periódicamente que le ayudan a gestionar el ciclo de vida de la aplicación de sus aplicaciones de Finanzas y operaciones. Para obtener más información, consulte [Recursos de Lifecycle Services](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

> [!TIP]
> Le recomendamos que se una al grupo de usuarios del complemento Visibilidad de inventario, donde puede encontrar guías útiles, obtener nuestras últimas actualizaciones y publicar cualquier pregunta que pueda tener sobre el uso de Visibilidad de inventario. Para unirse, envíe un correo electrónico al equipo de productos de Visibilidad de inventario a [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) e incluya su identificador de entorno de Supply Chain Management.

## <a name="inventory-visibility-prerequisites"></a>Requisitos previos Visibilidad de inventario

Para poder instalar el complemento de visibilidad de inventario, debe completar las siguientes tareas:

- Obtenga un proyecto de implementación de Lifecycle Services con al menos un entorno implementado.
- Asegúrese de que se hayan completado los requisitos previos para configurar complementos. Para obtener más información sobre estos requisitos previos, consulte [Información general sobre los complementos](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). La visibilidad de inventario no requiere vinculación de escritura dual.

> [!NOTE]
> Los países y regiones admitidos actualmente incluyen Canadá (CCA, ECA), Estados Unidos (WUS, EUS), la Unión Europea (NEU, WEU), Reino Unido (SUK, WUK) y Australia (EAU, SEAU), Japón (EJP, WJP) y Brasil (SBR, SCUS).

Si tiene alguna pregunta sobre estos requisitos previos, contacte con el equipo de productos de visibilidad de inventario en [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com).

## <a name="install-the-inventory-visibility-add-in"></a><a name="install-add-in"></a>Instalar el complemento de visibilidad de inventario

Antes de instalar el complemento, registre una solicitud y agregue un secreto de cliente a Azure Active Directory (Azure AD) en su suscripción de Azure. Para obtener instrucciones, consulte [Registrar una solicitud](/azure/active-directory/develop/quickstart-register-app) y [Agregar un secreto de cliente](/azure/active-directory/develop/quickstart-register-app#add-a-certificate). Asegúrese de anotar los valores de **Id. de la aplicación (cliente)**, **Secreto del cliente** e **Id. de inquilino**, porque los necesitará más adelante.

> [!IMPORTANT]
> Si tiene más de un entorno de Lifecycle Services, cree una aplicación de Azure AD diferente para cada uno de ellos. Si usa el mismo ID de aplicación y el mismo ID de inquilino para instalar el complemento de visibilidad de inventario para diferentes entornos, se producirá un problema de token para los entornos más antiguos. De este modo, solo será válida la último instalación.

Después de registrar una solicitud y agregar un secreto de cliente en Azure AD, siga estos pasos para instalar el complemento de visibilidad de inventario.

1. Inicie sesión en [Lifecycle Services](https://lcs.dynamics.com/Logon/Index).
1. En la página de inicio, seleccione el proyecto donde se implementa su entorno.
1. En la página del proyecto, seleccione el entorno donde desea instalar el complemento.
1. En la página del entorno, desplácese hacia abajo hasta que encuentre la sección **Complementos de entorno** en la sección **Integración de Power Platform**. Allí, puede encontrar el  nombre del entorno de Dataverse. Confirme que el nombre del entorno de Dataverse es el que desea utilizar para la visibilidad del inventario.

    > [!NOTE]
    > Actualmente, solo se admiten entornos de Dataverse creados mediante Lifecycle Services. Si su entorno de Dataverse se creó de otra forma (por ejemplo, usando el Centro de administración de PowerApps) y si está vinculado a su entorno de Supply Chain Management, primero debe solucionar el problema de asignación antes de instalar el complemento Visibilidad de inventario.
    >
    > Es posible que su entorno de doble escritura esté vinculado a una instancia de Dataverse mientras Lifecycle Services no está configurado para la integración de Power Platform. Este desajuste de vinculación puede provocar un comportamiento inesperado. Recomendamos que los detalles del entorno de Lifecycle Services coincidan con lo que está conectado en doble escritura para que los eventos comerciales, las tablas virtuales y los complementos puedan usar la misma conexión. Vea [Desajuste de enlace](../../fin-ops-core/dev-itpro/data-entities/dual-write/lcs-setup.md#linking-mismatch) para obtener información sobre cómo solucionar el problema de asignación. Una vez que se resuelve el problema de asignación, puede proceder a instalar Inventory Visibility.

1. En la sección **Complementos de entorno**, seleccione **Instalar un nuevo complemento**.

    ![Página de entorno en Lifecycle Services](media/inventory-visibility-environment.png "Página de entorno en Lifecycle Services")

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
> Si el sistema le advierte que no tiene permiso para instalar Inventory Visibility en Lifecycle Services, debe comunicarse con el administrador para modificar su permiso.
>
> Si tarda más de una hora en instalarse desde la página de Lifecycle Services, es probable que su cuenta de usuario no tenga permiso para instalar soluciones en el entorno de Dataverse. Siga estos pasos para solucionar el problema:
>
> 1. Cancele el proceso de instalación del complemento de visibilidad de inventario desde la página de Lifecycle Services.
> 1. Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com) y asegúrese de que la cuenta de usuario que desea usar para instalar el complemento tenga la licencia de "Plan de Dynamics 365 Unified Operations" asignada. Asigne la licencia si es necesario.
> 1. Inicie sesión en el [Centro de administración de Power Platform](https://admin.powerplatform.microsoft.com) utilizando la cuenta de usuario correspondiente. A continuación, instale el complemento de visibilidad de inventario siguiendo estos pasos:
>     1. Seleccione el entorno donde desea instalar el complemento.
>     1. Seleccione **Aplicaciones de Dynamics 365**.
>     1. Seleccione **Instalar aplicación**.
>     1. Seleccione **Visibilidad de inventario**
>
> 1. Una vez finalizada la instalación, vuelva a la página de Lifecycle Services e intente volver a instalar el complemento **Visibilidad de inventario**.

## <a name="set-up-inventory-visibility-in-supply-chain-management"></a><a name="setup-dynamics-scm"></a>Configurar la visibilidad del inventario en Supply Chain Management

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a>Implementar el paquete de integración de visibilidad de inventario

Si está ejecutando Supply Chain Management versión 10.0.17 o anterior, comuníquese con el equipo de soporte a bordo de Inventory Visibility en [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) para obtener el archivo del paquete. Luego implemente el paquete en Lifecycle Services.

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
    - **Modificador de compensación de reserva** - Seleccione el estado de la transacción de inventario que compensará las reservas realizadas en Visibilidad de inventario. Esta configuración determina la etapa de procesamiento del pedido que desencadena las compensaciones. La etapa se rastrea por el estado de la transacción de inventario del pedido. Seleccione una de las siguientes opciones:
        - *En orden* - Para el estado *En la transacción*, un pedido enviará una solicitud de compensación cuando se cree. La cantidad de compensación será la cantidad del pedido creado.
        - *Reserva* – Para el estado *Transacción de reserva solicitada*, un pedido enviará una solicitud de compensación cuando esté reservado, recogido, publicado en el albarán o facturado. La solicitud se disparará solo una vez, para el primer paso cuando se produzca el proceso mencionado. La cantidad de compensación será la cantidad a partir de la cual cambió el estado de la transacción de inventario de *En orden* a *Reservado ordenado* (o estado posterior) en la línea de pedido correspondiente.

1. Ir **Gestión del inventario \> Periódico \> Integración de visibilidad de inventario** y habilite el trabajo. Todos los eventos de cambio de inventario de Supply Chain Management ahora se publicarán en Visibilidad de inventario.

## <a name="uninstall-the-inventory-visibility-add-in"></a><a name="uninstall-add-in"></a>Desinstalar el complemento de visibilidad de inventario

Para desinstalar el complemento de visibilidad de inventario, siga estos pasos:

1. Inicie sesión en de Supply Chain Management.
1. Ir **Gestión del inventario \> Periódico \> Integración de visibilidad de inventario** y deshabilite el trabajo.
1. Vaya a Lifecycle Services y abra la página del entorno en el que desea desinstalar el complemento (consulte también [Instalar el complemento de visibilidad de inventario](#install-add-in)).
1. Seleccione **Desinstalar**.
1. El proceso de desinstalación ahora finaliza el complemento de visibilidad de inventario, anula el registro del complemento de Lifecycle Services y elimina los datos temporales almacenados en la caché de datos del complemento de visibilidad de inventario. Sin embargo, los datos de inventario principal que se sincronizaron con su suscripción de Dataverse todavía se almacenan allí. Para eliminar estos datos, complete el resto de este procedimiento.
1. Abra [Power Apps](https://make.powerapps.com).
1. Seleccione **Entorno** en la barra de navegación.
1. Seleccione el entorno de Dataverse que está enlazado con su entorno de Lifecycle Services.
1. Vaya a **Soluciones** y elimine las siguientes cinco soluciones en este orden:
    1. Dynamics 365 Inventory Visibility: delimitador
    1. Dynamics 365 Inventory Visibility - Complementos
    1. Dynamics 365 Inventory Visibility - Aplicación
    1. Dynamics 365 Inventory Visibility - Controles
    1. Dynamics 365 Inventory Visibility - Base 

    Después de eliminar estas soluciones, también se eliminarán los datos almacenados en tablas.

> [!NOTE]
> Si restaura una base de datos de Supply Chain Management después de desinstalar el complemento Inventory Visibility y luego desea volver a instalar el complemento, asegúrese de haber eliminado los datos antiguos de Inventory Visibility que están almacenados en su suscripción a Dataverse (como se describe en el procedimiento anterior) antes de reinstalar el complemento. Esto evitará problemas de inconsistencia de datos que de otro modo podrían ocurrir.

## <a name="clean-inventory-visibility-data-from-dataverse-before-restoring-the-supply-chain-management-database"></a><a name="restore-environment-database"></a>Limpiar datos de visibilidad de inventario de Dataverse antes de restaurar la base de datos de Supply Chain Management

Si ha estado usando Inventory Visibility y luego restauró su base de datos de Supply Chain Management, entonces su base de datos restaurada puede contener datos que ya no son consistentes con los datos sincronizados previamente por Inventory Visibility para Dataverse. Esta inconsistencia de datos puede causar errores del sistema y otros problemas. Por lo tanto, es importante que siempre limpie todos los datos de Visibilidad de inventario de Dataverse antes de restaurar una base de datos de Supply Chain Management.

Si necesita restaurar una base de datos de Supply Chain Management, use el siguiente procedimiento:

1. Desinstale el complemento de visibilidad de inventario y quite todos los datos relacionados de Dataverse, como se describe en [Desinstalar el complemento de visibilidad del inventario](#uninstall-add-in)
1. Restaure su base de datos de Supply Chain Management, por ejemplo, como se describe en [Restauración de un punto en el tiempo de la base de datos (PITR)](../../fin-ops-core/dev-itpro/database/database-point-in-time-restore.md) o [Restauración en un momento dado de la base de datos de producción en un entorno de espacio aislado](../../fin-ops-core/dev-itpro/database/database-pitr-prod-sandbox.md).
1. Si aún desea usarlo, vuelva a instalar y configure el complemento de visibilidad de inventario como se describe en [Instalar el complemento de visibilidad de inventario](#install-add-in) y [Configurar la integración de visibilidad de inventario](#setup-inventory-visibility-integration)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
