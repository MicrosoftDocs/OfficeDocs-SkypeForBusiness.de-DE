---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant enthält die aktuellen Teilnehmer pro Kanal und pro Server.
ms.openlocfilehash: bf6913d8bcc11db1589169c4479cec4a0238825d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295461"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
tblComplianceParticipant enthält die aktuellen Teilnehmer pro Kanal und pro Server.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|channelUri  <br/> |nvarchar (255); nicht NULL  <br/> |Kanal Uniform Resource Identifier (URI).  <br/> |
|UserID  <br/> |int, nicht NULL  <br/> |Prinzipal-ID des Teilnehmers (entsprechend der Tabelle tblPrincipal. prinID).  <br/> |
|joinedAt  <br/> |bigint, nicht NULL  <br/> |Zeitstempel des Joining-Ereignisses  <br/> |
|partedAt  <br/> |bigint  <br/> |NULL, wenn der Teilnehmer noch verbunden ist. Der Zeitstempel des Kanals, der das Ereignis verlässt, wenn nicht NULL.  <br/> Diese Einträge werden schließlich entfernt, wenn alle Übersetzer das Ereignis verarbeiten.  <br/> |
|userUri  <br/> |nvarchar (255); nicht NULL  <br/> |Benutzer-URI.  <br/> |
|ServerID  <br/> |int  <br/> |Serveridentität (wie in der Tabelle tblServerIdentity. Server-ID).  <br/> |
|SessionID  <br/> |bigint  <br/> |Server Sitzung. Hierbei handelt es sich um eine Zufallszahl, die bei jedem Start eines Chat-Diensts generiert wird. Sie wird zur Unterscheidung von Sitzungen zum Zweck der Identifizierung verwaister Teilnehmer verwendet.  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|\<channelUri, UserID, joinedAt\>  <br/> |Primärschlüssel  <br/> |
   

