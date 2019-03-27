---
title: Änderungen, die durch domänenvorbereitung in Skype für Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: Die folgende Tabelle enthält die Zugriffssteuerungseinträge (ACEs), die bei der domänenvorbereitung im Domänenstamm erstellt. Alle ACEs werden vererbt, sofern nicht anders angegeben.
ms.openlocfilehash: 5cf239e37badafee9980140d08fd20a11e3c233d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877699"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>Änderungen, die durch domänenvorbereitung in Skype für Business Server
 
Die folgende Tabelle enthält die Zugriffssteuerungseinträge (ACEs), die bei der domänenvorbereitung im Domänenstamm erstellt. Alle ACEs werden vererbt, sofern nicht anders angegeben.
  
**Zum Domänenstamm hinzugefügte aCEs**

|**Ass**|**RTCUniversal-UserReadOnly-Gruppe**|**RTCUniversal-ServerReadOnly-Gruppe**|**RTCUniversal UserAdmins**|**RTCHSUniversal-Dienste**|**Authentifizierte Benutzer**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Read Container (nicht vererbt)  <br/> |**Ja** <br/> |**"Ja"** <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Lesen Sie Benutzer PropertySet-Benutzer-Konto-Einschränkungen  <br/> |**"Ja"** <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Read PropertySet persönlich-Benutzerinformationen  <br/> |**"Ja"** <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Read PropertySet allgemeine-Benutzerinformationen  <br/> |**"Ja"** <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Read PropertySet Public-Benutzerinformationen  <br/> |**"Ja"** <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Benutzer PropertySet RTCUserSearchProperty festgelegten lesen  <br/> |**"Ja"** <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |**Ja** <br/> |
|Benutzer PropertySet RTCPropertySet lesen  <br/> |**"Ja"** <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |
|Benutzer-Eigenschaft Proxyadressen schreiben  <br/> |Nein  <br/> |Nein  <br/> |**"Ja"** <br/> |Nein  <br/> |Nein  <br/> |
|Benutzer PropertySet RTCUserSearchProperty festgelegten schreiben  <br/> |Nein  <br/> |Nein  <br/> |**"Ja"** <br/> |Nein  <br/> |Nein  <br/> |
|Benutzer PropertySet RTCPropertySet schreiben  <br/> |Nein  <br/> |Nein  <br/> |**"Ja"** <br/> |Nein  <br/> |Nein  <br/> |
|Read PropertySet DS-Replication-Get-Changes für alle Active Directory-Objekte  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |**"Ja"** <br/> |Nein  <br/> |
   
Die folgende Tabelle enthält die ACEs, die domänenvorbereitung in drei integrierten Containern erstellt: Benutzer, Computer und Domänencontroller. Alle ACEs werden vererbt, sofern nicht anders angegeben.
**Zu integrierten Containern hinzugefügte aCEs**

|**Ass**|**RTCUniversal-UserReadOnly-Gruppe**|**RTCUniversal-ServerReadOnly-Gruppe**|
|:-----|:-----|:-----|
|Read Container (nicht vererbt)  <br/> |**Ja** <br/> |**Ja** <br/> |
   

