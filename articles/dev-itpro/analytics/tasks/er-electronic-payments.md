--- 
title: "Generar documentos electrónicos para pagos mediante una configuración de formato para informes electrónicos (ER)"
description: "En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o desarrollador de informes electrónicos puede usar una nueva configuración de formato de informes electrónicos para generar documentos electrónicos para procesar pagos."
author: NickSelin
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: a5d958d3b55bfa76f3cfbb3c1a289e4e89c49146
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="generate-electronic-documents-for-payments-using-a-format-configuration-for-electronic-reporting-er"></a>Generar documentos electrónicos para pagos mediante una configuración de formato para informes electrónicos (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o desarrollador de informes electrónicos puede usar una nueva configuración de formato de informes electrónicos para generar documentos electrónicos para procesar pagos. Estos pasos se pueden llevar a cabo en la empresa de muestra de GBSI.

Para completar estos pasos, primero debe completar los pasos del procedimiento "Creación de una configuración con formato de documento de pago".


## <a name="change-the-configuration-of-the-electronic-payment-method"></a>Cambiar la configuración del método de pago electrónico
1. Vaya a Proveedores > Configuración de pagos > Formas de pago.
2. Alterne la sección de Formato de archivo para ampliarla, si es necesario.
3. Use el filtro rápido para buscar registros. Por ejemplo, filtre por el campo Forma de pago, por el valor "Electrónico".
4. Haga clic en Editar.
5. Establezca el campo de informes electrónicos generales en Sí.
    * Seleccione Sí para usar el modelo de informes electrónicos generales para la generación de archivos de pago.  
6. En el campo Nombre, haga clic en el botón desplegable para abrir la búsqueda.
7. Seleccione la configuración de formato BACS (ficticio Reino Unido).
8. Haga clic en Guardar.
9. Cierre la página.

## <a name="test-the-format-of-generated-payment-files"></a>Probar el formato de archivos de pago generados
1. Vaya a Proveedores > Pagos > Diario de pagos.
2. Haga clic en Nuevo.
3. En la lista, marque la fila seleccionada.
4. En el campo Nombre, haga clic en el botón desplegable para abrir la búsqueda.
5. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Seleccione VendPay.  
6. Haga clic en Guardar.
7. Haga clic en Líneas.
8. En el campo Empresa, escriba "DEMF".
    * DEMF  
9. En el campo Cuenta, especifique los valores "DE-01001".
    * DE - 01001  
10. En el campo Descripción, escriba "Pago".
    * Pago  
11. En el campo Débito, escriba un número.
    * 1000  
12. Haga clic en la ficha Pago.
13. En el campo Forma de pago, haga clic en el botón desplegable para abrir la búsqueda.
14. En la lista, busque y seleccione el registro deseado.
    * Seleccione el valor electrónico.  
15. En la lista, haga clic en el vínculo de la fila seleccionada.
16. Haga clic en Guardar.
17. Haga clic en Generar pagos.
18. En el campo Forma de pago, haga clic en el botón desplegable para abrir la búsqueda.
19. En la lista, busque y seleccione el registro deseado.
    * Seleccione el valor electrónico.  
20. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Seleccione el valor electrónico.  
21. En el campo Nombre de archivo, escriba un valor.
    * Por ejemplo, escriba "pagos".  
22. En el campo Cuenta bancaria, haga clic en el botón desplegable para abrir la búsqueda.
23. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Seleccione el valor GBSI OPER.  
24. Haga clic en Aceptar
25. Haga clic en Aceptar
    * Analice el archivo de pago creado en formato XML. Compárelo con el diseño de documento y los atributos de transacción de pago definidos.  


