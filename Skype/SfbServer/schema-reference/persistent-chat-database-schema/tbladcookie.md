---
title: "\"tbladcookie\""
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: "\"tbladcookie\" enthält die aktuellen Cookies Synchronisierung Lightweight Directory Access Protocol (LDAP)."
ms.openlocfilehash: bc2c0657caa66a0420bc493bf4b688a2a081db36
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tbladcookie"></a>"tbladcookie"
 
"tbladcookie" enthält die aktuellen Cookies Synchronisierung Lightweight Directory Access Protocol (LDAP).
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, nicht null  <br/> |Prinzipal-GUID der überwachten Domäne.  <br/> |
|prinDCHost  <br/> |Nvarchar (255)  <br/> |Vollqualifizierter Domänenname (FQDN) des aktuellen Domänencontrollers für Active Directory Domain Services Sync verwendet. Informative Wert hat.  <br/> |
|adcContent  <br/> |Bild (binär)  <br/> |Active Directory-Synchronisierung Cookie.  <br/> |
|lastUpdated  <br/> |datetime  <br/> |Zeitstempel mit Aktualisierungszeit der Zeile.  <br/> |
|lockedUntil  <br/> |datetime  <br/> |Zeitpunkt, bis die Zeile für Änderungen gesperrt ist. Dies ist Bestandteil eines Software Sperre Mechanismus, das wird sichergestellt, dass nur eine Chat-Dienste zu einem Zeitpunkt der Active Directory-Synchronisierung wird.  <br/> |
   
**Schlüssel**

|**Spalten**|**Beschreibung**|
|:-----|:-----|
|prinGuid  <br/> |Primärschlüssel.  <br/> |
|prinGuid  <br/> |Fremdschlüssel mit Abfrage der Principal.prinGuid-Tabelle.  <br/> |
   

