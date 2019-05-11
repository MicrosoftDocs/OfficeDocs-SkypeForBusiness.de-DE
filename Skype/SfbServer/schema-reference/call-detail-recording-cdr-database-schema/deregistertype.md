---
title: DeRegisterType-Tabelle in Skype für Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: DeRegisterType-Tabelle handelt es sich um eine statische Tabelle, die die Liste der möglichen Benutzer speichert eine Aufhebung der Registrierung Typen, z. B. "vom Client initiierte", "Registrierung abgelaufen" oder "Client reagiert."
ms.openlocfilehash: 958de5dd537f391ca75936ad86a84cb6fed0778d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901173"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>DeRegisterType-Tabelle in Skype für Business Server 2015
 
DeRegisterType-Tabelle handelt es sich um eine statische Tabelle, die die Liste der möglichen Benutzer speichert eine Aufhebung der Registrierung Typen, z. B. "vom Client initiierte", "Registrierung abgelaufen" oder "Client reagiert."
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Zulässige Werte: <br/>  0 – unbekannt <br/>  1 – der Client initiiert die Registrierung aufgehoben <br/>  2--Registrierung abgelaufen <br/>  3 – Clientabsturz <br/>  4--Benutzerattribute geändert <br/>  5 – bevorzugte Registrierungsstelle geändert <br/>  6--Legacyclient In Survival Mode <br/> |
   

