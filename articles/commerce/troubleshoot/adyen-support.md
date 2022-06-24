---
title: Solucionar problemas del Conector de pago de Dynamics 365 para problemas de Adyen
description: Este artículo proporciona una guía para la resolución de problemas que puede ayudarle a obtener soporte cuando tenga problemas con el Conector de pago de Microsoft Dynamics 365 para Adyen.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 6219747e794865e602c78d7ca519340046d5effc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896884"
---
# <a name="troubleshoot-dynamics-365-payment-connector-for-adyen-issues"></a>Solucionar problemas del Conector de pago de Dynamics 365 para problemas de Adyen

[!include [banner](../../includes/banner.md)]

Este artículo proporciona una guía para la resolución de problemas que puede ayudarle a obtener soporte cuando tenga problemas con el Conector de pago de Microsoft Dynamics 365 para Adyen.

## <a name="description"></a>Descripción

Tiene problemas con el Conector de pago de Dynamics 365 para Adyen en las siguientes áreas y necesita soporte del equipo de Adyen:

- Configuración de Punto de venta (POS), Punto de venta moderno (MPOS), centro de llamadas o Dynamics 365 Commerce
- El número de referencia del proveedor de servicios de pago (PSP) de Adyen (por ejemplo, si tiene preguntas sobre rechazos, incluidos rechazos de introducción manual de claves \[ MKE\])
- Todo lo que no funcione en entornos comerciales de prueba o en vivo

## <a name="resolution"></a>Resolución

Utilice la siguiente plantilla de correo electrónico para iniciar el proceso de soporte con el equipo de Adyen. Para acelerar la resolución de problemas, asegúrese de que el correo electrónico contenga todos los detalles requeridos.

| Campo        | Valor |
|--------------|-------|
| Para           | `support@adyen.com` |
| CC           | |
| Línea de asunto | Solicitud de soporte técnico de Microsoft Dynamics |
| Cuerpo         | <p>Hola, soporte técnico:</p><p>Proporcionen soporte técnico para el siguiente problema:</p><ul><li>Cuenta de comerciante</li><li>Entorno (prueba/producción)</li><li>Canal (PDV/centro de llamadas/comercio electrónico de Commerce)</li><li>Número de referencia de PSP, si el problema involucró una transacción específica (puede encontrar el número de referencia de PSP en el recibo, en el Área de clientes de Adyen o en el menú de transacciones en el terminal PDV).</li><li>Captura de pantalla o foto del mensaje de error, si corresponde</li><li>Registros del Visor de eventos (en formato .txt)</li><li>Descripción del problema y pasos de solución de problemas que ha intentado</li></ul> |

## <a name="additional-resources"></a>Recursos adicionales

[Aceptar pagos con el conector Adyen para Dynamics 365 Commerce](https://www.adyen.com/partners/dynamics-365-commerce)

[Conector de pago de Dynamics 365 para Adyen](../dev-itpro/adyen-connector.md)

[Configurar el conector de pago de Adyen para Dynamics 365](https://docs.adyen.com/plugins/microsoft-dynamics)
