---
title: Session-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: Jeder Datensatz steht für eine Sitzung der audio oder audio und video umfasst. Sie enthält allgemeine Informationen zu der Sitzung. Eine Sitzung wird als eine Audio- oder Videodatei Session Initiation Protocol (SIP) Dialogfeld zwischen zwei Endpunkte definiert.
ms.openlocfilehash: 7a0ea3f9753529c22299ef46017b863c314319b5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212376"
---
# <a name="session-table"></a>Session-Tabelle
 
Jeder Datensatz steht für eine Sitzung der audio oder audio und video umfasst. Sie enthält allgemeine Informationen zu der Sitzung. Eine Sitzung wird als eine Audio- oder Videodatei Session Initiation Protocol (SIP) Dialogfeld zwischen zwei Endpunkte definiert.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Der [Dialog Table](dialog.md)referenziert.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Der [Dialog Table](dialog.md)referenziert.  <br/> |
|**ConferenceKey** <br/> |int  <br/> |Ausländisch  <br/> |Konferenz-Taste. Verweis von der [Konferenz-Tabelle](conference.md).  <br/> |
|**CorrelationKey** <br/> |int  <br/> |Ausländisch  <br/> |Korrelations-Taste. Verweis von der [SessionCorrelation-Tabelle](sessioncorrelation.md).  <br/> |
|**DialogCategory** <br/> |bit  <br/> | <br/> |Dialogfeld Kategorie. 0 ist Skype für Business Server Mediation Server Abschnitts. 1: Vermittlungsserver zum PSTN-Gateway-Abschnitt.  <br/> |
|**MediationServerBypassFlag** <br/> |bit  <br/> ||Flag gibt an, ob der Anruf oder nicht umgangen wurde.  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||Dieses Feld gibt, falls vorhanden, warum ein Anruf nicht umgangen wurde, auch wenn die Umgehung IDs übereinstimmen. Für Skype für Business Server wird nur ein Wert definiert.  <br/> 0 x 0001 – unbekannte umgehungs-ID für Standardnetzwerkadapter.  <br/> |
|**StartTime** <br/> |datetime  <br/> | <br/> |Startzeit des Anrufs.  <br/> |
|**EndTime** <br/> |datetime  <br/> | <br/> |Die Endzeit des Anrufs.  <br/> |
|**CallerPool** <br/> |int  <br/> |Ausländisch  <br/> |Der Pool des Anrufers. Verweis von der [Pool-Tabelle](pool.md).  <br/> |
|**CalleePool** <br/> |int  <br/> |Ausländisch  <br/> |Der Pool, der den Empfänger des Anrufs. Verweis von der [Pool-Tabelle](pool.md).  <br/> |
|**CalleePAI** <br/> |int  <br/> |Ausländisch  <br/> |SIP-URI in der SIP p-asserted-Identity (PAI) des empfangenden Endpunkts. Verweis von der [Tabelle "Benutzer"](user-0.md).  <br/> |
|**CallerURI** <br/> |int  <br/> |Ausländisch  <br/> |URI des Anrufers. Verweis von der [Tabelle "Benutzer"](user-0.md).  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |Ausländisch  <br/> |Endpunkt des Anrufers. Verweis von der [Endpoint-Tabelle](endpoint.md).  <br/> |
|**CallerUserAgent** <br/> |bit  <br/> |Ausländisch  <br/> |Benutzer-Agent des Anrufers. Verweis von der [UserAgent-Tabelle](useragent.md).  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||Die Priorität dieses Anrufs.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Diese Spalte ist veraltet und wird nicht in Skype für Business Server verwendet. Stattdessen wird diese Informationen auf einen Media-Zeile Basiswerte gemeldet. Finden Sie weitere Informationen der [MediaLine-Tabelle](medialine-0.md) . <br/> |
|**CallerPAI** <br/> |int  <br/> |Ausländisch  <br/> |P-Asserted-Identity des Benutzers, der den Anruf ausgeführt hat. P-Asserted-Identity (PAI) wird verwendet, um auszudrücken true Identität des Benutzers, der den Anruf ausgeführt hat.  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |Ausländisch  <br/> |Endpunkt, der den Anruf empfangen hat.  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |Ausländisch  <br/> |Benutzer-Agent beschäftigt durch den Benutzer, der den Anruf empfangen hat. Benutzer-Agents darstellen Endpunkt Clientgeräts.  <br/> |
|**CalleeUri** <br/> |int  <br/> |Ausländisch  <br/> |SIP-URI des Benutzers, der den Anruf empfangen hat.  <br/> |
   

