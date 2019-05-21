---
title: Von der Domänenvorbereitung in Skype for Business Server vorgenommene Änderungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: In der folgenden Tabelle sind die Zugriffssteuerungseinträge (ACEs) aufgeführt, die von der Domänenvorbereitung für den Domänenstamm erstellt werden. Alle ACEs werden geerbt, sofern nicht anders angegeben.
ms.openlocfilehash: afd6747590e09b0b86b42119ad34eb26eaf9d8db
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296714"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>Von der Domänenvorbereitung in Skype for Business Server vorgenommene Änderungen
 
In der folgenden Tabelle sind die Zugriffssteuerungseinträge (ACEs) aufgeführt, die von der Domänenvorbereitung für den Domänenstamm erstellt werden. Alle ACEs werden geerbt, sofern nicht anders angegeben.
  
**ACEs, die dem Domänenstamm hinzugefügt wurden**

|**ACE**|**RTCUniversal-UserReadOnly-Gruppe**|**RTCUniversal-ServerReadOnly-Gruppe**|**RTCUniversal-UserAdmins**|**RTCHSUniversal-Dienste**|**Authentifizierte Benutzer**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Read-Container (nicht geerbt)  <br/> |**Ja** <br/> |**Ja** <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Lesen der Benutzer-PropertySet-Benutzerkonto Einschränkungen  <br/> |**Ja** <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Lesen der Benutzer-PropertySet Personal-Informationen  <br/> |**Ja** <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Lesen der Benutzer-PropertySet-allgemeine Informationen  <br/> |**Ja** <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Lesen der Benutzer-PropertySet-öffentlichen Informationen  <br/> |**Ja** <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Read User PropertySet RTCUserSearchProperty-Satz  <br/> |**Ja** <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |**Ja** <br/> |
|Read User PropertySet RTCPropertySet  <br/> |**Ja** <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Schreiben von Benutzer Eigenschafts Proxy-Adressen  <br/> |Nein  <br/> |Nein  <br/> |**Ja** <br/> |Nein  <br/> |Nein  <br/> |
|Schreiben von Benutzer-Eigenschaftssatz-RTCUserSearchProperty  <br/> |Nein  <br/> |Nein  <br/> |**Ja** <br/> |Nein  <br/> |Nein  <br/> |
|Schreiben von Benutzer-PropertySet-RTCPropertySet  <br/> |Nein  <br/> |Nein  <br/> |**Ja** <br/> |Nein  <br/> |Nein  <br/> |
|Lesen von PropertySet DS-Replikation-abrufen – Änderungen aller Active Directory-Objekte  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |**Ja** <br/> |Nein  <br/> |
   
In der folgenden Tabelle sind die ACEs aufgeführt, die von der Domänenvorbereitung in den drei integrierten Containern erstellt werden: Benutzer, Computer und Domänencontroller. Alle ACEs werden geerbt, sofern nicht anders angegeben.
**ACEs, die zu integrierten Containern hinzugefügt wurden**

|**ACE**|**RTCUniversal-UserReadOnly-Gruppe**|**RTCUniversal-ServerReadOnly-Gruppe**|
|:-----|:-----|:-----|
|Read-Container (nicht geerbt)  <br/> |**Ja** <br/> |**Ja** <br/> |
   

