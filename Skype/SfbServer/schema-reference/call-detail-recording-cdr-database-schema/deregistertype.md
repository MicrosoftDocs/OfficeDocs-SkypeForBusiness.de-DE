---
title: Tabelle "DeRegisterType" in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: Bei der Tabelle "DeRegisterType" handelt es sich um eine statische Tabelle, in der die Liste möglicher Typen von Benutzerregistrierungen, z. B. "Client initiiert", "Registrierung abgelaufen" oder "Client reagiert nicht mehr" speichert.
ms.openlocfilehash: 388aebc1ac180e1298addd54859cff6759b28be0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816075"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Tabelle "DeRegisterType" in Skype for Business Server 2015
 
Bei der Tabelle "DeRegisterType" handelt es sich um eine statische Tabelle, in der die Liste möglicher Typen von Benutzerregistrierungen, z. B. "Client initiiert", "Registrierung abgelaufen" oder "Client reagiert nicht mehr" speichert.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Zulässige Werte: <br/>  0 -- Unbekannt <br/>  1 -- Aufhebung der Registrierung durch den Client <br/>  2 -- Registrierung abgelaufen <br/>  3 – Client abgestürzt <br/>  4 -- Benutzerattribute geändert <br/>  5 – Bevorzugte Registrierung geändert <br/>  6 -- Legacyclient In Survival Mode <br/> |
   

