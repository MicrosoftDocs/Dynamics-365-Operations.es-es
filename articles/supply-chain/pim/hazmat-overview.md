---
title: Información general de materiales peligrosos
description: Este artículo proporciona una descripción general de las características relacionadas con la manipulación y documentación de materiales peligrosos durante la gestión de información de productos y de almacén.
author: t-benebo
ms.date: 06/10/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: c2cae4cb65dd163e9fbf1d24cff5a0a040e3ce3a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905816"
---
# <a name="hazardous-materials-overview"></a>Resumen de materiales peligrosos

[!include [banner](../includes/banner.md)]

Para seguir cumpliendo con las regulaciones de envío y transporte, las organizaciones que envían materiales clasificados como mercancías peligrosas deben incluir documentación adicional con sus envíos. La función de materiales peligrosos permite a los clientes almacenar información relacionada con los artículos despachados. Esta información se puede utilizar para ayudar a preparar la documentación de envío. Una organización que envía mercancías peligrosas debe tener sus propios procesos y procedimientos para gestionar el proceso de envío. Microsoft Dynamics 365 Supply Chain Management es solo una herramienta que puede ayudar a generar los documentos requeridos.

El siguiente diagrama ilustra los pasos necesarios para configurar y utilizar la función de materiales peligrosos.

![Configuración y uso de la función de materiales peligrosos.](media/hazmat-overview.png "Configuración y uso de la función de materiales peligrosos")

La función de materiales peligrosos se configura en la gestión de información de productos y proporciona documentos que se pueden imprimir a través de la gestión del almacén. Por lo tanto, en términos generales, esas áreas son las dos áreas principales en las que revisará, configurará y utilizará la funcionalidad de esta función:

- **Gestión de la información del producto**: configure los códigos que se aplicarán a los productos despachados.
- **Gestión de almacenes**: trabajar con documentos de envío adicionales que se imprimirán para los envíos.

> [!IMPORTANT]
> Las características de materiales peligrosos en Supply Chain Management proporcionan una colección de campos de información de productos útiles y funcionalidades relacionadas que pueden ayudarle a registrar y hacer referencia a información relacionada con sus productos peligrosos. Estas características también pueden ayudarle a diseñar e imprimir documentos de envío que incluyan parte de la misma información sobre cualquier material peligroso que esté enviando. Sin embargo, el sistema no hará que cumpla automáticamente todas las regulaciones de su país o región. Si bien estas herramientas están destinadas a ayudarla a cumplir con las regulaciones comunes, no son suficientes por sí mismas ni se garantiza que lo sean. Su organización es responsable de conocer todas las regulaciones aplicables y de tomar todas las medidas necesarias para cumplirlas.

## <a name="product-information-management"></a>Gestión de información de productos

La gestión de información de productos ofrece diversas tablas de configuración donde puede introducir la información de referencia para las listas de mercancías peligrosas para el transporte por carretera, aéreo y marítimo.

Se hizo referencia a las siguientes regulaciones comunes cuando se desarrolló esta funcionalidad:

- **ADR** - Regulaciones relacionadas con el transporte internacional de mercancías peligrosas por carretera.
- **CFR 49** - Regulaciones en los Estados Unidos para el transporte de mercancías peligrosas
- **IMDG** - El código internacional de mercancías peligrosas marinas (IMDG)
- **IATA** - Las regulaciones de mercancías peligrosas de la Asociación Internacional de Transporte Aéreo (IATA)

Cada conjunto de reglamentaciones proporciona listas estandarizadas de mercancías peligrosas y códigos de referencia. Por tanto, Supply Chain Management proporciona una tabla de referencia para los códigos comunes de esas listas. Cada lista también tiene algunos códigos únicos que puede definir.

Para obtener más información sobre cómo configurar regulaciones y valores para materiales peligrosos, y cómo asignar los valores a productos relevantes, consulte los siguientes artículos:

- [Configurar materiales peligrosos](hazmat-setup.md)
- [Materiales peligrosos en productos, pedidos, envíos y cargas](hazmat-items.md)

## <a name="warehouse-management"></a>Gestión de almacenes

Cuando prepare un envío en Gestión de almacenes, podrá imprimir varios informes nuevos que utilizan la información que configuró en Gestión de información de productos. Para obtener más información sobre los informes disponibles y cómo utilizarlos, consulte [Consultas e informes sobre materiales peligrosos](hazmat-reports.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]