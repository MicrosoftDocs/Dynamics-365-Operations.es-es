---
title: Configurar los parámetros de un formato de ER por entidad jurídica
description: En este tema se explica cómo puede configurar los parámetros de un formato de informes electrónicos (ER) por entidad jurídica.
author: NickSelin
ms.date: 10/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.openlocfilehash: 9b57c6165e5de4a115818a135ed1455e3b05e3f0
ms.sourcegitcommit: 4b7e9d074e368a08d2f75482b722dce0c69a4bbd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2021
ms.locfileid: "7733472"
---
# <a name="set-up-the-parameters-of-an-er-format-per-legal-entity"></a>Configurar los parámetros de un formato de ER por entidad jurídica

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

## <a name="prerequisites"></a>Requisitos previos

Para completar estos pasos, primero debe completar los pasos en [Configurar formatos de ER para usar parámetros que se especifican por entidad jurídica](er-app-specific-parameters-configure-format.md).

Para completar los ejemplos de este tema, debe tener acceso a Microsoft Dynamics 365 Finance para uno de los roles siguientes:

- Desarrollador de informes electrónicos
- Consultor funcional de informes electrónicos
- Administrador del sistema

## <a name="import-er-configurations"></a>Importar configuraciones de ER
Para importar configuraciones de ER, siga estos pasos: 

1. Inicie sesión en su entorno.
2. En el panel predeterminado, seleccione **Informes electrónicos**.
3. Seleccione **Configuraciones de informes**.
4. En la instancia actual de Finance, importe las configuraciones que exportó de los Regulatory Configuration Services (RCS) mientras completaba los pasos en [Configurar formatos de ER para usar parámetros que se especifican por entidad jurídica](er-app-specific-parameters-configure-format.md). Siga estos pasos para cada configuración de [informe electrónico (ER)](general-electronic-reporting.md) en el siguiente orden: modelo de datos, asignación de modelo y formatos.

    1. Seleccione **Cambio \> Cargar desde un archivo XML**.
    2. Seleccione **Examinar** para seleccionar el archivo para la configuración necesaria de ER en formato XML.
    3. Seleccione **Aceptar**.

    La siguiente ilustración muestra las configuraciones que debe tener cuando haya terminado.

    ![Página de configuraciones de ER.](./media/GER-AppSpecParms-ImportedConfigurations.PNG)

## <a name="set-up-parameters-for-the-demf-company"></a>Configurar parámetros para la empresa DEMF

Puede usar el marco de ER para configurar los parámetros específicos de la aplicación para un formato de ER.

1. Seleccionar la entidad jurídica **DEMF**.
2. En el árbol de configuraciones, seleccione el formato **Formato para aprender a buscar datos de LE**.
3. En el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Parámetros específicos de la aplicación**, seleccione **Configurar**.

    ![Página de parámetros específicos de la aplicación de ER para configurar los parámetros.](./media/GER-AppSpecParms-LookupForm.PNG)

    En la página **Parámetros específicos de la aplicación**, puede configurar las reglas para el origen de datos **Selector** del formato **Formato para aprender a buscar datos de LE**.

    Si el formato básico de ER contiene varios orígenes de datos del tipo **Búsqueda**, debe seleccionar el origen de datos deseado en la ficha desplegable **Búsquedas** antes de empezar a configurar el conjunto de reglas para el origen de datos.

    Para cada origen de datos, puede configurar reglas independientes para cada versión del formato de ER seleccionado.

    El conjunto completo de reglas para todos los orígenes de datos de la búsqueda que están disponibles en la versión seleccionada del formato básico de ER constituye los parámetros específicos de la aplicación para el formato de ER.

4. Seleccione la versión **1.1.1** del formato de ER.
5. En la ficha desplegable **Condiciones**, seleccione **Agregar**.
6. En el campo **Código** del nuevo registro, seleccione la flecha desplegable para abrir la búsqueda.

    La búsqueda presenta la lista de códigos de impuestos para la selección. El origen de datos **Model.Data.Tax** que se ha configurado en el formato básico de ER ha devuelto esta lista. Puesto que este origen de datos contiene el campo **Nombre**, el nombre de cada código de impuestos aparece en la búsqueda.

    ![Búsqueda del campo de código en la página de parámetros específicos de la aplicación de ER.](./media/GER-AppSpecParms-LookupForm-CodeFldPicker.PNG)

7. Seleccione el código de impuestos **VAT19**.
8. En el campo **Resultado de la búsqueda** del nuevo registro, seleccione la flecha desplegable para abrir la búsqueda. La búsqueda presenta la lista de valores para la enumeración del formato TaxationLevel para la selección.

    Tenga en cuenta que, si selecciona el alemán como el idioma preferido para el usuario que inicia sesión, las etiquetas de los valores de la búsqueda estarán en alemán, siempre que se haya traducido en el formato básico de ER. Además, si se ha traducido la etiqueta de un origen de datos de la búsqueda, esa etiqueta aparecerá en el idioma preferido del usuario en la pestaña **Búsquedas**.

    ![Campo de búsqueda traducido al alemán en la página de parámetros específicos de la aplicación de ER.](./media/GER-AppSpecParms-LookupForm-LookupFldPicker.PNG)

9. Seleccione el valor **Impuesto normal**.

    Al agregar este registro, define la siguiente regla: cuando se solicite el origen de datos de la búsqueda **Selector** y el código de impuesto **VAT19** se pase como argumento, **Impuesto normal** se devolverá como el nivel impositivo solicitado.

10. Seleccione **Agregar** y, a continuación, siga estos pasos:

    1. En el campo **Código**, seleccione el código de impuestos **InVAT19**.
    2. En el campo **Resultado de la búsqueda**, seleccione el valor **Impuesto normal**.

11. Seleccione **Agregar** y, a continuación, siga estos pasos:

    1. En el campo **Código**, seleccione el código de impuestos **VAT7**.
    2. En el campo **Resultado de la búsqueda**, seleccione el valor **Impuesto reducido**.

12. Seleccione **Agregar** y, a continuación, siga estos pasos:

    1. En el campo **Código**, seleccione el código de impuestos **InVAT**.
    2. En el campo **Resultado de la búsqueda**, seleccione el valor **Impuesto reducido**.

13. Seleccione **Agregar** y, a continuación, siga estos pasos:

    1. En el campo **Código**, seleccione el código de impuestos **THIRD**.
    2. En el campo **Resultado de la búsqueda**, seleccione el valor **Ningún impuesto**.

14. Seleccione **Agregar** y, a continuación, siga estos pasos:

    1. En el campo **Código**, seleccione el código de impuestos **InVAT0**.
    2. En el campo **Resultado de la búsqueda**, seleccione el valor **Ningún impuesto**.

15. Seleccione **Agregar** y, a continuación, siga estos pasos:

    1. En el campo **Código**, seleccione la opción **\*No en blanco\***.
    2. En el campo **Resultado de la búsqueda**, seleccione el valor **Otro**.

    Al agregar este último registro, define la siguiente regla: cuando el código de impuestos que se pasa como argumento no cumpla ninguna de las reglas anteriores, el origen de datos de la búsqueda devolverá **Otro** como el nivel impositivo solicitado.

    ![Último registro añadido en la página de parámetros específicos de la aplicación de ER.](./media/GER-AppSpecParms-LookupForm-RulesSet.PNG)

16. En el campo **Estado**, seleccione **Completado**.

    Cuando ejecute una versión de formato de ER que tenga un estado **Completado** o **Compartido**, este conjunto de reglas debe estar en el estado **Completado**. De lo contrario, la ejecución del formato básico de ER se interrumpirá cuando el formato trate de cargar datos de este conjunto de reglas mientras se está ejecutando el origen de datos de la búsqueda **Selector**.

    Cuando ejecute una versión de formato de ER que tenga un estado **Borrador**, el formato básico de ER puede acceder a este conjunto de reglas, independientemente de su estado.

17. Seleccione **Guardar**.
18. Cierre la página **Parámetros específicos de la aplicación**.

## <a name="run-the-er-format-in-the-demf-company"></a>Ejecutar el formato de ER en la empresa DEMF
Para ejecutar el formato de ER en la empresa DEMF, siga estos pasos: 

1. En el árbol de configuraciones, seleccione el formato **Formato para aprender a buscar datos de LE**.
2. En el panel de acciones, haga clic en **Ejecutar**.
3. En el cuadro de diálogo que aparece, seleccione **Aceptar**.
4. Descargue el extracto que se ha generado y almacénelo localmente.

    En la declaración generada, tenga en cuenta que el resumen del código de impuestos **InVAT7** está en el nivel **Reducido** y los resúmenes de los códigos de impuestos **VAT19** e **InVA19** están en el nivel **Normal**. Este comportamiento se determina según la configuración del conjunto de reglas que dependen de la entidad jurídica.

5. Vaya a **Impuestos \> Impuestos indirectos \> Impuestos \> Códigos de impuestos**.
6. Seleccione el código de impuestos **InVAT7**.
7. En el panel de acciones, en la pestaña **Código de impuestos**, en el grupo **Consultas**, seleccione **Impuestos registrados** para ver información acerca del valor de los impuestos y el tipo impositivo aplicado por código de impuestos.

    ![Página de impuestos registrados.](./media/GER-AppSpecParms-Statement.PNG)

8. Cierre la página **Impuestos registrados**.

## <a name="set-up-parameters-for-the-usmf-company"></a>Configurar parámetros para la empresa USMF
Para configurar los parámetros de la empresa USMF, complete los siguientes pasos: 

1. Seleccionar la entidad jurídica **USMF**.
2. Vaya a **Administración de la organización \> Informes electrónicos \> Configuraciones**.
3. En el árbol de configuraciones, expanda el elemento **Modelo para aprender llamadas con parámetros**, expanda el elemento **Formato para aprender llamadas con parámetros** y seleccione el formato **Formato para aprender a buscar datos de LE**.
4. En el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Parámetros específicos de la aplicación**, seleccione **Configurar**.
5. Seleccione la versión **1.1.1** del formato de ER seleccionado.
6. En la ficha desplegable **Condiciones**, seleccione **Agregar**.
7. En el campo **Código** del nuevo registro, seleccione la flecha desplegable para abrir la búsqueda.

    La búsqueda presenta ahora la lista de códigos de impuestos para los impuestos de empresa **USMF** para su selección.

    ![Códigos de impuestos para el impuesto de sociedades de USMF.](./media/GER-AppSpecParms-LookupForm-CodeFldPicker2.PNG)

8. Seleccione el código de impuestos **EXEMPT**.
9. En el campo **Resultado de la búsqueda** del nuevo registro, seleccione el valor **Ningún impuesto**.
10. Seleccione **Agregar**.
11. En el campo **Código** del nuevo registro, seleccione la opción **\*No en blanco\***.
12. En el campo **Resultado de la búsqueda** del nuevo registro, seleccione el valor **Impuesto normal**.
13. En el campo **Estado**, seleccione **Completado**.
14. Seleccione **Guardar**.

    ![Página de parámetros específicos de la aplicación de ER.](./media/GER-AppSpecParms-LookupForm-RulesSet2.PNG)

15. Cierre la página **Parámetros específicos de la aplicación**.

## <a name="run-the-er-format-in-the-usmf-company"></a>Ejecutar el formato de ER en la empresa USMF
Para ejecutar el formato de ER en la empresa USMF, complete los siguientes pasos:

1. En el árbol de configuraciones, seleccione el formato **Formato para aprender a buscar datos de LE**.
2. En el panel de acciones, haga clic en **Ejecutar**.
3. En el cuadro de diálogo que aparece, seleccione **Aceptar**.
4. Descargue el extracto que se ha generado y almacénelo localmente.

    En la declaración generada, tenga en cuenta que ahora ha reutilizado el mismo formato de ER para una entidad jurídica diferente, pero sin realizar ningún ajuste en el formato de ER.

## <a name="reuse-legal-entitydependent-parameters"></a>Reutilizar parámetros que dependen de la entidad jurídica

### <a name="duplicate-existing-parameters"></a>Duplicar parámetros existentes

#### <a name="export-parameters"></a>Exportar parámetros
Para exportar parámetros, complete los siguientes pasos:

1. Vaya a **Administración de la organización \> Espacios de trabajo \> Informes electrónicos**.
2. Seleccione **Configuraciones de informes**.
3. En el árbol de configuraciones, seleccione el formato **Formato para aprender a buscar datos de LE**.
4. En el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Parámetros específicos de la aplicación**, seleccione **Configurar**.
5. Seleccione la versión **1.1.1** del formato de ER.
6. En el panel de acciones, seleccione **Exportar**.
7. Descargue el archivo que se ha generado y almacénelo localmente.

    El conjunto configurado de parámetros específicos de la aplicación se ha exportado ahora como un archivo XML.

#### <a name="import-parameters"></a>Importar parámetros
Para importar parámetros, complete los siguientes pasos:

1. Seleccione la versión **1.1.2** del formato de ER.
2. En el panel de acciones, seleccione **Importar**.
3. Seleccione **Sí** para confirmar que desea anular los parámetros específicos de la aplicación existentes para esta versión del formato.
4. Seleccione **Examinar** para encontrar el archivo que contiene los parámetros específicos de la aplicación exportados para la versión **1.1.1**.
5. Seleccione **Aceptar**.

    La versión **1.1.2** del formato de ER ahora tiene los mismos parámetros específicos de la aplicación que configuró originalmente para la versión **1.1.1**.

##### <a name="applicability-considerations"></a>Consideraciones de aplicabilidad

Los parámetros específicos de la aplicación de un formato de ER dependen de la entidad jurídica. Para reutilizar los parámetros específicos de la aplicación que se configuraron para una entidad jurídica en una entidad jurídica diferente, debe exportarlos mientras inicia sesión en la primera entidad jurídica. Después, impórtelos después de iniciar sesión en la otra entidad jurídica.

También puede usar este enfoque de importar y exportar para transferir un formato de ER relacionado con parámetros específicos de la aplicación que se configuró originalmente en una instancia de Finance a otra instancia de Finance.

Si configura parámetros específicos de la aplicación para una versión de un formato ER y luego importa una versión posterior del mismo formato en la instancia de Finance actual, los parámetros específicos de la aplicación existentes no se aplicarán a la versión importada a menos que use la característica **Usar parámetros específicos de la aplicación de versiones anteriores de formatos de informes electrónicos**. Para obtener más información, consulte la sección [Reutilizar parámetros existentes](#reuse-existing-parameters) más adelante en este tema.

Cuando selecciona un archivo para importarlo, la estructura de los parámetros específicos de la aplicación en ese archivo se compara con la estructura los orígenes de datos correspondientes del tipo **Búsqueda** en el formato de ER seleccionado para su importación. De forma predeterminada, la importación se completa solo si la estructura de cada parámetro específico de la aplicación coincide con la estructura del origen de datos correspondiente en el formato de ER seleccionado para su importación. Si las estructuras no coinciden, recibe un mensaje de advertencia que indica que la importación no se puede completar. Si fuerza la importación, los parámetros específicos de la aplicación existentes para el formato de ER seleccionado se borrarán, y deberá configurarlos desde el principio.

### <a name="reuse-existing-parameters"></a>Reutilizar parámetros existentes

A partir de la versión 10.0.23 de Dynamics 365 Finance, puede reutilizar los parámetros específicos de la aplicación que se han configurado para una versión de un formato ER cuando ejecuta una versión superior del mismo formato. Para hacerlo, habilite la característica **Usar parámetros específicos de la aplicación de versiones anteriores de formatos de informes electrónicos** en el espacio de trabajo **Administración de características**. Cuando esta característica está habilitada y ejecuta una versión de un formato ER que intenta leer parámetros específicos de la aplicación, el informe electrónico intentará encontrar parámetros específicos de la aplicación que se hayan configurado para la versión en ejecución de este formato. O, cuando no estén disponibles, para la versión inferior más cercana de este formato.

> [!NOTE]
> Puede reutilizar parámetros específicos de la aplicación solo en el ámbito de la entidad jurídica actual.
>
> Se muestra un error en tiempo de ejecución cuando ejecuta una versión superior de un formato de ER que está intentando reutilizar parámetros específicos de la aplicación que se han configurado para una versión inferior del mismo formato y la estructura de al menos un origen de datos del tipo **Búsqueda** en la versión del formato superior ha cambiado.

## <a name="relationship-between-application-specific-parameters-and-an-er-format"></a>Relación entre los parámetros específicos de la aplicación y un formato de ER

La relación entre un formato de ER y sus parámetros específicos de la aplicación la establece el código de identificación único independiente de la instancia del formato de ER. Por lo tanto, cuando elimina un formato de ER de Finance, los parámetros específicos de la aplicación que se configuran para el formato de ER se mantienen en la instancia actual de Finance. Se puede acceder a estos cuando el formato básico de ER se reimporte en esta instancia de Finance.

## <a name="access-application-specific-parameters-by-using-the-er-framework"></a>Acceder a parámetros específicos de la aplicación mediante el marco de ER

En el ejemplo anterior, ha accedido a parámetros específicos de la aplicación de un formato de ER mediante el marco de ER. Este enfoque no le permite restringir el acceso a los parámetros específicos de la aplicación de un formato de ER específico. Si debe aplicar como restricciones, siga estos pasos. 

1. Volver a usar un elemento de menú **ERSolutionAppSpecificParametersDesigner** existente o implemente su propio elemento de menú **ERSolutionAppSpecificParametersDesigner**.

    ![Visualización de elementos de menú de ERSolutionAppSpecificParametersDesigner.](./media/GER-AppSpecParms-LookupForm-Access1.PNG)

2. Siga uno de estos pasos:

    1. Cree un nuevo botón de elementos de menú y vincúlelo al registro correspondiente de la tabla **ERSolutionTable** estableciendo su propiedad **Origen de datos** en **ERSolutionTable**.

        ![Visualización de la configuración de nuevos elementos de menú.](./media/GER-AppSpecParms-LookupForm-Access2.PNG)

    2. Cree un simple botón y anule el método **En el que se ha hecho clic** como se muestra en el siguiente ejemplo.

        Mediante este enfoque, puede especificar un id. de solución único (definido mediante el valor **GUID**) para permitir el acceso a los parámetros específicos de la aplicación de solo un formato de ER específico y a las copias descendientes que se han derivado de este.
        
        ```xpp
        public void clicked()
            {
                super();

                ERSolutionTable solutionTableRecord = ERSolutionTable::findByGUID(str2Guid('ADACCB2F-EFD1-4C90-877D-7E1E5D1AEE92'));

                Args args = new Args();
                args.record(solutionTableRecord);
                args.caller(this);

                new MenuFunction(menuItemDisplayStr(ERSolutionAppSpecificParametersDesigner), MenuItemType::Display)
                    .run(args);
            }
        ```

## <a name="additional-resources"></a>Recursos adicionales

[Diseñador de fórmulas en los informes electrónicos](general-electronic-reporting-formula-designer.md)

[Configurar formatos de ER para usar parámetros que se especifican por entidad jurídica](er-app-specific-parameters-configure-format.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
