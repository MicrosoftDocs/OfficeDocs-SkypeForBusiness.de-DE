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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant enthält die aktuellen Teilnehmer pro Kanal und pro Server.
ms.openlocfilehash: 8f4b90cd7e8949451c2b6c1b9bc3cfabbab826e9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814643"
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
   

