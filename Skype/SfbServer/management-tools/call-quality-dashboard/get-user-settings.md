---
title: Abrufen von Benutzereinstellungen
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Zusammenfassung: Informationen Sie zum Vorgang Benutzereinstellungen erhalten möchten, der Teil des Diensts für Benutzer ist. Die User Settings Service ist Bestandteil der Repository-API für die Qualitätsdashboard aufrufen. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.'
ms.openlocfilehash: 41bc45f63366337000ad8c263ff8e6dbcb36a3b3
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26293955"
---
# <a name="get-user-settings"></a>Abrufen von Benutzereinstellungen
 
**Zusammenfassung:** Informationen Sie zu den Get User Settings-Vorgang, der Teil des Diensts für Benutzer ist. Die User Settings Service ist Bestandteil der Repository-API für die Qualitätsdashboard aufrufen. Das Anrufqualitäts-Dashboard ist ein Tool für Skype for Business Server 2015.
  
Der erste User Settings-Vorgang ist Teil der Benutzerdienst Einstellungen in der Repository-API für die Qualitätsdashboard aufrufen.
  
## <a name="get-user-settings"></a>Abrufen von Benutzereinstellungen

Get-Benutzereinstellungen gibt eine Liste der Einstellungen für einen angegebenen Benutzer zurück.
  

|**Methode**|**Anforderungs-URI**|**HTTP-Version**|
|:-----|:-----|:-----|
|Erhalten  <br/> |https://\<Portal\>/QoERepositoryService/Repository/Benutzer / {Benutzer-ID} / festlegen  <br/> |HTTP/1.1  <br/> |
   
 **URI-Parameter**
  
- *eine effektive* - Optional. Dieser Parameter gilt nur, wenn die spezielle Benutzer-ID-Standardeinstellung verwendet wird. In anderen Fällen wird sie ignoriert. `True`Gibt eine effektive benutzereinstellungen und `false` gibt nur die benutzereinstellungen (Standard).
    
  **Anfordern von Kopfzeilen** - keine zusätzlichen Header.
  
  **Anforderungstextkörper** – None.
  
  **Antwort** - die Antwort enthält einen HTTP-Statuscode und einen Satz von Antwortheader.
  
  **Statuscode** - eine erfolgreiche Ausführung Gibt Statuscode 200 (OK).
  
  **Antwortheader** - keine zusätzlichen Header.
  
  **Antworttext** - ist im folgenden Beispiel Antwort Nutzlast in JSON.
  
```
[{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
},
{
"userId": 6,
"key": "ShowTimeStamps",
"value": "true"
}]
```