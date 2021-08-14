---
title: Telefon zum direkten Routing des Systems
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
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
description: hHw Direct-Routing unterstützt die Medienumgehung mit einem für ICE Lite aktivierten Session Border Controller.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c32838d282d6f5fff5eb1e85c36d78eee8828d41
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2021
ms.locfileid: "58234570"
---
# <a name="overview"></a>Übersicht

In diesem Artikel wird beschrieben, wie Direct Routing die Medienumgehung mit einem für ICE Lite aktivierten Session Border Controller (SBC) unterstützt, wie in [RFC 5245 beschrieben.](https://tools.ietf.org/html/rfc5245) Dieser Artikel richtet sich an Sprachadministratoren, die für die Konfiguration der Verbindung zwischen dem lokalen SBC und dem SIP-Proxydienst zuständig sind.

Dieser Artikel bietet eine Übersicht über die ICE Lite-Szenarien und -Anforderungen für die Interoperabilität. In diesem Artikel werden die Nachrichtenformate und die erforderlichen Zustandsautomatenübergänge beschrieben, um zuverlässige Anrufe und Medienströme sicherzustellen.

## <a name="terminology"></a>Terminologie

- First Hello – Die ersten Worte, die vom Anrufer und Anrufer gesprochen werden. Es ist wichtig, dass alle Anstrengungen unternommen werden, um sicherzustellen, dass die ersten Pakete von den Endpunkten für die meisten Einsatzfälle zuverlässig übermittelt werden.

- Freisprechen – Das Angebot des Anrufers kann an mehrere Endpunkte für Anrufer übermittelt werden, wenn der Anrufer auf mehreren Geräten verfügbar ist (beispielsweise könnte ein Teams-Benutzer bei Teams für Windows und Teams für Android oder iPhone angemeldet sein).

- Provisorische Antwort (183) – Die Endpunkte der Anrufe zur schnelleren Anrufeinrichtung senden eine Antwort mit den Kandidaten und Schlüsseln, die für die Einrichtung des Medienflusses erforderlich sind. Dies geschieht im Voraus, wenn der Benutzer den Anruf (200OK) dieser bestimmten Anruferinstanz entgegennahme. Mit "Forking" sollte der Anrufer mehrere provisorische Antworten erhalten können.

- Re-Invite – Angebot mit endgültigen Kandidaten, die vom ICE-Steuerungsendpunkt ausgewählt wurden. Dies hat das "a=remote-candidate"-Attribut, um alle Rennbedingungen aus der Behandlung mehrerer Forks zu lösen.

- Teams Endpunkt : Dies kann entweder ein Server (Medienprozessor, Transport relay) oder der Teams sein.

## <a name="message-format"></a>Nachrichtenformat

Die Teams verwendet RFC 5245 für ICE-Lite. Dies bedeutet, dass alle STUN-Nachrichten [RFC 5389 entsprechen.](https://tools.ietf.org/html/rfc5389)

Die SBCs, die RFC 5389 erfordert, müssen alle STUN-Attribute ignorieren, die sie nicht erkennen, und die Meldungen weiterhin mit den bekannten Attributen verarbeiten. 

Wenn falsch formatierte Pakete empfangen werden, müssen die Pakete verworfen werden, ohne dass dies Auswirkungen auf die Mediensitzung hat.

## <a name="ice-lite-requirements"></a>ICE Lite-Anforderungen

In diesem Abschnitt werden die Anforderungen für ICE Lite kurz beschrieben.

### <a name="candidate-gathering"></a>Kandidatentreffen

Der SBC darf nur einen Kandidaten anbieten, der öffentlich erreichbar ist. Derzeit werden nur IPV4-Kandidaten unterstützt.


#### <a name="connectivity-checks"></a>Verbindungsüberprüfungen

Die ICE Lite-Implementierung muss auf empfangene Verbindungsüberprüfungen reagieren. Der ICE Lite-Endpunkt darf keine Konnektivitätsprüfungsanforderungen senden. (Wenn Konnektivitätsprüfungen verletzt gesendet werden, reagiert die vollständige Implementierung, was dazu führen kann, dass unerwartete von Peers abgeleitete Kandidaten ermittelt werden und potenziell Fehler beim Aufruf zur Folge haben.)

#### <a name="nominations"></a>Ausdingungen

Der ENDPUNKT für die vollständige ICE-Implementierung ist immer der Endpunkt "Steuern" und folgt den "regulären" Anweisungen für die Auswahl der endgültigen Kandidaten, die für den Medienfluss verwendet werden sollen. Der ICE Lite-Endpunkt kann die Abos verwenden, um den Pfad zu schließen, der für die Mediennutzung und die vollständige Anrufering verwendet werden soll.

Hinweis: Im Fall von Aufschütten mit Peerendpunkten, die Antworten auf 183 Provisoren senden, muss der SBC bereit sein, auf Prüfungen von mehreren Endpunkten zu reagieren, und auch von mehreren Endpunkten aus, wenn die Benachrichtigungen vor 200OK auftreten. Abhängig von der Konvergenz des ICE-Zustandsautomaten für den endgültigen Pfad und der Anzeigedauer der Antwort durch den Benutzer kann der Spielstand vor oder nach 200OK auftreten. Der SBC muss in der Lage sein, beide Fälle zu behandeln.

#### <a name="converging-for-forking"></a>Konvergenz fürs Aufschütten

Wenn das Angebot von den SBC-Forks an mehrere Teams-Endpunkte Teams, reagieren die Teams-Endpunkte möglicherweise mit einer provisorischen Antwort und starten Konnektivitätsüberprüfungen. Der SBC muss darauf vorbereitet sein, Konnektivitätsprüfungen zu empfangen und auf Konnektivitätsüberprüfungen von mehreren Peerendpunkten zu reagieren. Beispielsweise könnte der Teams an einem Desktop und einem Mobiltelefon angemeldet sein. Beide Geräte werden über den eingehenden Anruf benachrichtigt und versuchen, die Konnektivitätsüberprüfungen mit dem SBC durchzuführen.

Schließlich wird nur einer der Endpunkte den Anruf entgegenrufen (200OK). Beim Empfangen von 200OK kann der SBC den richtigen Kontext für die Verarbeitung der Medienpakete einrichten.

## <a name="scenarios"></a>Szenarien

###  <a name="inbound-call-from-sbc"></a>Eingehender Anruf von SBC

In diesem Szenario gibt es mehrere mögliche Peerendpunkte, die der SBC behandeln muss:

- Serverendpunkte reagieren in der Regel direkt mit 200OK. Dabei handelt es sich um vollständige ICE-Endpunkte, die in der Regel in Szenarien mit Voicemail, Anrufwarteschleife und automatischer Telefonant einbezogen sind.

- Kundenendpunkte können mehrere Antworten auf provisorische Antworten mit unterschiedlichen Von/Zu-Tags (183) gefolgt von einem 200OK vom Endpunkt senden, der den Anruf beantwortet. Dies sind vollständige ICE-Endpunkte, die in der Regel Endbenutzerclients darstellen.

- Andere SBC-Endpunkte. Dies sind ICE Lite-Endpunkte, die in der Regel am Szenario des gleichzeitigen Anrufens von Clientendpunkten und einer anderen Telefonnummer beteiligt sind.

Der SBC muss auf alle gültigen Verbindungsüberprüfungsanforderungen reagieren, die von den vollständigen ICE-Endpunkten empfangen wurden. Nach RFC werden die vollständigen ICE-Endpunkte zu Kontrollendpunkten. Die Teams (Client/Server)-Endpunkte führen "Regelmäßige" Konnektivitätsprüfungen durch. Die letzten 200Ok-Daten können entweder von einem Endpunkt aus kommen, der frühe Medien gesendet hat, oder von einem anderen Endpunkt. Beim Empfang des 200Ok muss der SBC den richtigen Kontext für den Medienfluss einrichten. 

###  <a name="early-media"></a>Early media

Wenn ein frühzeitiger Medienfluss besteht, muss der SBC den ersten Endpunkt ausrufen, der mit dem Streamen von Medien beginnt. der Medienfluss beginnen kann, bevor die Kandidaten benannt werden. Der SBC sollte in dieser Phase über Unterstützung für das Senden von MFV verfügen, um IVR-/Voicemailszenarien zu ermöglichen. Der SBC sollte den Pfad mit der höchsten Priorität verwenden, für den es Überprüfungen empfangen hat, wenn die Zeit des Einsatzes nicht abgeschlossen wurde.

### <a name="outbound-call-to-sbc"></a>Ausgehender Anruf bei SBC

Die Teams Endpunkte sind der Anrufer für dieses Szenario und der steuernde Endpunkt. Wenn Sie entweder eine Antwort auf provisorische Unterstützung (183) oder eine endgültige Antwort (200OK) erhalten, startet der Teams-Endpunkt Konnektivitätsprüfungen und geht zu "Regulären" Konnektivitätsprüfungen weiter.

Hinweis: Wenn der SBC eine provisorische Antwort (183) sendet, muss der SBC Verbindungsüberprüfungsanforderungen empfangen und potenziell die Umschließungen abschließen können, bevor das 200OK von SBC gesendet wird. Wenn Überprüfungen und/oder Abschüttungen abgeschlossen wurden, bevor 200OK empfangen wurde, werden Überprüfungen und/oder Kandidaten nach 200OK nicht mehr durchgeführt. Der SBC darf ICE-Kandidaten, Kennwort und Ufrag (Benutzernamenfragment) zwischen 183 und 200 nicht ändern.

Um frühe Medien zu unterstützen, beginnt der SBC möglicherweise mit dem Streamen der Medien an den ICE-Peerkandidaten, mit der höchsten Priorität basierend auf den empfangenen Verbindungsüberprüfungen, sogar bevor die Daten durch den Endpunkt Teams werden. Der SBC sollte für jeden Kandidaten Medien Teams, bis die Ausdingung abgeschlossen ist. Sobald ein Kandidat benannt wurde, muss der SBC auf den richtigen Kontext zurückgesetzt werden, um Medienpakete zu senden und zu empfangen.

## <a name="srtp-support-requirements"></a>SRTP-Supportanforderungen

Der SBC muss SRTP-Verschlüsselungschiffre und AES_CM_128_HMAC_SHA1_80 bieten und beantworten in folgendem Format unterstützen:

```console
"inline:" <key||salt> ["|" lifetime]
```

Es folgt ein Beispiel für das Kryptografieattribut im SDP-Angebot von SBC:

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

MKI- und Length-Parameter sind nicht erforderlich.

Weitere Informationen finden Sie unter [RFC 4568, Abschnitt 6.1.](https://tools.ietf.org/html/rfc4568#section-6.1)

## <a name="sdes-support-requirements"></a>Supportanforderungen für SDES

Das Gerät muss SDES im unten beschriebenen Format anbieten können. Microsoft Media Processors bevorzugen immer SDES.

- Bei der Nicht-Medienumgehung werden die Medienprozessoren in SDES konvertiert, auch wenn ein Client nur DTLS unterstützt.

- Bei der Medienumgehung fügt Direct Routing eine MP in den Pfad ein, wenn ein Client nur DTLS ist (zukünftiger Google Chrome-Zustand). Dabei wird der Aufruf von der Medienumgehung in die Nicht-Medienumgehung konvertiert. Zwischen der SBC- und Medienprozessorkomponente von Direct-Routing wird SDES immer verwendet.

Derzeit gibt es keinen Teams, der nur DTLS bietet. Google hat jedoch angekündigt, dass die Unterstützung von SDES zu einem bestimmten Zeitpunkt beendet wird.

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>Format für das Angebot von SBC im Umgehungsmodus 

Das Angebot muss SDES enthalten und kann DTLS (optional) im folgenden Format enthalten:

```console
m=audio 54056 UDP/TLS/RTP/SAVP 0 8 76 77 18 9 101 13
a=rtcp:54056
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:krXco0QRglwErMqtbMs2zSw29tBdmdgXpEYZhQmp|2^31
a=fingerprint:sha-256 AE:24:07:15:5C:B7:45:1A:E4:45:60:C1:1E:68:0E:CC:8D:A6:78:3B:76:65:BB:B0:77:88:07:F8:98:18:62:34
a=setup:actpass
a=rtcp-mux
```

### <a name="format-for-answer-containing-sdes-to-sbc"></a>Format für Antwort mit SDES an SBC

```console
m=audio 54056 RTP/SAVP 111 103 104 9 0 8 description 106 13 110 112 113 126
a=rtcp:54056
a=crypto:2 AES_CM_128_HMAC_SHA1_80 inline:fBc61ikv1kMy0sF85DblNqTzVAbFa7hJQ9GKb6Yj|2^31|1:1
a=crypto:3 AES_CM_128_HMAC_SHA1_80 inline:O1qT9tWbs/NwJVwhfrgF5tCrbNOxnVDqkIqTx4rz|2^31
a=rtcp-mux

```

## <a name="format-for-offer-from-teams-to-sbc"></a>Format für angebote von Teams zu SBC 

### <a name="format-for-sdes-only-offer-to-sbc"></a>Format für nur SDES-Angebote für SBC

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

