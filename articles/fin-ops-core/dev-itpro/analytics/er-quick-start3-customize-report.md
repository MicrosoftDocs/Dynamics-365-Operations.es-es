---
title: Personalizar las configuraciones de informes electrónicos para generar un documento electrónico
description: En este artículo se explica cómo personalizar las configuraciones de informe electrónico (ER) proporcionadas por Microsoft para generar un documento electrónico personalizado.
author: kfend
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.custom: 220314,  ""intro-internal
ms.assetid: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
ms.openlocfilehash: cd3200bea07d622632dc5781638ec825c21233e4
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278958"
---
# <a name="customize-electronic-reporting-configurations-to-generate-an-electronic-document"></a>Personalizar las configuraciones de informes electrónicos para generar un documento electrónico

[!include[banner](../includes/banner.md)]

El [Marco de informes electrónicos (ER)](general-electronic-reporting.md) permite cargar las [configuraciones](general-electronic-reporting.md#Configuration) de informaciones electrónicos que Microsoft le proporciona a su instancia de Microsoft Microsoft Dynamics 365 Finance. De esta manera, las configuraciones proporcionadas por Microsoft pueden servir como la solución de informes electrónicos que se utiliza para generar facturas electrónicas de los clientes. Puede utilizar esta solución de ER para configurar su solución de ER personalizada, a fin de acceder a sus campos de base de datos personalizados y generar facturas electrónicas que cumplan sus requisitos específicos, sin tener que editar el código fuente.

## <a name="overview"></a>Información general

Para el ejemplo de este artículo, debe especificar un código de identificación fiscal federal como un nuevo atributo personalizado de cada cliente al que envíe facturas electrónicas. Por lo tanto, debe personalizar la estructura de la factura que se utiliza actualmente, agregando un nuevo artículo que se debe completar con el código de impuestos en cada factura electrónica que se genere.

Los procedimientos de este artículo explican cómo un usuario con el rol de administrador del sistema, desarrollador de informes electrónicos o consultor funcional de informes electrónicos puede realizar las tareas siguientes en su instancia de Finance:

- [Configurar el conjunto mínimo de parámetros de ER necesarios para empezar a utilizar el marco de ER](#ConfigureER).
- [Importar las versiones iniciales de las configuraciones estándar de ER que se proporcionan para generar facturas electrónicas](#ImportERConfigurations1).
- [Configurar los parámetros de Clientes para empezar a usar las configuraciones estándar de ER](#ConfigureAR1).
- [Configurar los parámetros de entidad jurídica para facturar a los clientes](#ConfigureLE).
- [Elaborar un registro de cliente para facturación electrónica](#ConfigureCustomer1).
- [Agregar, publicar y enviar una factura de cliente mediante las configuraciones estándar de ER](#ProcessInvoice1).
- [Agregar un campo de base de datos personalizado para administrar un código de identificación fiscal federal para los clientes](#AddCustomField).
- [Actualizar los metadatos de ER con el fin de permitir cambios en la base de datos para el diseñador de asignación de modelo de ER](#RefreshERMetadata).
- [Diseñar las configuraciones personalizadas de ER para generar facturas electrónicas que contengan el nuevo código de impuestos](#DesignCustomERConfigurations).
- [Configurar los parámetros de Clientes para empezar a usar las configuraciones personalizadas de ER](#ConfigureAR2).
- [Actualizar un registro de cliente para facturación electrónica](#ConfigureCustomer2).
- [Agregar, publicar y enviar una factura de cliente con las configuraciones personalizadas de ER](#ProcessInvoice2).
- [Importar las nuevas versiones de las configuraciones estándar de ER que se proporcionan para generar facturas electrónicas](#ImportERConfigurations2).
- [Adoptar los cambios de las nuevas versiones de las configuraciones estándar de ER en sus configuraciones personalizadas de ER](#RebaseCustomERConfigurations).
- [Agregar, publicar y enviar una factura de cliente con las nuevas versiones de las configuraciones personalizadas de ER](#ProcessInvoice3).

Todos estos procedimientos se pueden llevar a cabo en la empresa **DEMF**.

## <a name="configure-the-er-framework"></a><a name="ConfigureER"></a>Configurar el marco ER

Como usuario con el rol de Consultor funcional de informes electrónicos o Desarrollador de informes electrónicos, debe configurar el conjunto mínimo de parámetros de ER. Después puede empezar a utilizar el marco de ER para diseñar versiones personalizadas de las configuraciones estándar de la solución de ER que se utiliza para generar facturas electrónicas.

### <a name="configure-er-parameters"></a>Configurar los parámetros de ER

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Blueprint de localización**, en la sección **Vínculos relacionados**, seleccione **Parámetros de informes electrónicos**.
3. En la página **Parámetros de informes electrónicos**, en la pestaña **General**, establezca la opción **Habilitar modo de diseño** en **Sí**.
4. En la pestaña **Archivos adjuntos**, en el campo **Configuraciones**, seleccione **Archivo**.
5. En los campos **Archivo de trabajo**, **Temporal**, **Base** y **Otros**, seleccione el tipo **Archivo**.

Para obtener más información sobre cómo configurar los parámetros de ER, consulte [Configurar el marco de ER](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a>Activar un proveedor de configuración de ER

Cada configuración de ER que se agrega está marcada como propiedad de un proveedor de configuración de ER. El proveedor de configuración de ER que se activa en el espacio de trabajo **Informes electrónicos** se utiliza para este propósito. Por lo tanto, debe activar un proveedor de configuración de ER en el espacio de trabajo **Informes electrónicos** antes de comenzar a agregar o editar configuraciones de ER.

> [!NOTE]
> Solo el propietario de una configuración de ER puede editarla. Por lo tanto, antes de poder editar una configuración de ER, se debe activar el proveedor de configuración ER apropiado en el espacio de trabajo **Informes electrónicos**.

#### <a name="review-the-list-of-er-configuration-providers"></a>Revise la lista de proveedores de configuración de ER

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Blueprint de localización**, en la sección **Vínculos relacionados**, seleccione **Proveedores de configuración**.
3. En la página **Tabla de proveedor de configuración**, cada registro de proveedor tiene un nombre y URL únicos. Revise el contenido de esta página. Si un registro para **Litware, Inc.** (`https://www.litware.com`) ya existe, omita el siguiente procedimiento, [Agregar un nuevo proveedor de configuración de ER](#AddProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a id="AddProvider"></a>Añada una nueva configuración para el proveedor de ER

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Blueprint de localización**, en la sección **Vínculos relacionados**, seleccione **Proveedores de configuración**.
3. En la página **Proveedores de configuración**, seleccione **Nuevo**.
4. En el campo **Nombre**, introduzca **Litware, Inc.**
5. En el campo **Dirección de Internet**, introduzca `https://www.litware.com`.
6. Seleccione **Guardar**.

#### <a name="activate-an-er-configuration-provider"></a>Activar un proveedor de configuración de ER

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Blueprint de localización**, en la sección **Proveedores de configuración**, seleccione el mosaico **Litware, Inc.** y luego seleccione **Establecer activo**.

Para obtener más información sobre proveedores de configuración de ER, consulte [Crear proveedores de la configuración y marcarlos como activos](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-the-initial-versions-of-standard-er-configurations"></a><a name="ImportERConfigurations1"></a>Importar las versiones iniciales de las configuraciones estándar de ER

Para agregar las configuraciones estándar de ER a su instancia actual de Finance, debe importarlas desde el [repositorio](general-electronic-reporting.md#Repository) de ER que se configuró para esa instancia.

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Blueprint de localización**, en la sección **Proveedores de configuración**, seleccione el mosaico **Microsoft** y luego seleccione **Repositorios** para ver la lista de repositorios para el proveedor de Microsoft.
3. En la página **Configuración de repositorios**, seleccione el repositorio existente del tipo **Global** y después seleccione **Abrir**. Si se le solicita autorización para conectarse al Regulatory Configuration Service, siga las instrucciones de autorización.
4. En la página **Repositorio de configuración**, en el árbol de configuración del panel izquierdo, seleccione el formato de configuración **Factura de ventas Peppol**.
5. En la ficha desplegable **Versiones**, seleccione la versión **11.2.2**.
6. Seleccione **Importar** para descargar la versión seleccionada desde el repositorio Global.

![Página de configuración del repositorio.](./media/er-quick-start3-import-solution1.png)

> [!TIP]
> Si tiene problemas para acceder al [Repositorio global](er-download-configurations-global-repo.md), puede [descargar configuraciones](download-electronic-reporting-configuration-lcs.md) de Microsoft Dynamics Lifecycle Services (LCS) en su lugar.

### <a name="review-the-imported-er-configurations"></a>Revisar las configuraciones importadas de ER

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Blueprint de localización**, en la sección **Configuraciones**, seleccione el icono **Configuraciones de informes**.
3. En la página **Configuraciones**, expanda la ficha desplegable **Componentes de configuración**.
4. En el árbol de configuración del panel izquierdo, expanda **Modelo de factura** y, a continuación, expanda **Factura de ventas UBL**.

Tenga en cuenta que, además del formato de ER **Factura de ventas Peppol** seleccionado, se importaron otras configuraciones de ER necesarias. Como se publican constantemente nuevas versiones de las configuraciones de ER en el repositorio Global y LCS para mantener la compatibilidad de las soluciones correspondientes compatibles con los nuevos requisitos, se han importado las versiones más recientes de la configuración de modelo de datos requerida y su asignación de modelo.

![Página Configuraciones.](./media/er-quick-start3-imported-solution1a.png)

Para simular el estado en el que se encontrarían las configuraciones de ER en la instancia de Finance actual si importara la versión **11.2.2** del formato de ER **Factura de ventas Peppol** en el pasado (por ejemplo, el 7 de agosto de 2019), siga estos pasos.

- En el panel de acciones, seleccione **Eliminar** para eliminar todas las configuraciones de ER que se publicaron después del 7 de agosto de 2019. Deben dejarse las únicas configuraciones de **Modelo de factura**, **Asignación de modelo de factura** (inicialmente denominada **Asignación de modelo de factura del cliente**), **Factura de ventas UBL** y **Factura de ventas Peppol**.
- Para las configuraciones de ER restantes, en la ficha desplegable **Versiones**, seleccione **Eliminar** para eliminar todas las versiones de las configuraciones de ER que se publicaron después del 7 de agosto de 2019.

A continuación, compruebe que las siguientes configuraciones de ER están disponibles en el árbol de configuración:

- Configuración del modelo de datos de ER **Modelo de factura** (inicialmente llamado **Modelo de factura de cliente**):

    - La versión 11 contiene la versión 10 del componente de ER modelo de datos que representa la estructura de datos del dominio empresarial de facturación. Esta configuración de ER se ha importado como antepasado del formato de ER **Factura de ventas Peppol** que se seleccionó para importar.
    - La versión 50 contiene la versión 31 del componente de ER de modelo de datos. Esta configuración de ER se ha importado como un antepasado de la versión del 7 de agosto de 2019 de la configuración de asignación de modelo de ER **Asignación de modelo de factura**.

    ![Configuración del modelo de datos de ER del modelo de factura en la página Configuraciones.](./media/er-quick-start3-imported-solution1b1.png)

    > [!TIP]
    > Si no ve la versión 50 de este modelo de datos, abra el repositorio Global e importe la versión 50.19 de la configuración de ER **Asignación de modelo de factura**.

- Configuración de la asignación del modelo de ER **Asignación de modelo de factura** (inicialmente llamado **Asignación de modelo de factura de cliente**):

    - La versión 50.19 se ha importado como la implementación más reciente de la versión 50 de la configuración de modelo de datos de ER **Modelo de factura**. Contiene dos componentes de ER de asignación de modelo que describen cómo se rellena el modelo de datos con los datos de la aplicación en tiempo de ejecución.

    ![Configuración de la asignación del modelo de datos de ER para la asignación del modelo de factura en la página Configuraciones.](./media/er-quick-start3-imported-solution1b2.png)

    > [!TIP]
    > Si no ve la versión 50.19 de esta asignación de modelo, abra el repositorio Global e importe la versión 50.19 de la configuración de ER **Asignación de modelo de factura**.

- Configuración de formato de ER **Factura de ventas UBL**:

    - La versión 11.2 contiene los componentes de ER de formato y asignación de formato. El componente de formato especifica el diseño del informe. El componente de asignación de formato contiene el origen de datos del modelo y especifica cómo se usa este origen de datos para rellenar el diseño del informe en tiempo de ejecución. Este formato de ER se configuró para generar facturas electrónicas con formato Universal Business Language (UBL). Se ha importado como antepasado del formato de ER **Factura de ventas Peppol** que se seleccionó para importar.

- Configuración de formato de ER **Factura de ventas Peppol**:

    - La versión 11.2.2 contiene los componentes de ER de formato y asignación de formato que se configuraron para generar facturas electrónicas con formato Pan-European Public Procurement OnLine (PEPPOL).

    ![Configuración de formato de ER de factura de ventas Peppol en la página Configuraciones.](./media/er-quick-start3-imported-solution1b3.png)

## <a name="configure-the-accounts-receivable-parameters"></a><a name="ConfigureAR1"></a>Configurar los parámetros de clientes

1. Vaya a **Clientes** \> **Configuración** \> **Parámetros de clientes**.
2. En la pestaña **Documentos electrónicos**, en la ficha desplegable **Informes electrónicos**, en el campo **Factura de servicios y ventas**, seleccione **Factura de ventas Peppol**.
3. Seleccione **Guardar**.

![Pestaña Documentos electrónicos en la página Parámetros de clientes.](./media/er-quick-start3-configure-ar1.png)

## <a name="configure-the-legal-entity-parameters"></a><a name="ConfigureLE"></a>Configurar los parámetros de entidad jurídica

1. Vaya a **Administración de la organización** \> **Organizaciones** \> **Entidades jurídicas**.
2. Para la empresa **DEMF** seleccionada, en la ficha desplegable **Información de cuenta bancaria**, en el campo **Número de ruta**, escriba **1234**.
3. Seleccione **Guardar**.
4. Cierre la página **Entidades jurídicas**.

## <a name="prepare-a-customer-record"></a><a name="ConfigureCustomer1"></a>Preparar un registro de cliente

1. Vaya a **Clientes** \> **Clientes** \> **Todos los clientes**.
2. En la página **Todos los clientes**, seleccione el vínculo de cuente de cliente **DE-014**.

### <a name="add-a-customer-contact"></a>Agregar un contacto de cliente

1. Vaya a **Clientes** \> **Clientes** \> **Todos los clientes**.
2. En el panel de acciones, en la pestaña **Cliente** del grupo **Cuentas**, seleccione **Contactos**.
3. Seleccione **Agregar contactos**.
4. En la página **Contactos**, en el campo **Nombre**, abra la búsqueda, seleccione **Adam Carter** y, a continuación, seleccione **Seleccionar** para cerrar la búsqueda.
5. Seleccione **Guardar**.
6. Cierre la página **Contactos**.

### <a name="define-a-primary-contact"></a>Definir un contacto principal

1. Vaya a **Clientes** \> **Clientes** \> **Todos los clientes**.
2. En la ficha desplegable **Datos demográficos de ventas**, en el campo **Contacto principal**, seleccione **Adam Carter**.

### <a name="set-the-e-invoicing-option"></a>Configurar la opción de facturación electrónica

1. Vaya a **Clientes** \> **Clientes** \> **Todos los clientes**.
2. En la ficha desplegable **Factura y entrega**, establezca la opción **Factura electrónica** en **Sí**.
3. Seleccione **Guardar**.
4. Cierre la página **Todos los clientes**.

## <a name="process-a-customer-invoice-by-using-the-standard-er-configurations"></a><a name="ProcessInvoice1"></a>Procesar una factura de cliente mediante las configuraciones estándar de ER

Ahora puede usar las configuraciones estándar de ER que importó para enviar por vía electrónica una factura de servicios a un cliente.

### <a name="add-a-new-invoice"></a>Agregar una factura nueva

1. Vaya a **Clientes** \> **Facturas** \> **Todas las facturas de servicios**.
2. En la página **Factura de servicios**, seleccione **Nuevo**.
3. En la ficha desplegable **Encabezado de factura de servicios**, en el campo **Cuenta de cliente**, seleccione **DE-014**.
4. En la ficha desplegable **Líneas de factura** se agrega automáticamente una línea de factura. En esta línea, establezca los valores de los campos siguientes:

    - En el campo **Descripción**, escriba **Cuaderno de notas**.
    - En el campo **Cuenta principal**, seleccione **401100**.
    - En el campo **Precio unitario**, escriba **1000**.

5. Seleccione **Guardar**.

![Página de facturas de servicios.](./media/er-quick-start3-add-invoice.png)

Para obtener más información, consulte [Crear una factura de servicios](../../../finance/accounts-receivable/create-free-text-invoice-new.md).

### <a name="post-a-new-invoice"></a>Registrar una factura nueva

1. Vaya a **Clientes** \> **Facturas** \> **Todas las facturas de servicios**.
2. En la página **Factura de servicios**, en el panel de acciones, seleccione **Registrar**.
3. En el cuadro de diálogo **Registrar factura de servicios**, seleccione **Aceptar**.

![Página de detalles de factura de servicios.](./media/er-quick-start3-post-invoice.png)

### <a name="send-a-posted-invoice"></a>Enviar una factura registrada

1. Vaya a **Clientes** \> **Facturas** \> **Todas las facturas de servicios**.
2. En la página **Factura de servicios**, en el panel de acciones, en el grupo **Documento**, seleccione **Enviar** \> **Original**.

    ![Vista previa de la factura original.](./media/er-quick-start3-send-invoice.png)

3. Cierre la página **Factura de servicios**.

### <a name="analyze-a-generated-e-invoice"></a>Analizar una factura electrónica generada

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Trabajos de informes electrónicos**.
2. En la página **Trabajos de informes electrónicos**, seleccione el registro inicial que tiene la descripción de tarea **Enviar XML de factura electrónica**.
3. Seleccione **Mostrar archivos** para acceder a la lista de archivos generados.

    ![Página de trabajos de informes electrónicos.](./media/er-quick-start3-jobs-list.png)

4. Seleccione **Abrir** para descargar el archivo XML de factura electrónica que se genera.
5. Analice el archivo XML de factura electrónica. Observe que el esquema de impuestos del cliente está representado actualmente por los atributos XML **schemeID** y **schemeAgencyID**. Observe también que el elemento XML **cbc:CustomizationID** contiene actualmente el siguiente texto: `urn:www.cenbii.eu:transaction:biicoretrdm010:ver1.0:# urn:www.peppol.eu:bis:peppol5a:ver1.0`.

    ![Vista previa del archivo XML de factura electrónica generado.](./media/er-quick-start3-e-invoice1.png)

## <a name="add-a-custom-database-field"></a><a name="AddCustomField"></a>Agregar un campo de base de datos personalizado

Puede usar la característica [Campo personalizado](../../fin-ops/get-started/user-defined-fields.md) para realizar la siguiente personalización en la instancia de Finance actual:

- Personalice la estructura de la base de datos agregando un nuevo campo de base de datos personalizado que almacene un código de identificación fiscal federal para cada cliente.
- Personalice la página **Cliente** agregando un nuevo campo de entrada de datos que se pueda usar para especificar un valor de código de impuestos en el nuevo campo de base de datos personalizado.

Siga estos pasos para realizar la personalización.

1. Vaya a **Clientes** \> **Clientes** \> **Todos los clientes**.
2. En la página **Todos los clientes**, seleccione el vínculo de cuente de cliente **DE-014**.
3. En la ficha desplegable **General**, haga clic con el botón derecho en cualquier área en blanco bajo el campo **Idioma** y, a continuación, seleccione **Personalizar: GrupoSuperior**.

    El contenido de la ficha desplegable **General** se muestra resaltado y aparece un menú **Personalizar**.

4. En el menú **Personalizar**, seleccione **Agregar un campo**.
5. En el cuadro de diálogo **Agregar columnas**, seleccione **Crear nuevo campo**.
6. En el cuadro de diálogo **Crear nuevo campo**, en el campo **Nombre de la tabla**, seleccione **Clientes**.
7. En el campo **Prefijo del nombre**, escriba **FederalTaxID**.

    > [!NOTE]
    > El nombre completo del campo se define automáticamente como **FederalTaxID\_Personalizado**.

8. En el campo **Etiqueta**, escriba **Id. fiscal federal**.
9. En el campo **Tipo**, seleccione **Texto**.
10. En el campo **Longitud**, escriba **20**.
11. Seleccione **Guardar**.
12. En el cuadro de mensaje que aparece, seleccione **Sí** para confirmar que desea crear una nueva entrada de campo **FederalTaxID** para la tabla **Clientes**.
13. Seleccione **Insertar** para <a name="insert_custom_field"></a>agregar el campo **FederalTaxID\_Personalizado** a la página actual.

    ![Página Todos los clientes.](./media/er-quick-start3-create-new-field.gif)

14. Cierre la página **Todos los clientes**.

## <a name="refresh-the-er-metadata"></a><a name="RefreshERMetadata"></a>Actualizar los metadatos de ER

Debe actualizar los metadatos de ER para que el campo personalizado que agregó sea [visible](electronic-reporting-er-configure-parameters.md#frequently-asked-questions) en el diseñador de asignaciones de modelos.

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Regenerar referencias de tabla**.
2. En el cuadro de diálogo **Actualizar modelo de datos**, seleccione **Aceptar**.

## <a name="design-the-custom-er-configurations"></a><a name="DesignCustomERConfigurations"></a>Diseñar las configuraciones personalizadas de ER

Puede utilizar las configuraciones de ER proporcionadas por Microsoft para diseñar sus configuraciones de ER personalizadas de forma que generen facturas electrónicas que contengan el nuevo código de impuestos.

### <a name="customize-the-data-model-configuration"></a>Personalizar la configuración del modelo de datos

Como usuario con el rol de Consultor funcional de informes electrónicos puede diseñar su modelo de datos de ER personalizado.

#### <a name="add-a-custom-data-model-configuration"></a>Agregar una configuración de modelo de datos personalizada

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, seleccione **Modelo de factura de cliente**.
3. En el panel de acciones, seleccione **Crear configuración**.
4. En el cuadro de diálogo desplegable, en el campo **Nuevo**, seleccione **Derivar de nombre: modelo de factura de cliente, Microsoft** para indicar que su nueva configuración personalizada de modelo de datos de ER debe basarse en la configuración de modelo de datos de ER.
5. En el campo **Nombre**, escriba **Modelo de factura (Litware)**.
6. Seleccione **Crear configuración** para agregar la nueva configuración de ER.

Ahora puede utilizar el diseñador de modelos de datos de ER para editar la versión 50.1 de la configuración de ER **Modelo de factura (Litware)** con el estado **Borrador**.

![Versión 50.1 de la configuración de ER editable en la página Configuraciones.](./media/er-quick-start3-added-custom-model.png)

#### <a name="configure-a-custom-data-model"></a>Configurar un modelo de datos personalizado

Debe modificar su modelo de datos personalizado agregando un campo nuevo para proporcionar el valor de un código de identificación fiscal federal. Este código forma parte de los datos del cliente para cada formato de ER que usará este modelo de datos como origen de datos.

1. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, seleccione **Modelo de factura (Litware)**.
2. En la ficha desplegable **Versiones**, seleccione la versión **50.1** de la configuración de modelo de datos de ER con estado **Borrador** seleccionada.
3. En el panel de acciones, seleccione **Diseñador** para la versión de configuración seleccionada.
4. En la página **Diseñador de modelos de datos**, en el árbol del modelo de datos, seleccione **Información del cliente (cliente)**.
5. Seleccione **Nuevo**.
6. En el cuadro de diálogo desplegable, en el campo **Nuevo nodo como**, acepta el valor predeterminado, **Secundario de un nodo activo**.
7. En el campo **Nombre**, escriba **FederalTaxID\_Litware**.
8. En el campo **Tipo de artículo**, acepte el valor predeterminado, **Cadena**.
9. Seleccione **Agregar** y, a continuación, seleccione **Guardar**.

    ![Página de diseñador del modelo de datos.](./media/er-quick-start3-add-data-model-field.png)

    > [!NOTE]
    > Los campos **Etiqueta** y **Descripción** describen el propósito del nuevo campo. Puede rellenar estos campos en varios idiomas. Para obtener más información, consulte [Diseñar informes multilingües en los informes electrónicos](er-design-multilingual-reports.md).

10. Cierre la página **Diseñador de modelo de datos**.

#### <a name="complete-a-custom-data-model-configuration"></a>Completar una configuración de modelo de datos personalizada

Debe completar su trabajo con la versión 50.1 de la configuración de modelo de datos de ER personalizada para que esté disponible, de forma que se puedan agregar otras configuraciones de ER personalizadas.

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de factura** y seleccione **Modelo de factura (Litware)**.
3. En la ficha desplegable **Versiones**, seleccione **Cambiar Estado** \> **Completar** y luego seleccione **Aceptar**.

El estado de la versión 50.1 se cambia de **Borrador** a **Completado** y la versión se convierte en solo lectura. Se ha agregado una nueva versión editable, 50.2, y tiene un estado de **Borrador**. Puede usar esta versión para realizar más cambios en la configuración de modelo de datos de ER personalizada.

![Versión 50.1 completada en la página Configuraciones.](./media/er-quick-start3-completed-custom-model1.png)

### <a name="customize-the-model-mapping-configuration"></a>Personalizar la configuración de la asignación de modelo

Como usuario con el rol de Desarrollador de informes electrónicos puede diseñar su asignación de modelo de ER personalizada.

#### <a name="add-a-custom-model-mapping-configuration"></a>Agregar una configuración de asignación de modelo de ER personalizada

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de factura de cliente** y seleccione **Asignación de modelo de factura de cliente**.
3. En el panel de acciones, seleccione **Crear configuración**.
4. En el cuadro de diálogo desplegable, en el campo **Nuevo**, seleccione **Derivar de nombre: asignación de modelo de factura de cliente, Microsoft** para indicar que su nueva configuración personalizada de asignación de modelo de ER debe basarse en la configuración de asignación de modelo de ER.
5. En el campo **Nombre**, escriba **Asignación de modelo de factura (Litware)**.
6. En el campo **Modelo de destino**, seleccione **Modelo de factura (Litware)**.

    > [!IMPORTANT]
    > Este paso es muy importante. Si lo omite, no podrá utilizar su modelo de datos personalizado en la asignación de modelo configurada.

7. Seleccione **Crear configuración** para agregar la nueva configuración de ER.

![Agregar una asignación de modelo personalizada en la página Configuraciones.](./media/er-quick-start3-adding-custom-mapping.png)

#### <a name="configure-a-custom-model-mapping"></a>Configurar una asignación de modelo personalizada

Debe modificar la asignación de su modelo personalizado y especificar cómo se debe rellenar el campo personalizado **FederalTaxID\_Litware** del modelo de datos personalizado con los datos de la aplicación en tiempo de ejecución.

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de factura de cliente** \> **Asignación de modelo de factura de cliente** y seleccione **Asignación de modelo de factura (Litware)**.
3. En el panel de acciones, haga clic en **Diseñador**.
4. En la página **Asignación de modelo a origen de datos**, seleccione la asignación **Factura de cliente**.

    ![Página de asignación de modelo a origen de datos.](./media/er-quick-start3-select-customer-mapping.png)

5. Seleccione **Diseñador**.
6. En la página **Diseñador de asignación de modelo**, en el panel **Orígenes de datos**, expanda el origen de datos **CustInvoiceJour**, que representa la tabla de aplicación **CustInvoiceJour**.
7. En **CustInvoiceJour**, expanda **Relaciones** para revisar la lista de relaciones de tipo varios a uno (N: 1) para la tabla **CustInvoiceJour**.
8. En **CustInvoiceJour** \> **Relaciones**, expanda **Clientes (CustTable)** para acceder a los campos y relaciones de la tabla **Clientes (CustTable)**.
9. Seleccione el campo de origen de datos **FederalTaxID\_Personalizado** que implementó [anteriormente](#insert_custom_field).
10. En el panel **Modelo de datos**, expanda **Información del cliente (cliente)** y seleccione el campo de modelo de datos **FederalTaxID\_Litware**.
11. Seleccione **Enlazar**.

    ![Página de diseñador de asignación de modelos.](./media/er-quick-start3-customize-model-mapping.gif)

12. Seleccione **Guardar**.
13. Cierre la página **Diseñador de distribución del modelo**.
14. Cierre la página **Asignación de modelo a origen de datos**.

#### <a name="complete-a-custom-model-mapping-configuration"></a>Completar una configuración de asignación de modelo personalizada

Debe completar su trabajo con la versión 50.19.1 de su configuración de asignación de modelo de ER personalizada para que esté disponible.

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de factura de cliente** \> **Asignación de modelo de factura de cliente** y seleccione **Asignación de modelo de factura (Litware)**.
3. En la ficha desplegable **Versiones**, seleccione **Cambiar Estado** \> **Completar** y luego seleccione **Aceptar**.

El estado de la versión 50.19.1 se cambia de **Borrador** a **Completado** y la versión se convierte en solo lectura. Se ha agregado una nueva versión editable, 50.19.2, y tiene un estado de **Borrador**. Puede usar esta versión para realizar más cambios en la configuración de asignación de modelo de ER personalizada.

![Versión 50.19.1 completada en la página Configuraciones.](./media/er-quick-start3-completed-custom-mapping1.png)

> [!NOTE]
> El [ciclo de vida](general-electronic-reporting-manage-configuration-lifecycle.md) de configuración admitido no cubre el ciclo de vida de los cambios de base de datos. Si exporta la versión 50.19.1 de la configuración de **Asignación de modelo de factura (Litware)** de la instancia de Finance actual e intenta importarla en otra instancia que no contenga el campo **FederalTaxID\_Personalizado** de la tabla **CustTable**, se producirá una excepción. La excepción indicará que la configuración de ER importada no es compatible con los metadatos de la instancia de Finance de destino.

### <a name="customize-the-format-configuration"></a>Personalizar la configuración del formato

Como usuario con el rol de Consultor funcional de informes electrónicos, puede diseñar su formato de ER personalizado.

#### <a name="add-a-custom-format-configuration"></a>Agregar una configuración de formato personalizada

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de factura de cliente** \> **Factura de ventas UBL** y seleccione **Factura de ventas Peppol**.
3. En el panel de acciones, seleccione **Crear configuración**.
4. En el cuadro de diálogo desplegable, en el campo **Nuevo**, seleccione **Derivar de nombre: factura de ventas Peppol, Microsoft** para indicar que su configuración de formato de ER personalizada debe basarse en el formato de ER.
5. En el campo **Nombre**, escriba **Factura de ventas Peppol (Litware)**.
6. En el campo **Modelo de datos**, seleccione **Modelo de factura (Litware)** para utilizar sus componentes personalizados de modelo de datos y asignación de modelo.

    > [!NOTE]
    > Este paso es muy importante. Si lo omite, no podrá utilizar su modelo de datos personalizado en el formato configurado.

7. En el campo **Modelo de datos**, seleccione la definición de raíz **InvoiceCustomer**.
8. Seleccione **Crear configuración** para agregar la nueva configuración de ER.

![Agregar una configuración de formato personalizada en la página Configuraciones.](./media/er-quick-start3-adding-custom-format.png)

Ahora puede utilizar el diseñador de operaciones de ER para editar la versión 11.2.2.1 de la configuración de ER **Factura de ventas Peppol (Litware)** con el estado **Borrador**.

![Versión 11.2.2.1 de la configuración de ER editable en la página Configuraciones.](./media/er-quick-start3-added-custom-format.png)

#### <a name="configure-a-custom-format"></a>Configurar un formato personalizado

Debe modificar su formato personalizado agregando un nuevo elemento de formato para rellenar el valor del código de identificación fiscal federal de un cliente facturado.

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de factura de cliente** \> **Factura de ventas UBL** \> **Factura de ventas** y seleccione **Factura de ventas Peppol**.
3. En el panel de acciones, haga clic en **Diseñador**.
4. En el árbol de formato, expanda **XMLHeader** \> **Factura** \> **cac: AccountingCustomerParty** \> **cac:Party** \> **cac:PartyTaxScheme** \> **cac:TaxScheme** y seleccione **cbc:ID**.
5. Seleccione **Agregar** y, a continuación, seleccione **XML** \> **Atributo**.
6. En el cuadro de diálogo **Propiedad de componente**, en el campo **Nombre**, escriba **FederalTaxID**.
7. Seleccione **Aceptar** para agregar un nuevo elemento de formato a fin de crear un nuevo atributo XML **FederalTaxID** en un archivo XML generado.
8. En el árbol de formato, en **XMLHeader** \> **Factura** \> **cac:AccountingCustomerParty** \> **cac:Party** \> **cac:PartyTaxScheme** \> **cac:TaxScheme** \> **cbc:ID**, seleccione **FederalTaxID**.
9. Seleccione **Subir**.

![Nuevo elemento de formato en la página Diseñador de formato.](./media/er-quick-start3-customized-format.png)

#### <a name="configure-a-custom-format-mapping"></a>Configurar una asignación de formato personalizada

1. En la página **Diseñador de formato**, en la pestaña **Asignación**, expanda el origen de datos **Factura** del tipo **Modelo**.
2. En **Factura**, expanda **Información del cliente (cliente)** y seleccione **FederalTaxID\_Litware**.
3. Seleccione **Enlazar**.

    ![Página de diseñador de formato.](./media/er-quick-start3-customized-format-mapping.png)

4. Seleccione el origen de datos **Factura** del tipo **Modelo** y, a continuación, seleccione **Editar**.
5. En el campo **Versión**, seleccione la versión **1** de su modelo de datos personalizado y, a continuación, seleccione **Aceptar**.
6. Seleccione **Guardar**.
7. Cierre la página **Diseñador de formato**.

#### <a name="complete-a-custom-format-configuration"></a>Completar una configuración de formato personalizada

Debe completar su trabajo con la versión 11.2.2.1 de su configuración de formato de ER personalizada para que esté disponible.

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de factura de cliente** \> **Factura de ventas UBL** \> **Factura de ventas** y seleccione **Factura de ventas Peppol**.
3. En la ficha desplegable **Versiones**, seleccione **Cambiar Estado** \> **Completar** y luego seleccione **Aceptar**.

El estado de la versión 11.2.2.1 se cambia de **Borrador** a **Completado** y la versión se convierte en solo lectura. Se ha agregado una nueva versión editable, 11.2.2.2, y tiene un estado de **Borrador**. Puede usar esta versión para realizar más cambios en su configuración de formato ER personalizada.

![Versión 11.2.2.1 completada en la página Configuraciones.](./media/er-quick-start3-completed-custom-format1.png)

## <a name="configure-the-accounts-receivable-parameters-to-start-to-use-custom-er-configurations"></a><a name="ConfigureAR2"></a>Configurar los parámetros de clientes para empezar a usar las configuraciones personalizadas de ER.

1. Vaya a **Clientes** \> **Configuración** \> **Parámetros de clientes**.
2. En la pestaña **Documentos electrónicos**, en la ficha desplegable **Informes electrónicos**, en el campo **Factura de servicios y ventas**, seleccione **Factura de ventas Peppol (Litware)**.
3. Seleccione **Guardar**.

![Página Parámetros de clientes, pestaña Documentos electrónicos, ficha desplegable Informes electrónicos.](./media/er-quick-start3-configure-ar2.png)

## <a name="update-a-customer-record-by-adding-a-federal-tax-identification-code"></a><a name="ConfigureCustomer2"></a>Actualizar el registro de un cliente agregando un código de identificación fiscal federal

1. Vaya a **Clientes** \> **Clientes** \> **Todos los clientes**.
2. En la página **Todos los clientes**, seleccione el vínculo de cuente de cliente **DE-014**.
3. En la ficha desplegable **General**, en el campo **Id. de impuestos federales**, escriba **LITWARE-6789**.
4. Seleccione **Guardar**.

    ![Página de detalles del cliente DE-014.](./media/er-quick-start3-added-tax-id-value.png)

5. Cierre la página **Todos los clientes**.

## <a name="process-a-customer-invoice-by-using-custom-er-configurations"></a><a name="ProcessInvoice2"></a>Procesar una factura de cliente mediante las configuraciones personalizadas de ER.

### <a name="select-and-send-a-posted-invoice"></a>Seleccionar y enviar una factura registrada

1. Vaya a **Clientes** \> **Facturas** \> **Todas las facturas de servicios**.
2. En la página **Factura de servicios**, seleccione la factura que agregó y registró anteriormente.
3. En el panel de acciones, en el grupo **Documento**, seleccione **Enviar** \> **Original**.
4. Cierre la página **Factura de servicios**.

### <a name="analyze-a-generated-e-invoice"></a>Analizar una factura electrónica generada

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Trabajos de informes electrónicos**.
2. En la página **Trabajos de informes electrónicos**, seleccione el registro más reciente que tiene la descripción de tarea **Enviar XML de factura electrónica**.
3. Seleccione **Mostrar archivos** para acceder a la lista de archivos generados.
4. Seleccione **Abrir** para descargar el archivo XML de factura electrónica que se genera.
5. Analice el archivo XML de factura electrónica. Tenga en cuenta que, de acuerdo con su personalización, el esquema de impuestos del cliente incluye el atributo XML **FederalTaxID**, además de los atributos XML **schemeID** y **schemeAgencyID**. El valor de este nuevo atributo XML lo especifica el id. fiscal federal **LITWARE-6789** que se especificó para un cliente facturado.

    ![Vista previa del archivo XML de factura electrónica generado con sus personalizaciones.](./media/er-quick-start3-e-invoice2.png)

## <a name="import-the-latest-versions-of-standard-er-configurations"></a><a name="ImportERConfigurations2"></a>Importar las versiones más recientes de las configuraciones estándar de ER

Para mantener [actualizado](general-electronic-reporting-manage-configuration-lifecycle.md) el conjunto de configuraciones estándar de ER en su instancia de Finance, debe importar nuevas versiones de las configuraciones siempre que estén disponibles en el [repositorio](general-electronic-reporting.md#Repository) de ER que se configuró para esa instancia.

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones de localización**, en la sección **Proveedores de configuración**, seleccione el mosaico **Microsoft** y luego seleccione **Repositorios** para ver la lista de repositorios para el proveedor de Microsoft.
3. En la página **Configuración de repositorios**, seleccione el repositorio existente del tipo **Global** y después seleccione **Abrir**. Si se le solicita autorización para conectarse al Regulatory Configuration Service, siga las instrucciones de autorización.
4. En la página **Repositorio de configuración**, en el árbol de configuración del panel izquierdo, seleccione el formato de configuración **Factura de ventas Peppol**.
5. En la ficha desplegable **Versiones**, seleccione la versión **32.6.7** de la configuración de formato de ER seleccionada que se ha lanzado para permitir el uso de facturas electrónicas de cliente con el formato PEPPOL BIS 3. Para obtener más información, consulte [KB4490320](https://support.microsoft.com/help/4490320/an-update-for-european-union-to-support-export-of-customers-electronic).
6. Seleccione **Importar** para descargar la versión seleccionada del repositorio Global a la instancia actual de Finance.

![Versión 32.6.7 seleccionada en la página Repositorio de configuraciones.](./media/er-quick-start3-import-solution2.png)

Para obtener información sobre cómo se puede automatizar este proceso, consulte [Importar versiones actualizadas de configuraciones de ER](er-download-updated-versions-global-repo.md).

### <a name="review-the-imported-er-configurations"></a>Revisar las configuraciones importadas de ER

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones de localización**, en la sección **Configuraciones**, seleccione el icono **Configuraciones de informes**.
3. Expanda la ficha desplegable **Componentes de la configuración**.
4. En el árbol de configuración del panel izquierdo, expanda **Modelo de factura**. Observe que el nombre del **Modelo de factura de cliente** ha cambiado a **Modelo de factura** en una de las configuraciones del modelo de datos de ER importadas.
5. En el árbol de configuración del panel izquierdo, expanda **Asignación de modelo de factura**. Observe que el nombre de la **Asignación del modelo de factura de cliente** ha cambiado a **Asignación de modelo de factura** en una de las configuraciones de asignación de modelo de ER importadas.
6. Expanda **Factura de ventas UBL** \> **Factura de venta Peppol**.

Tenga en cuenta que, además del formato de ER **Factura de ventas Peppol** seleccionado, se importaron las versiones más recientes de otras configuraciones de ER necesarias. Como se publican constantemente nuevas versiones de las configuraciones de ER en el repositorio Global y LCS para mantener la compatibilidad de las soluciones de ER correspondientes compatibles con los nuevos requisitos, se han importado las versiones más recientes de la configuración de modelo de datos requerida y su asignación de modelo.

Asegúrese de que las siguientes configuraciones de ER estén disponibles en el árbol de configuración:

- Configuración del modelo de datos de ER **Modelo de factura**:

    - La versión 206 (o posterior) contiene la versión 24 (o posterior) del componente modelo de datos de ER que representa la estructura de datos del dominio empresarial de facturación. Esta configuración de ER se ha importado como un antepasado de la versión más reciente disponible de la configuración de asignación de modelo de ER **Asignación de modelo de factura**.

    ![Versión 206 en la página Configuraciones.](./media/er-quick-start3-imported-solution2b1.png)

- Configuración de la asignación de modelo de ER **Asignación de modelo de factura**:

    - La versión 206.132 (o posterior) se ha importado como la implementación más reciente de la versión 206 de la configuración de modelo de datos de ER **Modelo de factura**. Contiene varios componentes de ER de asignación de modelo que describen cómo se rellena el modelo de datos con los datos de la aplicación en tiempo de ejecución.

    ![Versión 206.132 en la página Configuraciones.](./media/er-quick-start3-imported-solution2b2.png)

- Configuración de formato de ER **Factura de ventas UBL**:

    - La versión 32.6 contiene los componentes de ER de formato y asignación de formato. El componente de formato especifica el diseño del informe. El componente de asignación de formato contiene el origen de datos del modelo y especifica cómo se usa este origen de datos para rellenar el diseño del informe en tiempo de ejecución. Este formato de ER se configuró para generar facturas electrónicas en formato UBL. Se ha importado como antepasado del formato de ER **Factura de ventas Peppol** que se seleccionó para importar.

- Configuración de formato de ER **Factura de ventas Peppol**:

    - La versión 32.6.7 contiene los componentes de ER de formato y asignación de formato que se configuraron para generar facturas electrónicas con formato PEPPOL.

    ![Versión 32.6.7 en la página Configuraciones.](./media/er-quick-start3-imported-solution2b3.png)

## <a name="adopt-the-changes-to-the-new-standard-er-configurations-in-your-custom-er-configurations"></a><a name="RebaseCustomERConfigurations"></a>Adoptar los cambios de las nuevas versiones de las configuraciones estándar de ER en sus configuraciones personalizadas de ER

### <a name="adopt-your-custom-er-data-model"></a>Adoptar su modelo de datos de ER personalizado

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de factura** y seleccione **Modelo de factura (Litware)**.
3. En la ficha desplegable **Versiones**, para la versión de borrador **50.2** de la configuración de modelo de datos seleccionada, seleccione **Reorganizar**.
4. En el campo **Versión de destino**, confirme la selección de la versión **206** de la configuración base del modelo de datos de ER y, a continuación, seleccione **Aceptar**.

    La versión de borrador de la configuración personalizada del modelo de datos de ER se vuelve a numerar de **50.2** a **206.2** para indicar que ahora contiene su personalización, fusionada con los cambios en la última versión (206) de la configuración base del modelo de datos de ER.

    > [!NOTE]
    > La acción de reorganización es reversible. Para cancelar esta reorganización, seleccione la versión **50.1** del modelo **Modelo de factura (Litware)** en la ficha desplegable **Versiones** y, a continuación, seleccione **Obtener esta versión**. La versión 206.2 se volverá a numerar **50.2** y el contenido de la versión borrador 50.2 coincidirá con el contenido de la versión 50.1.

5. En la ficha desplegable **Versiones**, seleccione **Cambiar Estado** \> **Completar** y luego seleccione **Aceptar**.

El estado de la versión 206.2 se cambia de **Borrador** a **Completado** y la versión se convierte en solo lectura. Se ha agregado una nueva versión editable, 206.3, y tiene un estado de **Borrador**. Puede usar esta versión para realizar más cambios en la configuración de modelo de datos de ER personalizada.

![Versión 206.2 completada en la página Configuraciones.](./media/er-quick-start3-completed-custom-model2.png)

### <a name="adopt-your-custom-er-model-mapping"></a>Adoptar su asignación de modelo de ER personalizado

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de factura** \> **Asignación de modelo de factura** y seleccione **Asignación de modelo de factura (Litware)**.
3. En la ficha desplegable **Versiones**, para la versión de borrador **50.19.2** de la configuración de asignación de modelo seleccionada, seleccione **Reorganizar**.
4. En el campo **Versión de destino**, confirme la selección de la versión **206.132** de la configuración base de la asignación de modelo de ER y, a continuación, seleccione **Aceptar**.

    La versión de borrador de la configuración personalizada de asignación de modelo de ER se vuelve a numerar de **50.19.2** a **206.132.2** para indicar que ahora contiene su personalización, fusionada con los cambios en la última versión (206.132) de la configuración base de la asignación de modelo de ER.

    Observe que se han descubierto algunos conflictos de reorganización. Ahora debe resolver estos conflictos manualmente.

    ![Mensaje de conflicto de reorganización en la página Configuraciones.](./media/er-quick-start3-rebase-conflicts-model-mapping1.png)

5. En el panel de acciones, seleccione **Diseñador** y, a continuación, en la lista de asignaciones, seleccione **Factura de cliente**.
6. Para cada conflicto de reorganización, seleccione **Conservar su propio valor**, porque debe mantener el número de versión de su modelo de datos personalizado para cada componente que se ha mencionado.

    ![Conflictos de reorganización en la página del diseñador de asignación de modelo.](./media/er-quick-start3-rebase-conflicts-model-mapping2.png)

7. Seleccione **Guardar** y, a continuación, cierre la página **Diseñador de asignación de modelo**.
8. En la lista de asignaciones, seleccione **Factura de proyecto**.
9. Para cada conflicto de reorganización, seleccione **Conservar su propio valor**, porque debe mantener el número de versión de su modelo de datos personalizado para cada componente que se ha mencionado.
10. Seleccione **Guardar** y, a continuación, cierre la página **Asignaciones de modelo**.

    > [!NOTE]
    > La acción de reorganización es reversible. Para cancelar esta reorganización, seleccione la versión **50.19.1** del modelo **Asignación de modelo de factura (Litware)** en la ficha desplegable **Versiones** y, a continuación, seleccione **Obtener esta versión**. La versión 206.132.2 se volverá a numerar **50.19.2** y el contenido de la versión borrador 50.19.2 coincidirá con el contenido de la versión 50.19.1.

11. En la ficha desplegable **Versiones**, seleccione **Cambiar Estado** \> **Completar** y luego seleccione **Aceptar**.

El estado de la versión 206.132.2 se cambia de **Borrador** a **Completado** y la versión se convierte en solo lectura. Se ha agregado una nueva versión editable, 206.132.3, y tiene un estado de **Borrador**. Puede usar esta versión para realizar más cambios en la configuración de asignación de modelo de ER personalizada.

![Versión 206.132.2 completada en la página Configuraciones.](./media/er-quick-start3-completed-custom-mapping2.png)

### <a name="adopt-your-custom-er-format"></a>Adoptar su formato de ER personalizado

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de factura** \> **Factura de ventas UBL** \> **Factura de ventas Peppol** y seleccione **Factura de ventas Peppol (Litware)**.
3. En la ficha desplegable **Versiones**, para la versión de borrador **11.2.2.2** de la configuración de formato seleccionada, seleccione **Reorganizar**.
4. En el campo **Versión de destino**, confirme la selección de la versión **32.6.7** de la configuración base del formato de ER y, a continuación, seleccione **Aceptar**.

    La versión de borrador de la configuración personalizada de formato de ER se vuelve a numerar de **11.2.2.2** a **32.6.7.2** para indicar que ahora contiene su personalización, fusionada con los cambios en la última versión (32.6.7) de la configuración base de formato de ER.

    Observe que se han descubierto algunos conflictos de reorganización. Ahora debe resolver estos conflictos manualmente.

5. En el panel de acciones, haga clic en **Diseñador**.
6. Para cada conflicto de reorganización, seleccione **Conservar su propio valor**, porque debe mantener el número de versión de su modelo de datos personalizado para cada componente que se ha mencionado.
7. Seleccione **Guardar**.
8. En la pestaña **Asignación**, seleccione el origen de datos **Factura** del tipo **Modelo** y, a continuación, seleccione **Editar**.
9. En el campo **Versión**, seleccione la versión **2** de su modelo de datos personalizado y, a continuación, seleccione **Aceptar**.
10. Seleccione **Guardar**.

    > [!NOTE]
    > La acción de reorganización es reversible. Para cancelar esta reorganización, seleccione la versión **11.2.2.1** del formato **Factura de ventas Peppol (Litware)** en la ficha desplegable **Versiones** y, a continuación, seleccione **Obtener esta versión**. La versión 32.6.7.2 se volverá a numerar **11.2.2.2** y el contenido de la versión borrador 11.2.2.2 coincidirá con el contenido de la versión 11.2.2.1.

11. Cierre la página **Diseñador de formato**.
12. En la ficha desplegable **Versiones**, seleccione **Cambiar Estado** \> **Completar** y luego seleccione **Aceptar**.

El estado de la versión 32.6.7.2 se cambia de **Borrador** a **Completado** y la versión se convierte en solo lectura. Se ha agregado una nueva versión editable, 32.6.7.3, y tiene un estado de **Borrador**. Puede usar esta versión para realizar más cambios en su configuración de formato ER personalizada.

![Versión 32.6.7.2 completada en la página Configuraciones.](./media/er-quick-start3-completed-custom-format2.png)

## <a name="process-a-customer-invoice-by-using-new-versions-of-the-custom-er-configurations"></a><a name="ProcessInvoice3"></a>Procesar una factura de cliente mediante las nuevas versiones de las configuraciones personalizadas de ER.

### <a name="select-and-send-a-posted-invoice"></a>Seleccionar y enviar una factura registrada

1. Vaya a **Clientes** \> **Facturas** \> **Todas las facturas de servicios**.
2. En la página **Factura de servicios**, seleccione la factura que agregó y registró anteriormente.
3. En el panel de acciones, en el grupo **Documento**, seleccione **Enviar** \> **Original**.

    > [!NOTE] 
    > Como ahora tiene dos versiones de la configuración de formato de ER **Factura de venta de Peppol (Litware)** y ninguna versión tiene un valor de fecha efectiva, se utiliza la última versión para generar una factura electrónica.

4. Cierre la página **Factura de servicios**.

### <a name="analyze-a-generated-e-invoice"></a>Analizar una factura electrónica generada

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Trabajos de informes electrónicos**.
2. En la página **Trabajos de informes electrónicos**, seleccione el registro más reciente que tiene la descripción de tarea **Enviar XML de factura electrónica**.
3. Seleccione **Mostrar archivos** para acceder a la lista de archivos generados.
4. Seleccione **Abrir** para descargar el archivo XML de factura electrónica que se genera.
5. Analice el archivo XML de factura electrónica. Tenga en cuenta que, de acuerdo con su personalización, el esquema de impuestos del cliente incluye el atributo XML **FederalTaxID**, además de los atributos XML **schemeID** y **schemeAgencyID**. Además, debido a que los cambios en la nueva versión del formato base **Factura de ventas UBL** se fusionaron con su personalización, el texto del elemento XML **cbc:CustomizationID** ha cambiado de `urn:www.cenbii.eu:transaction:biicoretrdm010:ver1.0:# urn:www.peppol.eu:bis:peppol5a:ver1.0` a `urn:cen.eu:en16931:2017#compliant#urn:fdc:peppol.eu:2017:poacc:billing:3.0`.

    ![Vista previa del archivo XML de factura electrónica generado con sus personalizaciones.](./media/er-quick-start3-e-invoice3.png)

## <a name="additional-resources"></a>Recursos adicionales

- [Visión general de los informes electrónicos](general-electronic-reporting.md)
- [Descargar configuraciones ER de Lifecycle Services](download-electronic-reporting-configuration-lcs.md)
- [Descargue las configuraciones de ER del repositorio global del servicio de configuración](er-download-configurations-global-repo.md)
- [Crear una factura de servicio](../../../finance/accounts-receivable/create-free-text-invoice-new.md)
- [Crear y trabajar con campos personalizados](../../fin-ops/get-started/user-defined-fields.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
