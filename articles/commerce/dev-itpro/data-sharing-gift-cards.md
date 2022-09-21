---
title: Uso compartido de datos entre empresas para tarjetas regalo
description: En este artículo se describe cómo configurar Microsoft Dynamics 365 Commerce para utilizar la funcionalidad de compartición de datos de Dynamics 365 Finance en todas las áreas de datos para sincronizar los datos de las tarjetas regalo.
author: BrianShook
ms.date: 08/26/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2022-06-20
ms.openlocfilehash: bc0df6c4aac72907e8523069e3f1ae100780dc3c
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473941"
---
# <a name="cross-company-data-sharing-for-gift-cards"></a>Uso compartido de datos entre empresas para tarjetas regalo

[!include [banner](../includes/banner.md)]

En este artículo se describe cómo configurar Microsoft Dynamics 365 Commerce para utilizar la funcionalidad de compartición de datos de Dynamics 365 Finance para sincronizar los datos de las tarjetas regalo. La funcionalidad de uso compartido de registros de datos se puede utilizar para compartir datos entre empresas entre dos áreas de datos. De esta forma, la tabla interna de regalos de Commerce puede compartir datos entre dos entidades de la empresa. Para obtener más información sobre el uso compartido de datos entre empresas de Dynamics 365 Finance, consulte [Intercambio de datos entre empresas](/dynamics365/fin-ops-core/dev-itpro/sysadmin/cross-company-data-sharing).

## <a name="key-terms"></a>Términos clave

| Condición | Description |
|---|---|
| Empresa | La entidad jurídica en el entorno de Dynamics 365 Finance. |
| Tarjeta regalo | El producto interno de tarjetas de regalo de Dynamics 365 Commerce. |

## <a name="prerequisites"></a>Requisitos previos

Los usuarios deben configurar su entorno para la compartición de datos entre empresas como se describe en [Uso compartido de datos entre empresas](/dynamics365/fin-ops-core/dev-itpro/sysadmin/cross-company-data-sharing).

**RetailGiftCardTable** debe tener el campo **DataSharingType** ajustado en **Duplicar** para activar el reparto de registros duplicados (DRS) para la tabla de tarjetas de regalo. Para obtener más información, consulte [Intercambio de datos entre empresas para desarrolladores](/dynamics365/fin-ops-core/dev-itpro/sysadmin/drs-srs-dev).

## <a name="configure-cross-company-data-sharing-for-gift-cards"></a>Configurar el intercambio de datos entre empresas para las tarjetas regalo

Para configurar el intercambio de datos entre empresas para las tarjetas regalo, siga estos pasos.

1. En Commerce headquarters, vaya a **Administración del sistema \> Configurar \> Configurar uso compartido de datos entre empresas**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar un registro de intercambio de datos.
1. En el campo **Nombre** introduzca un nombre para el registro de intercambio de datos (por ejemplo, **Tarjetas regalo**).
1. En la sección **Tablas y campos para compartir**, seleccione **Agregar**.
1. En el cuadro de diálogo **Compartir nueva tabla**, en el campo **Nombre de la tabla**, introduzca **RETAILGIFTCARDTABLE** (la tabla para tarjetas regalo). El campo **Etiqueta de la tabla** se deba ajustar automáticamente en **Tabla de tarjetas regalo**.
1. Asegúrese de que se hayan seleccionado las casillas de verificación **Guardar datos por empresa**, **Tiene un índice único** y **No compartido aún**. La selección de estas casillas de verificación desencadena validaciones relacionadas con la funcionalidad de intercambio de datos.
1. Seleccione **Agregar tabla**. El registro **Tabla de tarjetas regalo (RetailGiftCardTable)** ahora debería aparecer en **Tablas y campos para compartir**. Seleccione el símbolo de intercalación (^) para ver todos los campos de la tabla que se asocian automáticamente con la tabla para compartir.
1. En la sección **Empresas que comparten los registros en estas tablas**, seleccione **Agregar** para agregar una empresa con la que compartir datos.
1. En la fila bajo **Empresa**, seleccione una empresa en la lista desplegable.
1. En el campo **Nombre**, introduzca el nombre de la empresa.
1. Repita los pasos del 8 al 10 para agregar más filas de empresa.
1. Cuando haya terminado de agregar filas de empresas, en el Panel de acciones, seleccione **Habilitar**.
1. Recibe un mensaje de advertencia que dice: "Se recomienda realizar esta acción únicamente en horas no comerciales. Las operaciones de transacción simultáneas para las tablas en la directiva no se realizarán correctamente. ¿Desea continuar?" Seleccione **Sí** para aceptar.
1. Recibe un mensaje de advertencia que dice: "¿Desea copiar ahora todos los datos existentes en todas las empresas compartidas?" Seleccione **Sí** para aceptar.

Después de aceptar ambos mensajes, las tablas comenzarán a copiar datos en las empresas configuradas. Los saldos que se produzcan en la tarjeta regalo de una empresa serán visibles para la otra empresa.

## <a name="additional-resources"></a>Recursos adicionales

[Preguntas frecuentes sobre pagos](payments-retail.md)

[Módulo de finalización de compra](../add-checkout-module.md)

[Módulo de pago](../payment-module.md)
