---
title: DeRegisterType-Tabelle in Skype for Business Server 2015
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
ms.localizationpriority: medium
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: Bei der Tabelle "DeRegisterType" handelt es sich um eine statische Tabelle, in der die Liste möglicher Benutzertypen zur Aufhebung der Registrierung gespeichert wird, z. B. "Vom Client initiiert", "Registrierung abgelaufen" oder "Client reagiert nicht mehr".
ms.openlocfilehash: 93d06117974377b6df489f376aedf4ad88235fa2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599880"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>DeRegisterType-Tabelle in Skype for Business Server 2015
 
Bei der Tabelle "DeRegisterType" handelt es sich um eine statische Tabelle, in der die Liste möglicher Benutzertypen zur Aufhebung der Registrierung gespeichert wird, z. B. "Vom Client initiiert", "Registrierung abgelaufen" oder "Client reagiert nicht mehr".
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |Tinyint  <br/> |Primary  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Zulässige Werte: <br/>  0 -- Unbekannt <br/>  1 -- Aufhebung der Registrierung durch den Client <br/>  2 -- Registrierung abgelaufen <br/>  3 – Client abgestürzt <br/>  4 -- Benutzerattribute geändert <br/>  5 – Bevorzugte Registrierungsstelle geändert <br/>  6 -- Legacyclient In Survival Mode <br/> |
   

