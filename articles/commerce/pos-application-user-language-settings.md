---
title: Configuración de idioma del usuario y aplicación de punto de venta (PDV)
description: Este tema describe cómo cambiar la configuración del idioma en Modern POS (MPOS) y el PDV de la nube.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: HcmWorker, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.custom: 78891
ms.assetid: 0030940c-e0a5-4345-9511-8c3bd1f487ad
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 09824d3b2eb8e3c1602882f19131d9fe312baaac
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263165"
---
# <a name="point-of-sale-pos-application-and-user-language-settings"></a>Configuración de idioma del usuario y aplicación de punto de venta (PDV)

[!include [banner](includes/banner.md)]

Este tema describe cómo cambiar la configuración del idioma en Modern POS (MPOS) y el PDV de la nube.

## <a name="overview"></a>Visión general
Tanto Modern POS (MPOS) como el PDV en la nube admiten entornos en los que la configuración del idioma y las traducciones pueden variar entre los ajustes del usuario y los de la tienda. Por ejemplo, la tienda podría estar situada en una región donde el inglés es más común para sus clientes, pero algunos trabajadores prefieren usar la aplicación con traducciones al francés.

## <a name="data-language"></a>Idioma de los datos

Independientemente de la configuración del usuario, MPOS y Cloud POS usarán siempre la configuración del idioma de las tiendas para determinar las traducciones usadas para los datos. Esto garantiza que todos los usuarios y clientes tengan una experiencia coherente. Algunos ejemplos de datos incluyen:

- Productos
- Atributos y valores
- Nombres de categoría
- Recibos de transacciones impresas o enviadas por correo electrónico
- Nombres de métodos de pago
- Mensajes de visualización de líneas

El idioma de la tienda también se usará para la pantalla principal de inicio de sesión del PDV, ya que no se conoce al usuario antes de iniciar sesión. Si una traducción no está disponible para el idioma de la tienda, el PDV volverá al idioma de la empresa.

### <a name="configuring-the-stores-language-setting"></a>Configuración de ajustes del idioma de la tienda

La configuración del idioma de la tienda se define como **Todas las tiendas** en la página **Tiendas** en **General &gt; Configuración regional &gt; Idioma**. Use la lista desplegable para elegir el idioma para cada tienda.

## <a name="user-interface-language"></a>Idioma de la interfaz de usuario

La configuración del idioma del usuario del PDV determina las traducciones usadas en la interfaz de usuario de la aplicación. Esto incluye todas las etiquetas, los menús y las listas que no se consideren datos. Una excepción a esto es el texto que aparece en las cuadrículas de botones del PDV. No admiten traducciones, por lo que mostrarán siempre el texto como se define en el botón. Para admitir botones traducidos, tendrá que copiar y mantener cuadrículas de botones independientes y asignarlas a los usuarios si procede.

### <a name="configuring-the-users-language-setting"></a>Configuración de ajustes del idioma del usuario

La configuración del idioma del usuario del PDV se define en **Todos los trabajadores** en la página **Trabajador** en **Retail y Commerce &gt; Idioma**. N se establece en la pestaña del perfil principal. Esta configuración no es usada por PDV. Si el idioma del usuario no se define o se define como un idioma donde no están disponibles las traducciones, el PDV volverá al idioma de la tienda.

|             | Idioma de la IU                  | Idioma de los datos (productos, formatos de recibos, visualización de líneas, etc.) |
|-------------|----------------------------|---------------------------------------------------------------|
| **Empresa** | Predeterminada                    | Predeterminada                                                       |
| **Tienda**   | Reemplaza a la empresa          | Reemplaza a la empresa                                             |
| **Usuario**    | Reemplaza a la tienda o a la empresa | Nunca                                                         |


[!INCLUDE[footer-include](../includes/footer-banner.md)]