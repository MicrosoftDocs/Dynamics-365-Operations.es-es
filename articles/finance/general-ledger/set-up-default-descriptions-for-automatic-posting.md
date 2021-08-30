---
title: Configurar descripciones predeterminadas para registro automático
description: En este tema se explica cómo configurar el texto predeterminado que se usa para describir los asientos contables que se registran automáticamente en la contabilidad general. Puede configurar el texto de la descripción predeterminada mediante el texto de forma libre o seleccionando variables fijas.
author: aprilolson
ms.date: 07/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 222564
ms.assetid: ''
ms.search.region: global
ms.author: aolson
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 89ea19753abdc4e5d4219a123a832bb3606515a43b439d5f94a9619857b6c7d0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722704"
---
# <a name="set-up-default-descriptions-for-automatic-posting"></a>Configurar descripciones predeterminadas para registro automático

[!include [banner](../includes/banner.md)]

En este tema se explica cómo configurar el texto predeterminado que se usa para describir los asientos contables que se registran automáticamente en la contabilidad general. Puede configurar el texto de la descripción predeterminada mediante el texto de forma libre o seleccionando variables fijas.

> [!NOTE]
> Para algunos tipos de transacciones de algunos países o regiones, también puede incluir texto de los campos de la base de datos de Microsoft Dynamics AX relacionados con dichos tipos de transacción. Para obtener una lista de los tipos de transacciones, y los países y regiones, consulte la sección [Opcional: agregar otro texto a las descripciones predeterminadas](#optional-add-other-text-to-default-descriptions) más adelante en este tema.

## <a name="set-up-default-descriptions"></a>Configurar descripciones predeterminadas

1. Vaya a **Administración de la organización** \> **Configurar** \> **Descripciones predeterminadas**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el campo **Descripción**, seleccione el tipo de transacción para el que desea crear una descripción predeterminada.
4. En el campo **Idioma**, seleccione el idioma al que se aplica la descripción.
5. En el campo **Texto**, escriba la descripción predeterminada. Puede escribir texto en el campo o puede usar una o más de las siguientes variables de texto sin formato:

    - **%1**: agregar la fecha de la transacción.
    - **%2**: agregar un identificador que corresponde con el tipo de documento que se está registrando en la contabilidad general. Por ejemplo, para los tipos de transacción que están relacionadas con las facturas, la variable **%2** agrega el número de factura.
    - **%3**: agregar un identificador relacionado con el tipo de documento que se está registrando en la contabilidad general. Por ejemplo, para los tipos de transacción relacionados con las facturas, la variable **%3** agrega el número de cuenta del cliente.

## <a name="optional-add-other-text-to-default-descriptions"></a>Opcional: agregar otro texto a las descripciones predeterminadas

Para algunos tipos de transacciones de algunos países o regiones, las descripciones predeterminadas pueden incluir texto proveniente de campos de datos relacionados con dichos tipos de transacción. En las listas siguientes se muestran tipos de transacción y los países o regiones para los que está disponible esta opción.

**Tipos de transacciones**

Puede agregar otro texto a las descripciones predeterminadas para los tipos de transacción relacionados con los tipos de documentos siguientes:

- Facturas del cliente
- Notas de abono de cliente
- Pagos en efectivo de cliente
- Pagos de proveedores
- Pedidos de ventas
- Pedidos de compra
- Diarios de inventario
- Planificación maestra (MRP)
- Activos fijos

**Países y regiones**

Esta opción está disponible para los siguientes países y regiones:

- Brasil
- China
- República Checa
- Europa del Este
- Hungría
- India
- Japón
- Lituania
- Letonia
- Polonia
- Rusia

### <a name="add-text-to-default-descriptions"></a>Agregar otro texto a las descripciones predeterminadas

Tras completar los pasos de la sección [Configurar descripciones predeterminadas](#set-up-default-descriptions) anterior de este tema, siga estos pasos para agregar otro texto a las descripciones predeterminadas.

1. En la ficha desplegable **Parámetros**, seleccione **Agregar**.
2. En el campo **Tabla de referencia**, seleccione la tabla de base de datos desde la que desea agregar datos de parámetros a la descripción.
3. En el campo **Campo de referencia**, seleccione el campo desde el que desea agregar datos de parámetros a la descripción.
4. Repita los pasos del 1 al 3 para agregar más parámetros.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]