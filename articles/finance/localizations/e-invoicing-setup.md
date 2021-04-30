---
title: Configurar la facturación electrónica
description: Este tema explica cómo configurar la facturación electrónica en Microsoft Dynamics 365 Finance y Dynamics 365 Supply Chain Management.
author: gionoder
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 9aac18155fbc7a87554ac0521cd9f40d11eba9e2
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890840"
---
# <a name="set-up-electronic-invoicing"></a>Configurar la facturación electrónica

[!include [banner](../includes/banner.md)]


La configuración de la característica de facturación electrónica es el proceso de crear la configuración requerida a través del ambiente de Regulatory Configuration Services (RCS) y publicar esa configuración en el servidor de facturación electrónica. La configuración le permite crear las reglas configurables que permiten que la facturación electrónica utilice un protocolo seguro a través de Internet para comunicarse e intercambiar datos con una entidad de terceros a través de servicios web.

La capacidad de configuración se basa en la configuración del formato de informes electrónicos (ER) como un medio para crear contenido que se envía y recibe a través de archivos digitales. También se basa en la orquestación de acciones de comunicación para enviar solicitudes y recibir respuestas de servicios web de terceros sin necesidad de escribir código.

## <a name="overview"></a>Información general

"Característica de facturación electrónica" es el nombre genérico del recurso que se configura y publica para usar el servidor de facturación electrónica. La configuración de la característica combina, entre otras cosas, el uso de formatos de configuración de informes electrónicos (ER) para crear archivos de importación y exportación configurables, y el uso de acciones y flujos de acción para permitir la creación de reglas configurables para enviar solicitudes, importar respuestas y analizar el contenido de la respuesta.

La siguiente ilustración muestra los componentes principales de una función de facturación electrónica.

![Descripción general de la característica de facturación electrónica](media/e-Invoicing-services-feature-setup-Overview-e-Invoicing-feature.png)

Debido a las variaciones en los formatos de factura y los flujos de acción, la configuración de la función puede variar según el país o la región, o según los requisitos comerciales.

## <a name="set-up-the-electronic-invoicing-feature"></a>Configurar la característica de facturación electrónica

El proceso de configuración debe completarse en su entorno RCS. Siga estos pasos para crear una nueva característica de facturación electrónica.

1. Inicie sesión en su entorno RCS.
2. En el espacio de trabajo **Características de globalización**, en la sección **Características**, seleccione el mosaico **Facturación electrónica**.
3. En la página **Características de facturación electrónica**, seleccione **Importar** para importar la configuración del modelo de datos de ER desde el repositorio global.
4. Seleccione **Agregar** para crear una característica de facturación electrónica. Puede crear la característica desde cero o derivarla de una función adicional de facturación electrónica existente.

    ![Agregar una característica de facturación electrónica](media/e-Invoicing-services-feature-setup-Select-Add-e-Invoicing-feature.png)

> [!NOTE]
> Cuando crea una nueva característica de facturación electrónica, tiene un número de versión y su estado predeterminado se establece en **Borrador**.

### <a name="configurations"></a>Configuraciones

Las configuraciones contienen las configuraciones de formato ER que se requieren para las transformaciones y para crear los archivos que se intercambiarán durante la comunicación con servicios web de terceros. Una función de facturación electrónica puede tener tantas configuraciones de formato de archivo ER como sean necesarias, según la especificación técnica de integración proporcionada por el proveedor de servicios web.

Siga estos pasos para agregar formatos ER a la función de facturación electrónica.

1. En la página **Funciones de facturación electrónica**, en la pestaña **Configuraciones**, seleccione **Agregar** para agregar configuraciones de formato de archivo ER para la función de facturación electrónica.

    ![Agregar configuraciones de característica de facturación electrónica](media/e-Invoicing-services-feature-setup-Select-Add-e-Invoicing-feature-Configurations.png)

    > [!NOTE]
    > Cuando crea una función de facturación electrónica desde cero, debe agregar manualmente todas las configuraciones de formato de archivo ER. Cuando obtiene una función de facturación electrónica de una función existente, las configuraciones de formato de archivo ER se crean automáticamente, porque se heredan de la función de facturación electrónica original.

2. Seleccione **Editar** para abrir la página **Diseñador de formatos**, donde puede editar la configuración del formato de archivo ER.

    ![Editar configuraciones de característica de facturación electrónica](media/e-Invoicing-services-feature-setup-Select-Edit-e-Invoicing-feature-Configurations.png)

    > [!NOTE]
    > Mientras edita el formato, el estado de la versión de configuración se establece en **Borrador**.

3. Utilice la página **Diseñador de formatos** para cambiar la configuración del formato de archivo. Para obtener más información, consulte [Crear configuraciones de documentos electrónicos](../../fin-ops-core/dev-itpro/analytics/electronic-reporting-configuration.md).

    ![Página de diseñador de formato](media/e-Invoicing-services-feature-setup-ER-Format-designer.png)

### <a name="feature-setups"></a>Configuraciones de funciones

Las configuraciones de funciones encapsulan las reglas de comunicación y seguridad con un servicio web de terceros. Una función de facturación electrónica puede tener tantas configuraciones de características como sean necesarias, según la regla empresarial que desee lograr.

Siga estos pasos para agregar configuraciones de característica a la función de facturación electrónica.

1. En la página **Funciones de facturación electrónica**, en la pestaña **Configuraciones**, seleccione **Agregar** para agregar configuraciones de característica para la función de facturación electrónica.

    ![Agregar configuraciones de característica de facturación electrónica](media/e-Invoicing-services-feature-setup-Select-Add-e-Invoicing-feature-Setups.png)

    > [!NOTE]
    > Cuando crea una función de facturación electrónica desde cero, debe agregar manualmente todas las configuraciones de característica que necesita. Cuando obtiene una función de facturación electrónica de una función existente, todas las configuraciones de característica se crean automáticamente, porque se heredan de la función de facturación electrónica original.

2. Seleccione **Editar** para editar la configuración de la versión de la función.

    ![Editar configuraciones de característica de facturación electrónica](media/e-Invoicing-services-feature-setup-Select-Edit-e-Invoicing-feature-Setups.png)

3. Use la página **Configuración de la versión de función** para configurar acciones, reglas de aplicabilidad y variables.

    ![Acciones, reglas de aplicabilidad y variables](media/e-Invoicing-services-feature-setup-View-Actions-Applicability-Rules-Variables.png)

### <a name="actions"></a>Acciones

Las acciones son una lista predefinida de operaciones que se ejecutan en orden secuencial. Esta lista representa el desglose de los pasos necesarios para la ejecución completa de la función de facturación electrónica. Las acciones pueden encapsular, en la misma facturación electrónica, la comunicación en ambas direcciones: enviar una solicitud de destino, recibir una respuesta y analizar su contenido.

Cada acción contiene una lista predefinida de parámetros que son necesarios para que la acción logre su propósito. Opcionalmente, se pueden proporcionar parámetros adicionales.

#### <a name="actions-fasttab"></a>Ficha desplegable Acciones

En la página **Configuración de versiones de funciones**, en la pestaña **Acciones**, en la ficha desplegable **Acciones**, siga uno o ambos de estos pasos para administrar acciones:

- Seleccione **Nuevo** o **Eliminar** para agregar nuevas acciones o eliminar acciones existentes.
- Seleccione **Arriba** o **Abajo** para mover las acciones seleccionadas hacia arriba o hacia abajo en la cuadrícula y, por lo tanto, cambiar el orden en el que se ejecutan. Las acciones se ejecutan en el orden en que aparecen en la cuadrícula, de arriba a abajo.

![Gestionar acciones](media/e-Invoicing-services-feature-setup-Manage-Actions.png)

En la tabla siguiente se describen los campos disponibles en la ficha desplegable **Acciones**.

| Campo        | Descripción |
|--------------|-------------|
| Acción       | Hay ocho acciones predefinidas:<ul><li><strong>Firmar documento</strong></li><li><strong>FileStoreActionName</strong></li><li><strong>Transformar documento</strong></li><li><strong>Respuesta del proceso</strong></li><li><strong>Llamar al servicio web REST</strong></li><li><strong>Llamar al servicio PAC mexicano</strong></li><li><strong>Llamar al servicio SEFAZ brasileño</strong></li><li><strong>Llamar al servicio SDI italiano</strong></li></ul> |
| Nombre de acción  | El nombre de la acción y su orden de ejecución. |
| Descripción  | Una descripción de la acción. |
| Habilitar reintento | Una casilla de verificación seleccionada indica que la acción se puede reintentar si el intento anterior no tiene éxito. |
| Reintentar acción | En caso de un reintento, la acción desde la que se inicia el reintento. Luego, el reintento finaliza en la acción actual (reintento incluido). Para acciones que los tienen, los parámetros **Retroceso mínimo** y **Retroceso máximo** especifican el número mínimo y máximo de reintentos. |

#### <a name="parameters-fasttab"></a>Ficha desplegable Parámetros

La ficha desplegable **Parámetros** enumera los parámetros de la acción que se selecciona en la ficha desplegable **Acciones**.

![Ficha desplegable Parámetros](media/e-Invoicing-services-feature-setup-View-Actions-Parameters.png)

En la tabla siguiente se describen los campos disponibles en la ficha desplegable **Parámetros**.

| Campo       | Descripción |
|-------------|-------------|
| Nombre        | Una lista predefinida de parámetros. Para obtener más información, consulte la sección [Lista de parámetros por acción](#list-of-parameters-by-action). |
| Descripción | Una descripción del parámetro. |
| Valor       | El valor del parámetro. |

#### <a name="list-of-parameters-by-action"></a>Lista de parámetros por acción

Los parámetros disponibles varían, dependiendo de la acción que se seleccione en la ficha desplegable **Comportamiento**.

###### <a name="action-sign-document"></a>Acción: Firmar documento

| Parámetro                             | Descripción |
|---------------------------------------|-------------|
| Archivo de entrada                            | El archivo de documento XML de entrada que debe firmarse mediante una firma electrónica. |
| Nombre de certificado                      | El nombre del certificado almacenado. |
| Tipo de firma                        | Tipo de firma que usar. |
| Nombre del método de firma                 | El nombre del método de firma que se utiliza para generar una firma electrónica. |
| Nombre del método de resumen                    | El método de resumen que se utiliza para generar una cadena de resumen en la firma digital. |
| Nombre del método de canonización          | El método de canonización usado para calcular el hash de firma. |
| Nombre del atributo de referencia              | El nombre del atributo que indica dónde debe insertarse el ID de referencia en el elemento de firma. |
| Nombre del elemento a firmar               | El nombre del elemento XML del documento que debe firmarse mediante una firma electrónica. Si no se especifica ningún elemento, se firma la raíz del documento. |
| Nombre del elemento para insertar firma   | El nombre del elemento XML donde se debe insertar una firma digital generada. Si no se especifica ningún elemento, la firma se inserta en la raíz del documento. |
| Archivo XLST con transformación de resumen       | El archivo Extensible Stylesheet Language Transformations (XSLT) que contiene reglas de transformación de resumen para generar la cadena de resumen para una firma electrónica. |
| Ruta para insertar cadena de resumen          | La ruta, en formato **\<elementName\>.\<Attribute.Path\>**, de la ubicación donde se debe insertar la cadena de resumen generada. |
| Ubicación del número de certificado           | El nombre del elemento y atributo donde se debe colocar el número de certificado. |
| Ubicación de los datos del certificado          | El nombre del elemento y atributo donde se deben insertar los datos del certificado (base64). |
| El número de certificado está en formato ASCII | Valor que especifica si el número del certificado está codificado en formato ASCII. |

###### <a name="action-filestoreactionname"></a>Acción: FileStoreActionName

| Parámetro  | Descripción |
|------------|-------------|
| Archivo de entrada | El archivo de entrada para almacenar. |

###### <a name="action-transform-document"></a>Acción: Transformar documento

| Parámetro                       | Descripción |
|---------------------------------|-------------|
| Archivo de entrada                      | El archivo de origen que proporciona los datos que se deben ejecutar para la acción. |
| Dirección                       | Un valor que indica si se debe utilizar el formato de importación o el formato de exportación. |
| Id. de configuración                | El formato que se debe ejecutar. |
| Versión de configuración           | Si no se especifica una versión de configuración, se utilizará la versión más reciente. |
| Punto de integración de la configuración | El archivo de origen que proporciona datos al tiempo de ejecución de informes. |

###### <a name="action-process-response"></a>Acción: respuesta del proceso

| Parámetro                    | Descripción |
|------------------------------|-------------|
| Archivo de entrada                   | La respuesta a analizar. |
| Notificando lista de la configuración | Una lista de configuraciones que se usa para analizar las respuestas. |

###### <a name="action-call-rest-web-service"></a>Acción: Llamar al servicio web REST

| Parámetro                   | Descripción |
|-----------------------------|-------------|
| URL de servicio Web             | La URL a la que enviar solicitudes. |
| Tiempo de espera de solicitud web         | La cantidad máxima de tiempo (en milisegundos) para esperar una respuesta del servicio web. |
| Solicitar tipo de operación      | El tipo de operación de solicitud HTTP (por ejemplo, **OBTENER**, **ENVIAR** o **ELIMINAR**). |
| Nombres de certificado           | Nombres de certificado. |
| Codificación del cuerpo de respuesta      | La codificación esperada del cuerpo de respuesta HTTP, para que pueda decodificarse correctamente. |
| Tipo de contenido de solicitud HTTP   | La entrada del encabezado del tipo de contenido de la solicitud HTTP. |
| Cuerpo del contenido de la solicitud HTTP   | Cuerpo de la solicitud HTTP. (El cuerpo puede estar vacío). |
| Valores de consulta de parámetros HTTP | Valores de consulta de parámetros que se utilizan para completar la URL con parámetros variables. |
| Ruta de solicitud               | La ruta para la solicitud HTTP. Los parámetros variables se pueden escribir en notación **\{paramName\}**. Por ejemplo: **"api/{id}/submit"**. |
| Lista de parámetros de ruta        | Los parámetros de ruta, en notación clave-valor, que se utilizan para insertar variables en la ruta. |
| Encabezados HTTP personalizados         | Los encabezados HTTP personalizados para colocar en la solicitud. |
| Cookies de solicitud HTTP        | Una lista de cookies, en notación clave-valor, para colocar en la solicitud de encabezado de cookies HTTP. |
| Protocolo de seguridad           | El protocolo de seguridad que se utilizará para las solicitudes HTTP para comunicarse con el servidor. (Por defecto, se usa Transport Layer Security \[TLS\] 1.2). |

###### <a name="action-call-mexican-pac-service"></a>Acción: Llamar al servicio web de México

| Parámetro                | Descripción |
|--------------------------|-------------|
| Archivo de entrada               | El archivo que contiene datos XML que se enviarán al servicio web como parámetro de entrada del método. |
| Dirección URL              | La dirección del servicio web (punto final). |
| Nombre del método web (acción) | El nombre del método web (acción) que se debe ejecutar. |
| Certificados             | La cadena de certificados que el servicio web requiere para la autenticación del cliente. El certificado de cliente debe ser el último certificado de la cadena. Los certificados raíz e intermedios deben ser los primeros. |
| Tiempo de espera de solicitud web      | La cantidad máxima de tiempo (en milisegundos) para esperar una respuesta del servicio web. |
| Intervalo de reintento           | El intervalo entre los intentos de llamar y recibir una respuesta del servicio web. Si no se especifica ningún intervalo, no se realizarán reintentos adicionales después de que la primera llamada no tenga éxito. |
| Número de reintentos              | El número máximo de reintentos para llamar y recuperar una respuesta del servicio web. |
| Reintentar hasta               | El tiempo máximo (en milisegundos) que pueden continuar las llamadas de reintento. |
| Retroceso mínimo         | La tasa de retroceso mínima para el cálculo exponencial de los intervalos de reintento. |
| Retroceso máximo         | La tasa de retroceso máxima para el cálculo exponencial de los intervalos de reintento. |
| Protocolo de seguridad        | El protocolo de seguridad que se utilizará para las solicitudes HTTP para comunicarse con el servidor. (De forma predeterminada, se usa TLS 1.2). |

###### <a name="action-call-brazilian-sefaz-service"></a>Acción: Llamar al servicio SEFAZ brasileño

| Parámetro                | Descripción |
|--------------------------|-------------|
| Archivo de entrada               | El archivo que contiene datos XML que se enviarán al servicio web como parámetro de entrada del método. |
| Dirección URL              | La dirección del servicio web (punto final). |
| Nombre del método web (acción) | El nombre del método web (acción) que se debe ejecutar. |
| Certificados             | La cadena de certificados que el servicio web requiere para la autenticación del cliente. El certificado de cliente debe ser el último certificado de la cadena. Los certificados raíz e intermedios deben ser los primeros. |
| Tiempo de espera de solicitud web      | La cantidad máxima de tiempo (en milisegundos) para esperar una respuesta del servicio web. |
| Intervalo de reintento           | El intervalo entre los intentos de llamar y recibir una respuesta del servicio web. Si no se especifica ningún intervalo, no se realizarán reintentos adicionales después de que la primera llamada no tenga éxito. |
| Número de reintentos              | El número máximo de reintentos para llamar y recuperar una respuesta del servicio web. |
| Reintentar hasta               | El tiempo máximo (en milisegundos) que pueden continuar las llamadas de reintento. |
| Retroceso mínimo         | La tasa de retroceso mínima para el cálculo exponencial de los intervalos de reintento. |
| Retroceso máximo         | La tasa de retroceso máxima para el cálculo exponencial de los intervalos de reintento. |
| Protocolo de seguridad        | El protocolo de seguridad que se utilizará para las solicitudes HTTP para comunicarse con el servidor. (De forma predeterminada, se usa TLS 1.2). |

###### <a name="action-call-italian-sdi-service"></a>Acción: Llamar al servicio web italiano

| Parámetro                | Descripción |
|--------------------------|-------------|
| Archivo de entrada               | El archivo que contiene datos XML que se enviarán al servicio web como parámetro de entrada del método. |
| Dirección URL              | La dirección del servicio web (punto final). |
| Nombre del método web (acción) | El nombre del método web (acción) que se debe ejecutar. |
| Certificados             | La cadena de certificados que el servicio web requiere para la autenticación del cliente. El certificado de cliente debe ser el último certificado de la cadena. Los certificados raíz e intermedios deben ser los primeros. |
| Tiempo de espera de solicitud web      | La cantidad máxima de tiempo (en milisegundos) para esperar una respuesta del servicio web. |
| Intervalo de reintento           | El intervalo entre los intentos de llamar y recibir una respuesta del servicio web. Si no se especifica ningún intervalo, no se realizarán reintentos adicionales después de que la primera llamada no tenga éxito. |
| Número de reintentos              | El número máximo de reintentos para llamar y recuperar una respuesta del servicio web. |
| Reintentar hasta               | El tiempo máximo (en milisegundos) que pueden continuar las llamadas de reintento. |
| Retroceso mínimo         | La tasa de retroceso mínima para el cálculo exponencial de los intervalos de reintento. |
| Retroceso máximo         | La tasa de retroceso máxima para el cálculo exponencial de los intervalos de reintento. |
| Protocolo de seguridad        | El protocolo de seguridad que se utilizará para las solicitudes HTTP para comunicarse con el servidor. (De forma predeterminada, se usa TLS 1.2). |

### <a name="applicability-rules"></a>Reglas de aplicabilidad

Las reglas de aplicabilidad le permiten crear reglas lógicas que determinan el contexto de uso para la configuración de la función. Por lo tanto, la coincidencia entre el contexto proporcionado por el documento comercial que se envía para su procesamiento, junto con los criterios de la regla de aplicabilidad, determina qué función de facturación electrónica se utiliza para procesar ese envío.

#### <a name="set-up-applicability-rules"></a>Configurar reglas de aplicabilidad

1. En la página **Configuración de la versión de función**, en la pestaña **Reglas de aplicabilidad**, seleccione **Nuevo** para agregar una regla de aplicabilidad.

    ![Administrar reglas de aplicabilidad](media/e-Invoicing-services-feature-setup-Manage-Actions-Applicability-rules.png)

2. En la cuadrícula, seleccione las cláusulas que deben agruparse.
3. Seleccione **Cláusula de grupo**.

    ![Agrupación de cláusulas](media/e-Invoicing-services-feature-setup-Manage-Applicability-rules-Group-clause.png)

    Cuando se agrupan las cláusulas, se agrega una nueva columna a la cuadrícula. Esta columna especifica el operador lógico para las cláusulas agrupadas.

    ![Operador lógico para cláusulas agrupadas](media/e-Invoicing-services-feature-setup-Manage-Applicability-rules-Group-criterias.png)

Para desagrupar cláusulas, seleccione las cláusulas agrupadas que desee desagrupar y luego seleccione **Cláusula de desagrupar**.

![Desagrupación de cláusulas](media/e-Invoicing-services-feature-setup-Manage-Applicability-rules-UnGroup-criterias.png)

> [!NOTE]
> Cuando desagrupa una cláusula, siempre comience desde el nivel de agrupación más interno.

En la tabla siguiente se describen los campos disponibles en la pestaña **Reglas de aplicabilidad**.

| Campo         | Descripción |
|---------------|-------------|
| Y/o        | Operador lógico. |
| Campo         | El campo que se utilizará para construir la regla. |
| Tipo de operador | El tipo de operador.<ul><li>Igual</li><li>No igual</li><li>Mayor que/Menor que</li><li>Mayor o igual que/menor o igual que</li><li>Contiene</li><li>Empieza por</li></ul> |
| Valor         | El criterio de la regla. |

### <a name="variables"></a>Variables

Puede crear variables y luego usarlas como valor de entrada para un parámetro de una acción específica. También puede utilizarlos para intercambiar, entre los servicios de facturación electrónica y el cliente, información que sea el resultado de la ejecución de una acción específica como parte del flujo de envíos.

#### <a name="set-up-variables"></a>Configurar variables

- En la página **Configuración de la versión de función**, en la pestaña **Variables**, seleccione **Nuevo** o **Eliminar** para gestionar variables.

    ![Gestionar variables](media/e-Invoicing-services-feature-setup-Manage-Variables.png)

En la tabla siguiente se describen los campos disponibles en la pestaña **Variables**.

| Campo       | Descripción |
|-------------|-------------|
| Nombre        | El nombre de la variable. |
| Descripción | Descripción breve de la variable. |
| Tipo        | El tipo de variable.<ul><li><strong>Constante</strong>: el contenido de la variable es fijo.</li><li><strong>Del cliente</strong>: el contenido de la variable se adquiere del cliente de Microsoft Dynamics 365 durante la ejecución del proceso de envío.</li><li><strong>Al cliente</strong>: el contenido de la variable se pone a disposición para la importación por el cliente de Microsoft Dynamics 365 durante la ejecución del proceso de envío.</li></ul> |
| Tipo de datos   | Tipo de dato de la variable:<ul><li>Booleano</li><li>Fecha</li><li>Número</li><li>UUID</li><li>Cadena</li><li>Archivo</li></ul> |
| Valor       | El valor de la variable o el nombre de la acción que establece el valor de la variable. |

### <a name="validate-the-feature-setup"></a>Validar la configuración de la función

- En la página **Configuración de la versión de función**, en el panel de acciones, seleccione **Validar** para validar la configuración de la versión de la función.

   ![Selección del botón Validar](media/e-Invoicing-services-feature-setup-Select-Validate-Button.png)

La validación comprueba la coherencia de toda la configuración. Por ejemplo, si un parámetro específico para una acción es obligatorio pero su valor permanece en blanco, la validación detecta esta inconsistencia y recibe una advertencia.

## <a name="environments"></a>Entornos

Un ambiente de facturación electrónica debe estar asociado con la función de facturación electrónica y debe habilitarse para ello. Los ambientes de facturación electrónica deben crearse y publicarse con anticipación, mediante la configuración de las funciones de globalización en la cuenta RCS de su organización.

Siga estos pasos para habilitar el entorno de facturación electrónica para la función de facturación electrónica.

1. En la página **Funciones de facturación electrónica**, en la pestaña **Entornos**, seleccione **Habilitar** para agregar un entorno de facturación electrónica.
2. En el campo **Válido desde**, ingrese la fecha en que el nuevo entorno entra en vigencia.

![Habilitar un ambiente de facturación electrónica](media/e-Invoicing-services-feature-setup-Select-Enable-e-Invoicing-feature-Environment.png)

## <a name="organizations"></a>Organizaciones

La función de facturación electrónica se puede compartir entre varias organizaciones.

- En la página **Funciones de facturación electrónica**, en la pestaña **Organizaciones**, seleccione **Compartir con** para agregar la organización con la que desea compartir la función de facturación electrónica.

Para dejar de compartir la función de facturación electrónica con la organización, seleccione **Dejar de compartir**.

## <a name="versions"></a>Versiones

Las versiones ayudan a controlar el ciclo de vida de la función de facturación electrónica mediante la gestión de su estado. Puede crear una nueva versión de una función de facturación electrónica existente o, cuando se complete toda la configuración de la función de facturación electrónica, puede cambiar el estado de la función a **Completo** y luego a **Publicar**.

### <a name="create-a-new-version-of-an-existing-electronic-invoicing-feature"></a>Crear una nueva versión de una función de facturación electrónica existente

1. En la página **Características de facturación electrónica**, en la cuadrícula a la izquierda, seleccione la función de facturación electrónica.
2. En la pestaña **Versiones**, seleccione **Nueva** para agregar una nueva versión de la función de facturación electrónica.

### <a name="change-the-status-of-the-electronic-invoicing-feature"></a>Cambiar el estado de la función de facturación electrónica

Siga estos pasos para gestionar el ciclo de vida de la función de facturación electrónica.

1. En la página **Características de facturación electrónica**, en la cuadrícula a la izquierda, seleccione la función de facturación electrónica.
2. En la pestaña **Versiones**, seleccione **Cambiar Estado** y luego cambie el estado de **Borrador** a **Completar**.
3. Se le solicitará que confirme que desea completar la función de facturación electrónica y todos sus componentes. Seleccione **Sí** para confirmar la acción o **No** para cancelarla.

    > [!NOTE]
    > Cuando selecciona **Sí**, el estado de las versiones de configuración, que son componentes de la función de facturación electrónica, se cambia automáticamente de **Borrador** a **Completado**.

4. Seleccione **Cambiar Estado** y luego cambie el estado de **Completar** a **Publicar**.
5. Se le solicitará que confirme que desea publicar la función de facturación electrónica y todos sus componentes en el repositorio global. Seleccione **Sí** para confirmar la acción o **No** para cancelarla.

    > [!NOTE]
    > Cuando selecciona **Sí**, el estado de las versiones de configuración se cambia automáticamente de **Terminado** a **Compartido**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]