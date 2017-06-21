---
title: "Configuración de un modelo de configuración de productos"
description: "Este artículo describe los pasos para configurar y crear un modelo de configuración de productos."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCProductConfigurationModelListPage
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 4051
ms.assetid: 00df5537-b148-4e32-a248-3e35876ad4e1
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 8307ad3be2bc2799abdf057123b6022c7032b191
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="set-up-a-product-configuration-model"></a>Configuración de un modelo de configuración de productos

[!include[banner](../includes/banner.md)]


Este artículo describe los pasos para configurar y crear un modelo de configuración de productos.

| Tarea                                                        | Descripción                                                                                                                                                                                                                                                                                                                                                                                        |
|-------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Cree un producto maestro.                                    | Cree un producto maestro desde la lista **Producto maestro**. Emita el producto maestro a todas las empresas relevantes. Para un producto maestro que se usa como versión del modelo de configuración de un producto o como subcomponente, **Configuración basada en restricciones** debe estar seleccionado como tecnología de configuración, y la dimensión de configuración se debe seleccionar solo para el grupo de dimensiones del producto. |
| Cree componentes.                                          | Cree los componentes en la página **Componentes**. Los componentes son los componentes básicos de un modelo de configuración de productos y se pueden volver a usar en varios modelos de configuración de productos.                                                                                                                                                                                                                      |
| Cree tipos de atributo.                                     | Cree tipos de atributo en la página **Tipos de atributo**. Los tipos de atributo especifican el conjunto de tipos de datos para todos los atributos que se usan en modelos de configuración de productos. Los atributos **Booleano**, **Texto** con una lista fija y **Entero** con un tipo de intervalo enumeran el conjunto de valores disponibles cuando configura una variante de producto basada en un modelo de configuración de productos.       |
| Cree un modelo de configuración de productos.                       | Cree un modelo de configuración de productos en la página **Nuevo modelo de configuración de productos**.                                                                                                                                                                                                                                                                                                              |
| Agregue atributos a un modelo de configuración de productos.            | Cree un atributo en la ficha desplegable **Atributos** de página **Detalles del modelo de configuración de productos basados en restricciones**. Los atributos describen las características del modelo de configuración de productos.                                                                                                                                                                                                       |
| Agregue restricciones a un modelo de configuración de productos.           | Cree restricciones en la ficha desplegable **Restricciones** de página **Detalles del modelo de configuración de productos basados en restricciones**. Las restricciones son las limitaciones que una configuración de productos debe satisfacer. Las restricciones son restricciones de expresión o restricciones de tabla.                                                                                                                                 |
| Agregue subcomponentes a un modelo de configuración de producto.         | Cree subcomponentes en la ficha desplegable **Subcomponentes** de página **Detalles del modelo de configuración de productos basados en restricciones**. Los subcomponentes están relacionadas con los componentes y están vinculados a los artículos que representan el subcomponente.                                                                                                                                                                       |
| Agregue requisitos de usuario a un modelo de configuración de productos.     | Los requisitos de usuario son similares a los subcomponentes, pero no hacen referencia a un artículo. Puede pensar en los requisitos de usuario como una lista de materiales fantasma. Las líneas de lista de materiales u operaciones de ruta que se colocan directamente bajo el requisito de usuario deben contraerse dentro del componente principal.                                                                                                                       |
| Agregue líneas de lista de materiales a un modelo de configuración de productos.             | Cree líneas de lista de materiales en la ficha desplegable **Líneas de L. MAT.** de la página **Detalles del modelo de configuración de productos basados en restricciones**. Las líneas de lista de materiales representan una parte necesaria para crear una variante del producto.                                                                                                                                                                                                 |
| Agregue operaciones de ruta a un modelo de configuración de productos.      | Cree operaciones de ruta en la ficha desplegable **Operaciones de ruta** de la página **Detalles del modelo de configuración de productos basados en restricciones**. Las operaciones de ruta representan un paso en una secuencia de pasos llevados a cabo para crear una variante del producto.                                                                                                                                                    |
| Cree una versión activa para un modelo de configuración de productos. | Cree una versión activa del modelo de configuración de productos en la página **Versiones**. Una versión es la relación entre un modelo de configuración de productos y un producto maestro. Un modelo de configuración de productos con una versión activa se puede configurar desde un pedido de ventas, un presupuesto de ventas, un pedido de compra o un pedido de producción.                                                               |
| Pruebe un modelo de configuración de productos.                         | Pruebe el modelo de configuración de productos desde la página **Detalles basados en el modelo de configuración de productos** o la página **Lista de modelos de configuración de productos**. Al probar los modelos de configuración de productos se simula el proceso de configuración del modelo de productos que se produce durante la gestión de pedidos.                                                                                                |
| Cree una plantilla de modelo de configuración de productos.                | Cree una plantilla de modelo de configuración de productos en la página **Plantillas de configuración**. Una plantilla de configuración incluye los valores para los atributos en el modelo de configuración de productos. Seleccione los valores de atributo en la página **Configurar la línea**. Puede seleccionar cargar una plantilla de configuración de modelo de productos durante la configuración del modelo de productos.                                                   |
| Configure un artículo.                                          | Los modelos de configuración de productos se pueden configurar desde un pedido de ventas, un presupuesto de ventas, un pedido de compra o un pedido de producción.                                                                                                                                                                                                                                                                           |






