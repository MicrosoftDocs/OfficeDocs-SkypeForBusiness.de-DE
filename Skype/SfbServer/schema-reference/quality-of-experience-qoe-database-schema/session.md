---
title: Session-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: Jeder Eintrag stellt eine Sitzung dar, die Audio-oder Audio-und Videodaten beinhaltet. Sie enthält allgemeine Informationen zur Sitzung. Eine Sitzung ist als SIP-Dialog (Audio-oder Video Session Initiation Protocol) zwischen zwei Endpunkten definiert.
ms.openlocfilehash: f48857f826a4e85519d7dc7d2942d48967df8b01
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805773"
---
# <a name="session-table"></a>Session-Tabelle
 
Jeder Eintrag stellt eine Sitzung dar, die Audio-oder Audio-und Videodaten beinhaltet. Sie enthält allgemeine Informationen zur Sitzung. Eine Sitzung ist als SIP-Dialog (Audio-oder Video Session Initiation Protocol) zwischen zwei Endpunkten definiert.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Wird in der [Dialog Feld Tabelle](dialog.md)referenziert.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Wird in der [Dialog Feld Tabelle](dialog.md)referenziert.  <br/> |
|**ConferenceKey** <br/> |int  <br/> |Fremd  <br/> |Konferenz Taste. Wird aus der [Konferenz Tabelle](conference.md)referenziert.  <br/> |
|**CorrelationKey** <br/> |int  <br/> |Fremd  <br/> |Korrelationsschlüssel Wird in der [SessionCorrelation-Tabelle](sessioncorrelation.md)referenziert.  <br/> |
|**DialogCategory** <br/> |bit  <br/> | <br/> |Dialog Feld Kategorie; 0 ist Skype for Business Server to Mediation Server Leg; 1 ist Vermittlungs Server für das PSTN-Gateway-Bein.  <br/> |
|**MediationServerBypassFlag** <br/> |bit  <br/> ||Flag, das angibt, ob der Anruf umgangen wurde oder nicht.  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||Dieses Feld, falls vorhanden, gibt an, warum ein Anruf nicht umgangen wurde, auch wenn die Bypass-IDs übereinstimmten. Für Skype for Business Server ist nur ein Wert definiert.  <br/> 0x0001-unbekannte Bypass-ID für den standardmäßigen Netzwerkadapter.  <br/> |
|**StartTime** <br/> |datetime  <br/> | <br/> |Startzeit des Anrufs.  <br/> |
|**EndTime** <br/> |datetime  <br/> | <br/> |Endzeit des Anrufs.  <br/> |
|**CallerPool** <br/> |int  <br/> |Fremd  <br/> |Der Pool des Anrufers. Wird aus der [Pool Tabelle](pool.md)referenziert.  <br/> |
|**CalleePool** <br/> |int  <br/> |Fremd  <br/> |Der Pool des anrufempfängers. Wird aus der [Pool Tabelle](pool.md)referenziert.  <br/> |
|**CalleePAI** <br/> |int  <br/> |Fremd  <br/> |SIP-URI in der SIP p-asserted Identity (Pai) des empfangenden Endpunkts. Wird in der [Tabelle user](user-0.md)referenziert.  <br/> |
|**CallerURI** <br/> |int  <br/> |Fremd  <br/> |URI des Anrufers. Wird in der [Tabelle user](user-0.md)referenziert.  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |Fremd  <br/> |Endpunkt des Anrufers. Wird aus der [Endpunkt Tabelle](endpoint.md)referenziert.  <br/> |
|**CallerUserAgent** <br/> |bit  <br/> |Fremd  <br/> |Benutzer-Agent des Anrufers. Referenziert aus der [userAgent-Tabelle](useragent.md).  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||Die Priorität dieses Anrufs.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Diese Spalte wurde als veraltet markiert und nicht in Skype for Business Server verwendet. Stattdessen werden diese Informationen auf Basis einer einzelnen medienzeile gemeldet. Weitere Informationen finden Sie in der [Tabelle medialinie](medialine-0.md) . <br/> |
|**CallerPAI** <br/> |int  <br/> |Fremd  <br/> |P-bestätigt – Identität des Benutzers, der den Anruf getätigt hat. Die P-Asserted-Identity (Pai) wird verwendet, um die wahre Identität des Benutzers zu vermitteln, der den Anruf getätigt hat.  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |Fremd  <br/> |Endpunkt, der den Anruf empfangen hat.  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |Fremd  <br/> |Benutzer-Agent des Benutzers, der den Anruf erhalten hat. Benutzer-Agents stellen das Clientendpunkt Gerät dar.  <br/> |
|**CalleeUri** <br/> |int  <br/> |Fremd  <br/> |SIP-URI des Benutzers, der den Anruf erhalten hat.  <br/> |
   

