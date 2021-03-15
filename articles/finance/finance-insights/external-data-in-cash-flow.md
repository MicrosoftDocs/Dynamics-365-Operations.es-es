---
title: Utilizar datos externos en las previsiones de flujo de efectivo (versión preliminar)
description: Este tema describe los pasos de configuración que debe completar para que los datos externos se puedan introducir o importar en los pronósticos de flujo de efectivo.
author: rcarlson
manager: AnnBe
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-06-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: ae0eba6d397725cf425d9781a597d904e1958d44
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009402"
---
# <a name="use-external-data-in-cash-flow-forecasts-preview"></a>Utilizar datos externos en las previsiones de flujo de efectivo (versión preliminar)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Los datos externos se pueden introducir o importar en forma de pronósticos de flujo de efectivo. Este tema describe los pasos de configuración que son específicos para el uso de datos externos y que permiten que los datos externos se incluyan en una previsión de flujo de efectivo.

## <a name="external-data-setup"></a>Configuración de datos externos

Utilice la pestaña **Fuente externa** de la página **Configuración de pronóstico de flujo de efectivo** (**Gestión de efectivo y banco \> Previsión de flujo de efectivo**) para introducir configuraciones que admitan el uso de datos externos en las previsiones de flujo de efectivo.

Para obtener más información sobre la configuración, consulte [Previsión de flujo de efectivo](https://docs.microsoft.com/dynamics365/finance/cash-bank-management/cash-flow-forecasting).

Para introducir datos externos para pronósticos de flujo de efectivo, puede usar la experiencia Abrir en Excel para introducir y modificar datos externos. Seleccione el botón **Datos externos** y luego seleccione **Agregar datos externos** o **Editar datos externos existentes**. Cuando se abre el archivo de Microsoft Excel, puede introducir información en los siguientes campos:

- **Id. de entrada**
- **Descripción** (opcional)
- **Nombre de fuente externa**: seleccione uno de los valores de la lista que definió al configurar Finance Insights.
- **Entidad jurídica**
- **Fecha**
- **Importe en divisa de transacción**
- **Código de divisa**
- **Dimensión predeterminada** (opcional)
- **Número del Documento** (opcional)
- **Número de cuenta** (opcional)
- **Nombre de cuenta** (opcional)

## <a name="importing-external-data-by-using-the-data-management-framework"></a>Importación de datos externos mediante el marco Administración de datos

Puede importar datos externos para las previsiones de flujo de efectivo mediante el espacio de trabajo **Administración de datos** y la entidad que se denomina **Entrada de fuente externa de pronóstico de flujo de efectivo**.

Además, si debe mover los datos de configuración de un entorno a otro, las siguientes entidades están disponibles para las tablas de configuración necesarias:

- Configuración de origen externo de previsión de flujo de efectivo
- Configuración de entidad jurídica de origen externo de previsión de flujo de efectivo

#### <a name="privacy-notice"></a>Aviso de privacidad
Las versiones preliminares (1) pueden utilizar menos privacidad y menos medidas de seguridad que el servicio Dynamics 365 Finance and Operations, (2) no están incluidas en el acuerdo de nivel de servicio para este servicio, (3) no deben utilizarse para procesar datos personales u otros datos que estén sujetos a requisitos de cumplimiento legal o reglamentario, y (4) disponen de soporte limitado.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]