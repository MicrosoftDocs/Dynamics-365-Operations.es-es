---
title: Habilitar la impresión de la etiqueta de matrícula
description: En este tema se muestra cómo habilitar la impresión automática de una etiqueta de código de contenedor de envío en serie (SSCC) después de que el último artículo se selecciona del inventario en un proceso de trabajo de selección de ventas.
author: perlynne
manager: tfehr
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysCorpNetPrinterList, WHSParameters, NumberSequenceTableListPage, NumberSequenceDetails, WHSDocumentRoutingLayout, WHSDocumentRouting, WHSRFMenuItem, WHSRFMenu, WHSWorkTemplateTable, WHSLicensePlateLabelBuildConfig, WHSLicensePlateLabel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d5580edb3324f76f04140bd6793bddaace5fadcf
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977122"
---
# <a name="enable-license-plate-label-printing"></a>Habilitar la impresión de la etiqueta de matrícula

[!include [banner](../../includes/banner.md)]

En este tema se muestra cómo habilitar la impresión automática de una etiqueta de código de contenedor de envío en serie (SSCC) después de que el último artículo se selecciona del inventario en un proceso de trabajo de selección de ventas. Puede ejecutar este procedimiento en la empresa USMF de los datos de prueba. Si lo ejecuta mediante sus propios datos, debe tener una secuencia numérica configurada para las matrículas de entidad de almacén. Es necesario configurar una impresora de etiquetas para poder comenzar esta tarea. Vaya a Administración de la organización > Configurar > Impresoras de red. En el panel Acciones, haga clic en Opciones y, a continuación, haga clic en el botón Descargar instalador del agente de ruta de documentos. Ejecute el instalador y asegúrese de que tiene una impresora de red de trabajo establecida en Activa para poder continuar con el procedimiento.


## <a name="set-up-the-gs1-company-prefix"></a>Configurar el prefijo GS1 de la empresa
1. Vaya al **Panel de exploración > Módulos > Gestión de almacenes > Configuración > Almacén >Parámetros de gestión de almacenes**.
2. En el campo **Prefijo GS1 de la empresa**, escriba las 7 cifras del número GS1 de la empresa.
3. Seleccione **Guardar**.
4. Cierre la página.

## <a name="setup-the-sscc-license-plate-number-sequence"></a>Configurar la secuencia de la matrícula de entidad de almacén de SSCC
1. Vaya al **panel de navegación > Módulos > Administración de la organización > Secuencias numéricas > Secuencias numéricas**.
2. En el campo **Área**, seleccione una opción.
3. En el campo **Referencia**, seleccione una opción.
4. En el campo **Empresa**, escriba un valor.
5. Expanda la sección **Segmentos**.
6. Seleccione **Editar**.
7. En la tabla de **Segmentos**, seleccione la primera fila
8. Seleccione **Quitar**.
9. Seleccione **Quitar**.
10. Seleccione **Guardar**.
11. Cierre la página.

## <a name="create-the-document-route-layout"></a>Crear el diseño de la ruta de documentos
1. Vaya a **Panel de exploración > Módulos > Gestión de almacenes > Configurar > Ruta de documentos > Diseños de ruta de documentos**. Habilite la configuración de SSCC.  
2. Seleccione **Nuevo**.
3. En el campo **Id. de diseño**, escriba un valor.
4. En el campo **Descripción**, escriba un valor.
5. Seleccione **Insertar al final del texto**.
6. Seleccione **Guardar**.
7. Cierre la página.

## <a name="set-up-the-document-routing"></a>Configurar la ruta de documentos
1. Vaya a **Panel de exploración > Módulos > Gestión de almacenes > Configurar > Ruta de documentos > Ruta de documentos**.
2. En el campo **Tipo de pedido de trabajo**, seleccione una opción.
3. Seleccione **Nuevo**.
4. En el campo **Almacén**, escriba un valor.
5. En el campo **Nombre**, escriba un valor.
6. Seleccione **Nuevo**.
7. En el campo **Id. de diseño**, especifique o seleccione un valor.
8. En el campo **Nombre**, especifique el nombre de la impresora que desee utilizar.
9. Seleccione **Guardar**.
10. Cierre la página.

## <a name="create-mobile-device-menu"></a>Crear el menú del dispositivo móvil
1. Vaya al **Panel de exploración >Módulos > Administración de módulos > Configuración > Dispositivo móvil > Elementos de menú del dispositivo móvil**.
2. Seleccione **Nuevo**.
3. En el campo **Nombre del elemento de menú**, escriba un valor.
4. En el campo **Título**, escriba un valor.
5. En el campo **Modo**, seleccione una opción.
6. Seleccione **Sí** en el campo **Usar trabajo existente**.
7. Seleccione **Sí** en el campo **Generar matrícula de entidad de almacén**.
8. Expanda la sección **Clases de trabajo**.
9. Seleccione **Nuevo**.
10. En el campo **Id. de la clase de trabajo**, escriba un valor.
11. Seleccione **Guardar**.
12. Cierre la página.
13. Vaya al **Panel de exploración >Módulos > Administración de módulos > Configuración > Dispositivo móvil > Menú del dispositivo móvil**.
14. En el árbol, seleccione el elemento de menú que ha creado antes.
15. Seleccione **Editar**.
16. Seleccione la flecha para agregar el elemento de menú al menú.
17. Seleccione **Guardar**.
18. Cierre la página.

## <a name="update-a-work-template"></a>Actualizar una plantilla de trabajo
1. Vaya al **Panel de exploración > Módulos > Gestión de almacenes > Configuración > Trabajo > Plantillas de trabajo**.
2. Seleccione **Editar**.
3. Seleccione **Nuevo**.
4. En el campo **Tipo de trabajo**, seleccione **Imprimir**.
5. En el campo **Id. de la clase de trabajo**, especifique o seleccione un valor.
6. Seleccione **Subir**.
7. Seleccione **Guardar**.
8. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]