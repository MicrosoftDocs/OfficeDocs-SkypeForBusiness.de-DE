---
title: tblADCookie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: "\"tbladcookie\" enthält die aktuellen Cookies Synchronisierung Lightweight Directory Access Protocol (LDAP)."
ms.openlocfilehash: d990d02e73be9a4d6178037a314e36add448ad40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929945"
---
# <a name="tbladcookie"></a>tblADCookie
 
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
   

