---
title: DeRegisterType-Tabelle in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.openlocfilehash: f369416a15f0b1c024dd70fbe97042193940f669
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743991"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>DeRegisterType-Tabelle in Skype for Business Server 2015
 
Bei der Tabelle "DeRegisterType" handelt es sich um eine statische Tabelle, in der die Liste möglicher Benutzertypen zur Aufhebung der Registrierung gespeichert wird, z. B. "Vom Client initiiert", "Registrierung abgelaufen" oder "Client reagiert nicht mehr".
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |Tinyint  <br/> |Primary  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Zulässige Werte: <br/>  0 -- Unbekannt <br/>  1 -- Aufhebung der Registrierung durch den Client <br/>  2 -- Registrierung abgelaufen <br/>  3 – Client abgestürzt <br/>  4 -- Benutzerattribute geändert <br/>  5 – Bevorzugte Registrierungsstelle geändert <br/>  6 -- Legacyclient In Survival Mode <br/> |
   

