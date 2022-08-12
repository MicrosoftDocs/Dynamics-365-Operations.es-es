---
title: Habilitar la búsqueda de datos maestros para la configuración del cálculo de impuestos
description: Este artículo explica cómo configurar y habilitar la función de búsqueda de datos maestros de cálculo de impuestos.
author: kai-cloud
ms.date: 07/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 3642bb88d5b0570014513b64eef5fdab6d1ee9d3
ms.sourcegitcommit: 5b721f6fc1ba4350b5bd0eae457f71d80246db42
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2022
ms.locfileid: "9181136"
---
# <a name="enable-master-data-lookup-for-tax-calculation-configuration"></a>Habilitar la búsqueda de datos maestros para la configuración del cálculo de impuestos 

[!include [banner](../includes/banner.md)]

Este artículo explica cómo configurar y habilitar la función de búsqueda de datos maestros de cálculo de impuestos. Hay una lista desplegable disponible para seleccionar valores en la configuración de cálculo de impuestos para campos como **Entidad jurídica**, **Cuenta de proveedor**, **Código de artículo** y **Plazo de entrega**. Estos valores provienen del entorno Microsoft Dynamics 365 Finance conectado usando el origen de datos de Microsoft Dataverse.

> [!NOTE] 
> La función de búsqueda de datos maestros de cálculo de impuestos es una función opcional. Puede omitir los siguientes pasos si deshabilita la característica **Soporte para orígenes de datos de Dataverse del servicio de impuestos** en Regulatory Configuration Service (RCS). Sin embargo, en ese caso, la lista desplegable no estará disponible en la configuración de cálculo de impuestos.

Para habilitar la lista desplegable en la configuración de versión de características de Cálculo de impuestos, complete los siguientes pasos.

1. [Habilitar la integración de Microsoft Power Platform y abrir el entorno de Dataverse.](#enable)
2. [Instalar entidades virtuales de finanzas y operaciones.](#install)
3. [Registrar una aplicación de Azure Active Directory (Azure AD).](#register)
4. [Otorgar permisos de aplicaciones en aplicaciones de finanzas y operaciones.](#grant)
5. [Configurar el origen de datos de la entidad virtual.](#configure)
6. [Habilitar entidades virtuales de Dataverse.](#virtual)
7. [Configurar la aplicación conectada para Cálculo de impuestos.](#set-up)
8. [Importar y configurar la configuración de Asignación de modelos de Dataverse.](#import)

## <a name="enable-microsoft-power-platform-integration-and-open-the-dataverse-environment"></a><a name='enable'></a>Habilitar la integración de Microsoft Power Platform y abrir el entorno de Dataverse

La integración de aplicaciones de finanzas y operaciones con Microsoft Power Platform se puede habilitar cuando crea un nuevo entorno de aplicaciones de finanzas y operaciones en Microsoft Dynamics Lifecycle Services (LCS). Para obtener más información, consulte [Integración de Microsoft Power Platform - Información general de complementos](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). Cuando termine, el nombre de un entorno de Microsoft Power Platform aparecerá en la sección **Integración de Power Platform**.

1. En LCS, en su entorno de finanzas y operaciones, en la sección **Integración de Power Platform**, busque y tome nota del valor de **Nombre del entorno** para el entorno vinculado.

    [![Valor del nombre de entorno.](./media/tcs-dataverse-master-data-lookup-1.png)](./media/tcs-dataverse-master-data-lookup-1.png)

2. En el [centro de administración de Power Platform](https://admin.powerplatform.microsoft.com/environments), en la pestaña **Entornos**, seleccione el entorno que coincida con el valor de **Nombre del entorno** que anotó.
3. En la página **Detalles**, busque el valor de **URL del entorno** del entorno de Dataverse. Tome nota de este valor, porque lo necesitará en el [Paso 7. Configurar la aplicación conectada para Cálculo de impuestos](#set-up).
4. Asegúrese de que puede abrir el entorno de Dataverse en su navegador seleccionando el valor **URL del entorno**.

    [![Página del entorno de Dataverse.](./media/tcs-dataverse-master-data-lookup-2.png)](./media/tcs-dataverse-master-data-lookup-2.png)

    > [!NOTE]
    > Mantenga el entorno de Dataverse abierto en el navegador. Lo necesitará en el [Paso 5. Configurar el origen de datos de la entidad virtual](#configure).

Para obtener más información, consulte [Habilitar la integración de Microsoft Power Platform](../../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md).

## <a name="install-finance-and-operations-virtual-entities"></a><a name='install'></a>Instalar entidades virtuales de finanzas y operaciones

La solución de Dataverse para entidades virtuales de finanzas y operaciones debe instalarse desde la solución de entidades virtuales de Microsoft AppSource.

1. En AppSource, busque [Entidad virtual de finanzas y operaciones](https://appsource.microsoft.com/product/dynamics-365/mscrm.finance_and_operations_virtual_entity).
2. Seleccione **Obtener ahora**.
3. En el campo **Seleccionar un entorno**, ingrese el valor de **Nombre del entorno** que anotó anteriormente.
4. Seleccione las casillas y luego seleccione **Instalar**.

Cuando se completa la instalación, puede buscar la aplicación **Entidad virtual de finanzas y operaciones** en el [centro de administración de Power Platform](https://admin.powerplatform.microsoft.com/), en **Recursos** \> **Aplicaciones de Dynamics 365**.

Para obtener más información, consulte [Obtener la solución de entidades virtuales](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#get-virtual-entity-solution).

## <a name="register-an-azure-ad-application"></a><a name='register'></a>Registrar una aplicación de Azure AD

Debe registrar una aplicación de Azure AD en el mismo inquilino que las aplicaciones de finanzas y operaciones, para que puedan ser llamadas por Dataverse.

1. En el [portal de Azure](https://portal.azure.com), vaya a **Azure Active Directory \> Registros de aplicación**.
2. Seleccione **Nuevo registro** y después introduzca la información siguiente:

    - **Nombre** - Escriba un nombre único.
    - **Tipo de cuenta** - Ingrese **Cualquier directorio de Azure AD** (inquilino único o multiinquilino).
    - **URI de redireccionamiento**: deje este campo en blanco.

3. Seleccione **Registrar**.
4. Anote el valor de **Id. de aplicación (cliente)**, puesto que lo necesitará más adelante.

    [![Valor de Id. de aplicación de Azure AD (cliente).](./media/tcs-dataverse-master-data-lookup-3.png)](./media/tcs-dataverse-master-data-lookup-3.png)

5. Cree una clave simétrica para la aplicación.
6. En la nueva aplicación, seleccione **Certificados y secretos**.
7. Seleccione **Nuevo secreto de cliente**.
8. Ingrese una descripción, seleccione una fecha de vencimiento y luego seleccione **Guardar**. Se creará y mostrará una clave. Copie el valor para su uso posterior.

Para obtener más información, consulte [Registrar aplicación de Azure AD](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#register-the-app-in-the-azure-portal).

## <a name="grant-app-permissions-in-finance-and-operations-apps"></a><a name='grant'></a>Otorgar permisos de aplicaciones en aplicaciones de finanzas y operaciones

Dataverse usa la aplicación de Azure AD que creó para llamar aplicaciones de finanzas y operaciones. Por tanto, las aplicaciones de finanzas y operaciones deben confiar en la aplicación y asociarla con una cuenta de usuario que tenga los derechos adecuados. En las aplicaciones de finanzas y operaciones, debe crear un usuario de servicio especial que tenga derechos **solamente** a la funcionalidad de entidades virtuales. Este usuario del servicio no debe tener otros derechos. Después de completar este paso, cualquier aplicación que tenga el secreto de la aplicación de Azure AD que creó podrá llamar al entorno de aplicaciones de finanzas y operaciones y acceder a la funcionalidad de entidades virtuales.

1. En su entorno, vaya a **Administración del sistema** \> **Usuarios** \> **Usuarios**.
2. Seleccione **Nuevo** para agregar un nuevo usuario e ingrese la siguiente información de campo:

    - **Id. de usuario** - Ingrese **dataverseintegration** u otro valor.
    - **Nombre de usuario** - Ingrese **integración de dataverse** u otro valor.
    - **Proveedor**: establezca este campo en **NonAAD**.
    - **Correo electrónico**: ingrese **dataverseintegration** u otro valor. (El valor no tiene que ser una cuenta de correo electrónico válida).

3. Asigne el rol de seguridad **Aplicación de entidad virtual de CDS** al usuario.
4. Elimine todos los demás roles, incluido **Usuario del sistema**.
5. Vaya a **Administración del sistema** \> **Configuración** \> **Aplicaciones de Azure Active Directory** para registrar Dataverse. 
6. Agregue una fila y luego, en el campo **Id. de cliente**, ingrese el valor de **Id. de la aplicación (cliente)** que anotó anteriormente.
7. Escriba un nombre en el campo **Nombre**. Por ejemplo, escriba **Integración de Dataverse**.
8. En el campo **Id. de usuario**, escriba el id. de usuario que creó anteriormente.

Para obtener más información, consulte [Obtener permisos de aplicaciones en aplicaciones de finanzas y operaciones](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#grant-app-permissions-in-finance-and-operations-apps).

## <a name="configure-the-virtual-entity-data-source"></a><a name='configure'></a>Configurar la fuente de datos de la entidad virtual

Debe proporcionar a Dataverse la instancia de la aplicación de finanzas y operaciones a la que conectarse.

1. Su entorno de Dataverse aún debe estar abierto en su navegador desde el [Paso 1. Habilitar integración de Microsoft Power Platform y abrir el entorno de Dataverse](#enable). Seleccione el botón de configuración (símbolo de engranaje) en la parte superior derecha y, a continuación, seleccione **Configuración avanzada**.

    [![Abrir Configuración avanzada en el entorno de Dataverse.](./media/tcs-dataverse-master-data-lookup-4.png)](./media/tcs-dataverse-master-data-lookup-4.png)

2. En el menú desplegable **Configuración**, seleccione **Administración**.

    [![Administración.](./media/tcs-dataverse-master-data-lookup-5.png)](./media/tcs-dataverse-master-data-lookup-5.png)

3. Seleccione **Orígenes de datos de entidades virtuales**.

    [![Orígenes de datos de entidades virtuales.](./media/tcs-dataverse-master-data-lookup-6.png)](./media/tcs-dataverse-master-data-lookup-6.png)

4. Seleccione el origen de datos designado en **Finance and Operations**.

    [![Origen de datos para Finance and Operations.](./media/tcs-dataverse-master-data-lookup-7.png)](./media/tcs-dataverse-master-data-lookup-7.png)

5. Ingrese la siguiente información de los pasos anteriores:

    - **URL de destino**: ingrese la URL donde puede acceder a las aplicaciones de finanzas y operaciones.
    - **URL de OAuth**: ingrese `https://login.windows.net/`.
    - **Id. de inquilino**: especifique su inquilino. Este valor puede ser el nombre de dominio del correo electrónico de su empresa (como contoso.com).
    - **Id. de aplicación AAD**: introduzca el valor de **Id. de la aplicación (cliente)** que creó anteriormente.
    - **Secreto de aplicación de AAD**: introduzca el secreto que se generó anteriormente.
    - **Recurso de AAD**: introduzca **00000015-0000-0000-c000-000000000000**. Este valor es la aplicación de Azure AD que representa aplicaciones de finanzas y operaciones. Siempre debe ser este mismo valor.

6. Guarde los cambios.
7. Cierre la página para volver a la página **Administración**, donde comenzará [Paso 6. Habilitar entidades virtuales de Dataverse](#virtual).

    [![Cerrar la entidad para su edición.](./media/tcs-dataverse-master-data-lookup-8.png)](./media/tcs-dataverse-master-data-lookup-8.png)

Para obtener más información, consulte [Configurar el origen de datos de entidades virtuales](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#configure-the-virtual-entity-data-source).

## <a name="enable-dataverse-virtual-entities"></a><a name='virtual'></a>Habilitar entidades virtuales de Dataverse

La visibilidad de las entidades virtuales de las aplicaciones de finanzas y operaciones debe establecerse en **Sí** antes de que puedan ser consumidas por la configuración de Cálculo de impuestos.

> [!NOTE]
> Puede omitir este paso habilitando las entidades virtuales relacionadas con Cálculo de impuestos con solo un clic en [Paso 8. Configurar la aplicación conectada para Cálculo de impuestos](#import). Sin embargo, le recomendamos que habilite manualmente al menos una entidad virtual para indicar que la conexión entre las aplicaciones de finanzas y operaciones y Dataverse está bien establecida.

1. En su entorno de Dataverse, en la página **Administración**, seleccione el botón de filtro (símbolo de embudo) en la esquina superior derecha.

    [![Botón Filtro.](./media/tcs-dataverse-master-data-lookup-9.png)](./media/tcs-dataverse-master-data-lookup-9.png)

2. En la ventana **Búsqueda avanzada**, en el campo **Buscar**, seleccione **Entidades de operaciones y finanzas disponibles**.
3. Agregue la siguiente regla: **Nombre** – **Contiene** – **CompanyInfoEntity**. Luego seleccione **Resultados**.

    [![Ventana de búsqueda avanzada.](./media/tcs-dataverse-master-data-lookup-10.png)](./media/tcs-dataverse-master-data-lookup-10.png)

4. Seleccione **CompanyInfoEntity** en los resultados de la búsqueda, seleccione la casilla **Visible** y, a continuación, seleccione **Guardar**.

    [![Configuración de visibilidad de entidades.](./media/tcs-dataverse-master-data-lookup-11.png)](./media/tcs-dataverse-master-data-lookup-11.png)

5. Repita los pasos anteriores para las siguientes entidades a las que se hace referencia en la configuración de Cálculo de impuestos:

    - CompanyInfoEntity
    - CurrencyEntity
    - CustCustomerV3Entity
    - DeliveryTermsEntity
    - EcoResProductCategoryEntity
    - EcoResReleasedProductV2Entity
    - LogisticsAddressCountryRegionTranslationEntity
    - LogisticsAddressStateEntity
    - PurchProcurementChargeCDSEntity
    - SalesChargeCDSEntity
    - TaxGroupEntity
    - TaxItemGroupHeadingEntity
    - VendVendorV2Entity
    - InventOperationalSiteV2Entity
    - TaxExemptCodeEntity
    - InventWarehouseEntity

    > [!NOTE]
    > Solo los primeros 5000 registros de una entidad pueden ser recuperados por Dataverse y mostrarlos en la lista desplegable de la configuración de Cálculo de impuestos.

Para obtener más información, [Consulte las entidades virtuales de Microsoft Dataverse](../../fin-ops-core/dev-itpro/power-platform/enable-virtual-entities.md).

## <a name="set-up-the-connected-application-for-tax-calculation"></a><a name='set-up'></a>Configurar la aplicación conectada para Cálculo de impuestos

1. En RCS, abra el espacio de trabajo **Administración de características** y habilite las funciones siguientes:

    - Compatibilidad con orígenes de datos de Informes electrónicos de Dataverse
    - Soporte de orígenes de datos de Dataverse de servicio de impuestos
    - Características de globalización

2. Vaya a **Informes electrónicos** y, luego, en la sección **Vínculos relacionados**, seleccione **Aplicaciones conectadas**.

    [![Aplicaciones conectadas.](./media/tcs-dataverse-master-data-lookup-12.png)](./media/tcs-dataverse-master-data-lookup-12.png)

3. Seleccione **Nuevo** para agregar un registro e ingrese la siguiente información.

    - **Nombre** – Introduzca un nombre.
    - **Tipo**: seleccione **Dataverse**.
    - **Solicitud**: introduzca el valor de **URL del entorno** de su entorno de Dataverse, que anotó en el [Paso 1. Habilitar integración de Microsoft Power Platform y abrir su entorno de Dataverse](#enable).
    - **Inquilino**: introduzca su inquilino.
    - **URL personalizado**: ingrese su URL de Dataverse y adjúntela con **/api/data/v9.1**.

4. Seleccione **Comprobar conexión** y, a continuación, en el cuadro de diálogo que aparece, seleccione **Haga clic aquí para conectarse a la aplicación remota seleccionada**.

    [![Comprobar la conexión.](./media/tcs-dataverse-master-data-lookup-13.png)](./media/tcs-dataverse-master-data-lookup-13.png)
5. Asegúrese de recibir un mensaje de "Correcto" que indica que la conexión se ha establecido correctamente.

    [![Mensaje de éxito.](./media/tcs-dataverse-master-data-lookup-14.png)](./media/tcs-dataverse-master-data-lookup-14.png)

## <a name="import-and-set-up-the-dataverse-model-mapping-configuration"></a><a name='import'></a>Importar y configurar la configuración de asignación de modelos de Dataverse

Microsoft proporciona configuraciones predeterminadas de asignación de modelos para entidades desde aplicaciones de finanzas y operaciones hasta Cálculo de impuestos.

1. En RCS, vaya a **Espacios de trabajo > Informes electrónicos**.
2. En la sección **Proveedores de configuración**, en el mosaico para el proveedor **Microsoft**, seleccione **Repositorios**.

    [![Repositorios.](./media/tcs-dataverse-master-data-lookup-15.png)](./media/tcs-dataverse-master-data-lookup-15.png)

3. Seleccione el registro **Repositorio de configuración global** y después seleccione **Abrir**.
4. En **Modelo de datos fiscales** \> **Modelo de datos de cálculo de impuestos**, seleccione la configuración de **Asignación de modelos de Dataverse**.
5. En la ficha desplegable **Versiones**, seleccione una versión que coincida con la versión de sus aplicaciones de finanzas y operaciones, y luego seleccione **Importar**.

    [![Importar la configuración de la asignación de modelos de Dataverse.](./media/tcs-dataverse-master-data-lookup-16.png)](./media/tcs-dataverse-master-data-lookup-16.png)

    > [!IMPORTANT]
    > La configuración de **Asignación de modelos de Dataverse** es efectiva solo en su versión importada más alta. Por lo tanto, no debe importar una versión de la configuración de **Asignación de modelos de Dataverse** que sea superior a la versión de la configuración de Cálculo de impuestos que planea implementar. Por ejemplo, si planea implementar la versión 40.50.225 de la configuración de Cálculo de impuestos, solo debe importar la 40.50.13 de la configuración de **Asignación de modelos de Dataverse**. No debe importar la versión 40.54.14. De lo contrario, habrá una discrepancia en el modelo de datos en la configuración.

6. Vuelva a **Informes electrónicos** y seleccione el mosaico **Configuraciones de impuestos**.
7. Seleccione la configuración de **Asignación de modelos de Dataverse** importada y, a continuación, seleccione **Editar**.
8. Establezca la opción **Predeterminado para la asignación de modelo** a **Sí**.
9. En el campo **Aplicación conectada**, seleccione la aplicación conectada que configuró en el [Paso 7. Configurar la aplicación conectada para Cálculo de impuestos](#set-up).
10. Establezca la opción **Establecer la visibilidad de la tabla virtual** en **Sí** para configurar todas las entidades virtuales relacionadas con Cálculo de impuestos como visibles.

Ahora ha completado la configuración de la funcionalidad de búsqueda de datos maestros. Una lista desplegable para campos como **Entidad legal**, **Cuenta del proveedor**, **Código de artículo** y **Plazo de entrega** de Dynamics 365 Finance estará ahora habilitada en la configuración de **Versión de la característica Cálculo de impuestos**.

[![Lista desplegable de entidades legales.](./media/tcs-dataverse-master-data-lookup-17.png)](./media/tcs-dataverse-master-data-lookup-17.png)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
