---
title: Configurar mensajes electrónicos
description: Este tema proporciona información sobre cómo configurar la funcionalidad de mensajes electrónicos (EM).
author: liza-golub
ms.date: 07/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: ''
ms.search.region: Global
ms.author: elgolu
ms.search.validFrom: 2021-06-23
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 2b62efabfae26a6cc004604e687a49bce992d78a30f0d441aa74fa5cde70e063
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6752184"
---
# <a name="set-up-electronic-messages"></a>Configurar mensajes electrónicos

[!include [banner](../includes/banner.md)]

La funcionalidad de **mensajes electrónicos** (EM) ayuda a mantener varios procesos electrónicos de informes para distintos tipos de documentos. En algunos escenarios complejos que admiten [caracerísticas de informes específicas del país o la región](electronic-messaging.md#country-specific-regulatory-features-supported-by-the-em-functionality) la funcionalidad de EM se configura para que tenga una combinación de muchos estados de mensajes, estados de elementos de mensaje, acciones, más campos, y clases ejecutables. Para estos casos, los paquetes de entidades de los datos están disponibles para la importación. Si usa estos paquetes de entidad de datos, impòrtelos a una entidad jurídica mediante la herramienta de administración de datos. Para obtener más información sobre cómo usar la herramienta de gestión de datos, vea [Administración de datos](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).

Si no importa un paquete de entidad de datos, puede configurar manualmente la funcionalidad de EM. En tal caso, debe configurar los elementos siguientes:

- [Secuencias numéricas](#sequences)
- [Tipos de elementos de mensaje](#types)
- [Estados de elemento de mensaje](#item)
- [Estados de mensaje](#statuses)
- [Campos adicionales](#additional)
- [Configuración de clase ejecutable](#executable)
- [Acciones de llenado de registros](#populate)
- [Aplicaciones web](#applications)
- [Configuración de servicio web](#settings)
- [Acciones de procesamiento de mensajes](#actions)
- [Procesamiento de mensaje electrónico](#processing)

En las secciones siguientes se ofrece más información acerca de cada uno de estos elementos.

## <a name="number-sequences"></a><a id="sequences"></a>Secuencias numéricas

Configure secuencias numéricas para los mensajes y los elementos de mensaje. Luego, las secuencias numéricas se usan para numerar automáticamente los mensajes y los elementos de mensaje. Los números que se asignan se usan como identificadores únicos de los mensajes y los elementos de mensaje en el sistema. Puede configurar secuencias numéricas para mensajes electrónicos yendo a **Contabilidad general** \> **Configuración de contabilidad** \> **Parámetros de contabilidad general**.

## <a name="message-item-types"></a><a id="types"></a>Tipos de elementos de mensaje

Los tipos de elementos de mensaje identifican los tipos de registros que se usan en los mensajes electrónicos. Puede configurar los tipos de elementos del mensaje yendo a **Impuestos** \> **Configuración** \> **Mensajes electrónicos** \> **Tipos de elementos de mensaje**.

## <a name="message-item-statuses"></a><a id="item"></a>Estados de elemento de mensaje

Los estados del elemento de mensaje identifican los estados que se aplican a los elementos del mensaje en el proceso que está configurando. Puede configurar los estaods de elementos del mensaje yendo a **Impuestos** \> **Configuración** \> **Mensajes electrónicos** \> **Estados de elementos de mensaje**.

El parámetro **Permitir la cancelación** de un estado de elemento de mensaje define si puede eliminar elementos de mensaje con este estado mediante la página **Mensajes electrónicos** o la página **Elementos del mensaje electrónico**.

## <a name="message-statuses"></a><a id="statuses"></a>Estados de mensaje

Configure los estados del mensaje que deben estar disponibles en el procesamiento de mensajes. Puede configurar los estados de mensaje yendo a **Impuestos** \> **Configuración** \> **Mensajes electrónicos** \> **Estados de mensaje**.

En la tabla siguiente se describen los campos en la página **Estados del mensaje**.

| Nombre del campo          | Descripción |
|---------------------|-------------|
| Estado del mensaje      | Especificar un nombre único para el estado del mensaje. Los estados del mensaje se usan para caracterizar al estado de un mensaje electrónico en cada momento. El nombre que especifique se muestra en la página **Mensajes electrónicos** y en un registro que está relacionado con los mensajes electrónicos. |
| Descripción         | Introduzca una descripción del estado de mensaje. |
| Tipo de respuesta       | Seleccione el tipo de respuesta para el estado de mensaje. Algunas acciones en un proceso pueden producir más de un tipo de respuesta. Por ejemplo, una acción del tipo **Servicio web** puede producir respuestas del tipo **Ejecutado correctamente** o el tipo **Error técnico** en función del resultado de su ejecución. En este caso, defina los estados de mensaje para ambos tipos de respuesta. Para más información sobre los tipos de acción y sus tipos de respuesta relacionados, consulte la sección [Tipos de acción de procesamiento de mensajes](#action-types) más adelante en este tema. |
| Estado de elemento de mensaje | En ocasiones, el estado de un mensaje electrónico debe afectar al estado de los artículos de mensaje relacionados. Seleccione un estado de artículo del mensaje en este campo para asociarlo al estado del mensaje. |
| Permitir eliminación        | Seleccione esta casilla si los usuarios pueden borrar los mensajes electrónicos que tengan este estado en la página **Mensajes electrónicos**. |

## <a name="additional-fields"></a><a id="additional"></a>Campos adicionales

La funcionalidad EM le permite recopilar registros de tablas transaccionales en Microsoft Dynamics 365 Finance como elementos de mensaje. De esta manera, puede preparar los registros para informar y luego informarlos. Sin embargo, las tablas transaccionales no tienen a veces suficiente información para completar los registros de una forma que cumplan los requisitos de informes. Para completar toda la información que se debe notificar para un registro, puede configurar campos adicionales. Los campos adicionales se pueden asociar con mensajes y elementos de mensaje. Puede configurar campos adicionales yendo a **Impuestos** \> **Configuración** \> **Mensajes electrónicos** \> **Campos adicionales**.

En la tabla siguiente se describen los campos generales en la página **Campos adicionales**.

| Campo       | Descripción |
|-------------|-------------|
| Nombre de campo  | Escriba el nombre de un campo adicional para los mensajes electrónicos o elementos de mensaje relacionados con el proceso. Este nombre aparece en la interfaz de usuario (IU) mientras trabaja con el proceso. El nombre también se puede usar en configuraciones de informes electrónicos (ER) relacionadas con el proceso. |
| Descripción | Indique una descripción para el campo adicional. |
| Edición de usuario   | Establezca esta opción en **Sí** si los usuarios pueden cambiar el valor del campo adicional en la interfaz de usuario. |
| Contador     | Establezca esta opción en **Sí** si el campo adicional debe contener una secuencia numérica en un mensaje electrónico. El valor del campo adicional se rellenará automáticamente cuando se ejecute una acción de tipo **Exportación de informes electrónicos**. |
| Oculto      | Establezca esta opción en **Sí** si el campo adicional debe estar oculto en la interfaz de usuario en la página **Mensajes electronicos** o la página **Elementos de mensaje electrónico**. |

En la ficha desplegable **Valores**, puede predefinir los valores que puede tener un campo adicional. Estos valores están disponibles para que los usuarios los seleccionen. Por lo tanto, no es necesario completarlos manualmente durante el procesamiento. En la siguiente tabla se describen los campos.

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

## <a name="executable-class-settings"></a><a id="executable"></a>Configuración de clase ejecutable

Una clase ejecutable es un método o clase X++ que el procesamiento de mensajes electrónicos puede llamar en relación con una acción si se requiere evaluación para el proceso.

Puede configurar manualmente una clase ejecutable que se debe llamar durante el procesamiento yendo a **Impuesto** \> **Configuración** \> **Mensajes electronicos** \> **Configuración de clase ejecutable**. Sobre la página **Configuración de clase ejecutable**, cree una línea y configure los siguientes campos.

| Campo                 | Descripción |
|-----------------------|-------------|
| Clase ejecutable      | Escriba el nombre que se usará durante la configuración de una acción de procesamiento de mensajes en relación con la cual se llama esta clase. |
| Descripción           | Escriba una descripción de la clase de ejecutable. |
| Nombre de la clase ejecutable | Seleccione una clase ejecutable X++. |
| Nivel de ejecución       | Este campo se establece automáticamente, porque el valor se predefine para la clase ejecutable seleccionada. Este campo limita el nivel en que se ejecuta la evaluación relacionada. |
| Descripción de la clase     | Este campo se establece automáticamente, porque el valor se predefine para la clase ejecutable seleccionada. |
| Tipo de acción           | Este campo está disponible cuando la característica **\[EM\] Tipo de acción de clase ejecutable** está activada en el espacio de trabajo **Gestión de funciones**. Utilice este campo para especificar el tipo de acción para la clase ejecutable. Este campo proporciona un control más preciso sobre las próximas acciones que están disponibles para el mensaje electrónico en la página **Mensajes electronicos**. |

Algunas clases ejecutables pueden tener parámetros obligatorios que se deben definir antes de que la clase ejecutable se ejecute por primera vez. Para definir estos parámetros, en el Panel de acciones, seleccione **Parámetros**. En el cuadro de diálogo que aparece, establezca los campos y luego seleccione **Aceptar**. Es importante que se seleccione **Aceptar**. De lo contrario, los parámetros no se guardarán en la base de datos, y la clase ejecutable no será llamada correctamente.

## <a name="populate-records-actions"></a><a id="populate"></a>Acciones de llenado de registros

Las acciones de llenado de registros se usan para configurar acciones para agregar registros a la tabla de elementos de mensaje de forma que se puedan agregar a un mensaje electrónico. Por ejemplo, si el mensaje electrónico debe notificar facturas de cliente, debe configurar una acción de popular registros que esté vinculada al campo **Origen de datos** en la tabla Diario de facturas del cliente.

Puede configurar acciones de llenado de registros yendo a **Impuestos** \> **Configuración** \> **Mensajes electrónicos** \> **Acciones de llenado de registros**. Cree un registro nuevo para cada acción que debe agregar registros a la tabla, y establezca los campos siguientes.

| Campo       | Descripción |
|-------------|-------------|
| Nombre        | Escriba un nombre para la acción que rellena registros en su proceso. |
| Descripción | Especifique una descripción de la acción rellenar registros. |

En la ficha desplegable **Configuración de orígenes de datos**, agregue una línea para cada origen de datos usado para el proceso, y establezca los campos siguientes.

| Campo                  | Descripción |
|------------------------|-------------|
| Nombre                   | Escriba un nombre para el origen de datos. |
| Tipo de elemento de mensaje      | Seleccione el tipo de elemento de mensaje que se debe usar cuando los registros se crean para el origen de datos. |
| Tipo de cuenta           | Seleccione el tipo de cuenta para asociar a los registros desde el origen de datos. |
| Nombre de la tabla principal      | Seleccione la tabla que será un origen de datos. |
| Campo de número de documento  | Seleccione el campo de dónde se tomará el número de documento en la tabla maestra seleccionada. El valor de este campo se utiliza como el valor del campo **Número del documento** para el elemento de mensaje. |
| Campo de fecha de documento    | Seleccione el campo de dónde se tomará la fecha de documento en la tabla maestra seleccionada. El valor de este campo se utiliza como el valor del campo **Fecha de elemento de mensaje** para el elemento de mensaje. |
| Campo de cuenta de documento | Seleccione el campo de dónde se tomará la cuenta de documento en la tabla maestra seleccionada. El valor de este campo se utiliza como el valor del campo **Número de cuenta** para el elemento de mensaje. |
| Empresa                | Este campo está disponible cuando la función **Consultas entre empresas para las acciones de rellenar registros** está activada en el espacio de trabajo **Gestión de funciones**. Utilice esta función para configurar fuentes de datos entre empresas para las acciones de rellenar registros. Los datos se pueden obtener de varias empresas. |
| Consulta de usuario             | <p>Si configura una consulta seleccionando **Editar consulta** encima de la cuadrícula y usted especifica los criterios que deben aplicarse a la tabla maestra seleccionada desde la que se completan los datos, esta casilla de verificación se selecciona automáticamente. Si no, todos los registros se rellenan desde el origen de la tabla maestra seleccionada.</p><p>Cuando la función **Consultas entre empresas para las acciones de rellenar registros** está activada en el espacio de trabajo **Gestión de funciones** y los registros deben recopilarse de varias empresas, agregue una línea para cada entidad legal adicional que deba incluirse en los informes. Para cada nueva línea, seleccione **Editar consulta** y especifique un criterio relacionado que sea específico de la entidad jurídica que se especifica en el campo **Empresa** en la línea. Cuando haya terminado, la cuadrícula **Configuración de fuentes de datos** contendrá líneas para todas las entidades legales que deben incluirse en los informes.</p> |

## <a name="web-applications"></a><a id="applications"></a>Aplicaciones web

Use los valores de la aplicación web para configurar una aplicación web de modo que admita Open Authorization (OAuth) 2.0. OAuth es el estándar abierto que permite a los usuarios conceder "acceso seguro delegado” a la aplicación en su nombre, sin compartir sus credenciales de acceso. También puede pasar por el proceso de autorización obteniendo un código de autorización y un token de acceso. Puede configurar los parámetros de aplicaciones web yendo a **Impuestos** \> **Configuración** \> **Mensajes electrónicos** \> **Aplicaciones Web**.

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
| El token de acceso expirará en  | El tiempo restante antes de que el símbolo de acceso venza. Este campo se actualiza automáticamente. | 
| Aceptar                       | Especifique la propiedad **Aceptar** de solicitud web. Por ejemplo, introduzca **application/vnd.hmrc.1.0+json**. |
| Tipo de contenido                 | Especifique el tipo de contenido. Por ejemplo, introduzca **application/json**. |

Además, los siguientes botones están disponibles en el panel de acciones de la página **Aplicaciones Web** para admitir el proceso de autorización:

- **Obtener código de autorización** - Inicializa la autorización de la aplicación web. Esta función utiliza el formato ER que se especifica en el campo **Asignación de formato de autorización** para generar una solicitud de autorización.
- **Obtener token de acceso** - Inicializa el proceso de obtención de un token de acceso.
- **Actualizar token de acceso** - Actualiza un token de acceso. Esta función utiliza el formato ER que se especifica en el campo **Importar mapeo de modelo de token** para importar información sobre el token de acceso recibido.

Cuando un token de acceso a una aplicación web se almacena en la base de datos del sistema, está en formato cifrado que se puede usar para las solicitudes a un servicio web. Por motivos de seguridad el acceso al token se debe limitar a los roles de seguridad a los que se permiten para tratar dichas solicitudes. Si alguien de fuera del grupo de seguridad intenta dirigir una solicitud, recibirán un error informando de que no tienen permiso para interoperar usando la aplicación web seleccionada. Para configurar los roles de seguridad que tienen acceso al token de acceso, use la ficha desplegable **Roles de seguridad** en la página **Aplicaciones Web**. Si los roles de seguridad no se definen para una aplicación Web, solo un administrador del sistema podrá interoperar usando la aplicación Web.

Para cada acción con la aplicación web seleccionada, la ficha desplegable **Registro de Acción** guarda información sobre el usuario y la fecha y la hora.

Algunos servicios web pueden requerir que se incluyan diferentes encabezados en las solicitudes. El administrador del sistema puede configurar encabezados adicionales y sus valores en la ficha desplegable **Encabezados suplementarios** y luego utilícelos durante la generación de solicitudes.

## <a name="web-service-settings"></a><a id="settings"></a>Configuración de servicio web

Use los valores de servicio Web para configurar la transmisión de datos directa a un servicio web. Puede configurar los parámetros del servicio web yendo a **Impuestos** \> **Configuración** \> **Mensajes electrónicos** \> **Configuración de servicio Web**.

En la tabla siguiente se describen los campos en la página **Configuración de servicio web**.

| Campo                          | Descripción |
|--------------------------------|-------------|
| Servicio web                    | Escriba un nombre para el servicio Web. |
| Descripción                    | Especificar una descripción del servicio web. |
| Dirección de Internet               | <p>Permite especificar la dirección del servicio Web. Si una aplicación web se especifica para un servicio Web y si la dirección de Internet del servicio Web tiene que ser la misma que la que se ha definido para la aplicación Web seleccionada, seleccione **Copiar URL base**. Luego, la URL base de la aplicación web se copia en este campo.</p><p>**Advertencia:** Los servicios de terceros u otros servicios que configure aquí no requieren certificación y es posible que no cumplan con los estándares de privacidad de Microsoft. Debe revisar la documentación de privacidad de cada servicio y trabajar con cada proveedor de servicios para obtener más información sobre el nivel de cumplimiento que brinda su servicio. Usted es responsable de garantizar que estos servicios cumplan con sus estándares legales, de seguridad y privacidad. El usuario es el único responsable del uso de los servicios. Microsoft no concede ninguna garantía expresa, garantía o condición. Recomendamos encarecidamente que utilice solo servicios que brinden conexiones seguras y autorizadas, como HTTPS.</p> |
| Certificado                    | Seleccionar un certificado de Azure Key Vault que se ha configurado previamente. |
| Aplicación Web                | Seleccionar una aplicación web que se ha configurado previamente. |
| Tipo de respuesta – XML        | Establezca esta opción en **Sí** si el tipo de respuesta es XML. |
| Método de solicitud                 | Especifique el método de la solicitud. HTTP define un conjuntos de métodos de solicitud que indican la acción que se debe realizar para un recurso determinado. El método de solicitud puede ser **GET**, **POST**, o bien otro método HTTP. |
| Encabezados de solicitud                | Especifique los encabezados de solicitud. Un encabezado de solicitud es un encabezado HTTP que se puede utilizar en una solicitud HTTP. No está relacionado con el contenido del mensaje. |
| Aceptar                         | Especifique la propiedad accept de la solicitud web. |
| Aceptar codificación                | Especifique el valor accept-encoding. El encabezado HTTP de solicitud Accept-Encoding hace publicidad de codificación de contenido que el cliente puede entender. Esta codificación de contenido es normalmente un algoritmo de compresión. |
| Tipo de contenido                   | Especifique el tipo de contenido. El encabezado HTTP de la entidad del tipo de contenido indica el tipo de medio del recurso. |
| Código de respuesta correcto       | Especifique el código de estado HTTP que indica que la solicitud ha sido correcta. |
| Asignación de formato de encabezados de solicitud | Seleccione el formato de ER que se usa para generar la petición Web de encabezados. |

## <a name="message-processing-actions"></a><a id="actions"></a>Acciones de procesamiento de mensajes

Las acciones de procesamiento de mensajes se usan para crear acciones para los procesos y para configurar los parámetros. Puede configurar acciones de procesamiento de mensajes yendo a **Impuestos** \> **Configuración** \> **Mensajes electrónicos** \> **Acciones de procesamiento de mensajes**.

Las siguientes tablas describen los campos de la página **Acciones de procesamiento de mensajes**.

### <a name="general-fasttab"></a>Ficha desplegable General

| Campo                                     | Descripción |
|-------------------------------------------|-------------|
| Tipo de acción                               | Seleccione el tipo de acción. Para obtener información acerca de las opciones disponibles, consulte la sección [Tipos de acción de procesamiento de mensajes](#action-types) más adelante en este tema. |
| Asignación de formato                            | Seleccione el formato de ER que se debe llamar para la acción. Este campo solo está disponible para las acciones de tipo **Exportación de informes electrónicos**, **Importación de informes electrónicos**, y **Mensaje de exportación de informes electrónicos** . |
| Asignación de formato para ruta URL               | Seleccione el formato de ER que se debe llamar para la acción. Este formato se usa para componer la ruta de la dirección URL que se agregará a la dirección base de Internet que se especifica para el servidor Web seleccionado. Este campo solo está disponible para las acciones del tipo **Servicio web**. |
| Tipo de elemento de mensaje                         | Seleccione el tipo de registros para los que debe evaluarse la acción. Este campo está disponible para los tipos **Nivel de ejecución de elemento de mensaje**, **Exportación de informes electrónicos**, **Importación de informes electrónicos** y **Servicio web** y otros tipos. Si deja este campo en blanco, se evalúan todos los tipos de elementos de mensaje que se definen para el procesamiento de mensajes. |
| Clase ejecutable                          | Seleccione una configuración de clase ejecutable existente. Este campo solo está disponible para las acciones del tipo **Nivel de ejecución de elemento de mensaje** y **Nivel de ejecución de elemento de mensaje**. |
| Acción de llenado de registros                   | Seleccione una acción de rellenar registros existente. Este campo solo está disponible para las acciones del tipo **Rellenar registros** . |
| Servicio web                               | Seleccione un servicio web existente. Este campo solo está disponible para las acciones del tipo **Servicio web**. |
| Nombre de archivo                                 | Especifique el nombre del archivo que será el resultado de la acción. Este archivo puede ser la respuesta del servidor Web o del informe que se ha generado. Este campo solo está disponible para las acciones de los tipos **Servicio web** y **Mensaje de la exportación del informe electrónico**. |
| Adjuntar archivos a documentos de origen          | Seleccione esta casilla de verificación para adjuntar archivos generados a registros en una tabla maestra referenciada para elementos EM. Este campo solo está disponible para las acciones de los tipos **Servicio web** y **Exportación del informe electrónico**. |
| Adjuntar archivos desde archivo de salida a elementos | Seleccione esta casilla de verificación para extraer archivos XML separados del archivo de salida y adjuntarlos a los elementos de mensaje electrónico correspondientes. Este campo solo está disponible para las acciones del tipo **Exportación del informe electrónico**. |
| Número de elementos de mensaje por exportación        | Especifique el límite en el número de elementos de mensaje que deben incluirse en un archivo (mensaje). Este campo solo está disponible para las acciones del tipo **Exportación del informe electrónico**. |
| Usar origen de ER                             | Seleccione esta casilla de verificación para utilizar los parámetros de origen de ER para la importación. De lo contrario, se utiliza el archivo adjunto del mensaje electrónico. Este campo solo está disponible para las acciones del tipo **Importación del informe electrónico**. |
| Mostrar cuadro de diálogo                               | Establezca esta opción **Sí** si se debe mostrar un diálogo a los usuarios antes de la generación del informe. Este campo solo está disponible para las acciones del tipo **Mensaje de la exportación del informe electrónico**. |

#### <a name="message-processing-action-types"></a><a id="action-types"></a>Tipo de acciones de procesamiento de mensajes

Las opciones siguientes están disponibles en el campo **Tipo de acción**:

- **Crear mensaje** - Use este tipo de acción para permitir a los usuarios manualmente crear mensajes en la página **Mensaje electrónico**. Un estado inicial no se puede configurar para una acción de este tipo.
- **Rellenar registros** - Este tipo de acción ya debe estar configurado. Asóciela con una acción para rellenar registros para habilitarla e incluirla en el procesamiento. Se presupone que se usa este tipo de acción para la primera acción del procesamiento de mensajes (cuando no se ha creado ningún mensaje electrónico por adelantado) o para una acción que agrega elementos a mensaje a un mensaje creado previamente mediante el tipo de acción **Crear mensaje**. Por lo tanto, para acciones de este tipo, el estado del resultado solo se puede configurar para elementos del mensaje. Un estado inicial se puede configurar solo para mensajes.
- **Nivel de ejecución de mensaje** - Use este tipo de acción para configurar una clase ejecutable que se debe evaluar en el nivel de mensaje.
- **Nivel de ejecución de artículo de mensaje** - Use este tipo de acción para configurar una clase ejecutable que se debe evaluar en el nivel de elemento de mensaje.
- **Exportación de informes electrónicos** Use este tipo de acción para las acciones que deben generar un informe basado en una configuración de ER de exportación en el nivel de elemento de mensaje.
- **Mensaje de exportación de informes electrónicos** - Use este tipo de acción para las acciones que deben generar un informe basado en una configuración de ER de exportación en el nivel de mensaje (por ejemplo, cuando un mensaje no tiene ningún elemento de mensaje).
- **Importación de informes electrónicos** - Use este tipo de acción para las acciones que deben generar un informe basado en una configuración de ER de importación en el nivel de elemento de mensaje.
- **Procesamiento de usuario de nivel de mensaje** Use este tipo de acción para acciones que presuponen alguna acción manual por parte del usuario a nivel de mensaje. Por ejemplo, el usuario podría actualizar el estado de los mensajes.
- **Procesamiento de usuario** - Use este tipo de acción para acciones que presuponen alguna acción manual por parte del usuario a nivel de elemento. Por ejemplo, el usuario podría actualizar el estado de los elementos de mensajes.
- **Servicio web** - Use este tipo de acción para las acciones que deben transmitir un informe generado a un servicio web. No se usa este tipo de acción para los informes italianos de comunicación de la compra y las facturas de ventas. Para este tipo de acciones, la página **Acciones de procesamiento de mensajes** incluye una ficha desplegable **Detalles varios**, donde podrá especificar un texto de confirmación. Este texto de confirmación se presenta a los usuarios antes de que las solicitudes del servicio Web seleccionado se aborden.
- **Comprobación de solicitud** - Use este tipo de acción para solicitar la comprobación desde un servidor.

### <a name="initial-statuses-fasttab"></a>Ficha desplegable Estados iniciales

> [!NOTE]
> La ficha desplegable **Estados iniciales** no está disponible para acciones que tienen un tipo inicial de acción **Crear mensaje**.

| Campo               | Descripción |
|---------------------|-------------|
| Estado de elemento de mensaje | Seleccione el estado del elemento de mensaje para el que debe evaluarse la acción de procesamiento de mensaje seleccionada. |
| Descripción         | Descripción del estado del elemento de mensaje seleccionado. |

### <a name="result-statuses-fasttab"></a>Ficha desplegable Estados de resultado

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

## <a name="electronic-message-processing"></a><a id="processing"></a>Procesamiento de mensaje electrónico

El procesamiento de mensajes electrónicos es un concepto básico de la funcionalidad de EM. Agrega las acciones que se deben evaluar para el mensaje electrónico. Las acciones se pueden vincular usando un estado inicial y un estado de resultado. Como alternativa, las acciones del tipo **Procesamiento de usuario** se pueden iniciar de forma independiente. Para configurar el procesamiento de los mensajes electrónicos, vaya a **Impuesto** \> **Configuración** \> **Mensajes electrónicos** \> **Procesamiento de mensajes electrónicos**.

La ficha desplegable **Acción** permite agregar acciones predefinidas al procesamiento. Puede especificar si una acción se debe ejecutar por separado, o si puede iniciarse por el procesamiento. Para especificar que una acción en el proceso solo puede inicializarla un usuario, establezca el campo **Funcionamiento por separado** en **Sí** para dicho acción. Si una acción debería iniciarse por el procesado de mensaje o elementos de mensaje que están en el estado definido como el estado inicial para la acción, establezca el campo **Ejecutar por separado** en **No**. Las acciones del tipo **Acción del usuario** siempre se debe ejecutar por separado.

A veces, varias acciones se deben incluir en una secuencia, aunque la primera acción esté configurada para ejecutarse por separado. Por ejemplo, un usuario debe inicializar la generación de informes. Sin embargo, inmediatamente después de generar el informe, debe enviarse al servicio Web y la respuesta del servicio Web debe reflejarse en el sistema. En este caso, puede crear una secuencia inseparable para las acciones que deben ejecutarse siempre conjuntamente. En la pestaña desplegable **Acción** , seleccione **Secuencias inseparables** encima de la cuadrícula, y cree una secuencia. A continuación, para todas las acciones que deben ejecutarse juntas en una secuencia, seleccione la secuencia en el campo **Secuencia inseparable**. Para este ejemplo, el campo **Ejecutar por separado** se puede establecer en **Sí** para la primera acción de la secuencia y en **No** para el resto de acciones.

Las acciones de los tipos **Exportación de informes electrónicos** y **Mensaje de exportación de informes electrónicos** ejecutan un formato ER que tiene parámetros de entrada. Si el procesamiento de su mensaje electrónico incluye acciones de cualquiera de esos tipos, debe especificar los valores para los parámetros de entrada antes de generar el informe. De esta forma, el sistema puede utilizar un régimen por lotes para generar el informe. Puede elegir **Parámetros** encima de la cuadrícula para configurar los parámetros para el tipo de acción seleccionado (**Exportación de informes electrónicos** o **Mensaje de exportación de informes electrónicos**). Seleccione la casilla **Usar parámetros** para la acción que debe ejecutarse con los parámetros especificados en un régimen por lotes.

Use la ficha desplegable **Campos adicionales de elemento de mensaje** para agregar campos adicionales predefinidos relacionados con los elementos del mensaje. Debe agregar campos adicionales para cada tipo de elemento de mensaje con el que los campos están relacionados. Puede especificar un valor predeterminado que se asignará al campo adicional durante el procesamiento.

Use la ficha desplegable **Campos adicionales de elemento de mensaje** para agregar campos adicionales predefinidos relacionados con los mensajes. Puede especificar un valor predeterminado que se asignará al campo adicional durante el procesamiento.

Use la ficha desplegable **Roles de seguridad** para configurar los roles de seguridad que están predefinidos en el sistema para el procesamiento específico. Los usuarios con un rol específico solo verán el procesamiento definido para dicho rol.

Use la ficha desplegable **Lote** para configurar el procesamiento para que funcione en un régimen por lotes. Le recomendamos que configure un régimen por lotes para su procesamiento directamente en la página **Mensajes electronicos** o **Elementos de mensaje electrónico**, cuando selecciona **Ejecutar procesamiento** en el panel Acción para iniciar el procesamiento.
