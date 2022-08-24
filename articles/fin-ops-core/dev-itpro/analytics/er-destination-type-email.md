---
title: Tipo de destino de ER de correo electrónico
description: Este artículo explica cómo configurar un destino de correo electrónico para cada componente FOLDER o FILE de un informe electrónico (ER).
author: kfend
ms.date: 08/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.custom: 97423
ms.assetid: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
ms.openlocfilehash: 5e58618618d9125db4c81f49f62f48c2ce2f5e62
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285437"
---
# <a name="email-er-destination-type"></a>Tipo de destino de ER de correo electrónico

[!include [banner](../includes/banner.md)]

Cuando se ejecuta un formato de informes electrónicos (ER), se pueden generar uno o más documentos salientes. Los componentes de formato **Carpeta** o **Archivo** se utilizan en formatos ER para especificar la estructura de los documentos salientes. Puede configurar un destino de correo electrónico para este tipo de componentes para enviar documentos salientes como archivos adjuntos de correo electrónico.

Puede configurar un destino de correo electrónico para cada componente **Carpeta** o **Archivo** de un formato ER. En este caso, **cada documento saliente se envía por correo electrónico individualmente**. Según esta configuración de destino, un documento generado se entrega como archivo adjunto de un correo electrónico. 

> [!NOTE]
> Si no se genera ningún documento, porque la expresión **Habilitado** del componente **Archivo** relevante se ha configurado para devolver un valor booleano **Falso**, no se envía ningún correo electrónico, incluso si un destino de correo electrónico está configurado y habilitado para el componente.

También puede [agrupar](#grouping) varios componentes **Carpeta** o **Archivo** juntos y, a continuación, configurar un destino de correo electrónico para todos los componentes del grupo. En este caso, todos los documentos salientes generados por componentes que pertenecen al grupo **se envían como varios archivos adjuntos de un solo correo electrónico**. Según esta configuración de destino, cada documento generado se entrega como archivo adjunto en un único correo electrónico.

> [!NOTE]
> Si al menos un documento es generado por un componente **Archivo** en un grupo de componentes, se envía un correo electrónico. Si no se genera ningún documento por componentes agrupados, porque la expresión **Habilitado** de cada componente **Archivo** relevante se ha configurado para devolver un valor booleano **Falso**, no se envía ningún correo electrónico, incluso si un destino de correo electrónico está configurado y habilitado para el grupo de componentes.
>
> **Correo electrónico** es el único destino que se puede configurar para un grupo de componentes. Para entregar un documento que se envía por correo electrónico según la configuración de destino de correo electrónico para un grupo, agregue un registro de destino más, seleccione el componente que desee y luego configure otro destino para este registro.

Se pueden configurar varios grupos de componentes para una única configuración de formato ER. De esta manera, puede configurar un destino de correo electrónico para cada grupo de componentes y un destino de correo electrónico para cada componente.

## <a name="enable-an-email-destination"></a>Habilitar un destino de correo electrónico

Para enviar uno o más archivos de salida por correo electrónico, siga estos pasos.

1. En la página **Destino de informes electrónicos**, en la ficha desplegable **Destino de archivo**, seleccione un componente o grupo de componentes en la cuadrícula.
2. Seleccione **Configuración** y, después, en el cuadro de diálogo **Configuración de destino**, en la pestaña **Correo electrónico**, establezca la opción **Habilitado** en **Sí**.

[![Establecer la opción Activado en Sí para un destino de correo electrónico.](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)

## <a name="configure-an-email-destination"></a>Configurar un destino de correo

### <a name="email-content"></a>Contenido del correo electrónico

Puede editar el asunto y el cuerpo del mensaje de correo electrónico.

En el campo **Asunto**, escriba el texto del asunto del correo electrónico que debe aparecer en el campo de asunto de un mensaje electrónico que se genera en tiempo de ejecución. En el campo **Cuerpo**, escriba el texto del cuerpo del correo electrónico que debe aparecer en el campo de cuerpo de un mensaje electrónico. Puede configurar textos constantes para el asunto y el cuerpo de correo electrónico, o bien usar [fórmulas](er-formula-language.md) de informes electrónicos para crear dinámicamente textos de correo electrónico en tiempo de ejecución. La fórmula configurada debe devolver un valor de tipo [Cadena](er-formula-supported-data-types-primitive.md#string).

El cuerpo del correo electrónico se compone en formato TEXTO o HTML, según el cliente de correo electrónico. Puede usar cualquier diseño, estilo y marca que permitan el HTML y las hojas de estilo en cascada en línea (CSS).

> [!NOTE]
> Los clientes de correo electrónico imponen limitaciones de diseño y estilo que pueden requerir ajustes en el HTML y el CSS que utiliza para el cuerpo del mensaje. Le recomendamos que se familiarice con las prácticas recomendadas para crear HTML que los clientes de correo electrónico más populares admitan.
>
> Utilice la codificación correcta para implementar un retorno de carro, según el formato del cuerpo. Para obtener más información, consulte la definición del tipo de datos [Cadena](er-formula-supported-data-types-primitive.md#string).

### <a name="email-addresses"></a>Direcciones de correo electrónico

Puede especificar el remitente y los destinatarios del correo electrónico. De forma predeterminada, se envía correo electrónico en nombre del usuario actual. Para especificar otro remitente de correo electrónico, debe configurar el campo **De**.

> [!NOTE]
> Cuando se configura un destino de correo electrónico, el campo **De** solo es visible para los usuarios que tengan el privilegio de seguridad `ERFormatDestinationSenderEmailConfigure`, **Configurar la dirección de correo electrónico del remitente para destinos de formato ER**.
>
> Cuando se ofrece un destino de correo electrónico para su modificación en [tiempo de ejecución](electronic-reporting-destinations.md#security-considerations), el campo **De** solo es visible para los usuarios que tengan el privilegio de seguridad `ERFormatDestinationSenderEmailMaintain`, **Mantener la dirección de correo electrónico del remitente para el destino de formato ER**.
>
> Cuando el campo **De** está configurado para usar una dirección de correo electrónico distinta a la del usuario actual, el permiso **Enviar como** o **Enviar en nombre de** debe estar correctamente [configurado](/microsoft-365/solutions/allow-members-to-send-as-or-send-on-behalf-of-group) por adelantado. De lo contrario, se genera la siguiente excepción en tiempo de ejecución: "No se puede enviar correo electrónico como \<from email account\> desde la cuenta \<current user account\>, compruebe los permisos 'Enviar como' en la \<from email account\>."

Puede configurar el campo **De** para devolver más de una dirección de correo electrónico. En este caso, la primera dirección de la lista se utiliza como dirección de correo electrónico del remitente.

Para especificar los destinatarios de correo electrónico, debe configurar los campos **Para** y **CC** (opcionales).

Puede configurar direcciones de correo electrónico para el ER de dos maneras. La configuración se puede completar de la misma manera que la función de Gestión de impresión o puede resolver una dirección de correo electrónico utilizando una referencia directa a la configuración de ER mediante una fórmula.

## <a name="email-address-types"></a>Tipos de direcciones de correo electrónico

Si selecciona **Editar** junto al campo **De**, **Para** o **CC** en el cuadro de diálogo **Configuración de destino**, aparece el cuadro de diálogo **Correo electrónico de**, **Correo eletrónico para** o **CC de correo electrónico**. Allí podrá configurar el remitente y los destinatarios del correo electrónico. Seleccione **Agregar** y después seleccione el tipo de dirección de correo electrónico que se usará. Actualmente se admiten dos tipos: **Correo electrónico de configuración** y **Correo electrónico de gestión de impresión**.

[![Seleccionar el tipo de dirección de correo electrónico.](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)

### <a name="print-management-email"></a>Correo electrónico de administración de impresión

Si selecciona **Correo electrónico de gestión de impresión** como tipo de dirección de correo electrónico, puede introducir direcciones de correo electrónico fijas en el cuadro de diálogo **Correo electrónico de**, **Correo electrónico para** o **CC de correo electrónico** configurando los siguientes campos:

- En el campo **Origen de correo electrónico**, seleccione **Ninguno**.
- En el campo **Direcciones de correo electrónico adicionales, separadas por";"** campo, introduzca las direcciones de correo electrónico fijas.

Alternativamente, puede obtener direcciones de correo electrónico de los datos de contacto de la parte para la que genera un documento saliente. Para utilizar direcciones de correo electrónico que no son fijas en el campo **Correo de origen**, seleccione el [rol](../../fin-ops/organization-administration/overview-global-address-book.md#party-roles) de la parte del archivo de destino. Se admiten los siguientes roles:

- Cliente
- Proveedor
- Cliente prospecto
- Contacto
- Competidor
- Trabajador
- Candidato
- Proveedor prospecto
- Proveedor no permitido
- Entidad jurídica

Por ejemplo, para configurar un destino de correo electrónico para un formato ER que se utiliza para procesar pagos de proveedores, seleccione el rol **Proveedor**.

Después de seleccionar el rol deseado, seleccione el botón **Enlazar** (símbolo de cadena) junto al campo **Cuenta de origen de correo electrónico** para abrir la página del [Diseñador de fórmulas](general-electronic-reporting-formula-designer.md). Luego, puede usar esta página para configurar una fórmula que devuelva, en runtime, el número de cuenta de la parte que está asignada al rol configurado desde el documento procesado hasta el destino del correo electrónico.

> [!NOTE]
> Las fórmulas son específicas de la configuración de ER.

En la página del **Diseñador de fórmulas**, en el campo **Fórmula**, introduzca una referencia específica del documento a un rol admitido. En lugar de escribir la referencia, en el panel **Origen de datos**, busque y seleccione el nodo de origen de datos que representa una cuenta del rol configurado y luego seleccione **Agregar origen de datos** para actualizar la fórmula. Por ejemplo, si configura el destino de correo electrónico para la configuración **Transferencia de crédito ISO 20022** que se utiliza para procesar pagos a proveedores, el nodo que representa una cuenta de proveedor es `'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`.

![Configurar una cuenta de origen de correo electrónico.](./media/er_destinations-emaildefineaddresssource.gif)

Si los números de cuenta del rol configurado son únicos para toda la instancia de Microsoft Dynamics 365 Finance, el campo **Compañía de origen del correo electrónico** en el cuadro de diálogo **Correo para** puede permanecer en blanco.

Alternativamente, puede tener una situación en la que diferentes partes de la [Libreta de direcciones global](../../fin-ops/organization-administration/overview-global-address-book.md) han sido registrados en diferentes empresas ([entidades legales](../../fin-ops/organization-administration/organizations-organizational-hierarchies.md#legal-entities)) de tal manera que todos utilicen el mismo número de cuenta para cubrir el rol configurado. En este caso, los números de cuenta para el rol configurado no son únicos para toda la instancia de Finance. Por lo tanto, para seleccionar explícitamente una parte, no puede especificar solo un número de cuenta. También debe especificar la empresa en la que se ha registrado el partido para cubrir el rol configurado. Seleccione el botón **Enlazar** (símbolo de cadena) junto al campo **Correo de origen de la compañía** en el cuadro de diálogo **Correo para** para abrir la página del [Diseñador de formulas](general-electronic-reporting-formula-designer.md). Luego, puede usar esta página para configurar una fórmula que devuelva, en runtime, el código de la empresa en la que se debe encontrar la fuente deseada en el alcance.

> [!TIP]
> Si debe utilizar el código de la empresa para ejecutar un formato ER, pero el formato ER no proporciona ninguna fuente de datos de la que se pueda obtener el código de la empresa, configure la fórmula `GetCurrentCompany()` utilizando la función ER incorporada [GETCURRENTCOMPANY](er-functions-other-getcurrentcompany.md).

> [!NOTE]
> Las fórmulas son específicas de la configuración de ER.

Para especificar el tipo de direcciones de correo electrónico que se deben utilizar en runtime, en el cuadro de diálogo **Correo para**, seleccione **Editar** al lado del campo **Para** para abrir el cuadro de diálogo desplegable **Asignar dirección de correo electrónico**. Entonces establezca los campos siguientes:

- En el campo **Propósito**, seleccione los propósitos deseados. Solo se utilizarán las direcciones de correo electrónico de los fines seleccionados de los contactos de la parte descubierta.
- Establezca la opción **Contacto principal** a **Sí** para usar una dirección de correo electrónico que esté configurada para la parte descubierta como la dirección de correo electrónico principal.

> [!NOTE]
> Si se seleccionan propósitos en el campo **Propósito** y la opción **Contacto primario** está configurada en **Sí** al mismo tiempo, todos los correos electrónicos que satisfagan al menos un criterio configurado se utilizarán en tiempo de ejecución.

### <a name="configuration-email"></a>Correo electrónico de configuración

Seleccione **Correo electrónico de configuración** como tipo de dirección de correo electrónico si la configuración que utiliza tiene un nodo en las fuentes de datos que devuelve una sola dirección de correo electrónico o varias direcciones de correo electrónico separadas por punto y coma (;). Puede usar orígenes de datos y [funciones](er-formula-language.md#Functions) en el diseñador de fórmulas para obtener una dirección de correo electrónico con el formato correcto o direcciones de correo electrónico con el formato correcto que estén separadas por punto y coma. Por ejemplo, si usa la configuración **Transferencia de crédito ISO 20022**, el nodo que representa la dirección de correo electrónico principal de un proveedor de los detalles de contacto del proveedor al que se debe enviar la carta de presentación es `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.

[![Configurar un origen de dirección de correo electrónico.](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)

## <a name="group-format-components"></a><a id="grouping"></a>Componentes de formato de grupo

Para agrupar componentes de formato, en la página **Destino de informes electrónicos**, en la ficha desplegable **Destino del archivo**, seleccione los componentes en la cuadrícula y luego seleccione **Grupo**.

**Correo** es el único destino configurado previamente que todavía está disponible para los componentes seleccionados. No hay disponibles otros destinos configurados previamente, porque se consideran no compatibles con un grupo de componentes. Se le notificará sobre estos cambios según corresponda.

El registro que agregó anteriormente se considera el encabezado del grupo que se crea. Este registro de encabezado contiene la configuración de destino de correo electrónico para el grupo. Otros registros son miembros del grupo que usarán la configuración de destino de correo electrónico del registro de encabezado del grupo.

Para desagrupar componentes de formato, en la ficha desplegable **Destino del archivo**, seleccione un registro que pertenezca al grupo y luego seleccione **Desagrupar**.

- Si selecciona un registro de encabezado, se desagrupará todo el grupo.
- Si selecciona un registro de miembro y es el último registro de miembro de un grupo, se desagrupará todo el grupo.
- Si selecciona un registro de miembro que no es el último registro de miembro de un grupo, ese registro se excluirá del grupo actual.

La siguiente ilustración muestra la estructura de un formato ER que se configuró para producir un archivo de salida comprimido que contiene una nota de carta de cobro y las facturas de cliente correspondientes en formato PDF.

[![Estructura de un formato ER que genera documentos salientes.](./media/ER_Destinations-Email-Grouping1.png)](./media/ER_Destinations-Email-Grouping1.png)

La siguiente ilustración muestra el proceso, como se describe en este artículo, de agrupar componentes individuales y habilitar el destino **Correo** para el nuevo grupo, de modo que se envíe una nota de carta de cobro junto con las facturas de cliente correspondientes como archivos adjuntos de correo electrónico.

[![Agrupar componentes individuales y habilitar el destino del correo electrónico.](./media/ER_Destinations-Email-Grouping2.gif)](./media/ER_Destinations-Email-Grouping2.gif)

## <a name="additional-resources"></a>Recursos adicionales

- [Información general de los informes electrónicos (ER)](general-electronic-reporting.md)
- [Destinos de informes electrónicos (ER)](electronic-reporting-destinations.md)
- [Diseñador de fórmulas en los informes electrónicos (ER)](general-electronic-reporting-formula-designer.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
