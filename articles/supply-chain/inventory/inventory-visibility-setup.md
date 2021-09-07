---
title: Establecer la visibilidad de inventario
description: Este tema describe cómo instalar el complemento de visibilidad de inventario para Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 8573fe01abb1c6092012baf85e8b7df40b74a31f
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "7343593"
---
# <a name="set-up-inventory-visibility"></a>Establecer la visibilidad de inventario

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Este tema describe cómo instalar el complemento de visibilidad de inventario para Microsoft Dynamics 365 Supply Chain Management.

Debe usar Microsoft Dynamics Lifecycle Services (LCS) para instalar el complemento de visibilidad de inventario. LCS es un portal de colaboración que proporciona un entorno y un conjunto de servicios actualizados periódicamente que le ayudan a gestionar el ciclo de vida de la aplicación de sus aplicaciones de Finance and Operations.

Para obtener más información, consulte [Recursos de Lifecycle Services](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

## <a name="inventory-visibility-prerequisites"></a>Requisitos previos Visibilidad de inventario

Para poder instalar el complemento de visibilidad de inventario, debe completar las siguientes tareas:

- Obtenga un proyecto de implementación de LCS con al menos un entorno implementado.
- Asegúrese de que se hayan completado los requisitos previos para configurar complementos. Para obtener más información sobre estos requisitos previos, consulte [Información general sobre los complementos](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). La visibilidad de inventario no requiere vinculación de escritura dual.
- Póngase en contacto con el equipo de productos de Visibilidad del inventario en [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) para obtener los siguientes archivos obligatorios:

    - `InventoryServiceApplication.PackageDeployer.zip`
    - `Inventory Visibility Integration.zip` (si la versión de Supply Chain Management que está ejecutando es anterior a la versión 10.0.18)

> [!NOTE]
> Los países y regiones admitidos actualmente incluyen Canadá (CCA, ECA), Estados Unidos (WUS, EUS), la Unión Europea (NEU, WEU), Reino Unido (SUK, WUK) y Australia (EAU, SEAU). .

Si tiene alguna pregunta sobre estos requisitos previos, comuníquese con el equipo de productos de Visibilidad de inventario.

## <a name="set-up-dataverse"></a><a name="setup-microsoft-dataverse"></a>Configurar Dataverse

Para configurar Dataverse para que pueda usarse con Visibilidad de inventario, use la herramienta Package Deployer para implementar el paquete de Visibilidad de inventario. En las siguientes subsecciones, se describe cómo completar cada tarea.

> [!NOTE]
> Actualmente, solo se admiten entornos de Dataverse creados mediante LCS. Si su entorno de Dataverse se creó de otra forma (por ejemplo, usando el Centro de administración de Power Apps) y si está vinculado a su entorno de Supply Chain Management, primero debe comunicarse con el equipo de productos de Visibilidad de inventario para solucionar el problema de asignación. Luego podrá instalar Visibilidad de inventario.

### <a name="migrate-from-an-old-version-of-the-dataverse-solution"></a>Migrar desde una versión anterior de la solución Dataverse

Si ha instalado una versión anterior de la solución Dataverse de Visibilidad de inventario, siga estas instrucciones para actualizar su versión. Existen dos casos:

- **Caso 1:** Si configura manualmente Dataverse importando la solución `Inventory Visibility Dataverse Solution_1_0_0_2_managed.zip`, siga estos pasos:

    1. Descargue los tres archivos siguientes:

        - `Inventory Visibility Dataverse Solution_1_0_0_3_managed.zip`
        - `InventoryServiceBase_managed.cab`
        - `InventoryServiceApplication.PackageDeployer.zip`

    1. Importe manualmente `Inventory Visibility Dataverse Solution_1_0_0_3_managed.zip` e `InventoryServiceBase_managed.cab` en Dataverse siguiendo estos pasos:

        1. Abra la URL de su entorno de Dataverse.
        1. Abra la página **Soluciones**.
        1. Seleccione **Importar**.

    1. Utilice la herramienta Package Deployer para implementar el paquete de `InventoryServiceApplication.PackageDeployer.zip`. Para obtener instrucciones, consulte la sección [Utilizar la herramienta Package Deployer para implementar el paquete](#deploy-package) más adelante en este tema.

- **Caso 2:** Si configuró Dataverse mediante el uso de la herramienta Package Deployer antes de instalar el antiguo paquete de `.*PackageDeployer.zip`, descargue `InventoryServiceApplication.PackageDeployer.zip` y haga una actualización. Para obtener instrucciones, consulte la sección [Utilizar la herramienta Package Deployer para implementar el paquete](#deploy-package).

### <a name="use-the-package-deployer-tool-to-deploy-the-package"></a><a name="deploy-package"></a>Utilizar la herramienta Package Deployer para implementar el paquete

1. Instale las herramientas de desarrollo como se describe en [Descargar herramientas de NuGet](/dynamics365/customerengagement/on-premises/developer/download-tools-nuget).
1. Desbloquee el archivo de `InventoryServiceApplication.PackageDeployer.zip` que descargó del grupo Teams siguiendo estos pasos:

    1. Mantenga seleccionado (o haga clic con el botón derecho) el archivo y luego seleccione **Propiedades**.
    1. En el cuadro de diálogo **Propiedades**, en la ficha **General**, busque la sección **Seguridad**, seleccione **Desbloquear** y aplique el cambio. Si no hay ninguna sección de **Seguridad** en la ficha **General**, el archivo no está bloqueado. En este caso, continúe con el siguiente paso.

    ![Desbloquear el archivo descargado](media/unblock-file.png "Desbloquear el archivo descargado")

1. Descomprima `InventoryServiceApplication.PackageDeployer.zip` para encontrar los siguientes elementos:

    - Carpeta `InventoryServiceApplication`
    - Archivo `[Content_Types].xml`
    - Archivo `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll`

1. Copie cada uno de esos elementos en el directorio `.\Tools\PackageDeployment`. (Este directorio se creó cuando instaló las herramientas de desarrollo).
1. Ejecute `.\Tools\PackageDeployment\PackageDeployer.exe` y siga las instrucciones en pantalla para importar las soluciones.

## <a name="install-the-inventory-visibility-add-in"></a><a name="install-add-in"></a>Instalar el complemento de visibilidad de inventario

Antes de instalar el complemento, registre una solicitud y agregue un secreto de cliente a Azure Active Directory (Azure AD) en su suscripción de Azure. Para obtener instrucciones, consulte [Registrar una solicitud](/azure/active-directory/develop/quickstart-register-app) y [Agregar un secreto de cliente](/azure/active-directory/develop/quickstart-register-app#add-a-certificate). Asegúrese de anotar los valores de **Id. de la aplicación (cliente)**, **Secreto del cliente** e **Id. de inquilino**, porque los necesitará más adelante.

Después de registrar una solicitud y agregar un secreto de cliente en Azure AD, siga estos pasos para instalar el complemento de visibilidad de inventario.

1. Inicie sesión en [LCS](https://lcs.dynamics.com/Logon/Index).
1. En la página de inicio, seleccione el proyecto donde se implementa su entorno.
1. En la página del proyecto, seleccione el entorno donde desea instalar el complemento.
1. En la página del entorno, desplácese hacia abajo hasta que encuentre la sección **Complementos de entorno** en la sección **Integración de Power Platform**. Allí, puede encontrar el  nombre del entorno de Dataverse.
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

## <a name="uninstall-the-inventory-visibility-add-in"></a><a name="uninstall-add-in"></a>Desinstalar el complemento de visibilidad de inventario

Para desinstalar el complemento de visibilidad de inventario, seleccione **Desinstalar** en la página LCS. El proceso de desinstalación finaliza el complemento de visibilidad de inventario, anula el registro del complemento de LCS y elimina los datos temporales almacenados en la caché de datos del complemento de visibilidad de inventario. Sin embargo, los datos de inventario principal que se almacenan en su suscripción de Dataverse no se eliminan.

Para desinstalar los datos de inventario almacenados en su suscripción de Dataverse, abra [Power Apps](https://make.powerapps.com), seleccione **Entorno** en la barra de navegación y seleccione el entorno de Dataverse que está vinculado con su entorno LCS. Luego vaya a **Soluciones** y elimine las siguientes cinco soluciones:

- Anclar la solución para la aplicación Inventory Visibility en soluciones de Dynamics 365
- Solución de aplicaciones de Dynamics 365 FNO SCM Inventory Visibility
- Configuración del servicio de inventario
- Visibilidad de inventario independiente
- Solución básica de Dynamics 365 FNO SCM Inventory Visibility

Después de eliminar estas soluciones, también se eliminarán los datos almacenados en tablas.

## <a name="set-up-supply-chain-management"></a><a name="setup-dynamics-scm"></a>Configurar Supply Chain Management

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

1. En Supply Chain Management, abra el espacio de trabajo **[Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** y active la caracterísica *Integración de visibilidad de inventario*.
1. Ir **Gestión del inventario \> Configurar \> Parámetros de integración de visibilidad de inventario** e ingrese la URL del entorno en el que está ejecutando Visibilidad de inventario. Para obtener más información, consulte [Buscar el punto de conexión de servicio](inventory-visibility-power-platform.md#get-service-endpoint).
1. Ir **Gestión del inventario \> Periódico \> Integración de visibilidad de inventario** y habilite el trabajo. Todos los eventos de cambio de inventario de Supply Chain Management ahora se publicarán en Visibilidad de inventario.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
