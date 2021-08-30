---
title: Configurar destinos de informes electrónicos dependientes de acciones
description: Este tema explica cómo configurar destinos dependientes de acciones para un informe electrónico (ER) que se ha configurado para generar documentos de salida.
author: NickSelin
ms.date: 02/09/2021
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
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 93adc5b91667fdcd5969439994170fe7d28258fc9f5762d1262d8e72862c4f5f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6762257"
---
# <a name="configure-action-dependent-er-destinations"></a>Configurar destinos de informes electrónicos dependientes de acciones

[!include [banner](../includes/banner.md)]

Puede configurar [destinos](electronic-reporting-destinations.md) para cada componente de salida (carpeta o archivo) de una [configuración](general-electronic-reporting.md#Configuration) de [formato](general-electronic-reporting.md#FormatComponentOutbound) de [informe electrónico (ER)](general-electronic-reporting.md) que se usa para generar un documento de salida. Los usuarios que ejecutan un formato de informe electrónico de este tipo y que tienen los derechos de acceso adecuados también pueden cambiar los ajustes de destino configurados en runtime.

En la **versión 10.0.17 y posteriores** de Microsoft Dynamics 365 Finance, un formato de informe electrónico se puede ejecutar mediante el [aprovisionamiento](er-apis-app10-0-17.md) de un código de acción que realiza el usuario al ejecutar ese formato de informe electrónico. Por ejemplo, en el módulo **clientes**, en la configuración de Gestión de impresión, puede seleccionar un formato de informe electrónico que genere un documento empresarial específico, como una factura de servicios. A continuación, puede seleccionar **Ver** para obtener una versión preliminar de la factura o **Imprimir** para enviarla a una impresora. Si se pasa una acción de usuario para el formato de informe electrónico en runtime, puede configurar diferentes destinos de informes electrónicos para diferentes acciones de usuario. Este tema explica cómo configurar destinos de informes electrónicos para este tipo de formato de informe electrónico.

## <a name="make-action-dependent-er-destinations-available"></a>Habilitar los destinos de informes electrónicos dependientes de acciones

Para configurar destinos de informes electrónicos dependientes de acciones en la instancia actual de Finance y habilitar la [nueva](er-apis-app10-0-17.md) API de informes electrónicos, abra el espacio de trabajo [Administración de características](../../fin-ops/get-started/feature-management/feature-management-overview.md#the-feature-management-workspace) y active la característica **Configurar destinos de informes electrónicos específicos para usarlos en diferentes acciones de gestión**. Para utilizar destinos de informes electrónicos configurados para informes [específicos](#reports-list-wave1) en runtime, habilite la función **Redirigir la salida de informes de gestión basados en destinos de informes electrónicos que son específicos de acciones del usuario (oleada1)**.

## <a name="configure-action-dependent-er-destinations"></a>Configurar destinos de informes electrónicos dependientes de acciones

Cuando activa la característica **Configurar destinos de informes electrónicos específicos para usarlos en diferentes acciones de gestión**, puede configurar destinos de informes electrónicos dependientes acciones en la ficha desplegable **Destino de archivo** de la página **Destino de informes electrónicos**. Para cada componente, puede agregar un registro y habilitar destinos específicos de informes electrónicos. Para cada registro, debe especificar el tipo de documento que se deben solicitar los destinos de informes electrónicos configurados. En el campo **Tipo de documento**, seleccione uno de los siguientes valores:

- Seleccione **Electrónico** para aplicar los destinos configurados si no se proporciona ningún código de acción del usuario en runtime.
- Seleccione **Gestión de impresión** para aplicar los destinos configurados si no se proporciona ningún código de acción del usuario en runtime.
- Seleccione **Cualquiera** para aplicar siempre los destinos configurados se haya proporcionado o no un código de acción del usuario en runtime.

Si selecciona el tipo de documento **Gestión de impresión**, debe especificar las acciones del usuario para las que se deben solicitar los destinos de informes electrónicos configurados. En el campo **Acción de Gestión de impresión**, seleccione uno de los siguientes valores:

- Seleccione **Ver** para aplicar los destinos configurados si se proporciona la acción de usuario **Ver** en runtime.
- Seleccione **Imprimir** para aplicar los destinos configurados si se proporciona la acción de usuario **Imprimir** en runtime.
- Seleccione **Enviar** para aplicar los destinos configurados si se proporciona la acción de usuario **Enviar** en runtime.

> [!NOTE]
> Se pueden seleccionar varias acciones para un solo registro de destino.

Si selecciona tipo de documento **Cualquiera**, se selecciona automáticamente **Detección automática** en el campo **Acción de Gestión de impresión** como una acción del usuario, y se produce el siguiente comportamiento:

- Si no se ha proporcionado ningún código de acción del usuario en runtime, se aplican todos los destinos de informes electrónicos configurados.
- Si se proporciona un código de acción del usuario en runtime, se aplica un destino de informes electrónicos predefinido para una acción específica, **independientemente de si se ha habilitado**:

    - Cuando la acción **Ver** se proporciona en runtime, se aplica el destino de informes electrónicos **Pantalla**.
    - Cuando la acción **Enviar** se proporciona en runtime, se aplica el destino de informes electrónicos **Correo electrónico**.
    - Cuando la acción **Imprimir** se proporciona en runtime, se aplica el destino de informes electrónicos **Impresora**.

Por ejemplo, puede utilizar el formato de informes electrónicos **Factura de servicios (Excel)** para imprimir una [factura de servicios](../../../finance/accounts-receivable/create-free-text-invoice-new.md) cuando lo publique. Para dirigir un documento generado, debe configurar destinos de informes electrónicos para este formato de informes electrónicos. Por ejemplo, es posible que deba configurar estos destinos de informes electrónicos para realizar lo siguiente en un documento generado:

- Archivar el documento si se ejecuta el formato de informes electrónicos pero no se proporciona ningún código de acción (por ejemplo, cuando el documento se envía electrónicamente).
- Obtener una vista preliminar del documento en un navegador web cuando un usuario realiza la acción **Ver**.
- Archivar e imprimir el documento cuando un usuario realiza la acción **Imprimir**.
- Archivar el documento y enviarlo por correo electrónico como archivo adjunto de un mensaje de correo electrónico saliente cuando un usuario realiza la acción **Enviar**.

La siguiente ilustración muestra cómo puede lograr esto configurando destinos de informes electrónicos como el conjunto de registros de destino individuales cuando cada registro está configurado para una acción de usuario individual:

![Página de destino de informes electrónicos que tiene configuraciones de destino dependientes de acciones para un formato de informes electrónicos cuando cada registro de destino está configurado para una sola acción de usuario.](./media/er-destination-action-dependent-01.png)

La siguiente ilustración muestra cómo puede lograr lo mismo de forma alternativa configurando destinos de informes electrónicos como el conjunto de registros de destino individuales cuando cada registro está configurado para un destino individual:

![Página de destino de informes electrónicos que tiene configuraciones de destino dependientes de acciones para un formato de informes electrónicos cuando cada registro de destino está configurado para un solo destino.](./media/er-destination-action-dependent-01a.png)

> [!NOTE]
> Si se proporciona un código de acción para el formato de informes electrónicos en ejecución, pero no se han configurado destinos para ese código de acción, se aplica el comportamiento de destino [predeterminado](electronic-reporting-destinations.md#default-behavior).

## <a name="change-action-dependent-er-destinations-at-runtime"></a>Cambiar los destinos de informes electrónicos dependientes de acciones en runtime

Cuando se ejecuta un formato de informes electrónicos, si las acciones del usuario han sido aprovisionadas por usuarios que tienen los [permisos](electronic-reporting-destinations.md#security-considerations) adecuados para cambiar la configuración de destino configurada en runtime, aparece un cuadro de diálogo que ofrece la opción de cambiar la configuración de destino configurada. Este cuadro de diálogo es opcional y su apariencia depende de cómo se haya implementado la llamada que hace el marco de informes electrónicos para ejecutar un formato de informes electrónicos. Si aparece este cuadro de diálogo, los destinos de informes electrónicos en él se habilitarán de acuerdo con la acción del usuario que se proporcione.

La siguiente ilustración muestra un ejemplo del cuadro de diálogo **Destinos de formato de informes electrónicos** que aparece cuando se [publica](../../../finance/accounts-receivable/create-free-text-invoice-new.md) una factura de servicios y el formato de informes electrónicos **Factura de servicios (Excel)** se ejecuta para generar este documento si se ha proporcionado la acción **Impresora** y los destinos de informes electrónicos se configuraron para este formato, como se mostró anteriormente en este tema.

![Cuadro de diálogo que ofrece la opción de cambiar los destinos de informes electrónicos configurados inicialmente para el formato de informes electrónicos en ejecución.](./media/er-destination-action-dependent-02.gif)

> [!NOTE]
> Si configuró destinos de informes electrónicos para varios componentes del formato de informes electrónicos en ejecución, se ofrecerá una opción por separado para cada componente configurado del formato de informes electrónicos.

## <a name="verify-the-provided-user-action"></a>Verificar la acción del usuario proporcionada

Puede verificar qué acción de usuario, si corresponde, se proporciona para el formato de informes electrónicos en ejecución cuando realiza una acción de usuario específica. Esta verificación es importante cuando debe configurar destinos de informes electrónicos dependientes de acciones, pero no está seguro de qué código de acción de usuario se proporciona, si corresponde. Por ejemplo, cuando comienza a registrar una factura de servicios y establece la opción **Imprimir factura** a **Sí** en el cuadro de diálogo **Registrar la factura de servicios**, puede configurar la opción **Usar destino de gestión de impresora** a **Sí** o **No**.

Siga estos pasos para verificar el código de acción del usuario que se proporciona.

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Configuración avanzada**, seleccione **Parámetros de usuario**.
3. En el cuadro de diálogo **Parámetros de usuario**, [establezca](er-trace-reports-compare-baseline.md#configure-er-parameters-to-use-the-baseline-feature) la opción **Ejecutar en modo depuración** a **Sí**.
4. Realice una acción de usuario ejecutando un formato de informes electrónicos. Recuerde que los parámetros de usuario de informes electrónicos son específicos de la compañía y del usuario.
5. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configurar registros de depuración**.
6. En la página **Configurar registros de depuración**, filtre los registros de ejecución de informes electrónicos para encontrar el registro de su ejecución en formato de informes electrónicos.
7. Revise las entradas del registro que deben contener el registro que presenta el código de acción del usuario proporcionado, si se ha proporcionado alguna acción para la ejecución del formato de informes electrónicos.

    ![Página de registros de ejecución de informes electrónicos que contiene información sobre el código de acción del usuario que se ha proporcionado para la ejecución filtrada de un formato de informes electrónicos.](./media/er-destination-action-dependent-03.png)

## <a name=""></a><a name="reports-list-wave1">Lista de documentos empresariales (oleada 1)</a>

La siguiente lista de documentos empresariales está controlada por la característica **Redirigir la salida de informes de gestión basados en destinos de informes electrónicos que son específicos de acciones del usuario (oleada1)**:

- Factura de cliente (factura de servicios)
- Factura de cliente (factura de ventas)
- Pedido de compra
- Consulta de compra de pedido de compra
- Confirmación del pedido de ventas
- Nota de la carta de cobros
- Extracto de cuenta de cliente
- Nota de interés
- Aviso de pago de proveedor
- Solicitud de presupuesto

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de los informes electrónicos (ER)](general-electronic-reporting.md)

[Destinos de informes electrónicos (ER)](electronic-reporting-destinations.md)

[Cambios en la API del marco de informes electrónicos para Application update 10.0.17](er-apis-app10-0-17.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]