---
title: Commerce analytics (versión preliminar)
description: Este tema explica cómo instalar y utilizar la capacidad de análisis en Microsoft Dynamics 365 Commerce.
author: AamirAllaq
ms.date: 11/23/2021
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: aamiral
ms.search.validFrom: 2021-11-12
ms.openlocfilehash: 8cfe2af756315b5be3eb22d99376a96166fffc52
ms.sourcegitcommit: f9fca3d55b47e615e5ef64669dab184e057ec234
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2021
ms.locfileid: "7862782"
---
# <a name="commerce-analytics-preview"></a>Commerce analytics (versión preliminar)

[!include [banner](includes/banner.md)]

Este tema explica cómo instalar Commerce analytics (versión preliminar), la capacidad de análisis funcional que se incluye en Microsoft Dynamics 365 Commerce.

## <a name="commerce-analytics-preview-live-demo"></a>Demostración en vivo de Commerce analytics (versión preliminar)

Puede probar una [demostración en vivo de Commerce Analytics (versión preliminar)](https://aka.ms/CommerceAnalyticsDemo).

![Resumen de Commerce Analytics (versión preliminar)](media/CommerceAnalytics_Summary.png)
![Pagos de Commerce Analytics (versión preliminar)](media/CommerceAnalytics_Payments.png)
![Actividad web de Commerce Analytics (versión preliminar)](media/CommerceAnalytics_WebActivity.png)


## <a name="commerce-analytics-preview-system-architecture"></a>Arquitectura del sistema Commerce analytics (versión preliminar)

### <a name="key-components"></a>Componentes clave

Commerce analytics (versión preliminar) consta de los siguientes componentes clave:

- Informes Power BI interactivos listos para usar
- Vistas SQL en Azure Synapse Analytics
- Datos de entidad y ontología en Azure Data Lake
- Datos sin procesar en Data Lake

![Componentes clave de la arquitectura del sistema Commerce analytics](media/CommerceAnalyticsArchitecture_v2.png)

### <a name="data-flow"></a>Flujo de datos

#### <a name="step-1-data-generation"></a>Paso 1: generación de datos

Los datos se originan como datos transaccionales o datos de comportamiento desde una de las siguientes fuentes:

- Un asociado del centro de llamadas utiliza el cliente de Commerce HQ para procesar pedidos de ventas.
- Un cajero en el punto de venta (POS) procesa transacciones de ventas.
- Se crean ventas en aplicaciones personalizadas utilizando Headless Commerce (Commerce Scale Unit).
- Un comprador de comercio electrónico navega por su sitio web de comercio electrónico.
- Un comprador de comercio electrónico realiza un pedido en su sitio web de comercio electrónico.
- Otros sistemas producen datos , como Dynamics 365 Connected Spaces.

#### <a name="step-2-ingestion-and-pre-processing"></a>Paso 2: Ingestión y preprocesamiento

Los datos transaccionales van a Commerce HQ directamente (en el caso de pedidos que se capturan directamente en el cliente de Commerce HQ) o a través de Commerce Scale Unit (en el caso de pedidos que se capturan en el PDV, en comercio electrónico o en clientes personalizados que utilizan Headless Commerce).

La característica Exportar a Data Lake se utiliza para copiar los datos transaccionales a su lago de datos como datos sin procesar. En el lago de datos, los datos sin procesar se almacenan en la carpeta Tablas.

Los datos de actividad web de comercio electrónico se envían directamente al lago de datos. Los datos producidos por otros sistemas, como Dynamics 365 Connected Spaces, son enviados directamente al lago de datos por esos sistemas.

#### <a name="step-3-transformation-and-aggregation"></a>Paso 3: Transformación y agregación

Una vez que los datos sin procesar están en su lago de datos, el servicio Commerce analytics los lee, transforma, agrega y vuelve a escribir en el lago de datos en forma de entidades lógicas (en la carpeta Entidades) y métricas agregadas (en la carpeta Ontologías).

#### <a name="step-4-querying"></a>Paso 4: consulta

Azure Synapse Analytics se utiliza para consultar datos en su lago de datos a través de una interfaz de Transact-SQL (T-SQL). Esta interfaz incluye vistas SQL. Las vistas SQL permiten la consulta federada de datos en el lago de datos, ya sea directamente a través de un cliente T-SQL (para análisis ad-hoc) o mediante una herramienta de visualización como Power BI.

#### <a name="step-5-modeling-and-serving"></a>Paso 5: modelar y servir

Datos consultados por Azure Synapse Analytics pasan al modelo semántico de Power BI. Dependiendo del tipo de datos, se importan periódicamente en la memoria en Power BI o se consultan directamente en tiempo de ejecución.

Finalmente, los datos se representan en elementos visuales de Power BI, para que los usuarios puedan verlos e interactuar con ellos.

## <a name="commerce-analytics-preview-functional-overview"></a>Descripción general funcional de Commerce analytics (versión preliminar)

### <a name="summary"></a>Resumen

La aplicación de plantillas Commerce Analytics incluye las siguientes páginas de informes principales:

1. [Filtros de nivel superior](#TopLevelFilters)
2. [Productos](#ProductsPage)
3. [Clientes](#CustomersPage)
4. [Canales](#ChannelsPage)
5. [Ventas](#SalesPage)
6. [Márgenes](#MarginsPage)
7. [Devoluciones](#ReturnsPage)
8. [Descuentos](#DiscountsPage)
9. [Pagos](#PaymentsPage)
10. [Clientes](#CustomersPage)
11. [Comparación](#ComparisonPage)
12. [Actividad Web](#WebActivityPage)
13. [Actividad web: filtro de nivel superior](#WebActivityTopLevelFilters)

####  <a name="top-level-filters"></a><a name="TopLevelFilters"></a> Filtros de nivel superior

- Configuración de fecha

    - Año
    - Trimestre
    - Mes
    - Semana
    - Día

- Configuración del canal

    - Entidad jurídica
    - Tipo de canal
    - Tipo de cliente
    - Tipo de venta
    - Canal
    - Jerarquía organizativa

- Configuración de producto

    - Jerarquía de categoría
    - Categoría

####  <a name="products"></a><a name="ProductsPage"></a> Productos

- Ventas
- Margen
- Devoluciones

####  <a name="customers"></a><a name="CustomersPage"></a> Clientes

- Ventas
- Margen
- Devoluciones

#### <a name="channels"></a><a name="ChannelsPage"></a> Canales

- Ventas
- Margen
- Devoluciones

### <a name="sales"></a>Ventas <a name="SalesPage"></a>

- Por ubicación de entrega
- Por canal/tienda/terminal
- Por empleado
- Por fecha
- Por hora
- Por categoría de producto

### <a name="margins"></a><a name="MarginsPage"></a> Márgenes

- Por ubicación de entrega
- Producto derivado
- Por fecha

### <a name="returns"></a><a name="ReturnsPage"></a> Devoluciones

- Devolución por importe

    - Por tienda
    - Producto derivado
    - Por fecha

- Devolución por transacción

    - Por tienda
    - Producto derivado
    - Por fecha

### <a name="discounts"></a><a name="DiscountsPage"></a> Descuentos

- Por tienda
- Producto derivado
- Por fecha
- Descomposición

    - Entidad jurídica
    - Almacén
    - Tipo de descuento
    - Nombre del descuento
    - Producto

### <a name="payments"></a><a name="PaymentsPage"></a> Pagos

- Por canal/terminal
- Por método/tipo de pago
- Por fecha
- Descomposición

    - Entidad jurídica
    - Tipo de canal
    - Almacén
    - Terminal
    - Método de pago

### <a name="customers"></a><a name="CustomersPage"></a> Clientes

- Valor de duración (LTV)

    El LTV se calcula en función de la cantidad total que gasta un cliente en todos los canales de venta de Dynamics 365 Commerce (incluidos PDV, comercio electrónico y centro de llamadas).

- Recency

    La novedad se calcula en función del número de días transcurridos desde la última interacción transaccional de un cliente con la organización. Actualmente, la novedad no considera las señales de interacción no transaccional, como la actividad de navegación del comercio electrónico.

- Frecuencia

    La frecuencia se calcula en función de la interacción transaccional de un cliente con la organización. Actualmente, la frecuencia no considera las señales de interacción no transaccional, como la actividad de navegación del comercio electrónico.

- Duración de la relación

    La duración de la relación se calcula en función del número de días desde que se creó el registro del cliente en el sistema.

- Recuento de transacciones

### <a name="comparison"></a><a name="ComparisonPage"></a> Comparación

- Comparación de productos por período de tiempo

    - Ventas y diferencia de ventas
    - Margen y diferencia de margen

- Cliente por periodo de tiempo

    - Ventas y diferencia de ventas
    - Margen y diferencia de margen

### <a name="web-activity"></a><a name="WebActivityPage"></a> Actividad Web

#### <a name="top-level-filters"></a><a name="WebActivityTopLevelFilters"></a> Filtros de nivel superior

- Intervalo de fechas
- Tipo de canal
- Canal
- Jerarquía de categoría

#### <a name="acquisitions"></a>Adquisiciones

- Vistas de página

    - Por país o región
    - Producto derivado
    - Por estado de inicio de sesión del usuario
    - Por fecha

- Pedidos de comercio electrónico
- Tasa de conversión

    - Por fecha

- Embudo de conversión

    - Vista de página por tipo de página (página de inicio, página de categoría o página de detalles del producto)
    - Agregar al carro
    - Finalizar compra
    - Compra

#### <a name="sessions"></a>Sesiones

Una sesión es un episodio de la visita de un usuario a su sitio web de comercio electrónico. Una sesión se considera finalizada después de 30 minutos de inactividad o 24 horas de uso activo.

- Por país o región
- Por origen (origen de referencia externa)
- Por estado de inicio de sesión del usuario
- Recuento de sesiones

    - Por fecha
    - Por página de entrada

- Pedido por sesión

    - Por fecha

- Tasa de rebote de sesión

    Un rebote de sesión es una sesión en la que un usuario abandona inmediatamente después de visitar su sitio web de comercio electrónico. Para obtener más información, consulte [Tasa de rebote](https://en.wikipedia.org/wiki/Bounce_rate).

- Clics por sesión

#### <a name="visitors"></a>Visitantes

Un visitante anónimo en su sitio de comercio electrónico se identifica de forma única según el navegador específico y el dispositivo específico que está utilizando el usuario. Commerce analytics no rastrea visitantes anónimos en diferentes navegadores o dispositivos. Un visitante anónimo que usa el mismo navegador en el mismo dispositivo se identifica de manera única en varias sesiones de usuario, hasta que se borren los datos almacenados en caché del navegador o transcurra un período (generalmente 12 meses), lo que ocurra primero.

Si los visitantes navegan por su sitio de comercio electrónico mientras están conectados, Commerce analytics puede proporcionar información adicional sobre ellos. Esta información se basa en la relación existente que su organización tiene con los visitantes como resultado de sus compras anteriores en todos los canales de venta de Dynamics 365 Commerce (incluidos PDV, comercio electrónico y centro de llamadas). La información adicional incluye datos de novedad, duración de relación, valor de duración y frecuencia.

- Margen de visitante
- Pedidos promedio de visitantes
- Ventas promedio de visitantes
- Recuento de visitantes de comercio electrónico

    - Por fecha
    - Por ubicación

        Actualmente, Commerce analytics solo puede proporcionar granularidad a nivel de país/región para información de ubicación para visitantes de comercio electrónico.

    - Por novedad

        La novedad se calcula en función del número de días transcurridos desde la última interacción transaccional de un cliente con la organización. Actualmente, la novedad no considera las señales de interacción no transaccional, como la actividad de navegación del comercio electrónico.

    - Por duración de la relación

        La duración de la relación se calcula en función del número de días desde que se creó el registro del cliente en el sistema.

    - Por valor de duración (LTV)

        El LTV se calcula en función de la cantidad total que gasta un cliente en todos los canales de venta de Dynamics 365 Commerce (incluidos PDV, comercio electrónico y centro de llamadas).

    - Por frecuencia

        La frecuencia se calcula en función de la interacción transaccional de un cliente con la organización. Actualmente, la frecuencia no considera las señales de interacción no transaccional, como la actividad de navegación del comercio electrónico.

#### <a name="impressions"></a>Impresiones

Una impresión es una vista única de un elemento visual de producto por parte de un visitante de comercio electrónico. Por ejemplo, un visitante de comercio electrónico va a la página de inicio de su sitio web de comercio electrónico y ve un producto de esterilla de yoga en un módulo de lista **Más vendidos**. A continuación, el visitante ve el mismo producto de esterilla de yoga en un módulo de lista **Selecciones para ti**. En este caso, hay dos impresiones de producto. 

Actualmente, las impresiones se registran en las siguientes superficies:

- Listas (por ejemplo, **Recomendados**, **Más vendidos**, **Selecciones para ti** y **Tendencias**)
- Módulo de carro
- Contenedor de resultados de búsqueda
- Contenedor de resultados de búsqueda de categoría

Actualmente, los productos que se procesan en un módulo de carrusel o en imágenes personalizadas no se cuentan en las métricas relacionadas con las impresiones.

La página **Informe de impresiones** incluye las siguientes métricas:

- Recuento de impresiones

    - Por tipo y módulo de página

        El tipo de página es el tipo genérico de página que se define para cada página en su sitio web de comercio electrónico. El tipo de módulo es el tipo de módulo visual de comercio electrónico en el que se muestra el producto.

        Para ver impresiones por módulo, es posible que deba profundizar en los elementos visuales de la página y del módulo.

    - Producto derivado
    - Por estado de inicio de sesión del usuario
    - Por fecha

- Recuento de clics de impresiones

    Un clic de impresión se produce cuando un visitante de comercio electrónico selecciona un elemento visual de un producto. Por lo general, el visitante pasa a la página de detalles del producto.

- Tasa de clics (CTR) de impresiones

    El CTR se calcula como el número total de clics de impresiones dividido por el número total de impresiones.

## <a name="commerce-analytics-preview-installation"></a>Instalación de Commerce analytics (versión preliminar)

> [!NOTE]
> Commerce analytics (versión preliminar) está en versión preliminar en las regiones de Estados Unidos, Canadá, Reino Unido, Europa, Sudeste de Asia, Este de Asia, Australia y Japón. Si su entorno de Finance and Operations se encuentra en cualquiera de esas regiones, puede habilitar esta función en su entorno utilizando Microsoft Dynamics Lifecycle Services (LCS). Antes de poder utilizar esta función, consulte [Configurar la exportación a Azure Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

### <a name="enable-and-configure-commerce-analytics-preview"></a><a name="enableCommerceAnalytics"></a>Habilitar y configurar Commerce analytics (versión preliminar)

Para instalar Commerce analytics (versión preliminar), debe tener permisos para crear recursos en una suscripción de Azure. También debe tener permisos para instalar complementos en LCS. Esta es una visión general de los pasos:

1. [Envíe el formulario de admisión de versión preliminar para Commerce analytics (versión preliminar)](#joinPreview).
2. [Habilitar y configurar Exportar a Data Lake](#enableExportToDataLake).
3. [Habilitar y configurar el complemento Commerce analytics (versión preliminar)](#enableCommerceAnalyticsAddin).
4. [Generar un token de firma de acceso compartido (SAS) para su cuenta de almacenamiento](#getSASToken).
5. [Descargar los scripts de implementación para vistas de Azure Synapse](#downloadSynapseDeploymentScripts).
6. [Instalar y configurar un Azure Synapse workspace](#configureAzureSynapse).
7. [Instalar la aplicación de plantillas Power BI](#powerbi).

### <a name="submit-the-preview-intake-form-for-commerce-analytics-preview"></a><a name="joinPreview"></a>Enviar el formulario de admisión de versión preliminar para Commerce analytics (versión preliminar)

Envíe el [formulario de admisión de versión preliminar para Commerce analytics (versión preliminar)](https://forms.office.com/r/vW5VLJGXZ2). Espere hasta tres días hábiles para que se procese el formulario. Una vez procesado, se enviará un correo electrónico de confirmación a la dirección de correo electrónico que proporcionó en el formulario.

### <a name="enable-and-configure-export-to-data-lake"></a><a name="enableExportToDataLake"></a>Habilitar y configurar Exportar a Data Lake

Commerce analytics (versión preliminar) se basa en la función Exportar a Data Lake para exportar datos de la sede central de Commerce a Data Lake y mantener los datos actualizados. Antes de configurar Commerce analytics (versión preliminar), habilite y configure Exportar a Data Lake siguiendo los pasos en [Configurar la exportación a Azure Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

Mientras configura Exportar a Data Lake, tome nota de la siguiente información, ya que tendrá que ingresarla más tarde:

- <a name="keyVault"></a>El nombre del sistema de nombres de dominio (DNS) del almacén de claves y los nombres secretos donde almacena el ID de la aplicación y el secreto de la aplicación. Para obtener información, vea [Agregar secretos al almacén de claves](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#addsecrets).
- <a name="storageAccount"></a>El nombre de la cuenta de almacenamiento para la instancia de Data Lake. Para más información, vea [Crear una cuenta de Data Lake Storage (Gen2) en su suscripción](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#createsubscription).

### <a name="enable-and-configure-the-commerce-analytics-preview-add-in"></a><a name="enableCommerceAnalyticsAddin"></a>Habilitar y configurar el complemento Commerce analytics (versión preliminar)

Para instalar el complemento Commerce analytics (versión preliminar) en LCS, usted debe ser administrador de entorno en LCS para el entorno que planea usar.

Para instalar y configurar el complemento Commerce analytics (versión preliminar), siga estos pasos.

1. Inicie sesión en [LCS](https://lcs.dynamics.com/) y vaya a su entorno.
2. En la página **Entorno**, en la pestaña **Complementos de entorno**, seleccione **Instalar un nuevo complemento**.
3. En el cuadro de diálogo, seleccione **Commerce analytics (versión preliminar)**.

    Si **Commerce analytics (versión preliminar)** no aparece en la lista, asegúrese de que se ha unido al Insider Program.

4. En el cuadro de diálogo **Configurar complemento**, especifique la siguiente información.

    | Información | Origen | Valor de ejemplo |
    |---|---|---|
    | Identificación de inquilino de Azure AD para su entorno | Inicie sesión en el [Portal de Azure](https://portal.azure.com/) y abra el servicio **Azure Active Directory**. A continuación, abra la página **Propiedades** y copie el valor en el campo **ID de directorio**. | 72f988bf-0000-0000-00000-2d7cd011db47 |
    | Nombre DNS de su almacén de claves | Proporcione el [nombre DNS](#keyVault) de su almacén de claves. Debería haber anotado este valor en la sección anterior. | `https://contosod365datafeedpoc.vault.azure.net/` |
    | Secreto que contiene el ID de la aplicación | Escriba el [nombre secreto que almacena el ID de la aplicación](#keyVault). Debería haber anotado este valor en la sección anterior. | app-id |
    | Secreto que contiene el secreto de la aplicación | Escriba el [nombre secreto que almacena el secreto de la aplicación](#keyVault). Debería haber anotado este valor en la sección anterior. | app-secret |

5. Acepte los términos de la oferta seleccionando la casilla de verificación y luego seleccione **Instalar**.

    El sistema instala y configura el complemento Commerce analytics (versión preliminar) para el entorno. El proceso puede tardar unos minutos. Una vez completado, **Commerce analytics (versión preliminar)** debe figurar en la página **Entorno** y el estado debe ser **Instalado**.

### <a name="generate-a-sas-token-for-your-storage-account"></a><a name="getSASToken"></a>Genere un token SAS para su cuenta de almacenamiento

Un token SAS permite que las entidades externas accedan a su cuenta de almacenamiento y tengan un conjunto específico de privilegios durante un período de tiempo finito. Azure Synapse utilizará el token SAS para acceder a los datos subyacentes en Data Lake.

> [!NOTE]
> Debido a una limitación conocida de Commerce analytics (versión preliminar), la instancia de Azure Synapse perderá el acceso al lago de datos cuando caduque el token SAS. Por lo tanto, cuando genere el token SAS, debe establecer la fecha de vencimiento máxima que permiten las directivas de seguridad de su organización.

Siga los siguientes pasos para generar un token SAS.

1. En el Azure Portal, vaya a la [cuenta de almacenamiento](#storageAccount) que creó mientras configuraba Exportar a Data Lake.
2. En el panel izquierdo, debajo de la cuenta de almacenamiento, seleccione **Firma de acceso compartido**.
3. En la página **Opciones de SAS**, configure los siguientes campos.

    | Campo | Valor |
    |---|---|
    | Servicios permitidos | Seleccione **Blob**. |
    | Tipos de recursos permitidos | Seleccione **Servicio**, **Contenedor** y **Objeto**. |
    | Permisos permitidos | Seleccione **Leer**, **Escribir**, **Eliminar**, **Enumerar**, **Agregar** y **Crear**. |
    | Permisos de versiones de Blob | Seleccione **Habilita eliminación de versiones**. |
    | Fecha/hora de inicio y vencimiento | Establezca una fecha y hora de inicio y finalización para el token SAS según corresponda. |
    | Direcciones IP permitidas | Deje este campo en blanco. |
    | Protocolos permitidos | Seleccione **Solo HTTPS**. |
    | Nivel de enrutamiento preferido | Seleccione **Básico (predeterminado)**. |
    | Clave de firma | Seleccione **clave1** o **clave2**, según sea apropiado. |

4. Seleccione **Generar SAS y cadena de conexión**.
5. Copie el valor en el campo **Token SAS** y péguelo en un editor de texto como el Bloc de notas.

### <a name="download-the-deployment-scripts-for-azure-synapse-views"></a><a name="downloadSynapseDeploymentScripts"></a>Descargar los scripts de implementación para vistas de Azure Synapse

Para crear y publicar las vistas requeridas en un Azure Synapse workspace debe ejecutar un conjunto de scripts. Siga estos pasos para descargar los scripts.

1. En GitHub, vaya al repositorio de [microsoft/Dynamics365Commerce.Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions).
2. Descargue los scripts en su equipo local clonando el repositorio o descargándolo como un archivo zip.

### <a name="install-and-configure-an-azure-synapse-workspace"></a><a name="configureAzureSynapse"></a>Instalar y configurar un Azure Synapse workspace

Para instalar y configurar un Azure Synapse workspace, siga estos pasos.

1. Instale un Azure Synapse workspace en su suscripción de Azure. Para más información, vea [Inicio rápido: crear un espacio de trabajo de Synapse](/azure/synapse-analytics/quickstart-create-workspace).
2. En el Bloc de notas u otro editor de texto, abra el archivo de script **SetupSynapse.sql** desde la carpeta de su equipo local en el que clonó o descargó el repositorio de Dynamics365Commerce.Solutions en la sección anterior. El archivo de script estará en la carpeta /Pipeline/CommerceAnalyticsSynapse/. En el script, reemplace el texto del marcador de posición con valores como se muestra en la siguiente tabla.

    | Texto de marcador de posición | Valor de sustitución |
    |---|---|
    | placeholder_storageaccount | El nombre de la [cuenta de almacenamiento](#storageAccount) que creó mientras configuraba Exportar a Data Lake. |
    | <a name="phContainer"></a>placeholder_container | El nombre del contenedor de almacenamiento que se creó en su instancia de Data Lake después de instalar correctamente el complemento Exportar a Data Lake en LCS. Para obtener el nombre del contenedor, debe usar el Explorador de almacenamiento en Azure Portal para explorar su cuenta de almacenamiento. |
    | placeholder_sastoken | El [Token SAS](#getSASToken) que generó. Asegúrese de quitar el signo de interrogación (**?**) del comienzo del valor del token SAS. |
    | <a name="phUserPwd"></a>placeholder_password | Una contraseña segura de su elección. Tome nota de esta contraseña. Se establecerá como contraseña para la nueva cuenta **reportreadonlyuser** que crea el script. **No** ingrese la contraseña de la cuenta de **sqladminuser**. |

3. Copie el contenido actualizado del archivo de script.
4. En Azure Portal, vaya al nuevo Azure Synapse workspace. En la página **Visión general**, seleccione **Abrir Synapse Studio**.
5. En Synapse Studio, seleccione **Nuevo \> Script SQL** y pegue el contenido del archivo de script en el editor de script de SQL.
6. Asegúrese de que el campo **Usar base de datos** está configurado en **master**.
7. Seleccione **Ejecutar** y espere a que termine de ejecutarse el script. La ejecución correcta del script creará la base de datos para Commerce analytics, credenciales para acceder al lago de datos y una cuenta de usuario de solo lectura que Power BI utilizará para conectarse a la instancia de Azure Synapse.
8. En su equipo local, abra Windows PowerShell en modo de administrador y vaya a la carpeta /Pipeline/CommerceAnalyticsSynapse/ debajo de la carpeta en la que clonó o descargó el repositorio de Dynamics365Commerce.Solutions.
9. Configure la directiva de ejecución de Windows PowerShell ejecutando el siguiente comando.

    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
    ```

10. Si el módulo SQL Server PowerShell aún no está instalado, instálelo ejecutando el siguiente comando.

    ```powershell
    Install-Module sqlserver
    ```

    > [!NOTE]
    > Durante la instalación del módulo, es posible que se le solicite que instale el proveedor NuGet. En este caso, seleccione **S** para instalar el proveedor NuGet. También es posible que se le solicite que reconozca que está instalando módulos desde un repositorio que no es de confianza. En este caso, seleccione **S** para continuar con la instalación. Opcionalmente, puede ejecutar el cmdlet **Set-PSRepository** para confiar en el repositorio de **PSGallery**.

11. Publique las vistas de Azure Synapse ejecutando el siguiente comando.

    ```powershell
    .\PublishSynapseViews.ps1 -serverName SERVER_NAME -password PASSWORD -storageAccount STORAGE_ACCOUNT -containerName CONTAINER_NAME -datarootpath DATA_ROOT_PATH
    ```

    Cuando ejecute este comando, reemplace los valores de marcador de posición como se muestra en la siguiente tabla.

    | Valor de marcador de posición | Valor de sustitución |
    |---|---|
    | SERVER_NAME | El nombre del extremo de Azure Synapse Serverless SQL. Puede obtener este valor de la página **Visión general** para el Azure Synapse workspace en el portal de Azure. |
    | PASSWORD | La contraseña para la cuenta de **sqladminuser**. |
    | STORAGE_ACCOUNT | El nombre de la cuenta de almacenamiento para Data Lake. |
    | CONTAINER_NAME | El nombre del contenedor creado por la función Exportar a Data Lake. Este contenedor es el mismo contenedor que especificó como valor de [placeholder_container](#phContainer) en el paso 2. |
    | DATA_ROOT_PATH | El nombre de la carpeta debajo del contenedor que contiene todos los datos. |

    > [!NOTE]
    > Puede encontrar el nombre de la cuenta de almacenamiento, el nombre del contenedor y la ruta de la raíz de datos mediante el explorador de Azure Storage y su cuenta de almacenamiento de Data Lake en Azure Portal.

12. Espere a que termine de ejecutarse el script. La ejecución exitosa del script creará vistas SQL en la instanacia de Azure Synapse Serverless SQL.

### <a name="install-the-power-bi-template-app"></a><a name="powerbi"></a>Instalar la aplicación de plantillas Power BI

Para instalar la aplicación de plantillas Power BI para Commerce analytics (versión preliminar), siga estos pasos.

1. Inicie sesión en el [portal de Power BI](https://powerbi.microsoft.com/) mediante el ID de su organización.
2. Instale la aplicación de plantillas Power BI de Commerce analytics (versión preliminar) yendo a [https://aka.ms/cdireport-installapp](https://aka.ms/cdireport-installapp). Es posible que reciba una advertencia que indique que la aplicación no figura en AppSource. Seleccione **Instalar**.
3. Si está instalando la aplicación por primera vez, continúe con el paso 5. Si ha instalado esta aplicación antes, se muestran las siguientes opciones para actualizar la aplicación:

    - **Actualizar el espacio de trabajo y la aplicación** - Actualice la aplicación de plantillas existente y sobrescriba la configuración de aplicación existente, como el nombre de la instancia de la aplicación y las configuraciones de permisos.
    - **Actualizar solo el contenido del espacio de trabajo sin actualizar la aplicación** - Actualice la aplicación de plantilla existente, pero mantenga la configuración de la aplicación existente. *Esta es la opción recomendada para las actualizaciones de la aplicación.*
    - **Instalar otra copia de la aplicación en un nuevo espacio de trabajo** - Cree un nuevo espacio de trabajo y luego cree en él una copia de la aplicación de plantillas existente. El espacio de trabajo existente se dejará intacto.

4. Seleccione una de las opciones de actualización y luego seleccione **Instalar**.
5. Abra la aplicación instalada seleccionando **Aplicaciones** en el panel izquierdo y luego seleccionando la aplicación.
6. Conecte la aplicación a su origen de datos seleccionando **Conectar**. Si ha instalado la aplicación antes, seleccione el enlace **Conectar sus datos** en la barra de mensajes amarilla.
7. Establezca los campos siguientes.

    | Campo | Valor |
    |---|---|
    | Servidor | Ingrese el nombre del extremo Azure Synapse Serverless SQL que creó en la sección anterior. Puede obtener este valor de la página **Visión general** para el Azure Synapse workspace en el portal de Azure. |
    | Base de datos | Escriba **CommerceAnalytics**. |
    | Idioma | Seleccione un valor de la lista. Este campo se utiliza para nombres de categorías y productos localizados. El valor distingue entre mayúsculas y minúsculas. |
    | Intervalo de fechas | Seleccione un valor de la lista. Los datos para el número seleccionado de meses se importarán en el conjunto de datos de Power BI. El valor que seleccione afecta al tamaño del conjunto de datos y el tiempo necesario para la sincronización. |

8. Seleccione **Siguiente**. Se le pedirá que ingrese las credenciales para conectarse a la base de datos SQL de Azure Synapse. Configure los campos como se describe en la tabla siguiente.

    | Campo | Valor |
    |---|---|
    | Método de autenticación | Seleccione **Básico**. |
    | Nombre de usuario | Escriba **reportreadonlyuser**. |
    | Contraseña | Ingrese el valor que reemplazó el marcador de posición [placeholder_password](#phUserPwd) dentro del script SetupSynapse.sql. Esta contraseña es la contraseña para la cuenta **reportreadonlyuser**. |

9. Seleccione **Iniciar sesión y conectar**.
10. Espere hasta que el conjunto de datos se actualice correctamente. Luego seleccione el botón **Editar aplicación** para abrir el espacio de trabajo de la aplicación, donde puede ver el estado de actualización del conjunto de datos. En el espacio de trabajo de la aplicación, también puede configurar opcionalmente programas de actualización automática para su conjunto de datos, administrar permisos y cambiar el nombre de la instancia de la aplicación.

### <a name="privacy"></a><a name="privacy"></a>Privacidad

Su privacidad es importante para nosotros. Para obtener más información, lea nuestra [Declaración de privacidad](https://go.microsoft.com/fwlink/?LinkId=521839).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
