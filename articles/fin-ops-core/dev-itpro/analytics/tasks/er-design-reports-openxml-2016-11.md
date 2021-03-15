---
title: ER Diseña una configuración para generar informes en formato OPENXML (noviembre de 2016)
description: Este tema describe cómo crear una nueva configuración de informes electrónicos que contiene una plantilla para generar documentos electrónicos en formato OPENXML.
author: NickSelin
manager: AnnBe
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERDataSourceAddDropDialog, ERModelGroupByFunctionEditor, VendPaymMode, LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3b832961061d05e3f1ae046f820bc7a37baaf90c
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092675"
---
# <a name="er-design-a-configuration-for-generating-reports-in-openxml-format-november-2016"></a>ER Diseña una configuración para generar informes en formato OPENXML (noviembre de 2016)

[!include [banner](../../includes/banner.md)]

En este tema se explica cómo un usuario con rol de administrador del sistema o desarrollador de informes electrónicos puede crear una nueva configuración de informes electrónicos que contenga una plantilla para generar documentos electrónicos en formato OPENXML. Esta configuración se usará para procesar los pagos de proveedor.

En este ejemplo, creará una configuración para la empresa de demostración, Litware, Inc. Estos pasos se pueden realizar en empresa GBSI.

Para completar estos pasos, primero debe completar los pasos del procedimiento "Creación y activación de un proveedor de configuraciones". También debe tener un archivo Excel que se importará el crear la plantilla. A este archivo se obtiene acceso desde la [Plantilla de informe de pago](https://go.microsoft.com/fwlink/?linkid=862266).


## <a name="upload-the-payments-data-model-configuration"></a>Cargar la configuración del modelo de datos de pagos
1. En el Panel de exploración, vaya a **Módulos > Administración de la organización > Espacios de trabajo > Informes electrónicos**.
2. En la lista, marque el proveedor de la configuración de la empresa de ejemplo, Litware, Inc. Si no ve a este proveedor de configuración, primero debe completar los pasos del procedimiento [Crear y activar proveedores de configuraciones](er-configuration-provider-mark-it-active-2016-11.md).
3. Seleccione **Definir como activo**.
4. Seleccione **Repositorios**. Seleccione un repositorio para el tipo de recursos de operaciones, si está disponible. Si está disponible, omita los siguientes pasos acerca de la creación de un nuevo repositorio.  
5. Seleccione **Agregar** para abrir el cuadro desplegable.
6. En el campo **Repositorio de configuración**, escriba `Operations resourcesdd`.
7. Seleccione **Crear repositorio**.
8. Seleccione **Aceptar**.
9. Seleccione **Abrir**.
10. En el árbol, seleccione **Modelo de pago**.
11. Seleccione **Importar**. Importe este modelo de datos. Se usará como origen de datos en una nueva configuración de formato. Omita este paso si esta configuración ya se ha importado.  
12. Seleccione **Sí**.
13. Cierre las páginas hasta que vuelva a la página Informes electrónicos.

## <a name="create-a-new-format-configuration"></a>Creación de una configuración de formato nueva
1. Seleccione **Configuraciones de informes**.
2. En el árbol, seleccione **Modelo de pago**.
3. Seleccione **Crear configuración** para abrir el cuadro de diálogo desplegable.
4. En el campo **Nuevo**, escriba `Format based on data model PaymentModel`. Cree un formato que se base en el modelo de datos de PaymentModel.
5. En el campo **Nombre**, escriba `Sample worksheet report`. Informe de hoja de cálculo de muestra  
6. En el campo **Descripción**, escriba `Sample worksheet report for vendors' payments`, Informe de hoja de cálculo para pagos de proveedores.  
7. En el campo **definición del modelo de Datos**, introduzca o seleccione un valor. Seleccione la definición **CustomerCreditTransferInitiation**.  
8. Seleccionar **Crear configuración**.

## <a name="design-a-new-document-in-openxml-worksheet-format"></a>Diseñar un documento nuevo en formato de hoja de cálculo OPENXML
1. En el árbol, seleccione **Modelo de pago\Informe de hoja de cálculo de muestra**.
2. Seleccione **Diseñador**.
3. En el panel de acciones, seleccione **Importar**.
4. Seleccione **Importar desde Excel**.
5. Seleccione **Archivos adjuntos**. Adjunte el documento de Excel existente como plantilla.  
6. Seleccione **Nuevo**.
7. Seleccione **Archivo**. Señale al archivo de Excel existente.  
8. Cierre la página.
9. En el campo **Plantilla**, especifique o seleccione un valor. Seleccione el archivo de Excel adjunto que se usará como plantilla.  
10. Seleccione **Aceptar**. Tenga en cuenta que los componentes en formato ER se han creado en el formato de diseño basado en la estructura del documento de MS Excel de referencia (intervalos con nombre).  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a>Crear un nuevo origen de datos para calcular totales por códigos de divisa
1. Seleccione la pestaña **Asignación**.
2. Seleccione **Agregar raíz** para abrir el cuadro de diálogo desplegable.
3. En el árbol, seleccione **Funciones\Agrupar por**.
4. En el campo **Nombre**, escriba `PaymentByCurrency`.
5. Seleccione **Editar grupo por**.
6. En el árbol, expanda **modelo** y, a continuación, seleccione **modelo\Pagos**.
7. Seleccione **Agregar campo a**.
8. Seleccione **Elementos para agrupar**.
9. En el árbol, expanda **modelo\Pagos** y, a continuación, seleccione **modelo\Pagos\Moneda**.
10. Seleccione **Agregar campo a**.
11. Seleccione **Campos agrupados**.
12. En el árbol, seleccione **modelo\Pagos\Importe ordenado(InstructedAmount)**.
13. Seleccione **Agregar campo a** y, a continuación, seleccione **Campos de agregación**.
14. En el campo **Método**, seleccione una opción. Seleccione la función de **agregación SUMA**.  
15. En el campo **Nombre**, escriba `TotalInstructuredAmount`.
16. Seleccione **Guardar**.
17. Cierre la página.
18. Seleccione **Aceptar**.

## <a name="map-format-components-to-data-sources"></a>Asignar componentes de formato a orígenes de datos
1. En el árbol, seleccione **modelo\Pagos\Parte iniciadora(InitiatingParty)\Nombre** y **Excel\ReportHeader\CompanyName**.
2. Seleccione **Enlazar**.
3. En el árbol, seleccione **modelo\Pagos\Cuenta de acreedor(Creditor)\Identification\Source ID(SourceID)** y **Excel\PaymLines\VendAccountName**.
4. Seleccione **Enlazar**.
5. En el árbol, seleccione **modelo\Pagos\Acreedor\Nombre** y **Excel\PaymLines\VendName**.
6. Seleccione **Enlazar**.
7. En el árbol, seleccione **modelo\Pagos\Agente de acreedor(CreditorAgent)\Nombre** y **Excel\PaymLines\Banco**.
8. Seleccione **Enlazar**.
9. En el árbol, seleccione **modelo\Pagos\Agente de acreedor(CreditorAgent)\Número de ruta(RoutingNumber)** y **Excel\PaymLines\RoutingNumber**.
10. Seleccione **Enlazar**.
11. En el árbol, seleccione **modelo\Pagos\Cuenta de acreedor(CreditorAccount)\Identificación\Número** y **Excel\PaymLines\AccountNumber**.
12. Seleccione **Enlazar**.
13. En el árbol, seleccione **modelo\Pagos\Importe ordenado(InstructedAmount)** y **Excel\PaymLines\Débito**.
14. Seleccione **Enlazar**.
15. En el árbol, seleccione **modelo\Pagos\Divisa** y **Excel\PaymLines\Divisa**.
16. Seleccione **Enlazar**.
17. En el árbol, seleccione **PaymentByCurrency\agrupado\Divisa** y **Excel\SummaryLines\SummaryCurrency**.
18. Seleccione **Enlazar**.
19. En el árbol, seleccione **PaymentByCurrency\agregado\TotalInstructuredAmount** y **Excel\SummaryLines\SummaryAmount**.
20. Seleccione **Enlazar**.
21. En el árbol, seleccione **PaymentByCurrency** y **Excel\SummaryLines**.
22. Seleccione **Enlazar**.
23. En el árbol, seleccione **modelo\Pagos** y **Excel\PaymLines**.
24. Seleccione **Enlazar**.
25. Haga clic en **Guardar** y, a continuación, cierre la página.

## <a name="use-the-created-configuration-for-payments-processing"></a>Usar la configuración creada para procesar los pagos
1. Seleccione **Cambiar estado**.
2. Seleccione **Completar**.
3. Seleccione **Aceptar**.
4. En el Panel de exploración, vaya a **Módulos > Proveedores > Configuración de pagos > Métodos de pago**.
5. Use el Filtro Rápido para filtrar el campo **Método de pago** con un valor de **Electronic**.
6. Seleccione **Editar**.
7. Expanda la sección **Formatos de archivo**.
8. Seleccione **Sí** en el campo **Informes electrónicos genéricos**.
9. En el campo **Configuración de formato de exportación**, especifique o seleccione un valor. Seleccione la configuración **Informe de hoja de cálculo de muestra**.  
10. Seleccione **Guardar**.
11. Cierre la página.

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a>Usar la configuración creada para probar el procesamiento de diarios de pago
1. En el Panel de exploración, vaya a **Módulos > Proveedores > Pagos > Diario de pagos**.
2. Seleccionar **Nuevo** para crear un diario de pagos.
3. En el campo **Nombre**, escriba **VendPay**.
4. Seleccionar **Líneas**.
5. En el campo **Cuenta**, especifique los valores `GB_SI_000001`.
6. Establezca **Débito** en `1000`.
7. Seleccione **Nuevo**.
8. En el campo **Cuenta**, especifique los valores `GB_SI_000005`.
9. Establezca **Débito** en `2000`.
10. En el campo **Divisa**, escriba `EUR`.
11. En el campo **Cuenta de contrapartida**, especifique los valores `GBSI OPER`.
12. En el campo **Método de pago**, escriba `Electronic`.
13. Seleccione **Guardar**.
14. Seleccione **Generar pagos**.
15. En el campo **Método de pago**, escriba `Electronic`.
16. En el campo **Nombre de archivo**, escriba `Payments`.
17. En el campo **Cuenta bancaria**, escriba `GBSI OPER`.
18. Seleccione **Aceptar** y, a continuación, vuelva a seleccionar **Aceptar**. Revise la hoja de trabajo creada, incluidos los detalles de líneas de pago así como los totales para cada código de divisa usado en este mensaje de pago.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]