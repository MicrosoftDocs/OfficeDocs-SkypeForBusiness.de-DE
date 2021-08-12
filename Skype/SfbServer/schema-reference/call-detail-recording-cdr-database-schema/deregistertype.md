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
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: Bei der Tabelle "DeRegisterType" handelt es sich um eine statische Tabelle, in der die Liste möglicher Benutzertypen zur Aufhebung der Registrierung gespeichert wird, z. B. "Vom Client initiiert", "Registrierung abgelaufen" oder "Client reagiert nicht mehr".
ms.openlocfilehash: 606065f0442043d660c917c61b89111b48679145088b4eba9a7a80e668248161
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347790"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>DeRegisterType-Tabelle in Skype for Business Server 2015
 
Bei der Tabelle "DeRegisterType" handelt es sich um eine statische Tabelle, in der die Liste möglicher Benutzertypen zur Aufhebung der Registrierung gespeichert wird, z. B. "Vom Client initiiert", "Registrierung abgelaufen" oder "Client reagiert nicht mehr".
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |Tinyint  <br/> |Primary  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Zulässige Werte: <br/>  0 -- Unbekannt <br/>  1 -- Aufhebung der Registrierung durch den Client <br/>  2 -- Registrierung abgelaufen <br/>  3 – Client abgestürzt <br/>  4 -- Benutzerattribute geändert <br/>  5 – Bevorzugte Registrierungsstelle geändert <br/>  6 -- Legacyclient In Survival Mode <br/> |
   

