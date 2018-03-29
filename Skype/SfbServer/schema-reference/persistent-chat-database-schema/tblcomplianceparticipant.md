---
title: tblComplianceParticipant
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: TblComplianceParticipant enthält die aktuellen Teilnehmer pro Kanal und pro Server.
ms.openlocfilehash: ba488f377592b48845880acaeed61074bc31ccd2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
TblComplianceParticipant enthält die aktuellen Teilnehmer pro Kanal und pro Server.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|channelUri  <br/> |Nvarchar (255), nicht null  <br/> |Kanal Uniform Resource Identifier (URI).  <br/> |
|Benutzer-ID  <br/> |Int, nicht null  <br/> |Prinzipal-ID des Teilnehmers (entsprechend der tblPrincipal.prinID-Tabelle).  <br/> |
|joinedAt  <br/> |Bigint, nicht null  <br/> |Zeitstempel des Ereignisses des Beitritts.  <br/> |
|partedAt  <br/> |bigint  <br/> |"NULL" Wenn Teilnehmer noch angeschlossen ist. Der Zeitstempel des Kanals Ereignis verlassen, wenn nicht null.  <br/> Diese Einträge werden schließlich entfernt, wenn alle Übersetzer des Ereignisses Verarbeitung.  <br/> |
|userUri  <br/> |nvarchar(255), nicht null  <br/> |Der URI des Benutzers.  <br/> |
|serverID  <br/> |int  <br/> |Serveridentität (wie in tblserveridentity.ServerID).  <br/> |
|Sitzungs-ID  <br/> |bigint  <br/> |Server-Sitzung. Dies ist eine Zufallszahl generiert jedes Mal, wenn ein Chatdienst gestartet wird. Es wird zur Unterscheidung von Sitzungen zur Identifizierung von verwaisten Teilnehmer verwendet.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<ChannelUri, UserId, joinedAt\>  <br/> |Primärschlüssel.  <br/> |
   

