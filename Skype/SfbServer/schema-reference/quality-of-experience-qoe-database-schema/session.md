---
title: Sitzungstabelle
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: Jeder Datensatz stellt eine Sitzung dar, die Audio oder Audio und Video umfasst. Es enthält allgemeine Informationen über die Sitzung. Eine Sitzung ist als SIP-Dialog (Session Initiation Protocol) für Audio oder Video zwischen zwei Endpunkten definiert.
ms.openlocfilehash: 044d7d2626ca0d04bb55b7a060d39e7ec330312d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60840927"
---
# <a name="session-table"></a>Sitzungstabelle
 
Jeder Datensatz stellt eine Sitzung dar, die Audio oder Audio und Video umfasst. Es enthält allgemeine Informationen über die Sitzung. Eine Sitzung ist als SIP-Dialog (Session Initiation Protocol) für Audio oder Video zwischen zwei Endpunkten definiert.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |Datum/Uhrzeit  <br/> |Primary  <br/> |Referenziert aus der [Dialogtabelle.](dialog.md)  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Referenziert aus der [Dialogtabelle.](dialog.md)  <br/> |
|**ConferenceKey** <br/> |int  <br/> |Ausländisch  <br/> |Konferenzschlüssel. Referenziert aus der [Konferenztabelle.](conference.md)  <br/> |
|**CorrelationKey** <br/> |int  <br/> |Ausländisch  <br/> |Korrelationsschlüssel. Referenziert aus der [SessionCorrelation-Tabelle.](sessioncorrelation.md)  <br/> |
|**DialogCategory** <br/> |Bit  <br/> | <br/> |Dialogkategorie; 0 ist Skype for Business Server vermittlungsserver leg; 1 ist Vermittlungsserver zu PSTN-Gateway.  <br/> |
|**MediationServerBypassFlag** <br/> |Bit  <br/> ||Flag, das angibt, ob der Anruf umgangen wurde oder nicht.  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||Dieses Feld gibt gegebenenfalls an, warum ein Anruf nicht umgangen wurde, auch wenn die Umgehungs-IDs übereinstimmen. Für Skype for Business Server wird nur ein Wert definiert.  <br/> 0x0001: Unbekannte Umgehungs-ID für Standardnetzwerkadapter.  <br/> |
|**StartTime** <br/> |Datum/Uhrzeit  <br/> | <br/> |Die Startzeit des Anrufs.  <br/> |
|**EndTime** <br/> |Datum/Uhrzeit  <br/> | <br/> |Die Endzeit des Anrufs.  <br/> |
|**CallerPool** <br/> |int  <br/> |Ausländisch  <br/> |Der Pool des Anrufers. Referenziert aus der [Pool-Tabelle.](pool.md)  <br/> |
|**CalleePool** <br/> |int  <br/> |Ausländisch  <br/> |Der Pool des Anrufempfängers. Referenziert aus der [Pool-Tabelle.](pool.md)  <br/> |
|**CalleePAI** <br/> |int  <br/> |Ausländisch  <br/> |SIP-URI in der SIP-p-asserted Identity (PAI) des empfangenden Endpunkts. Referenziert aus der [Tabelle "User".](user-0.md)  <br/> |
|**CallerURI** <br/> |int  <br/> |Ausländisch  <br/> |Der URI des Aufrufers. Referenziert aus der [Tabelle "User".](user-0.md)  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |Ausländisch  <br/> |Endpunkt des Anrufers. Referenziert aus der [Endpunkttabelle.](endpoint.md)  <br/> |
|**CallerUserAgent** <br/> |Bit  <br/> |Ausländisch  <br/> |Der Benutzer-Agent des Anrufers. Referenziert aus der [UserAgent-Tabelle.](useragent.md)  <br/> |
|**CallPriority** <br/> |Smallint  <br/> ||Die Priorität dieses Aufrufs.  <br/> |
|**ClassifiedPoorCall** <br/> |Bit  <br/> ||Diese Spalte ist veraltet und wird in Skype for Business Server nicht mehr verwendet. Stattdessen werden diese Informationen auf einer Pro-Media-Linienbasis gemeldet. Weitere Informationen finden Sie in der [MediaLine-Tabelle.](medialine-0.md) <br/> |
|**CallerPAI** <br/> |int  <br/> |Ausländisch  <br/> |P-Asserted-Identity des Benutzers, der den Anruf getätigt hat. Die P-Asserted-Identity (PAI) wird verwendet, um die tatsächliche Identität des Benutzers zu vermitteln, der den Anruf getätigt hat.  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |Ausländisch  <br/> |Endpunkt, der den Anruf empfangen hat.  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |Ausländisch  <br/> |Benutzer-Agent, der von dem Benutzer eingesetzt wird, der den Anruf empfangen hat. Benutzer-Agents stellen das Clientendpunktgerät dar.  <br/> |
|**CalleeUri** <br/> |int  <br/> |Ausländisch  <br/> |SIP-URI des Benutzers, der den Anruf empfangen hat.  <br/> |
   

