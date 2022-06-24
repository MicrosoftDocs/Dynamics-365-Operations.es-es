---
title: Segmentación por dispositivo, mercado y geolocalización
description: Este artículo describe cómo crear, editar y administrar públicos y destinos en el creador de sitios de Microsoft Dynamics 365 Commerce mediante el uso de información de dispositivo, mercado y geolocalización.
author: sushma-rao
ms.date: 02/03/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2021-07-31
ms.dyn365.ops.version: AX 10.0.21
ms.openlocfilehash: 90772fd942db30bbf4f65a87b1dca4b2aaacee1e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8881666"
---
# <a name="device-market-and-geolocation-targeting"></a>Segmentación por dispositivo, mercado y geolocalización

[!include [banner](includes/banner.md)]

Este artículo describe cómo crear, editar y administrar públicos y destinos en el creador de sitios de Microsoft Dynamics 365 Commerce mediante el uso de información de dispositivo, mercado y geolocalización.

Dynamics 365 Commerce le permite personalizar variaciones del contenido de su página (conocido como *destinos*) para grupos específicos de clientes (conocidos como *públicos*) para ayudar a aumentar la involucración y la satisfacción de los usuarios. Primero puede crear un público o un destino. Sin embargo, una experiencia de focalización exitosa requiere ambos componentes.

Puede crear y administrar públicos en el creador de sitios de Commerce, en función de los datos del cliente, como la ubicación, la información del dispositivo, el estado de inicio de sesión y otra información derivada dinámicamente de las solicitudes web de los clientes. También crea y administra destinos en módulos y fragmentos de comercio electrónico en el creador de sitios de Commerce.

**Descargo de responsabilidad:** usted es responsable de utilizar esta función de conformidad con todas las leyes y normativas aplicables, incluidas las relacionadas con la segmentación y la creación de perfiles. 

## <a name="audiences"></a>Públicos

Un público es un grupo de usuarios y la pertenencia al grupo está determinada por un conjunto de reglas dinámicas. Estas reglas son pruebas lógicas simples que se ejecutan con información que está disponible en las solicitudes de los clientes u otros segmentos disponibles. Puede combinar varias reglas utilizando los operadores Y/O.

Commerce admite de forma nativa segmentos básicos como la información del dispositivo, el estado de inicio de sesión, la referencia y los parámetros de la cadena de consulta. También admite segmentos extensibles a través de conexiones con proveedores externos.

### <a name="basic-segments"></a>Segmentos básicos

De forma predeterminada, los siguientes segmentos están disponibles y se pueden incluir en las definiciones de públicos:

- **Estado de inicio de sesión** - Pruebe si un usuario está autenticado.
- **Plataforma de dispositivo** - Pruebe los siguientes tipos de dispositivos:

    - Móvil
    - Escritorio
    - Tableta
    - Otra

- **SO del dispositivo** - Pruebe los siguientes sistemas operativos:

    - Windows
    - Linux
    - iOS
    - Android, otros

- **Parámetros de la cadena de consulta** - Pruebe la existencia de un par de valores clave en un parámetro de cadena de consulta de una URL de solicitud. Por ejemplo, para la URL `www.fabrikam.com/en-us/request?promo=true`, se puede escribir una regla para probar que el parámetro **promoción** tiene el valor **verdadero**.
- **Cookie** - Pruebe un valor de cookie establecido para el dominio en la URL de solicitud. Por ejemplo, una solicitud de Fabrikam.com podría incluir una cookie con el nombre **CustomLayout** y el valor **1**. La prueba de cookies comprueba la existencia de una cookie pero no la crea explícitamente. En el ejemplo anterior, JavaScript debe haber configurado previamente la cookie **CustomLayout** de otro módulo o algún otro proceso comercial.

    > [!NOTE]
    > Asegúrese de que el uso de cookies cumpla con las leyes aplicables.

- **Referente** - Si un usuario sigue un enlace para solicitar la página, el referente es la URL de la página que alojó el enlace.

### <a name="extensible-segments"></a>Segmentos extensibles

Commerce le permite expandir la lista de segmentos disponibles conectándose a proveedores de segmentación de terceros. Un proveedor de segmentación describirá los tipos de segmentos que están disponibles. Para obtener más información sobre cómo conectarse a un proveedor de geolocalización o segmentación, consulte [Configurar y habilitar conectores](e-commerce-extensibility/connectors.md).

> [!NOTE]
> - Si un proveedor externo está habilitado, es posible que se conecte a un servicio que tenga un rendimiento impredecible. Para ayudar a garantizar una mejor experiencia de usuario, si un usuario solicita una página que incluye orientación y esa página hace referencia a un público que verifica un proveedor de segmento externo, se muestra la versión predeterminada de la página.
> - El usuario debe dar su consentimiento para permitir cookies. Luego, el navegador del usuario solicita todos los segmentos de los proveedores relevantes, y los resultados se colocan en una cookie que se devuelve al usuario. Las solicitudes posteriores a la página utilizarán esta información para ofrecer contenido dirigido al usuario. Para obtener más información sobre el cumplimiento de las cookies, consulte [Cumplimiento de cookies](cookie-compliance.md).

**Descargo de responsabilidad:** Si habilita esta función, sus datos se compartirán con los sistemas de terceros que seleccione. Usted controla qué datos, si los hay, proporciona al tercero. Comprende que los estándares de cumplimiento y tratamiento de datos del tercero pueden diferir de los estándares de Microsoft Dynamics 365 Commerce. Su privacidad es importante para Microsoft. Para obtener más información, lea nuestro [Aviso de privacidad y cookies](https://privacy.microsoft.com/privacystatement).

### <a name="create-an-audience-in-site-builder"></a>Crear un público en el generador de sitios

Para crear un público nuevo en el generador de sitios de Commerce, siga estos pasos.

1. En el panel de navegación izquierdo, seleccione **Públicos**.
1. Seleccione **Nuevo**.
1. Especifique un nombre para el público. Opcionalmente, también puede agregar etiquetas y una descripción.
1. Seleccione **Crear** y luego **Agregar nuevo bloque de reglas**. Un bloque de reglas es una colección de reglas unidas por condiciones Y. También puede crear varios bloques de reglas que tengan condiciones O entre ellos.
1. Seleccione un origen de datos para sus segmentos y luego especifique el nombre, el operador y los valores del segmento. Puede crear y eliminar más reglas en un bloque de reglas, o puede crear y eliminar bloques de reglas completos. También puede mover bloques de reglas hacia arriba o hacia abajo según lo requiera.

    > [!NOTE]
    > Puede tener hasta 100 valores en una lista y cada elemento de la lista puede contener hasta 50 caracteres.

1. Cuando esté satisfecho con la configuración del público, seleccione **Terminar de editar**. A continuación, puede seleccionar **Publicar** para que la audiencia esté disponible para su uso en un destino en directo. Alternativamente, puede publicar el público junto con el destino. 

Para editar un público, seleccione el hipervínculo correspondiente en la pestaña **Públicos** y luego seleccione **Editar** en el editor de público que aparece. Para ver la lista de destinos y páginas que hacen referencia a un público, seleccione el público en la vista de lista de públicos y luego seleccione **Ver asignaciones**. Para eliminar un público en la vista de lista de públicos o en el editor de públicos, anule la publicación si ya se ha publicado y luego seleccione **Borrar** en la barra de comandos.

> [!NOTE]
> Los públicos son un concepto a nivel de sitio en el geenrador de sitios de Commerce. Puede compartir el mismo público en varios destinos.

### <a name="rename-an-audience-in-site-builder"></a>Cambiar el nombre del público en el generador de sitios

Para cambiar el nombre de un público existente en el generador de sitios de Commerce, siga estos pasos.

1. En el panel de navegación izquierdo, seleccione **Públicos**.
1. Seleccione el nombre del segmento del público que desee cambiar.
1. Seleccione **Editar** para empezar a editar la audiencia.
1. En el panel de propiedades de la audiencia, seleccione el símbolo del bolígrafo junto al nombre de la audiencia.
1. Edite el nombre del público según sea necesario.
1. Seleccione la marca de verificación para confirmar el cambio de nombre.
1. Seleccione **Finalizar edición**.

## <a name="targets"></a>Público objetivo

Un destino es la experiencia del usuario que se muestra a los miembros de uno o más públicos seleccionados. Puede incluir variaciones de uno o más módulos en una página o en un fragmento. 

Puede definir una programación para sus destinos para especificar cuánto tiempo deben permanecer activos. Tenga en cuenta que esta acción es independiente de la acción de programar un grupo de publicación que determina cuándo se publicará una colección de contenido. También puede obtener una vista previa de sus destinos para ver cómo se verán los miembros de los públicos seleccionados. Además, puede priorizar sus destinos para especificar qué destino debe mostrarse en caso de conflicto.

### <a name="create-a-target"></a>Crear un destino

Para crear una shell de destino para los módulos de la página en el creador de sitios de Commerce, siga estos pasos.

1. En el panel de navegación izquierdo, seleccione **Páginas**. Luego, seleccione el hipervínculo de la página que tiene los módulos a los que desea dirigirse.
1. Seleccione **Editar** para comprobar la página para editar.
1. En el menú **Destino**, seleccione **Nuevo destino** para crear una nueva shell de destino. Puede crear varios destinos en una página según sus necesidades.
1. Introduzca un nombre y una descripción para su destino y luego seleccione **Siguiente**.
1. Seleccione **Agregar** para incluir los públicos que verán el contenido de destino o para excluir los públicos. A continuación, seleccione **Siguiente**.

    > [!NOTE]
    > La asignación de público es un paso opcional durante la creación del destino. Sin embargo, antes de publicar el destino, debe incluir al menos un público para asegurarse de que los grupos de usuarios previstos vean el contenido de destino.

1. Defina la ventana de tiempo para la visualización de su destino seleccionando la zona horaria y las fechas y horas de inicio y finalización. Puede establecer el destino para que se muestre en todo momento durante la ventana, o puede seleccionar días y horas específicas. Cuando haya terminado, haga clic en **Siguiente**.

    > [!NOTE]
    > Las horas y la zona horaria que especifique son globales. Si desea dirigirse a diferentes ubicaciones en diferentes momentos o en diferentes zonas horarias, debe crear diferentes destinos y definir el horario deseado para cada ubicación.

1. Revise los detalles y, cuando todo parezca correcto, seleccione **Crear una experiencia de destino** y luego **Ir al destino**. Se crea la shell de destino. Ahora puede agregarle módulos.
1. Seleccione el módulo al que dirigirse, seleccione los puntos suspensivos (**...**) y luego seleccione **Agregar al destino actual**. Cuando tu destino es un módulo primario, todos sus elementos secundarios pasan a formar parte de ese destino. Los módulos de destino están resaltados en verde.
1. Realice las actualizaciones de contenido necesarias en el módulo de destino y agregue más módulos al destino según lo requiera. Después, sseleccione **Guardar** para guardar todos los cambios.
1. Antes de publicar su destino, asegúrese de seleccionar **Vista previa** en la barra de comandos para revisarlo. Después, podrá seleccionar una de las siguientes opciones:

    - **Vista previa básica** - Seleccione esta opción para obtener una vista previa solo de la variación seleccionada (página o destino predeterminados), sin ningún público asociado.
    - **Vista previa avanzada** - Seleccione esta opción si tiene varios destinos en una página y desea obtener una vista previa de ellos como un usuario que pertenece a un grupo seleccionado de públicos, o en una fecha/hora específica. Seleccione **Siguiente** para seleccionar de una lista de públicos relevantes. También puede eliminar el filtro para seleccionar entre todos los públicos.

1. Cuando esté satisfecho con la configuración de destino, debe publicar la página para que el destino se active. Seleccione **Publicar** para que el destino se active de inmediato. Alternativamente, puede utilizar un grupo de publicación para programar cuándo se activa la página. Para obtener información sobre los grupos de publicación, consulte [Trabajar con grupos de publicación](publish-groups.md).

También puede dirigirse a fragmentos. El procedimiento es similar. Sin embargo, en el paso 1, selecciona **Fragmentos** en lugar de **Páginas** en el panel de navegación izquierdo.

> [!NOTE]
> Para evitar cualquier impacto negativo en sus métricas, puede tener un experimento o destinos en una página o en un fragmento. No puede tener un experimento y objetivos a la vez.

### <a name="manage-targets"></a>Administrar destinos

Para editar, duplicar o eliminar destinos, vaya a la página o el fragmento predeterminados y siga estos pasos.

1. En el menú desplegable, seleccione **Destino** y luego seleccione **Administrar destinos**.
1. Seleccione un destino para editar, duplicar o eliminar.
1. Si tiene varios destinos en el mismo módulo, o si varios destinos tienen horarios en conflicto, seleccione **Priorizar destinos** para especificar el orden en el que deben mostrarse. Si agrega más de un destino en una página o en un fragmento, el botón **Priorizar destinos** también aparece en la barra de notificaciones para recordarle que debe priorizar los destinos. Si no se especifica ninguna prioridad, el destino más reciente se selecciona de forma predeterminada.

### <a name="localize-targets"></a>Localizar destinos

Los destinos en páginas y fragmentos se incluyen automáticamente cuando los archivos XLIFF se exportan e importan con fines de localización. Sin embargo, si no se requiere ninguna configuración regional, puede eliminar los destinos correspondientes después de importar los archivos XLIFF localizados.

> [!NOTE]
> Los destinos se administran por canal y configuración regional. Los cambios que realiza en los destinos en un canal o configuración regional no se transfieren automáticamente a otros canales o configuraciones regionales.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
