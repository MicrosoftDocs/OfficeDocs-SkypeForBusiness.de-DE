---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: TblComplianceParticipant enthält die aktuellen Teilnehmer pro Kanal und pro Server.
ms.openlocfilehash: 6644796d88f303c6614cbd73d98224fe0e41eabb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929938"
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
   

