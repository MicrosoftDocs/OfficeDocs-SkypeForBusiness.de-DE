---
title: tblADCookie
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
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: "\"tblADCookie\" enthält die aktuellen Cookies für die LDAP-Synchronisierung (Lightweight Directory Access Protocol)."
ms.openlocfilehash: 78a477399da811e674bb5a4493e61100acdd4782
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814755"
---
# <a name="tbladcookie"></a>tblADCookie
 
"tblADCookie" enthält die aktuellen Cookies für die LDAP-Synchronisierung (Lightweight Directory Access Protocol).
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, nicht NULL  <br/> |Prinzipal-GUID der überwachten Domäne.  <br/> |
|prinDCHost  <br/> |nvarchar (255)  <br/> |Vollqualifizierter Domänenname (FQDN) des aktuellen Domänencontrollers, der für die Synchronisierung der Active Directory-Domänendienste verwendet wird. Verfügt über einen Informationswert.  <br/> |
|adcContent  <br/> |image (binary)  <br/> |Cookie für die Active Directory-Synchronisierung.  <br/> |
|lastUpdated  <br/> |Datum/Uhrzeit  <br/> |Zeitstempel der Aktualisierungszeit der Zeile.  <br/> |
|lockedUntil  <br/> |Datum/Uhrzeit  <br/> |Zeitpunkt bis zu dem die Zeile für Änderungen gesperrt ist. Dies ist Teil eines Sperrmechanismus der Software, durch den sichergestellt ist, dass nur jeweils ein Chatdienst die Active Directory-Synchronisierung durchführt.  <br/> |
   
**Keys**

|**Spalte(n)**|**Beschreibung**|
|:-----|:-----|
|prinGuid  <br/> |Primärschlüssel  <br/> |
|prinGuid  <br/> |Fremdschlüssel mit Abfrage der Principal.prinGuid-Tabelle.  <br/> |
   

