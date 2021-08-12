---
title: Sitzungstabelle
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: Jeder Datensatz stellt eine Sitzung dar, die Audio oder Audio und Video umfasst. Es enthält allgemeine Informationen über die Sitzung. Eine Sitzung wird als SIP-Dialogfeld (Session Initiation Protocol) zwischen zwei Endpunkten definiert.
ms.openlocfilehash: 749f151def046abdb5169b39ccbd81ea5f07f5d4ee3d1c971ac112a2d4b90cce
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340031"
---
# <a name="session-table"></a>Sitzungstabelle
 
Jeder Datensatz stellt eine Sitzung dar, die Audio oder Audio und Video umfasst. Es enthält allgemeine Informationen über die Sitzung. Eine Sitzung wird als SIP-Dialogfeld (Session Initiation Protocol) zwischen zwei Endpunkten definiert.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |Datum/Uhrzeit  <br/> |Primary  <br/> |Referenziert aus der [Dialogtabelle.](dialog.md)  <br/> |
|**SessionSeq** <br/> |Ganzzahl  <br/> |Primary  <br/> |Referenziert aus der [Dialogtabelle.](dialog.md)  <br/> |
|**ConferenceKey** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |Konferenzschlüssel. Referenziert aus der [Konferenztabelle.](conference.md)  <br/> |
|**CorrelationKey** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |Korrelationsschlüssel. Referenziert aus der [SessionCorrelation-Tabelle.](sessioncorrelation.md)  <br/> |
|**DialogCategory** <br/> |Bit  <br/> | <br/> |Dialogkategorie; 0 ist Skype for Business Server vermittlungsserver leg; 1 ist Vermittlungsserver zu PSTN-Gateway.  <br/> |
|**MediationServerBypassFlag** <br/> |Bit  <br/> ||Flag, das angibt, ob der Anruf umgangen wurde oder nicht.  <br/> |
|**MediaBypassWarningFlag** <br/> |Ganzzahl  <br/> ||Dieses Feld gibt gegebenenfalls an, warum ein Anruf nicht umgangen wurde, auch wenn die Umgehungs-IDs übereinstimmen. Für Skype for Business Server wird nur ein Wert definiert.  <br/> 0x0001 : Unbekannte Umgehungs-ID für Standardnetzwerkadapter.  <br/> |
|**StartTime** <br/> |Datum/Uhrzeit  <br/> | <br/> |Die Startzeit des Anrufs.  <br/> |
|**EndTime** <br/> |Datum/Uhrzeit  <br/> | <br/> |Die Endzeit des Anrufs.  <br/> |
|**CallerPool** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |Der Pool des Anrufers. Referenziert aus der [Pool-Tabelle.](pool.md)  <br/> |
|**CalleePool** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |Der Pool des Anrufempfängers. Referenziert aus der [Pool-Tabelle.](pool.md)  <br/> |
|**CalleePAI** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |SIP-URI in der SIP-p-asserted Identity (PAI) des empfangenden Endpunkts. Referenziert aus der [Tabelle "User".](user-0.md)  <br/> |
|**CallerURI** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |Der URI des Aufrufers. Referenziert aus der [Tabelle "User".](user-0.md)  <br/> |
|**CallerEndpoint** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |Endpunkt des Anrufers. Referenziert aus der [Endpunkttabelle.](endpoint.md)  <br/> |
|**CallerUserAgent** <br/> |Bit  <br/> |Ausländisch  <br/> |Der Benutzer-Agent des Anrufers. Referenziert aus der [UserAgent-Tabelle.](useragent.md)  <br/> |
|**CallPriority** <br/> |Smallint  <br/> ||Die Priorität dieses Aufrufs.  <br/> |
|**ClassifiedPoorCall** <br/> |Bit  <br/> ||Diese Spalte ist veraltet und wird nicht in Skype for Business Server verwendet. Stattdessen werden diese Informationen auf einer Pro-Media-Linienbasis gemeldet. Weitere Informationen finden Sie in der [MediaLine-Tabelle.](medialine-0.md) <br/> |
|**CallerPAI** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |P-Asserted-Identity des Benutzers, der den Anruf getätigt hat. Die P-Asserted-Identity (PAI) wird verwendet, um die tatsächliche Identität des Benutzers zu vermitteln, der den Anruf getätigt hat.  <br/> |
|**CalleeEndpoint** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |Endpunkt, der den Anruf empfangen hat.  <br/> |
|**CalleeUserAgent** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |Benutzer-Agent, der von dem Benutzer eingesetzt wird, der den Anruf empfangen hat. Benutzer-Agents stellen das Clientendpunktgerät dar.  <br/> |
|**CalleeUri** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |SIP-URI des Benutzers, der den Anruf empfangen hat.  <br/> |
   

