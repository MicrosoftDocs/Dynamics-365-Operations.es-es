---
title: Agregar ubicación y tipos de relaciones de las partes
description: En este tema se explica cómo agregar una nueva ubicación y un tipo de relación de las partes.
author: ShivamPandey-msft
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-05-02
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 36c2c45c8f078abdc7e0bc40481a544491384245
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2022
ms.locfileid: "8711503"
---
# <a name="add-location-and-party-relationship-types"></a>Agregar ubicación y tipos de relaciones de las partes 

[!include [banner](../includes/banner.md)]

## <a name="add-location-roles"></a>Agregar roles de ubicación

Existen dos formas de agregar nuevos roles de ubicación para la dirección y la información de contacto:

-  Agréguelo a través de la página **Propósito de la dirección y de la información de contacto**. El nuevo rol se guardará en la tabla **LogisticsLocationRole** con el tipo = 0, lo que indica que la función no es un rol del sistema definido en la enumeración **LogisticsLocationRoleType** y sus extensiones. Un usuario podrá utilizar esta función al crear la dirección o la información de contacto.

    ![Propósito de la dirección y de la información del contenido.](media/Address-Contact.PNG)

-  Agréguelo a la extensión de la enumeración **LogisticsLocationRoleType** y deje que se complete mediante el proceso de sincronización de la base de datos.

    1.  Crear una extensión para la enumeración **LogisticsLocationRoleType** y agregue el nuevo rol en la extensión. 
  
        ![Extensión para la enumeración LogisticsLocationRoleType.](media/Logistics.PNG)

    2. Cree un nuevo archivo de recursos para el nuevo rol y, a continuación, asigne un valor para sus propiedades.
     
     ![Nuevo archivo de recursos.](media/Resource.PNG)
        
    3.  Cree una clase de rellenado de datos y proporcione un método de controlador para rellenar el nuevo rol. 

        ![Rellenado de datos.](media/Dirdata.PNG)

    4.  Para probar a rellenar el nuevo rol de ubicación, puede crear una clase ejecutable y denominar DirDataPopulation::insertLogisticsLocationRoles() en Main(). Una vez completado este proceso, debe ver el nuevo rol rellenado en la tabla **LogisticsLocationRole** con tipo \> 0. El nuevo rol se mostrará en la página **Propósito de la dirección y de la información de contacto**.

        ![Insertar nueva ubicación.](media/InsertNewLocation.PNG)

## <a name="add-party-relationship-types"></a>Agregar tipos de relación de terceros 

Existen dos formas de agregar un nuevo tipo de relación:

-   Agréguelo a través de la página **Tipos de relación**. La nueva relación se guardará en **DirRelationshipTypeTable** con systemtype = 0.

    ![Tipos de relaciones.](media/Relationship.PNG)

-  Agréguelo a la extensión de la enumeración **DirSystemRelationshipType** y deje que se complete mediante el proceso de sincronización de la base de datos.

    1.  Crear una extensión para la enumeración **DirSystemRelationshipType** y agregar el nuevo tipo de relación.

    2. Crear un inicializador para este nuevo tipo. Puede encontrar varios ejemplos en el código del núcleo, uno de ellos es **DirRelationshipTypeChildInitialize**. Se trata de una clase de inicializador para el tipo de relación de las partes "Secundaria". Puede empezar con su inicializador copiando y pegando este código y, a continuación, actualizar las áreas resaltadas.
    
    ![Inicializador de DirRelationshipChild.](media/DirRelationship.PNG)

    3.  Para probar a rellenar el nuevo tipo de relación, puede crear una clase ejecutable y denominar DirDataPopulation::insertDirRelationshipTypes() en Main(). Solo debería ver el nuevo tipo de relación en **DirRelationshipTypeTable** y el nuevo tipo de relación estará disponible en la página **Tipos de relación** .

        ![Clase ejecutable.](media/Runnable.PNG)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
