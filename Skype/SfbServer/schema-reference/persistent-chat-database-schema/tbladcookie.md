---
title: tblADCookie
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
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie enthält die aktuellen LDAP-Synchronisierungs Cookies (Lightweight Directory Access Protocol).
ms.openlocfilehash: c9a4c666a5fe4a76ecb3685f60f1208ec3ea88ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814703"
---
# <a name="tbladcookie"></a>tblADCookie
 
tblADCookie enthält die aktuellen LDAP-Synchronisierungs Cookies (Lightweight Directory Access Protocol).
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, nicht NULL  <br/> |Prinzipal-GUID der zu überwachenden Domäne.  <br/> |
|prinDCHost  <br/> |nvarchar (255)  <br/> |Vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des aktuellen Domänencontrollers, der für die Synchronisierung von Active Directory-Domänendiensten verwendet wird. Hat einen Informationswert.  <br/> |
|adcContent  <br/> |Bild (binär)  <br/> |Active Directory-Synchronisierungs Cookie  <br/> |
|lastUpdated  <br/> |datetime  <br/> |Zeitstempel mit der Zeilen Aktualisierungszeit.  <br/> |
|lockedUntil  <br/> |datetime  <br/> |Zeit, bis die Zeile für Änderungen gesperrt ist. Dies ist Teil eines Software-Interlock-Mechanismus, der sicherstellt, dass nur einer der Chat Dienste die Active Directory-Synchronisierung gleichzeitig durchführt.  <br/> |
   
**Schlüssel**

|**Spalte (n)**|**Beschreibung**|
|:-----|:-----|
|prinGuid  <br/> |Primärschlüssel  <br/> |
|prinGuid  <br/> |Fremdschlüssel mit Lookup in der Principal. prinGuid-Tabelle.  <br/> |
   

