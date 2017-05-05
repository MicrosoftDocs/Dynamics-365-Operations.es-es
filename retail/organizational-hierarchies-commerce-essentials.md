---
title: "Organizaciones y jerarquías organizativas (conceptos básicos de Commerce)"
description: "Commerce essentials tiene tres tipos de organizaciones internas que se pueden definir para ayudar a una organización a realizar un proceso empresarial o a alcanzar un objetivo."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 21251
ms.assetid: 2bfc6bfe-784b-42e8-8bf0-116e9f0a558e
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 93711977ad8d861ca75ba80ee542ee112c8ddd2f
ms.lasthandoff: 03/31/2017


---

# <a name="organizations-and-organizational-hierarchies-commerce-essentials"></a>Organizaciones y jerarquías organizativas (conceptos básicos de Commerce)

[!include[banner](includes/banner.md)]


Commerce essentials tiene tres tipos de organizaciones internas que se pueden definir para ayudar a una organización a realizar un proceso empresarial o a alcanzar un objetivo. 

Una organización es un grupo de personas que trabajan juntas para realizar un proceso empresarial o lograr un objetivo. Una jerarquía organizativa representa las relaciones que hay entre las unidades de negocio que con forman la organización.

## <a name="organizations"></a>Organizaciones
En los conceptos básicos de Commerce puede definir tres tipos de organizaciones internas: entidades jurídicas, unidades operativas y equipos. En Microsoft Dynamics AX, todas las organizaciones internas son tipos de la entidad Parte. Por tanto, estas organizaciones usan una libreta de direcciones para almacenar direcciones y otra información de contacto. Una parte puede ser una persona o una organización, y puede pertenecer a una o varias libretas de direcciones.
### <a name="legal-entities"></a>Entidades jurídicas

Una entidad jurídica es una organización que tiene una estructura jurídicas registrada o legislada. Las entidades jurídicas pueden realizar contratos legales y tienen la obligación de preparar declaraciones para dar a conocer su rendimiento. Una empresa es un tipo de entidad jurídica en Microsoft Dynamics AX y todas las entidades jurídicas están asociadas a un identificador de empresa. Esta asociación existe porque se usa un identificador de empresa o DataAreaId en algunos modelos de datos en los que se emplean empresas como límite para la seguridad de datos. Los usuarios sólo pueden obtener acceso a los datos de la empresa en la que han iniciado sesión.

### <a name="operating-units"></a>Unidades operativas

Una unidad operativa es una organización que se usa para dividir el control de los recursos económicos y los procesos operativos de un negocio. Las personas de una unidad operativa tienen el deber de optimizar el uso de recursos escasos, mejorar los procesos y responder de su rendimiento. En los conceptos básicos de Commerce, los tipos de unidades operativas incluyen los centros de coste, las unidades de negocio, los flujos de valor, los departamentos y los canales comerciales. En la siguiente tabla se proporciona más información sobre cada tipo de unidad operativa.
|                         |                                                                                         |                                                                                                                                             |
|-------------------------|-----------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| **Tipo de unidad operativa** | **Descripción**                                                                         | **Propósito**                                                                                                                                 |
| Unidad de negocio           | Unidad operativa semiautónoma que se crea para cumplir objetivos empresariales estratégicos. | Use unidades de negocio para la notificación financiera basada en industrias o líneas de productos que la organización produce a través de la entidades jurídicas. |
| Canal comercial          | Una unidad operativa que representa un almacén físico.                             | Se usa para gestionar y controlar uno o varios almacenes dentro o entre entidades jurídicas.                                                               |

## <a name="organizational-hierarchies"></a>Jerarquías organizativas
En los conceptos básicos de Commerce, cada jerarquía tiene asignado un propósito. El propósito de una jerarquía determina los tipos de organizaciones que se pueden incluir en la jerarquía. El propósito también determina en qué escenarios de aplicación se puede usar una jerarquía. Por ejemplo, una jerarquía de venta minorista se puede usar para comprar y para vender productos en una tienda de venta minorista. Las organizaciones de una jerarquía pueden compartir parámetros, directivas y transacciones. Una organización puede heredar o reemplazar los parámetros de su organización principal. Sin embargo, los datos maestros compartidos, como los productos y las libretas de direcciones, se aplican a toda la organización y no pueden reemplazarse para organizaciones individuales.
### <a name="best-practices-for-setting-up-an-organization-in-a-hierarchy"></a>Prácticas recomendadas para configurar una organización en una jerarquía

Tenga en cuenta las siguientes prácticas recomendadas al implementar una jerarquía organizativa:
-   Cree un departamento para especificar la intersección entre una entidad jurídica y una unidad de negocio. A continuación, puede acumular datos de un departamento a una entidad jurídica para informes estatutarios, y desde un departamento a una unidad de negocio para informes internos.
-   En una única entidad jurídica, no configure varias jerarquías para el mismo propósito de la jerarquía.
-   No cree una jerarquía para cada propósito. Por lo general, puede usar una jerarquía para distintos fines. Por ejemplo, se puede asignar una jerarquía de unidades operativas a todos los propósitos relacionados con directivas.
-   Crea jerarquías equilibradas. En una jerarquía, todos los nodos que tienen la misma distancia del nodo raíz se definen como un nivel. En una jerarquía equilibrada, solo se puede producir un tipo de unidad operativa en cada nivel, y la distancia del nodo raíz hasta cada uno de los niveles es coherente. Si hay niveles intermedios entre un departamento y una entidad jurídica o una unidad de negocio, las organizaciones de marcador de posición pueden ser necesarias para crear una jerarquía equilibrada.
-   No configure una jerarquía independiente de las unidades operativas si la estructura para las entidades jurídicas también es su estructura operativa. Una jerarquía mixta de entidades jurídicas y unidades operativas puede servir a ambos propósitos.
-   Antes de configurar los escenarios de reestructuración principales, use las fechas de vigencia de la jerarquía para llevar a cabo un análisis de impacto y una prueba de validación.
-   Guarde una jerarquía como borrador si puede que desee cambiar una jerarquía antes de publicarla.
-   Limite el número de personas con permisos para agregar o quitar organizaciones de una jerarquía en un entorno de producción. Un número más pequeño reduce la posibilidad de que se puedan producir costosos errores y de que se deban realizar correcciones.

## <a name="retail-store-management"></a>Gestión de tienda comercial
En la siguiente tabla se describen los escenarios de conceptos básicos de Commerce en los que se pueden usar jerarquías organizativas.
| Tarea                                                                           | Descripción                                                                                                                                                                                                                                                                                                | Propósito de jerarquía    |
|--------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------|
| Administrar selecciones comerciales                                                      | Identifique los productos disponibles en cada tienda minorista.                                                                                                                                                                                                                                             | Selección comercial    |
| Administrar el reabastecimiento comercial                                                    | Agrupe almacenes para reabastecer el inventario según reglas de reabastecimiento.                                                                                                                                                                                                                                          | Reabastecimiento comercial |
| Crear informes de datos para los almacenes                                                         | Agrupe almacenes para la creación de informes.                                                                                                                                                                                                                                                                                | Informes comerciales     |
| Registrar inventario, calcular informes o registrar informes para un grupo de almacenes | Cree un grupo de almacenes que se pueden asignar a un trabajo por lotes. Si define un trabajo por lotes para registrar el inventario, calcular informes o registrar informes, puede especificar la jerarquía a la que se aplica el trabajo. Cuando se agregan a se eliminan almacenes de la jerarquía, no es necesario modificar el trabajo por lotes. | Registro de Retail POS   |






