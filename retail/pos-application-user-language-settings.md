---
title: "Configuración de idioma del usuario y aplicación del PDV"
description: "En este tema se describe cómo cambiar la configuración de idioma en el sistema POS moderno al por menor MPOS () y nublarse PDV."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmWorker, RetailStoreTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 78891
ms.assetid: 0030940c-e0a5-4345-9511-8c3bd1f487ad
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: bf5b75572529bb497d3079752de187f30aa59294
ms.lasthandoff: 03/31/2017


---

# <a name="pos-application-and-user-language-settings"></a>Configuración de idioma del usuario y aplicación del PDV

En este tema se describe cómo cambiar la configuración de idioma en el sistema POS moderno al por menor MPOS () y nublarse PDV.

<a name="overview"></a>Visión general
========

PDV moderno al por menor MPOS () y los entornos tanto de soporte de PDV de la nube donde la configuración de idioma y las conversiones pueden variar del almacén y la configuración del usuario. Por ejemplo, el almacén se podría estar ubicada en una región en el que es la más habituales el inglés para sus clientes, pero algunos trabajadores prefieren usar la aplicación con las traducciones francesas.

## <a name="data-language"></a>Idioma de los datos
Independientemente de la configuración del usuario, MPOS y la nube PDV utilizarán siempre la configuración de idioma de la tienda para determinar las traducciones utilizadas para los datos. Con esto que todos los usuarios y clientes tienen una experiencia coherente.  Ejemplos de los datos:

-   Productos
-   Atributos y valores
-   Nombres de categoría
-   Recibos de transacciones impresas o enviadas por correo electrónico
-   Nombres de métodos de pago
-   Mensajes de visualización de líneas

El idioma del almacén también se usará para la pantalla de inicio principal de PDV, puesto que no conoce al usuario antes de iniciar sesión. Si una traducción no está disponible para el idioma de la tienda, PDV revertirá el idioma de la empresa.

### <a name="configuring-the-stores-language-setting"></a>Configuración de ajustes del idioma de la tienda

La configuración de idioma del almacén se establece ** de todas comercios ** ** en tienda al por menor ** páginas correspondientes debajo ** idioma &gt; general &gt; de la configuración regional. ** Descenso Use el siguiente para seleccionar el idioma para cada tienda.

## <a name="user-interface-language"></a>Idioma de la interfaz de usuario
La configuración de idioma de usuario POS determina las traducciones utilizadas en la interfaz de usuario de Aplicación. Esto incluye todas las etiquetas, menús las listas, y que no se consideren los datos. Una excepción es el texto que se muestra en las cuadrículas de botones de Retail POS. Las cuadrículas de botones no admite las traducciones, por lo que muestren siempre el texto como se define en el botón. Para admitir tradujo los botones, tendrá que copiar y mantener las cuadrículas de botones independientes y asignarlas a los usuarios como corresponda.

### <a name="configuring-the-users-language-setting"></a>Configuración de ajustes del idioma del usuario

La configuración de idioma de usuario POS se establece de ** todos los trabajadores ** en ** trabajador ** la página en ** idioma &gt; al por menor **.  No se establece en la ficha principal del perfil.  Este valor no usa Retail POS. Si el idioma del usuario no se define o se define como un idioma donde no están disponibles las traducciones, el PDV volverá al idioma de la tienda.  

|             |                            |                                                                   |
|-------------|----------------------------|-------------------------------------------------------------------|
| ** **       | ** Idioma del IU ** ** **      | **Idioma de los datos (productos, formatos de recibos, visualización de líneas, etc.)** |
| **Empresa** | Predeterminada                    | Predeterminada                                                           |
| **Tienda**   | Reemplaza a la empresa          | Reemplaza a la empresa                                                 |
| **User**    | Reemplaza a la tienda o a la empresa | Nunca                                                             |




