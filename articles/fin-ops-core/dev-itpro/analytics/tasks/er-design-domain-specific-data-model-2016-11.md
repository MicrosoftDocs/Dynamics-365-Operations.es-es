---
title: CE Diseñar el modelo de datos específico de dominio
description: Este artículo describe cómo crear una nueva configuración de informes electrónicos (ER) que contiene un modelo de datos para documentos de pago electrónicos.
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
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERDataContainerDescriptorReferenceSwitchDialog
ms.openlocfilehash: 6116ee7bc65aa72f655aa3e5d1467560792bd024
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291126"
---
# <a name="er-design-domain-specific-data-model"></a>CE Diseñar el modelo de datos específico de dominio

[!include [banner](../../includes/banner.md)]

En los pasos siguientes se explica cómo un usuario con rol de administrador del sistema o desarrollador de informes electrónicos puede crear una nueva configuración de informes electrónicos que contenga un modelo de datos para los documentos de pago electrónico. Este modelo de datos se usará posteriormente como origen de datos al crear el formato de los documentos de pago.

En este ejemplo, creará una configuración para la empresa de demostración, Litware, Inc. Estos pasos se pueden realizar en cualquier empresa a medida que las configuraciones de ER se comparten entre las empresas. Para completar estos pasos, primero debe completar los pasos del procedimiento "Creación y activación de un proveedor de configuraciones".

1. Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.

    Seleccione el proveedor de configuración de la empresa de ejemplo, "Litware, Inc". Si no ve a este proveedor de configuración, primero debe completar los pasos del procedimiento "Creación de un proveedor de configuración y marcarlo como activo".  
    
2. Haga clic en Configuraciones de informes.

    Creará una configuración que contenga un modelo de datos para los documentos de pago electrónico. Este modelo de datos se usará posteriormente como origen de datos cuando cree el formato para los documentos de pago.  

## <a name="create-a-new-data-model-configuration"></a>Creación de un nuevo modelo de configuración de datos
1. Haga clic en Crear configuración para abrir el cuadro de diálogo desplegable.
2. En el campo Nombre, escriba Pagos (modelo simplificado).
3. En el campo Descripción, escriba Configuración del modelo de pago.

    El proveedor de configuraciones activo se especifica automáticamente aquí. Este proveedor podrá mantener esta configuración. Otros proveedores podrán usar esta configuración, pero no podrán mantenerla.  

4. Haga clic en el botón "Crear configuración" para completar la tarea de creación de la configuración

## <a name="create-a-data-model"></a>Creación de un modelo de datos
Usted está creando un nuevo modelo de datos para la configuración seleccionada. Esta versión de la configuración tendrá un estado de borrador.  
1. Haga clic en Diseñador.

## <a name="define-the-structure-of-a-party-participating-in-a-payment-process"></a>Definición de la estructura de una parte que participa en un proceso de pago
1. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
2. Escriba "Parte" en el campo Nombre.
3. Haga clic en Agregar.
4. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
5. En el campo Nombre, escriba "Nombre".
6. En el campo Tipo de artículo, seleccione Cadena.
7. Haga clic en Agregar.
8. Escriba "Parte" en el campo Buscar.
9. Haga clic en Buscar anterior.

## <a name="define-the-bank-structure-for-this-model"></a>Definición de la estructura bancaria para este modelo
1. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
2. En el campo Nombre, escriba "Agente".
3. En el campo Tipo de artículo, seleccione Registro.
4. Haga clic en Agregar.
5. En el campo Descripción, escriba "Entidad financiera (por ejemplo, un banco) que proporciona una cuenta a una de las partes (deudor/acreedeor).

    Entidad financiera (por ejemplo, un banco) que proporciona una cuenta a una de las partes (deudor/acreedor).  

6. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
7. En el campo Nombre, escriba "Nombre". 
8. En el campo Tipo de artículo, seleccione Cadena.
9. Haga clic en Agregar.
10. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
11. En el campo Nombre, escriba "SWIFT'.
12. Haga clic en Agregar.
13. En el campo Descripción, escriba un "código de identificación del Banco". 
14. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
15. En el campo Nombre, especifique "RoutingNumber".
16. Haga clic en Agregar.
17. En el campo Descripción, especifique un "Número de ruta".
18. Haga clic en Buscar anterior.

## <a name="define-the-bank-account-structure-for-this-model"></a>Definición de la cuenta bancaria para este modelo
1. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
2. En el campo Nombre, escriba "Cuenta". 
3. En el campo Tipo de artículo, seleccione Registro.
4. Haga clic en Agregar.
5. En el campo Descripción, escriba "Identificación de una cuenta de una parte en una entidad financiera (por ejemplo, un banco)".

    Identificación de una cuenta de una parte en una entidad financiera (por ejemplo, un banco).  

6. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
7. En el campo Nombre, escriba "Divisa". 
8. En el campo Tipo de artículo, seleccione Cadena.
9. Haga clic en Agregar.
10. En el campo Descripción, especifique un "Código de moneda".
11. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
12. En el campo Nombre, escriba "Número". 
13. Haga clic en Agregar.
14. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
15. En el campo Nombre, escriba "IBAN". 
16. Haga clic en Agregar.
17. En el campo descripción, escriba "Número de cuenta bancaria internacional".

## <a name="define-the-payment-message-structure-for-credit-transfer-payment-type"></a>Definición de la estructura del mensaje de pago para el tipo de pago de transferencia de crédito.
1. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
2. En el campo "Nuevo nodo como", escriba "Raíz del modelo".
3. En el campo Nombre, escriba "CustomerCreditTransferInitiation".
4. Haga clic en Agregar.
5. En el campo Buscar, escriba "CustomerCreditTransferInitiation". 
6. Haga clic en Buscar anterior.
7. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
8. En el campo Nombre, escriba "MessageIdentification". 
9. Haga clic en Agregar.
10. En el campo Descripción, escriba "La referencia punto a punto asignada por la parte ordenante (y enviada a la siguiente parte) para identificar un mensaje".

    La referencia punto a punto asignada por la parte ordenante (y que se envía a la siguiente parte) para identificar un mensaje.  

11. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
12. En el campo Nombre, escriba "ProcessingDateTime".
13. En el campo Tipo de artículo, seleccione DateTime.
14. Haga clic en Agregar.
15. En el campo Descripción, escriba "Fecha y hora de creación del mensaje de pago". 
16. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.

    Definición de la estructura de transacción de pago para este modelo.  

17. En el campo Nombre, escriba "Pagos".
18. En el campo Tipo de artículo, seleccione Lista de registros.
19. Haga clic en Agregar.
20. En el campo Descripción, especifique Líneas de pago del mensaje actual.
21. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
22. En el campo Nombre, escriba "Acreedor". 
23. En el campo Tipo de artículo, seleccione Registro.
24. Haga clic en Agregar.
25. En el campo Descripción, escriba "Parte a la que se debe una suma de dinero". 
26. Haga clic en Cambiar referencia del artículo.
27. Escriba "Parte" en el campo Buscar.
28. Haga clic en Buscar siguiente.
29. Haga clic en Aceptar.
30. En el campo Buscar, escriba "Pagos".
31. Haga clic en Buscar siguiente.
32. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
33. En el campo Nombre, escriba "Deudor". 
34. Haga clic en Agregar.
35. En el campo Descripción, escriba "Parte que adeuda una suma de dinero al (último) acreedor".
36. Haga clic en Cambiar referencia del artículo.
37. Escriba "Parte" en el campo Buscar.
38. Haga clic en Buscar siguiente.
39. Haga clic en Aceptar.
40. Haga clic en Buscar siguiente.
41. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
42. En el campo Nombre, escriba "Descripción".
43. En el campo Tipo de artículo, seleccione Cadena.
44. Haga clic en Agregar.
45. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
46. En el campo Nombre, escriba "Divisa".
47. Haga clic en Agregar.
48. En el campo Descripción, especifique un "Código de moneda".
49. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
50. En el campo Nombre, escriba "TransactionDate". 
51. En el campo Tipo de artículo, seleccione Fecha.
52. Haga clic en Agregar.
53. En el campo Descripción, escriba una "Fecha de transacción". 
54. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
55. En el campo Nombre, escriba "InstructedAmount".  
56. En el campo Tipo de artículo, seleccione Real.
57. Haga clic en Agregar.
58. En el campo Descripción, escriba "La suma de dinero que se transferirá entre el deudor y el acreedor, antes de la deducción de cargos". El importe se debe expresar en la divisa solicitada por la parte iniciadora."

    La suma de dinero que se transferirá entre el deudor y el acreedor, antes de la deducción de cargos. El importe se debe expresar en la divisa solicitada por la parte iniciadora.  

59. Haga clic en Nueva para abrir el cuadro de diálogo desplegable.
60. En el campo Nombre, escriba "End2EndID". 
61. En el campo Tipo de artículo, seleccione Cadena.
62. Haga clic en Agregar.
63. En el campo Descripción, escriba "La identificación única asignada por la parte iniciadora". Esta identificación se pasa, sin cambios, por la cadena completa, de extremo a extremo". 
64. En el campo Nombre, especifique "PaymentModel".

    El nombre del modelo de pago se alinea con las interfaces predefinidas de los formularios de pago.  

65. Haga clic en Guardar.
66. Cierre la página.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
