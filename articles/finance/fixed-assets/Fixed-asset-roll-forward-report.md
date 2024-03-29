---
title: Informe de puesta al día para activos fijos
description: Este artículo explica cómo utilizar el informe de puesta al día para activos fijos.
author: moaamer
ms.date: 01/08/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 23021
ms.assetid: d7e86f72-95db-4423-9b04-761e9536a959
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2017-12-20
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: a4d423b149957e624269231aede510190f0c14c7
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9068792"
---
# <a name="fixed-assets-roll-forward-report"></a>Informe de puesta al día para activos fijos

[!include [banner](../includes/banner.md)]

El informe de **Puesta al día para activos fijos** proporciona, en un formato de Microsoft Excel fácil de leer, los datos detallados del activo fijo que pueda necesitar para el cierre del período, los informes financieros y la notificación de impuestos. El informe incluye los saldos de inicio y fin para los activos fijos, junto con los movimientos de la evaluación para el período y cualquier adquisición y disposición de activos nueva que se hayan producido durante el período. Los datos se notifican para activos fijos individuales y los valores también se resumen para los grupos de activos fijos y la entidad jurídica.

El informe **de puesta al día para activos fijos** utiliza el marco de informes electrónicos (ER). Antes de poder ejecutar el informe, el modelo de activos fijos y las configuraciones de puesta al día para activos fijos deben importarse de Microsoft Dynamics Lifecycle Services (LCS). Para obtener más información, consulte [Descargar configuraciones de informes electrónicos de Lifecycle Services](/dynamics365/unified-operations/dev-itpro/analytics/download-electronic-reporting-configuration-lcs).

Este informe sólo está disponible en Microsoft Dynamics 365 Finance, Enterprise Edition 7.3, o como sustitución de Microsoft Dynamics 365 Finance, Enterprise Edition (julio de 2017). Deben aplicarse tres revisiones a los entornos que tienen la versión de julio de 2017:

- **KB 4041754:** la configuración de informes electrónicos (ER) no se puede descargar de LCS como no aplicable para la versión actual después de aplicar el paquete de actualización de la plataforma
- **KB 4056107:** actualización acumulativa de informe electrónica 5 (GER)
- **KB 4056353:** los informes de extractos y notas de activos fijos no cumplen los requisitos en GAAP e IFRS

En la tabla siguiente se describen los campos disponibles en el informe.


|                    Campo                    |                                                                                                                                Descripción                                                                                                                                |
|---------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|              Saldos: apertura              |                                                                                           El valor neto en los libros del activo fijo a partir de la fecha "de inicio" que se especifica en el informe.                                                                                           |
|              Saldos: cierre              |                                                                                            El valor neto en los libros del activo fijo a partir de la fecha "final" que se especifica en el informe.                                                                                            |
|         Adquisiciones: valor de apertura         |                                                 La suma de todas las transacciones de los tipos <strong>Adquisición</strong> y <strong>Ajuste de adquisición</strong> hasta la fecha "de inicio" que se especifica en el informe.                                                  |
|      Adquisiciones: adquisiciones del periodo      |                                                 La suma de todas las transacciones de los tipos <strong>Adquisición</strong> y <strong>Ajuste de adquisición</strong> que se registraron durante el intervalo de fechas del informe.                                                  |
|       Adquisiciones: cancelaciones del periodo        |                                                                        La suma de todas las inversiones de adquisición que se registraron que tenían una transacción de cancelación durante el intervalo de fechas del informe.                                                                        |
|         Adquisiciones: valor cierre         |                                                  La suma de todas las transacciones de los tipos <strong>Adquisición</strong> y <strong>Ajuste de adquisición</strong> hasta la fecha "final" que se especifica en el informe.                                                   |
|        Depreciaciones: valor de apertura         | La suma todas las transacciones de los tipos <strong>Depreciación</strong>, <strong>Ajuste de depreciación</strong>, <strong>Método de amortización por depreciación especial</strong> y <strong>Depreciación extraordinaria</strong> hasta la fecha "de inicio" que se especifica en el informe. |
|     Depreciaciones: depreciaciones del período     |                         La suma de todas las transacciones de los tipos <strong>Depreciación</strong>, <strong>Ajuste de depreciación</strong> y <strong>Depreciación extraordinaria</strong> que se registraron durante el intervalo de fechas del informe.                          |
| Depreciaciones: depreciaciones especiales del período |                                                              La suma de todas las transacciones del tipo <strong>Método de amortización por depreciación especial</strong> que se registraron durante el intervalo de fechas del informe.                                                               |
|       Depreciaciones: cancelaciones del periodo       |                                                                       La suma de todas las inversiones de depreciación que se registraron que tenían una transacción de cancelación durante el intervalo de fechas del informe.                                                                        |
|        Depreciaciones: valor de cierre         |  La suma todas las transacciones de los tipos <strong>Depreciación</strong>, <strong>Ajuste de depreciación</strong>, <strong>Método de amortización por depreciación especial</strong> y <strong>Depreciación extraordinaria</strong> hasta la fecha "final" que se especifica en el informe.  |
|    Revalorizaciones/Devaluaciones: valor de apertura     |                              La suma de todas las transacciones de los tipos <strong>Ajuste de revalorización</strong>, <strong>Ajuste de devaluación</strong> y <strong>Revaloración</strong> hasta la fecha "de inicio" que se especifica en el informe.                               |
|   Revalorizaciones/Devaluaciones: revaloraciones del periodo   |                                                                    La suma de todas las transacciones del tipo <strong>Ajuste de revalorización</strong> que se registraron durante el intervalo de fechas del informe.                                                                    |
|  Revalorizaciones/Devaluaciones: devaluaciones del periodo  |                                                                   La suma de todas las transacciones del tipo <strong>Ajuste de devaluación</strong> que se registraron durante el intervalo de fechas del informe.                                                                   |
| Revalorizaciones/Devaluaciones: revaloraciones del periodo  |                                                                        La suma de todas las transacciones del tipo <strong>Revaluación</strong> que se registraron durante el intervalo de fechas del informe.                                                                        |
|   Revalorizaciones/Devaluaciones: cancelaciones del periodo   |                                                           La suma de todas las inversiones de revalorización, devaluación y revaluación que se registraron que tenían una transacción de cancelación durante el intervalo de fechas del informe.                                                           |
|    Revalorizaciones/Devaluaciones: valor de cierre     |                               La suma de todas las transacciones de los tipos <strong>Ajuste de revalorización</strong>, <strong>Ajuste de devaluación</strong> y <strong>Revaloración</strong> hasta la fecha "final" que se especifica en el informe.                                |
|          Cancelaciones. fecha de cancelación           |                                                                                                                La fecha de cancelación del libro de activos fijos.                                                                                                                |
|    Cancelaciones: valor neto en los libros en la cancelación    |                                                                                                    El valor neto en los libros del libro de activos fijos en el momento de la cancelación.                                                                                                    |
|            Cancelaciones: valor de ventas            |                                                                                               El valor de ventas para el libro de activos fijos con una cancelación – transacción de venta.                                                                                                |
|           Cancelaciones: valor residual            |                                                                                               El valor residual para el libro de activos fijos con una cancelación – transacción residual.                                                                                               |
|           Cancelaciones: pérdidas/ganancias            |                                                                                 El valor de pérdidas o ganancias que se calcula como parte de la transacción de cancelación del libro de activos fijos.                                                                                 |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]

