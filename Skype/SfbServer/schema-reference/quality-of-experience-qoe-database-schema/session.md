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
description: Jeder Datensatz stellt eine Sitzung dar, die Audio oder Audio und Video umfasst. Sie enthält allgemeine Informationen zur Sitzung. Eine Sitzung ist als ein Audio- oder Video-SIP-Dialogfeld (Session Initiation Protocol) zwischen zwei Endpunkten definiert.
ms.openlocfilehash: cdf639e7360248e02378c66eb68a60d49acb9749
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802675"
---
# <a name="session-table"></a>Sitzungstabelle
 
Jeder Datensatz stellt eine Sitzung dar, die Audio oder Audio und Video umfasst. Sie enthält allgemeine Informationen zur Sitzung. Eine Sitzung ist als ein Audio- oder Video-SIP-Dialogfeld (Session Initiation Protocol) zwischen zwei Endpunkten definiert.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |Datum/Uhrzeit  <br/> |Primary  <br/> |Referenziert aus der [Dialogtabelle](dialog.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Referenziert aus der [Dialogtabelle](dialog.md).  <br/> |
|**ConferenceKey** <br/> |int  <br/> |Fremd  <br/> |Konferenzschlüssel. Referenziert aus der [Konferenztabelle](conference.md).  <br/> |
|**CorrelationKey** <br/> |int  <br/> |Fremd  <br/> |Korrelationsschlüssel. Referenziert aus der [SessionCorrelation-Tabelle.](sessioncorrelation.md)  <br/> |
|**DialogCategory** <br/> |bit  <br/> | <br/> |Dialogkategorie; 0 ist die Skype for Business Server-zu-Vermittlungsserver-Leg; 1 ist die Vermittlungsserver-zu-PSTN-Gateway-Leg.  <br/> |
|**MediationServerBypassFlag** <br/> |bit  <br/> ||Flag, das angibt, ob der Anruf umgangen wurde oder nicht.  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||Dieses Feld gibt an, warum ein Anruf nicht umgangen wurde, selbst wenn die Umgehungs-IDs übereinstimmen. Für Skype for Business Server ist nur ein Wert definiert.  <br/> 0x0001 – Unbekannte Umgehungs-ID für Standardnetzwerkadapter.  <br/> |
|**StartTime** <br/> |Datum/Uhrzeit  <br/> | <br/> |Die Startzeit des Anrufs.  <br/> |
|**EndTime** <br/> |Datum/Uhrzeit  <br/> | <br/> |Die Endzeit des Anrufs.  <br/> |
|**CallerPool** <br/> |int  <br/> |Fremd  <br/> |Der Pool des Anrufers. Referenziert aus der [Pooltabelle](pool.md).  <br/> |
|**CalleePool** <br/> |int  <br/> |Fremd  <br/> |Der Pool des Anrufempfängers. Referenziert aus der [Pooltabelle](pool.md).  <br/> |
|**CalleePAI** <br/> |int  <br/> |Fremd  <br/> |SIP-URI in der SIP-P-Asserted Identity (PAI) des empfangenden Endpunkts. Referenziert aus der [Benutzertabelle](user-0.md).  <br/> |
|**CallerURI** <br/> |int  <br/> |Fremd  <br/> |URI des Anrufers. Referenziert aus der [Benutzertabelle](user-0.md).  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |Fremd  <br/> |Endpunkt des Anrufers. Referenziert aus der [Endpunkttabelle](endpoint.md).  <br/> |
|**CallerUserAgent** <br/> |bit  <br/> |Fremd  <br/> |Der Benutzeragent des Anrufers. Referenziert aus der [UserAgent -Tabelle](useragent.md).  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||Die Priorität dieses Aufrufs.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Diese Spalte ist veraltet und wird in Skype for Business Server nicht verwendet. Stattdessen werden diese Informationen auf basis der Medienlinien gemeldet. Weitere Informationen finden [Sie in der Tabelle "MediaLine".](medialine-0.md) <br/> |
|**CallerPAI** <br/> |int  <br/> |Fremd  <br/> |P-Asserted-Identity des Benutzers, der den Anruf abting. Die P-Asserted-Identity (PAI) wird verwendet, um die echte Identität des Benutzers zu vermitteln, der den Anruf abting.  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |Fremd  <br/> |Endpunkt, der den Anruf empfangen hat.  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |Fremd  <br/> |Der vom Benutzer, der den Anruf angenommen hat, eingesetzter Benutzeragent. Benutzeragenten stellen das Clientendpunktgerät dar.  <br/> |
|**CalleeUri** <br/> |int  <br/> |Fremd  <br/> |SIP-URI des Benutzers, der den Anruf empfangen hat.  <br/> |
   

