---
title: Modelo de valor de activos fijos y fusión del libro de amortización
description: 'En versiones anteriores, había dos conceptos de la evaluación para activos fijos: modelos de valor y libros de depreciación. En el lanzamiento de Microsoft Dynamics 365 for Operations (1611), la función del modelo de valor y la del libro de amortización se han combinado en un solo concepto que se conoce como libro.'
author: moaamer
ms.date: 10/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 221564
ms.assetid: 7c68eb7c-8b1a-4dd9-afb8-04b4040e305e
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f4f06b7916fb2eeed802b2dce95edfce448dcd97
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880856"
---
# <a name="fixed-asset-value-model-and-depreciation-book-merge"></a>Modelo de valor de activos fijos y fusión del libro de amortización

[!include [banner](../includes/banner.md)]

Este artículo describe la funcionalidad del libreo actual en Activos fijos. Esta función se basa en la función del modelo de valor que estaba disponible en versiones anteriores, pero también incluye todas las funciones que se proporcionaron anteriormente únicamente en libros de depreciación.

La funcionalidad del libro le permite utilizar un único conjunto de páginas, consultas e informes para todos los procesos de activos fijos de su organización. Las tablas de este artículo describen la función anterior para los libros de amortización y los modelos de valor, así como la actual función para los libros.

## <a name="setup"></a>Configurar
De forma predeterminada, los libros se registran tanto en la contabilidad general (GL) como en el subdiario de activo fijo. Los libros tienen una nueva opción de **Registrar en la contabilidad general** que permite deshabilitar la publicación en la contabilidad general y registrar solo el subdiario de activo fijo. Esta función es similar al comportamiento anterior de registro de los libros de amortización. La configuración de los nombres de diario tiene una nueva capa de registro que se denomina Ninguno. Esta capa de registro se ha añadido específicamente para las transacciones de activos fijos. Para registrar transacciones de libros que no se registran en la contabilidad general, debe utilizar un nombre de diario que tiene la capa de registro establecida en **Ninguno**.


| &nbsp;                                           | Libro amortización               | Modelo de valor                     | Libro (Nuevo)                                              |
|--------------------------------------------------|---------------------------------|---------------------------------|---------------------------------------------------------|
| Registrar en el libro mayor                                   | Nunca                           | Siempre                          | Opción para registrar en el libro mayor                                |
| Capas de registro                                   | No aplicable                  | 3: Actual, Operaciones e Impuestos | 11: Actual, Operaciones, Impuesto, 7 niveles personalizados, y Ninguno |
| Nombres de diarios                                    | Nombres del diario del libro amortización | Contabilidad general: nombres de diarios              | Contabilidad general: nombres de diarios                                      |
| Libros derivados                                    | No permitido                     | Permitida                         | Permitida                                                 |
| Anulación del perfil de depreciación al nivel del activo | Permitido                         | No permitido                     | Permitido                                                 |

## <a name="processes"></a>Procesos
Los procesos ahora usan una página común. Se permiten algunos procesos si la opción **Registrar en la contabilidad general** se ha establecido a **No** en la configuración de libros.

| &nbsp;                                           | Libro amortización               | Modelo de valor                     | Libro (Nuevo)                                              |
|--------------------------------|---------------------------|---------------------|------------------------------------------|
| Entrada de transacción              | Diario del libro amortización | Diario de activos fijos | Diario de activos fijos                      |
| Depreciación de bonificación             | Permitido                   | No permitido         | Permitido                                  |
| Eliminar transacciones históricas | Permitido                   | No permitido         | Permitido, salvo que esté registrando en la contabilidad general |
| Actualización masiva                    | Permitido                   | No permitido         | Permitido, salvo que esté registrando en la contabilidad general |

## <a name="inquiries-and-reports"></a>Consultas e informes
Las consultas e informes admiten todos los libros. Los informes que no se incluyen en la tabla siguiente admitían anteriormente los libros de amortización y los modelos de valor, y ahora seguirán apoyando todos los tipos de libro. El campo **Capa de registro** también se ha agregado a los informes, para que pueda identificar fácilmente los registros de transacción.

| &nbsp;                                           | Libro amortización               | Modelo de valor                     | Libro (Nuevo)                                              |
|---------------------------------------|--------------------------------|--------------------------|--------------------------|
| Consultas                             | Transacciones del libro amortización | Transacciones de activos fijos | Transacciones de activos fijos |
| Extracto de activos fijos                 | No permitido                    | Permitido                  | Permitido                  |
| Base de activo fijo                     | Permitido                        | No permitido              | Permitido                  |
| Aplicabilidad de la mitad del trimestre del activo fijo | Permitido                        | No permitido              | Permitido                  |

## <a name="upgrade"></a>Actualizar
El proceso de actualización moverá la configuración existente y todas sus transacciones existentes a la estructura del nuevo libro. Los modelos de valor se mantendrán como hasta ahora, como un libro que registra en la contabilidad general. Sin embargo, los libros de amortización se moverán a un libro que tiene la opción **Registrar en la contabilidad general** establecida en **No**. Los nombres del diario del libro de amortización se moverán a un nombre de diario de la contabilidad general que tenga la capa de registro establecida en **Ninguno**.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
