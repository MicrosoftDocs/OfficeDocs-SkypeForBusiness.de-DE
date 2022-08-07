---
title: 'Direct Routing für Teams-Telefonsysteme: Definitionen und RFC-Standards'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/16/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: So implementiert Microsoft Phone System Direct Routing RFC-Standardprotokolle.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 01dbd61748d14ef21a600b2e4f44a306517e46d9
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271240"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>Direct Routing – Definitionen und RFC-Standards

In diesem Artikel wird beschrieben, wie Microsoft Phone System Direct Routing RFC-Standardprotokolle implementiert. Dieser Artikel richtet sich an Sprachadministratoren, die für die Konfiguration der Verbindung zwischen dem lokalen Session Border Controller (SBC) und dem SIP-Proxydienst (Session Initiation Protocol) verantwortlich sind.

Der SBC des Kunden verbindet sich mit den folgenden Komponenten im Microsoft Teams-Back-End: 

- **Der SIP-Proxy** für die Signalisierung. Dies ist die ins Internet gerichtete Komponente von Direct Routing, die SIP-Verbindungen (TLS) zwischen sbCs und Direct Routing verarbeitet.

- **Die Medienprozessoren** für Medien. Dies ist die im Internet zugängliche Komponente von Direct Routing, die den Mediendatenverkehr verarbeitet. Diese Komponente verwendet SRTP- und SRTCP-Protokolle.


Weitere Informationen zu Direct Routing finden Sie unter [Telefonsystem-Direct Routing](direct-routing-landing-page.md).

Weitere Informationen dazu, wie Direct Routing das SIP-Protokoll implementiert, finden Sie [unter Direct Routing – SIP-Protokoll](direct-routing-protocols-sip.md).

## <a name="rfc-standards"></a>RFC-Standards

Direct Routing entspricht RFC-Standards.  Der mit Direct Routing verbundene SBC muss auch den folgenden RFCs (oder deren Nachfolgern) entsprechen. 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>Standards für Geräte, die den Umgehungsmodus ohne Medien unterstützen 

Die folgenden Standards gelten für Geräte, die nur den Umgehungsmodus ohne Medien unterstützen:

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol
- [RFC 3325](https://www.ietf.org/rfc/rfc3325). Private Erweiterung des Sitzungsinitiierungsprotokolls für die eingefügte Identität in vertrauenswürdigen Netzwerken – Abschnitte zum Behandeln des P-Asserted-Identity-Headers. Direct Routing sendet P-Asserted-Identity mit Datenschutz-ID-Headern. 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Eine Erweiterung des Session Initiation Protocol (SIP) für erforderliche Verlaufsinformationen. Weitere Informationen finden Sie unter:Routing SIP Protocol description for more information.
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) Der Referred-By-Mechanismus des Sitzungsinitiierungsprotokolls
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) Der Session Initiation Protocol (SIP)-Header "Replaces" 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) Session Initiation Protocol (SIP) Verwendung des Angebots-/Antwortmodells.
  Weitere Informationen finden Sie im Abschnitt "Abweichungen von RFC".
- [RFC 3711](https://tools.ietf.org/html/rfc3711) und [RFC 4771](https://tools.ietf.org/html/rfc4771). Schützen von RTP-Datenverkehr mit SRTP. Der SBC muss in der Lage sein, Schlüssel mithilfe von SDES einzurichten. 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) SDP-Angebots-/Antwortklärungen (Session Description Protocol) für RTP-/RTCP-Multiplexing

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>Standards für Geräte, die den Medienumgehungsmodus unterstützen

Zusätzlich zu den standards listed as applicable to non-bypass mode, the following standards are used for media bypass mode:

- [RFC 5245 Interactive Connectivity Establishment (ICE) für die Medienumgehung](https://tools.ietf.org/html/rfc5245).  Der SBC muss Folgendes unterstützen:
  - ICE Lite - Die Teams-Clients sind volle ICE-Clients
  - [ICE-Neustarts](https://tools.ietf.org/html/rfc5245#section-9.1.1.1). Weitere Informationen zu ICE-Neustarts – Anwendungsfall und Beispiele im ICE-Neustart: Medienumgehungsaufruf, der an einen Endpunkt weitergeleitet wird, der die Medienumgehung nicht unterstützt   
- [RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Übertragung](https://tools.ietf.org/html/rfc5589). 
- [Rfc 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), see sections 3.1, Forking, and 3.2, Ringing Tone Generation 
- [RFC 5389 Session Traversal Utilities for NAT (STUN)](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 Traversal Using Relays around NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>Für die Unterstützung der Übermittlung von Standortinformationen an E911-Anbieter geltende Standards

- [RFC 6442, Location Conveyance for the Session Initiation Protocol](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>Abweichungen vom RFC

In der folgenden Tabelle sind die Abschnitte der RFC(s) aufgeführt, in denen die Implementierung von SIP oder Medienstapel durch Microsoft vom Standard abweicht:

| RFC und Abschnitte | Beschreibung | Abweichung |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337, Abschnitt 5.3: Halten und Fortsetzen von Medien](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC ermöglicht die Verwendung von "a=inactive", "a=sendonly", a=recvonly", um einen Anruf in den Haltebereich zu setzen. |Der SIP-Proxy unterstützt nur "a=inactive" und versteht nicht, ob der SBC "a=sendonly" oder "a=recvonly" sendet.
| [RFC 6337, Abschnitt 5.4 "Verhalten beim Empfangen von SDP mit c=0.0.0.0](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264) erfordert, dass ein Agent SDP mit der Verbindungsadresse 0.0.0.0 empfangen kann. In diesem Fall bedeutet dies, dass weder RTP noch RTCP an den Peer gesendet werden sollten. | Diese Option wird vom SIP-Proxy nicht unterstützt. |

## <a name="operational-modes"></a>Betriebsmodi

Es gibt zwei Betriebsmodi für Direct Routing:

- **Ohne Medienumgehung** , bei der der gesamte RTP-Datenverkehr zwischen dem Teams-Client, den Medienprozessoren und dem SBC fließt.  

- **Mit Medienumgehung** , bei der alle RTP-Medien zwischen den Teams-Endpunkten und dem SBC fließen. 

Beachten Sie, dass DER SIP-Datenverkehr immer über den SIP-Proxy fließt. 

## <a name="dtmf"></a>DTMF
In-Band-DTMF wird vom Medienstapel nicht unterstützt.
