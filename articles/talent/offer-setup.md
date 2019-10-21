---
title: Configurar la gestión de ofertas
description: Este tema describe cómo configurar ofertas en Microsoft Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 02/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-18
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 706766ba5133af03d00df99dba1c2a7b0405cd86
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2019
ms.locfileid: "2010853"
---
# <a name="set-up-offer-management"></a>Configurar la gestión de ofertas 

[!include [banner](includes/banner.md)]

Cuando trasladan a un candidato a la etapa de oferta en Dynamics 365 Talent: Attract, debe asegurarse de que las ofertas se pueden crear rápidamente para el candidato, aprobar según sea necesario, y enviarlas al candidato. Puesto que la mayoría de las propuestas son estándar, se pueden crear con plantillas reutilizables. En Attract, todas las propuestas se agrupan en un paquete de propuesta, que es una recopilación de uno o más documentos. 

Este tema muestra todos los pasos que un administrador de Attract seguiría para configurar diferentes plantillas de paquete de oferta como parte de la capacidad de gestión de la oferta de Attract. Los usuarios con roles de usuario que no son de administrador no tendrán acceso a estas capacidades.

>[!NOTE]
> Las capacidades de gestión de la propuesta están disponibles como parte del complemento de contratación completa.

## <a name="offer-data"></a>Datos de oferta 

Los datos de la propuesta son la unidad más pequeña dentro de la plantilla de paquete de propuesta. Una oferta típica consta de texto estándar y un conjunto de valores. Los conjuntos de valores son los únicos valores que pueden cambiar entre ofertas. Durante la creación de la propuesta, el aspecto más importante en el que se puede concentrar el creador de la propuesta es la lista de marcadores de posición de los datos de la propuesta presentes en una plantilla de paquete de propuesta. Para configurar los datos de la oferta, haga lo siguiente.

1.  Vaya a **Administración de ofertas**.

1.  Expanda la sección **Biblioteca** en el panel de navegación izquierdo y a continuación, vaya a **Datos de oferta**.

    >[!NOTE]
    > En la página **Datos de oferta** están las secciones **Detalles del candidato** y **Detalles del trabajo**. Attract proporciona inmediatamente unos cuantos marcadores de posición de los datos de la oferta.
    
    > Existen secciones en la página para organizar los distintos marcadores de posición de los datos de la propuesta en grupos lógicos. Estas secciones son útiles para el mantenimiento de los datos de la propuesta y el rellenado de datos durante el proceso de creación de la propuesta.

1.  Para crear una nueva sección de datos de oferta, haga clic en **Agregar una sección** y escriba un nombre único para la sección.

1.  Para agregar marcadores de posición de los datos de la oferta en una sección, haga clic en **Agregar datos de oferta** y escriba un nombre único para el marcador. de posición.

1.  Para editar el nombre de una sección, pase el mouse sobre el nombre de sección y actualice el nombre.

1.  Para editar el nombre de cualquier marcador de datos de oferta existente, primero asegúrese de que el marcador ya no forme parte de ninguna plantilla. A continuación, pase el mouse por encima del nombre del marcador de posición de datos de la oferta y actualice el nombre según sea necesario.

1. Para eliminar un marcador de datos de oferta existente, primero asegúrese de que el marcador no forme parte de ninguna otra plantilla. A continuación, pase el mouse sobre el marcador y cuando aparezca el icono de papelera, haga clic en él para eliminar el marcador de los datos de la propuesta.
    >[!NOTE]
    > Puede ver de cuántas plantillas forma parte un marcador de datos de oferta consultando el indicador numérico que está junto a cada dato de la propuesta. 

1. Para eliminar una sección, pase el mouse sobre el nombre. Si no aparece ninguno de los marcadores de datos de la propuesta de la sección en ninguna plantilla, puede hacer clic en el icono de papelera para eliminarlo. 
    >[!NOTE]
    > Al eliminar la sección también eliminará todos los marcadores de los datos de la oferta de la sección.

Una vez que se hayan configurado los marcadores de los datos de la propuesta, puede utilizarlos en todas las plantillas de documento. Los marcadores de datos de la propuesta no se limitan a una plantilla específica; el mismo conjunto se puede usar en todas las plantillas.

## <a name="offer-data-rules"></a>Reglas de datos de la oferta

La mayoría de las organizaciones tienen reglas para cómo crear ofertas. Por ejemplo, una organización puede requerir que una combinación de propuesta del sueldo anual máximo para una ubicación concreta y el nivel de asignación de la antigüedad tenga que estar dentro de un intervalo determinado, o que solo haya algunos valores específicos posibles para el nivel de oferta de la nueva contratación. Attract admite actualmente todas las reglas de datos de este tipo mediante un archivo CSV.

Para preparar el archivo CSV de las reglas de los datos, haga lo siguiente.

1.  Determine el marcador de los datos de la propuesta para el conjunto de reglas. Por ejemplo, **Sueldo anual**.

1.  Identifique los valores de los marcadores de datos de la oferta dependientes. Por ejemplo, **Ubicación de trabajo** y **Nivel**.

1.  Especifique las columnas 1 y 2 como **Ubicación de trabajo** y **Nivel**.

1.  Para cargar un valor de rango, convierta las columnas 3 y 4 en **Sueldo anual**. Para cargar un valor específico en lugar de un intervalo, convierta la columna 3 en **Sueldo anual**.

1.  Rellene el archivo Microsoft Excel en función de sus roles necesarios.

1.  Asegúrese de que cada fila es una combinación única de todos los valores conjuntos.

1.  Guardar el archivo en formato CSV.

Para cargar el archivo de las reglas de los datos de la oferta haga lo siguiente.

1.  Vaya a **Administración de ofertas**.

1.  Expanda la sección **Biblioteca** en el panel de navegación izquierdo y a continuación, vaya a **Reglas de datos de oferta**.

1.  Haga clic en **Conjunto de datos nuevo** para mostrar el cuadro de diálogo **Cargar**.

1.  Especifique un nombre único para el conjunto de reglas y después cargue el archivo CSV guardado.

1.  Haga clic en **Agregar**.
    El conjunto de reglas se procesará en segundo plano y cuando finalice se le notificará en la aplicación y por correo electrónico.

    Se le notificará si hay errores mientras se procesa la carga. A continuación puede descargar el registro de errores, corregir el archivo, y cargarlo de nuevo.

1.  Utilice la opción de botón de las elipsis (**…**) si desea descargar el conjunto de reglas y actualizar el conjunto de valores. Después de actualizar, puede cargar el archivo de nuevo.

1.  Puede eliminar una carga existente del conjunto de reglas si el marcador de posición que se define no se está utilizando en otra plantilla de documento.

>[!NOTE]
> - Cada marcador solo puede tener un conjunto exclusivo de columnas de las que dependa. Por ejemplo, si **Sueldo anual** depende de **Ubicación de trabajo** y **Nivel**, no puede cargar a otro conjunto de reglas en el que **Sueldo anual** dependa de otro conjunto de columnas.

> - Puede descargar conjuntos de reglas de los datos de la propuesta de muestra en la pestaña **Ejemplos** en la página **Reglas de datos de la oferta**.

> - Cuando un creador de oferta anula los valores recomendados por las reglas de los datos de la oferta, la propuesta se marca como no estándar y es obligatorio un flujo de trabajo de aprobación de la oferta.

## <a name="document-templates"></a>Plantillas de documentos

Una plantilla de documento de oferta puede ayudar a los administradores a crear cartas de propuesta. La plantilla de documento de oferta es una combinación del texto que formará parte de la oferta así como de los marcadores de datos de la oferta definida. 

Para crear una plantilla de documento de oferta, haga lo siguiente.

1.  Vaya a **Administración de ofertas**.

1.  Expanda la sección **Biblioteca** en el panel de navegación izquierdo y a continuación, vaya a **Plantillas**.

    La página **Plantillas** mostrará una lista de plantillas de documento que ya se han definido.

1.  Para crear una plantilla de documento nueva, haga clic en **Nueva plantilla**.

1.  Especifique un nombre único para la plantilla y haga clic en **Crear**.

1.  Use el editor de texto enriquecido para insertar o editar el contenido del documento de la propuesta. Puede insertar tablas, imágenes, e hipervínculos mediante las opciones disponibles en la parte superior del editor de texto.

1.  Puede insertar marcadores de posición de datos de la propuesta en el documento de la plantilla de la propuesta:

    - Arrastrando y soltando desde el panel derecho.

    - Poniendo un hashtag en el marcador de los datos de la propuesta directamente en el puesto. Escribiendo **\#** y después empezando a escribir el nombre del marcador de los datos de la propuesta. Las opciones aparecerán en la lista desplegable. Haga clic o pulse en **Entrar** para insertar el marcador de los datos de la propuesta.

    >[!NOTE]
    > - Para asociar un marcador a la plantilla de documento de oferta sin mostrar su valor al candidato, pase el mouse sobre el marcador de los datos de la propuesta y haga clic en el icono **Fijar**. Esto pasará el marcador a la sección **Datos de oferta anclados** de la plantilla de documento de la propuesta. Para desanclar, siga los mismos pasos pero haga clic en **Desanclar** en la lista de marcadores de posición de los datos de la propuesta.

    > - Para ver la lista de marcadores de posición de datos de la propuesta activos, cambie a la ficha **Activo** en el panel derecho.

    > - Si inserta un marcador de posición controlado por un conjunto de reglas de datos de la oferta, puede ver la dependencia de ese marcador de datos de la oferta en otros valores.

    > - Como alternativa, puede **Importar** el contenido de un archivo .docx en su equipo local y editarlo según sea necesario. De esta forma, no tiene que escribir todo el contenido en el editor.

1. Para obtener una vista preliminar del documento de la propuesta, use la opción **Vista previa** de la parte superior de la página.

1. Para determinar si un creador de la propuesta puede editar el contenido del documento de la propuesta, use la opción **Gestionar permiso** de la parte superior de la página. Si desea que el creador de la oferta solo inserte valores de marcador de posición y no edite el texto, establezca el valor de permiso en **No**.

1. Haga clic en **Guardar** para guardar su progreso. La plantilla se guardará en estado de borrador.

1. Para finalizar y marcar el documento como publicado, haga clic en **Fin**.

1. Puede ver qué plantillas de documento están activas actualmente, en modo de borrador, y se han almacenado y ya no se usan en la experiencia de destino de la biblioteca de plantillas de documentos.

>[!NOTE]
> Puede eliminar cualquier plantilla de documento de oferta que no sea parte de una plantilla de paquete de oferta ya existente.


## <a name="offer-package-templates"></a>Plantillas de paquetes de oferta

Los paquetes de ofertas son artefactos de oferta que se comparten con el candidato y están formados por una combinación de una o varias plantillas de documento de oferta. Para crear un paquete de oferta, haga lo siguiente.

1.  Vaya a **Administración de ofertas**.

1.  Vaya a **Paquetes** en el panel de exploración izquierdo.

    Se muestra una lista de plantillas de paquetes activa que están disponibles para las usen los creadores de la propuesta.

1.  Para crear un nuevo paquete de oferta, haga clic en **Nuevo paquete**.

1.  Especifique un nombre único y haga clic en **Crear**.

1.  Haga clic en **Agregar plantilla**.

    >[!NOTE]
    > - Puede elegir crear una plantilla nueva o seleccionar una ya existente.

    > - Si elige agregar una plantilla ya existente, tiene que asegurarse de que la plantilla de documento de la oferta se haya guardado, finalizado y marcado como activa.
    
    > - Puede elegir tantas plantillas de documento como desee. 
    
1.  Haga clic en **Listo** para volver a **Gestión de paquetes**.

    Puede configurar la secuencia de documentos y también marcar si el documento específico de la oferta es necesario durante la creación de la oferta. El creador de la oferta tendrá una opción de eliminar documentos marcados como **No requerido**.

1. Para guardar la plantilla del paquete de la oferta de modo que todos los creadores de ofertas puedan usarla, haga clic en **Guardar y publicar**.

   Para ver las plantillas de paquete de oferta de borrador, vaya a la pestaña **Borradores**. Si se realiza un cambio en la plantilla de paquete de oferta, tiene que guardarse y volverse a publicar.

## <a name="configure-an-offer-process"></a>Configurar un proceso de oferta

Existen varias partes del proceso de creación de la oferta que un administrador de Attract puede configurar.

- **Aprobaciones de oferta** - Elija si es necesario aprobar la oferta antes de enviarla al candidato. Como administrador, puede decidir también si todas las aprobaciones de oferta se producirrán de manera secuencial o en un flujo de trabajo de aprobación paralelo. También puede ordenar si los aprobadores de la propuesta deben agregar un comentario junto con su aprobación de la propuesta. Las aprobaciones de propuesta son obligatorias para todas las ofertas que no son estándar.

- **Experiencia de la propuesta del candidato** - Como administrador, tiene la opción de establecer si todas las propuestas tienen una fecha de vencimiento, y si es así cuál tiene que ser el aplazamiento predeterminado para la fecha de vencimiento. También puede configurar si los candidatos pueden rechazar una propuesta.

- **Firmas electrónicas** - Como administrador, puede elegir también el método que los candidatos pueden utilizar para firmar propuestas.
    - Adobe Sign- Todos los paquetes de la propuesta se enviarán y firmarán mediante Adobe Sign. Cada creador de ofertas que publica la oferta necesita tener su cuenta de Adobe Sign conectada a Attract. Para las licencias de Adobe Sign y una prueba gratis, visite este [vínculo](https://acrobat.adobe.com/us/en/business/integrations/microsoft-dynamics-365-for-talent.html).

    - DocuSign- Todos los paquetes de la propuesta se enviarán y firmarán mediante DocuSign. Cada creador de ofertas que publica la oferta necesita tener su cuenta de DocuSign conectada a Attract. 
    
    - ESign - ésta es la opción predeterminada, proporcionada lista para usar, donde el usuario puede firmar una oferta escribiendo su nombre e iniciales.


Para obtener más información acerca del proceso de creación de la oferta, consulte [Crear, aprobar y firmar propuestas](./creating-offers.md).
