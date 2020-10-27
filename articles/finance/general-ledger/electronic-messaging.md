---
title: Mensajes electrónicos
description: Este tema proporciona información general y de configuración del correo electrónico en Microsoft Dynamics 365 Finance.
author: ShylaThompson
manager: AnnBe
ms.date: 11/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-10-28
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: b5887efc32c71759e4cb3c31e1b18c4c8b64f173
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3977200"
---
# <a name="electronic-messaging"></a>Mensajería electrónica

[!include [banner](../includes/banner.md)]

Este tema proporciona información general y de configuración del correo electrónico.

Recientemente, los gobiernos y las autoridades legislativas de varios países y regiones en todo el mundo han implementado los requisitos de informe para las empresas que se registran en dichos países o regiones. El objetivo de los requisitos es habilitar que los datos que se obtienen de dichas empresas estén en formato electrónico, directamente desde sistemas donde se han contabilizado, almacenado, y procesado.

La funcionalidad de los mensajes electrónicos en Finance admite varios procesos de interoperación electrónica entre Finance y los sistemas que los gobiernos y las autoridades legislativas proporcionan para informar, enviar y recibir información oficial.

La funcionalidad de los mensajes electrónicos se integra con el módulo **Informes electrónicos** (ER). Por lo tanto, puede configurar los formatos de ER para los mensajes electrónicos. Para obtener más información, consulte [Informes electrónicos (ER)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/general-electronic-reporting).

Los mensajes electrónicos se basan en las entidades siguientes:

- **Mensaje electrónico** – Un informe o una declaración que debe notificarse y/o transmitirse internamente. Un ejemplo es un informe que se envía a una delegación de Hacienda.
- **Elementos del mensaje electrónico** Registros que se deben incluir en el mensaje que se notifica.
- **Procesamiento de mensaje electrónico**: una cadena de acciones que se debe ejecutar para obtener los datos necesarios, generar informes, almacenar datos en el almacenamiento de Microsoft Azure Blob, transmitir informes fuera del sistema, recibir respuestas que se encuentran fuera del sistema, y actualizar la base de datos, según la información que se recibe. Las acciones en la cadena pueden ser vinculadas o desvinculadas

La ilustración siguiente muestra el flujo de datos de los mensajes electrónicos.

![Flujo de datos de mensajes electrónicos](media/electronic-messaging-data-flow.png)

La funcionalidad de los mensajes electrónicos admite los escenarios siguientes:

- Crear manualmente los mensajes y generar los informes basados en formatos de ER asociados de exportación de distintos tipos: Microsoft Excel, XML, JavaScript Object Notation (JSON), PDF, texto y Microsoft Word.
- Crear automáticamente y procesar mensajes que se basan en la información que se solicitó y se recibió de una autoridad mediante un formato ER de importación asociado.
- Recopilar y procesar información de un origen de datos como elementos de mensaje. Origen de datos es una tabla Finance.
- Almacenar la información adicional, y evaluar los diversos valores llamando a clases ejecutables específicamente definidas en relación con mensajes o elementos de mensajes.
- Agregar información obtenida en elementos de mensaje, dividir dicha información por mensaje, y generar informes que se encuentran en formatos de ER asociados de exportación.
- Transmitir los informes que se generan a un servicio Web mediante la información de seguridad que se almacena en Azure Key Vault.
- Recibir una respuesta de un servicio Web, interpretar la respuesta, y actualizar los datos de Finance según sea adecuado.
- Almacenar y revisar todos los informes generados.
- Almacenar y revisar toda la información de registro relacionada con las acciones que se ejecutan para un mensaje o un elemento de mensaje.
- Controlar el procesamiento a través de distintos estados de mensaje y estados de elementos de mensaje.

## <a name="set-up-electronic-messaging"></a>Configurar mensajes electrónicos

Los mensajes electrónicos pueden ayudarle a mantener varios procesos electrónicos de informes para distintos tipos de documentos. En algunas escenarios complejos, el correo electrónico se configura para que tenga una combinación de muchos estados de mensajes, estados de elementos de mensaje, acciones, más campos, y clases ejecutables. Para estos casos, los paquetes de entidades de los datos están disponibles para la importación. Si usa estos paquetes de entidad de datos, debe importarlos a una entidad jurídica mediante la herramienta de administración de datos. Para obtener más información sobre cómo usar la herramienta de gestión de datos, vea [Administración de datos](../../dev-itpro/data-entities/data-entities-data-packages.md).

Si no importa un paquete de entidad de datos, puede configurar manualmente la funcionalidad de mensajes electrónicos. En tal caso, debe configurar los elementos siguientes:

- [Secuencias numéricas](#number-sequences)
- [Tipos y estados de elementos de mensajes](#message-item-types-and-statuses)
- [Estados de mensaje](#message-statuses)
- [Campos adicionales](#additional-fields)
- [Configuración de clase ejecutable](#executable-class-settings)
- [Acciones de llenado de registros](#populate-records-actions)
- [Aplicaciones web](#web-applications)
- [Configuración de servicio web](#web-service-settings)
- [Acciones de procesamiento de mensajes](#message-processing-actions)
- [Procesamiento de mensaje electrónico](#electronic-message-processing)

En las secciones siguientes se ofrece más información acerca de cada uno de estos elementos.

### <a name="number-sequences"></a>Secuencias numéricas

Configure secuencias numéricas para los mensajes y los elementos de mensaje. Las secuencias numéricas se usan para numerar automáticamente los mensajes y los elementos de mensaje. Los números que se asignan se usarán como identificadores únicos de los mensajes y los elementos de mensaje en el sistema. Puede configurar secuencias numéricas para mensajes electrónicos en la página **Parámetros de contabilidad general** (**contabilidad general** \> **Configuración de contabilidad** \> **Parámetros de contabilidad general**).

### <a name="message-item-types-and-statuses"></a>Tipos y estados de elementos de mensajes

Los tipos de elementos de mensaje identifican los tipos de registros que se usarán en los mensajes electrónicos. Puede configurar los tipos de elementos del mensaje en la página **Tipos de elementos de mensaje** (**Impuestos** \> **Configuración** \> **Mensajes electrónicos** \> **Tipos de elementos de mensaje**).

Los estados del elemento de mensaje identifican los estados que se aplicarán a los elementos del mensaje en el proceso que está configurando. Puede configurar los tipos de elementos del mensaje en la página **Estados de elemento de mensaje** (**Impuestos** \> **Configuración** \> **Mensajes electrónicos** \> **Estados de elemento de mensaje**).

El parámetro **Permitir la cancelación** de un estado de elemento de mensaje define si los usuarios podrán eliminar elementos de mensaje con este estado mediante la página **Mensajes electrónicos** o la página **Elementos del mensaje electrónico**.

### <a name="message-statuses"></a>Estados de mensaje

Configure los estados del mensaje que deben estar disponibles en el procesamiento de mensajes. Puede configurar los estados del mensaje en la página **Estados de mensaje** (**Impuestos** \> **Configuración** \> **Mensajes electrónicos** \> **Estados de mensaje**).

En la tabla siguiente se describen los campos en la página **Estados del mensaje**.

| Nombre del campo          | Descripción |
|---------------------|-------------|
| Estado del mensaje      | Especificar un nombre único para el estado del mensaje. Los estados del mensaje se usan para caracterizar al estado de un mensaje electrónico en cada momento. El nombre que especifique se muestra en la página **Mensajes electrónicos** y en un registro que está relacionado con los mensajes electrónicos. |
| Descripción         | Introduzca una descripción del estado de mensaje. |
| Tipo de respuesta       | Seleccione el tipo de respuesta para el estado de mensaje. Algunas acciones en un proceso pueden producir más de un tipo de respuesta. Por ejemplo, las acciones del tipo **Servicio web** pueden producir respuestas del tipo **Ejecutado correctamente** o el tipo **Error técnico** en función del resultado de su ejecución. En este caso, debe definir los estados de mensaje para ambos tipos de respuestas. Para más información sobre los tipos de acción y sus tipos de respuesta relacionados, consulte [Tipos de acción de procesamiento de mensajes](#message-processing-action-types). |
| Estado de elemento de mensaje | En ocasiones, el estado de un mensaje electrónico debe afectar al estado de los artículos de mensaje relacionados. Seleccione un estado de artículo del mensaje en este campo para asociarlo al estado del mensaje. |
| Permitir eliminación        | Seleccione esta casilla si los usuarios pueden borrar los mensajes electrónicos que tengan este estado en la página **Mensajes electrónicos**. |

### <a name="additional-fields"></a>Campos adicionales

La funcionalidad de los mensajes electrónicos permite rellenar los registros desde una tabla transaccional. De esta manera, puede preparar los registros para informar y luego informarlos. Sin embargo, las tablas transaccionales no tienen a veces suficiente información para completar los registros de una forma que cumplan los requisitos de informes. Para completar toda la información que se debe notificar para un registro, puede configurar campos adicionales. Los campos adicionales se pueden asociar con mensajes y elementos de mensaje. Puede configurar campos adicionales en la página **Campos adicionales** (**Impuestos** \> **Configuración** \> **Mensajes electrónicos** \> **Campos adicionales**).

En la tabla siguiente se describen los campos generales en la página **Campos adicionales**.

| Campo       | Descripción |
|-------------|-------------|
| Nombre del campo  | Escriba el nombre del atributo adicional de elementos de mensaje relacionados con el proceso. Este nombre aparece en la interfaz de usuario (IU) mientras trabaja con el proceso. También se puede usar en configuraciones de ER relacionadas con el proceso. |
| Descripción | Indique una descripción para el campo adicional. |
| Edición de usuario   | Establezca esta opción en **Sí** si los usuarios pueden cambiar el valor del campo adicional desde la interfaz de usuario. |
| Contador     | Establezca esta opción en **Sí** si el campo adicional debe contener una secuencia numérica en un mensaje electrónico. El valor del campo adicional se rellenará automáticamente cuando se ejecute una acción de **Exportación de informes electrónicos**. |
| Oculto      | Establezca esta opción en **Sí** si el campo adicional debería estar oculto en la interfaz de usuario. |

Cada campo adicional puede tener diferentes valores para el procesamiento. Puede definir estos parámetros en la ficha desplegable **Valores**. En la siguiente tabla se describen los campos.

| Campo                | Descripción |
|----------------------|-------------|
| Valor del campo          | Especifique el valor de campo para un elemento de mensaje o un mensaje durante la notificación. |
| Descripción          | Indique una descripción para el valor de campo. |
| Tipo de cuenta         | Algunos valores de campo pueden limitarse a tipos de cuenta específicos. Seleccione uno de los valores siguientes: **Todo**, **Cliente** o **Proveedor**. |
| Código de cuenta         | Si seleccionó **Cliente** o **Proveedor** en el campo **Tipo de cuenta** , puede limitar aún más el uso de valor de campo a un grupo o a una tabla específico. |
| Número de grupo/cuenta | Si seleccionó **Cliente** o **Proveedor** en el campo **Tipo de cuenta** , y si especificó un grupo o una tabla en el campo **Código de cuenta** , puede especificar un grupo o contratista específico en este campo. |
| Vigente            | Especifique la fecha en que el valor debe comenzar a ser considerado. |
| Caducidad           | Especifique la fecha en que el valor debe terminar de ser considerado. |

De forma predeterminada, las combinaciones de criterios que están definidos por **Número de la cuenta o de grupo**, **Código de cuenta**, **Efectivo**, y de campos **Caducidad** no influyen en la selección de valores para los campos adicionales. Sin embargo, estas combinaciones se pueden usar en una clase ejecutable para implementar la lógica específica que calcula los valores para los campos adicionales.

### <a name="executable-class-settings"></a>Configuración de clase ejecutable

Una clase ejecutable es un método o clase X++ que el procesamiento de mensajes electrónicos puede llamar en relación con una acción si se requiere evaluación para el proceso.

Puede configurar manualmente una clase ejecutable en la página **Configuración de clase ejecutable** (**Impuestos** \> **Configuración** \> **Mensajes electrónicos** \> **Configuración de clase ejecutable**). Cree una línea, y establezca los campos siguientes.

| Campo                 | Descripción |
|-----------------------|-------------|
| Clase ejecutable      | Escriba el nombre que se usará durante la configuración de una acción de procesamiento de mensajes en relación con la cual se llama esta clase. |
| Descripción           | Escriba una descripción de la clase de ejecutable. |
| Nombre de la clase ejecutable | Seleccione una clase ejecutable X++. |
| Nivel de ejecución       | Este campo se establece automáticamente, porque el valor debe predefinirse para la clase ejecutable seleccionada. Este campo limita el nivel en que se ejecuta la evaluación relacionada. |
| Descripción de la clase     | Este campo se establece automáticamente, porque el valor debe predefinirse para la clase ejecutable seleccionada. |

Algunas clases ejecutables pueden tener parámetros obligatorios que se deben definir antes de que la clase ejecutable se ejecute por primera vez. Para definir estos parámetros, seleccione **Parámetros** en el panel de acciones, establezca los campos en el cuadro de diálogo que aparece y, a continuación seleccione **Aceptar**. Es importante que se seleccione **Aceptar**. De lo contrario, los parámetros no se guardarán en la base de datos, y la clase ejecutable no será llamada correctamente.

### <a name="populate-records-actions"></a>Acciones de llenado de registros

Las acciones de llenado de registros se usan para configurar acciones para agregar registros a la tabla de elementos de mensaje de forma que se puedan agregar a un mensaje electrónico. Por ejemplo, si el mensaje electrónico debe notificar facturas de cliente, debe configurar una acción de popular registros que esté vinculada al campo **Origen de datos** en la tabla Diario de facturas del cliente. Puede configurar acciones de llenado de registros en la página **Acción de llenado de registros** (**Impuestos** \> **Configuración** \> **Mensajes electrónicos** \> **Acciones de llenado de registros**). Cree un registro nuevo para cada acción que debe agregar registros a la tabla, y establezca los campos siguientes.

| Campo       | Descripción |
|-------------|-------------|
| Nombre        | Escriba un nombre para la acción que rellena registros en su proceso. |
| Descripción | Especifique una descripción de la acción rellenar registros. |

En la ficha desplegable **Configuración de orígenes de datos**, agregue una línea para cada origen de datos usado para el proceso, y establezca los campos siguientes.

| Campo                  | Descripción |
|------------------------|-------------|
| Nombre                   | Escriba un nombre para el origen de datos. |
| Tipo de elemento de mensaje      | Seleccione el tipo de elemento de mensaje que se debe usar cuando los registros se crean para el origen de datos. |
| Tipo de cuenta           | Seleccione el tipo de cuenta que debe asociarse a los registros desde el origen de datos. |
| Nombre de la tabla principal      | Seleccione la tabla que debe ser un origen de datos. |
| Campo de número de documento  | Seleccione el campo de dónde debe tomarse el número de documento en la tabla seleccionada. |
| Campo de fecha de documento    | Seleccione el campo de dónde debe tomarse la fecha de documento en la tabla seleccionada. |
| Campo de cuenta de documento | Seleccione el campo de dónde debe tomarse la cuenta de documento en la tabla seleccionada. |
| Consulta de usuario             | Si se activa esta casilla, puede configurar una consulta seleccionando **Editar consulta** sobre la cuadrícula. Si no, todos los registros se rellenarán desde el origen de datos seleccionado. |

### <a name="web-applications"></a>Aplicaciones web

Use los valores de la aplicación web para configurar una aplicación web de modo que admita Open Authorization (OAuth) 2.0. OAuth es el estándar abierto que permite a los usuarios conceder "acceso seguro delegado” a la aplicación en su nombre, sin compartir sus credenciales de acceso. También puede pasar por el proceso de autorización obteniendo un código de autorización y un token de acceso. Puede configurar los parámetros de aplicaciones Web en la página **aplicaciones Web** (**Impuestos** \> **Configuración** \> **Mensajes electrónicos** \> **Aplicaciones Web**).

En la tabla siguiente se describen los campos en la página **Aplicaciones web**.

| Campo                        | Descripción |
|------------------------------|-------------|
| Nombre de la aplicación             | Escriba un nombre para la aplicación Web. |
| Descripción                  | Especifique una descripción para la aplicación web. |
| Dirección URL base                     | Permite especificar la dirección de internet base de la aplicación Web. |
| Ruta URL de autorización       | Especifique la ruta que se usa para producir la URL para la autorización. |
| Ruta URL de token               | Especifique la ruta que se usa para producir la URL para el token. |
| URL de redireccionamiento                 | Especifique la dirección URL de redireccionamiento. |
| Id. de cliente                    | Especifique el identificador del cliente de la aplicación web. |
| Secreto de cliente                | Especifique el secreto del cliente de la aplicación web. |
| Token de servidor                 | Especifique el token de servidor de la aplicación web. |
| Asignación de formato de autorización | Seleccione el formato de ER que se usa para generar la petición de autorización. |
| Importar asignación de modelo de token   | Seleccione la asignación de modelo de importación ER que se utilizará para almacenar el token de acceso. |
| Ámbito concedido                | El ámbito que se concede para las solicitudes a la aplicación. Este campo se actualiza automáticamente. |
| El token de acceso expirará en  | El tiempo restante antes de que el símbolo de acceso venza. | 
| Aceptar                       | Especifique la propiedad **Aceptar** de solicitud web. Por ejemplo, introduzca **application/vnd.hmrc.1.0+json**. |
| Tipo de contenido                 | Especifique el tipo de contenido. Por ejemplo, introduzca **application/json**. |

Además, los siguientes botones están disponibles en el panel de acciones de la página **Aplicaciones Web** para admitir el proceso de autorización:

- **Obtener código de autorización** - Inicializa la autorización de la aplicación web.
- **Obtener token de acceso** - Inicializa el proceso de obtención de un token de acceso.
- **Actualizar token de acceso** - Actualiza un token de acceso.

Cuando un token de acceso a una aplicación web se almacena en la base de datos del sistema, está en formato cifrado que se puede usar para las solicitudes a un servicio web. Por motivos de seguridad el acceso al token de acceso se debe limitar a los roles de seguridad a los que se debe permitir tratar dichas solicitudes. Si los usuarios de fuera del grupo de seguridad intentan dirigir una solicitud, recibirán un error informando de que no tienen permiso para interoperar mediante la aplicación web seleccionada. Para configurar los roles de seguridad que deben tener acceso al token de acceso, use la ficha desplegable **Roles de seguridad** en la página **Aplicaciones Web**. Si los roles de seguridad no se definen para una aplicación Web, solo un administrador del sistema podrá interoperar mediante esta aplicación Web.

### <a name="web-service-settings"></a>Configuración de servicio web

Use los valores de servicio Web para configurar la transmisión de datos directa a un servicio web. Puede configurar los parámetros de servicio Web en la página **Configuración de servicio Web** (**Impuestos** \> **Configuración** \> **Mensajes electrónicos** \> **Configuración de servicio Web**).

En la tabla siguiente se describen los campos en la página **Configuración de servicio web**.

| Campo                          | Descripción |
|--------------------------------|-------------|
| Servicio web                    | Escriba un nombre para el servicio Web. |
| Descripción                    | Especificar una descripción del servicio web. |
| Dirección de Internet               | Permite especificar la dirección del servicio Web. Si una aplicación web se especifica para un servicio Web y si la dirección de Internet del servicio Web tiene que ser la misma que la que se ha definido para la aplicación Web seleccionada, seleccione **Copiar URL base** para copiar la dirección URL base de la aplicación web a este campo. |
| Certificado                    | Seleccionar un certificado de Key Vault que se ha configurado previamente. |
| Aplicación web                | Seleccionar un certificado de Key Vault que se ha configurado previamente. |
| Tipo de respuesta – XML        | Establezca esta opción en **Sí** si el tipo de respuesta es XML. |
| Método de solicitud                 | Especifique el método de la solicitud. HTTP define un conjuntos de métodos de solicitud que indican la acción que se debe realizar para un recurso determinado. El método de solicitud puede ser **GET**, **POST**, o bien otro método HTTP. |
| Encabezados de solicitud                | Especifique los encabezados de solicitud. Un encabezado de solicitud es un encabezado HTTP que se puede usar en una solicitud HTTP, y que no está relacionado con el contenido del mensaje. |
| Aceptar                         | Especifique la propiedad **Aceptar** de solicitud web. |
| Aceptar codificación                | Especifique el valor **Accept-Encoding**. El encabezado HTTP de solicitud Accept-Encoding hace publicidad de codificación de contenido que el cliente puede entender. Esta codificación de contenido es normalmente un algoritmo de compresión. |
| Tipo de contenido                   | Especifique el tipo de contenido. El encabezado HTTP de la entidad del tipo de contenido indica el tipo de medio del recurso. |
| Código de respuesta correcto       | Especifique el código de estado HTTP que indica que la solicitud ha sido correcta. |
| Asignación de formato de encabezados de solicitud | Seleccione el formato de ER que se usa para generar la petición Web de encabezados. |

### <a name="message-processing-actions"></a>Acciones de procesamiento de mensajes

Las acciones de procesamiento de mensajes se usan para crear acciones para los procesos y para configurar los parámetros. Puede configurar las acciones de procesamiento del mensaje en la página **Acciones de procesamiento de mensajes** (**Impuestos** \> **Configuración** \> **Mensajes electrónicos** \> **Acciones de procesamiento de mensajes**).

Las siguientes tablas describen los campos de la página **Acciones de procesamiento de mensajes**.

#### <a name="general-fasttab"></a>Ficha desplegable General

| Campo                       | Descripción |
|-----------------------------|-------------|
| Tipo de acción                 | Seleccione el tipo de acción. Para obtener información acerca de las opciones disponibles, consulte la sección [Tipos de acción de procesamiento de mensajes](#message-processing-action-types). |
| Asignación de formato              | Seleccione el formato de ER que se debe llamar para la acción. Este campo solo está disponible para las acciones de tipo **Exportación de informes electrónicos**, **Importación de informes electrónicos**, y **Mensaje de exportación de informes electrónicos** . |
| Asignación de formato para ruta URL | Seleccione el formato de ER que se debe llamar para la acción. Este campo solo está disponible para las acciones del tipo **Servicio web**. Se usa para componer la ruta de la dirección URL que se agregará a la dirección base de Internet que se especifica para el servidor Web seleccionado. |
| Tipo de elemento de mensaje           | Seleccione el tipo de registros para los que debe evaluarse la acción. Este campo está disponible para los tipos **Nivel de ejecución de elemento de mensaje**, **Exportación de informes electrónicos**, **Importación de informes electrónicos** y **Servicio web** y también algunos tipos más. Si deja este campo en blanco, se evalúan todos los tipos de elementos de mensaje que se definen para el procesamiento de mensajes. |
| Clase ejecutable            | Seleccione los valores de clase de ejecutable anteriormente creados. Este campo solo está disponible para las acciones del tipo **Nivel de ejecución de elemento de mensaje** y **Nivel de ejecución de elemento de mensaje**. |
| Acción de llenado de registros     | Seleccione una acción de rellenar registros que se configuró anteriormente. Este campo solo está disponible para las acciones del tipo **Rellenar registros** . |
| Servicio web                 | Seleccione un servicio web que se configuró anteriormente. Este campo solo está disponible para las acciones del tipo **Servicio web**. |
| Nombre de archivo                   | Especifique el nombre del archivo que será el resultado de la acción. Este archivo puede ser la respuesta del servidor Web o del informe que se ha generado. Este campo solo está disponible para las acciones de los tipos **Servicio web** y **Mensaje de la exportación del informe electrónico**. |
| Mostrar cuadro de diálogo                 | Establezca esta opción **Sí** si se debe mostrar un diálogo a los usuarios antes de la generación de informes. Este campo solo está disponible para las acciones del tipo **Mensaje de la exportación del informe electrónico**. |

##### <a name="message-processing-action-types"></a>Tipo de acciones de procesamiento de mensajes

Las opciones siguientes están disponibles en el campo **Tipo de acción**:

- **Crear mensaje** - Use este tipo de acción para permitir a los usuarios manualmente crear mensajes en la página **Mensaje electrónico**. Un estado inicial no se puede configurar para una acción de este tipo.
- **Rellenar registros** - Una acción del tipo **Rellenar registros** debe estar configurada previamente. Asocie este tipo de acción con una acción de rellenar registros para habilitar esa acción para incluirla en el procesamiento. Se presupone que se usa este tipo de acción para la primera acción del procesamiento de mensajes (cuando no se ha creado ningún mensaje electrónico por adelantado) o para una acción que agrega elementos a mensaje a un mensaje creado previamente mediante una acción del tipo **Crear mensaje**. Por lo tanto, para acciones de este tipo, el estado del resultado solo se puede configurar para elementos del mensaje. Un estado inicial se puede configurar solo para mensajes.
- **Nivel de ejecución de mensaje** - Use este tipo de acción para configurar una clase ejecutable que se debe evaluar en el nivel de mensaje.
- **Nivel de ejecución de artículo de mensaje** - Use este tipo de acción para configurar una clase ejecutable que se debe evaluar en el nivel de elemento de mensaje.
- **Exportación de informes electrónicos** - Use este tipo de acción para las acciones que deben generar un informe basado en una configuración de ER de exportación en el nivel de elemento de mensaje.
- **Mensaje de exportación de informes electrónicos** - Use este tipo de acción para las acciones que deben generar un informe basado en una configuración de ER de exportación en el nivel de mensaje (por ejemplo, cuando un mensaje no tiene ningún elemento de mensaje).
- **Importación de informes electrónicos** - Use este tipo de acción para las acciones que deben generar un informe basado en una configuración de ER de importación en el nivel de elemento de mensaje.
- **Procesamiento de usuario de nivel de mensaje** Use este tipo de acción para acciones que presuponen alguna acción manual por parte del usuario a nivel de mensaje. Por ejemplo, el usuario podría actualizar el estado de los mensajes.
- **Procesamiento de usuario** - Use este tipo de acción para acciones que presuponen alguna acción manual por parte del usuario a nivel de elemento. Por ejemplo, el usuario podría actualizar el estado de los elementos de mensajes.
- **Servicio web** - Use este tipo de acción para las acciones que deben transmitir un informe generado a un servicio web. No se usa este tipo de acción para los informes italianos de comunicación de la compra y las facturas de ventas. Para acciones del tipo **Servicio web**, la página **Acciones de procesamiento de mensajes** incluye una ficha desplegable **Detalles varios**, donde podrá especificar un texto de confirmación. Este texto de confirmación se presentará a los usuarios antes de que las solicitudes del servicio Web seleccionado se aborden.
- **Comprobación de solicitud** - Use este tipo de acción para solicitar la comprobación desde un servidor.

#### <a name="initial-statuses-fasttab"></a>Ficha desplegable Estados iniciales

> [!NOTE]
> La ficha desplegable **Estados iniciales** no está disponible para acciones que tienen un tipo inicial de acción **Crear mensaje**.

| Campo               | Descripción |
|---------------------|-------------|
| Estado de elemento de mensaje | Seleccione el estado del elemento de mensaje para el que debe evaluarse la acción de procesamiento de mensaje seleccionada. |
| Descripción         | Descripción del estado del elemento de mensaje seleccionado. |

#### <a name="result-statuses-fasttab"></a>Ficha desplegable Estados de resultado

| Campo               | Descripción |
|---------------------|-------------|
| Estado del mensaje      | Seleccione los estados de mensaje para los que debe evaluarse la acción de procesamiento de mensaje seleccionada. Este campo solo está disponible para las acciones de procesamiento de mensajes que se evalúan en el nivel de mensaje. Por ejemplo, está disponible para las acciones de los tipos **Exportar informes electrónicos** e **Importar informes electrónicos** , pero no está disponible para las acciones de los tipos **Procesamiento de usuario** y **Nivel de la ejecución del artículo de mensaje**. |
| Descripción         | Descripción del estado de mensaje seleccionado. |
| Tipo de respuesta       | El tipo de respuesta del estado de mensaje seleccionado. |
| Estado de elemento de mensaje | Seleccione los estados obtenidos que deben estar disponibles después de evaluarse la acción de procesamiento de mensaje seleccionada. Este campo solo está disponible para las acciones de procesamiento de mensajes que se evalúan en el nivel de elemento de mensaje. Por ejemplo, está disponible para las acciones de los tipos **Procesamiento de usuario** y **Nivel de ejecución de artículo de mensaje**. Para acciones de procesamiento de mensajes que se evalúan en el nivel de mensaje, este campo muestra el estado del elemento de mensaje configurado para el estado del mensaje seleccionado. |

En la tabla siguiente se muestran los estados de resultado que deben estar configurados para los distintos tipos de acción y de respuesta.

| Tipo de acción de mensaje electrónico/Tipo de respuesta | Ejecutado correctamente | Error empresarial | Error técnico | Definido por el usuario | Cancelar |
|----------------------------------------------|-----------------------|----------------|-----------------|--------------|--------|
| Crear mensaje                               | X                     |                |                 |              |        |
| Exportación de informes electrónicos                  | X                     |                |                 |              |        |
| Importación de informes electrónicos                  |                       |                |                 |              |        |
| Servicio web                                  | X                     |                | X               |              |        |
| Procesamiento de usuarios                              |                       |                |                 |              |        |
| Nivel de ejecución de mensaje                      |                       |                |                 |              |        |
| Rellenar registros                             |                       |                |                 |              |        |
| Nivel de ejecución de artículo de mensaje                 |                       |                |                 |              |        |
| Comprobación de solicitud                         | X                     | X              | X               |              |        |
| Mensaje de exportación de informes electrónicos          | X                     |                |                 |              |        |
| Procesamiento de usuario de nivel de mensaje                |                       |                |                 |              |        |

### <a name="electronic-message-processing"></a>Procesamiento de mensaje electrónico

El procesamiento de mensajes electrónicos es un concepto básico de la funcionalidad de los mensajes electrónicos. Agrega las acciones que se deben evaluar para el mensaje electrónico. Las acciones se pueden vincular a través de un estado inicial y un estado de resultado. Como alternativa, las acciones del tipo **Procesamiento de usuario** se pueden iniciar de forma independiente. En la página **Procesamiento de mensaje electrónico** (**Impuestos** \> **Configuración** \> **Mensajes electrónicos** \> **Procesamiento de mensaje electrónico**), también puede seleccionar los campos adicionales que deben admitirse para el procesamiento ya sea en el nivel de mensaje o en el nivel de elementos de mensaje.

La ficha desplegable **Acción** permite agregar acciones predefinidas al procesamiento. Puede especificar si una acción se debe ejecutar por separado, o si puede iniciarse por el procesamiento. Para especificar que una acción en el proceso solo puede inicializarla un usuario, establezca el campo **Funcionamiento por separado** en **Sí** para dicho acción. Si una acción debería iniciarse por el procesado de mensaje o elementos de mensaje que están en el estado definido como el estado inicial para la acción, establezca el campo **Ejecutar por separado** en **No**. Las acciones del tipo **Acción del usuario** siempre se debe ejecutar por separado.

A veces, varias acciones se deben incluir en una secuencia, aunque la primera acción esté configurada de modo que ejecute por separado. Por ejemplo, cuando se requiere que la generación de informes deba ser inicializada por un usuario pero inmediatamente después de que se haya generado el informe, este debe enviarse al servicio Web y la respuesta del servicio Web debe reflejarse en el sistema. En esta situación, puede crear una secuencia inseparable para las acciones que deben ejecutarse siempre conjuntamente. En la pestaña desplegable **Acción** , seleccione **Secuencias inseparables** encima de la cuadrícula, y cree una secuencia. A continuación, para todas las acciones que deben ejecutarse conjunto, seleccione la secuencia en el campo **Secuencia inseparable**. En este caso, el campo **Ejecutar por separado** se puede establecer en **Sí** para la primera acción de la secuencia pero en **No** para el resto de acción.

La ficha desplegable **Campos adicionales de elemento de mensaje** permite agregar campos adicionales predefinidos relacionados con los elementos del mensaje. Debe agregar campos adicionales para cada tipo de elemento de mensaje con el que los campos están relacionados.

La ficha desplegable **Campos adicionales de elemento de mensaje** permite agregar campos adicionales predefinidos relacionados con los mensajes.

La ficha desplegable **Roles de seguridad** configuración le permite configurar los roles de seguridad que están predefinidos en el sistema para el procesamiento específico. Los usuarios con un rol específico solo verán el procesamiento definido para dicho rol.

La ficha desplegable **Lote** permite configurar el procesamiento para que funcione en un régimen por lotes.

## <a name="work-with-the-electronic-messages-functionality"></a>Trabajo con la funcionalidad de mensajes electrónicos

Si trabaja en el nivel de mensaje, la página **Mensajes electrónicos** (**Impuestos** \> **Consultas e informes** \> **Mensajes electrónicos** \> **Mensajes electrónicos**) es más útil. Si trabaja en el nivel de recopilación de datos (elemento de mensaje), la página **Elementos de mensaje electrónico** (**Impuestos** \> **Consultas e informes** \> **Mensajes electrónicos** \> **elementos de mensaje electrónico**) es más útil.

### <a name="electronic-messages"></a>Mensajes electrónicos

La página **Mensajes electrónicos** muestra el proceso que tiene disponible para el usuario en función de su rol. Los roles de seguridad están asociados al procesamiento en la configuración de dicho procesamiento. Para cada proceso que el usuario tiene disponible, la página muestra mensajes electrónicos e información relacionada con ellos.

La ficha desplegable **Mensajes** muestra mensajes electrónicos para el procesamiento seleccionado. En función del estado del mensaje seleccionado y del procesamiento predefinido, puede ejecutar algunas acciones usando los botones sobre la cuadrícula:

- **Nuevo** Este botón está asociado a las acciones del tipo **Crear mensaje**.
- **Eliminar** Este botón está disponible si la casilla de verificación **Permitir la cancelación** está seleccionada para el estado actual del mensaje seleccionado.
- **Recopilar datos** - Este botón está asociado con acciones del tipo **Rellenar registros**.
- **Generar informe** Este botón está asociado a acciones del tipo **Mensaje de exportación de informes electrónicos**.
- **Enviar informe** Este botón está asociado a acciones del tipo **Servicio web**.
- **Importar respuesta** - Este botón está asociado a acciones del tipo **Importar informes electrónicos**.
- **Actualizar estado** Este botón está asociado a las acciones del tipo **Procesamiento de usuario de nivel de mensaje**.
- **Elementos de mensaje** Abre la página **Elementos del mensaje electrónico**.

La ficha desplegable **Registro de acción** muestra información acerca de todas las acciones que se han ejecutado para el mensaje seleccionado. Si una acción causa un error, la información acerca del error se vinculará a la línea relacionada en la cuadrícula. Para revisar la información acerca del error, seleccione la línea de la cuadrícula y seleccione el botón **Adjuntos** (el símbolo de clip de papel) en la esquina superior derecha de la página.

La ficha desplegable **Campos adicionales de mensaje** muestra todos los campos adicionales que se han definido para los mensajes en la configuración de procesamiento. También muestra los valores de estos campos adicionales.

La ficha desplegable **Elementos de mensaje** muestra todos los elementos de mensaje relacionados con el mensaje seleccionado. En función del estado del mensaje seleccionado y del elemento, puede ejecutar algunas acciones usando los botones sobre la cuadrícula:

- **Eliminar** Este botón está disponible si la casilla de verificación **Permitir la cancelación** está seleccionada para el estado actual del elemento de mensaje seleccionado.
- **Actualizar estado** Este botón está asociado a las acciones del tipo **Procesamiento de usuario**.
- **Documento original** - Abre una página que muestra el documento original para el elemento de mensaje seleccionado.

Todos los informes que ya se han generado y se han recibido para un mensaje se adjuntan a dicho mensaje. Para revisar los adjuntos relacionados con un mensaje, seleccione el mensaje y después seleccione el botón **Adjuntos** (el símbolo de clip de papel) en la esquina superior derecha de la página.

![Botón de datos adjuntos](media/attachment-icon.png)

La página **Adjuntos** muestra todos los datos adjuntos relacionados con el mensaje seleccionado. Para ver un archivo, selecciónelo en la lista de la izquierda, y después seleccione **Abrir** en el panel de acciones.

![Botón Abrir](media/open-button.png)

También puede revisar los datos adjuntos relacionadas con una acción específico que se ejecutó anteriormente para un mensaje. En la página **Mensajes electrónicos** , seleccione el mensaje en la ficha desplegable **Mensajes** , seleccione la acción **Registro de acción** en la ficha desplegable, y seleccione el botón **Adjuntos** en la esquina superior derecha de la página.

También puede ejecutar el procesamiento entero o solo un acción específica seleccionando **Ejecutar procesamiento** en el panel de acciones.

### <a name="electronic-message-items"></a>Elementos de mensaje electrónico

La página **Elementos del mensaje electrónico** muestra todos los elementos de mensaje y un registro de las acciones que se han ejecutado para cada elemento de mensaje. También muestra los campos adicionales que se han definido para los elementos de mensaje, y los valores de estos campos adicionales.

En la tabla siguiente se describen los campos en la pestaña **Elementos de mensaje**.

<table>
<thead>
<tr>
<th>Campo</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr>
<td>En procesamiento</td>
<td>El nombre del procesamiento usado para crear el elemento de mensaje.</td>
</tr>
<tr>
<td>Elemento de mensaje</td>
<td>Identificador del elemento de mensaje. Este identificador se asigna automáticamente, en función de la secuencia numérica del <strong>elemento de mensaje</strong> que se define en la página <strong>Parámetros de contabilidad general</strong>.</td>
</tr>
<tr>
<td>Fecha de elemento de mensaje</td>
<td>La fecha de creación del elemento de mensaje.</td>
</tr>
<tr>
<td>Tipo de elemento de mensaje</td>
<td>El tipo de elemento de mensaje. Se pueden configurar varios tipos de elementos de mensaje para el mismo procesamiento (por ejemplo, <strong>Facturas de entrada</strong> y <strong>Facturas salientes</strong>). Este campo se puede rellenar automáticamente solo si una factura se agrega a la tabla de elementos de mensaje.</td>
</tr>
<tr>
<td>Estado de elemento de mensaje</td>
<td>El estado real del elemento de mensaje. Los estados disponibles varían, en función del tipo de elemento de mensaje. A continuación se incluyen algunos ejemplos:
<ul>
<li><strong>Rellenado</strong> – Un registro se ha agregado a la tabla de elementos de mensaje.</li>
<li><strong>Evaluado</strong> – Los atributos adicionales se calcularon para el elemento de mensaje.</li>
<li><strong>Notificado</strong> – El elemento de mensaje se ha agregado correctamente a un informe.</li>
<li><strong>Excluido</strong> – Este estado puede ser útil si se deben excluir algunos elementos de mensaje del informe antes de que se exporte.</li>
</ul>
</td>
</tr>
<tr>
<td>Fecha de transmisión</td>
<td>Para el procesamiento que transmite automáticamente un informe generado fuera del sistema, la fecha en la que el elemento de mensaje se transmite.</td>
</tr>
<tr>
<td>Número de documento</td>
<td>Este campo se rellena automáticamente en función de la configuración de la acción de llenar registros. Este campo se puede rellenar automáticamente solo si una factura se agrega a la tabla de elementos de mensaje.</td>
</tr>
<tr>
<td>Número de cuenta</td>
<td>El número de cuenta de un cliente o proveedor (u otro valor de campo, en función del campo que se define en la acción rellenar registros). Este campo se puede rellenar automáticamente solo si una factura se agrega a la tabla de elementos de mensaje.</td>
</tr>
<tr>
<td>Mensaje</td>
<td>El número del mensaje. Este número se asigna automáticamente, en función de la secuencia numérica del <strong>mensaje</strong> que se define en la página <strong>Parámetros de contabilidad general</strong>.</td>
</tr>
<tr>
<td>Estado del mensaje</td>
<td>El estado real del mensaje electrónico.</td>
</tr>
<tr>
<td>Acción siguiente</td>
<td>Los siguientes acciones que se pueden iniciar para el estado actual del elemento de mensaje.</td>
</tr>
</tbody>
</table>

La pestaña **Campos adicionales** muestra los campos adicionales del emento del mensaje seleccionado, y sus valores.

#### <a name="run-processing"></a>Ejecutar procesamiento

Seleccione **Ejecutar procesamiento** en el panel de acciones para ejecutar el procesamiento para los elementos de mensaje. Para ejecutar una acción específica, en el cuadro de diálogo **Ejecutar procesamiento** establezca la opción **Elegir acción** en **Sí**, y después seleccione una acción. Para ejecutar el procesamiento entero, deje la opción **Elegir acción** en **No**.

#### <a name="generate-report"></a>Generar informe

Seleccione **Generar informe** en el panel de acciones para generar un informe. Este botón está asociado a acciones del tipo **exportación de informes electrónicos**.

#### <a name="update-status"></a>Actualizar estado

Seleccione **Actualizar estado** en el panel de acciones para actualizar el estado de uno o más elementos de mensaje. En el cuadro **Actualizar estado** , use la ficha desplegable **Registros para incluir** para seleccionar los elementos de mensaje a actualizar. Asegúrese de que se definan correctamente los criterios de selección, porque se actualizarán los estados del elemento de mensaje en función de estos criterios, el estado inicial de la acción seleccionada, y el valor **Nuevo estado** que especifique. Tras realizar una actualización del estado, es difícil determinar qué elementos se han actualizado. Por lo tanto, es difícil revertir las actualizaciones de estado.

#### <a name="electronic-messages"></a>Mensajes electrónicos

Seleccione **Mensajes electrónicos** en el panel de acciones para revisar un mensaje electrónico que esté relacionado con el elemento del mensaje seleccionado.

También puede revisar todos los archivos relacionados a un elemento de mensaje específico. Seleccione el campo **Mensaje** para el elemento de mensaje, o seleccione **Mensajes electrónicos** en el panel de acciones. Entonces en la página **Mensaje electrónico**, seleccione el mensaje del que se revisarán archivos y después seleccione el botón **Adjuntos** (el símbolo de clip de papel) en la esquina superior derecha de la página.

![Botón de datos adjuntos](media/attachment-icon.png)

La página **Datos adjuntos** muestra todos los datos adjuntos relacionados con el mensaje. Para ver un archivo, selecciónelo en la lista de la izquierda, y después seleccione **Abrir** en el panel de acciones.

![Botón Abrir](media/open-button.png)

#### <a name="original-document"></a>Documento original

Seleccione **Documento original** en el panel de acciones para abrir el documento original para el elemento del mensaje seleccionado.

## <a name="example-set-up-and-run-processing-to-call-a-simple-er-exporting-format-to-generate-an-excel-report"></a>Ejemplo: Configurar y ejecutar un procesamiento para llamar a un formato de exportación ER simple para generar un informe de Excel

Una vez que haya creado el formato de ER, lo haya asignado a orígenes de datos, y lo haya completado, puede ejecutarlo mediante el espacio de trabajo **Informes electrónicos**. Se genera un informe que puede guardar localmente.

Para controlar los siguientes aspectos del proceso de informes, debe configurar procesos de correo electrónico:

- Registrar información sobre la persona que generó el informe.
- Registrar información sobre cuándo se generó el informe.
- Guardar los informes generados para períodos anteriores.

Esta sección proporciona un ejemplo que muestra cómo puede configurar mensajes electrónicos para generar un informe basado en un formato de ER de exportación para Excel. Si quiere seguir este ejemplo, el formato de exportación de Excel de ER debe haberse creado, asignado a orígenes de datos, y completado ya. Además, una secuencia numérica se debe haber configurado para los mensajes electrónicos.

Al compilar el procesamiento, resulta útil definir primero las acciones y los estados del proceso que se configurarán. La ilustración siguiente muestra lo que parece el procesamiento en este ejemplo.

![Esquema de procesamiento](media/processing-scheme.png)

#### <a name="create-message-statuses"></a>Crear estados de mensajes

1. Vaya a **Impuestos \> Configuración \> Mensajes electrónicos \> Estados de mensaje**.
2. Cree los estados del mensaje siguientes:

    - Nueva
    - Preparado
    - Generadas

    ![Estados de mensaje](media/message-statuses.png)

3. En la línea del estado **Nuevo** , seleccione la casilla de verificación **Permitir la cancelación** para permitir a los usuarios borrar los mensajes que tengan este estado.

#### <a name="create-additional-fields"></a>Crear campos adicionales

1. Vaya a **Impuestos \> Configuración \> Mensajes electrónicos \> Campos adicionales**.
2. Agregue un campo adicional y sus valores. He aquí un ejemplo.

    ![Campos adicionales](media/additional-fields.png)

3. Establezca la opción **Edición del usuario** en **Sí** para permitir a los usuarios editar el campo.

#### <a name="create-message-processing-actions"></a>Crear acciones de procesamiento de mensajes

Para este ejemplo, cree las siguientes acciones:

- **Crear mensaje**
- **Actualizar a preparado**
- **Generar informe**
- **Actualización al estado inicial** (opcional)

1. Vaya a **Impuestos \> Configuración \> Mensajes electrónicos \> Acciones de procesamiento de mensajes**.
2. Crear una acción que se llama **Crear el mensaje**. En la ficha desplegable **General** , en el campo **Tipo de acción** , seleccione **Crear el mensaje**.
3. Cree una acción que se llama **Actualizar a preparado**, y establezca los siguientes campos:

    - En la ficha desplegable **General** , en el campo **Tipo de acción** , seleccione **Procesamiento de usuario de nivel de mensaje**.
    - En la ficha desplegable **Estados iniciales** , en el campo **Estado del mensaje** , seleccione **Nuevo**.
    - En la ficha desplegable **Estados de resultado** , en el campo **Estado del mensaje** , seleccione **Preparado**. En el campo **Tipo de respuesta** , especifique **Ejecutado correctamente**.

4. Cree una acción que se llama **Generar informe**, y establezca los siguientes campos:

    - En la ficha desplegable **General** , en el campo **Tipo de acción** , seleccione **Exportación de informes electrónicos**. En el campo **Asignación de formato** , seleccione el formato de ER de exportación. Las opciones son **Excel**, **XML**, **JSON**, **Text**, y **Otros**.
    - En la ficha desplegable **Estados iniciales** , en el campo **Estado del mensaje** , seleccione **Preparado**.
    - En la ficha desplegable **Estados de resultado** , en el campo **Estado del mensaje** , seleccione **Generado**. En el campo **Tipo de respuesta** , especifique **Ejecutado correctamente**.

    ![Generar acción de informe](media/generate-report-action.png)

5. Opcional: Para que los usuarios puedan volver a generar un informe varias veces, puede crear una acción **Actualización a estado inicial** y establecer los campos siguientes:

    - En la ficha desplegable **General** , en el campo **Tipo de acción** , seleccione **Procesamiento de usuario de nivel de mensaje**.
    - En la ficha desplegable **Estados iniciales** , en el campo **Estado del mensaje** , seleccione **Generado**.
    - En la ficha desplegable **Estados de resultado**, agregue una línea independiente para cada uno de los dos estados del mensaje (**Preparado** y **Nuevo**). Para las dos líneas, establezca el campo **Tipo de respuesta** en **Ejecutado correctamente**.

#### <a name="electronic-message-processing"></a>Procesamiento de mensaje electrónico

En este ejemplo, todas las acciones deben configurarse para que ejecuten por separado. Se presupone que cada acción será inicializada por el usuario.

1. Vaya a **Impuestos \> Configuración \> Mensajes electrónicos \> Procesamiento de mensaje electrónico**.
2. Agregue un registro para su procesamiento, y agregue todas las acciones definidas previamente y un campo adicional.
3. Opcional: en la ficha desplegable **Roles de seguridad** , defina los roles de seguridad para que su procesamiento limite el acceso al informe específico.
4. Vaya a **Impuestos \> Consultas e informes \> Mensajes electrónicos \> Mensajes electrónicos**.
5. Seleccione **Nuevo** para crear un mensaje. En este punto, puede agregar fechas y una descripción. También puede actualizar el valor del campo adicional como sea necesario.

    ![Crear un mensaje electrónico](media/create-electronic-message.png)

La cuadrícula de la ficha desplegable **Registro de acción** se completa automáticamente con un registro de todas las acciones que se realizan en el mensaje.

Ahora puede eliminar o actualizar el estado del mensaje. Para actualizar el estado del mensaje, seleccione **Actualizar estado**. En el campo **Nuevo estado** , seleccione **Preparado**, y después seleccione **Aceptar**.

![Actualizar el estado del mensaje](media/update-status.png)

El estado del mensaje se actualiza a **Preparado**, y ahora puede generar el informe seleccionando **Generar informe**. Se genera el informe, y el estado del mensaje y el registro de acción se actualizan. Para ver el informe generado, seleccione el botón **Adjuntos** (el símbolo de clip de papel) en la esquina superior derecha de la página.
