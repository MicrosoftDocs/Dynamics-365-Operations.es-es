---
title: Definir esquemas de fidelización comercial
description: Este procedimiento muestra cómo definir un esquema de fidelización.
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 362d6cf877c484c438641980d109b3bed4464b68
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "315162"
---
# <a name="define-loyalty-schemes"></a>Definir esquemas de fidelización comercial

[!include [task guide banner](../includes/task-guide-banner.md)]

Este procedimiento muestra cómo definir un esquema de fidelización. Los esquemas de fidelización son reglas de canje y obtención de recompensas para un programa de fidelización. Este procedimiento usa la empresa de datos de demostración USRT.

1. Vaya a Venta minorista y comercio > Clientes > Fidelidad > Planes de fidelización.
2. Haga clic en Nuevo.
3. En el campo Id. de esquema, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. En el campo Nombre, haga clic en el botón desplegable para abrir la búsqueda.
    * Puede tener varios esquemas de fidelización para un programa de fidelización. Los esquemas de fidelización pueden ser para todos los canales o solo un subconjunto de canales.  
6. En la lista, busque y seleccione el registro deseado.
7. En la lista, haga clic en el vínculo de la fila seleccionada.
8. Haga clic en Guardar.
9. Haga clic en Agregar línea.
10. En el campo Tipo de actividad, seleccione una opción.
    * Seleccione Comprar productos por importe si desea que los clientes obtengan recompensas basadas en cuánto gastan. Seleccione Comprar productos por cantidad si desea que los clientes obtengan recompensas basadas en cuántos productos compran.  Seleccione Recuento de transacciones de venta si desea que los clientes obtengan recompensas por cada transacción de ventas, independientemente de qué o cuánto se compra.  
    * Permite seleccionar una categoría. La categoría limitará a qué productos se aplica esta regla de ganancia.  
    * Si desea que la regla de ganancia se aplique a todos los productos, deje este campo en blanco.  
11. En el campo Importe o cantidad de la actividad, escriba un número.
    *  Para el Recuento de transacciones de venta de tipo de actividad, debe usar siempre un valor de "1.0". Para los tipos de actividad de compra por importe o de compra por cantidad, cualquier transacción menor que el valor especificado no accionará la regla de ganancia. Por ejemplo, si el tipo de actividad es compra por importe, y especifica "10.00", una transacción de ventas para "9.00" no obtendrá recompensas para esta regla de ganancia.  
12. En el campo Divisa de la actividad, escriba un valor.
13. En el campo Id. de punto de recompensa, haga clic en el botón desplegable para abrir la búsqueda.
14. En la lista, haga clic en el vínculo de la fila seleccionada.
15. En el campo Puntos de recompensa, escriba un número.
    * Los puntos de recompensa de tipo de importe registrarán importes obtenidos con decimales. Por ejemplo, si la regla de ganancia indica 1 punto de recompensa obtenido por cada dólar canadiense gastado, y el cliente gasta 1,25 dólares canadienses, el cliente ganará 1,25 puntos de recompensa. Los puntos de recompensa de tipo de importe registrarán importes obtenidos en enteros. Usando el ejemplo en el que la regla de ganancia indica 1 punto de recompensa obtenido por cada dólar canadiense gastado, y el cliente gasta 1,25 dólares canadienses, el cliente ganará 1,0 puntos de recompensa.  
16. Haga clic en Guardar.
17. Haga clic en Agregar línea.
    * Se usan reglas de canje cuando se usa el método de pago de fidelización.  
18. En el campo Id. de punto de recompensa, haga clic en el botón desplegable para abrir la búsqueda.
    * Solo se muestran los puntos de recompensa canjeables.  
19. En la lista, haga clic en el vínculo de la fila seleccionada.
20. En el campo Puntos de recompensa, escriba un número.
21. En el campo Tipo de canje, seleccione una opción.
    * La selección de Pago por importe hace que el campo Importe o cantidad se trate como un valor de divisa. En este caso, el importe de los puntos de recompensa usados por unidad de divisa de pago es un coeficiente fijo. La selección de Pago por cantidad hace que el campo Importe o cantidad se trate como un valor de cantidad. En este caso, el importe de puntos de recompensa por cantidad de artículo es un coeficiente fijo; sin embargo, el importe en divisa puede variar si el precio de los artículos pagados con puntos de recompensa de fidelización varía para la misma cantidad. El tipo de canje de descuento de puntos de fidelización solo es válido cuando la clave de configuración de características específicas de país o región de "Rusia" y los perfiles de la funcionalidad de PDV tienen un código ISO de "RU".  
    * Permite seleccionar una categoría. La categoría limitará a qué productos se aplica esta regla de canje.  
    * Si desea que la regla de canje se aplique a todos los productos, deje este campo en blanco.  
22. En el campo Importe o cantidad, escriba un número.
23. En el campo Divisa, escriba un valor.
24. Haga clic en Guardar.
25. Haga clic en Agregar línea.
    * Seleccione uno o más nodos en la lista Nodos organizativos disponibles y muévalos a la lista Nodos organizativos seleccionados haciendo clic en la flecha entre las dos listas.  
26. Haga clic en Aceptar
27. Haga clic en Guardar.
    * Siempre que cambia los canales para un esquema de fidelización, debe ejecutar Procesar esquemas de fidelización. De esa manera, los canales obtendrá esquemas de fidelización actualizados.  

