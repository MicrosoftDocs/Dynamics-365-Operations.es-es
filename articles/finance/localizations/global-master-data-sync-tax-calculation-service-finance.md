---
title: Sincronizar la configuración de impuestos del servicio de cálculo de impuestos a Dynamics 365 Finance
description: Este artículo explica cómo sincronizar los datos maestros de configuración de impuestos del servicio de cálculo de impuestos a Microsoft Dynamics 365 Finance.
author: EricWangChen
ms.date: 01/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.21
ms.custom: intro-internal
ms.search.form: TaxIntegration, TaxServiceParameters
ms.openlocfilehash: 315f2b27a64906ca0fc404d704d0b170dbfa48c5
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283865"
---
# <a name="sync-the-tax-setup-from-the-tax-calculation-service-to-dynamics-365-finance"></a>Sincronizar la configuración de impuestos del servicio de cálculo de impuestos a Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

Este artículo explica cómo sincronizar los datos maestros de configuración de impuestos del servicio de cálculo de impuestos a Microsoft Dynamics 365 Finance.

Después de completar los pasos de configuración requeridos en [Introducción al cálculo de impuestos](global-get-started-with-tax-calculation-service.md), los siguientes datos de configuración de impuestos se sincronizan automáticamente desde el servicio de cálculo de impuestos a Finance.

## <a name="sales-tax-code"></a>Código de impuestos

| Servicio de cálculo de impuestos           | Finance                             |
| --------------------------------- | ----------------------------------- |
| Código de impuestos                          | Código de impuestos                      |
| Description                       | Name                                |
| Entrada de usuario                        | Período de liquidación                   |
| Entrada de usuario                        | Grupo de registro                |
| Entrada de usuario                        | Divisa de impuestos                  |
| Se configura un tipo impositivo negativo | Permitir porcentaje de impuestos negativo |

## <a name="tax-value"></a>Valor de impuestos

| Servicio de cálculo de impuestos | Finance                   |
| ----------------------- | ------------------------- |
| Fecha de transacción desde   | Fecha de inicio                 |
| Fecha de transacción hasta     | Fecha de finalización                   |
| Importe mínimo          | Límite mínimo             |
| Importe máximo          | Límite máximo             |
| Índice de impuestos                | Valor                     |
| Tipo no deducible     | Porcentaje no deducible |

## <a name="tax-limits"></a>Límites de impuestos

| Servicio de cálculo de impuestos | Finance           |
| ----------------------- | ----------------- |
| Fecha de transacción desde   | Fecha de inicio         |
| Fecha de transacción hasta     | Fecha de finalización           |
| Importe mínimo del impuesto      | Impuesto mínimo |
| Importe máximo del impuesto      | Impuesto máximo |

## <a name="sales-tax-group"></a>Grupo de impuestos

| Servicio de cálculo de impuestos                         | Finance                                    |
| ----------------------------------------------- | ------------------------------------------ |
| Grupo de impuestos                                       | Grupo de impuestos                            |
| Códigos de impuestos en este grupo de impuestos                  | Códigos de impuestos de ventas en este grupo de impuestos de ventas |
| El código de impuestos está marcado como **Está exento**         | Exento                                     |
| El código de impuestos está marcado como **Está exento**         | Código de exención                                |
| El código de impuestos está marcado como **Es cargo invertido**. | Cargo invertido                             |
| El código de impuestos está marcado como **Es IVA de importación**.        | IVA de importación                                    |

## <a name="item-sales-tax-group"></a>Grupo de impuestos de artículos

| Servicio de cálculo de impuestos             | Finance                                         |
| ----------------------------------- | ----------------------------------------------- |
| Grupo de impuestos de artículos                      | Grupo de impuestos de artículos                            |
| Códigos de impuestos en este grupo de impuestos de árticulo | Códigos de impuestos de ventas en este grupo de impuestos de ventas de artículos |

Una vez completada la sincronización, continúe manteniendo los parámetros restantes en Finance para publicación e informes.

> [!NOTE]
> No se admite la sincronización de la configuración de impuestos de Finance con el servicio de cálculo de impuestos. Para un entorno de Finance existente, primero cree la configuración de impuestos en el servicio de cálculo de impuestos. Luego, sincronice los datos de configuración con el entorno de Finance.
