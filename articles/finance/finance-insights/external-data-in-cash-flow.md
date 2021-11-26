---
title: Usar datos externos en previsiones de flujo de efectivo
description: Este tema describe los pasos de configuración que debe completar para que los datos externos se puedan introducir o importar en los pronósticos de flujo de efectivo.
author: rcarlson
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: dbfa04228cf63c0874a7d69af4e2b932544c0d7f
ms.sourcegitcommit: 03fa7556840aa59f825697f6f9edeb58ea673fca
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "7753011"
---
# <a name="use-external-data-in-cash-flow-forecasts"></a>Usar datos externos en previsiones de flujo de efectivo

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Los datos externos se pueden introducir o importar en forma de pronósticos de flujo de efectivo. Este tema describe los pasos de configuración que son específicos para el uso de datos externos y que permiten que los datos externos se incluyan en una previsión de flujo de efectivo.

## <a name="external-data-setup"></a>Configuración de datos externos

Utilice la pestaña **Fuente externa** de la página **Configuración de pronóstico de flujo de efectivo** (**Gestión de efectivo y banco \> Previsión de flujo de efectivo \> Configuración de la previsión de flujo de efectivo**) para introducir configuraciones que admitan el uso de datos externos en las previsiones de flujo de efectivo.

Los datos externos se pueden introducir o importar en forma de pronósticos de flujo de efectivo. Antes de introducir o importar datos externos, debe configurar orígenes externos. En la pestaña **Origen externo**, configure categorías de flujo de efectivo externas. Una categoría puede ser **Saliente** o **Entrante**. **Liquidez** debe seleccionarse como tipo de registro. En la cuadrícula **Configuración de entidad legal**, seleccione las entidades legales y las cuentas principales correspondientes a las que se aplican las categorías de flujo de efectivo externas.

Para obtener más información sobre cómo configurar previsiones de flujo de efectivo, consulte [Previsiones de flujo de efectivo](../cash-bank-management/cash-flow-forecasting.md).

## <a name="enter-external-data"></a>Especificar datos externos

Para introducir y modificar datos externos para pronósticos de flujo de efectivo, puede usar la experiencia **Abrir en Excel**. Seleccione el botón **Datos externos** en la página **Configuración de la previsión de flujo de efectivo** y luego seleccione **Agregar datos externos** o **Editar datos externos existentes**. Cuando se abre el archivo de Microsoft Excel, puede introducir información en los siguientes campos:

- **Id. de entrada** (único)
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

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
