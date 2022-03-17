---
title: Commerce analytics (versión preliminar)
description: Este tema explica cómo instalar y utilizar la capacidad de análisis en Microsoft Dynamics 365 Commerce.
author: AamirAllaq
ms.date: 02/24/2022
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: aamiral
ms.search.validFrom: 2021-11-12
ms.openlocfilehash: 7e3721421e15bc3e5937691cdbaee51e4d3cdd17
ms.sourcegitcommit: d2e5d38ed1550287b12c90331fc4136ed546b14c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8349752"
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

#### <a name="top-level-filters"></a><a name="TopLevelFilters"></a> Filtros de nivel superior

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

#### <a name="products"></a><a name="ProductsPage"></a> Productos

- Ventas
- Margen
- Devoluciones

#### <a name="customers"></a><a name="CustomersPage"></a> Clientes

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
> Commerce analytics (versión preliminar) está en versión preliminar en las regiones de Estados Unidos, Canadá, Reino Unido, Europa, Sudeste de Asia, Este de Asia, Australia y Japón. Si su entorno de finanzas y operaciones se encuentra en cualquiera de esas regiones, puede habilitar esta característica en su entorno utilizando Microsoft Dynamics Lifecycle Services (LCS). Antes de poder utilizar esta función, consulte [Configurar la exportación a Azure Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

### <a name="enable-and-configure-commerce-analytics-preview"></a><a name="enableCommerceAnalytics"></a>Habilitar y configurar Commerce analytics (versión preliminar)

Para instalar Commerce analytics (versión preliminar), debe tener permisos para crear recursos en una suscripción de Azure. También debe tener permisos para instalar complementos en LCS. 

Para habilitar y configurar Commerce analytics (versión preliminar), siga estos pasos.

1. [Habilitar y configurar el complemento Exportar a Data Lake](#enableExportToDataLake).
1. [Instalar y configurar un Azure Synapse workspace](#configureAzureSynapse).
1. [Agregar secretos al almacén de claves](#addSecrets).
1. [Habilitar y configurar el complemento Commerce analytics (versión preliminar)](#enableCommerceAnalyticsAddin).
1. [Instalar la aplicación de plantillas Power BI](#powerbi).

### <a name="enable-and-configure-the-export-to-data-lake-add-in"></a><a name="enableExportToDataLake"></a>Habilitar y configurar el complemento Export a Data Lake

> [!IMPORTANT]
> Cuando configure el complemento Exportar a Data Lake, borre la casilla **Cambios de datos en tiempo real** en la página de configuración del complemento Exportar a Data Lake para asegurarse de que los cambios de datos en tiempo real no estén habilitados. La característica **Cambios de datos en tiempo real** está en versión preliminar y actualmente no es compatible con Commerce Analytics. Si habilita la característica, Commerce Analytics no podrá procesar sus datos en el lago de datos y la mayoría de sus informes de Power BI no mostrarán datos.

Commerce analytics (versión preliminar) se basa en la función Exportar a Data Lake para exportar datos de la sede central de Commerce a Data Lake y mantener los datos actualizados. Antes de configurar Commerce analytics (versión preliminar), habilite y configure Exportar a Data Lake siguiendo los pasos en [Configurar la exportación a Azure Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

Mientras configura el complemento Exportar a Data Lake, tome nota de la siguiente información, ya que tendrá que introducirla más tarde:

- <a name="keyVault"></a>El nombre del Sistema de nombres de dominio (DNS) del almacén de claves que proporcionó.
- Los nombres de secretos que proporcionó y que contienen el id. de la aplicación y el secreto de la aplicación. Para obtener información, vea [Agregar secretos al almacén de claves](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#addsecrets).

### <a name="install-and-configure-an-azure-synapse-workspace"></a><a name="configureAzureSynapse"></a>Instalar y configurar un Azure Synapse workspace

Commerce Analytics (versión preliminar) requiere que se aprovisione Synapse SQL a petición en su Azure Synapse workspace. Para instalar y configurar un Azure Synapse workspace, siga estos pasos.

1. Instale un Azure Synapse workspace en su suscripción de Azure. Para más información, vea [Inicio rápido: crear un espacio de trabajo de Synapse](/azure/synapse-analytics/quickstart-create-workspace).
1. <a name="serverlessep"></a>Después de aprovisionar el espacio de trabajo, abra la página de información general de recursos y tome nota del valor de **Extremo de Serverless SQL**. Tendrá que almacenar este valor en el almacén de claves en la siguiente sección.
1. En la página de resumen, seleccione el vínculo **Abrir Synapse Studio** para abrir Azure Synapse Studio para su espacio de trabajo.
1. Seleccione **Administrar** en el menú izquierdo. Para ver los nombres de los menús, es posible que deba seleccionar el vínculo para expandir en el menú de la izquierda.
1. Debajo de **Grupo de seguridad**, seleccione **Control de acceso**. 
1. Seleccione **Agregar**.
1. En el panel **Agregar asignación de roles**, establezca las opciones como se describe en la siguiente tabla.

    | Opción | Valor |
    |--------|-------|
    | Ámbito | Seleccione **Espacio de trabajo**. |
    | Rol | Seleccione **Administrador de Synapse SQL**.|
    | Seleccionar usuario | Busque el nombre de la aplicación que [creó durante la instalación del complemento Exportar a Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#createapplication). Cuando la aplicación aparezca en los resultados de la búsqueda, selecciónela. La aplicación ahora aparecerá en la sección **Usuarios, grupos o entidades de servicio seleccionados**. |

1. Seleccione **Aplicar** para completar la asignación de roles. La aplicación tiene concedidos privilegios de administrador de Synapse SQL. Por lo tanto, puede crear las vistas requeridas durante la configuración del complemento LCS de Commerce Analytics (versión preliminar).

### <a name="add-secrets-to-the-key-vault"></a><a name="addSecrets"></a>Agregar secretos al almacén de claves

En el mismo [almacén de claves](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#createkeyvault) que usó mientras configuraba el complemento Exportar a Data Lake, debe agregar los secretos que se muestran en la siguiente tabla. Para cada secreto, debe proporcionar un nombre de secreto y el valor especificado.

| Nombre de secreto sugerido | Valor secreto | Valor de secreto de ejemplo |
|---------|---------|---------|
| synapse-sql-server | El valor del extremo de serverless SQL que anotó mientras [configuró el Azure Synapse workspace](#serverlessep). | `test-ondemand.sql.azuresynapse.net` |
| <a name="roUser"></a>readonly-sql-pwd | La contraseña que se establecerá para el usuario de solo lectura de SQL. El informe de Power BI usará esta contraseña para conectarse a Serverless SQL. Para establecer la contraseña, siga las directivas de contraseña de su organización. | |

### <a name="enable-and-configure-the-commerce-analytics-preview-add-in"></a><a name="enableCommerceAnalyticsAddin"></a>Habilitar y configurar el complemento Commerce analytics (versión preliminar)

Para instalar el complemento Commerce analytics (versión preliminar) en LCS, usted debe ser administrador de entorno en LCS para el entorno que planea usar.

Para instalar y configurar el complemento Commerce analytics (versión preliminar), siga estos pasos.

1. Inicie sesión en [LCS](https://lcs.dynamics.com/) y vaya a su entorno.
2. En la página **Entorno**, en la pestaña **Complementos de entorno**, seleccione **Instalar un nuevo complemento**.
3. En el cuadro de diálogo, seleccione **Commerce analytics (versión preliminar)**.
4. En el cuadro de diálogo **Configurar complemento**, especifique la siguiente información.

    | Información | Origen | Valor de ejemplo |
    |---|---|---|
    | Id. de suscriptor de Azure Active Directory (Azure AD) | Inicie sesión en el [Portal de Azure](https://portal.azure.com/) y abra el servicio **Azure Active Directory**. A continuación, abra la página **Propiedades** y copie el valor en el campo **Id. de suscriptor**. | `72f988bf-0000-0000-00000-2d7cd011db47` |
    | Nombre DNS de su almacén de claves de Azure | Proporcione el nombre DNS de su almacén de claves. Debería haber tomado nota de este valor mientras [configuró el complemento Exportar a Data Lake](#keyVault). | `https://contosod365datafeedpoc.vault.azure.net/` |
    | Nombre de secreto que contiene el id. de la aplicación | Escriba el nombre secreto que almacena el ID de la aplicación. Debería haber tomado nota de este valor mientras [configuró el complemento Exportar a Data Lake](#keyVault). | `app-id` |
    | Nombre de secreto que contiene el secreto de la aplicación | Escriba el nombre secreto que almacena el secreto de la aplicación. Debería haber tomado nota de este valor mientras [configuró el complemento Exportar a Data Lake](#keyVault). | `app-secret` |
    | Nombre de secreto que contiene el extremo de Serverless SQL para Azure Synapse | Escriba el nombre de secreto que almacena el extremo de Serverless SQL. Debería haber creado el secreto mientras [agregó secretos al valor de clave](#addSecrets). | `synapse-sql-server` |
    | Nombre de secreto que contiene la contraseña que se establecerá para los usuarios de solo lectura de SQL en Azure Synapse | Introduzca el nombre de secreto que almacena la contraseña que se establecerá para el usuario de solo lectura de Serverless SQL. Este usuario se creará para usted y debe usarse en el informe de Power BI para conectarse a Serverless SQL server. Debería haber creado el secreto mientras [agregó secretos al valor de clave](#addSecrets). | `readonly-sql-pwd` |

1. Acepte los términos de la oferta seleccionando la casilla de verificación y luego seleccione **Instalar**.

    El sistema instala y configura el complemento Commerce analytics (versión preliminar) para el entorno. El proceso puede tardar unos minutos. Una vez completado, **Commerce analytics (versión preliminar)** debe figurar en la página **Entorno** y el estado debe ser **Instalado**.

### <a name="install-the-power-bi-template-app"></a><a name="powerbi"></a>Instalar la aplicación de plantillas Power BI

Para instalar la aplicación de plantillas Power BI para Commerce analytics (versión preliminar), siga estos pasos.

1. Inicie sesión en el [portal de Power BI](https://powerbi.microsoft.com/) mediante el ID de su organización.
1. Instale la aplicación de plantillas Power BI de Commerce analytics (versión preliminar) yendo a [https://aka.ms/cdireport-installapp](https://aka.ms/cdireport-installapp). Alternativamente, visite la [página de AppSource para Dynamics 365 Commerce Analytics](https://appsource.microsoft.com/product/power-bi/dynamics-365-commerce.dydnamics-365-commerce-analytics) y seleccione **Obtener ahora**.
1. Si está instalando la aplicación por primera vez, continúe con el paso 5. Si la ha instalado antes, las siguientes opciones para actualizar la aplicación son aplicables:

    - **Actualizar el espacio de trabajo y la aplicación** - Actualice la aplicación de plantillas existente y sobrescriba la configuración de aplicación existente, como el nombre de la instancia de la aplicación y las configuraciones de permisos.
    - **Actualizar solo el contenido del espacio de trabajo sin actualizar la aplicación** - Actualice la aplicación de plantilla existente, pero mantenga la configuración de la aplicación existente. *Esta es la opción recomendada para las actualizaciones de la aplicación.*
    - **Instalar otra copia de la aplicación en un nuevo espacio de trabajo** - Cree un nuevo espacio de trabajo y luego cree en él una copia de la aplicación de plantillas existente. El espacio de trabajo existente se dejará intacto.

1. Seleccione una de las opciones de actualización y luego seleccione **Instalar**.
1. Abra la aplicación instalada seleccionando **Aplicaciones** en el panel izquierdo y luego seleccionando la aplicación.
1. Conecte la aplicación a su origen de datos seleccionando **Conectar**. Si ha instalado la aplicación antes, seleccione el enlace **Conectar sus datos** en la barra de mensajes amarilla.
1. Establezca los campos siguientes.

    | Campo | Valor |
    |---|---|
    | Servidor | Especifique el extremo de Serverless SQL que anotó después de [crear el Azure Synapse workspace](#serverlessep). |
    | Base de datos | Escriba **CommerceAnalytics**. |
    | Idioma | Seleccione un valor de la lista. Este campo se utiliza para nombres de categorías y productos localizados. El valor distingue entre mayúsculas y minúsculas. |
    | Intervalo de fechas | Seleccione un valor de la lista. Los datos para el número seleccionado de meses se importarán en el conjunto de datos de Power BI. El valor que seleccione afecta al tamaño del conjunto de datos y el tiempo necesario para la sincronización. |

1. Seleccione **Siguiente**. Cuando se le solicite que introduzca las credenciales para conectarse a la base de datos SQL de Azure Synapse, establezca los valores de campo como se muestran en la siguiente tabla.

    | Campo | Valor |
    |---|---|
    | Método de autenticación | Seleccione **Básico**. |
    | Nombre de usuario | Escriba **reportreadonlyuser**. |
    | Contraseña | Escriba la contraseña que [almacenó para el usuario de solo lectura de SQL en el almacén de claves](#roUser). |

1. Seleccione **Iniciar sesión y conectar**.
1. Espere hasta que el conjunto de datos se haya actualizado correctamente. Luego seleccione **Editar aplicación** para abrir el espacio de trabajo de la aplicación, donde puede ver el estado de actualización del conjunto de datos. En el espacio de trabajo de la aplicación, también puede configurar opcionalmente programas de actualización automática para su conjunto de datos, administrar permisos y cambiar el nombre de la instancia de la aplicación.

### <a name="privacy"></a><a name="privacy"></a>Privacidad

Su privacidad es importante para nosotros. Para obtener más información, lea nuestra [Declaración de privacidad](https://go.microsoft.com/fwlink/?LinkId=521839).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
