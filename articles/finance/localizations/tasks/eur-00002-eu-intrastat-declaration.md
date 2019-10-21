---
title: EUR-00002 Generar una declaración de intrastat de la UE
description: Este procedimiento le guía por los pasos necesarios para exportar la declaración de Intrastat en el formato de archivo electrónico y obtener una vista previa los datos de la declaración en formato Excel.
author: Anasyash
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionRepositoryTable, ERSolutionImport, IntrastatParameters, IntrastatCommodityLookup, IntrastatCompressParameters, Intrastat, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: anasyash
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0d7ab1d274b527bf5071900940bf53a57a88f482
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2183572"
---
# <a name="eur-00002-generate-an-eu-intrastat-declaration"></a>EUR-00002 Generar una declaración de intrastat de la UE

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento le guía por los pasos necesarios para exportar la declaración de Intrastat en el formato de archivo electrónico y obtener una vista previa los datos de la declaración en formato Excel. 

Para poder completar este procedimiento, debe transferir transacciones a intrastat. 

Este procedimiento se creó con los datos de demostración de la empresa DEMF.


## <a name="import-configurations-with-settings"></a>Importar configuraciones con ajustes
1. Vaya a Áreas de trabajo > Informes electrónicos
2. Haga clic en Definir como activo.
3. Haga clic en Repositorios.
4. Haga clic en Abrir.
5. Abra el filtro de columna Nombre de configuración.
6. Aplique un filtro en el campo "Nombre de configuración" con un valor de "Intrastat (DE)", mediante el operador de filtro "empieza por".
    * Debe seleccionar el nombre de la configuración aplicable para el país de su entidad jurídica. Este procedimiento usa la entidad jurídica alemana (DEMF) como ejemplo, por tanto se debe elegir "Intrastat (DE)".  
    * Haga clic en Importar y, a continuación, en Sí.  
7. Abra el filtro de columna Nombre de configuración.
8. Aplique un filtro en el campo "Nombre de configuración" con un valor de "informe intrastat", mediante el operador de filtro "empieza por".
    * Haga clic en Importar y, a continuación, en Sí.  

## <a name="set-up-foreign-trade-parameters"></a>Configurar parámetros de comercio exterior
1. Vaya a Impuestos > Configuración > Comercio exterior > Parámetros de comercio exterior.
2. Expanda la sección Informes electrónicos.
3. En el campo Asignación de formato de archivo, especifique o seleccione un valor Intrastat (DE).
4. En el campo Asignación de formato de informe, especifique o seleccione un valor para Informe intrastat
5. Expanda la sección Reglas de redondeo.
    * Debe configurar las reglas de redondeo que son aplicables en su país o región para informes de intrastat.  
6. En el campo Regla de redondeo, escriba un número
    * Especifique la precisión del redondeo, por ejemplo, especifique “0,01".  
7. En el campo Número de decimales para el importe, especifique un número.
    * Por ejemplo, escribe "2".  
8. En el campo Redondeo inferior a 1 kg, seleccione una opción.
    * Por ejemplo, seleccione "Redondeo a 1 kg".  
9. En el campo Regla de redondeo, escriba un número
    * Por ejemplo, especifique "1" para redondear el peso al número entero.  
10. Expanda la sección Límite mínimo.
11. En el campo Peso, escriba un número.
    * Por ejemplo, especifique "10" como el peso mínimo.  
12. En el campo Importe, especifique un número.
    * Por ejemplo, especifique "200" como el importe mínimo.  
13. En el campo Código Intrastat de la mercancía, especifique o seleccione un valor.

## <a name="set-up-compression-of-intrastat"></a>Configurar la compresión de Intrastat
1. Vaya a Impuesto > Configurar > Comercio exterior > Compresión de Intrastat.
2. Haga clic en Quitar.
3. En la lista, busque y seleccione el registro deseado.
    * Por ejemplo, seleccione Mercancía en la sección Disponible.  
4. Haga clic en Agregar.

## <a name="generate-intrastat-declaration"></a>Generar la declaración de Intrastat
1. Vaya a Impuestos > Declaraciones > Comercio exterior > Intrastat
2. Haga clic en Validar.
    * La validación se realiza en función del campo Comprobar configuración de la página Parámetros de comercio exterior.  
3. Haga clic en Aceptar
4. Haga clic en Actualizar.
5. Haga clic en Límite mínimo.
6. En el campo Fecha inicial, especifique una fecha.
    * Por ejemplo, escriba 1 de enero de 2015.  
7. Seleccione Sí en el campo Comprimir.
8. En el campo Fecha final, especifique una fecha.
    * Por ejemplo, escriba 31 de enero de 2015.  
9. Haga clic en Aceptar
10. Haga clic en Actualizar.
11. Haga clic en Comprimir.
    * Esta compresión se produce en función de cómo se establece la configuración la Compresión de intrastat.  
12. En el campo Fecha inicial, especifique una fecha.
    * Por ejemplo, escriba 1 de enero de 2015.  
13. En el campo Fecha final, especifique una fecha.
    * Por ejemplo, escriba 31 de enero de 2015.  
14. Haga clic en Aceptar
15. Haga clic en Actualizar.
16. Haga clic en Volver a generar los números de secuencia.
17. Haga clic en Aceptar
18. Haga clic en Salida.
19. Haga clic en Informe.
20. En el campo Fecha inicial, especifique la primera fecha del período de informes.
    * Por ejemplo, establezca la fecha en el 1 de enero de 2015.  
21. Especifique una fecha en el campo Fecha final.
    * Por ejemplo, escriba 31 de enero de 2015.  
22. Seleccione Sí en el campo Generar archivo.
23. En el campo Nombre de archivo, escriba un valor.
24. Seleccione Sí en el campo Generar informe.
25. En el campo Nombre de archivo del informe, escriba un valor.
26. En el campo Dirección, seleccione una opción.
    * Por ejemplo, seleccione "Distribuciones".  
27. Haga clic en Aceptar

