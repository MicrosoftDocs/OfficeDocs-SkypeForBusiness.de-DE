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
description: Direkte Routingprotokolle
appliesto:
- Microsoft Teams
ms.openlocfilehash: 88fb4459192ad9ff5af8702878d1cbf6a59d8e9d
ms.sourcegitcommit: 6227667c9941cc3289029099b7b6781581f16ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52569203"
---
# <a name="direct-routing---definitions-and-rfc-standards"></a>Direct Routing - Definitionen und RFC-Standards

In diesem Artikel wird beschrieben, wie Microsoft-Telefon System Direct Routing RFC-Standardprotokolle implementiert. Dieser Artikel richtet sich an Sprachadministratoren, die für die Konfiguration der Verbindung zwischen dem lokalen Session Border Controller (SBC) und dem SIP-Proxydienst (Session Initiation Protocol) verantwortlich sind.

Die Kunden-SBC-Schnittstellen mit den folgenden Komponenten im Microsoft Teams Backend: 

- **Der SIP-Proxy** für die Signalisierung. Dies ist die internetbezogene Komponente von Direct Routing, die SIP-Verbindungen (TLS) zwischen den SBCs und Direct Routing verarbeitet.

- **Die Medienprozessoren** für Medien. Dies ist die internetbezogene Komponente von Direct Routing, die den Mediendatenverkehr verarbeitet. Diese Komponente verwendet SRTP- und SRTCP-Protokolle.


Weitere Informationen zum Direct Routing finden Sie unter [Telefonsystem Direct Routing](direct-routing-landing-page.md).

Weitere Informationen dazu, wie Direct Routing das SIP-Protokoll implementiert, finden Sie unter [Direct Routing - SIP-Protokoll](direct-routing-protocols-sip.md).

## <a name="rfc-standards"></a>RFC-Standards

Direct Routing entspricht den RFC-Standards.  Die mit Direct Routing verbundene SBC muss auch die folgenden RFCs (oder deren Nachfolger) erfüllen. 

### <a name="standards-applicable-to-devices-that-support-non-media-bypass-mode"></a>Standards für Geräte, die den Bypass-Modus a-media unterstützen 

Die folgenden Standards gelten für Geräte, die nur den Nicht-Medien-Bypass-Modus unterstützen:

- [RFC 3261 SIP](https://tools.ietf.org/html/rfc3261): Session Initiation Protocol
- [RFC 3325](https://www.ietf.org/rfc/rfc3325). Private Erweiterung des Session Initiation Protocol für bestätigte Identität in vertrauenswürdigen Netzwerken - Abschnitte zur Behandlung des P-Asserted-Identity-Headers. Direct Routing sendet P-Asserted-Identity mit Privacy ID-Headern. 
- [RFC 4244](https://www.ietf.org/rfc/rfc4244.txt) Eine Erweiterung des Session Initiation Protocol (SIP) für erforderliche Verlaufsinformationen. Weitere Informationen finden Sie auch: Routing-SIP-Protokollbeschreibung.
- [RFC 3892](https://www.ietf.org/rfc/rfc3892.txt) Das Sitzungsinitiierungsprotokoll Referred-By Mechanismus
- [RFC 3891](https://www.ietf.org/rfc/rfc3891.txt) Der "Replaces"-Header (Session Initiation Protocol) 
- [RFC 6337](https://tools.ietf.org/html/rfc6337) SIP(Session Initiation Protocol) Verwendung des Angebots/Antwortmodells.
  Siehe Abschnitt "Abweichungen von RFC".
- [RFC 3711](https://tools.ietf.org/html/rfc3711) und [RFC 4771](https://tools.ietf.org/html/rfc4771). Schützen Sie RTP-Datenverkehr mit SRTP. Der SBC muss in der Lage sein, Schlüssel mit SDES einzurichten. 
- [RFC 8035](https://www.ietf.org/rfc/rfc8035.txt) Session Description Protocol (SDP) Angebot/Antwort Klarstellungen für RTP/RTCP Multiplexing

### <a name="standards-applicable-to-devices-that-support-media-bypass-mode"></a>Standards für Geräte, die den Medienumgehungsmodus unterstützen

Zusätzlich zu den Standards, die für den Nichtumgehungsmodus aufgeführt sind, werden die folgenden Standards für den Medienumgehungsmodus verwendet:

- [RFC 5245 Interactive Connectivity Establishment (ICE) für Medienumgehung](https://tools.ietf.org/html/rfc5245).  Der SBC muss Folgendes unterstützen:
  - ICE Lite - die Teams Kunden sind volle ICE-Clients
  - [ICE startet neu](https://tools.ietf.org/html/rfc5245#section-9.1.1.1). Weitere Informationen zum Anwendungsfall für ICE-Neustarts und Beispiele in ICE Restart: Medienumgehungsaufruf, der an einen Endpunkt übertragen wird, der die Medienumgehung nicht unterstützt   
- [RFC RFC 5589 Session Initiation Protocol (SIP) Call Control – Transfer](https://tools.ietf.org/html/rfc5589). 
- [RFC 3960 Early Media and Ringing Tone Generation in the Session Initiation Protocol (SIP)](https://tools.ietf.org/html/rfc3960), siehe Abschnitte 3.1, Forking und 3.2, Ringing Tone Generation 
- [RFC 5389 Session Traversal Utilities für NAT (STUN)](https://tools.ietf.org/html/rfc5389)
- [RFC 5766 Traversal mit Relais um NAT (TURN): Relay Extensions to Session Traversal Utilities for NAT (STUN)](https://tools.ietf.org/html/rfc5766)

### <a name="standards-applicable-to-support-conveying-location-information-to-e911-providers"></a>Normen für die Unterstützung der Übermittlung von Standortinformationen an E911-Anbieter

- [RFC 6442, Standortübertragung für das Session Initiation Protocol](https://tools.ietf.org/html/rfc6442)

### <a name="deviations-from-the-rfcs"></a>Abweichungen von den RFC-

In der folgenden Tabelle sind die Abschnitte der RFC(s) aufgeführt, in denen die Implementierung des SIP- oder Medienstapels durch Microsoft vom Standard abweicht:

| RFC und Abschnitte | Beschreibung | Abweichung |
| :---------------------  |:---------------------- |:-----------------------|
| [RFC 6337, Abschnitt 5.3 Medienhalten und Fortsetzen](https://tools.ietf.org/html/rfc6337#section-5.3) | RFC ermöglicht die Verwendung von "a=inactive", "a=sendonly", a=recvonly", um einen Anruf in der Warteschleife zu platzieren. |Der SIP-Proxy unterstützt nur "a=inactive" und versteht nicht, ob der SBC "a=sendonly" oder "a=recvonly" sendet.
| [RFC 6337, Abschnitt 5.4 "Verhalten beim Empfangen von SDP mit c=0.0.0.0](https://tools.ietf.org/html/rfc6337#section-5.4) | [RFC3264](https://tools.ietf.org/html/rfc3264) erfordert, dass ein Agent SDP mit der Verbindungsadresse 0.0.0.0 empfangen kann. | Der SIP-Proxy unterstützt diese Option nicht. |

## <a name="operational-modes"></a>Betriebsmodi

Es gibt zwei Betriebsmodi für Direct Routing:

- **Ohne Medienumgehung,** bei der der gesamte RTP-Datenverkehr zwischen dem Teams Client, den Medienprozessoren und dem SBC fließt.  

- **Mit Medienumgehung,** bei der alle RTP-Medien zwischen den Teams Endpunkten und dem SBC fließen. 

Beachten Sie, dass DER SIP-Datenverkehr immer über den SIP-Proxy fließt. 

## <a name="dtmf"></a>Dtmf
In-Band-DTMF wird vom Medienstapel nicht unterstützt.
