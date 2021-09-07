---
title: Configuración de modelos de valor
description: Este procedimiento muestra cómo crear un nuevo libro de activos fijos y asociarlo con un grupo de activos fijos.
author: moaamer
ms.date: 08/12/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, AssetGroupBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 46c26e5fad3c5c60d87c2fea2b29043c69b82b5d
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "7344667"
---
# <a name="set-up-value-models"></a>Configuración de modelos de valor

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../../includes/preview-banner.md)]


Este procedimiento muestra cómo crear un nuevo libro de activos fijos y asociarlo con un grupo de activos fijos. Usa el rol de contable y los datos de prueba de la entidad jurídica USMF.

## <a name="create-a-book"></a>Crear un libro
1. Vaya a Activos fijos > Configuración > Libros.
2. Haga clic en Nuevo.
3. En el campo Libro, escriba un valor.
4. En el campo Descripción, escriba un valor.
    * Si se selecciona Calcular depreciación, el libro de activos asociado se incluirán en las propuestas de depreciación. Si no se selecciona, el libro de activos no se depreciará automáticamente.  
5. Seleccione Sí en el campo Calcular depreciación.
6. En el campo Método de depreciación, especifique o seleccione un valor.
    * Un método de depreciación alternativo también se conoce como método de cambio de depreciación. La propuesta de depreciación cambiará a este perfil cuando el perfil alternativo calcule un importe de depreciación que sea mayor o igual que el perfil de depreciación predeterminado.  
    * El método de depreciación extraordinaria que se usa para la depreciación adicional de un activo en circunstancias inusuales. Por ejemplo, puede usar esta opción para registrar la depreciación que se produzca a causa de un desastre natural.  
    * Si está activado Crear ajustes de depreciación con ajustes de base, los ajustes de depreciación se crearán automáticamente cuando se actualice el valor del activo. Si no se selecciona, el valor del activo actualizado solo afectará a los cálculos de depreciación a partir de la fecha actual.  
7. Seleccione Sí en el campo Crear ajustes de depreciación con ajustes de base.
    * De forma predeterminada, las transacciones del libro de activos fijos se registran en la contabilidad general. Puede deshabilitar el registro en la contabilidad general para el libro configurando el registro en el campo de contabilidad general en No. Los libros que no se registran en la contabilidad general normalmente se utilizan para fines de informes de impuestos. Esto le da flexibilidad adicional para eliminar las transacciones históricas para el libro de activos ya que no se han confiado a la contabilidad general.  
    * La capa de registro recibe los valores por defecto la capa Actual si el libro se registra en la contabilidad general y Ninguna si no se registra en la contabilidad general. Actualice la capa de registro si necesita que las transacciones de este libro se registren en otra capa.  
8. En el campo Calendario, especifique o seleccione un valor.
    * Los libros derivados registran las transacciones en distintos libros al mismo tiempo. Puede crear transacciones con el libro principal y durante el registro, una copia precisa de la transacción se registra en el libro derivado. No hay cálculo con transacciones del libro derivadas, por lo que no se va a utilizar para las transacciones de depreciación.  

## <a name="associate-the-book-with-a-fixed-asset-group"></a>Asociar el libro con un grupo de activos fijos
1. Haga clic en Grupos de activos fijos.
2. En el campo Grupo de activos fijos, escriba o seleccione un valor.
3. En el campo Tiempo de vida, especifique un número.

  - Los períodos de depreciación se calculan después de introducir el tiempo de vida del activo.  
  - Puede establecer la convención de depreciación según sea necesario para fines de impuestos.
  - Para los activos fijos asociados con arrendamientos, el valor del campo **Tiempo de vida** se anulará por el menor entre el plazo de arrendamiento en el libro de activos o la vida útil del activo. Si el campo **Transferencia de la propiedad** está configurado en **Sí** para el libro de arrendamiento, el valor del campo **Tiempo de vida** siempre será la vida útil del activo.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
