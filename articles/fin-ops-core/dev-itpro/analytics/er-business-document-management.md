---
title: Visión general de la gestión de documentos empresariales
description: Este tema proporciona información acerca de cómo utilizar la característica de gestión de documentos empresarial del marco de ER.
author: NickSelin
manager: AnnBe
ms.date: 08/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERSecurityAccessEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0a2fa6a7f6efef05862a3727a80122c22d591487
ms.sourcegitcommit: 4162d9ef4239c9d4e5297b8aaa903dd54f9cafc3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "2824529"
---
# <a name="business-document-management-overview"></a>Visión general de la gestión de documentos empresariales

Los usuarios empresariales usan la [Visión general de los informes electrónicos (ER)](general-electronic-reporting.md) para configurar formatos para documentos de salida en función de los requisitos legales de diversos países o regiones. Los usuarios también pueden definir el flujo de datos para especificar qué datos de la aplicación se colocan en los documentos generados. El marco de ER genera documentos de salida en los formatos de Microsoft Office (libros de Excel o documentos de Word) a través de plantillas predefinidas. Las plantillas se rellenan con los datos requeridos según el flujo de datos configurado mientras se generan los documentos necesarios. Cada formato configurado se puede publicar como parte de una solución de ER para generar documentos de salida específicos. Esto se representa mediante una configuración de formato de ER que pueda contener plantillas que puede usar para generar distintos documentos de salida. Los usuarios empresariales pueden usar este marco para gestionar los documentos empresariales necesarios.

**Gestión de documentos empresariales** aprovecha el marco de ER y permite a los usuarios empresariales editar plantillas de documentos empresariales mediante el servicio de Microsoft Office 365 o la aplicación de escritorio de Microsoft Office apropiada. Las ediciones a los documentos pueden incluir modificar los diseños de los documentos empresariales y agregar marcadores para datos sin cambios del código fuente ni nuevas implementaciones. No se requiere ningún conocimiento del marco de ER para actualizar las plantillas de los documentos empresariales.

> [!NOTE]
> Tenga en cuenta que la gestión de documentos empresariales le permite modificar las plantillas que se utilizan para generar documentos empresariales como facturas, pedidos, etc.. Cuando se modifica una plantilla y se publica una nueva versión de ella, esta versión se usa para generar los documentos empresariales requeridos. La gestión de documentos empresariales no se puede usar para modificar los documentos empresariales ya generados.

## <a name="supported-deployments"></a>Implementaciones compatibles

Actualmente, la función de gestión de documentos empresariales se implementa solo para implementaciones en la nube. Si esta función es fundamental para su implementación local, háganoslo saber con comentarios en el sitio [Ideas](https://experience.dynamics.com/ideas/).

## <a name="supported-microsoft-office-applications"></a>Aplicaciones de Microsoft Office admitidas

Para usar la gestión de documentos empresariales para editar plantillas en formatos de Excel o Word mediante aplicaciones de escritorio de Microsoft Office, debe tener instalado Microsoft Office 2010 o versiones posteriores. Se admite en implementaciones locales y en la nube.

## <a name="business-document-availability"></a>Disponibilidad de los documentos empresariales

Los siguientes informes, con plantillas basadas Excel, estarán disponibles con el lanzamiento de la versión preliminar pública:

**Clientes** (agosto 2019)

- Factura de anticipo de ventas
- Albarán del pedido de ventas

**Proveedores** (agosto 2019)

- Factura de anticipo de compra
- Pedido de compra
- Albarán del pedido de compra

Más informes estarán disponibles. Las notificaciones especiales sobre informes adicionales se enviarán por separado. 

Lista completa de todos los informes previstos para la versión de octubre de 2019 se puede encontrar en [Informes de documentos empresariales configurables en Word y Excel](https://docs.microsoft.com/en-us/dynamics365-release-plan/2019wave2/dynamics365-finance-operations/configurable-business-documents-reporting-word-excel-pdf#feature-details). Para obtener más información acerca de esta característica, complete el ejemplo de este tema.

## <a name="configure-er-parameters"></a>Configurar los parámetros de ER

Dado que la gestión de documentos empresariales aprovecha el marco de ER, debe configurar los parámetros de ER para empezar a trabajar con la gestión de los documentos empresariales. Para ello, debe configurar los parámetros de ER como se describe en [Configurar el informe electrónico (ER)](electronic-reporting-er-configure-parameters.md). También debe agregar un nuevo proveedor de configuración como se describe en [Crear proveedores de configuración y marcarlos como activos](tasks/er-configuration-provider-mark-it-active-2016-11.md).

![Espacio de trabajo de ER](./media/BDM-Overview-ERSetting.png)

## <a name="import-er-solutions"></a>Importar soluciones de ER

Los ejemplos de configuraciones de ER se utilizan en el ejemplo de este procedimiento. Debe importar, en su instancia actual de Dynamics 365 Finance, las configuraciones de ER que contengan las plantillas de documentos empresariales que se pueden editar mediante la gestión de documentos empresariales. Descargue y luego almacene localmente los archivos siguientes para completar este procedimiento.

**Solución de facturación a clientes de ER de ejemplo**

| **Archivo**                                  | **Contenido**                                |
|-------------------------------------------|--------------------------------------------|
| Customer invoicing model.version.2.xml    | [Configuración del modelo datos de ER](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Customer FTI report (GER).version.2.3.xml | [Configuraciones del formato de ER para facturas de servicios](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

**Solución de cheques de pago de ER de ejemplo**

| **Archivo**                                  | **Contenido**                                |
|-------------------------------------------|--------------------------------------------|
| Model for cheques.version.10.xml          | [Configuración del modelo datos de ER](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Cheques printing format.version.10.9.xml  | [Configuración del formato de ER para cheques de pago](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

**Solución de comercio exterior de ER de ejemplo**

| **Archivo**                                  | **Contenido**                                |
|-------------------------------------------|--------------------------------------------|
| Intrastat model.version.1.xml             | [Configuración del modelo datos de ER](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Intrastat report.version.1.9.xml          | [Configuración del formato de ER para informes de control de intrastat](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

Use el procedimiento siguiente para importar cada archivo. Importe la configuración del *modelo de datos* de ER de cada solución de ER en las tablas de más arriba antes importar la configuración correspondiente del *formato* de ER.

1. Abra la página **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. Seleccione **Cambio** en la parte superior de la página.
3. Seleccione **Cargar desde un archivo XML**.
4. Seleccione **Explorar** para cargar el archivo XML requerido.
5. Seleccione **Aceptar** para confirmar la importación de la configuración.

![Página de configuraciones de ER](./media/BDM-Overview-ERSolutions.png)


Como alternativa, puede importar las configuraciones de formato de ER publicadas oficialmente desde Microsoft Dynamics Lifecycle Service (LCS). Por ejemplo, para completar este procedimiento puede importar la última versión de la configuración del formato de ER **Factura de servicios (Excel)**. El modelo de datos de ER correspondiente y las configuraciones de asignación de modelo de ER se importarán automáticamente.

![Página de contenido de la biblioteca de activos compartidos de LCS](./media/BDM-Overview-SharedAssetLibrary.png)

Para obtener más información acerca de la importación de las configuraciones de ER, consulte [Gestionar el ciclo de vida de la configuración de ER](general-electronic-reporting-manage-configuration-lifecycle.md).


## <a name="enable-business-document-management"></a>Habilitar la gestión de documentos empresariales

Para iniciar la gestión de documentos empresariales, debe abrir el área de trabajo **Administración de características** y habilitar la característica **Administración de documentos empresariales**.

Use el procedimiento siguiente para habilitar la funcionalidad de gestión de documentos empresariales para todas las entidades jurídicas.

1. Abra el espacio de trabajo **Administración de características**.
2. En la pestaña **Nuevo**, seleccione la característica **Gestión de documentos empresariales** de la lista.
3. Seleccione **Habilitar ahora** para activar la característica seleccionada.
4. Actualice la página para obtener acceso a la característica nueva.

>[!NOTE]
> También debe habilitar **Experiencia de interfaz de usuario similar a oficina para la gestión de documentos empresariales** para usar la nueva interfaz de administración del documentos empresariales

![Espacio de trabajo Administración de características.](./media/BDM-Overview-FMEnabling.png)

Para obtener más información acerca de la activación nuevas características, consulte [Visión general de la Administración de características](../../fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="configure-parameters"></a>Configurar parámetros

Use la información en las secciones siguientes para configurar los parámetros básicos para la gestión de documentos empresariales.

### <a name="prerequisites-for-parameter-setup"></a>Requisitos previos para configurar parámetros
Antes de poder configurar la gestión de documentos empresariales, debe configurar el tipo de documento requerido en el marco de la gestión de documentos. Este tipo de documento se usa para especificar un almacenamiento temporal de los documentos en los formatos de Office (Excel y Word) que se utilizan como plantillas para los informes de ER. La plantilla de almacenamiento temporal se puede editar mediante las aplicaciones de escritorio de Office.

Para este tipo de documento, los valores de atributo siguientes se deben seleccionar.

| **Nombre de atributo**  | **Valor de atributo**   |
|---------------------|-----------------------|
| Clase               | Vincular archivo           |
| Grupo               | Archivo                  |
| Ubicación            | SharePoint            |

Para obtener información sobre cómo configurar los parámetros de gestión de documentos requeridos y los tipos de documentos, consulte [Configurar la gestión de documentos](../../fin-ops/organization-administration/configure-document-management.md).

![Configurar el tipo de documento para la gestión de documentos](./media/BDM-Overview-DMSetting.png)

### <a name="set-up-parameters"></a>Configurar parámetros

Los parámetros básicos para la gestión de documentos empresariales se pueden configurar en la página **Parámetros de documentos empresariales**. Solo usuarios específicos pueden tener acceso a la página. Esto incluye:

- Usuarios que tienen asignado el rol de **Administrador del sistema**.
- Usuarios que están asignados a cualquier rol configurado para ejecutar el derecho, **Mantener los parámetros de gestión de documentos empresariales** (nombre AOT **ERBDMaintainParameters**).

Use el procedimiento siguiente para configurar parámetros básicos para todas las entidades jurídicas.

1. Inicie sesión como usuario con acceso a la página **Parámetros de documentos empresariales**.
2. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Gestión de documentos empresariales** \> **Parámetros de los documentos empresariales**.
3.  En la página **Parámetros de los documentos empresariales**, en la pestaña **Datos adjuntos**, en el campo **Tipo de documento de SharePoint**, defina el tipo de documento que se debe utilizar para almacenar temporalmente plantillas en formatos de Office mientras se están editando con aplicaciones de escritorio de la Office. 

> [!NOTE]
> Solo los tipos de documento que se configuran con una ubicación de SharePoint están disponibles para este parámetro.

![Configurar los parámetros para la gestión de documentos empresariales](./media/BDM-Overview-BDMSetting.png)

El tipo de documento seleccionado es específico de una empresa y se usará cuando el usuario esté trabajando con la gestión de documentos empresariales en la empresa para la que se configuró el tipo de documento seleccionado. Cuando el usuario esté trabajando con la gestión de documentos empresariales en otra empresa, se usará el mismo tipo de documento seleccionado si no se hubiera configurado uno para esta empresa. Cuando se ha configurado un tipo de documento, se usará en lugar del seleccionado en el campo **Tipo de documento de SharePoint**.

## <a name="configure-access-permissions"></a>Configurar los permisos de acceso

De forma predeterminada, cuando no se habilita el acceso a los permisos de la gestión de documentos empresariales, cada usuario con acceso al espacio de trabajo de la gestión de documentos empresariales verá todas las plantillas de la solución de ER disponibles. El espacio de trabajo de gestión de documentos empresariales mostrará solo las plantillas que residen en configuraciones del formato de ER y que están marcadas por una etiqueta **Tipo de documento empresarial**.

![Página de configuraciones de ER](./media/BDM-Overview-ERFormatTags.png)

La lista de plantillas disponibles en el espacio de trabajo de la gestión de documentos empresariales se puede limitar configurando permisos de acceso. Esto puede ser importante cuando distintas plantillas se usan para preparar documentos empresariales para distintos dominios de negocio (áreas funcionales), y desea permitir el acceso de usuarios específicos a plantillas diferentes para editar en el espacio de trabajo de la gestión de documentos empresariales.

Los permisos de administrador de documentos empresariales se pueden configurar en **Configurador de permisos de acceso**. Solo los usuarios siguientes pueden tener acceso a la página:

- Usuarios asignados al rol de **Administrador del sistema**.
- Usuarios asignados a cualquier otro rol que se haya configurado para ejercer el derecho, **Configurar los permisos para acceder a las plantillas de documentos empresariales para editar** (nombre de AOT **ERBDTemplatesSecurity**).

Use el procedimiento siguiente para configurar el acceso a los permisos de gestión de documentos empresariales para todas las entidades jurídicas.

1. Inicie sesión como usuario con acceso a la página **Configurador de permisos de acceso**.
2. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Gestión de documentos empresariales** \> **Administrar permisos de acceso**.

    Preste atención a la notificación que le indica que el uso de los permisos de acceso para la gestión de documentos empresariales no está habilitado actualmente.

    ![Configurador de la página de los permisos de gestión de documentos empresariales](./media/BDM-Overview-TemplatesAccess1.png)

    Con esta configuración, cada usuario asignado a cualquier rol de seguridad configurado para ejercer el derecho **Gestionar plantillas de documentos empresariales** (nombre AOT **ERBDManageTemplates**) podrá abrir el espacio de trabajo de gestión de documentos empresariales y editar cualquier plantilla que esté disponible.

    En el gráfico siguiente se muestra lo que está disponible en el espacio de trabajo de gestión de documentos empresariales para los usuarios asignados al rol **Funcionario de clientes** . Con el parámetro de permisos de acceso actual, el usuario puede editar plantillas de documentos empresariales de varias áreas funcionales incluidas la facturación, la generación de informes normativos y los pagos.

    ![Página del espacio de trabajo de la gestión de documentos empresariales](./media/BDM-Overview-TemplatesForAlice1.png)

3. En la página **Configurador de permisos de acceso**, seleccione **Configuración de permisos de acceso**.
4. En el cuadro de diálogo **Configuración de los permisos de acceso para editar plantillas**, habilite la opción **Aplicar permisos de acceso configurados**.
5. Seleccione **Aceptar** para confirmar que se han habilitado los permisos de gestión de documentos empresariales.

    ![Configuración de la página de los permisos de gestión de documentos empresariales](./media/BDM-Overview-TemplatesAccess2.png)

6. Seleccione **Agregar** para especificar un nuevo rol de negocio para el que es preciso que los permisos para acceder a las plantillas de la gestión de documentos empresariales estén configurados.
7. En el cuadro de diálogo **Roles de seguridad**, seleccione el rol **Funcionario de clientes** y después seleccione **Aceptar** para confirmar el rol de la selección.
8. En la pestaña **Permisos de acceso por etiquetas de configuraciones**, seleccione **Nuevo**.
9. En el campo **Tipo de etiqueta**, seleccione **Área funcional** y, en el campo **Identificador** , seleccione **Facturación**.
10. Seleccione **Guardar** para almacenar los permisos de acceso configurados para el rol seleccionado.

    La configuración actual significa que para cualquier usuario asignado al rol **Funcionario de clientes** y que ejecute el derecho, **Administrar plantillas de documentos empresariales** (nombre AOT **ERBDManageTemplates**), las plantillas de configuración del formato de ER con el valor **Facturación** para la etiqueta **Área funcional** estarán disponibles para su edición en el espacio de trabajo de gestión de documentos empresariales.

11. Cambiar el panel **Información relacionada** desde el lado derecho de la página actual. El panel **Información relacionada** muestra cómo los permisos de acceso configurados se aplicarán, incluido qué plantillas de configuración de ER estarán disponibles para los usuarios que están asignados al rol **Funcionario de clientes**.

    ![Configuración de la página de los permisos de gestión de documentos empresariales](./media/BDM-Overview-TemplatesAccess3.png)

12. En la pestaña **Permisos de acceso por configuraciones**, seleccione el botón **Agregar**.
13. En el cuadro de diálogo **Seleccionar configuración**, marque la configuración del formato de ER **Informe de intrastat**.
14. Seleccione **Aceptar** para confirmar la entrada de las configuraciones seleccionadas y después seleccione **Guardar** para almacenar los permisos de acceso configurados para el rol seleccionado.

La configuración actual significa que para cualquier usuario asignado al rol **Funcionario de clientes** y que ejecute el derecho, **Administrar plantillas de documentos empresariales** (nombre AOT **ERBDManageTemplates**), las siguientes plantillas estarán disponibles para su edición en el espacio de trabajo de gestión de documentos empresariales.

- Plantillas que tienen el valor **Facturación** para la etiqueta **Área funcional**.
- Plantillas de las configuraciones de formato de ER que se enumeran en la pestaña **Permisos de acceso por configuraciones** (plantillas de la configuración del formato **Informe de intrastat** del dominio **Informes estatutarios** en este ejemplo).

![Configuración de la página de los permisos de gestión de documentos empresariales](./media/BDM-Overview-TemplatesAccess4.png)

En el gráfico siguiente se muestra lo que el espacio de trabajo de gestión de documentos empresariales proporciona a los usuarios asignados al rol **Funcionario de clientes**. Con el valor de permisos de acceso actual de la gestión de documentos empresariales, el usuario puede editar plantillas de documentos empresariales del dominio **Facturación** y la configuración del formato de ER **Informe de intrastat** . Las plantillas del dominio **Pagos** no están accesibles para el rol **Funcionario de clientes** .

![Página del espacio de trabajo de la gestión de documentos empresariales](./media/BDM-Overview-TemplatesForAlice2.png)

> [!NOTE]
> Las reglas de **Permisos de acceso por configuraciones** se almacenan usando el identificador único de una configuración de formato de ER. Esto significa que estas reglas no se eliminarán cuando se elimine una configuración de ER que hace referencia a todas ellas. Al importar las configuraciones eliminadas de nuevo a esta instancia, estas reglas volverán a referirse a ellas. No es necesario configurar las reglas de nuevo tras volver a importar las configuraciones eliminadas.

## <a name="use-business-document-management-to-edit-templates"></a>Usar la gestión de documentos empresariales para editar plantillas

Los usuarios empresariales pueden tener acceso a las plantillas de documentos empresariales para editar en el espacio de trabajo de gestión de documentos empresariales. Solo los siguientes usuarios pueden tener acceso al espacio de trabajo de la gestión de documentos empresariales:

- Usuarios asignados al rol de **Administrador del sistema**.
- Usuarios que están asignados a cualquier rol configurado para ejercer el derecho, **Administrar plantillas de documentos empresariales** (nombre AOT **ERBDManageTemplates**).

Use el procedimiento siguiente para editar plantillas de facturas de servicios en el espacio de trabajo de gestión de documentos empresariales. Para completar este procedimiento, debe haber completado todos los procedimientos anteriores en este tema.

1. Inicie sesión como usuario con acceso al espacio de trabajo de administración de documentos empresariales.
2. Abra el espacio de trabajo de la gestión de documentos empresariales.

![Página del espacio de trabajo de la gestión de documentos empresariales](./media/BDM-Overview-EditingTemplate1.png)

La pestaña **Plantilla** muestra el contenido de la plantilla seleccionada. Seleccione la pestaña **Detalles** para revisar los detalles de la plantilla seleccionada así como los detalles de una configuración del formato de ER donde resida esta plantilla. Observe que todas las plantillas tienen un estado de **Publicada**, y no contienen detalles en la columna **Revisión**. Esto significa que estas plantillas no se están editando actualmente.

### <a name="initiate-editing-templates-owned-by-your-configuration-provider"></a>Comenzar a editar plantillas propiedad de su proveedor de configuración

1. En el espacio de trabajo de gestión de documentos empresariales, seleccione la plantilla **Formato de impresión de cheques** en la lista.
2. Seleccionar la pestaña **Detalles**.

![Página del espacio de trabajo de la gestión de documentos empresariales](./media/BDM-Overview-EditingTemplate2.png)

La opción **Editar plantilla** está disponible para la plantilla seleccionada. Esta opción está siempre disponible para una plantilla en una configuración de formato de ER propiedad del proveedor de la configuración de ER activa (**Litware, Inc.** en este ejemplo). Cuando se selecciona **Editar plantilla**, la plantilla existente de la versión de borrador de la configuración del formato de ER subyacente estará disponible para editar.

### <a name="initiate-editing-templates-owned-by-other-providers"></a>Comenzar a editar plantillas propiedad de otros proveedores

1. En el espacio de trabajo de Gestión de documentos empresariales, seleccione **Nuevo documento**.

![Página del espacio de trabajo de la gestión de documentos empresariales](./media/BDM_overview_new_template1.png)

2. Seleccione el documento que desea usar como una plantilla.

![Página del espacio de trabajo de la gestión de documentos empresariales](./media/BDM_overview_new_template2.png)

3. Haga clic en **Crear documento**
4. En el campo **Título**, cambie el título de la plantilla editable si es necesario. El texto se usará para asignar un nombre a configuración del formato de ER que se crea automáticamente. Tenga en cuenta que la versión del borrador de esta configuración (**Copia de informe FTI de cliente (GER)**) que incluirá la plantilla editada se marcará automáticamente para ejecutar este formato de ER para el usuario actual. Al mismo tiempo, la plantilla original no modificada de la configuración del formato básico de ER se usará para ejecutar este formato de ER para cualquier otro usuario.
5. En el campo **Nombre**, cambie el nombre de la primera revisión de la plantilla editable que se creará automáticamente.
6. En el campo **Comentario**, cambie los comentarios para la revisión creada automáticamente de la plantilla editable.
7. Seleccione **Aceptar** para confirmar el inicio del proceso de edición

![Página del espacio de trabajo de la gestión de documentos empresariales](./media/BDM_overview_new_template3.png)

La opción **Nuevo documento** está siempre disponible para una plantilla en una configuración de formato de ER que proporciona otro proveedor (Microsoft en este ejemplo). Cuando haga clic en **Nuevo documento** verá todas las plantillas que poseen los proveedores actuales y otros proveedores. Después de elegir la plantilla, se abrirá para editarla. La plantilla editada se almacenará en una nueva configuración del formato de ER que se genera automáticamente.

### <a name="start-editing-a-template"></a>Comenzar a editar plantillas

1. En la plantilla seleccionada, seleccione **Editar documento**.
2. En el campo **Nombre**, cambie el nombre de la primera revisión de la plantilla editable que se creará automáticamente.
3. En el campo **Comentario**, cambie los comentarios para la revisión creada automáticamente de la plantilla editable.

    ![Página del espacio de trabajo de la gestión de documentos empresariales](./media/BDM_overview_new_template4.png)

5. Seleccione **Aceptar** para confirmar el inicio del proceso de edición.

La página **Editor de plantillas de BDM** se abrirá. La plantilla seleccionada estará disponible para la edición en línea de Office 365.

![Página del espacio de trabajo de la gestión de documentos empresariales](./media/BDM-Overview-EditingLayout1.png)

### <a name="edit-a-template-in-office-365"></a>Editar una plantilla en Office 365

Modifique la plantilla con la funcionalidad de Office 365. Por ejemplo, en Office Online, cambie la fuente de los mensajes de campo en el encabezado de **Normal** a **Negrita**. Estos cambios se almacenan automáticamente para la plantilla editable almacenada en el almacenamiento principal de la plantilla (de forma predeterminada, el almacenamiento blob de Azure) que está configurado para el marco de ER.

![Página del editor de plantillas de la gestión de documentos empresariales](./media/BDM-Overview-EditingLayout2.png)

### <a name="edit-a-template-in-the-office-desktop-application"></a>Editar una plantilla en la aplicación de escritorio de Office

1. Seleccione la opción **Abrir en aplicación de escritorio** para modificar la plantilla con la funcionalidad de la aplicación de escritorio de Office (Excel en este ejemplo). La plantilla editable se copia de almacenamiento permanente el almacenamiento temporal configurado en los parámetros de la gestión de documentos empresariales como una carpeta de SharePoint.
2. Confirme que desea abrir la plantilla desde el almacenamiento de archivos temporal en la aplicación Excel de escritorio de Office.

    ![Página del espacio de trabajo de la gestión de documentos empresariales](./media/BDM-Overview-EditingLayout3.png)

3. Modifique la plantilla. Por ejemplo, cambie la fuente de los mensajes de campo en el encabezado de la plantilla actualizando el color de **Negro** a **Azul**.

    ![Página del editor de plantillas de la gestión de documentos empresariales](./media/BDM-Overview-EditingLayout4.png)

4. Seleccione **Guardar** en la aplicación de escritorio de Excel para almacenar los cambios de la plantilla en el almacenamiento temporal.

    ![Página del editor de plantillas de la gestión de documentos empresariales](./media/BDM-Overview-EditingLayout5.png)

5. Cierre la aplicación de escritorio de Excel.
6. Seleccione **Sincronizar copia almacenada** para sincronizar el almacenamiento temporal de la plantilla al almacenamiento permanente de la plantilla.

> [!NOTE]
> La copia de la plantilla editable en el archivo de almacenamiento temporal se conserva solo para la sesión actual de edición de plantillas. Cuando termine esta sesión cerrando la página **Editor de plantillas de BDM**, esta copia se eliminará. Si ajustó la plantilla en el archivo de almacenamiento temporal y no seleccionó **Sincronizar copia almacenada**, cuando intente cerrar la página **Editor de plantillas de BDM**, un mensaje preguntará si desea almacenar los cambios realizados. Seleccione **Sí** si desea guardar los cambios en la plantilla en la ubicación de archivo permanente.

### <a name="validate-a-template"></a>Validar una plantilla

1. En la página **Editor de plantillas de BDM**, seleccione **Buscar problemas** para validar la plantilla modificada frente a la configuración subyacente de formato de ER. Siga las recomendaciones (en su caso) de alinear la plantilla con la estructura del formato de la configuración básica de formato de ER.
2. Seleccione **Mostrar formato** para ver la estructura actual del formato de la configuración básica de formato de ER que se debe alinear con la plantilla editable. 
3. Seleccione **Ocultar formato** para cerrar el panel.

    ![Página del editor de plantillas de BDM](./media/BDM-Overview-EditingTemplate6.png)

4. Cierre la página **Editor de plantillas de BDM**.

La plantilla actualizada se muestra en la pestaña **Plantilla**. Tenga en cuenta que el estado de la plantilla editada ahora es **Borrador** y la revisión actual ya no estará vacía. Esto significa que el proceso de edición de esta plantilla se ha iniciado.

![Página del espacio de trabajo de la gestión de documentos empresariales](./media/BDM-Overview-EditingTemplate5.png)

### <a name="test-the-modified-template"></a>Probar la plantilla modificada 

1. En la aplicación, cambie a la empresa, **USMF**.
2. Vaya a **Clientes** \> **Facturas** \> **Todas las facturas de servicios**.
3. Seleccione la factura **FTI-00000002** y, a continuación, seleccione **Gestión de impresión**.
4. Seleccione el nivel **Módulo - Clientes** \> **Documentos** \> **Factura de servicios** \> **Documento original** para especificar el ámbito de las facturas para procesar.
5. En el campo **Formato del informe**, seleccione el formato de ER **Copia de informe FTI de cliente (GER)** para el nivel especificado del documento.

    ![Página de configuración de la administración de impresión](./media/BDM-Overview-TestRun1.png)

6. Presione **Esc** para cerrar la página actual.
7. Seleccione **Imprimir** y, después, haga clic en **Seleccionado**.
8. Descargue el documento y ábralo mediante la aplicación de escritorio de Excel.

![Página de facturas de servicios](./media/BDM-Overview-TestRun2.png)

La plantilla modificada se usa para generar el informe de facturas de servicios para el artículo seleccionado. Para analizar cómo este informe se ve afectado por los cambios que haya especificado en la plantilla, puede ejecutar este informe en una sesión de la aplicación tras modificar la plantilla en otra sesión de la aplicación.

### <a name="create-an-alternative-template-revision"></a>Crear una revisión alternativa de la plantilla

1. Abre la página **Editor de plantillas de BDM** y seleccione la plantilla **Copia de informe FTI de cliente (GER)**.
2. En la pestaña **Revisiones**, seleccione **Nuevo**.
3. Si es necesario, en el campo **Nombre**, cambie el nombre de la segunda revisión y básese en la primera revisión activa actualmente.
4. Si es necesario, en el campo **Comentario**, cambie los comentarios para la revisión creada automáticamente de la plantilla editable.

    ![Página del espacio de trabajo de la gestión de documentos empresariales](./media/BDM-Overview-AddRevision.png)

    Ha creado una nueva revisión de la plantilla que se había almacenado en el almacenamiento de la plantilla permanente. Ahora puede seguir editando la plantilla de la segunda revisión que está actualmente seleccionada como activa.

5. Seleccione la primera revisión y, después, seleccionan **Definir como activo**. Puede seleccionar otra revisión como un activa en cualquier momento para volver a esa revisión de la plantilla.
6. Seleccione la segunda revisión y, a continuación, seleccione **Eliminar**.
7. Seleccione **Aceptar** para confirmar que desea eliminar la revisión seleccionada. Puede eliminar las revisiones inactivas cuando no se necesiten.

### <a name="delete-a-modified-template"></a>Eliminar una plantilla modificada

1. En la página **Editor de plantillas de BDM**, seleccione la pestaña **Plantilla**.
2. Seleccione **Eliminar**.
3. Si se selecciona **Aceptar** para confirmar la eliminación, el formato de ER **Copia de informe FTI de cliente (GER)** con la plantilla modificada se eliminará. Seleccione **Cancelar** para explorar otras opciones.

### <a name="revoke-changes-of-template"></a>Revocar los cambios de la plantilla

Al editar la plantilla desde un formato de ER propiedad del proveedor activo actual, se le ofrecerá la opción de revocar los cambios aplicados en la plantilla.

![Página del espacio de trabajo de la gestión de documentos empresariales](./media/BDM-Overview-RevokeChanges.png)

1. En la página **Editor de plantillas de BDM**, seleccione la pestaña **Plantilla**.
2. Seleccione **Deshacer**.
3. Si se selecciona **Aceptar** para revocar los cambios aplicados en la plantilla, la plantilla modificada se reemplazará por la plantilla original y todos los cambios se eliminarán. Si revoca los cambios en la plantilla, podrá eliminar la plantilla. Seleccione **Cancelar** para explorar otras opciones.

### <a name="publish-a-modified-template"></a>Publicar una plantilla modificada
1. En la página **Editor de plantillas de BDM**, en la pestaña **Plantilla**, seleccione **Publicar**.
2. Si se selecciona **Aceptar** para confirmar la publicación, la versión del borrador del formato derivado de ER **Copia de informe FTI de cliente (GER)** que contenga la plantilla modificada se marcará como completado. La plantilla modificada pasará a estar disponible para otros usuarios. Las versiones completadas de este formato de ER conservarán solo la última revisión activa de la plantilla. Se eliminarán otras revisiones. Seleccione **Cancelar** para explorar otras opciones.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

#### <a name="i-selected-edit-document-but-instead-of-opening-the-bdm-template-editor-page-in-finance-and-operations-i-have-been-sent-to-the-office-365-web-page"></a>Seleccioné **Editar documento**, pero en lugar de abrir la página **Editor de plantillas de BDM** en Finance and Operations, me han enviado a la página web de Office 365.
Esto se un problema conocido de la redirección de Office 365. Esto ocurre al iniciar sesión en Office 365 la primera vez. Para solucionar este error, seleccione el botón **Atrás** del explorador para regresar.

#### <a name="i-understand-how-to-edit-a-template-by-using-office-365-in-the-first-application-session-and-how-to-use-the-template-in-the-second-application-session-adjusting-the-template-to-see-how-my-changes-affect-the-generated-business-document-can-i-do-this-using-the-office-desktop-application"></a>Entiendo cómo editar una plantilla con Office 365 en la primera sesión de la aplicación y cómo usar la plantilla en la segunda sesión de la aplicación ajustándola para ver cómo mis cambios afectan al documento empresarial generado. ¿Puedo hacer esto mediante la aplicación de escritorio de Office?
Sí, puede. En la primera sesión de la aplicación, seleccione **Abrir en aplicación de escritorio**. Su plantilla se almacenará en el archivo de almacenamiento temporal y se abrirá en la aplicación de escritorio de Office. A continuación, realice los pasos siguientes para obtener una vista previa de los cambios en la plantilla en el documento empresarial generado:

1. Realice cambios en la plantilla con la aplicación de escritorio de Office.
2. Seleccione **Guardar** en la aplicación de escritorio de Office.
3. En la página **Editor de plantillas de BDM** de la primera sesión de la aplicación, seleccione **Sincronizar copia almacenada**.
4. Ejecute este formato de ER en la segunda sesión de la aplicación.

#### <a name="i-get-the-error-value-cannot-be-null-parameter-name-externalid-when-i-select-open-in-desktop-app-how-do-i-work-around-this"></a>Me devuelve el error "El valor no puede ser nulo. Nombre de parámetro: externalId" cuando selecciono **Abrir en aplicación de escritorio**. ¿Cómo solucione este problema? 
Probablemente inició sesión en la instancia actual de la aplicación del dominio Azure AD que es distinta del dominio Azure AD que se usó para implementar esta instancia. Dado que el servicio de SharePoint, que se utiliza para almacenar las plantillas para que estén disponibles para su edición mediante las aplicaciones de escritorio de Office, pertenece al mismo dominio, no tenemos permisos para tener acceso al servicio de SharePoint. Para resolver este problema, inicie sesión en la instancia actual mediante las credenciales de un usuario con el dominio correcto de Azure AD.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de los informes electrónicos (ER)](general-electronic-reporting.md)

[ER Diseña una configuración para generar informes en formato OPENXML (noviembre de 2016)](tasks/er-design-reports-openxml-2016-11.md)

[Diseñar configuraciones de ER para generar informes en formato Word](tasks/er-design-configuration-word-2016-11.md)

[Insertar imágenes y formas en los documentos generados con ER](electronic-reporting-embed-images-shapes.md)

[Configurar informes electrónicos (ER) para proporcionar datos a Power BI](general-electronic-reporting-report-configuration-get-data-powerbi.md)
