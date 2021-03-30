---
title: Informes de arrendamiento de activos
description: Este tema enumera y describe brevemente los informes que están disponibles en Arrendamiento de activos.
author: moaamer
manager: Ann Beebe
ms.date: 10/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-27
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ab55d778f55c3ec96141c4f868724af1e11aed09
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5229583"
---
# <a name="asset-leasing-reports"></a>Informes de arrendamiento de activos

[!include [banner](../includes/banner.md)]

Este tema enumera y describe brevemente los informes que están disponibles en Arrendamiento de activos. La mayoría de los informes se muestran al completar estos pasos o pasos que son muy similares, como se indica. 

- Para ver la mayoría de los informes de arrendamiento de activos, vaya a **Arrendamiento de activos > Consultas e informes > Informes de arrendamiento** y luego seleccione un informe para verlo. Para los informes que requieren una ruta de selección diferente, los pasos para abrir el informe se incluyen con la descripción de ese informe. 
- Cuando selecciona un informe para imprimir, se abre una página de parámetros que le permite filtrar la información que se incluye en el informe. Introduzca los criterios de filtrado y luego seleccione **Aceptar** para generar el informe. El informe generado mostrará información que se encuentra dentro de los filtros que especificó.

## <a name="asset-movement"></a>Movimiento de activos
El informe de movimiento de activos sirve como un informe de avance para los saldos de activos por derecho de uso para cada arrendamiento. Este informe le permite ver las transacciones de activos de un arrendamiento durante un período específico. El informe incluye los campos siguientes. 

|     Campos de informe                  |     Descripción                                                                |
|------------------------------------|--------------------------------------------------------------------------------|
|     Fecha de inicio              |     La fecha de inicio de la primera versión del arrendamiento.                     |   
|     Plazo del arrendamiento                     |     El plazo del arrendamiento de la primera versión del arrendamiento.                            |
|     Arrendamiento a corto plazo               |     Si el arrendamiento se clasifica como arrendamiento a corto plazo, se mostrará como **Sí**.         |
|     Arrendamiento de bajo valor                |     Si el arrendamiento se clasifica como arrendamiento de bajo valor, se mostrará como **Sí**.          |
|     Activo por derecho de uso inicial     |     El valor original del activo por derecho de uso desde el asiento de diario de reconocimiento inicial.      |
|     Saldo inicial              |     El valor neto en los libros del activo por derecho de uso desde la **Fecha inicial**.                         |
|     Gasto de depreciación del período    |     El importe del gasto de depreciación tomado dentro del rango de fechas definido para el informe.        |
|     Depreciación acumulada       |     El importe de la depreciación acumulada desde la **Fecha inicial**.                               |
|     Deterioro                     |     El importe de depreciación del activo en el rango de fechas definido para el informe.               |
|     Modificaciones                  |     La cantidad de ajustes al activo por derecho de uso entre los parámetros de fecha.                            |
|     Valor neto en los libros                 |     El valor neto contable final del activo por derecho de uso, que es el neto de la depreciación acumulada desde la **Fecha inicial**.    |

## <a name="differences-report"></a>Informe de diferencias
El informe de diferencias muestra las diferencias entre la información cargada en el marco de importación de arrendamiento y la información que se encuentra actualmente en el sistema. Esto le permite comparar lo que se ajustó, actualizó o agregó a través del marco de importación de arrendamiento.  

Los valores del informe variarán según el arrendamiento seleccionado. El informe solo mostrará aquellos campos que difieran de lo que está actualmente en el sistema y lo que está en las tablas de almacenamiento provisional. El valor anterior es lo que está actualmente en el sistema o lo que estaba anteriormente en el sistema, dependiendo de si se ha ejecutado el proceso de importación. El nuevo valor muestra el valor que está en la tabla de almacenamiento provisional que reemplazará al valor anterior.

## <a name="five-years-undiscounted-payment-forecast"></a>Previsión de pago sin descuento a cinco años
El informe de pronóstico de pagos sin descuento a cinco años muestra los pagos por arrendamiento sin descuento proyectados que se pagarán durante los próximos cinco años a partir de la fecha especificada en los parámetros del informe. El informe incluye los campos siguientes. 

|     Campos de informe         |     Descripción                                                                                       |
|-------------------------- |---------------------------------------------------------------------------------------------------    |
|     Descripción del arrendamiento     |     La descripción del arrendamiento del encabezado del arrendamiento.                                                      |
|     Id. de arrendamiento              |     El id. exclusivo del arrendamiento.                                                                              |
|     Reserva                  |     El libro de arrendamiento asociado al id. del libro.                                                         |
|     Clasificación        |     La clasificación del arrendamiento.                                                                  |
|     Capa de registro         |     La capa en la que se registra este arrendamiento.                                                         |
|     Divisa              |     La divisa del arrendamiento.                                                                        |
|     Actuales               |     La suma de todos los pagos por arrendamiento pagaderos dentro de los próximos 12 meses a partir de la fecha del informe.          |
|     13-24 meses          |     La suma de todos los pagos por arrendamiento entre 13 y 24 meses a partir de la fecha del informe.           |
|     25-36 meses          |     La suma de todos los pagos por arrendamiento entre 25 y 36 meses a partir de la fecha del informe.           |
|     37-48 meses          |     La suma de todos los pagos por arrendamiento entre 37 y 48 meses a partir de la fecha del informe.           |
|     49-60 meses          |     La suma de todos los pagos por arrendamiento entre 49 y 60 meses a partir de la fecha del informe.           |
|     Posterior            |     La suma de todos los pagos por arrendamiento en el mes 61 o posteriores a partir de la fecha del informe.              |

## <a name="gaap-cash-flows-report"></a>Informe de flujos de efectivo GAAP
El informe de divulgaciones GAAP satisface el requisito de divulgación de US GAAP especificado en 842-20-50-4(g)(1). Para ver este informe, vaya a **Arrendamiento de activos > Consultas e informes > Divulgaciones > GAAP: flujos de efectivo**. 

|     Campos de informe                                 |     Descripción                                                                                                                                               |
|------------------------------------------------   |-----------------------------------------------------------------------------  |
|     A partir de la fecha <br> Hasta fecha                        |     Define un rango de fechas que se usa para restringir la información incluida en el informe.      |
|     Entidad jurídica                                  |     La entidad jurídica vinculada a los arrendamientos.                                      |
|     Tipo de arrendamiento                                    |     La clasificación del arrendamiento como financiero u operativo.           |
|     Id. de arrendamiento                                      |     El id. exclusivo del arrendamiento.                                                      |
|     Descripción del arrendamiento                             |     La descripción del arrendamiento del encabezado del arrendamiento.                              |
|     Libro de arrendamientos                                    |     El libro de arrendamientos al que se refiere la línea.                        |
|     Capa de registro                                 |     Cada libro vinculado a un activo fijo se configura para una capa de registro concreta que tiene un objetivo de depreciación general.                          |
|     Grupo de arrendamientos                                   |     El grupo al que está asignado el arrendamiento.                                     |
|     Divisa                                      |     La abreviatura de la divisa de transacción usada. Todos los informes convertirán la divisa transaccional a la divisa del informe.                      |
|     Arrendamientos financieros: flujos de efectivo operativos         |     La suma del total de los pagos variables registrados y el total de pagos de intereses registrados del programa de amortización entre los parámetros de fecha.        |
|     Arrendamientos financieros: flujos de efectivo financieros           |     La suma del total de pagos de principal del programa de amortización entre los parámetros de fecha.       |
|     Arrendamientos operativos: flujos de efectivo operativos       |     La suma de todos los pagos de arrendamiento registrados y los pagos variables registrados entre los parámetros de fecha.            |

## <a name="lease-balances-forecast"></a>Previsión de saldos de arrendamiento
El pronóstico de saldos de arrendamiento enumera información directamente desde el programa de amortización de pasivos y el programa de depreciación de activos. El informe muestra los importes previstos del pasivo por arrendamiento proyectado y los activos por derecho de uso durante un período de tiempo, incluidos todos los gastos proyectados para esos arrendamientos. El informe incluye los campos siguientes.

|     Campos de informe                 |     Descripción                                                                                                                                                                               |
|---------------------------------  |--------------------------------------------------------------------------------------------------------------------   |
|     Saldo inicial             |     El saldo inicial en el programa de amortización del arrendamiento para el período que contiene la fecha de inicio del informe.            |
|     Reconocimiento inicial           |     Si la fecha de inicio del arrendamiento cae dentro del rango de fechas definido para el informe, esta columna mostrará el valor de la cuenta de pasivo del asiento de diario de reconocimiento inicial.      |
|     Pagos                      |     La suma de los pagos del arrendamiento que se encuentran dentro del rango de fechas definido para el informe.                               |
|     Interés                      |     La suma de los gastos por intereses del arrendamiento que se encuentran dentro del rango de fechas definido para el informe.                    |
|     Saldo final                |     El saldo del pasivo del arrendamiento a partir de la **Fecha final**.                                                             |
|     Pasivo a corto plazo          |     El importe del pasivo a corto plazo en el programa de amortización del arrendamiento desde la **Fecha final**.                           |
|     Pasivo a largo plazo           |     El importe del pasivo a largo plazo en el programa de amortización del arrendamiento desde la **Fecha final**.                            |
|     Inicio de valor neto      |     El “Inicio de valor neto” en el programa de depreciación de activos del arrendamiento para el período que contiene la fecha de inicio del informe      |
|     Reconocimiento inicial           |     Si la fecha de inicio del arrendamiento cae entre los parámetros de fechas del informe, esta columna mostrará el valor de la cuenta de pasivo del movimiento de diario de reconocimiento inicial.            |
|     Gasto de depreciación          |     La suma de los gastos por depreciación del arrendamiento que se encuentran dentro del rango de fechas definido para el informe.                  |
|     Saldo final                |     El saldo del activo del arrendamiento a partir de la **Fecha final**.                                                              |
|     Ajuste de recursos propios             |     El saldo inicial menos el valor neto inicial.                                                             |

## <a name="lease-commencements-report"></a>Informe de inicios de arrendamientos
El informe de inicios de arrendamientos muestra todos los arrendamientos que han comenzado dentro de un rango de fechas especificado, incluidos el pasivo inicial y los saldos de activos por derecho de uso. El informe incluye los campos siguientes. 

|     Campos de informe                 |     Descripción                                                                                       |
|---------------------------------  |---------------------------------------------------------------------------------------------------    |
|     Fecha de inicio             |     La fecha del movimiento de diario de reconocimiento inicial que se registró para esa versión de arrendamiento.         |
|     Importe de pasivo inicial      |     El importe del pasivo del asiento de diario de reconocimiento inicial.                                  |
|     Importe de activo inicial          |     El importe del activo del movimiento de diario de reconocimiento inicial.                                      |

## <a name="lease-modification-report"></a>Informe de modificación de arrendamiento
El informe de modificación de arrendamiento muestra todos los arrendamientos que se han modificado dentro de un rango de fechas especificado. El informe también muestra el usuario que ajustó el arrendamiento y el importe total de pasivo ajustado. El informe incluye los campos siguientes. 

|     Campos de informe                 |     Descripción           |
|---------------------------------  |-------------------------  |
|     Ajustado por                   |     El nombre de usuario de la persona que modificó el arrendamiento.                                |
|     Fecha de ajuste               |     La fecha en la que se registró el movimiento de diario de ajuste.                        |
|     Ajustes                   |     El importe de cualquier movimiento de diario de ajuste registrado en la cuenta de pasivo del arrendamiento entre los parámetros de fecha. Los créditos aparecerán positivos, mientras que los débitos serán negativos.       |
|     Importe de ganancia (pérdida)            |     El importe de cualquier movimiento de diario de ajuste registrado en la cuenta de ganancias/pérdidas del arrendamiento entre los parámetros de fecha. Los créditos aparecerán positivos, mientras que los débitos serán negativos.       |
|     Ganancias retenidas             |     El importe de cualquier movimiento de diario de ajuste registrado en la cuenta de ingresos retenidos del arrendamiento entre los parámetros de fecha.      |
|     Saldo final del pasivo      |     El saldo del pasivo resultante a partir de la fecha de ajuste del arrendamiento.           |

## <a name="lease-movement-report"></a>Informe de movimientos de arrendamientos
El informe de movimiento de arrendamientos sirve como un informe de avance para los saldos de pasivos por arrendamiento para cada arrendamiento. Este informe permite al usuario ver las transacciones de pasivos de un arrendamiento durante un período específico.

|     Campos de informe             |     Descripción                                               |
|----------------------------   |-------------------------------------------------------------- |
|     Fecha de inicio         |     La fecha de inicio de la primera versión del arrendamiento.    |
|     Plazo del arrendamiento                |     El plazo del arrendamiento de la primera versión del arrendamiento.           |
|     Pagos restantes        |     El número de pagos que aún no se han registrado para el arrendamiento.                       |
|     Saldo inicial         |     La suma de todas las transacciones que afectan el pasivo del arrendamiento que ocurrieron antes de la fecha de inicio del informe.             |
|     Reconocimiento inicial       |     El importe de cualquier transacción de reconocimiento inicial para el arrendamiento que se registró dentro del rango de fechas definido para el informe.     |
|     Pagos                  |     La suma de las transacciones de pagos del arrendamiento que se han registrado dentro del rango de fechas definido para el informe. Los valores de esta columna aparecerán como cantidades negativas a medida que los pagos disminuyan el saldo del pasivo del arrendamiento.  |
|     Interés                  |     La suma de las acumulaciones de intereses que se han registrado contra el arrendamiento dentro del rango de fechas definido para el informe.            |
|     Ajustes               |     La suma de los las transacciones de ajuste del arrendamiento registradas que se encuentran dentro del rango de fechas definido para el informe.                               |
|     Saldo final            |     El saldo de todas las transacciones de pasivo del arrendamiento que se han contabilizado desde la **Fecha final** del informe.                  |

## <a name="lease-transactions-report"></a>Informe de transacciones de arrendamiento
La consulta de transacciones de arrendamiento muestra todos los asientos de diario que se han generado mediante el arrendamiento de activos. Cada movimiento de diario está vinculada con el id. del libro del que se originó. Esto le permite asociar fácilmente el movimiento de diario con el arrendamiento correspondiente. La consulta de transacciones de arrendamiento funciona de una manera similar a la página **Transacciones de cupones** del libro mayor.

## <a name="weighted-average-discount-rate-report"></a>Informe de tasa de descuento promedio ponderado
El informe de tasa de descuento promedio ponderado satisface el requisito de divulgación de US GAAP especificado en ASC 842-20-50-4(g)(4) para una tasa de descuento promedio ponderada. Para ver este informe, vaya a **Arrendamiento de activos > Consultas e informes > Divulgaciones > Tasa de descuento promedio ponderada**. El informe incluye los campos siguientes. 

|     Campos de informe                     |     Descripción                                                           |
|------------------------------------   |------------------------------------------------------------------------   |
|     A partir de la fecha                        |     Este informe incluirá todos los arrendamientos que hayan comenzado en o antes del parámetro de fecha **A partir de**. Este informe debe ejecutarse a partir del último día del período a divulgar.      |
|     Entidad jurídica                      |     La entidad jurídica que está vinculada al arrendamiento.                           |
|     Id. de arrendamiento                          |     El id. exclusivo del arrendamiento.                                                  |
|     Descripción del arrendamiento                 |     La descripción del arrendamiento del encabezado del arrendamiento.                          |
|     Reserva                              |     El tipo de libro específico del arrendamiento mostrado.                                                                                                                                            |
|     Capa de registro                     |     Cada libro vinculado a un activo fijo se configura para una capa de registro concreta que tiene un objetivo de depreciación general.      |
|     Grupo de arrendamiento                       |     El grupo al que pertenece el arrendamiento.                                 |
|     Tasa de descuento                     |     La tasa utilizada para descontar los pagos de arrendamiento.                             |
|     Divisa                          |     La abreviatura de la divisa de transacción usada. Todos los informes convertirán la divisa transaccional a la divisa del informe.  |
|     Pagos por arrendamiento restantes          |     El importe total de los pagos de arrendamiento impagados de la programación de pagos que quedan desde la fecha **A partir de**.            |
|     Pagos ponderados restantes       |     Los pagos de arrendamiento restantes multiplicados por la tasa de descuento utilizada.   |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]