--- 
title: "Habilitar la impresión de la etiqueta de matrícula"
description: "Este procedimiento le permite la impresión automática de una etiqueta de código de contenedor de envío en serie (SSCC) después de que el último artículo se selecciona del inventario en un proceso de trabajo de selección de ventas."
author: perlynne
manager: AnnBe
ms.date: 11/03/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6d186bf7e4aee8cfa97adbd90b9090085e842f9b
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="enable-license-plate-label-printing"></a>Habilitar la impresión de la etiqueta de matrícula

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento le permite la impresión automática de una etiqueta de código de contenedor de envío en serie (SSCC) después de que el último artículo se selecciona del inventario en un proceso de trabajo de selección de ventas. Puede ejecutar este procedimiento en la empresa USMF de los datos de prueba. Si lo ejecuta mediante sus propios datos, debe tener una secuencia numérica configurada para las matrículas de entidad de almacén. Es necesario configurar una impresora de etiquetas para poder comenzar esta tarea. Vaya a Administración de la organización > Configurar > Impresoras de red. En el panel de acciones, haga clic en Opciones y, a continuación, haga clic en el botón Descargar instalador del agente de ruta de documentos. Ejecute el instalador y asegúrese de que tiene una impresora de red de trabajo establecida en Activa para poder continuar con el procedimiento.


## <a name="set-up-the-gs1-company-prefix"></a>Configurar el prefijo GS1 de la empresa
1. Vaya a Gestión de almacenes > Configurar > Parámetros de gestión de inventario y almacenes.
2. En el campo Prefijo GS1 de la empresa, escriba las 7 cifras del número GS1 de la empresa.
3. Haga clic en Guardar.
4. Cierre la página.

## <a name="setup-the-sscc-license-plate-number-sequence"></a>Configurar la secuencia de la matrícula de entidad de almacén de SSCC
1. Vaya a Administración de la organización > Secuencias numéricas > Secuencias numéricas.
2. En el campo Área, seleccione una opción.
3. En el campo Referencia, seleccione una opción.
4. En el campo Empresa, escriba un valor.
5. En la lista, marque la fila seleccionada.
6. En la lista, haga clic en el vínculo de la fila seleccionada.
7. Expanda la sección Segmentos.
8. Haga clic en Editar.
9. En la tabla de segmentos, seleccione la primera fila
10. Haga clic en Quitar.
11. Haga clic en Quitar.
12. Haga clic en Guardar.
13. Cierre la página.

## <a name="create-the-document-route-layout"></a>Crear el diseño de la ruta de documentos
1. Vaya a Gestión de almacenes > Configurar > Ruta de documentos > Diseños de ruta de documentos.
    * Habilite la configuración de SSCC.  
2. Haga clic en Nuevo.
3. En el campo Id. de diseño, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. En la lista, busque y seleccione el registro deseado.
6. Haga clic en Insertar al final del texto.
7. Haga clic en Guardar.
8. Cierre la página.

## <a name="set-up-the-document-routing"></a>Configurar la ruta de documentos
1. Vaya a Gestión de almacenes > Configurar > Ruta de documentos > Ruta de documentos.
2. En el campo Tipo de pedido de trabajo, seleccione una opción.
3. Haga clic en Nuevo.
4. En el campo Almacén, escriba un valor.
5. En el campo Nombre, escriba un valor.
6. Haga clic en Nuevo.
7. En el campo Id. de diseño, especifique o seleccione un valor.
8. En el campo Nombre, especifique el nombre de la impresora que desee utilizar.
9. Haga clic en Guardar.
10. Cierre la página.

## <a name="create-mobile-device-menu"></a>Crear el menú del dispositivo móvil
1. Vaya a Gestión de almacenes > Configurar > Dispositivo móvil > Elementos de menú del dispositivo móvil.
2. Haga clic en Nuevo.
3. En el campo Nombre del elemento de menú, escriba un valor.
4. En el campo Título, escriba un valor.
5. En el campo Modo, seleccione una opción.
6. Seleccione Sí en el campo Usar trabajo existente.
7. Seleccione Sí en el campo Generar matrícula de entidad de almacén.
8. Expanda la sección Clases de trabajo.
9. Haga clic en Nuevo.
10. En el campo Identificador de la clase de trabajo, escriba un valor.
11. Haga clic en Guardar.
12. Cierre la página.
13. Vaya a Gestión de almacenes > Configurar > Dispositivo móvil > Menú del dispositivo móvil.
14. En la lista, busque y seleccione el registro deseado.
15. En el árbol, seleccione "En el árbol, seleccione el elemento de menú que ha creado antes".
16. Haga clic en Editar.
17. Haga clic en la flecha para agregar el elemento de menú al menú.
18. Haga clic en Guardar.
19. Cierre la página.

## <a name="update-a-work-template"></a>Actualizar una plantilla de trabajo
1. Vaya a Gestión de almacenes > Configurar > Trabajo > Plantillas de trabajo.
2. En la lista, busque y seleccione el registro deseado.
3. Haga clic en Editar.
4. Haga clic en Nuevo.
5. En la lista, marque la fila seleccionada.
6. En el campo Tipo de trabajo, seleccione "Imprimir".
7. En el campo Identificador de la clase de trabajo, especifique o seleccione un valor.
8. En la lista, haga clic en el vínculo de la fila seleccionada.
9. Haga clic en Subir.
10. Haga clic en Guardar.
11. Cierre la página.


