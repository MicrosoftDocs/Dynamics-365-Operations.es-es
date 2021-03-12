---
title: Registro de artículos habilitados para almacenamiento avanzado mediante un diario de recepción de artículos
description: Este procedimiento muestra cómo registrar artículos mediante el diario de recepción de artículos cuando se usa los procesos avanzados de gestión de almacenes.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSJournalTable, WMSJournalCreate, WHSLicensePlate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0f05034454002fa9c4161b8f2d6cafdaeaa24d32
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977097"
---
# <a name="register-items-for-an-advanced-warehousing-enabled-item-using-an-item-arrival-journal"></a>Registro de artículos habilitados para almacenamiento avanzado mediante un diario de recepción de artículos

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo registrar artículos mediante el diario de recepción de artículos cuando se usa los procesos avanzados de gestión de almacenes. Esto lo realiza normalmente un empleado de recepción. 

Puede realizar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos. Necesita tener un pedido de compra confirmado con una línea de pedido de compra abierta antes de comenzar esta guía. El artículo en la línea debe estar en existencias, no debe usar variantes de producto y no debe tener dimensiones de seguimiento. El artículo debe estar asociado con un grupo de dimensiones de almacenamiento habilitado con proceso de gestión de almacenes. El almacén que se usa debe estar habilitado para los procesos de gestión de almacén y la ubicación que usa para recepción debe controlada por matrículas de entidad de almacén. Si está usando USMF, puede usar la cuenta de empresa 1001, el almacén 51 y el artículo M9200 para crear su pedido de compra. 

Anote el número de pedido de compra que cree y también tenga en cuenta el código de artículo y el sitio que usó para la línea de pedido de compra.


## <a name="create-an-item-arrival-journal-header"></a>Creación de un encabezado del diario de recepción de artículos
1. Vaya a Recepción de artículos.
2. Haga clic en Nuevo.
3. En el campo Nombre, escriba un valor.
    * Si está usando USMF, puede escribir WHS. Si está usando otros datos, el diario cuyo nombre elija tiene que tener las siguientes propiedades: Comprobar ubicación de picking debe estar definido en No, y Gestión de cuarentena debe estar definido en No.  
4. En el campo Número, escriba un valor.
5. En el campo Sitio, escriba un valor.
    * Seleccione el sitio que usó para la línea de pedido de compra. Esto servirá como valor predeterminado para todas las líneas del diario. Si ha usado el almacén 51 en USMF, elija el sitio 5.  
6. En el campo Almacén, escriba un valor.
    * Seleccione un almacén válido para el sitio que ha seleccionado. Esto servirá como valor predeterminado para todas las líneas del diario. Si está usando los valores de ejemplo en USMF, seleccione 51.  
7. En el campo Ubicación, escriba un valor.
    * Seleccione una ubicación válida en el almacén que ha seleccionado. La ubicación se tiene que asociar con un perfil de ubicación, que está controlado por matrículas de entidad de almacén. Esto servirá como valor predeterminado para todas las líneas del diario. Si está usando los valores de ejemplo en USMF, seleccione Bulk-008.  
8. Haga clic con el botón secundario en la flecha desplegable del campo Matrícula de entidad de almacén y seleccione a continuación Ver detalles.
9. Haga clic en Nuevo.
10. En el campo Matrícula de entidad de almacén, escriba un valor.
    * Anote el valor.  
11. Haga clic en Guardar.
12. Cierre la página.
13. En el campo Matrícula de entidad de almacén, escriba un valor.
    * Especifique el valor de la matrícula de entidad de almacén que acaba de crear. Esto servirá como valor predeterminado para todas las líneas del diario.  
14. Haga clic en Aceptar

## <a name="add-a-line"></a>Adición de una línea
1. Haga clic en Agregar línea.
2. En el campo Código de artículo, escriba un valor.
    * Especifique el código de artículo que usó en la línea de pedido de compra.  
3. En el campo Cantidad, especifique un número.
    * Escriba la cantidad que desee registrar.  
    * El campo Fecha determina la fecha en la que la cantidad disponible del artículo se registrará en el inventario.  
    * El sistema rellenará el Id. de lote si se puede identificar de forma exclusiva con la información proporcionada. De lo contrario, tendrá que agregar esto manualmente. Esto es un campo obligatorio, que vincula este registro a una línea de documento de origen específica.  

## <a name="complete-the-registration"></a>Completar el registro
1. Haga clic en Validar.
    * Esto comprueba que el diario está listo para registrarse. Si se produce un error en la validación, tendrá que corregir los errores para poder registrar el diario.  
2. Haga clic en Aceptar
    * Una vez que haya hecho clic en Aceptar, compruebe el mensaje. Debe haber un mensaje que indica que el diario es correcto.  
3. Haga clic en Registrar.
4. Haga clic en Aceptar
    * Una vez que haya hecho clic en Aceptar, compruebe la barra de mensajes. Debe haber un mensaje que indica que se ha completado la operación.  
5. Cierre la página.

