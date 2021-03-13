---
title: Crear un método de puntuación para solicitudes de presupuesto
description: Este procedimiento muestra cómo crear un método de puntuación.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQScoringMethod
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 738768a6756db83a6855756ef48fffb4a5874b4a
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021388"
---
# <a name="create-a-scoring-method-for-rfqs"></a>Crear un método de puntuación para solicitudes de presupuesto

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo crear un método de puntuación. Un método de puntuación es un conjunto de criterios que se pueden utilizar para comparar ofertas que se envían en respuesta a una solicitud de presupuesto. Por ejemplo, puede que desee evaluar el rendimiento de un proveedor anterior, o calificar si la empresa es respetuosa con el medio ambiente o un buen colaborador, o puede que desee comparar ofertas en función del precio. El método de puntuación se puede asociar a un tipo de solicitud como el método de puntuación predeterminado para solicitudes de presupuesto de ese tipo. Estas tareas las realizará normalmente el director de compras. Puede utilizar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.

1. Vaya a Adquisición y abastecimiento > Configuración > Solicitud de presupuesto > Método de puntuación.
2. Haga clic en Nuevo.
3. En el campo Nombre, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. Haga clic en Guardar.
6. Haga clic en Nuevo.
7. En el campo Nombre, escriba un valor.
8. En el campo Descripción, escriba un valor.
    * Esta descripción se muestra junto con el nombre del método de puntuación cuando hay un método de puntuación seleccionado para una solicitud de presupuesto.  
9. En el campo Inicio de intervalo, escriba un número.
    * El rango limita qué puede introducir el profesional de compras como puntuación. Cuando hay varios criterios de puntuación en una solicitud de presupuesto, las puntuaciones que se han introducido se agregan a cada uno y la suma se hace disponible para permitir la comparación de las ofertas.  
10. En el campo Fin de intervalo, escriba un número.
11. Haga clic en Nuevo.
12. En el campo Nombre, escriba un valor.
13. En el campo Descripción, escriba un valor.
14. En el campo Inicio de intervalo, escriba un número.
15. En el campo Fin de intervalo, escriba un número.

