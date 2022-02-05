---
title: tblFileToken
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: TblFileToken enthält temporäre Token für die Dateiübertragung.
---

# <a name="tblfiletoken"></a>tblFileToken
 
TblFileToken enthält temporäre Token für die Dateiübertragung.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|fileToken  <br/> |nvarchar (50), nicht NULL  <br/> |Eindeutiges Token (eine GUID).  <br/> |
|fileTokenUserID  <br/> |int, nicht NULL  <br/> |ID des Prinzipals, der die Datei überträgt.  <br/> |
|fileTokenChannelID  <br/> |GUID, nicht NULL  <br/> |GUID des Chatroomknotens.  <br/> |
|fileTokenExpireDate  <br/> |datetime, nicht NULL  <br/> |Ablaufzeit. (Token laufen nach 30 Minuten ab, wenn sie nicht gebunden werden (siehe Beschreibungen in dieser Tabelle.)  <br/> |
|fileTokenComplianceFileUrl  <br/> |nvarchar(256)  <br/> |URL der übertragenen Datei (für den Kompatibilitätsdienst).  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |nvarchar(256)  <br/> |URL des Miniaturbilds der übertragenen Datei (für den Kompatibilitätsdienst).  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |Zeitstempel für die tatsächliche Dateiübertragung (für den Kompatibilitätsdienst).  <br/> |
|fileTokenComplianceIsUpload  <br/> |Bit  <br/> |True bei Upload; False bei Download (für den Kompatibilitätsdienst).  <br/> |
|fileTokenCompliancePinned  <br/> |Bit, nicht NULL  <br/> |True, wenn das Token gebunden ist. Es wird verwendet, um das Token in der Tabelle zu speichern, bis der Compliancedienst die Möglichkeit hat, die relevanten Felder daraus abzurufen.  <br/> |
   
**Keys**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|fileToken  <br/> |Primärschlüssel  <br/> |
|fileTokenChannelID  <br/> |Fremdschlüssel mit Abfrage der tblNode.nodeGuid-Tabelle.  <br/> |
   

