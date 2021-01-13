---
title: tblComplianceData
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
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: "\"tblComplianceData\" enthält die Kompatibilitätsereignisse, die noch nicht vom Kompatibilitätsadapter verarbeitet wurden."
ms.openlocfilehash: e4ceda662b2f601660c144319a4231cebeea39ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809855"
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
"tblComplianceData" enthält die Kompatibilitätsereignisse, die noch nicht vom Kompatibilitätsadapter verarbeitet wurden.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |bigint, nicht NULL  <br/> |Ereignis-ID  <br/> |
|entryDate  <br/> |smalldatetime, nicht NULL  <br/> |Zeitpunkt des Einfügevorgangs (kann für "cmplType=9" in ferner Zukunft liegen, da der Eintrag in diesem Fall nur ein Platzhalter ist).  <br/> |
|cmplType  <br/> |int, nicht NULL  <br/> | Typ des Kompatibilitätsereignisses: <br/>  1: Chat <br/>  2: Backchat <br/>  3: Dateidownload <br/>  4: Dateiupload <br/>  9: Vorläufige Dateiübertragung <br/>  10: Chatlöschung (mit Ersatz) <br/>  11: Chatbereinigung <br/> |
|cmplTime  <br/> |bigint, nicht NULL  <br/> |Zeitstempel für das Ereignis.  <br/> |
|cmplChannelUri  <br/> |nvarchar (255), nicht NULL  <br/> |Kanal-URI (Uniform Resource Identifier)  <br/> |
|cmplChatID  <br/> |bigint  <br/> |Chat-ID (entsprechend der Tabelle "tblChat.chatId").  <br/> |
|cmplUserID  <br/> |int, nicht NULL  <br/> |Prinzipal-ID des Bereitstellers (entsprechend der Tabelle "tblPrincipal.prinID").  <br/> |
|cmplUserUri  <br/> |nvarchar (255), nicht NULL  <br/> |Benutzer-URI  <br/> |
|cmplMessage  <br/> |nvarchar (max)  <br/> |Nachricht (Codierung abhängig von "cmplType").  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|cmplEventID  <br/> |Primärschlüssel  <br/> |
   

