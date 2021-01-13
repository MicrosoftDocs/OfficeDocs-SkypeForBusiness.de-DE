---
title: Änderungen, die bei der Domänenvorbereitung in Skype for Business Server vorgenommen wurden
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
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: In der folgenden Tabelle sind die ACEs (Access Control Entries, Zugriffssteuerungseinträge) aufgeführt, die während der Domänenvorbereitung im Domänenstamm erstellt werden. Alle ACEs werden vererbt, sofern nicht anders angegeben.
ms.openlocfilehash: 46eaedb25ca245a5426314a8118be7443fb612e1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831905"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>Änderungen, die bei der Domänenvorbereitung in Skype for Business Server vorgenommen wurden
 
In der folgenden Tabelle sind die ACEs (Access Control Entries, Zugriffssteuerungseinträge) aufgeführt, die während der Domänenvorbereitung im Domänenstamm erstellt werden. Alle ACEs werden vererbt, sofern nicht anders angegeben.
  
**Zum Domänenstamm hinzugefügte ACEs**

|**ACE**|**RTCUniversal-UserReadOnly-Group**|**RTCUniversal-ServerReadOnly-Group**|**RTCUniversal-UserAdmins**|**RTCHSUniversal-Services**|**Authentifizierte Benutzer**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Read Container (nicht vererbt)  <br/> |**Ja** <br/> |**Ja** <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Read User PropertySet User-Account-Restrictions  <br/> |**Ja** <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Read User PropertySet Personal-Information  <br/> |**Ja** <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Read User PropertySet General-Information  <br/> |**Ja** <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Read User PropertySet Public-Information  <br/> |**Ja** <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Read User PropertySet RTCUserSearchProperty-Set  <br/> |**Ja** <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |**Ja** <br/> |
|Read User PropertySet RTCPropertySet  <br/> |**Ja** <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Write User Property Proxy-Addresses  <br/> |Nein  <br/> |Nein  <br/> |**Ja** <br/> |Nein  <br/> |Nein  <br/> |
|Write User PropertySet RTCUserSearchProperty-Set  <br/> |Nein  <br/> |Nein  <br/> |**Ja** <br/> |Nein  <br/> |Nein  <br/> |
|Write User PropertySet RTCPropertySet  <br/> |Nein  <br/> |Nein  <br/> |**Ja** <br/> |Nein  <br/> |Nein  <br/> |
|Read PropertySet DS-Replication-Get-Changes für alle Active Directory-Objekte  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |**Ja** <br/> |Nein  <br/> |
   
In der folgenden Tabelle sind die ACEs (Access Control Entries, Zugriffssteuerungseinträge) aufgeführt, die während der Domänenvorbereitung in den drei integrierten Containern erstellt werden: für Benutzer, Computer und Domänencontroller. Alle ACEs werden vererbt, sofern nicht anders angegeben.
**Zu integrierten Containern hinzugefügte ACEs**

|**ACE**|**RTCUniversal-UserReadOnly-Group**|**RTCUniversal-ServerReadOnly-Group**|
|:-----|:-----|:-----|
|Read Container (nicht vererbt)  <br/> |**Ja** <br/> |**Ja** <br/> |
   

