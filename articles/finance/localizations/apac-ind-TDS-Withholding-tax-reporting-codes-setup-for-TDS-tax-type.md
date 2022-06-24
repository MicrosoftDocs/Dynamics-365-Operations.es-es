---
title: Configurar códigos de notificación de retención de impuestos para tipos de impuestos de TDS
description: Los códigos de notificación de retención de impuestos se utilizan para generar declaraciones del formulario 26Q y del formulario 27Q para impuestos deducidos en el origen (TDS). Este artículo explica cómo configurar los pasos de los códigos de notificación de retención de impuestos para que pueda configurar los códigos de notificación de TDS.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: bdd2e89d29807dc31d8f2d4684ee413470b1dbde
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907809"
---
# <a name="set-up-withholding-tax-reporting-codes-for-the-tds-tax-type"></a>Configurar códigos de notificación de retención de impuestos para tipos de impuestos de TDS

[!include [banner](../includes/banner.md)]

Los códigos de notificación de retención de impuestos se utilizan para generar declaraciones del formulario 26Q y del formulario 27Q para impuestos deducidos en el origen (TDS). Este artículo explica cómo configurar los pasos de los códigos de notificación de retención de impuestos para que pueda configurar los códigos de notificación de TDS.

1. Vaya a **Impuesto \> Configuración \> Retención de impuestos \> Códigos de notificación de retención de impuestos**.

    [![Página Códigos de notificación de retenciones de impuestos.](./media/apac-ind-TDS-16.png)](./media/apac-ind-TDS-16.png)

2. En el campo **Tipo de impuesto**, seleccione **TDS** para definir los códigos de notificación de retención de impuestos para el tipo de impuesto TDS.
3. En el campo **Componente de retención de impuestos**, seleccione el componente de TDS para el que está definiendo el código de notificación de retención de impuestos. El campo **Grupo de componentes de retención de impuestos** muestra el grupo de componentes de TDS que se definió para el componente de TDS que está definiendo.

    El campo **Código de sección** en la ficha desplegable **General** muestra el código de sección que se adjunta al grupo de componentes de TDS.

4. En la ficha desplegable **General**, en el campo **Código de notificación**, seleccione el código de notificación de TDS:

    - TDS
    - TCS
    - Suplemento
    - PE\_Cess
    - SHE\_Cess

5. Cierre la página.
