---
title: Trabajar con configuraciones de características
description: Este artículo explica cómo configurar las características de Facturación electrónica.
author: dkalyuzh
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 23466a53bb8ba597503aaa12d41395fc82b9f14e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904336"
---
# <a name="work-with-feature-setups"></a>Trabajar con configuraciones de características

[!include [banner](../includes/banner.md)]

Para configurar la generación de archivos electrónicos y otros pasos de procesamiento (por ejemplo, firmar archivos digitalmente, enviarlos al servicio web de la administración pública y recibir una respuesta o almacenarlos), configure la canalización de procesamiento, las reglas de aplicabilidad y las variables para características de Facturación electrónica.

La información de configuración se combina en el concepto de *configuración de características*, y se puede crear, eliminar, ajustar. Para las versiones completas de las características de Facturación electrónica, también se puede ver la información.

Puede crear tantos elementos de configuración de características como necesite para definir diferentes escenarios para generar, procesar y recibir archivos electrónicos. Aunque estos elementos de configuración de características tienen acciones de procesamiento y condiciones de ejecución independientes, se crean como parte de una sola característica de Facturación electrónica y heredan su ciclo de vida y proceso de implementación.

## <a name="add-a-feature-setup"></a>Agregar un configuración de característica

1. Inicie sesión en su cuenta del Servicio de configuración reguladora (RCS).
2. En el espacio de trabajo **Características de globalización**, en la sección **Características**, seleccione el mosaico **Facturación electrónica**.
3. En la página **Características de facturación electrónica**, seleccione una versión de característica de facturación electrónica que tenga un estado de **Borrador**.
4. En la pestaña **Configuraciones**, seleccione **Agregar**.
5. En el cuadro de diálogo **Crear configuración de características**, en el grupo del campo **Nuevo**, seleccione una de las siguientes opciones.
 
    - **Configuración personalizada**: cree una nueva configuración de características que tenga canales vacíos, una lista de canalización de procesamiento vacía, una sección vacía para las reglas de aplicabilidad y un conjunto predeterminado de variables, según el tipo de configuración.
    - **Desde la configuración de características**: cree una copia de otra configuración de características en el ámbito de la característica Facturación electrónica actual.

6. Si ha seleccionado la opción **Configuración personalizada** en el último paso, escriba un nombre y una descripción del elemento de configuración de características y luego, en el grupo de campos **Tipo de configuración**, seleccione una de las siguientes opciones:

    - **Canalización de procesamiento**: seleccione esta opción para generar y procesar documentos electrónicos salientes. Para este tipo de configuración, el sistema crea una lista de canalización de procesamiento vacía, una sección vacía para reglas de aplicabilidad y un conjunto predeterminado de variables. No podrá trabajar con los canales para documentos electrónicos entrantes.
    - **Canal de datos**: seleccione esta opción para configurar el proceso de recepción de documentos electrónicos entrantes desde uno de los canales definidos y analizarlos directamente en Microsoft Dynamics 365 Finance o Dynamics 365 Supply Chain Management sin acciones adicionales. Para este tipo de configuración, el sistema crea una lista predefinida de parámetros para canales de datos, una sección vacía para reglas de aplicabilidad y un conjunto de variables predeterminadas. No podrá agregar ninguna acción en la canalización de procesamiento.
    - **Canal de datos y canalización de procesamiento**: este tipo de configuración se parece al tipo de configuración **Canal de datos**. Sin embargo, antes de que un documento electrónico entrante pase a Finance o Supply Chain Management, puede configurar acciones adicionales en la canalización de procesamiento.

7. Si seleccionó la opción **Canal de datos** o **Canal de datos y canalización de procesamiento** en el último paso, en el campo **Seleccionar canal de datos**, debe seleccionar el canal con el que integrará.
8. Seleccione **Crear**.

Después de crear una configuración de características, puede seleccionar **Editar** para configurarla.

## <a name="edit-a-feature-setup"></a>Editar un configuración de característica

Según el tipo de configuración de características, puede configurar el proceso de generar archivos electrónicos salientes y enviarlos a canales externos, o recibir documentos entrantes y pasarlos a su aplicación de Finance o Supply Chain Management.

### <a name="data-channel"></a>Canal de datos

Un *canal de datos* toma el archivo electrónico y lo procesa o lo pasa directamente a Finance o Supply Chain Management. Esta opción no está disponible para configuraciones de características del tipo **Canalización de procesamiento**.

Para configurar un canal de datos, escriba el nombre del canal. Luego defina los parámetros, según el tipo de canal seleccionado. El identificador del canal de datos debe hacer referencia a la variable que se crea específicamente para identificar el canal de datos. Se utilizará como referencia en Finance o Supply Chain Management.

En la pestaña **Filtro de archivos adjuntos**, debe definir un conjunto de filtros para obtener archivos específicos del canal. Puede crear varias líneas si espera que los archivos tengan diferentes extensiones de nombre de archivo, o si los archivos deben procesarse de manera diferente según el nombre de archivo. Estos son los principales parámetros:

- **Nombre** : escriba el nombre del archivo al que el sistema hará referencia durante el procesamiento. En las aplicaciones Finance y Supply Chain Management, podrá ver los archivos en el registro de envío.
- **Filtro**: defina el filtro para seleccionar archivos.
- **Opcional**: si esta casilla no está seleccionada, se requiere el archivo. En este caso, el sistema mostrará un mensaje de error si los canales no contienen archivos que correspondan al filtro. Este parámetro es aplicable a correos electrónicos.

Si el canal es un buzón y un correo electrónico entrante contiene varios archivos adjuntos, puede configurar reglas para definir cómo el servicio debe manejar los archivos adjuntos. El servicio puede considerar cada archivo adjunto como una factura electrónica independiente, o puede tratar un archivo adjunto como una factura principal y todos los demás archivos adjuntos como adiciones.

### <a name="processing-pipeline"></a>Procesamiento de canalización

Una *canalización de procesamiento* es un conjunto de *acciones* que se ejecutan secuencialmente hasta que se completan correctamente. Puede usar una canalización de procesamiento para configurar el proceso para generar archivos electrónicos y realizar otros pasos (por ejemplo, firmar archivos digitalmente, enviarlos a servicios web externos y analizar la respuesta, y recibir y procesar documentos entrantes).

La lista de acciones está predefinida. Puedes usar los botones **Nuevo** y **Borrar** para especificar la combinación de acciones que define lógicamente el proceso requerido para enviar o recibir documentos.

El orden de las acciones es importante. Puede ajustar el orden mediante los botones **Arriba** y **Abajo**.

Cada acción tiene un conjunto de parámetros que puede configurar o ajustar. El conjunto específico de parámetros depende del tipo de acción.

- **Acción**: seleccione el tipo de acción.
- **Nombre de acción**: especifique el nombre de la acción. Este nombre aparecerá en los registros de envío y en los mensajes de las aplicaciones de Finance y Supply Chain Management.
- **Descripción**: proporcione más detalles sobre el propósito de la acción en el proceso.
- **Habilitar reintento**: si selecciona esta casilla, puede seleccionar una acción en el campo **Reintentar acción** y configurar parámetros adicionales en la pestaña **Parámetros de reintento**.

    La funcionalidad de reintento le permite configurar el comportamiento del servicio si no se puede ejecutar una acción específica. Por ejemplo, si el servicio web externo al que intenta conectarse no responde, puede especificar cuántas veces el sistema debe volver a intentar la conexión, en qué intervalo y desde qué acción en la canalización de procesamiento.

- **Exportar resultados**: puede seleccionar esta casilla para *una* acción en la canalización de procesamiento. El archivo electrónico que genera la acción en la aplicación Finance o Supply Chain Management se puede exportar desde la página **Registro de envío de documentos electrónicos**.

### <a name="applicability-rules"></a>Reglas de aplicabilidad

Las *reglas de aplicabilidad* son cláusulas configurables que proporcionan un contexto para la ejecución de características de Facturación electrónica a través del conjunto de capacidades de Facturación electrónica.
Los documentos empresariales que se envían de Finance o Supply Chain Management a Facturación electrónica no incluyen una referencia explícita que permita al conjunto de capacidades de Facturación electrónica llamar a una versión de característica de Facturación electrónica y un elemento de configuración de características en particular para procesar el envío. Sin embargo, cuando se configura correctamente u documento comercial, contiene los elementos necesarios que permitirán a la Facturación electrónica determinar qué versión de característica de Facturación electrónica y canalización de procesamiento se debe seleccionar y ejecutar.

Las reglas de aplicabilidad permiten que el servicio de Facturación electrónica encuentre las características exactas de Facturación electrónica que se deben utilizar para procesar un envío. Para encontrar las características correctas, los campos **Contexto** del documento comercial enviado se comparan con las cláusulas de las reglas de aplicabilidad.

Puede trabajar con reglas de aplicabilidad de las siguientes formas:

- Seleccione **Nuevo** para agregar una nueva cláusula a un conjunto de reglas de aplicabilidad.
- Seleccione **Eliminar** para eliminar una cláusula.
- Seleccione varios registros y luego use el botón **Agrupar** o **Desagrupar** para crear una combinación de elementos o instrucciones lógicas. Por ejemplo, seleccione las líneas que desea agrupar y luego seleccione **Agrupar cláusula**. Cuando se agrupan las cláusulas, se agrega una nueva columna a la cuadrícula. Esta columna especifica el operador lógico para la cláusula agrupada. Actualmente se admiten los siguientes tipos de operadores:

    - Equal
    - Not equal
    - Mayor que/Menor que
    - Mayor o igual que/menor o igual que
    - Contiene
    - Empieza por

    > [!NOTE]
    > Cuando desagrupa una cláusula, siempre comience desde el nivel de agrupación más interno.

### <a name="variables"></a>Variables

Las *variables* le brindan más flexibilidad cuando configura una canalización de procesamiento y el flujo de datos entre acciones. Puede hacer referencia a una variable en algunos parámetros de acción para almacenar temporalmente datos o archivos electrónicos. Algunas variables se utilizan para pasar datos entre las aplicaciones Finance o Supply Chain Management y el servicio de Facturación electrónica.

El sistema crea algunas variables de manera predeterminada. Por ejemplo, la variable **BusinessDocumentDataModel** contiene datos comerciales en una estructura de notación de objetos JavaScript (JSON) que viene en la llamada de la aplicación conectada durante el proceso de envío.

Están disponibles los siguientes tipos de variables:

- **Constante**: un contenedor para almacenar datos temporales que se utilizan en el procesamiento de acciones de canalización.
- **Del cliente**: el contenido de la variable se adquiere del cliente de Dynamics 365 cuando se ejecuta el proceso de envío.
- **Al cliente**: el contenido de la variable se pone a disposición para la importación por el cliente de Dynamics 365 cuando se ejecuta el proceso de envío.
- **Tipo de datos**: seleccione el tipo de datos de la información que se almacena en la variable.

### <a name="parameters"></a>Parámetros

La opción **Deshabilitar la reducción de datos comerciales** se utiliza para optimizar la estructura de la carga útil de datos comerciales que proviene de la aplicación Finance o Supply Chain Management durante el envío de documentos electrónicos. La optimización ayuda a reducir los datos que se introducen en el servicio de Facturación electrónica para su posterior transformación en el archivo electrónico requerido. El valor predeterminado es **No**.

- **Sí**: Finance o Supply Chain Management enviará un archivo JSON de la estructura **Modelo de factura** o **Modelo fiscal** (para Brasil) que se define en el módulo **Informes electrónicos**. Todos los elementos del modelo se llenan con datos comerciales en el lado de la aplicación, independientemente de la estructura final del archivo electrónico. Los modelos suelen contener más datos comerciales de los que requiere la estructura de archivos de destino, y se puede requerir más tiempo para generar estos datos en la aplicación. Un valor de **Sí** para esta opción es necesario en el raro caso de que desee generar diferentes archivos de salida en una característica de facturación electrónica y configuración de características. Un valor de **Sí** es útil cuando soluciona problemas en sus escenarios, la estructura de los archivos electrónicos y la integridad de los datos comerciales.
- **No**: Finance o Supply Chain Management realizarán la primera llamada al servicio sin ningún dato comercial. El propósito de esta llamada es obtener información sobre la configuración de Informes electrónicos (ER) que se utilizará para la transformación de archivos electrónicos en la canalización de procesamiento. Esta información se devuelve a la aplicación, que la utiliza para determinar el subconjunto de datos comerciales que se debe incluir en el archivo JSON de la estructura del **Modelo de factura** o **Modelo Fiscal** (para Brasil). Un valor de **No** para esta opción ayuda a reducir el volumen de datos comerciales que la aplicación envía al servicio, ya que la aplicación puede enviar solo los datos comerciales necesarios para generar correctamente un archivo electrónico.

### <a name="validate-a-feature-setup"></a>Validar una configuración de características

Puede ejecutar la validación para comprobar la coherencia de toda la configuración. Por ejemplo, si un parámetro obligatorio para una acción se ha quedado en blanco, la validación detecta esta incoherencia y recibe un mensaje de advertencia.

- En la página **Configuración de la versión de característica**, en el panel de acciones, seleccione **Validar**.

## <a name="delete-a-feature-setup"></a>Eliminar una configuración de características

1. En la página **Características de facturación electrónica**, seleccione una versión de característica de facturación electrónica que tenga un estado de **Borrador**.
2. En la pestaña **Configuraciones**, seleccione **Eliminar**.
3. En el cuadro de mensaje que aparece, seleccione **Sí** para confirmar que desea eliminar la configuración de características.
