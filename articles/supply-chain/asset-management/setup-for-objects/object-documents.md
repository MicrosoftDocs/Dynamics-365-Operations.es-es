---
title: Documentos de activos
description: Este tema explica los documentos de activos en Administración de activos.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectDocument
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 77b7265b1ba56dbd1cd955f5d90afea02f589ce2eebdd05a2fef3a7ddebc0ee1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722496"
---
# <a name="asset-documents"></a>Documentos de activos

[!include [banner](../../includes/banner.md)]

 

Este tema explica los documentos de activos en Administración de activos.

En Administración de activos, puede configurar los documentos para que se relacionen automáticamente con los tipos de trabajo, los fabricantes de activos, los tipos de activos o los activos, por ejemplo. Esta funcionalidad es de utilidad cuando se publican versiones de documento actualizadas. En ese caso, solo tiene que colocar el documento actualizado en la ubicación estándar que se utiliza para los documentos de Supply Chain Management y vincular el documento al registro de documento de activo que ha creado. Después, el documento actualizado está accesible desde los elementos de menú **Todos los activos**, **Activos activos**, **Mis activos activos**, **Todas las órdenes de trabajo** y **Trabajos de orden de trabajo activos**. El proceso para adjuntar documentos a un registro de documento de activo utiliza el sistema de control de documentos estándar.

**Ejemplo 1:** un documento relacionado con un tipo de trabajo puede describir un procedimiento para ese tipo de trabajo.

**Ejemplo 2:** un documento relacionado con una combinación de tipo de activo, fabricante y modelo puede ser el manual estándar del modelo del fabricante del activo seleccionado.

## <a name="create-asset-document-relation"></a>Crear una relación de documento de activo

1. Seleccione **Administración de activos** \> **Configuración** \> **Documentos de activos**.
2. Seleccione **Nuevo** para crear un registro de documento de activo.
3. En función de lo específica que desea que sea la relación, realice las selecciones relevantes en uno o más de los campos siguientes: **Tipo de activo**, **Fabricante**, **Modelo**, **Activo**, **Categoría de tipo de trabajo**, **Tipo de trabajo**, **Variante del tipo de trabajo** y **Requisito de trabajo**. Las opciones disponibles en **Variante del tipo de trabajo** y **Requisito de trabajo** dependen de la selección realizada en el campo **Tipo de trabajo**.

    > [!NOTE]
    > Cuando el sistema busca documentos que deben estar relacionados con un activo o una orden trabajo, Administración de activos recorre todos los registros de documentos de activos para buscar una coincidencia. Comprueba siempre primero la combinación más específica. Es decir, Administración de activos primero busca una coincidencia para el campo **Requisito de trabajo**. Si no se encuentra ninguna coincidencia, comprueba si hay una coincidencia para el campo **Variante de tipo de trabajo**. Si no se encuentra ninguna coincidencia, comprueba si hay una coincidencia para el campo **Tipo de trabajo**, y así sucesivamente. Como puede ver en el diseño de la página **Documentos de activos**, este comportamiento significa que, para encontrar la combinación más específica, Administración de activos comprueba cada registro de derecha a izquierda en busca de una coincidencia. Varios documentos pueden estar relacionados con un activo o una orden de trabajo. Puede editar el nivel de servicio en una solicitud de mantenimiento o una orden de trabajo según sea necesario.

4. Seleccione **Archivos adjuntos**. Aparece la página **Gestión de documentos** estándar.
5. Configure los documentos o las notas que se deben vincular al registro de documento de activo. Después de vincular documentos, el campo **Archivos adjuntos** muestra el número de documentos relacionados con el registro.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]