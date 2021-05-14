---
title: Instrumentos de prueba de gestión de calidad
description: Este tema describe cómo crear instrumentos de prueba, de modo que se puedan usar para pruebas en pedidos de calidad en Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestInstrument
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dc09021f89a9064a3140a726fca74e3eceab13da
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956820"
---
# <a name="quality-management-test-instruments"></a>Instrumentos de prueba de gestión de calidad

[!include [banner](../includes/banner.md)]

Este tema describe cómo crear instrumentos de prueba, de modo que se puedan usar para pruebas en pedidos de calidad en Microsoft Dynamics 365 Supply Chain Management.

Use la página **Instrumentos de prueba** para definir y ver detalles sobre los dispositivos que se utilizan para realizar pruebas en pedidos de calidad. Los instrumentos de prueba son opcionales. Sin embargo, pueden ayudar a los trabajadores de calidad a saber qué dispositivo o herramienta deben usar para realizar una prueba específica.

## <a name="test-instrument-example"></a>Ejemplo de instrumento de prueba

Está realizando varias pruebas en componentes eléctricos. Algunas pruebas son para la salida de tensión de los componentes, una prueba es para su temperatura y una prueba es para su peso. Se utilizan diferentes herramientas, dispositivos o equipos para realizar cada prueba. Por ejemplo, se usa un medidor de tensión para medir la tensión, se usa un termómetro para medir la temperatura y se usa una balanza para medir el peso. Puede configurar cada uno de estos dispositivos como un instrumento de prueba e indicar la unidad de medida en la que se deben registrar los resultados de la prueba. Por ejemplo, los resultados del medidor de tensión se registran en voltios, los resultados del termómetro se registran en grados Fahrenheit o grados Celsius y los resultados de la báscula se registran en libras o kilogramos.

## <a name="create-a-test-instrument"></a>Crear un instrumento de prueba

1. Vaya a **Gestión del inventario \> Configurar \> Control de calidad \> Instrumentos de prueba**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula. Entonces establezca los siguientes campos para la fila nueva:

    - **Instrumento de prueba**: introduzca un id. o nombre único para el instrumento de pruebas.
    - **Descripción**: escriba una descripción detallada del instrumento de pruebas.
    - **Unidad**: seleccione la unidad en la que el instrumento mide los resultados. El campo **Precisión** se configura automáticamente, según la unidad que seleccione.

1. Cierre la página.

## <a name="additional-resources"></a>Recursos adicionales

- [Pruebas de gestión de calidad](quality-tests.md)
- [Grupos de pruebas de gestión de calidad](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
