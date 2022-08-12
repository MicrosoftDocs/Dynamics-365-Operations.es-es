---
title: Libro mayor integrado
description: Este artículo describe la integración de datos del libro mayor entre finanzas y operaciones y otras aplicaciones de Dynamics 365 mediante Dataverse.
author: tonyafehr
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: tfehr
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: e5598295a25e31b33cd8b4d7ce3250a982ab4e87
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2022
ms.locfileid: "9112252"
---
# <a name="integrated-ledger"></a>Libro mayor integrado

[!include [banner](../../includes/banner.md)]



En una aplicación empresarial, los datos de contabilidad definen la configuración básica acerca de cómo una empresa hace negocios. Por ejemplo, los datos de contabilidad describen el ejercicio que la empresa sigue, las divisas con las que hace transacciones y las cuentas que utiliza. Este artículo describe la integración de estos datos financieros básicos.

## <a name="templates"></a>Plantillas

Los datos de contabilidad incluyen una colección de mapas de tabla financiera básicos que funcionan conjuntamente durante la interacción de los datos, como se muestra en la tabla siguiente.

Aplicaciones de finanzas y operaciones | Aplicaciones Customer Engagement     | Descripción
---------------------------------|----------------------------------|------------
[Tipos de cambio CDS](mapping-reference.md#123) | msdyn_currencyexchangerates |
[Plan de cuentas](mapping-reference.md#121) | msdyn_chartofaccountses |
[Divisas](mapping-reference.md#218) | transactioncurrencies |
[Par de divisas del tipo de cambio](mapping-reference.md#122) | msdyn_currencyexchangeratepairs |
[Tipo de cambio](mapping-reference.md#129) | msdyn_exchangeratetypes |
[Formato de dimensión financiera](mapping-reference.md#130) | msdyn_financialdimensionformats |
[Dimensiones financieras](mapping-reference.md#128) | msdyn_dimensionattributes |
[Entidad de integración de calendario fiscal](mapping-reference.md#132) | msdyn_fiscalcalendars |
[Período de calendario fiscal](mapping-reference.md#131) | msdyn_fiscalcalendarperiods |
[Entidad de integración de año de calendario fiscal](mapping-reference.md#133) | msdyn_fiscalcalendaryears |
[Contabilidad](mapping-reference.md#148) | msdyn_ledgers |
[Cuenta principal](mapping-reference.md#152) | msdyn_mainaccounts |
[Categorías de cuenta principal](mapping-reference.md#151) | msdyn_mainaccountcategories |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

