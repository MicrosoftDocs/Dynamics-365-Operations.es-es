---
title: Configurar y administrar imágenes para Modern POS (MPOS)
description: Este artículo explica los pasos para realizar la configuración y la gestión de imágenes para las distintas entidades que aparecen en Modern POS (MPOS).
author: athinesh99
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailChannelProfile, RetailMediaGallery, RetailImages,
audience: Application User
ms.reviewer: josaw
ms.custom: 52851
ms.assetid: 5c21385e-64e0-4091-98fa-6a662eb33010
ms.search.region: global
ms.search.industry: Retail
ms.author: athinesh
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 1139d4c826b6c35f1a6660d3880449e495473441
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5264513"
---
# <a name="set-up-and-manage-images-for-modern-pos-mpos"></a>Configurar y administrar imágenes para Modern POS (MPOS)

[!include [banner](includes/banner.md)]

Este artículo explica los pasos para realizar la configuración y la gestión de imágenes para las distintas entidades que aparecen en Modern POS (MPOS).

## <a name="setting-up-the-media-base-url-and-defining-media-templates-to-configure-the-format-for-image-urls"></a>Configurar la URL de base media y definir las plantillas de medios para configurar el formato para las URL de imagen

Las imágenes que aparecen en Modern POS (MPOS). deben hospedarse externamente, fuera de Commerce. Normalmente, se alojan en un sistema de gestión de contenidos, una cuadrícula de contenido (CDN) de entrega, o un servidor multimedia. MPOS después lleva y muestra las imágenes para entidades adecuadas, como los productos y los catálogos, teniendo acceso a URL de destino. Para elevar estas imágenes externamente alojadas, MPOS requiere el formato correcto de dirección URL para imágenes. Puede configurar el formato requerido de dirección URL para imágenes configurando el valor **URL de base de medios** en el perfil del canal y mediante la funcionalidad **Definir plantilla de los medios** para cada entidad. También puede sobrescribir el formato estándar de dirección URL para un subconjunto de entidades mediante la funcionalidad **Editar en Excel**.

> [!IMPORTANT]
> En la versión actual de Commerce, ya no se puede configurar el formato de dirección URL mediante el XML de atributo **Imagen** para MPOS en el grupo de atributos **Predeterminado** para entidades. Si está familiarizado con Microsoft Dynamics AX 2012 R3 y ahora está usando la versión actual de Commerce, asegúrese de que se usa siempre la nueva funcionalidad **Definir la plantilla multimedia** para configurar imágenes. No use ni modifique el atributo **Imagen** del grupo de atributos **Predeterminado** para ninguna entidad, incluidos los productos. Los cambios que se realicen directamente en el grupo de atributos **Predeterminado** para imágenes no se reflejará. Esta opción se desactivará en una versión futura.

En los siguientes procedimientos, la imágenes se configuran para la entidad del catálogo como ejemplo. Estos procedimientos ayudarán a garantizar que la ruta correcta de destino de la imagen se establece de forma implícita para todas las imágenes de catálogo que usan una ruta común. Por ejemplo, si ha configurado un servidor multimedia o CDN externamente, y desea que las imágenes aparezcan en MPOS para una determinada tienda, la función **Defini la plantilla multimedia** le ayuda a establecer la ruta en la que MPOS puede buscar hacia y recuperar las imágenes.

> [!NOTE]
> En este ejemplo de datos de prueba, el servidor multimedia se implementa en Commerce Scale Unit. Sin embargo, puede tenerlo en cualquier lugar fuera de Commerce.

### <a name="set-up-the-media-base-url-for-a-channel"></a>Configurar la base URL multimedia para un canal

1. Abre el portal de la sede de Commerce.
2. Haga clic en **Retail y Commerce** &gt; **Configuración de canales** &gt; **Perfiles de canales**.

    [![Navegación](./media/channel-profile1.png)](./media/channel-profile1.png)

3. En el perfil del canal que su tienda usa para MPOS, actualice el campo **URL de base multimedia** con la URL base de su servidor multimedia o CDN. El URL base es la primera parte de la dirección URL que es común para todas las carpetas de imagen de distintas entidades.

    [![Página de perfiles del canal](./media/channel-profile2.png)](./media/channel-profile2.png)

### <a name="define-the-media-template-for-an-entity"></a>Definir la plantilla multimedia para una entidad

1. Haga clic en **Retail y Commerce** &gt; **Gestión de catálogo** &gt; **Imágenes de catálogo**.
2. En la página **Imágenes de catálogo**, oen el Panel de acciones, haga clic en **Definir plantilla multimedia**. En el cuadro de diálogo **Definir plantilla multimedia**, en el campo **Entidad**, **Catálogo** debe seleccionarse de forma predeterminada.
3. En la ficha desplegable **Ruta multimedia**, especifique la ruta restante de la ubicación de la imagen. La ruta multimedia admite **LanguageID** como variable. Por ejemplo, para los datos de prueba, puede crear una carpeta **Catálogos** para todas las imágenes del catálogo en la URL base multimedia para su servidor multimedia (`https://testax3ret.cloud.test.dynamics.com/RetailServer/MediaServer`). Puede tener una carpeta para cada idioma, como en-US or fr-FR y copiar las imágenes adecuadas debajo de cada carpeta. Si no tiene diferentes imágenes para distintos idiomas, puede omitir la variable **LanguageID** de su estructura de carpetas e ir directamente a la carpeta de catálogos que contiene las imágenes del catálogo.

    > [!NOTE]
    > La versión actual de Commerce admite el token **{LanguageId}** para las entidades del catálogo, del producto y de la categoría. (El token **{LanguageID}** no se admite para las entidades de cliente y de trabajador, según el estándar existente vigente desde Microsoft Dynamics AX 6.x.)

4. Para imágenes, el formato del nombre de archivo está codificado con el nombre del catálogo y no se puede modificar. Por lo tanto, puede cambiar de nombre a las imágenes de modo que tengan nombres adecuados de catálogo, para ayudar a garantizar que MPOS los gestiona correctamente.
5. En el campo **Extensión de archivo**, seleccione la extensión esperada del nombre de archivo, en función del tipo de imágenes que tenga. Por ejemplo, para los datos de prueba, las imágenes del catálogo se establecen en la extensión del formato .jpg. (Los archivos de imagen también se renombran de modo que tengan nombres de catálogo.)
6. Haga clic en **Aceptar**.
7. Para validar que la plantilla multimedia para imágenes se ha guardado correctamente, en la página **Imágenes de catálogo**, haga clic en **Definir plantilla multimedia** otra vez. Para validar la plantilla sin cerrar el cuadro de diálogo **Definr plantilla multimedia**, puede usar la ficha desplegable **Generar URL de imagen para Excel**. Compruebe el aspecto de la URL de la imagen y compruebe que la dirección URL se ajusta al estándar de la plantilla que se mencionó anteriormente. El cuadro de diálogo **Definir plantilla multimedia** ahora ha configurado la ruta de la imagen de forma implícita para todas las imágenes de catálogo que usan esta ruta común de dirección URL. Esta ruta de dirección URL se aplica a todas las imágenes del catálogo a menos que se sobrescriban. La primera parte de la ruta de la imagen se obtiene del URL base multimedia que ha definido en el perfil del canal. La parte restante de la ruta se toma de la ruta que definió en la plantilla multimedia. Las dos partes se concatenan para proporcionar el URL completo de ubicación de la imagen. Por ejemplo, un catálogo en los datos de prueba se denomina catálogo de la base de Fabrikam. Por lo tanto, el nombre de la imagen debe ser Fabrikam Base Catalog.jpg, de modo que use el nombre del catálogo y la extensión del nombre de archivo .jpg que se configura en la plantilla. En este caso, después de la concatenación, la URL será `https://testax3ret.cloud.test.dynamics.com/RetailServer/MediaServer/Catalogs/en-US/Fabrikam Base Catalog.jpg`.
8. Ejecute los trabajos de sincronización para llevar la nueva plantilla a la base de datos del canal, de modo que MPOS pueda usar la plantilla para tener acceso a las imágenes.
9. Para actualizar la plantilla multimedia para las imágenes del catálogo en el lado del canal, asegúrese de ejecutar **Catalog Job 1150** de **TI de Retail y Commerce** &gt; **Programa de distribución**.

    [![Defina la plantilla de medios del cuadro de diálogo](./media/catalog1.png)](./media/catalog1.png)

## <a name="previewing-an-image-from-the-entity-level"></a>Ver una imagen de una vista previa del nivel de entidad

1. De la página para el artículo de la entidad en HQ, puede ver la imagen con antelación que usa el URL de la imagen que se deriva de la plantilla multimedia. Para este ejemplo, vaya al catálogo adecuado y, a continuación, en el Panel de acciones, haga clic en **Medios** &gt; **Imágenes**. Use la lista desplegable para seleccionar varias tiendas que pueden tener distintos perfiles de canal.
2. Para editar o quitar la plantilla multimedia predeterminada, debe volver al cuadro de diálogo **Definir plantilla multimedia** para la página **Imágenes de catálogo**.
3. Puede usar los botones **Agregar** y **Quitar** para cambiar manualmente la ruta que se basa en la plantilla implícita y se usa para una imagen específica. Para obtener más información, consulte [Sobrescribir la plantilla multimedia para los artículos de la entidad](#overwriting-the-media-template-for-entity-items) que aparece más adelante en este artículo.
4. Una vez que haya terminado de previsualizar una imagen y de realizar los cambios que requiere, inicie la instancia de MPOS para la tienda adecuada, y compruebe si las imágenes del catálogo se aparecen.

    [![Cuadro de diálogo de imágenes](./media/catalog4.png)](./media/catalog4.png)

> [!NOTE]
> Puede usar el mismo procedimiento para las cinco entidades que se admiten: Trabajador, cliente, catálogo, categoría y productos. “Productos del catálogo” (productos que se establecen en el nivel del catálogo) y “productos del canal” (productos que se establecen en el nivel del canal) usan la plantilla multimedia que se establece para la entidad de los productos. Para la plantilla multimedia de los productos, puede seleccionar el número de imágenes de productos para mostrar por producto. También puede establecer la imagen predeterminada para un producto determinado. De esta manera, puede evitar imágenes en blanco en MPOS y ayudar a controlar qué imagen se usa como la imagen predeterminada para un producto. En el siguiente ejemplo, cada producto tiene cinco imágenes, y la primera imagen se establece como la imagen predeterminada. Los productos variantes se tratan la misma manera que los productos principales. El nombre de archivo de imagen se debe basar en el número de producto. Algunos caracteres también se escapan mientras se genera el nombre de archivo. Por lo tanto, se debe comprobar el nombre de archivo en la sección **Generar URL de imagen para Excel**. Consulte la sección [Sobrescribir mediante Edición en Excel](#overwrite-by-using-edit-in-excel) más adelante en este artículo.

## <a name="synchronization-jobs-to-send-a-media-template-to-the-channel-side"></a>Trabajos de sincronización para enviar una plantilla multimedia en la parte del canal

Para las cinco entidades admitidas (trabajador, cliente, catálogo, categoría y productos), siempre que se actualice el cuadro de diálogo **Definir plantilla multimedia** para configurar una imagen, asegúrese de que ejecuta el trabajo del catálogo (1150) en **TI de Retail y Commerce** &gt; **Programa de distribución**. Este trabajo le permitirá a la plantilla multimedia actualizada sinconizarse con el canal y se usará por MPOS. Ejecute el trabajo del catálogo (1150) después de realizar cambios de los siguientes modos:

- Actualice plantilla multimedia de la imagen del catálogo desde **Imágenes de catálogo** &gt; **Definir plantilla multimedia**.
- Actualice plantilla multimedia de la imagen del empleado desde **Imágenes de empleado** &gt; **Definir plantilla multimedia**.
- Actualice plantilla multimedia de la imagen del cliente desde **Imagen de cliente** &gt; **Definir plantilla multimedia**.
- Actualice la plantilla multimedia de la imagen del producto desde **Imágenes del producto** &gt; **Definir plantilla multimedia**.
- Actualice la plantilla de medios de la imagen de la categoría en **Imágenes de categoría** &gt; **Definir plantilla de medios**. También debe publicar el canal.

## <a name="overwriting-the-media-template-for-entity-items"></a>Sobreescribir la plantilla multimedia para elementos de entidad

Como en la sección anterior, la plantilla multimedia para una entidad determinada sólo admite una ruta común. Esta ruta se basa en la URL base multimedia que se configura y la ruta multimedia que se define. Sin embargo, en muchos casos, un minorista desea poder usar imágenes de distintos orígenes para un subconjunto de artículos en una entidad. Por ejemplo, una tienda usa el servidor multimedia autoalojado para un conjunto de imágenes del catálogo pero usa URL de CDN para otro conjunto. Para sobrescribir las URL de imagen basadas en una plantilla multimedia para las imágenes de la entidad en el nivel de entidad, puede usar Editar en Excel y Editar manualmente en la página **Previsualización**.

### <a name="overwrite-by-using-edit-in-excel"></a>Sobrescribir mediante Edición de Excel

1. Haga clic en **Retail y Commerce** &gt; **Gestión de catálogo** &gt; **Imágenes de catálogo**.
2. En la página **Imágenes de catálogo**, haga clic en **Definir plantilla multimedia**. En el cuadro de diálogo **Definir plantilla multimedia**, en el campo **Entidad**, **Catálogo** debe seleccionarse.
3. En la ficha desplegable **Ruta multimedia**, observe la ubicación de la imagen.
4. En la ficha desplegable **Generar URL de la imagen para Excel**, haga clic en **Generar**.

    > [!IMPORTANT]
    > Siempre que se cambie la plantilla multimedia, debe hacer clic en **Generar** para poder usar la funcionalidad Editar de Excel.

    Ahora ve una vista preliminar de las URL de imagen generadas en función de la última plantilla multimedia guardada.

    [![En la ficha desplegable Generar URL de la imagen para Excel, haga clic en Generar.](./media/excel2.png)](./media/excel2.png)

    > [!NOTE]
    > Las URL que se generan para Excel usan la ruta y las convenciones de la plantilla multimedia que se define. Estas convenciones incluyen las convenciones de los nombres de archivo. La expectativa es que ha configurado las imágenes físicas fuera de Commerce y las imágenes se pueden recuperar de las direcciones URL que se derivan de la plantilla multimedia que definió anteriormente. Puede sobrescribir estas URL derivadas mediante la funcionalidad Editar de Excel.

5. Haga clic en **Editar en Excel**.
6. Después de que se inicie la hoja de cálculo de Microsoft Excel, haga clic en **Activar edición** cuando se le pida.
7. Cuando se le pida, haga clic en **Confiar en este complemento** en el panel derecho, y espere a que el complemento complete la instalación.

    [![Confiar en este complemento](./media/excel4.jpg)](./media/excel4.jpg)

8. Si se le pide que inicie sesión, especifique las credenciales que usó para iniciar sesión en HQ.

    [![Petición de iniciar sesión](./media/excel5.png)](./media/excel5.png)

9. Tras iniciar sesión, debe poder ver la lista de URL de imagen para varias entradas del catálogo.
10. Puede corregir, agregar y eliminar las URL de imagen para diferentes artículos de la entidad.
11. Para todas las entidades excepto los productos, puede sobrescribir la URL de imagen. Modifique la URL de imagen existente, de modo que use la nuevo dirección URL de destino de la imagen, y actualice el nombre de archivo con el nuevo nombre de archivo para el archivo de imagen. El nombre de archivo debe ser único para ayudar a garantizar que el registro sea único.

    [![Sobrescribir las URL de imagen en Excel](./media/excel6.jpg)](./media/excel6.jpg)

    > [!NOTE]
    > Cuando sobrescribe la URL de imagen para entidades de los productos mediante la función Editar de Excel o la página del artículo de la entidad, MPOS muestra siempre todas las URL de imagen de la plantilla multimedia junto con la URL de la imagen sobrescrita.

12. Una vez que haya terminado de realizar cambios, haga clic en **Publicar en Excel** para crear una nueva entrada explícita de la asociación.
13. Vuelva a HQ, y haga clic en **Aceptar**.
14. Ejecute los trabajos apropiados de sincronización para la entidad, y compruebe la previsualización en la página de la entidad o en MPOS.

#### <a name="creating-new-records"></a>Creando registros nuevos

Puede crear nuevos registros en Excel. Sin embargo, debe asegurarse de proporcionar la información correcta. Por ejemplo, para crear una nueva entrada para un catálogo, asegúrese de que la identificación del catálogo y el nombre del catálogo son correctos, y también debe proporcionar un nombre de archivo único. El nombre de archivo único es muy importante porque la exclusividad de registros en Excel se valida durante la publicación. Primero, copie los detalles del catálogo para el que desea crear un nuevo registro, y copie el registro. Sólo es necesario actualizar el nombre de archivo y la dirección URL, ya que el resto de la información será la misma. Para crear nuevos registros para los artículos de la entidad de producto, debe usar el mismo procedimiento básico. Desde la hoja de cálculo de Excel, copie un registro existente para el producto para el que desea para crear un nuevo registro y, a continuación, sustituya la URL de imagen y el nombre de archivo. Asegúrese de que el nombre de archivo sea único.

#### <a name="deleting-an-existing-record"></a>Eliminar un registro existente

Solo los registros sobrescritos de URL de imagen se pueden eliminar. Después de que se elimine una imagen y la sincronización se complete, la imagen ya no aparecerá en la página **Previsualización** o en MPOS. Los registros de URL de imagen que se derivan de la plantilla multimedia no se pueden eliminar, pues estos registros se derivan siempre de la plantilla mmultimedia.

### <a name="overwrite-from-the-entity-level-preview-page"></a>Sobrescribir desde la página de vista previa del nivel de entidad

Para todas las entidades excepto los productos, puede sobrescribir la URL de imagen para un artículo determinado de la entidad en el nivel de artículo de la entidad desde la página **Vista previa**. Para los productos, puede usar la página de entidad "Productos del catálogo". Este ejemplo muestra cómo anular una imagen del catálogo.

1. Haga clic en **Catálogos** &gt; **Multimedia** &gt; **Imágenes**, y seleccione la imagen del catálogo para actualizar.
2. Haga clic en **Agregar**, y especifique la URL de imagen para sobrescribir la plantilla URL multimedia.
3. Si desea que la imagen se muestre en MPOS para el catálogo, puede establecerla como la imagen predeterminada.
4. Haga clic en **Aceptar**. La URL de imagen se actualiza para esta imagen del catálogo, y se mostrará una vista previa.

    [![Dirección URL actualizada en el nuevo cuadro de diálogo de imagen](./media/preview3.png)](./media/preview3.png)

5. También puede ver el la vista previa de la imagen para todas las URL de imágenes sobreescritas en la página de galería **Imágenes del catálogo**.

    [![Página de galería de imágenes del catálogo](./media/preview-4.png)](./media/preview-4.png)

> [!NOTE]
> Actualmente, la galería no muestra vistas previas de imagen para las URL de imagen de la plantilla multimedia. Para las entidades del catálogo, del trabajador, del cliente y de la categoría, si el usuario proporciona explícitamente una URL a través de esta página, se recomienda que indique qué imagen es la imagen predeterminada, ya que los clientes de Commerce Scale Unit muestran solo una imagen por catálogo, cliente, trabajador y categoría. Si el usuario no especifica una imagen predeterminada, el sistema determina la imagen predeterminada y la envía al visitante del servicio Commerce (MPOS o comercio electrónico).

### <a name="overwrite-the-image-url-for-catalog-product-images-from-the-preview-page"></a>Sobrescribir la URL de imagen para imágenes de productos del catálogo de la página de vista previa

Para sobrescribir las URL de imagen para imágenes de productos del catálogo, debe usar la página **Vista previa**. No puede utilizar la funcionalidad Edit en Excel.

1. Para sobrescribir imágenes de productos en un nivel del catálogo, seleccione un catálogo y seleccione el producto en el que sobrescribir la imagen.
2. Haga clic en **Atributos**.
3. En la página siguiente, seleccione **Imagen** y luego haga clic en **Editar**. La página de **Vista previa** se abre como un cuadro de diálogo deslizante.
4. Haga clic en **Agregar**, y sobrescriba la URL de imagen con nueva dirección URL.
5. Haga clic en **Aceptar**. Ahora verá la vista previa de la nueva imagen y podrá establecerla como la imagen predeterminada.

    [![Imagen de la vista previa en el cuadro de diálogo de Imagen nueva](./media/cat3.png)](./media/cat3.png)

> [!NOTE]
> Tras la asociación de categoría de la imagen, debe publicar el canal y ejecutar el trabajo del canal para ayudar a garantizar que los cambios se publican en la base de datos del canal.

## <a name="setting-up-images-to-appear-in-offline-mode-for-mpos"></a>Configuración de imágenes para que aparezcan en el modo sin conexión para MPOS

MPOS puede ejecutar en modo en línea (cuando MPOS se conecta con Commerce Scale Unit) o modo sin conexión (cuando no hay Commerce Scale Unit o conectividad a la red, y las transacciones se almacenan en una base de datos sin conexión local). Cuando MPOS ejecuta en modo sin conexión, no puede obtener imágenes del servidor externo de imágenes para mostrar desde Commerce Scale Unit, ya que se ha perdido la conexión. Sin embargo, puede seguir configurando imágenes para que se muestren cuando MPOS se ejecuta en modo sin conexión.

### <a name="set-up-product-images-to-appear-in-offline-mode-for-mpos"></a>Configure imágenes de productos para que aparezcan en el modo sin conexión para MPOS

Las imágenes de los productos que se deben usar en modo sin conexión pueden configurarse cargando la imagen física requerida en la imagen del producto base.

1. Haga clic en **Gestión de información de productos** &gt; **Productos** &gt; **Productos**.
2. Seleccione el producto para el que quiere establecer la imagen sin conexión.
3. Haga clic en **Editar** y, a continuación, haga clic en la flecha situada en la esquina derecha para mostrar el panel derecho.
4. En la ficha desplegable **Imágenes de productos**, haga clic en **Cambiar la imagen**, y cargue la imagen física que quiere usar para el producto seleccionado en modo sin conexión.
5. Guarde y cierre la página.
6. Mientras MPOS se encuentra en el modo en línea, ejecute el trabajo del catálogo en el HQ, para asegurarse de que los datos se envían al menos una vez a la base de datos sin conexión.
7. Configure MPOS en modo sin conexión. Debería ver la imagen que cargó para el producto específico en el HQ.

    [![Imagen de producto en modo sin conexión](./media/offline1.png)](./media/offline1.png)

### <a name="set-up-catalog-category-employee-and-customer-images-to-appear-in-offline-mode-for-mpos"></a>Configurar imagénes del catálogo, la categoría, el empleado y el cliente para que aparezcan en el modo sin conexión para MPOS

Las imágenes del catálogo, la categoría, el empleado y el cliente que se deben usar en modo sin conexión pueden configurarse agregando el vínculo de destino de la imagen a la galería y configurando la imagen como la imagen predeterminada para la entidad seleccionada.

1. Vaya al catálogo y luego, en el panel de acción, haga clic en **Multimedia** &gt; **Imágenes**.
2. Siga los pasos en la sección [Sobrescribir desde la página de vista previa de nivel de entidad](#overwrite-from-the-entity-level-preview-page) para agregar la URL de imagen externa.
3. Marque esta imagen como la imagen predeterminada para el catálogo seleccionando la casilla de la imagen que aparece en la cuadrícula.
4. Ejecute el trabajo de catálogo. La imagen ahora se usará como la imagen sin conexión para dicho catálogo en MPOS.
5. Siga un proceso similar para otras entidades, como categoría, empleado y cliente.

    [![Imagen sin conexión](./media/offline2.png)](./media/offline2.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]