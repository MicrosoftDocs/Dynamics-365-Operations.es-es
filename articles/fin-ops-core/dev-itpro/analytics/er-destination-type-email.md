---
title: Tipo de destino de ER de correo electrónico
description: Este tema proporciona información sobre cómo configurar un destino de correo electrónico para cada componente FOLDER o FILE de un formato de informe electrónico (ER) que está configurado para generar documentos salientes.
author: NickSelin
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 086114d6a8d425ca01521d9607e4a70ec5aa766b
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019986"
---
# <a name="EmailDestinationType">Destino de correo electrónico</a>

[!include [banner](../includes/banner.md)]

Puede configurar un destino de correo electrónico para cada componente FOLDER o FILE de un formato de informe electrónico (ER) que está configurado para generar documentos salientes. Según la configuración de destino, un documento generado se entrega como archivo adjunto de un correo electrónico.

Establezca **Habilitado** en **Sí** para enviar un archivo de salida por correo electrónico. Después de que se haya habilitado esta opción, puede especificar los destinatarios de correo electrónico y editar el asunto y el cuerpo del mensaje de correo electrónico. Puede configurar textos constantes para el asunto y el cuerpo de correo electrónico, o bien usar las [fórmulas](er-formula-language.md) de ER dinámicamente para crear textos de correo electrónico. 

Puede configurar direcciones de correo electrónico para el ER de dos maneras. La configuración se puede completar de la misma manera que la función de administración de impresión la completa, o puede resolver una dirección de correo electrónico utilizando una referencia directa a la configuración de ER a través de una fórmula.

[![Habilitar destino de correo electrónico](./media/ER_Destinations-EnableSingleDestination.png)](./media/ER_Destinations-EnableSingleDestination.png)

## <a name="email-address-types"></a>Tipos de direcciones de correo electrónico

Al seleccionar **Editar** en los campos **Para** o **Cc**, se muestra el cuadro de diálogo **Correo electrónico para**. A continuación puede seleccionar el tipo de dirección de correo electrónico que se usará. Los tipos de correo electrónico **Correo electrónico de configuración** y **Gestión de impresión** son compatibles actualmente.

[![Seleccionar el tipo de correo electrónico](./media/ER_Destinations-EmailSelectAddressType.png)](./media/ER_Destinations-EmailSelectAddressType.png)

### <a name="print-management"></a>Gestión de impresión

Si selecciona el tipo de correo electrónico **Administración de impresión**, puede especificar direcciones de correo electrónico fijas en el campo **Para**. 

[![Configurar direcciones de correo electrónico fijas](./media/ER_Destinations-EmailFixedAddress.png)](./media/ER_Destinations-EmailFixedAddress.png)

Para utilizar direcciones de correo electrónico que no son fijas, debe seleccionar el tipo de origen de correo electrónico para un destino de archivo. Se admiten los siguientes valores: **Cliente**, **Proveedor**, **Cliente potencial**, **Contacto**, **Competidor**, **Trabajador**, **Candidato**, **Proveedor potencial** y **Proveedor no permitido**. Tras seleccionar un tipo de origen de correo electrónico, use el botón junto al campo **Cuenta de origen de correo electrónico** para abrir el formulario **Diseñador de fórmula**. Puede usar este formulario para adjuntar una fórmula que devuelve en tiempo de ejecución la **cuenta de la parte** del tipo de origen seleccionado desde el documento procesado hasta el destino del correo electrónico.

[![Configurar la cuenta de origen de correo electrónico](./media/ER_Destinations-EmailDefineAddressSource.png)](./media/ER_Destinations-EmailDefineAddressSource.png)

Las fórmulas son específicas de la configuración de ER. En la **Fórmula**, especifique una referencia específica de documento para un tipo de parte de cliente o proveedor. En lugar de escribir, puede encontrar el nodo del origen de datos que represente la cuenta del cliente o proveedor y, a continuación, seleccionar **Agregar origen de datos** para actualizar la fórmula. Por ejemplo, si utiliza la configuración **ISO 20022 Transferencia de crédito**, el nodo que representa una cuenta de proveedor es `'\$PaymentsForCoveringLetter'.Creditor.Identification.SourceID`.

Si introduce un valor de cadena, como `"DE-001"` y guarda una fórmula, se enviará un correo electrónico a la persona de contacto del proveedor, **DE-001**.


[![Página del diseñador de fórmulas de ER](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)](./media/ER_Destinations-EmailDefineAddressSourceFormula.png)

[![Configurar la cuenta de origen de correo electrónico](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)](./media/ER_Destinations-EmailDefineAddressSourceAttributes.png)



### <a name="configuration-email"></a>Correo electrónico de configuración

Use este tipo de correo electrónico si la configuración que utiliza tiene un nodo en los orígenes de datos que devuelve una **dirección de correo electrónico**. Puede usar orígenes de datos y funciones en el diseñador de fórmula para obtener una dirección de correo electrónico con formato correcto. Por ejemplo, si utiliza la configuración **ISO 20022 Transferencia de crédito**, el nodo que representa una dirección de correo electrónico de la persona de contacto del proveedor es `'$PaymentsForCoveringLetter'.Creditor.ContactDetails.Email`.

[![Configurar el origen de la dirección de correo electrónico](./media/ER_Destinations-EmailDefineAddressSource2.png)](./media/ER_Destinations-EmailDefineAddressSource2.png)

## <a name="additional-resources"></a>Recursos adicionales

- [Visión general de los informes electrónicos (ER)](general-electronic-reporting.md)
- [Destinos de informes electrónicos (ER)](electronic-reporting-destinations.md)
- [Diseñador de fórmulas en los informes electrónicos (ER)](general-electronic-reporting-formula-designer.md)
