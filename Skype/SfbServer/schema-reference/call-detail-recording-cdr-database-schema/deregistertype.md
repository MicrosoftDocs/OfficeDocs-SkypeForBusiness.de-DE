---
title: DeRegisterType-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: DeRegisterType-Tabelle handelt es sich um eine statische Tabelle, die die Liste der möglichen Benutzer speichert eine Aufhebung der Registrierung Typen, z. B. "vom Client initiierte", "Registrierung abgelaufen" oder "Client reagiert."
ms.openlocfilehash: be6fd10388c9f85315554605fd491aafa9d3a0d0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213193"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>DeRegisterType-Tabelle in Skype für Business Server 2015
 
DeRegisterType-Tabelle handelt es sich um eine statische Tabelle, die die Liste der möglichen Benutzer speichert eine Aufhebung der Registrierung Typen, z. B. "vom Client initiierte", "Registrierung abgelaufen" oder "Client reagiert."
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Zulässige Werte: <br/>  0 – unbekannt <br/>  1 – der Client initiiert die Registrierung aufgehoben <br/>  2--Registrierung abgelaufen <br/>  3 – Clientabsturz <br/>  4--Benutzerattribute geändert <br/>  5 – bevorzugte Registrierungsstelle geändert <br/>  6--Legacyclient In Survival Mode <br/> |
   

