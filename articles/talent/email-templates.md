---
title: Crear plantillas de correo electrónico en Attract
description: Este tema proporciona información acerca de las plantillas de correo electrónico que puede crear y usar en Microsoft Dynamics 365 Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 10/19/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 55c12010cfd055ee6977f50e566b70f76a2e1682
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462431"
---
# <a name="create-email-templates-in-attract"></a>Crear plantillas de correo electrónico en Attract

[!include [banner](includes/banner.md)]

Mediante la biblioteca de plantillas de correo electrónico, los administradores pueden crear un tema y una personalización de marca uniformes para todos los mensajes de correo electrónico enviados con Microsoft Dynamics 365 Talent: Attract y Offer. Los administradores también pueden seleccionar una colección de plantillas de contenido del correo electrónico que otros usuarios puedan consumir. El equipo de contratación puede utilizar estas plantillas en su flujo de trabajo para enviar mensajes de correo electrónico de forma más eficaz. Algunos mensajes de correo electrónico se configuran para enviarse automáticamente, y el administrador puede usar la biblioteca de plantillas de correo electrónico para personalizar el contenido de dichos mensajes de correo electrónico.

> [!NOTE]
> Para usar plantillas de correo electrónico, la organización debe tener el complemento de contratación completa.

## <a name="global-template-configurations"></a>Configuraciones de plantilla globales

Para crear una personalización de marca coherente para todas las comunicaciones realizadas por correo electrónico, el administrador debe establecer en primer lugar el encabezado y el pie de página globales para todas las plantillas de correo electrónico. En el centro de gestión, en la pestaña **Configuración de plantilla de correo electrónico**, en la sección **Encabezado**, el administrador puede cargar una imagen que se usará como la cabecera o el banner de todos los mensajes de correo electrónico. La imagen puede ser un logotipo de la empresa, un membrete, o cualquier otra imagen representativa. Recomendamos que el ancho esté entre 25 y 800 píxeles, y el alto esté entre 25 y 150 píxeles, ya que estas dimensiones son óptimas para la mayoría de los clientes de correo electrónico, como Microsoft Outlook. La imagen debe ser un archivo JPEG, JPG, PNG, o SVG, y el tamaño de archivo debe ser inferior a 1 megabyte (MB). Después de cargar una imagen, una vista preliminar del encabezado se genera y se muestra. Si la imagen del encabezado debe quitarse o reemplazarse, el administrador puede utilizar la opción **Quitar** sobre la vista previa.

En la sección **Pie de página**, el administrador puede proporcionar vínculos a la directiva de privacidad de la empresa para las comunicaciones, y a los términos y condiciones. Estos vínculos se especifican en un pie de página que se genera automáticamente. A continuación se muestra una vista previa de este pie de página. El administrador también puede elegir un idioma determinado en el que los pies de página del correo electrónico se enviarán como parte de todos los correos electrónicos. También se utilizará la misma configuración de idioma para juntar la tabla de resumen de la entrevista. 

Asegúrese de guardar los cambios antes de cerrar el centro de administración.

> [!NOTE] 
> El encabezado y el pie de página son una configuración global para todos los mensajes de correo electrónico. Por lo tanto, aparecerán en todos los correos electrónicos que se envíen a través de Attract. Si los valores no se configuran, no habrá encabezado y pie de página en los correos electrónicos.

## <a name="email-template-library"></a>Biblioteca de plantillas de correo electrónico 

Una vez configuradas las configuraciones de plantilla globales, el administrador puede empezar a crear y seleccionar plantillas para todos los correos electrónicos que se envían desde Attract y Offer. La biblioteca de plantillas de correo electrónico solo está disponible para los administradores. Para abrir la biblioteca, en el menú de navegación principal, seleccione la pestaña **Plantillas de correo electrónico**. La biblioteca está dividida en categorías según las distintas actividades de Attract para las que deben enviarse mensajes de correo electrónico, por ejemplo la programación, la evaluación, y la creación y oferta de trabajos. El administrador puede seleccionar cualquier categoría para ver todos los tipos de correo electrónico que están asociados a la actividad. Por ejemplo, seleccione **Programación** para ver los diversos tipos de correo electrónico que se envían durante el proceso de programación y todas las plantillas que están disponibles para cada tipo de correo electrónico. Cada subsección de una categoría representa un tipo de correo electrónico.

Algunos tipos de correo electrónico pueden tener más de un destinatario. Por ejemplo, en la categoría **Programación**, los mensajes de correo electrónico que se envían cuando se necesita el resumen de la programación, se envían a los candidatos y los entrevistadores. Cada sección tiene dos columnas principales: **Título de plantilla** y **Destinatario**. Cada fila en una sección representa una sola plantilla para un tipo de correo electrónico. Inicialmente, un símbolo de bloqueo aparecerá en la fila para cada plantilla. Este símbolo indica que la plantilla es la plantilla estándar que se proporcion con Attract y que no se puede eliminar. Para cualquier plantilla, el administrador puede usar puntos suspensivos (**...**) para duplicar la plantilla, establecerla como plantilla predeterminada, o eliminarla. Cuando una plantilla se establece como plantilla predeterminada, uno de dos comportamientos puede producirse. El comportamiento se indica con la tarjeta o las tarjetas que aparecen en la fila para la plantilla:

- **Predeterminado** Esta tarjeta indica que la plantilla es la plantilla predeterminada del correo electrónico que se envía, y que la información se especificará en ella cuando un usuario envíe un correo electrónico de ese tipo específico.
- **Predeterminado** + **Enviado automáticamente** - Esta combinación de tarjetas indica que la plantilla es la plantilla activa para los correos electrónicos generados por el sistema que se envían automáticamente.

Para editar una plantilla, seleccione la fila, y aplique los cambios a la plantilla.

> [!NOTE]
> Cada destinatario de un tipo específico de correo electrónico tiene una plantilla predeterminada. Todas las plantillas de Attract estándar se establecen como plantillas predeterminadas hasta que el administrador cree una nueva plantilla para un tipo específico de correo electrónico y la establezca como la plantilla predeterminada.

## <a name="create-a-template"></a>Crear una plantilla

Para crear una plantilla, en la esquina superior derecha de la biblioteca de plantillas de correo electrónico, seleccione **+ Nueva plantilla**. Para seleccionar el tipo de correo electrónico para el que está creando la plantilla, seleccione el destinatario, el proceso, y el evento para el que el correo electrónico se debe enviar. Después seleccione **Crear**.

La plantilla se abre en vista de edición, y puede dar un nombre a la plantilla. Por ejemplo, si la plantilla está destinada a candidatos de una universidad de Estados Unidos. pero el contenido está escrito en francés, puede especificar **Universidad\_EE. UU.\_Francais** como título. El título, la línea de asunto, y el contenido del cuerpo de cualquier plantilla admiten otros idiomas además del inglés.

El campo **A** para una plantilla no se puede editar, porque ya ha seleccionado el destinatario a primera vez que creó la plantilla.

Puede agregar personas como **Reclutador** o **Administrador de contratación** a la línea de (Cc) de copia carbón. Cuando se envía el correo electrónico, estos roles automáticamente se reemplazan con los usuarios adecuados, basándose en el contexto del trabajo.

El contenido de la línea de asunto y del cuerpo admite marcadores de posición. Puede insertar marcadores de posición escribiendo **\#** y seleccionando el marcador adecuado en la lista desplegable de autocompletar. La lista de marcadores de posición disponibles aparece a la derecha de la página. Cuando se envía el correo electrónico, los marcadores de posición automáticamente se reemplazan basándose en el contexto del trabajo y el destinatario. Por ejemplo, una plantilla para un correo electrónico que envía a los candidatos contiene el marcador \#{Candidate\_Name}. Cuando el correo electrónico se envía a un candidato que se llama Cameron, dicho marcador se reemplazará con el nombre de Cameron.

El editor del contenido del cuerpo es un editor de texto enriquecido que le permite diseñar y dar formato al texto. También le permite insertar hipervínculos y anclajes.

Una vez que una plantilla se cree para un tipo específico de correo electrónico, seleccione los puntos suspensivos (**...**) en la fila para la plantilla, y especifíquela como plantilla predeterminada.

## <a name="consume-templates"></a>Uso de plantillas

Cuando el equipo de contratación envía un mensaje de correo electrónico, puede usar plantillas que creó el administrador. Si se han creado numerosas plantillas para el correo electrónico que un usuario envía, aparece una lista desplegable en el flujo de trabajo de composición del correo electrónico. La plantilla predeterminada se introduce automáticamente, pero el usuario puede seleccionar otra plantilla.

> [!NOTE] 
> Para los mensajes de correo electrónico que se envían automáticamente, se pueden crear varias plantillas. Sin embargo, solo una plantilla se puede definir como plantilla activa. Dado que este proceso se activa mediante eventos, solo el administrador puede determinar qué plantilla se debe usar, en función de la combinación de tarjetas **Predeterminado** y **Enviado automáticamente** de la biblioteca de plantillas.
