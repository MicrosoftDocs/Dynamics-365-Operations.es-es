---
title: Configurar de informes electrónicos específicos de registros de gestión de impresión
description: En este tema se explica cómo configurar destinos específicos de registros de gestión de impresión para un formato de informes electrónicos (ER) que se ha configurado para generar documentos salientes.
author: NickSelin
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-08-01
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 1e06fafe8d8bbe92ddf4fcd94d7271a1fbb6362a
ms.sourcegitcommit: 7e32e5e39e762a4b1606161cb603a450d13b5251
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2021
ms.locfileid: "7413615"
---
# <a name="configure-print-management-record-specific-er-destinations"></a>Configurar de informes electrónicos específicos de registros de gestión de impresión

[!include [banner](../includes/banner.md)]

En este tema se explica cómo un usuario que tenga el rol de Administrador del sistema o Funcionario de clientes puede realizar las siguientes tareas:

- Configurar destinos de [informes electrónicos (ER)](general-electronic-reporting.md) con nombre para una solución de ER que genera facturas de servicios.
- Asignar un destino de ER a un solo registro de [gestión de impresión](document-reporting-services.md).

Los procedimientos se pueden llevar a cabo en la empresa USMF. No se requiere codificación.

## <a name="introduction"></a>Introducción

Puede configurar [destinos](electronic-reporting-destinations.md) para cada carpeta del componente de salida de archivo de una [configuración](general-electronic-reporting.md#Configuration) de [formato](general-electronic-reporting.md#FormatComponentOutbound) de informe electrónico (ER) que se usa para generar un documento saliente. Si cuando ejecuta un formato de informe electrónico de este tipo tiene los derechos de acceso adecuados, también puede cambiar los ajustes de destino configurados en tiempo de ejecución.

En la **versión 10.0.17 y posteriores** de Microsoft Dynamics 365 Finance, se puede [configurar](er-apis-app10-0-17.md) un código de acción para un formato de informes electrónicos a fin de especificar la acción que realizan los usuarios al ejecutar ese formato de informes electrónicos. Por ejemplo, en el módulo **Clientes**, en la configuración de Gestión de impresión, puede seleccionar un formato de informes electrónicos que genere un documento empresarial específico, como una factura de servicios. A continuación, puede seleccionar **Ver** para obtener una versión preliminar de la factura o **Imprimir** para enviarla a una impresora. Si se pasa una acción para el formato de informes electrónicos en tiempo de ejecución, puede [configurar diferentes destinos de informes electrónicos para diferentes acciones de usuario](er-action-dependent-destinations.md).

En la **versión 10.0.21 y posteriores** de Finance, se puede [configurar](er-apis-app10-0-21.md) un destino con nombre para un formato de informes electrónicos y asignarlo al registro de gestión de impresión que se procesa cuando se ejecuta ese formato de ER. Por ejemplo, en el módulo **Clientes**, en los ajustes de gestión de impresión, desea configurar el registro **Original** para realizar las siguientes acciones:

- Ejecutar un formato de ER.
- Enviar por correo electrónico la factura generada a un cliente.
- Configurar el registro **Copia** que para que ejecute el mismo formato.
- Imprimir una copia de la factura en una impresora de red.

En este caso, debe configurar diferentes destinos de ER para el formato de ER que se está ejecutando y debe seleccionar los destinos para los distintos registros de gestión de impresión.

## <a name="prerequisites"></a>Requisitos previos

Antes de comenzar, se debe activar la función **Permitir configurar destinos de ER por elemento de gestión de impresión** en el espacio de trabajo [Administración de características](../../fin-ops/get-started/feature-management/feature-management-overview.md#the-feature-management-workspace). También se debe modificar el código fuente para permitir la configuración de destinos de ER con nombre en la instancia actual de Finance y para habilitar la [nueva](er-apis-app10-0-21.md) API de ER.

Además, se debe [importar](er-download-configurations-global-repo.md) la configuración de ER **Factura de servicios (Excel)** en su instancia de Finance.

## <a name="configure-a-new-er-destination"></a>Configurar un nuevo destino de ER

1. Vaya a **Clientes** \> **Facturas** \> **Todas las facturas de servicios**.
2. Seleccione una factura para la cuenta de cliente **US-001**.
3. En la página **Factura de servicios**, en la pestaña **Factura**, en el grupo **Gestión de impresión**, seleccione **Gestión de impresión**.
4. En la página **Configuración de gestión de impresión**, expanda **Módulo - Clientes** \> **Documentos** \> **Factura de servicios**, seleccione el registro **Original** y siga estos pasos:

    1.  Observe la configuración actual del registro seleccionado:
        -   El informe de SSRS predeterminado **FreeTextInvoice.Report** está seleccionado en el campo **Formato de informe**.
        -   En el campo **Destino** se muestra el nombre **\<Default\>** para indicar que no hay ningún destino personalizado seleccionado para el informe de SSRS asignado. 
    2.  En el campo **Formato de informe**, seleccione la configuración de formato de ER **Factura de servicios (Excel)**.
        -   El nombre del campo **Destino** cambia a **Nombre de destino**.
        -   En el campo **Nombre de destino** se muestra el nombre **\<No named destination\>** para indicar que no hay ningún destino con nombre seleccionado para el formato de ER asignado.
    3.  Seleccione el botón de flecha que hay a la derecha del campo **Nombre de destino**.    
    4. En la página **Destino con nombre de informes electrónicos**, en el campo **Nombre**, escriba **Destino principal**.
    5. Seleccione **Guardar**.
    6. En la ficha desplegable **Destino de archivo**, [configure](er-destination-type-email.md) el destino **Correo electrónico** para el componente **Informe**.
    7. Cierre la página **Destino con nombre de informes electrónicos**.
    8. En la página **Configuración de gestión de impresión**, en el campo **Nombre de destino**, seleccione el destino con nombre **Destino principal**.

    ![Configuración de un destino de ER con nombre para el formato de ER seleccionado y su asignación a un registro de gestión de impresión configurado en la página Configuración de gestión de impresión](./media/er-named-destinations-01.gif)

    Ha configurado el destino de ER con nombre **Destino principal** para el formato **Factura de servicios (Excel)** y lo ha asignado al registro de gestión de impresión **Original** en **Módulo - Clientes** \> **Documentos** \> **Factura de servicios**.

5. Expanda **Módulo - Clientes** \> **Cuenta - US-001** \> **Factura de servicios**, seleccione el registro **Original** y siga estos pasos:

    1. Seleccione y mantenga seleccionado el registro (o haga clic en él con el botón derecho) y luego seleccione **Invalidar**.
    2. Seleccione el botón de flecha que hay a la derecha del campo **Nombre de destino**.
    3. En la página **Destino con nombre de informes electrónicos**, en el panel de acciones, seleccione **Nuevo**.
    4. En el campo **Nombre**, especifique **Destino US-001**.
    5. En la ficha desplegable **Destino de archivo**, [configure](er-destination-type-print.md) el destino **Impresora** para el componente **Informe**.
    6. Cierre la página **Destino con nombre de informes electrónicos**.
    7. En la página **Configuración de gestión de impresión**, en el campo **Nombre de destino**, seleccione el destino con nombre **Destino US-001**.

    ![Configuración de un destino de ER con nombre para el formato de ER seleccionado y su asignación al registro de gestión de impresión configurado en la página Configuración de gestión de impresión](./media/er-named-destinations-02.gif)

    Ha configurado el destino de ER con nombre **Destino US-001** para el formato **Factura de servicios (Excel)** y lo ha asignado al registro de gestión de impresión **Original** en **Módulo - Clientes** \> **Cuentas - US-001** \> **Factura de servicios**.

Ahora, cuando se procese una factura de servicios, se ejecutará el formato de ER **Factura de servicios (Excel)** y se producirá uno de los siguientes eventos:

- Si la factura de servicios es para un cliente que no es US-001, el documento generado se envía por correo electrónico.
- Si la factura de servicios es para el cliente US-001, el documento generado se imprime.

> [!NOTE]
> Cuando no se ha definido ningún destino con nombre para un registro de gestión de impresión que se procesa en tiempo de ejecución, se utilizan los destinos de ER predeterminados si están disponibles para el formato de ER que se está ejecutando.

> [!IMPORTANT]
> En la página **Destino de informes electrónicos** (**Administración de la organización** \> **Informes electrónicos** \> **Destino de informes electrónicos**), si selecciona un formato de ER para el que se configuró al menos un destino con nombre, se le notificará la presencia de destinos con nombre.
>
> ![Notificación sobre la existencia de destinos con nombre configurados para el formato de ER seleccionado en la página Destino de informes electrónicos](./media/er-named-destinations-03.png)
>
> Si elimina el destino predeterminado, también se eliminarán todos los destinos con nombre. Si esos destinos con nombre se seleccionaron para los registros de gestión de impresión, la selección de esos destinos con nombre se cancela.

## <a name="copy-an-existing-er-destination-as-a-new-named-destination"></a>Copiar un destino de ER existente como un nuevo destino con nombre

Cuando el destino de ER con nombre predeterminado está disponible para un formato de ER, puede utilizarse como plantilla para nuevos destinos de ER. Para crear un nuevo destino de ER basado en el destino predeterminado, seleccione **Copiar del predeterminado** en la página **Destino con nombre de informes electrónicos**. El nuevo destino se llama **Predeterminado**. Puede repetir este paso tantas veces como sea necesario.

Puede seleccionar cualquier destino con nombre existente como plantilla para un nuevo destino con nombre. Para crear un nuevo destino de ER con nombre basado en un destino con nombre seleccionado, seleccione **Copiar** en la página **Destino con nombre de informes electrónicos**. El nuevo destino tiene el mismo nombre que el destino con nombre seleccionado, pero se le agrega el sufijo "Copia". Puede repetir este paso tantas veces como sea necesario.

## <a name="security-considerations"></a>Consideraciones de seguridad

Solo puede configurar destinos de ER con nombre en la página **Configuración de gestión de impresión** si tiene [permiso](../sysadmin/role-based-security.md#permissions) para realizar esta tarea. Se le puede conceder permiso si se ha asignado el [derecho](../sysadmin/role-based-security.md#duties) **Configurar destino de formato de informes electrónicos** a uno de sus [roles de seguridad](../sysadmin/role-based-security.md#security-roles). Para obtener más información, consulte [Consideraciones de seguridad](electronic-reporting-destinations.md#security-considerations).

## <a name="additional-resources"></a>Recursos adicionales

[Información general de los informes electrónicos (ER)](general-electronic-reporting.md)

[Destinos de informes electrónicos (ER)](electronic-reporting-destinations.md)

[Cambios en la API del marco de informes electrónicos para Application update 10.0.17](er-apis-app10-0-17.md)

[Cambios en la API del marco de informes electrónicos para Application update 10.0.21](er-apis-app10-0-21.md)

[Cambiar el código para permitir que los usuarios configuren y usen destinos de ER con nombre](er-api-named-destinations.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
