--- 
title: "Producir el informe electrónico de contabilidad de libro mayor del producto mexicano versión 1.1"
description: "Esta tarea le muestra todos los pasos necesarios para configurar la generación de archivos XML electrónicos de cuenta contable mediante la herramienta de informes electrónicos."
author: sndray
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Mexico
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2ef0348c0b3a051de6cbb725efbd8e30e7968bd3
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="produce-mexican-electronic-ledger-accounting-report-version-11"></a>Producir el informe electrónico de contabilidad de libro mayor del producto mexicano versión 1.1

[!include[task guide banner](../../includes/task-guide-banner.md)]

Esta tarea le muestra todos los pasos necesarios para configurar la generación de archivos XML electrónicos de cuenta contable mediante la herramienta de informes electrónicos. Puede importar desde el centro de recursos de AX el modelo y los formatos de archivos XML para generar los extractos. 


## <a name="import-a-configuration-including-xml-formats"></a>Importación de una configuración con formatos XML
1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
2. En la lista Proveedores de configuración, haga clic en Definir como activo en el cuadro de proveedor de Microsoft.
    * Si el proveedor de Microsoft ya es el proveedor activo, puede omitir este paso.  
3. En la lista Proveedores de configuración, haga clic en el vínculo Repositorios en el cuadro de proveedor de Microsoft.
4. Haga clic en Agregar para abrir el cuadro desplegable.
5. Haga clic en Crear un repositorio.
6. En el campo Nombre, escriba un valor.
7. En el campo Descripción, escriba un valor.
8. Haga clic en Aceptar
9. En la lista, seleccione la configuración que acaba de crear.
10. En el panel de acciones, haga clic en Abrir.
11. En el árbol, seleccione Modelo electrónico de cuenta contable MX.
12. Haga clic en Importar.
13. Haga clic en Sí.
14. En el árbol, seleccione Modelo electrónico de cuenta contable MX\Libro mayor auxiliar XML MX.
15. Haga clic en Importar.
16. Haga clic en Sí.
17. En el árbol, seleccione Modelo electrónico de cuenta contable MX\Plan contable XML MX.
18. Haga clic en Importar.
19. Haga clic en Sí.
20. En el árbol, seleccione Modelo electrónico de cuenta contable MX\Diarios XML MX.
21. Haga clic en Importar.
22. Haga clic en Sí.
23. En el árbol, seleccione Modelo electrónico de cuenta contable MX\Saldo de comprobación XML MX.
24. Haga clic en Importar.
25. Haga clic en Sí.
26. Cierre la página.
27. Cierre la página.
28. Haga clic en el cuadro Configuraciones.
29. En el árbol, seleccione Modelo electrónico de cuenta contable MX.
30. En el árbol, expanda "En el árbol, expanda "Modelo electrónico de cuenta contable MX".
    * Podrá ver los cuatro (4) formatos XML que importó anteriormente.  

## <a name="configure-general-ledger-parameters-for-electronic-reporting-mapping"></a>Configuración de parámetros de contabilidad general para asignar informes electrónicos
1. Vaya a Contabilidad general > Configuración de contabilidad > Parámetros de Contabilidad general.
2. En el campo Saldo de comprobación, haga clic en el botón desplegable para abrir la búsqueda.
3. En la lista, seleccione el formato XML de saldo de comprobación.
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. En el campo Libro mayor auxiliar, haga clic en el botón desplegable para abrir la búsqueda.
6. En la lista, seleccione el formato XML de libro mayor auxiliar.
7. En el campo Movimientos contables, haga clic en el botón desplegable para abrir la búsqueda.
8. En la lista, seleccione el formato XML para diarios.
9. En la lista, haga clic en el vínculo de la fila seleccionada.
10. En el campo Plan contable, haga clic en el botón desplegable para abrir la búsqueda.
11. En la lista, seleccione el formato XML para plan de cuentas.
12. Haga clic en Guardar.

## <a name="generate-xml-files"></a>Generación de archivos XML
1. Vaya Contabilidad general > Consultas e informes > Informes de contabilidad > Extracto electrónico de cuenta contable.
2. En el campo Grupo de cuentas de consolidación de SAT, haga clic en el botón desplegable para abrir la búsqueda.
3. En la lista, busque y seleccione el registro deseado.
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. En el campo Período, especifique una fecha.
6. Active o desactive la opción Saldo de comprobación.
    * Esta opción genera los archivos XML del plan contable y el saldo de comprobación.  
7. Active o desactive la casilla Movimientos contables.
8. Active o desactive la casilla Libro mayor auxiliar.
9. En el campo Tipo de solicitud, seleccione una opción.
10. En el campo Número de pedido, escriba un valor.
11. Haga clic en Aceptar


