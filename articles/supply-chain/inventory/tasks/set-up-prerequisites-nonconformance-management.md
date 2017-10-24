---
title: "Configurar requisitos previo para la gestión"
description: "Use este procedimiento para habilitar procesos de gestión de disconformidades."
author: perlynne
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 842a9441158defca74d1b203a1b2509773ba8919
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-prerequisites-for-management"></a>Configurar requisitos previo para la gestión

[!include[task guide banner](../../includes/task-guide-banner.md)]

Use este procedimiento para habilitar procesos de gestión de disconformidades. Una no conformidad hace referencia a un procedimiento o artículo que tiene un problema de calidad, donde la información descriptiva incluye el origen y el tipo de problema. Este procedimiento usa la empresa de datos de demostración USMF. Este procedimiento lo realiza normalmente un gestor de calidad.


## <a name="enable-quality-management-processes-within-the-company"></a>Habilitar los procesos de administración de calidad dentro de la empresa
1. Vaya a Gestión del inventario > Configurar > Parámetros de la gestión de inventario y almacenes.
2. Haga clic en la ficha Administración de calidad.
3. Seleccione Sí en el campo Usar administración de calidad.
    * Seleccione este parámetro para habilitar los procesos de gestión de calidad para la empresa.  
4. En el campo Índice por hora, escriba un número.
    * Use el campo Índice por hora para especificar un índice de trabajo por hora en la divisa local. El índice por hora se usa para calcular los costes de operaciones relacionadas con una disconformidad. El índice por hora y los costes calculados proporcionan información de referencia para una disconformidad, y no interactúan con otras funcionalidades.  
5. Haga clic en Configuración del informe.
    * Esta página le permite definir los tipos de nota del informe de calidad que se usarán en diferentes tipos de informes de administración de calidad.  
6. Cierre la página.
7. Cierre la página.

## <a name="enable-user-for-nonconformance-processing"></a>Habilitar el procesamiento de disconformidad.
1. Vaya a Administración del sistema > Usuarios > Usuarios.
    * Para procesar la aprobación de un caso de disconformidad, el usuario que aprueba o rechaza las disconformidades debe tener un valor "Nombre" asignado en la página Usuarios. Para usar las notas de documento, el usuario también debe tener activada la gestión de documentos en las opciones de usuario.  
2. Use el filtro rápido para buscar registros. Por ejemplo, filtrar en el campo Nombre con un valor de "Ricardo".
    * Use el filtro para encontrar el usuario que aprobará o rechazará los registros disconformidad.  
3. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Para procesar la aprobación de un caso de disconformidad, asegúrese de que el usuario que aprueba o rechaza las disconformidades tiene un valor "Nombre" asignado en la página Usuarios.  
4. Haga clic en Opciones de usuario.
5. Haga clic en la ficha Preferencias.
6. Seleccione Sí en el campo Habilitar gestión de documentos.
    * Para usar las notas de documento, el usuario también debe tener activada la gestión de documentos en las opciones de usuario.  
7. Cierre la página.
8. Cierre la página.
9. Cierre la página.

## <a name="define-diagnostic-types-for-nonconformance-processing"></a>Definir tipos de diagnóstico para el procesamiento de disconformidad
1. Vaya a Gestión del inventario > Configurar > Administración de calidad > Tipos de diagnóstico.
    * Use la página Tipos de diagnóstico para definir una clasificación de acciones de diagnóstico. Una corrección identifica qué tipo de acción de diagnóstico se debe realizar en una disconformidad aprobada, quién debe efectuarla, y la fecha de finalización solicitada y planificada.  
2. Haga clic en Nuevo.
3. En el campo Diagnóstico, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. Cierre la página.

## <a name="define-quality-charges-for-nonconformance-processing"></a>Definir gastos de calidad para procesamiento de disconformidad
1. Vaya a Gestión del inventario > Configurar > Administración de calidad > Gastos de calidad.
    * Use la página Gastos de calidad para definir una clasificación de los gastos que se utilizarán en operaciones relacionadas con disconformidades.  
2. Haga clic en Nuevo.
3. En el campo Código de gastos, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. Cierre la página.

## <a name="define-the-operations-for-nonconformance-processing"></a>Definir las operaciones para procesamiento de disconformidad
1. Vaya a Gestión del inventario > Configurar > Administración de calidad > Operaciones.
    * Use la página Operaciones para definir una clasificación del trabajo que se puede efectuar para un caso de disconformidad aprobado. Al relacionar una operación relacionada con una disconformidad, se puede definir información acerca del material asociado, las horas de trabajo y los gastos varios requeridos para llevar a cabo la operación. Esta información proporciona la base para calcular un coste estimado para la ejecución de la operación.  
2. Haga clic en Nuevo.
3. En el campo Operación, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. Cierre la página.

## <a name="define-problem-types-for-nonconformance-processing"></a>Definir tipos de problema para procesamiento de disconformidad
1. Vaya a Gestión del inventario > Configurar > Administración de calidad > Tipos de problemas.
    * Use la página Tipos de problemas para definir una clasificación de problemas de calidad encontradas en los distintos tipos de disconformidad. Entre los tipos de disconformidad se incluyen Interna, Cliente, Proveedor, Solicitud de servicio, Producción y Producción de coproductos. Un tipo de problema único se puede asociar con varios tipos de disconformidad.  
2. Haga clic en Nuevo.
3. En el campo Tipo de problema, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. Haga clic en Tipos de no conformidad.
    * Use la página Tipos de no conformidad para autorizar el uso de un tipo de problema para uno o varios tipos de disconformidad. Por ejemplo, un tipo de problema relativo a un código defectuoso se podría aplicar a todos los tipos de no conformidad, mientras que un tipo de problema acerca de quejas del cliente sólo se puede aplicar a los tipos de no conformidad de cliente y solicitud de servicio.  
6. Haga clic en Nuevo.
7. En la lista, marque la fila seleccionada.
8. En el campo Tipo de no conformidad, seleccione una opción.
9. Cierre la página.
10. Cierre la página.

## <a name="define-quarantine-zones-for-nonconformance-processing"></a>Definir zonas de cuarentena para el procesamiento de disconformidad
1. Vaya a Gestión del inventario > Configurar > Administración de calidad > Zonas de cuarentena.
2. Haga clic en Nuevo.
3. En el campo Zona de cuarentena, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. Cierre la página.

