---
title: Preguntas frecuentes sobre informes financieros
description: En este tema se proporcionan respuestas a algunas de las preguntas más frecuentes sobre los informes financieros.
author: jiwo
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e1b67f86446403933005008a9a1e2cc6739dc516
ms.sourcegitcommit: ecabf43282a3e55f1db40341aa3f3c7950b9e94c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2021
ms.locfileid: "6266642"
---
# <a name="financial-reporting-faq"></a>Preguntas frecuentes sobre informes financieros

En este tema se proporcionan respuestas a las preguntas más frecuentes sobre los informes financieros.

## <a name="how-do-i-restrict-access-to-a-report-by-using-tree-security"></a>¿Cómo puedo restringir el acceso a un informe mediante seguridad de árbol?

En el siguiente ejemplo se muestra cómo restringir el acceso a un informe mediante seguridad de árbol.

La empresa de demostración USMF tiene un informe de **balance de situación** al que no todos los usuarios de informes financieros deberían tener acceso. Solución: puede utilizar la seguridad de árbol para restringir el acceso a un solo informe, de modo que solo usuarios específicos puedan acceder a él.

1. Iniciar sesión en Financial Reporter Report Designer.
2. Seleccione **Archivo \> Nuevo \> Definición de árbol** para crear una nueva definición de árbol.
3. Toque dos veces (o haga doble clic) en la línea **Resumen** de la columna **Seguridad de la unidad**.
4. Seleccione **Usuarios y grupos**.
5. Seleccione los usuarios o grupos a los que debe conceder acceso al informe.
6. Seleccione **Guardar**.
7. En la definición del informe, agregue su nueva definición de árbol.
8. En la definición del árbol, seleccione **Configuración**. Luego, en **Selección de unidad de informes**, seleccione **Incluir todas las unidades**.

## <a name="how-do-i-identify-which-accounts-dont-match-my-balances"></a>¿Cómo identifico qué cuentas no coinciden con mis saldos?

Si cuenta con un informe que no tiene saldos coincidentes, use los siguientes procedimientos para identificar cada cuenta y desviación.

### <a name="in-financial-reporter-report-designer"></a>En Financial Reporter Report Designer

1. Cree una nueva definición de fila.
2. Seleccione **Editar \> Insertar filas desde Dimensiones**.
3. Seleccione **MainAccount**.
4. Seleccione **Aceptar**.
5. Guarde la definición de fila.
6. Cree una nueva definición de columna.
7. Cree una nueva definición de informe.
8. Seleccione **Ajustes** y desmarque esta opción.
9. Genere el informe. 
10. Exporte el informe a Microsoft Excel.

### <a name="in-dynamics-365-finance"></a>En Dynamics 365 Finance

1. Vaya a **Contabilidad general \> Consultas e informes \> Saldo de comprobación**.
2. Establezca los campos siguientes:

    - **Fecha inicial**: introduzca la fecha de inicio del ejercicio.
    - **Fecha final**: introduzca la fecha para la que está generando el informe.
    - **Dimensión financiera**: establezca este campo en **Conjunto de cuenta principal**.

3. Seleccione **Calcular**.
4. Exportar el informe a Excel.

Ahora debería poder copiar los datos desde el informe de Excel de Financial Reporter al informe **Saldo de comprobación**, de modo que puede comparar las columnas **Saldo de cierre**.

## <a name="when-i-design-a-report-in-report-designer-or-when-i-generate-a-financial-report-i-received-the-following-message-the-operation-could-not-be-completed-due-to-a-problem-in-the-data-provider-framework-how-should-i-respond"></a>Cuando diseño un informe en Report Designer o cuando genero un informe financiero, recibo el siguiente mensaje: "La operación no se pudo completar debido a un problema en el marco del proveedor de datos". ¿Cómo debo responder?

El mensaje indica que se produjo un problema cuando el sistema intentó recuperar metadatos financieros del data mart mientras usaba Financial Reporting. Hay dos formas de responder a este problema:

- Revise el estado de integración de los datos yendo a **Herramientas \> Estado de integración** en Report Designer. Si la integración está incompleta, espere a que se complete. Luego, vuelva a intentar lo que estaba haciendo cuando recibió el mensaje.
- Póngase en contacto con el servicio de asistencia para identificar y solucionar el problema. Puede haber datos incoherentes en el sistema. Los ingenieros de soporte pueden ayudarle a identificar ese problema en el servidor y encontrar datos específicos que pueden requerir una actualización.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
