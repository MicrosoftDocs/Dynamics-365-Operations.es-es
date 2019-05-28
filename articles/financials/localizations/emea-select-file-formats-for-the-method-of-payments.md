---
title: Formatos de archivo para métodos de pago
description: En este tema se describen los dos métodos para obtener los formatos de archivo que puede usar para los métodos de pago.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymMode, VendPaymMode
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 262514
ms.search.region: Belgium, France, Germany, Norway, Spain, Sweden, Switzerland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 21414624e1b0fe74a9a1c390f9c118892a480779
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1537796"
---
# <a name="file-formats-for-methods-of-payment"></a>Formatos de archivo para métodos de pago

[!include [banner](../includes/banner.md)]

En este tema se describen los dos métodos para obtener los formatos de archivo que puede usar para los métodos de pago.

Hay dos métodos que puede utilizar para obtener formatos de archivo para su uso con métodos de pago, formatos de archivo de informes electrónicos (ER) o formatos de archivo X++. Cuando configura un método de pago para un cliente o proveedor, indica qué formatos de archivo y estándares deben usarse para los pagos y cómo se procesarán los pagos. Puede seleccionar entre los siguientes tipos de formatos:

-   Exportar
-   Importar
-   Devolución
-   Envío

### <a name="method-1-electronic-reporting-file-formats"></a>Método 1: formatos de archivo de informes electrónicos

Para formatos de archivo basados en configuraciones de ER, debe importar las configuraciones de Lifecycle Services (LCS). Para obtener más información, consulte [Descargar configuraciones de informes electrónicos de Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md). Después de importar las configuraciones de informes para esos formatos de archivo, los formatos importados estarán disponibles para seleccionar en la página **Métodos de pago**. El proceso para importar y seleccionar formatos de archivo para Europa es similar al procedimiento para Japón. Para obtener más información, consulte [Habilitar el formato de archivo de pago de JBA](tasks/jba-payment-file-format.md)

### <a name="method-2-x-file-formats"></a>Método 2: formatos de archivo X++

Para seleccionar formatos de archivo basados en código X++, siga los pasos descritos a continuación.

1.  Vaya a la página **Métodos de pago**.
2.  En la ficha desplegable **Formatos de archivo**, haga clic en **Configuración**.
3.  Seleccione la ficha que corresponde al tipo de formato del archivo.
4.  Seleccione un formato de archivo en la lista **Disponible** y muévalo a la lista **Seleccionado** con el control de flecha.
5.  Cierre la página **Formatos de archivo para métodos de pago**.
6.  En la ficha desplegable **Formatos de archivo**, seleccione el formato de archivo que desea utilizar para el método de pago en el campo de formato de archivo apropiado. Las opciones generales de informes electrónicos deben establecerse en **No** para formatos de archivo X++.




