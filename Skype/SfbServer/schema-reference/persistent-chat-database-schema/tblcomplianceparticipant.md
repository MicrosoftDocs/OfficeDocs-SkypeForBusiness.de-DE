---
title: tblComplianceParticipant
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
ms.localizationpriority: medium
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant enthält die aktuellen Teilnehmer pro Kanal und pro Server.
ms.openlocfilehash: 8c94aab78c7f0cc9a04e849a2ad798134ff38e42
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627767"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
tblComplianceParticipant enthält die aktuellen Teilnehmer pro Kanal und pro Server.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|channelUri  <br/> |nvarchar (255), nicht NULL  <br/> |Kanal-URI (Uniform Resource Identifier).  <br/> |
|userId  <br/> |int, nicht NULL  <br/> |Prinzipal-ID des Teilnehmers (entsprechend der tblPrincipal.prinID-Tabelle).  <br/> |
|joinedAt  <br/> |bigint, nicht NULL  <br/> |Zeitstempel des Ereignisses des Beitritts.  <br/> |
|partedAt  <br/> |Bigint  <br/> |NULL, wenn der Teilnehmer noch immer teilnimmt. Der Zeitstempel des Ereignisses des Verlassens des Kanals, sofern nicht NULL.  <br/> Diese Einträge werden schließlich entfernt, wenn das Ereignis von allen Konvertern verarbeitet wird.  <br/> |
|userUri  <br/> |nvarchar(255), nicht NULL  <br/> |Benutzer-URI  <br/> |
|serverID  <br/> |int  <br/> |Serveridentität (wie in tblServerIdentity.serverID).  <br/> |
|Sessionid  <br/> |Bigint  <br/> |Serversitzung. Zufallszahl, die nach jedem Starten eines Chatdiensts generiert wird. Wird zur Unterscheidung von Sitzungen verwendet, mit dem Zweck, verwaiste Teilnehmer zu identifizieren.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<channelUri, userId, joinedAt\>  <br/> |Primärschlüssel  <br/> |
   

