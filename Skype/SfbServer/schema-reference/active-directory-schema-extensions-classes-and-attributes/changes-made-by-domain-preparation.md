---
title: 'Änderungen, die von der Domänenvorbereitung in Skype for Business Server vorgenommen wurden'
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
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: 'In der folgenden Tabelle sind die ACEs (Access Control Entries, Zugriffssteuerungseinträge) aufgeführt, die während der Domänenvorbereitung im Domänenstamm erstellt werden. Alle ACEs werden vererbt, sofern nicht anders angegeben.'
---

# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>Änderungen, die von der Domänenvorbereitung in Skype for Business Server vorgenommen wurden
 
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
   

