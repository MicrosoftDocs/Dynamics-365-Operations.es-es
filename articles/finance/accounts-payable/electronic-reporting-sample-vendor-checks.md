---
title: Cheques de proveedor de ejemplo para informes electrónicos
description: Este tema proporciona información general sobre cómo usar los formatos de cheque de muestra de los informes electrónicos.
author: ShylaThompson
ms.date: 06/14/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: a405fee368bb1789addbdf4316a007e85616d98d
ms.sourcegitcommit: 7d0cfb359a4abc7392ddb3f0b3e9539c40b7204d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2021
ms.locfileid: "5897097"
---
# <a name="electronic-reporting-sample-vendor-checks"></a>Cheques de proveedor de ejemplo para informes electrónicos

[!include [banner](../includes/banner.md)]

Puede usar informes electrónicos (ER) para dar formato a los cheques de proveedores. Muchos formatos de cheque específicos de bancos y proveedores están disponibles en el mercado. Los formatos de cheque de ejemplo se han incluido en el modelo de cheques de pago en el repositorio de la herramienta de ER. Estos cheques de ejemplo se etiquetan como **Cheque en el medio (EE. UU.)** y **Cheque sobre recibo inferior (EE. UU.)**.

## <a name="what-check-formats-are-currently-supported"></a>¿Qué formatos de cheque se admiten actualmente?

Debe ir siempre a la biblioteca de activos compartidos de Microsoft Dynamics Lifecycle Services (LCS) y ver la lista actual de archivos disponibles que tienen un tipo de activo de **Configuración de GER**. La siguiente sección, “¿Qué tengo que configurar? ”, incluye un vínculo al tema que explica cómo crear un repositorio de LCS para que pueda revisar las configuraciones disponibles e importar las configuraciones seleccionadas.

Microsoft Dynamics 365 Finance también incluye un formato de muestra donde el cheque está en la parte superior, seguido de dos secciones de la remesa. También incluye un formato de muestra donde el cheque está en el medio, entre dos secciones de la remesa. Estos formatos de ejemplo se corresponden con los formatos de cheques empresariales Deluxe.

## <a name="what-do-i-have-to-set-up"></a>¿Qué tengo que configurar?

- Para poder crear imprimir cheques utilizando ER, antes debe activar al menos una configuración de cheque de crédito en las configuraciones de ER. Para obtener más información, consulte [Descargar configuraciones de informes electrónicos de Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).
- Cuando configure cheques de efectivo y de gestión bancaria para la cuenta bancaria, seleccione la casilla de verificación **Formato de exportación electrónica genérica** y seleccione el formato de cheque apropiado como configuración del formato de exportación.
- También debe especificar el número de líneas de albaranes que se imprimirán en la remesa. Asegúrese de incluir las filas de encabezado cuando se calcula este número. Para los dos formatos de cheque de ejemplo, el número de líneas de albarán recomendado es 17. Sin embargo, este número variará, en función de sus existencia de cheques y los controladores de la impresora.
- Es recomendable que imprima un cheque de prueba para validar el diseño de cheques. Para imprimir un cheque de prueba, seleccione la opción **Imprimir prueba**. Los formatos de cheque de prueba funcionan mejor cuando los **Márgenes** se establecen en **Ninguno** en las propiedades de impresora avanzadas para Microsoft Excel. Una vez que se haya generado el cheque de prueba, habilite la edición de salida de Excel y configure el diseño de página para definir todos los márgenes en **0** (cero). Compare la copia de prueba de los cheques con las existencias de cheques y ajuste los valores hasta que se quede satisfecho con la alineación.
- Al generar los pagos para la cuenta bancaria configurada en el diario de pagos, los cheques se imprimirán con el formato especificado.

Para obtener más información, consulte [Modificar un formato de informe electrónico](../../fin-ops-core/dev-itpro/analytics/modify-electronic-reporting-format-reapply-excel-template.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]