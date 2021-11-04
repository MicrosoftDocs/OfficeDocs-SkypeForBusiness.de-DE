---
title: tblADCookie
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
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: "\"tblADCookie\" enthält die aktuellen Cookies für die LDAP-Synchronisierung (Lightweight Directory Access Protocol)."
ms.openlocfilehash: 770900c7ad5e31173a9e62ea3eb5a8c711afca98
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743171"
---
# <a name="tbladcookie"></a>tblADCookie
 
"tblADCookie" enthält die aktuellen Cookies für die LDAP-Synchronisierung (Lightweight Directory Access Protocol).
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, nicht NULL  <br/> |Prinzipal-GUID der überwachten Domäne.  <br/> |
|prinDCHost  <br/> |nvarchar (255)  <br/> |Vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des aktuellen Domänencontrollers, der für die Active Directory Domain Services-Synchronisierung verwendet wird. Weist einen Informationswert auf.  <br/> |
|adcContent  <br/> |image (binary)  <br/> |Cookie für die Active Directory-Synchronisierung.  <br/> |
|lastUpdated  <br/> |Datum/Uhrzeit  <br/> |Zeitstempel der Aktualisierungszeit der Zeile.  <br/> |
|lockedUntil  <br/> |Datum/Uhrzeit  <br/> |Zeitpunkt bis zu dem die Zeile für Änderungen gesperrt ist. Dies ist Teil eines Sperrmechanismus der Software, durch den sichergestellt ist, dass nur jeweils ein Chatdienst die Active Directory-Synchronisierung durchführt.  <br/> |
   
**Keys**

|**Spalten**|**Beschreibung**|
|:-----|:-----|
|prinGuid  <br/> |Primärschlüssel  <br/> |
|prinGuid  <br/> |Fremdschlüssel mit Abfrage der Principal.prinGuid-Tabelle.  <br/> |
   

