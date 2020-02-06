---
title: tblFileToken
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
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken enthält temporäre Token für Datei Übertragungs Zwecke.
ms.openlocfilehash: 573c921278521eb5b9ed7cc754dec9fa3471e9f4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814593"
---
# <a name="tblfiletoken"></a>tblFileToken
 
tblFileToken enthält temporäre Token für Datei Übertragungs Zwecke.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|FileToken  <br/> |nvarchar (50); nicht NULL  <br/> |Eindeutiges Token (eine GUID).  <br/> |
|fileTokenUserID  <br/> |int, nicht NULL  <br/> |Die ID des Prinzipals, der die Datei übertragen wird.  <br/> |
|fileTokenChannelID  <br/> |GUID, nicht NULL  <br/> |GUID des Chatroom-Knotens.  <br/> |
|fileTokenExpireDate  <br/> |DateTime, nicht NULL  <br/> |Ablaufzeit. (Token werden nach 30 Minuten ablaufen, es sei denn, angeheftet (siehe die folgenden Beschreibungen in dieser Spalte).  <br/> |
|fileTokenComplianceFileUrl  <br/> |nvarchar(256)  <br/> |Die URL der übertragenen Datei (für die Verwendung des Kompatibilitätsdiensts).  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |nvarchar(256)  <br/> |Die URL der Miniaturansicht für die übertragene Datei (für die Verwendung des Kompatibilitätsdiensts).  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |Timestamp für den eigentlichen Dateiübertragungsvorgang (für die Verwendung des Kompatibilitätsdiensts).  <br/> |
|fileTokenComplianceIsUpload  <br/> |bit  <br/> |True, wenn Upload; False, wenn Download (für Compliance-Dienstnutzung).  <br/> |
|fileTokenCompliancePinned  <br/> |Bit, nicht NULL  <br/> |True, wenn Token angeheftet ist. Sie wird verwendet, um das Token in der Tabelle beizubehalten, bis der Kompatibilitätsdienst die entsprechenden Felder aus ihm abrufen kann.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|FileToken  <br/> |Primärschlüssel  <br/> |
|fileTokenChannelID  <br/> |Fremdschlüssel mit Lookup in der tblNode. nodeGuid-Tabelle.  <br/> |
   

