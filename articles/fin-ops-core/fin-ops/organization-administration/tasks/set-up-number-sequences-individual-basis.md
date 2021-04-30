---
title: Configurar secuencias numéricas de manera individual
description: Este tema explica cómo configurar secuencias numéricas de manera individual.
author: sericks007
ms.date: 08/16/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceDetails
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 83ebcf96aa6a5b5c757285be1c5602ac4e8f50fc
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890867"
---
# <a name="set-up-number-sequences-on-an-individual-basis"></a>Configurar secuencias numéricas de manera individual

[!include [banner](../../includes/banner.md)]

Este tema explica cómo configurar secuencias numéricas de manera individual. Las secuencias numéricas se usan para generar identificadores únicos y legibles para los registros de datos maestros y los registros de transacciones que los necesitan. El registro de datos maestros o de transacciones que necesita un identificador se denomina referencia. Para poder crear nuevos registros para una referencia, debe configurar una secuencia numérica y asociarla a la referencia. Puede configurar todas las secuencias de números necesarias al mismo tiempo usando el asistente **Configurar secuencias numéricas**, o bien crear o modificar secuencias numéricas individuales usando la página **Secuencias numéricas**.

1. Vaya al **panel de navegación > Módulos > Administración de la organización > Secuencias numéricas > Secuencias numéricas**.
2. Seleccione **Secuencia numérica**.
3. En el campo **Código de secuencia numérica,** escriba un valor.
4. En el campo **Nombre**, escriba un valor.
5. En la ficha desplegable **Parámetros del ámbito**, seleccione un ámbito para la secuencia numérica y seleccione los valores de ámbito en la lista desplegable. El ámbito define qué organizaciones usan la secuencia numérica. Además, las secuencias numéricas con un ámbito distinto de **Compartido** pueden contener segmentos que correspondan a su ámbito. Por ejemplo, una secuencia numérica con un ámbito de **Entidad jurídica** puede contener un segmento de entidad jurídica. Para obtener más información acerca de los alcances, consulte [Información general de secuencias numéricas](../number-sequence-overview.md). 
6. Expanda la sección **Segmentos**.
    - Defina el formato de la secuencia numérica agregando, quitando y reorganizando segmentos.  
    - Las secuencias numéricas de todos los ámbitos pueden contener *segmentos constantes* y *segmentos alfanuméricos*. Los segmentos constantes contienen un conjunto de caracteres alfanuméricos que no cambian. Use este tipo de segmento para agregar un guión u otros separadores entre segmentos de secuencias numéricas. Los segmentos alfanuméricos contienen una combinación de signos de número (#) y ampersands (&). Estos caracteres representan letras y números que aumentan siempre que se usa un número de la secuencia. Use un signo de número (#) para indicar el incremento de números y un ampersand (&) para incrementar un incremento de letras. Por ejemplo, el formato `#####_2014` crea la secuencia `00001_2014`, `00002_2014`, etc. Debe haber, como mínimo, un segmento alfanumérico. Los segmentos de ámbito, como empresa o entidad jurídica, no son obligatorios. Sin embargo, si no incluye segmentos de ámbito en el formato, se siguen generando por ámbito números para la referencia seleccionada.  
7. Expanda la sección **Referencias**. Seleccione el tipo de documento o el registro a los que asignar esta secuencia numérica. Este paso es optativo para las secuencias definidas para patrones de uso de aplicación especial. En estos casos, se genera un nuevo número usando el valor de un identificador o código de secuencia numérica, sin usar una referencia. Un ejemplo de este patrón de uso de aplicación especial es una serie de asientos que se usa con nombres de diario específicos. Sin embargo, no se recomienda usar estos patrones.  
8. Expanda la sección **General**. En la ficha desplegable General, especifique si la secuencia numérica es manual, y continua o no continua. Especifique además los números más altos y más bajos que se pueden usar en la secuencia numérica. No se recomienda cambiar una secuencia numérica no continua por una secuencia numérica continua. La secuencia numérica no será verdaderamente continua. Este cambio también puede provocar infracciones de clave duplicada en la base de datos. Además, las secuencias numéricas continuas tienen un efecto mayor sobre el rendimiento.   
9. Haga clic en **Guardar**.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
