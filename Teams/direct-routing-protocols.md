---
title: Direktes Routing für Telefonsysteme
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/16/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: Direkte Routing Protokolle
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7462822626b698f95b80a716a55f94dfe92148ff
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41835025"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>Direct Routing-Definitionen und RFC-Standards

In diesem Artikel wird beschrieben, wie das direkt Routing von Microsoft Phone System RFC-Standardprotokolle implementiert. Dieser Artikel richtet sich an sprach Administratoren, die für die Konfiguration der Verbindung zwischen dem lokalen Session Border Controller (SBC) und dem SIP-Proxydienst (Session Initiation Protocol) verantwortlich sind.

Der Kunde SBC Schnittstellen mit den folgenden Komponenten im Microsoft Teams-Back-End ab: 

- **Der SIP-Proxy** zum signalisieren. Hierbei handelt es sich um die mit dem Internet verbundene Komponente des direkten Routings, die SIP (TLS)-Verbindungen zwischen dem SBCS und dem direkten Routing verarbeitet.

- **Die Medien Prozessoren** für Medien. Hierbei handelt es sich um die mit dem Internet verbundene Komponente des direkten Routings, die den Mediendatenverkehr verarbeitet. Diese Komponente verwendet SRTP-und SRTCP-Protokolle.


Weitere Informationen zum direkten Routing finden Sie unter [Direktes Routing für das Telefon System](direct-routing-landing-page.md).

Weitere Informationen dazu, wie das SIP-Protokoll von Direct Routing implementiert wird, finden Sie unter [Direct Routing – SIP-Protokoll](direct-routing-protocols-sip.md).

## <a name="rfc-standards"></a>RFC-Standards

Das direkte Routing entspricht den RFC-Standards.  Der SBC, der mit Direct Routing verbunden ist, muss auch den folgenden RFCs (oder deren Nachfolgern) entsprechen. 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>Standards für Geräte, die den nicht-Medien-Bypass-Modus unterstützen 

Die folgenden Standards gelten für Geräte, die nur den nicht-Medien-Bypass-Modus unterstützen:

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol
- [RFC 3325](https://www.ietf.org/rfc/rfc3325). Private Erweiterung des Sitzungs Initiierungs Protokolls für die Assertions Identität in vertrauenswürdigen Netzwerken – Abschnitte zur Behandlung von P-Asserted-Identity-Header. Direct Routing sendet P-Asserted-Identity mit Datenschutz-ID-Headern. 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Eine Erweiterung des Session Initiation Protocol (SIP) für erforderliche Verlaufsinformationen. Weitere Informationen finden Sie auch unter Routing SIP-Protokoll Beschreibung.
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) Mechanismus für das Sitzungs Initiierungs Protokoll
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) Der Header des Session Initiation Protocol (SIP) "ersetzt" 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) SIP-Nutzung (Session Initiation Protocol) des Angebots/Antwort-Modells
  Lesen Sie den Abschnitt "Abweichungen von RFC".
- [RFC 3711](https://tools.ietf.org/html/rfc3711) und [RFC 4771](https://tools.ietf.org/html/rfc4771). Schützen Sie den RTP-Datenverkehr mithilfe von SRTP. Der SBC muss in der Lage sein, Schlüssel mithilfe von SDES festzulegen. 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Session Description Protocol (SDP)-Angebot/Antwort Klärungen für RTP/RTCP-Multiplexing

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>Für Geräte, die den Medien Umgehungsmodus unterstützen, gelten Standards

Zusätzlich zu den Standards, die in Bezug auf den nicht-Bypass-Modus aufgeführt sind, werden die folgenden Standards für den Medien Umgehungsmodus verwendet:

- [RFC 5245 Interactive Connectivity Establishment (ICE) für die medienumgehung](https://tools.ietf.org/html/rfc5245)  Der SBC muss Folgendes unterstützen:
  - Ice lite – die Kunden von Teams sind Full Ice-Kunden
  - [Ice startet neu](https://tools.ietf.org/html/rfc5245#section-9.1.1.1). Weitere Informationen finden Sie unter Ice-Neustarts Anwendungsfall und Beispiele im ICE-Neustart: Medien Umgehungs Anruf an einen Endpunkt übertragen, der keine medienumgehung unterstützt   
- [RFC RFC 5589 Session Initiation Protocol (SIP)-Anrufsteuerung – Übertragung](https://tools.ietf.org/html/rfc5589). 
- [RFC 3960 Early Media und Klingelton Generierung im Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), siehe Abschnitte 3,1, Forking und 3,2, Klingelton Generierung 
- [RFC 5389-Sitzungs Traversal-Dienstprogramme für NAT (Stun)](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 Traversal mit Relays um NAT (wiederum): Relay-Erweiterungen zu Session Traversal Utilities für NAT (Stun)](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>Standards, die für die Unterstützung der Übermittlung von Standortinformationen an E911-Anbieter gelten

- [RFC 6442, Standortübertragung für das Sitzungs Initiierungs Protokoll](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>Abweichungen von der RFC

In der folgenden Tabelle sind die Abschnitte der RFC (s) aufgeführt, in denen die Implementierung des SIP-oder Medien Stapels von Microsoft vom Standard abweicht:

| RFC und Abschnitte | Beschreibung | Abweichung |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337, Abschnitt 5,3 halten und Fortsetzen von Medien](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC ermöglicht die Verwendung von "a = inaktiv", "a = sendonly", a = recvonly ", um einen Anruf in Wartestellung zu platzieren. |Der SIP-Proxy unterstützt nur "a = inaktiv" und versteht nicht, ob der SBC "a = sendonly" oder "a = recvonly" sendet.
| [RFC 6337, Abschnitt 5,4 "Verhalten beim Empfangen von SDP mit c = 0.0.0.0](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264) erfordert, dass ein Agent SDP mit einer Verbindungsadresse von 0.0.0.0 empfangen kann, in diesem Fall bedeutet dies, dass weder RTP noch RTCP an den Peer gesendet werden sollen. | Diese Option wird vom SIP-Proxy nicht unterstützt. |

## <a name="operational-modes"></a>Betriebsmodi

Es gibt zwei Betriebsmodi für das direkte Routing:

- **Ohne medienumgehung** , bei der der gesamte RTP-Datenverkehr zwischen dem Teams-Client, den Medien Prozessoren und dem SBC fließt.  

- **Mit medienumgehung** , bei der alle RTP-Medien zwischen den Endpunkten der Teams und dem SBC fließen. 

Beachten Sie, dass der SIP-Datenverkehr immer über den SIP-Proxy fließt.   
