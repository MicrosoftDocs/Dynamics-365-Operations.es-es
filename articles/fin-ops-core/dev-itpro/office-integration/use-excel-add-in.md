---
title: Ver y actualizar datos de entidad con Excel
description: Este tema explica cómo abrir los datos de entidad en Microsoft Excel y, a continuación, ver, actualizar y editar los datos mediante el complemento de Excel de Microsoft Dynamics.
author: jasongre
manager: AnnBe
ms.date: 01/22/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 267914
ms.assetid: 4e6c7194-a059-4057-bd62-ec0c802c36fd
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0a9486b3d700cdbe19fbcdba431f673d0a03014f
ms.sourcegitcommit: ca05440ee503bf15fe98fe138d317c1cdf21ad16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "5141885"
---
# <a name="view-and-update-entity-data-with-excel"></a>Ver y actualizar datos de entidad con Excel 

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tema explica cómo abrir los datos de entidad en Microsoft Excel y, a continuación, ver, actualizar y editar los datos mediante el complemento de Excel de Microsoft Dynamics. Para abrir los datos de entidad, puede comenzar desde Excel o las aplicaciones de Finance and Operations.

Al abrir los datos de la entidad en Excel, puede ver y editar los datos de forma rápida y sencilla mediante el complemento de Excel. Este complemento necesita Microsoft Excel 2016 o posterior.

> [!NOTE]
> Si su inquilino de Microsoft Azure Active Directory (Azure AD) está configurado para usar Servicios de federación de Active Directory (AD FS), debe asegurarse de que se haya aplicado la actualización de mayo de 2016 para Office, de modo que el complemento de Excel pueda registrarle correctamente.

Para obtener más información sobre el uso del complemento de Excel, vea el breve vídeo [Crear una plantilla de Excel para patrones de encabezado y línea](https://youtu.be/RTicLb-6dbI).

## <a name="open-entity-data-in-excel-when-you-start-from-a-finance-and-operations-app"></a>Abrir los datos de entidad en Excel en el inicio desde una aplicación de Finance and Operations
1. En una página de una aplicación de Finance and Operations, seleccione **Abrir en Microsoft Office**.

    Si el origen de datos raíz (tabla) de la página es el mismo que el origen de datos raíz de cualquier entidad, se generan las opciones **Abrir en Excel** predeterminadas en la página. Las opciones **Abrir en Excel** se pueden encontrar en las páginas utilizadas con frecuencia como, por ejemplo, **Todos los proveedores** y **Todos los clientes**.
 
2. Seleccione la opción **Abrir en Excel** y abra el libro que se ha generado. Este libro contiene información vinculante para la entidad, un puntero para su entorno y un puntero para el complemento de Excel.
3. En Excel, seleccione **Habilitar edición** para habilitar el complemento de Excel que desee ejecutar. El complemento de Excel se ejecuta en un panel a la derecha de la ventana de Excel.
4. Si ejecuta el complemento de Excel por primera vez, seleccione **Confiar en este complemento**.
5. Si se le pide que inicie sesión, seleccione **Iniciar sesión** y, a continuación, inicie sesión con las mismas credenciales empleadas para la aplicación de Finance and Operations. El complemento de Excel utilizará el contexto de un inicio de sesión anterior desde el explorador e iniciará su sesión automáticamente, si es posible. (Para obtener información sobre el explorador que se utiliza en función del sistema operativo, consulte [Exploradores utilizados por los complementos de Office](https://docs.microsoft.com/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins.) Para asegurarse de que el inicio de sesión se ha realizado correctamente, compruebe el nombre de usuario en la esquina superior derecha del complemento de Excel. 

El complemento de Excel lee automáticamente los datos de la entidad que ha seleccionado. Tenga en cuenta que no habrá datos en el libro hasta que el complemento de Excel lo haya leído.

## <a name="open-entity-data-in-excel-when-you-start-from-excel"></a>Abrir los datos de la entidad en Excel en el inicio desde Excel
1. En Excel, en la ficha **Insertar** , en el grupo **Complementos**, seleccione **Tienda** para abrir la Tienda Office.
2. En la Tienda Office, busque con la palabra clave **Dynamics** y luego seleccione **Agregar** junto al **Complemento de Microsoft Dynamics Office** (el complemento de Excel).
3. Si ejecuta el complemento de Excel por primera vez, seleccione **Confiar en este complemento** para permitir la ejecución del complemento de Excel. El complemento de Excel se ejecuta en un panel a la derecha de la ventana de Excel.
4. Seleccione **Agregar información de servidor** para abrir el panel **Opciones**.
5. En el explorador, copie la URL del explorador de su instancia de aplicación de Finance and Operations de destino, péguela en el campo **URL de servidor** y borre todo lo que sigue al nombre del host. La dirección URL resultante debe tener solo el nombre de host.

    Por ejemplo, si la URL es `https://xxx.dynamics.com/?cmp=usmf&amp;mi=CustTableListPage`, elimine todo excepto `https://xxx.dynamics.com`.

6. Seleccione **Aceptar** y, a continuación **Sí** para confirmar el cambio. El complemento de Excel se reinicia y carga los metadatos.

    El botón **Diseño** está ahora disponible. Si el complemento de Excel tiene un botón **Cargar applets**, probablemente no haya iniciado sesión como el usuario correcto. Para obtener más información, consulte “Aparece el botón Cargar applets” en la sección [Solución de problemas](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/office-integration/use-excel-add-in#troubleshooting) de este tema.

7. Seleccione **Diseño**. El complemento de Excel recupera los metadatos de la entidad.
8. Seleccione **Agregar tabla**. Aparece una lista de entidades. Las entidades aparecen con el formato "Nombre - Etiqueta".
9. Seleccione una entidad de la lista, como **Cliente - Clientes** y luego seleccione **Siguiente**.
10. Para agregar un campo de la lista **Campos disponibles** a la lista **Campos seleccionados**, seleccione el campo y luego seleccione **Agregar**. De forma alternativa, haga doble clic en el campo en la lista **Campos disponibles**.
11. Una vez que haya acabado de agregar campos a la lista **Campos seleccionados**, asegúrese de que el cursor se encuentre en el lugar adecuado de la hoja de cálculo (por ejemplo, celda A1), y seleccione **Listo**. Seleccione **Listo** para salir del diseñador.
12. Seleccione **Actualizar** para extraer en un conjunto de datos.

## <a name="view-and-update-entity-data-in-excel"></a>Ver y actualizar datos de la entidad en Excel
Una vez que el complemento de Excel lea los datos de la entidad en el libro, puede actualizar los datos en cualquier momento seleccionando **Actualizar** en el complemento de Excel.

## <a name="edit-entity-data-in-excel"></a>Editar datos de la entidad en Excel
Puede cambiar los datos de entidad de la forma necesaria y después publicarlos en las aplicaciones de Finance and Operations seleccionando **Publicar** en el complemento de Excel. Para editar un registro, seleccione una celda en la hoja de cálculo y, a continuación, modifique el valor de la celda. Para agregar un nuevo registro, siga uno de estos pasos:

- Haga clic en cualquier lugar de la tabla de orígenes de datos y, a continuación, seleccione **Nuevo** en el complemento de Excel.
- Haga clic en cualquier parte de la última fila de la tabla de orígenes de datos y pulse el tabulador hasta que el cursor salga de la última columna de dicha fila y se cree una nueva fila.
- Haga clic en cualquier parte de la fila justo debajo de la tabla de orígenes de datos y comience a introducir datos en una celda. Cuando saque el foco de dicha celda, la tabla se expandirá para incluir la nueva fila.
- Para los enlaces de campos de registros de encabezado, seleccione uno de los campos y, a continuación, seleccione **Nuevo** en el complemento de Excel.

Tenga en cuenta que solo se puede crear un nuevo registro si la clave y los campos obligatorios están enlazados en la hoja de cálculo, o si los valores predeterminados se completaron mediante la condición de filtro.

Para eliminar un nuevo registro, siga uno de estos pasos:

- Haga clic con el botón secundario en el número de la fila situado junto a la fila de la hoja de cálculo que se debe eliminar y, a continuación, haga clic en **Eliminar**.
- Haga clic con el botón secundario en cualquier parte de la fila de la hoja de cálculo que se debe eliminar y, a continuación, haga clic en **Eliminar** &gt; **Filas de tabla**.

Si los orígenes de datos se han agregado como relacionados, el encabezado se publica antes de las líneas. Si existen dependencias entre otros orígenes de datos, es posible que tenga que cambiar el orden de publicación predeterminado. Para cambiar el orden de publicación, en el complemento de Excel, seleccione el botón **Opciones** (el símbolo de engranaje) y, a continuación, en la ficha desplegable **Conector de datos**, seleccione **Configurar orden de publicación**.

## <a name="add-or-remove-columns"></a>Agregar o quitar columnas
Puede usar al diseñador para ajustar las columnas que se agregan automáticamente a la hoja de cálculo.

> [!NOTE]
> Si el botón **Diseño** no aparece debajo del botón **Filtro** en el complemento de Excel, deberá habilitar el diseñador del origen de datos. Seleccione el botón **Opciones** (el símbolo de engranaje), y luego seleccione la casilla **Habilitar diseño**.

1. En el complemento de Excel, seleccione **Diseño**. Se enumeran todos los orígenes de datos.
2. Junto al origen de datos, seleccione el botón **Editar** (el símbolo de lápiz).
3. En la lista **Campos seleccionados**, ajuste la lista de campos como sea necesario:

    - Para agregar un campo de la lista **Campos disponibles** a la lista **Campos seleccionados**, seleccione el campo y luego seleccione **Agregar**. De forma alternativa, haga doble clic en el campo en la lista **Campos disponibles**.
    - Para quitar un campo de la lista **Campos seleccionados**, seleccione el campo y luego seleccione **Quitar**. También puede hacer doble clic en el campo.
    - Para cambiar el orden de los campos en la lista **Campos seleccionados**, seleccione un campo y luego seleccione **Arriba** o **Abajo**.

4. Para aplicar los cambios al origen de datos, seleccione **Actualizar**. Seleccione **Listo** para salir del diseñador.
5. Si ha agregado un campo (columna), seleccione **Actualizar** para extraer un conjunto de datos actualizado.

## <a name="change-the-publish-batch-size"></a>Cambiar el tamaño del lote de publicación
Cuando los usuarios publican cambios en registros de datos mediante el complemento de Excel, las actualizaciones se envían por lotes. El tamaño de lote de publicación predeterminado es 100 filas. En la versión 10.0.17 y posteriores, la característica **Permitir la configuración del tamaño del lote de publicación en el complemento de Excel** le ofrece un control flexible sobre el tamaño del lote de publicación.

Los administradores del sistema pueden especificar un límite para todo el sistema en el tamaño del lote de publicación para los libros "Abrir en Excel" estableciendo el campo **Publicar límite de lote** de la sección **Parámetros de aplicación** de la página **Parámetros de aplicación de Office**.

El tamaño del lote de publicación también se puede cambiar para un libro individual mediante el complemento de Excel.

1. Abra el libro en Excel.
2. Seleccione el botón **Opción** (engranaje) en la parte superior derecha del complemento de Excel.
3. Seleccione el campo **Publicar tamaño de lote** como desee. El valor que establezca debe ser menor que el límite de lote de publicación para todo el sistema.
4. Seleccione **Aceptar**.
5. Guarde el libro. Si no guarda el libro después de realizar cambios en la configuración del complemento, esos cambios no se mantendrán cuando se vuelva a abrir el libro.

Los autores de plantillas de libros de Excel pueden utilizar el mismo procedimiento para establecer el tamaño del lote de publicación de las plantillas antes de cargarlas en el sistema.

## <a name="copy-environment-data"></a>Copiar datos de entorno

Los datos que se leen en el libro de un entorno se pueden copiar en otro entorno. Sin embargo, no puede simplemente modificar la dirección URL de conexión, ya que la caché de datos del libro continuará tratando los datos como datos existentes. En su lugar, debe usar la funcionalidad Copiar datos de entorno para publicar los datos en un nuevo entorno como nuevos datos.

1. Seleccione el botón **Opciones** (el símbolo de engranaje) y, a continuación, en la ficha desplegable **Conector de datos** , seleccione **Copiar datos de entorno**. 
2. Especifique la dirección URL del servidor del nuevo entorno. 
3. Seleccione **Aceptar** y, a continuación **Sí** para confirmar la acción. El complemento de Excel se reinicia y se conecta al nuevo entorno. Los datos existente en el libro se tratan como nuevos datos.

    Después de reiniciar el complemento de Excel, un cuadro de mensaje indica que el libro se encuentra en Modo de copia de entorno.

4. Para copiar los datos al nuevo entorno como nuevos datos, seleccione **Publicar**. Para cancelar la operación de copia de entorno y revisar los datos existentes en el nuevo entorno, seleccione **Actualización**.

## <a name="troubleshooting"></a>Solución de problemas
Existen problemas que se pueden resolver con unos sencillos pasos.

- **Aparece el botón Cargar applets** - Si el complemento de Excel tiene un botón **Cargar applets** tras el inicio de sesión, probablemente no haya iniciado sesión como el usuario correcto. Para resolver este problema, compruebe que el nombre de usuario correcto aparece en la esquina superior derecha del complemento de Excel. Si aparece un nombre de usuario incorrecto, selecciónelo, cierre la sesión y vuelva a abrirla.
- **Recibe un "Mensaje prohibido"** - Si recibe un mensaje “Prohibido” mientras que el complemento de Excel está cargando metadatos, la cuenta que ha iniciado sesión en el complemento de Excel no tiene permisos para usar el servicio, la instancia o en la base de datos objetivo. Para resolver este problema, compruebe que el nombre de usuario correcto aparece en la esquina superior derecha del complemento de Excel. Si aparece un nombre de usuario incorrecto, selecciónelo, cierre la sesión y vuelva a abrirla.
- **Aparece una página web en blanco sobre Excel** - Si se abre una página web en blanco durante proceso de inicio de sesión, la cuenta requiere AD FS, pero la versión de Excel que está ejecutando el complemento de Excel no es lo suficientemente reciente para cargar el cuadro de diálogo de inicio de sesión. Para resolver este problema, actualice la versión de Excel que usa. Para actualizar la versión de Excel si se encuentra en una empresa que está en el canal diferido, utilice la [Herramienta de implementación de Office](https://technet.microsoft.com/library/jj219422.aspx) para [cambiar del canal diferido al canal actual](https://technet.microsoft.com/library/mt455210.aspx).
- **Recibe un tiempo de espera mientras publica cambios de datos**: si recibe mensajes de tiempo de espera mientras intenta publicar cambios de datos en una entidad, piense en reducir el tamaño del lote de publicación para el libro afectado. Las entidades que desencadenan mayores cantidades de lógica en los cambios de registro pueden requerir que las actualizaciones se envíen en lotes más pequeños para ayudar a evitar tiempos de espera.
