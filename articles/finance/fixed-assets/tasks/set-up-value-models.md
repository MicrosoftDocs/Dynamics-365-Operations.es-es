---
title: Configuración de modelos de valor
description: Este procedimiento muestra cómo crear un nuevo libro de activos fijos y asociarlo con un grupo de activos fijos.
author: moaamer
ms.date: 12/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, AssetGroupBookSetup
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 71d256b600956a4e525cde626c958713f6258f5a
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2022
ms.locfileid: "8727072"
---
# <a name="set-up-value-models"></a>Configuración de modelos de valor

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../../includes/preview-banner.md)]

Este procedimiento muestra cómo crear un nuevo libro de activos fijos y asociarlo con un grupo de activos fijos.

## <a name="create-a-book"></a>Crear un libro
1. Vaya a **Activos fijos \> Configuración \> Libros**.
2. Seleccione **Nuevo**.
3. En el campo **Libro**, escriba un valor.
4. En el campo **Descripción**, especifique un valor.
5. Establezca la opción **Calcular depreciación** en **Sí**.

    Si la opción **Calcular depreciación** se establece en **Sí** para que el libro del activo asociado se incluya en las propuestas de depreciación. Si se establece en **No**, el libro de activos no se depreciará automáticamente.

6. En el campo **Método de depreciación**, especifique o seleccione un valor.

    * Un método de depreciación alternativo también se conoce como método de cambio de depreciación. La propuesta de depreciación cambiará a este perfil cuando el perfil alternativo calcule un importe de depreciación que sea mayor o igual que el perfil de depreciación predeterminado.
    * El método de depreciación extraordinaria que se usa para la depreciación adicional de un activo en circunstancias inusuales. Por ejemplo, puede usar esta opción para registrar la depreciación que se produzca a causa de un desastre natural.
    * Si selecciona **Crear ajustes de depreciación con ajustes de base**, los ajustes de depreciación se crearán automáticamente cuando se actualice el valor del activo. De lo contrario, el valor del activo actualizado afectará solo a los cálculos de depreciación futuros.

7. Establezca la opción **Crear ajustes de depreciación con ajustes de base** en **Sí**.

    * De forma predeterminada, las transacciones del libro de activos fijos se registran en la contabilidad general. No obstante, también puede deshabilitar el registro del libro en la contabilidad general configurando la opción **Registrar en el libro mayor** en **No**. Los libros que no se registran en la contabilidad general se suelen para informes tributarios. Esta opción proporciona más flexibilidad para eliminar las transacciones históricas para el libro de activos, ya que no se han asignado a la contabilidad general.
    * De forma predeterminada, el campo **Capa de registro** se establece en **Capa actual** si el libro se registra en la contabilidad general y en **Ninguna** si no se registra en la contabilidad general. Actualice el valor del campo **Capa de registro** si las transacciones de este libro se deben registrar en una capa diferente.

8. Calcule la depreciación positiva.

    * De forma predeterminada, la opción **Calcular la depreciación positiva** se establece en **No**. Este ajuste indica que la depreciación se acreditará al libro de activos seleccionado. Asimismo, las opciones **Permitir un valor neto en los libros superior al precio de adquisición** y **Permitir un valor neto en los libros negativo** se establecen en **No** y los ajustes se pueden cambiar independientemente. 
    * Para calcular la depreciación positiva, establezca la opción **Calcular la depreciación positiva** en **Sí**. Este ajuste indica que la depreciación se cargará en el libro de activos fijos. Cuando la opción **Calcular la depreciación positiva** se establece en **Sí**, las opciones **Permitir un valor neto en los libros superior al precio de adquisición** y **Permitir un valor neto en los libros negativo** se establecerán automáticamente en **Sí** y se bloquearán. Este bloqueo ayuda a asegurar que la depreciación positiva se aplicará solo a los activos fijos que se adquirieron con un valor en los libros negativo (crédito). 

10. En el campo **Calendario**, especifique o seleccione un valor.

    Los libros derivados registran las transacciones en distintos libros al mismo tiempo. Puede crear transacciones con el libro principal y durante el registro, una copia precisa de la transacción se registra en el libro derivado. No hay cálculo con transacciones del libro derivadas, por lo que no se va a utilizar para las transacciones de depreciación.

## <a name="associate-the-book-with-a-fixed-asset-group"></a>Asociar el libro con un grupo de activos fijos

1. Seleccione **Grupos de activos fijos**.
2. En el campo **Grupo de activos fijos**, escriba o seleccione un valor.
3. En el campo **Tiempo de vida**, introduzca un número.

    * Los períodos de depreciación se calculan después de introducir el tiempo de vida del activo.
    * Puede establecer la convención de depreciación según sea necesario para fines de impuestos.
    * Para los activos fijos asociados con arrendamientos, el valor del campo **Tiempo de vida** se anulará por el menor entre el plazo de arrendamiento en el libro de activos o la vida útil del activo. Si la opción **Transferencia de la propiedad** está configurada en **Sí** para el libro de arrendamiento, el valor del campo **Tiempo de vida** siempre será la vida útil del activo.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
