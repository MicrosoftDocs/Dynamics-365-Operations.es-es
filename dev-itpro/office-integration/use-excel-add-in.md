---
title: Usar el complemento de Excel
description: "Este tema explica cómo abrir los datos de la entidad en Microsoft Excel y, a continuación, ver, actualizar y editar los datos mediante el complemento de Microsoft Dynamics Office para Excel. Para abrir los datos de la entidad, puede iniciar desde Excel o Microsoft Dynamics 365 for Operations."
author: ChrisGarty
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 267914
ms.assetid: 4e6c7194-a059-4057-bd62-ec0c802c36fd
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: c391fb70d837db9c0f167b392291fc1c5cc2bb53
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="use-the-excel-add-in"></a>Usar el complemento de Excel

[!include[banner](../includes/banner.md)]


Este tema explica cómo abrir los datos de la entidad en Microsoft Excel y, a continuación, ver, actualizar y editar los datos mediante el complemento de Microsoft Dynamics Office para Excel. Para abrir los datos de la entidad, puede iniciar desde Excel o Microsoft Dynamics 365 for Operations.

Al abrir los datos de la entidad en Microsoft Excel, puede ver y editar los datos de forma rápida y sencilla mediante el complemento de Microsoft Dynamics Office para Excel. Este complemento requiere Microsoft Excel 2016. **Nota:** si su inquilino de Microsoft Azure Active Directory (Azure AD) está configurado para usar Servicios de federación de Active Directory (AD FS), debe asegurarse de que se haya aplicado la actualización de mayo de 2016, de modo que el complemento de Excel pueda registrarle correctamente.

## <a name="open-entity-data-in-excel-when-you-start-from-dynamics-365-for-operations"></a>Abrir los datos de la entidad en Excel en el inicio desde Dynamics 365 for Operations
1.  En una página de Microsoft Dynamics 365 for Operations, haga clic en **Abrir en Microsoft Office**. Si el origen de datos raíz (tabla) de la página es el mismo que el origen de datos raíz de cualquier entidad, se generan las opciones **Abrir en Excel** predeterminadas en la página. Las opciones **Abrir en Excel** se pueden encontrar en las páginas utilizadas con frecuencia como, por ejemplo, **Todos los proveedores** y **Todos los clientes**.
2.  Haga clic en la opción **Abrir en Excel** y abra el libro que se ha generado. Este libro contiene información vinculante para la entidad, un puntero para su entorno y un puntero para el complemento de Excel.
3.  En Excel, haga clic en **Habilitar edición** para habilitar el complemento de Excel que desee ejecutar. El complemento de Excel se ejecuta en un panel a la derecha de la ventana de Excel.
4.  Si ejecuta el complemento de Excel por primera vez, haga clic en **Confiar en este complemento**.
5.  Si se le pide que inicie sesión, haga clic en **Iniciar sesión** y, a continuación, inicie sesión con las mismas credenciales empleadas para Dynamics 365 for Operations. El complemento de Excel utilizará el contexto de un inicio de sesión previo de Internet Explorer e iniciará su sesión automáticamente, si es posible. Por lo tanto, compruebe el nombre de usuario en la esquina superior derecha del complemento de Excel.

El complemento de Excel lee automáticamente los datos de la entidad que ha seleccionado. Tenga en cuenta que no habrá datos en el libro hasta que el complemento de Excel lo haya leído.

## <a name="open-entity-data-in-excel-when-you-start-from-excel"></a>Abrir los datos de la entidad en Excel en el inicio desde Excel
1.  En Excel, en la ficha **Insertar** , en el grupo **Complementos**, haga clic en **Tienda** para abrir la Tienda Office.
2.  En la Tienda Office, busque con la palabra clave “Dynamics” y haga clic en **Agregar** junto al **Complemento de Microsoft Dynamics Office** (el complemento de Excel).
3.  Si ejecuta el complemento de Excel por primera vez, haga clic en **Confiar en este complemento** para permitir la ejecución del complemento de Excel. El complemento de Excel se ejecuta en un panel a la derecha de la ventana de Excel.
4.  Haga clic en **Agregar información de servidor** para abrir el panel **Opciones**.
5.  Copie la URL de explorador de su instancia de Dynamics 365 for Operations objetivo, péguela en el campo **URL de servidor** y borre todo lo que sigue al nombre del host. La dirección URL resultante debe tener solo el nombre de host.
Por ejemplo, si la dirección https://xxx.dynamics.com/?cmp=usmf&amp;mi=CustTableListPage, elimine todo excepto **https://xxx.dynamics.com**.
6.  Haga clic en **Aceptar** y, a continuación en **Sí** para confirmar el cambio. El complemento de Excel se reinicia y carga los metadatos. El botón **Diseño** está ahora disponible. Si el complemento de Excel tiene un botón **Cargar applets**, probablemente no haya iniciado sesión como el usuario correcto. Para obtener más información, consulte “Aparece el botón Cargar applets” en la sección “Solución de problemas” de este tema.
7.  Haga clic en **Diseño**. El complemento de Excel recupera los metadatos de la entidad.
8.  Haga clic en **Agregar tabla**. Aparece una lista de entidades. Las entidades aparecen con el formato "Nombre - Etiqueta".
9.  Seleccione una entidad de la lista, como **Cliente - Clientes** y haga clic en **Siguiente**.
10. Para agregar un campo de la lista **Campos disponibles** a la lista **Campos seleccionados**, haga clic en el campo y en **Agregar**. También puede hacer doble clic en el campo.
11. Una vez que haya acabado de agregar campos a la lista **Campos seleccionados**, asegúrese de que el cursor se encuentre en el lugar adecuado de la hoja de cálculo (por ejemplo, celda A1), y haga clic en **Listo**. Haga clic en **Listo** para salir del diseñador.
12. Haga clic en **Actualizar** para extraer en un conjunto de datos.

## <a name="view-and-update-entity-data-in-excel"></a>Ver y actualizar datos de la entidad en Excel
Una vez que el complemento de Excel lea los datos de la entidad en el libro, puede actualizar los datos en cualquier momento haciendo clic en **Actualizar** en el complemento de Excel.

## <a name="edit-entity-data-in-excel"></a>Editar datos de la entidad en Excel
Puede cambiar los datos de la entidad de la forma necesaria y después publicarlos haciendo clic en **Publicar** en el complemento de Excel. Para editar un registro, seleccione una celda en la hoja de cálculo y, a continuación, modifique el valor de la celda. Para agregar un nuevo registro, siga uno de estos pasos:

-   Haga clic en cualquier lugar de la tabla de orígenes de datos y, a continuación, haga clic en **Nuevo** en el complemento de Excel.
-   Haga clic en la última fila de la tabla de orígenes de datos y pulse el tabulador hasta que el cursor salga de la última columna de dicha fila y se cree una nueva fila.
-   Haga clic en la fila justo debajo de la tabla de orígenes de datos y comience a introducir datos en una celda. Cuando saque el foco de dicha celda, la tabla se expandirá para incluir la nueva fila.
-   Para los enlaces de campos de registros de encabezado, haga clic en uno de los campos y, a continuación, haga clic en **Nuevo** en el complemento de Excel.

Tenga en cuenta que solo se puede crear un nuevo registro si la clave y los campos obligatorios están enlazados en la hoja de cálculo, o si los valores predeterminados se completaron mediante la condición de filtro.
Para eliminar un nuevo registro, siga uno de estos pasos:

-   Haga clic con el botón secundario en el número de la fila situado junto a la fila de la hoja de cálculo que desea eliminar y, a continuación, haga clic en **Eliminar**.
-   Haga clic con el botón secundario en la fila de la hoja de cálculo que desea eliminar y, a continuación, haga clic en **Eliminar** &gt; **Filas de tabla**.
Si los orígenes de datos se han agregado como relacionados, el encabezado se publica antes de las líneas. Si existen dependencias entre otros orígenes de datos, es posible que tenga que cambiar el orden de publicación predeterminado. Para cambiar el orden de la publicación, en el complemento de Excel, haga clic en el botón **Opciones** (el símbolo de engranaje). A continuación, en el ficha desplegable **Conector de datos**, haga clic en **Configurar orden de publicación**.

## <a name="add-or-remove-columns"></a>Agregar o quitar columnas
Puede usar al diseñador para ajustar las columnas que se agregan automáticamente a la hoja de cálculo.

1.  Inicie el diseñador de origen de datos del complemento de Excel haciendo clic en el botón **Opciones** (el símbolo del engranaje) y seleccione la casilla **Habilitar diseño**.
2.  Haga clic en **Diseño** en el complemento de Excel. Se enumeran todos los orígenes de datos.
3.  Al lado del origen de datos, haga clic en el botón **Editar** (el símbolo de lápiz).
4.  Ajuste la lista en la lista **Campos seleccionados** como sea necesario:
    -   Para agregar un campo de la lista **Campos disponibles** a la lista **Campos seleccionados**, haga clic en el campo y en **Agregar**. También puede hacer doble clic en el campo.
    -   Para quitar un campo de la lista **Campos seleccionados**, haga clic en el campo y en **Quitar**. También puede hacer doble clic en el campo.
    -   Para cambiar el orden de los campos, haga clic en la lista **Campos seleccionados** y en **Arriba** o **Abajo**.

5. Para aplicar los cambios al origen de datos, haga clic en **Actualizar**. Haga clic en **Listo** para salir del diseñador. 
6. Si ha agregado un campo (columna), haga clic en **Actualizar** para extraer un conjunto de datos actualizado.

## <a name="httpspowerappsmicrosoftcomenustutorialsdataplatforminteractiveexceltroubleshootingtroubleshooting"></a>[](https://powerapps.microsoft.com/enus/tutorials/dataplatforminteractiveexcel/#troubleshooting)Solución de problemas
Existen problemas que se pueden resolver con unos sencillos pasos.

-   **Aparece el botón Cargar applets.** Si el complemento de Excel tiene un botón **Cargar applets** tras el inicio de sesión, probablemente no haya iniciado sesión como el usuario correcto. Para resolver este problema, compruebe que el nombre de usuario correcto aparece en la esquina superior derecha del complemento de Excel. Si aparece un nombre de usuario incorrecto, púlselo, cierre la sesión y vuelva a abrirla.
-   **Recibe un "Mensaje prohibido.** Si recibe un mensaje “Prohibido” mientras que el complemento de Excel está cargando metadatos, la cuenta que ha iniciado sesión en el complemento de Excel no tiene permisos para usar el servicio, la instancia o en la base de datos objetivo. Para resolver este problema, compruebe que el nombre de usuario correcto aparece en la esquina superior derecha del complemento de Excel. Si aparece un nombre de usuario incorrecto, púlselo, cierre la sesión y vuelva a abrirla.
-   **Aparece una página web en blanco sobre Excel.** Si se abre una página web en blanco durante proceso de inicio de sesión, la cuenta requiere AD FS, pero la versión de Excel que está ejecutando el complemento no es lo suficientemente reciente para cargar el cuadro de diálogo de inicio de sesión. Para resolver este problema, actualice la versión de Excel que usa. Para actualizar la versión de Excel si se encuentra en una empresa que está en el canal diferido, utilice la [Herramienta de implementación de Office](https://technet.microsoft.com/library/jj219422.aspx) para [cambiar del canal diferido al canal actual](https://technet.microsoft.com/library/mt455210.aspx).





