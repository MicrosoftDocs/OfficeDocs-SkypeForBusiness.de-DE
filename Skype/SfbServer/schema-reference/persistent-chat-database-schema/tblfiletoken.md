---
title: tblFileToken
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: TblFileToken enthält temporäre Token für die Dateiübertragung.
ms.openlocfilehash: 86047611c21301543a12486fa1c15bb15fde4c65
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tblfiletoken"></a>tblFileToken
 
TblFileToken enthält temporäre Token für die Dateiübertragung.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|fileToken  <br/> |Nvarchar (50), nicht null  <br/> |Eindeutiges Token (eine GUID).  <br/> |
|fileTokenUserID  <br/> |Int, nicht null  <br/> |ID des Prinzipals, der die Datei überträgt.  <br/> |
|fileTokenChannelID  <br/> |GUID, nicht null  <br/> |GUID des chatroomknotens.  <br/> |
|fileTokenExpireDate  <br/> |DateTime, nicht null  <br/> |Ablaufzeit. (Token laufen ab nach 30 Minuten, es sei denn, fixiert (siehe die folgenden Beschreibungen in dieser Spalte).  <br/> |
|fileTokenComplianceFileUrl  <br/> |nvarchar(256)  <br/> |URL der übertragenen Datei (für den Kompatibilitätsdienst).  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |nvarchar(256)  <br/> |URL des Miniaturbilds der übertragenen Datei (für den Kompatibilitätsdienst).  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |Zeitstempel für die tatsächliche Dateiübertragung (für den Kompatibilitätsdienst).  <br/> |
|fileTokenComplianceIsUpload  <br/> |bit  <br/> |True, wenn hochzuladen. False, wenn herunterladen (für den Kompatibilitätsdienst).  <br/> |
|fileTokenCompliancePinned  <br/> |Bit, nicht null  <br/> |True, wenn Token fixiert ist. Es wird verwendet, um das Token in der Tabelle beibehalten, bis kompatibilitätsdienst Möglichkeit, die entsprechenden Felder daraus abgerufen wurde.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|fileToken  <br/> |Primärschlüssel.  <br/> |
|fileTokenChannelID  <br/> |Fremdschlüssel mit Abfrage der tblNode.nodeGuid-Tabelle.  <br/> |
   

