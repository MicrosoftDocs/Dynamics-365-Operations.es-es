---
title: EUR-00011 Configurar informes de listas de ventas de la UE
description: Esta tarea le guía por una visión general de los requisitos previos necesarios para los Informes de listas de ventas de la UE.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionRepositoryTable, ERSolutionImport, SysQueryForm, SysQueryFieldLookUp,  TaxTable, TaxGroup, TaxItemGroup, TaxCountryRegionParameters, TaxVATNumTable, IntrastatParameters, CustTable, DirPartyQuickCreateForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c312e14247c42acd5e0de5df02833275d9e3a4f1
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140703"
---
# <a name="eur-00011-set-up-eu-sales-list-reporting"></a>EUR-00011 Configurar informes de listas de ventas de la UE

[!include [banner](../../includes/banner.md)]

Esta tarea le guía por una visión general de los requisitos previos necesarios para los Informes de listas de ventas de la UE. Para obtener más información acerca de los informes de la lista de ventas de la UE, incluidos requisitos previos necesarios, remítase a la Ayuda.

Esta tarea se aplica a todos los países o regiones europeos. La guía se ha creado con la empresa de datos de demostración DEMF y, por tanto, Alemania como país o región nacional de ejemplo. La guía también utiliza Portugal como país o región de la UE de ejemplo.

Estas tareas están destinadas a administradores del sistema.


## <a name="import-electronic-reporting-configurations-for-eu-sales-list-reporting"></a>Importar las configuraciones de informes electrónicos para informes de listas de ventas de la UE
1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.
2. Haga clic en Definir como activo.
3. Haga clic en Repositorios.
4. Haga clic en Abrir.
5. En el panel de acciones, haga clic en Opciones.
6. Haga clic en Ordenación o filtro avanzado.
7. Haga clic en Agregar.
8. En el campo Campo, seleccione "Nombre de configuración".
9. En el campo Criterios, escriba "Lista de ventas de la UE (DE)".
10. Haga clic en Aceptar
11. Haga clic en Importar.
12. Haga clic en Sí.
13. En el panel de acciones, haga clic en Opciones.
14. Haga clic en Ordenación o filtro avanzado.
15. Haga clic en Restablecer.
16. Haga clic en Agregar.
17. En el campo Campo, seleccione "Nombre de configuración".
18. En el campo Criterios, escriba "Lista de ventas de la UE por informe de filas".
19. Haga clic en Aceptar
20. Haga clic en Importar.
21. Haga clic en Sí.

## <a name="set-up-sales-tax-codes-for-eu-sales-list-reporting"></a>Configurar códigos de impuestos para informes de listas de ventas de la UE
1. Vaya a Impuestos > Impuestos indirectos > Impuestos > Códigos de impuestos.
2. Use un filtro rápido para filtrar el campo Código de impuestos con un valor de "VAT19".
3. Expanda la sección Configuración del informe.
    * Compruebe que la selección excluida se establece en No.  
    * Es posible que tenga que desbloquear la guía de tareas para cambiar esta configuración.  

## <a name="set-up-sales-tax-groups-for-eu-sales-list-reporting"></a>Configurar grupos de impuestos para informes de listas de ventas de la UE
1. Vaya a Impuestos > Impuestos indirectos > Impuestos > Grupos de impuestos.
2. Use un filtro rápido para filtrar el campo Grupo de impuestos sobre las ventas con un valor de "AR-DOM".
3. Haga clic en Editar.
4. Expanda la sección Configuración.
5. En la lista, seleccione la primera fila.
6. Active la casilla Exento.
7. En la lista, seleccione la segunda fila.
8. Active la casilla Exento.
9. En la lista, seleccione la tercera fila.
10. Active la casilla Exento.

## <a name="set-up-item-sales-tax-groups-for-eu-sales-list-reporting"></a>Configurar grupos de impuestos de artículos para informes de listas de ventas de la UE
1. Vaya a Impuestos > Impuestos indirectos > Impuestos > Grupos de impuestos de artículos.
2. Use un filtro rápido para filtrar por el campo Grupo de impuestos de artículos con un valor de "FULL".
    * Compruebe que la selección Tipo de notificación se establece en "Artículo".  
    * Es posible que tenga que desbloquear la guía de tareas para cambiar el valor en este campo.  
3. Use un filtro rápido para filtrar por el campo Grupo de impuestos de artículos con un valor de "RED".
    * Compruebe que la selección Tipo de notificación se establece en "Servicio".  
    * Es posible que tenga que desbloquear la guía de tareas para cambiar el valor en este campo.  

## <a name="set-up-countryregion-parameters-for-eu-sales-list-reporting"></a>Configurar parámetros de país o región para informes de listas de ventas de la UE
1. Vaya a Impuestos > Configuración > Impuestos > Parámetros por país o región.
2. Haga clic en Nuevo.
3. En el campo País/región, escriba "PRT".
4. En el campo Impuestos, escriba "PT".

## <a name="create-tax-exempt-numbers"></a>Crear números de exención fiscal
1. Vaya a Impuestos > Configuración > Impuestos > Números de identificación fiscal.
2. Haga clic en Nuevo.
3. En el campo País/región, escriba "PRT".
4. En el campo NIF, escriba "PT12345".

## <a name="set-up-eu-sales-list-reporting-parameters"></a>Configurar parámetros de informes de listas de ventas de la UE
1. Vaya a Impuestos > Configuración > Comercio exterior > Parámetros de comercio exterior.
2. Haga clic en la ficha Lista de ventas de la UE.
3. Seleccione Sí en el campo Transferir compras.
4. Expanda la sección Reglas de redondeo.
5. Establezca la regla de redondeo en "0,1".
6. Seleccione Sí en el campo Usar valor mínimo.
7. En el campo Número de decimales, escriba "2".
8. Expanda la sección Informes electrónicos.
9. En el campo Asignación de formato de archivo, seleccione "Lista de ventas de la UE (DE)".
10. En el campo Asignación de formato de informe, seleccione "Lista de ventas de la UE por informe de filas".
11. Haga clic en la ficha Propiedades de país/región.
    * Compruebe que el campo Tipo de país/región está establecido en "Nacional" para País o región DEU.  
    * Es posible que tenga que desbloquear la guía de tareas para cambiar el valor en este campo.  
12. Haga clic en Nuevo.
13. En el campo País/región, escriba "PRT".
14. En el campo Código intrastat, escriba "PT".
15. En el campo Tipo de país/región, seleccione "UE".
16. Haga clic en la ficha Secuencias numéricas.
    * Compruebe que hay un Código de secuencia numérica especificado para la referencia "Lista de ventas de la UE".  

## <a name="create-a-customer-for-eu-sales-list-reporting-demo-purposes"></a>Crear un cliente para fines de demostración de informes de lista de ventas de la UE
1. Vaya a Clientes > Clientes > Todos los clientes.
2. Haga clic en Nuevo.
3. En el campo Cuenta de cliente, escriba "PRT-001".
4. En el campo Nombre, escriba "Un cliente de Portugal".
5. En el campo Grupo de clientes seleccione "10".
6. En el campo Grupo de impuestos, seleccione "AR-DOM".
7. En el campo NIF, seleccione "PT12345".
8. En el campo País/región, escriba "PRT".
9. Haga clic en Guardar.

