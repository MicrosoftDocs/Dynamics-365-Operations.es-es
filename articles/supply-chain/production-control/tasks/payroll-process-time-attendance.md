---
title: Habilitar el proceso de nómina para tiempo y asistencia
description: Este procedimiento muestra cómo habilitar el proceso de nóminas para tiempo y asistencia.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: JmgPayTable, JmgPayRate, JmgPayAgreementTable, JmgPayAgreementLine, HcmWorker
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d3b196e25699c43dbac06e950aae0ad8a9457a8d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7566560"
---
# <a name="enable-the-payroll-process-for-time-and-attendance"></a>Habilitar el proceso de nómina para tiempo y asistencia

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo habilitar el proceso de nóminas para tiempo y asistencia. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.


## <a name="create-a-pay-type-with-a-related-pay-rate"></a>Crear un tipo de sueldo con un índice salarial relacionado
1. Tiempo y asistencia > Configurar > Nómina > Tipos de sueldo
2. Haga clic en Nuevo.
3. En el campo Tipo de sueldo, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. Haga clic en Guardar.
6. Haga clic en Tasas.
    * Los índices para los tipos de sueldo se configuran para intervalos de tiempo concretos, y se pueden especificar índices individuales para los trabajadores. No siempre es necesario crear índices para los tipos de tiempo y asistencia. Esta información puede existir en el sistema de nómina utilizado para generar los salarios.  
7. Haga clic en Nuevo.
8. En la lista, marque la fila seleccionada.
9. En el campo Tasa, escriba un número.
10. Haga clic en Guardar.

## <a name="create-a-pay-agreement"></a>Crear un acuerdo de sueldo
1. Cierre la página.
2. Cierre la página.
3. Vaya a Acuerdos de sueldo.
    * Tiempo y asistencia > Configurar > Acuerdos de sueldo  
4. Haga clic en Nuevo.
5. En el campo Acuerdo de sueldo, escriba un valor.
6. En el campo Descripción, escriba un valor.
7. Haga clic en Guardar.
8. Haga clic en Líneas de acuerdo.
9. Haga clic en Nuevo.
10. En la lista, marque la fila seleccionada.
11. En el campo Tipo de perfil, especifique o seleccione un valor.
12. En el campo Tipo de sueldo, especifique o seleccione un valor.

## <a name="set-up-pay-agreement-for-time-and-registration-worker"></a>Configurar un acuerdo de sueldo para un trabajador de tiempo y registro
1. Cierre la página.
2. Cierre la página.
3. Vaya a Trabajadores con registro de horas.
    * Tiempo y asistencia > Configurar > Trabajadores con registro de horas  
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. Haga clic en la ficha Empleo.
6. Expanda la sección Registro de horas.
7. Haga clic en Editar.
8. En el campo Acuerdo de sueldo, especifique o seleccione un valor.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]