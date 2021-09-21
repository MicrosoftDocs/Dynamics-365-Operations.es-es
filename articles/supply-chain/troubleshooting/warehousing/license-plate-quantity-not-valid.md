---
title: La cantidad no es válida al registrar pedidos entrantes
description: 'Si la cantidad que se asigna para una matrícula excede la cantidad que aún debe recibirse para las dimensiones actuales, recibirá el error: "La cantidad no es válida".'
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 5099b320447bf59c72f5017564ea660f19c690a5
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477564"
---
# <a name="license-plate-quantity-is-not-valid-when-registering-inbound-orders"></a>La cantidad de la matrícula no es válida al registrar pedidos entrantes

## <a name="symptoms"></a>Síntomas

Al registrar pedidos entrantes, puede que reciba el siguiente mensaje de error:

> La cantidad no es válida.

Si el campo **Directiva de agrupación de matrículas** está configurado en *Definido por el usuario* para un elemento de menú de dispositivo móvil que se utiliza para registrar pedidos entrantes, recibe este error y no puede completar el registro.

## <a name="cause"></a>Causa

Cuándo *Definido por el usuario* se utiliza como una directiva de agrupación de matrículas, el sistema divide el inventario entrante en matrículas separadas, como lo indica el grupo de secuencia de unidades. Si se utilizan números de lote o de serie para rastrear el artículo que se está recibiendo, las cantidades de cada lote o serie deben especificarse por matrícula registrada. Si la cantidad que se especifica para una matrícula excede la cantidad que aún debe recibirse para las dimensiones actuales, recibirá este mensaje de error.

## <a name="resolution"></a>Resolución

Cuando registra un elemento utilizando un elemento de menú de dispositivo móvil donde el campo **Directiva de agrupación de matrículas** el campo está configurado en *Definido por el usuario*, es posible que el sistema requiera que confirme o ingrese números de matrícula, números de lote o números de serie.

En la página de confirmación de la matrícula, el sistema mostrará la cantidad asignada para la matrícula actual. En las páginas de confirmación del lote o de la serie, el sistema mostrará la cantidad que aún debe recibirse en la matrícula actual. También incluirá un campo donde puede ingresar la cantidad a registrar para esa combinación de placa y lote o número de serie. En este caso, asegúrese de que la cantidad que se está registrando para la matrícula no exceda la cantidad que aún debe recibirse.

Alternativamente, si se generan demasiadas matrículas en el registro de pedidos entrantes, el valor del campo **Directiva de agrupación de matrículas** se puede cambiar a *Agrupación de matrículas*, se puede asignar un nuevo grupo de secuencia de unidades al artículo, o la opción **Agrupación de matrículas** para el grupo de secuencia de unidades se puede desactivar.
