---
title: Use el complemento de Excel
description: "Este tema explica cómo los datos de la entidad abierto en Microsoft Excel y, a continuación, actualiza ver, y editar los datos mediante el complemento de la oficina de Microsoft Dynamics for Excel. Para abrir los datos de la entidad, puede iniciar desde Excel o de Microsoft Dynamics 365 para las operaciones."
author: ChrisGarty
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 267914
ms.assetid: 4e6c7194-a059-4057-bd62-ec0c802c36fd
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: af7e7288f741b3c519227e2778c4c4311c3a2012
ms.openlocfilehash: 8af663b47117759ed3b2e2ed8eee85ae4df100d1
ms.lasthandoff: 03/31/2017


---

# <a name="use-the-excel-add-in"></a>Use el complemento de Excel

Este tema explica cómo los datos de la entidad abierto en Microsoft Excel y, a continuación, actualiza ver, y editar los datos mediante el complemento de la oficina de Microsoft Dynamics for Excel. Para abrir los datos de la entidad, puede iniciar desde Excel o de Microsoft Dynamics 365 para las operaciones.

Por datos de la entidad que abren en Microsoft Excel, puede de forma rápida y sencilla ver y editar los datos mediante el complemento de la oficina de Microsoft Dynamics for Excel. Este complemento requiere Microsoft Excel 2016. ** Nota: ** Si configuran al arrendatario de Microsoft Azure Active Directory (ANUNCIO blanco cielo) usar el Servicios de federación de Active Directory (ANUNCIO FS), debe asegurarse de que se haya aplicado la actualización de mayo de 2016, de modo que el complemento de Excel pueda correctamente firmarle en.

## <a name="open-entity-data-in-excel-when-you-start-from-dynamics-365-for-operations"></a>Datos de la entidad abierto en Excel cuando deja de Dynamics 365 para las operaciones
1.  En una página en Microsoft Dynamics 365 para las operaciones, abra ** clic en Microsoft Office **. Si el origen de datos de la tabla raíz () para la página es el mismo que el origen de datos para cualquier entidad, valor predeterminado ** Abrir de la raíz en Excel ** las opciones que se genera para la página. ** Abrir en Excel ** opciones se puede encontrar en las páginas utilizadas con frecuencia, por ejemplo ** todos los proveedores ** ** y todos los clientes **.
2.  Haga clic en ** abra en Excel ** una opción, y abra el libro se ha generado. Este libro tiene información de enlace para la entidad, un puntero a un entorno, y un puntero al complemento de Excel.
3.  En Excel, haga clic ** ediciones de permiso ** para habilitar el complemento de Excel que desee ejecutar. El complemento de Excel se ejecuta en un panel a la derecha de la ventana de Excel.
4.  Si ejecuta el complemento de Excel por primera vez, haga clic ** dependan este complemento **.
5.  Si se le pedirá que iniciar sesión, haga clic en firme ** ** en y, a continuación en firme mediante las mismas credenciales que se firmaba en a Dynamics 365 para las operaciones. El complemento de Excel utilizará un inicio anterior en contexto de Internet Explorer y se le firmará en, si es posible. Por lo tanto, compruebe el nombre de usuario en la esquina superior derecha del complemento de Excel.

El complemento de Excel lee automáticamente los datos para la entidad que ha seleccionado. Tenga en cuenta que no habrá datos en el libro hasta que el complemento de Excel lo lea en.

## <a name="open-entity-data-in-excel-when-you-start-from-excel"></a>Datos de la entidad abierto en Excel cuando deja Excel
1.  En Excel, en ** Insert **, en la ficha ** Complementos ** el grupo, haga clic ** ** almacén para abrir el almacén de la oficina.
2.  En el almacén de oficina, busque en la palabra clave “Dynamics,” ** clic y agregue ** junto al ** complemento de la oficina de Microsoft Dynamics ** (complemento de Excel).
3.  Si ejecuta el complemento de Excel por primera vez, haga clic en ** dependan este ** complemento para habilitar el complemento de Excel que desee ejecutar. El complemento de Excel se ejecuta en un panel a la derecha de la ventana de Excel.
4.  Haga clic en ** agregar información del servidor ** a abrir ** opciones ** el panel.
5.  ¿Copia el explorador que la dirección URL de Dynamics 365 su destino de las operaciones presupuesto como ejemplo, en peguelo ** dirección URL del servidor ** campo y, a continuación eliminan todos después del nombre de host (por ejemplo, **/? de la cancelación** cmp=usmf&mi=CustTableListPage). La dirección URL resultante debe tener sólo el nombre de host (por ejemplo, ** https://xxx.dynamics.com**).
6.  Haga clic ** éste **, haga clic en Sí ** ** para confirmar el cambio. Los los reinicia de Excel y los metadatos de las cargas. ** Diseño ** el botón está disponible ahora. Si el complemento de Excel tiene ** a los subprogramas de flete ** abotone, no se firman probablemente en como el usuario correcto. Para obtener más información, consulte “los subprogramas de flete que el botón se muestra” en la sección “de la solución de problemas” de este tema.
7.  Haga clic en diseño ** **. Metadatos de la entidad recupera archivos de el complemento de Excel.
8.  Haga clic en ** agregue la tabla **. Una lista de partes aparece. Las entidades en nombre “-” etiquete el formato.
9.  Seleccione una entidad de la lista, como ** cliente - Cliente **, y haga clic en Siguiente ** **.
10. Para agregar un campo ** los campos disponibles ** de la lista ** los campos seleccionados ** a la lista, haga clic en el campo y, a continuación haga clic en ** agregue **. De forma alternativa, haga doble clic en el campo.
11. Una vez agregados los campos seleccionados ** los campos seleccionados ** a la lista, asegúrese de que el cursor se encuentre en el lugar adecuado en la hoja de cálculo (por ejemplo, celda A1), y haga clic en ** hecho **. A continuación haga clic en ** hecho ** para salir del diseñador.
12. Haga clic en ** actualización ** para extraer en un conjunto de datos.

## <a name="view-and-update-entity-data-in-excel"></a>Ver y datos actualizados de la entidad en Excel
Una vez que el complemento de Excel leer datos de la entidad en el libro, puede actualizar los datos en cualquier momento haciendo clic en ** actualización ** en el complemento de Excel.

## <a name="edit-entity-data-in-excel"></a>Datos de la entidad de edición en Excel
Puede cambiar datos de la parte como lo requiere y después publica posterior haciendo clic en ** publique ** en el complemento de Excel. Para editar un registro, seleccione una celda en la hoja de cálculo y, a continuación modifican el valor de la celda. Para agregar un nuevo registro, siga uno de estos pasos:

-   Haga clic en cualquier lugar de la hoja de cálculo y, a continuación haga clic en ** nuevo ** en el complemento de Excel.
-   Haga clic en la última fila de la hoja de cálculo, y presione el tabulador hasta que el cursor desplace de la columna de dicha última fila y se crea una nueva fila.
-   Haga clic en la fila inmediatamente por debajo de la hoja de cálculo, y antes de registrar datos en una celda. Cuando mueve el enfoque de dicha celda, la hoja de cálculo expande para incluir la nueva fila.

Para eliminar un registro, siga uno de estos pasos:

-   Haga clic con el botón secundario en el número de la fila situada junto a la fila de la hoja de cálculo que desea eliminar y, a continuación haga clic en ** Eliminar **.
-   Haga clic con el botón secundario en la fila de la hoja de cálculo que desea eliminar y, a continuación haga clic en ** Eliminar ** &gt; ** las filas de la tabla **.

## <a name="add-or-remove-columns"></a>Agregar o quitar columnas
Puede usar al diseñador para ajustar las columnas que se agregan automáticamente a la hoja de cálculo.

1.  Iniciar el diseñador del origen de datos del complemento de Excel haciendo clic en las opciones ** ** botón (el símbolo de engranaje) y selecciona ** permiso diseñar ** la casilla.
2.  Haga clic en diseño ** ** en el complemento de Excel. Se enumeran todos los orígenes de datos.
3.  Al lado del origen de datos, haga clic en ** edición ** el botón (el símbolo de lápiz).
4.  Ajustar la lista ** en los campos seleccionados ** la lista como sea necesario:
    -   Para agregar un campo ** los campos disponibles ** de la lista ** los campos seleccionados ** a la lista, haga clic en el campo y, a continuación haga clic en ** agregue **. De forma alternativa, haga doble clic en el campo.
    -   Para quitar un campo ** los campos seleccionados ** de la lista, haga clic en el campo y, a continuación haga clic en ** quite **. De forma alternativa, haga doble clic en el campo.
    -   Para cambiar el orden de campos, haga clic en el campo en ** los campos seleccionados ** la lista, y haga clic en ** ** por arriba o abajo ** **.

5.  Aplicar los cambios al origen de datos haciendo clic en ** ** actualización. A continuación haga clic en ** hecho ** para salir del diseñador. Si agregó un campo (columna), haga clic ** actualización ** para extraer en un conjunto de datos actualizado.

## <a name="httpspowerappsmicrosoftcomenustutorialsdataplatforminteractiveexceltroubleshootingtroubleshooting"></a>[](https://powerapps.microsoft.com/enus/tutorials/dataplatforminteractiveexcel/#troubleshooting)Troubleshooting
Existen problemas que se pueden resolver a través de algunos pasos fáciles.

-   ** Aparece el botón de los subprogramas de flete. ** Si el complemento de Excel tiene ** a los subprogramas de flete ** abotone después de inicio en, no se firman probablemente en como el usuario correcto. Para resolver este problema, compruebe que el nombre de usuario correcto aparece en la esquina superior derecha del complemento de Excel. Si aparece un nombre de usuario incorrecto, haga clic en él, firme salida, y después firme devolución en.
-   ** Se recibe un mensaje “prohíbe”. ** Si recibe un mensaje “prohíbe” mientras que el complemento de Excel se cargue metadatos, la cuenta que se iniciar sesión al complemento de Excel no tiene permiso para usar el servicio, la instancia, o en la base de datos concreta. Para resolver este problema, compruebe que el nombre de usuario correcto aparece en la esquina superior derecha del complemento de Excel. Si aparece un nombre de usuario incorrecto, haga clic en él, firme salida, y después firme devolución en.
-   ** Una página Web en blanco se muestra información acerca de Excel. ** Si una página Web en blanco abre durante proceso de inicio en la cuenta, requiere el ANUNCIO FS, pero la versión de Excel que esté ejecutando el complemento no es suficiente reciente cargar inicio en el cuadro de diálogo. Para resolver este problema, actualice la versión de Excel que usa. Para actualizar la versión de Excel cuando se encuentre en una empresa que esté en el canal diferido, utilice [herramienta de implementación] de la oficina (https://technet.microsoft.com/library/jj219422.aspx) [movimiento de canal diferido al canal actual (https://technet.microsoft.com/library/mt455210.aspx)].



