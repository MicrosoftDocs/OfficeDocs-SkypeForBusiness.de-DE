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
description: Direct Routing-Protokolle
appliesto:
- Microsoft Teams
ms.openlocfilehash: 88fb4459192ad9ff5af8702878d1cbf6a59d8e9d
ms.sourcegitcommit: 6227667c9941cc3289029099b7b6781581f16ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52569203"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>Direct Routing – Definitionen und RFC-Standards

In diesem Artikel wird beschrieben, Microsoft-Telefon System Direct Routing RFC-Standardprotokolle implementiert. Dieser Artikel richtet sich an Sprachadministratoren, die für die Konfiguration der Verbindung zwischen dem lokalen Session Border Controller (SBC) und dem SIP-Proxydienst (Session Initiation Protocol) verantwortlich sind.

Der SBC-Kunde schnittstellen zu den folgenden Komponenten im Microsoft Teams Back-End: 

- **Der SIP-Proxy** für Signalisierungen. Dies ist die in das Internet gerichtete Komponente des Direct-Routings, die SIP-Verbindungen (TLS) zwischen den SBCs und Direct Routing behandelt.

- **Die Medienprozessoren** für Medien. Dies ist die in das Internet gerichtete Komponente von Direct-Routing, die den Medienverkehr behandelt. Diese Komponente verwendet die Protokolle SRTP und SRTCP.


Weitere Informationen zu Direct-Routing finden Sie unter Telefonsystem [Direct-Routing.](direct-routing-landing-page.md)

Weitere Informationen zur Implementierung des SIP-Protokolls durch Direct Routing finden Sie unter [Direct-Routing – SIP-Protokoll.](direct-routing-protocols-sip.md)

## <a name="rfc-standards"></a>RFC-Standards

Direct Routing entspricht DEN RFC-Standards.  Der mit Direct Routing verbundene SBC muss auch den folgenden RFCs (oder deren Nachfolgern) entsprechen. 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>Standards für Geräte, die den Nicht-Medienumgehungsmodus unterstützen 

Die folgenden Standards gelten für Geräte, die nur den Nicht-Medienumgehungsmodus unterstützen:

- [RFC 3261 SIP:](https://tools.ietf.org/html/rfc3261)Session Initiation Protocol
- [RFC 3325](https://www.ietf.org/rfc/rfc3325). Private Erweiterung des Session Initiation Protocol für bestätigte Identität in vertrauenswürdigen Netzwerken – Abschnitte zum Behandeln des Headers "P-Asserted-Identity". Direct Routing sendet P-Asserted-Identity mit Datenschutz-ID-Headern. 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Eine Erweiterung des Session Initiation Protocol (SIP) für erforderliche Verlaufsinformationen. Weitere Informationen finden Sie unter Routing SIP-Protokollbeschreibung.
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) Der Sitzungsinitiierungsprotokoll-Referred-By Mechanismus
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) Der Sip-Header (Session Initiation Protocol) "Replaces" 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) Verwendung des Angebots-/Antwortmodells (Session Initiation Protocol, SIP).
  Weitere Informationen finden Sie im Abschnitt "RFC-Abweichungen".
- [RFC 3711](https://tools.ietf.org/html/rfc3711) und [RFC 4771.](https://tools.ietf.org/html/rfc4771) Schützen Sie RTP-Datenverkehr mithilfe von SRTP. Der SBC muss in der Lage sein, Schlüssel mithilfe von SDES zu erstellen. 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) SDP-Angebots-/Antworterklärungen für RTP/RTCP-Multiplexing

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>Standards für Geräte, die den Medienumgehungsmodus unterstützen

Zusätzlich zu den Standards, die für den Nichtumgehungsmodus gelten, werden die folgenden Standards für den Medienumgehungsmodus verwendet:

- [RFC 5245 Interactive Connectivity Connectivity Connectivity (ICE) für die Medienumgehung.](https://tools.ietf.org/html/rfc5245)  Der SBC muss Folgendes unterstützen:
  - ICE Lite – die Teams Clients sind vollständige ICE-Clients
  - [ICE wird neu gestartet.](https://tools.ietf.org/html/rfc5245#section-9.1.1.1) Weitere Informationen finden Sie unter ICE-Neustarts – Anwendungsfall und Beispiele in ICE Restart: Media bypass call transferred to an endpoint which does not support media bypass   
- [RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589) 
- [RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960)( siehe Abschnitte 3.1, Forking und 3.2, Klingeltongenerierung) 
- [RFC 5389 Session Traversal Utilities for NAT (STUN)](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>Standards, die zur Unterstützung der Vermittlung von Standortinformationen an E911-Anbieter gelten

- [RFC 6442, Location Conveyance for the Session Initiation Protocol](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>Abweichungen von den RFC-

In der folgenden Tabelle sind die Abschnitte der RFC(s) aufgeführt, in denen die Implementierung des SIP- oder Medienstapels von Microsoft vom Standard abweichen kann:

| RFC und Abschnitte | Beschreibung | Abweichung |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337, Abschnitt 5.3 – Halten und Fortsetzen von Medien](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC ermöglicht die Verwendung von "a=inactive", "a=sendonly", a=recvonly" zum Halten eines Anrufs. |Der SIP-Proxy unterstützt nur "a=inactive" und versteht nicht, ob der SBC "a=sendonly" oder "a=recvonly" sendet.
| [RFC 6337, Abschnitt 5.4 "Verhalten beim Empfangen von SDP mit c=0.0.0.0](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264) erfordert, dass ein Agent SDP mit der Verbindungsadresse 0.0.0.0 empfangen kann. In diesem Fall bedeutet dies, dass weder RTP noch RTCP an den Peer gesendet werden sollten. | Der SIP-Proxy unterstützt diese Option nicht. |

## <a name="operational-modes"></a>Betriebsmodi

Es gibt zwei Betriebsmodi für Direct-Routing:

- **Ohne Medienumgehung,** bei der der rtp-Datenverkehr zwischen dem Teams-Client, den Medienprozessoren und dem SBC fließt.  

- **Mit der Medienumgehung,** bei der alle RTP-Medien zwischen den Teams und dem SBC fließen. 

Beachten Sie, dass der SIP-Datenverkehr immer über den SIP-Proxy fließt. 

## <a name="dtmf"></a>MFV
In-Band DTMF wird vom Medienstapel nicht unterstützt.
