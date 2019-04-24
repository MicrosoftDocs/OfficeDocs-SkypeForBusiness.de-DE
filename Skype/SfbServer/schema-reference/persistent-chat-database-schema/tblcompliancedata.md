---
title: tblComplianceData
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: "\"tblcompliancedata\" enthält die genehmigungsereignisse, die nicht vom kompatibilitätsadapter noch verarbeitet wurden."
ms.openlocfilehash: e617f7821fcf026f279f333d45f526a1322509a1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212614"
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
"tblcompliancedata" enthält die genehmigungsereignisse, die nicht vom kompatibilitätsadapter noch verarbeitet wurden.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |Bigint, nicht null  <br/> |Ereignis-ID  <br/> |
|entryDate  <br/> |Smalldatetime, nicht null  <br/> |Zeitpunkt des Einfügevorgangs (möglicherweise weit in der Zukunft für CmplType = 9, da der Eintrag in diesem Fall nur ein Platzhalter ist).  <br/> |
|"cmpltype"  <br/> |Int, nicht null  <br/> | Der Typ des kompatibilitätsereignisses: <br/>  1: chat <br/>  2: Backchat <br/>  3: Dateidownload <br/>  4: Dateiupload <br/>  9: vorläufige Dateiübertragung <br/>  10: chatlöschung (mit Ersatz) <br/>  11: chatbereinigung <br/> |
|cmplTime  <br/> |Bigint, nicht null  <br/> |Zeitstempel für das Ereignis.  <br/> |
|cmplChannelUri  <br/> |Nvarchar (255), nicht null  <br/> |Kanal Uniform Resource Identifier (URI).  <br/> |
|cmplChatID  <br/> |bigint  <br/> |Chat-ID (entsprechend der Tabelle "tblchat.chatid").  <br/> |
|cmplUserID  <br/> |Int, nicht null  <br/> |Prinzipal-ID des bereitstellers (entsprechend der tblPrincipal.prinID-Tabelle).  <br/> |
|cmplUserUri  <br/> |Nvarchar (255), nicht null  <br/> |Der URI des Benutzers.  <br/> |
|cmplMessage  <br/> |Nvarchar (Max.)  <br/> |Nachricht (Codierung abhängig "cmpltype").  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|cmplEventID  <br/> |Primärschlüssel.  <br/> |
   

