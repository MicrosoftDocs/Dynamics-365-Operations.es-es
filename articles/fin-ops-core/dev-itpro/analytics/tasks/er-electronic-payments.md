---
title: ER Generar documentos electrónicos para pagos con una configuración de formato
description: Este artículo describe cómo usar una nueva configuración de formato de informes electrónicos (ER) para generar documentos electrónicos para el procesamiento de pagos.
author: kfend
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: VendPaymMode, LedgerJournalTable, LedgerJournalTransVendPaym, BankAccountTableLookUp
ms.openlocfilehash: b70b246e3618e8f083e5f6757ee8a97d8072a635
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290886"
---
# <a name="er-generate-electronic-documents-for-payments-using-a-format-configuration"></a>ER Generar documentos electrónicos para pagos con una configuración de formato

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
