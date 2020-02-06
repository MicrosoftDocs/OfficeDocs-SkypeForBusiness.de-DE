---
title: tblComplianceData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData enthält die Konformitätsereignisse, die noch nicht vom Kompatibilitätsadapter verarbeitet wurden.
ms.openlocfilehash: f09acd44e803c629e45afa18683ac7bc863564a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814663"
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
tblComplianceData enthält die Konformitätsereignisse, die noch nicht vom Kompatibilitätsadapter verarbeitet wurden.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |bigint, nicht NULL  <br/> |Ereignis-ID.  <br/> |
|entryDate  <br/> |smalldatetime, nicht NULL  <br/> |Zeitpunkt der Einfügung (kann für cmplType = 9 weit in der Zukunft liegen, da der Eintrag nur ein Platzhalter in diesem Fall ist).  <br/> |
|cmplType  <br/> |int, nicht NULL  <br/> | Art des Konformitäts Ereignisses: <br/>  1: Chat <br/>  2: Backchat <br/>  3: Herunterladen von Dateien <br/>  4: Hochladen von Dateien <br/>  9: provisorische Dateiübertragung <br/>  10: Löschen des Chats (mit Replace) <br/>  11: Chat-Bereinigung <br/> |
|cmplTime  <br/> |bigint, nicht NULL  <br/> |Zeitstempel für das Ereignis.  <br/> |
|cmplChannelUri  <br/> |nvarchar (255); nicht NULL  <br/> |Kanal Uniform Resource Identifier (URI).  <br/> |
|cmplChatID  <br/> |bigint  <br/> |Chat-ID (entsprechend der tblChat. Chat-Tabelle).  <br/> |
|cmplUserID  <br/> |int, nicht NULL  <br/> |Prinzipal-ID des Plakats (entsprechend der tblPrincipal. prinID-Tabelle).  <br/> |
|cmplUserUri  <br/> |nvarchar (255); nicht NULL  <br/> |Benutzer-URI.  <br/> |
|cmplMessage  <br/> |nvarchar (max)  <br/> |Nachricht (Codierung hängt von cmplType ab).  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|cmplEventID  <br/> |Primärschlüssel  <br/> |
   

