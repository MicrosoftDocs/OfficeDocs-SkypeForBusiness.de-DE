---
title: Übersicht über das Direkte Routing des Telefonsystems
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
f1.keywords:
- NOCSH
description: hHw Direct Routing unterstützt die Medienumgehung mit einem Session Border Controller, der für ICE Lite aktiviert ist.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59ea283069c6fc37590d6329aeac46e40484f8ca
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267760"
---
# <a name="overview"></a>Übersicht

In diesem Artikel wird beschrieben, wie Direct Routing die Medienumgehung mit einem Session Border Controller (SBC) unterstützt, der für ICE Lite aktiviert ist, wie in [RFC 5245](https://tools.ietf.org/html/rfc5245) beschrieben. Dieser Artikel richtet sich an Sprachadministratoren, die für die Konfiguration der Verbindung zwischen dem lokalen SBC und dem SIP-Proxydienst verantwortlich sind.

Dieser Artikel enthält eine Übersicht über die ICE Lite-Szenarien und -Anforderungen für die Interoperabilität. Der Artikel beschreibt die Nachrichtenformate und die erforderlichen Zustandsautomatübergänge, um einen zuverlässigen Anruf- und Medienfluss sicherzustellen.

## <a name="terminology"></a>Terminologie

- First Hello – Die ersten Wörter, die vom Anrufer und dem Angerufenen gesprochen werden. Es ist wichtig, dass alle Anstrengungen unternommen werden, um sicherzustellen, dass die ersten Pakete von den Endpunkten für die meisten Anwendungsfälle zuverlässig übermittelt werden.

- Freihandeingabe – Das Angebot des Anrufers kann an mehrere Endpunkte des Angerufenen übermittelt werden, wenn der Angerufene auf mehreren Geräten verfügbar ist (z. B. kann ein Teams-Benutzer bei Teams für Windows und Teams für Android oder iPhone angemeldet sein).

- Vorläufige Antwort (183) – Die Endpunkte des Angerufenen für eine schnellere Anrufeinrichtung senden eine Antwort mit den Kandidaten und Schlüsseln, die zum Einrichten des Medienflusses erforderlich sind. Dies geschieht in Erwartung, dass der Benutzer den Anruf (200OK) von dieser bestimmten Instanz des Angerufenen möglicherweise entgegen nimmt. Bei der Freihandeingabe sollte der Anrufer bereit sein, mehrere vorläufige Antworten zu erhalten.

- Re-Invite – Angebot mit finalen Kandidaten, die vom ICE-Kontroll-Endpunkt ausgewählt wurden. Dies weist das Attribut a=remote-candidate auf, um alle Racebedingungen vom Behandeln mehrerer Gabeln zu lösen.

- Teams-Endpunkt – Dies kann entweder ein Server (Medienprozessor, Transportrelay) oder der Teams-Client sein.

## <a name="message-format"></a>Nachrichtenformat

Die Teams-Infrastruktur folgt RFC 5245 für ICE-Lite. Dies bedeutet, dass alle STUN-Nachrichten rfc [5389](https://tools.ietf.org/html/rfc5389) entsprechen.

Die SBCs gemäß RFC 5389 müssen alle STUN-Attribute ignorieren, die sie nicht erkennen, und die Nachrichten weiterhin mit den bekannten Attributen verarbeiten. 

Wenn falsch formatierte Pakete empfangen werden, müssen die Pakete verworfen werden, ohne dass sich dies auf die Einrichtung von Mediensitzungen auswirkt.

## <a name="ice-lite-requirements"></a>ICE Lite-Anforderungen

In diesem Abschnitt werden die Anforderungen für ICE Lite kurz erfasst.

### <a name="candidate-gathering"></a>Kandidatensammeln

Der SBC darf nur einen Kandidaten anbieten, der öffentlich erreichbar ist. Derzeit werden nur IPV4-Kandidaten unterstützt.


#### <a name="connectivity-checks"></a>Konnektivitätsprüfungen

Die ICE Lite-Implementierung muss auf alle empfangenen Konnektivitätsprüfungen reagieren. Der ICE Lite-Endpunkt darf keine Verbindungsüberprüfungsanforderungen senden. (Wenn Konnektivitätsprüfungen in Verletzung gesendet werden, reagiert die vollständige Implementierung, was dazu führen kann, dass unerwartete Peer-abgeleitete Kandidaten ermittelt werden und möglicherweise zu Anruffehlern führen.)

#### <a name="nominations"></a>Nominierungen

Der vollständige ICE-Implementierungsendpunkt ist immer der Controlling-Endpunkt und folgt den "regulären" Nominierungen für die Auswahl der endgültigen Kandidaten, die für den Medienfluss verwendet werden sollen. Der ICE Lite-Endpunkt kann die Nominierungen verwenden, um den für Medien zu verwendenden Pfad zu schließen und die Einrichtung von Anrufen abzuschließen.

Hinweis: Bei Freihandeingaben mit Peer-Endpunkten, die 183 vorläufige Antworten senden, muss der SBC bereit sein, auf Prüfungen von mehreren Endpunkten und auch auf Nominierungen von mehreren Endpunkten zu reagieren, wenn die Nominierungen vor 200OK stattfinden. Abhängig von der Konvergenz der ICE-Zustandsmaschine auf dem endgültigen Weg und dem Zeitpunkt der Benutzerantwort können die Nominierungen vor oder nach 200OK erfolgen. Der SBC muss in der Lage sein, beide Fälle zu behandeln.

#### <a name="converging-for-forking"></a>Konvergieren für die Verschmiedung

Wenn das Angebot des SBC mehreren Teams-Endpunkten zugibt, reagieren die Teams-Endpunkte möglicherweise mit einer vorläufigen Antwort und starten Konnektivitätsprüfungen. Der SBC muss darauf vorbereitet sein, Konnektivitätsprüfungen zu empfangen und auf Konnektivitätsprüfungen von mehreren Peer-Endpunkten zu reagieren. Beispielsweise kann der Teams-Benutzer sowohl auf einem Desktop als auch auf einem Mobiltelefon angemeldet sein. Beide Geräte werden über den eingehenden Anruf benachrichtigt und versuchen, die Verbindung mit dem SBC zu überprüfen.

Letztendlich wird nur einer der Endpunkte den Anruf annehmen (200OK). Beim Empfang der 200OK kann der SBC den richtigen Kontext für die Verarbeitung der Medienpakete einrichten.

## <a name="scenarios"></a>Szenarien

###  <a name="inbound-call-from-sbc"></a>Eingehender Anruf vom SBC

Für dieses Szenario gibt es mehrere mögliche Peerendpunkte, die der SBC behandeln muss:

- Serverendpunkte reagieren in der Regel direkt mit 200OK. Hierbei handelt es sich um vollständige ICE-Endpunkte, die in der Regel in Szenarien mit Voicemail, Anrufwarteschleife und automatischer Telefonzentrale involviert sind.

- Clientendpunkte können mehrere vorläufige Antworten mit unterschiedlichen From/To-Tags (183) senden, gefolgt von einer 200OK vom Endpunkt, der den Anruf anhört. Dies sind vollständige ICE-Endpunkte, die in der Regel Endbenutzerclients darstellen.

- Andere SBC-Endpunkte. Hierbei handelt es sich um ICE Lite-Endpunkte, die in der Regel in das Szenario des gleichzeitigen Klingelns von Clientendpunkten und einer anderen(n) Telefonnummer(n) einbezogen werden.

Der SBC muss auf alle gültigen Verbindungsüberprüfungsanforderungen reagieren, die von den vollständigen ICE-Endpunkten empfangen wurden. Gemäß RFC werden die vollständigen ICE-Endpunkte zu Steuernden Endpunkten. Die Teams-Endpunkte (Client/Server) führen "reguläre" Nominierungen durch, um Konnektivitätsprüfungen durchzuführen. Die endgültige 200Ok kann entweder von einem Endpunkt stammen, der frühe Medien gesendet hat, oder von einem anderen Endpunkt. Beim Empfang der 200Ok muss der SBC den richtigen Kontext für den Medienfluss einrichten. 

###  <a name="early-media"></a>Frühe Medien

Wenn ein frühzeitiger Medienfluss vorliegt, muss der SBC an den ersten Endpunkt verriegelungen, der das Streamen von Medien startet. Der Medienfluss kann beginnen, bevor Kandidaten nominiert werden. Der SBC sollte während dieser Phase unterstützung für das Senden von DTMF haben, um IVR/Voicemail-Szenarien zu ermöglichen. Der SBC sollte den Pfad mit der höchsten Priorität verwenden, auf dem er Prüfungen erhalten hat, wenn Nominierungen nicht abgeschlossen wurden.

### <a name="outbound-call-to-sbc"></a>Ausgehender Anruf an SBC

Die Teams-Endpunkte sind der Aufrufer für dieses Szenario und werden der steuernde Endpunkt sein. Nach erhalt einer vorläufigen Antwort (183) oder einer endgültigen Antwort(200OK) startet der Teams-Endpunkt Konnektivitätsprüfungen und fährt mit "regulären" Nominierungen fort, um die Konnektivitätsprüfungen abzuschließen.

Hinweis: Wenn der SBC eine vorläufige Antwort sendet (183), muss der SBC bereit sein, Verbindungsüberprüfungsanforderungen zu erhalten und die Nominierungen möglicherweise abzuschließen, bevor der SBC die 200OK sendet. Wenn Prüfungen und/oder Nominierungen abgeschlossen sind, bevor die 200OK eingeht, werden Nachprüfungen und/oder Nominierungen nicht erneut durchgeführt, nachdem 200OK eingetroffen ist. Der SBC darf zwischen 183 und 200 keine ICE-Kandidaten, kein Kennwort und keine Ufrag (Benutzernamenfragment) ändern.

Um frühe Medien zu unterstützen, kann der SBC mit dem Streaming der Medien an den Peer ICE-Kandidaten beginnen, mit der höchsten Priorität basierend auf den empfangenen Konnektivitätsprüfungen, noch bevor nominierungen vom Teams-Endpunkt abgeschlossen werden. Der SBC sollte Medien von Teams für jeden Kandidaten erwarten, bis die Nominierungen abgeschlossen sind. Nachdem ein Kandidat nominiert wurde, muss der SBC auf den richtigen Kontext zurückgesetzt werden, um Medienpakete zu senden und zu empfangen.

## <a name="srtp-support-requirements"></a>SRTP-Supportanforderungen

Der SBC muss die SRTP-Verschlüsselungschiffre AES_CM_128_HMAC_SHA1_80 für Angebot und Antwort im folgenden Format unterstützen:

```console
"inline:" <key||salt> ["|" lifetime]
```

Es folgt ein Beispiel für das Kryptoattribut im SDP-Angebot des SBC:

```console
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:V/Lr6Lsvhad/crSB9kCQ28jrYDxR2Yfk5bXryH5V|2^31
```

MKI- und Length-Parameter sind nicht erforderlich.

Weitere Informationen finden Sie [unter RFC 4568, Abschnitt 6.1](https://tools.ietf.org/html/rfc4568#section-6.1).

## <a name="sdes-support-requirements"></a>SDES-Supportanforderungen

Das Gerät muss SDES im folgenden Format anbieten können. Microsoft-Medienprozessoren bevorzugen immer SDES.

- Bei der Nicht-Medienumgehung werden die Medienprozessoren auch dann in SDES konvertiert, wenn ein Client nur DTLS unterstützt.

- Bei der Medienumgehung fügt Direct Routing, wenn ein Client nur DTLS ist (zukünftiger Google Chrome-Zustand), einen MP in den Pfad ein, wodurch der Anruf von der Medienumgehung in eine Nicht-Medienumgehung konvertiert wird. Zwischen der SBC- und der Medienprozessorkomponente von Direct Routing wird SDES immer verwendet.

Derzeit gibt es keinen Teams-Client, der nur DTLS anbietet. Google hat jedoch angekündigt, dass sie zu einem bestimmten Zeitpunkt die Unterstützung von SDES beenden werden.

## <a name="format-for-offer-from-sbc-in-bypass-mode"></a>Format für das Angebot von SBC im Umgehungsmodus 

Das Angebot muss SDES enthalten und kann DTLS optional im folgenden Format enthalten:

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

## <a name="format-for-offer-from-teams-to-sbc"></a>Format für Das Angebot von Teams bis SBC 

### <a name="format-for-sdes-only-offer-to-sbc"></a>Format für SDES nur für SBC anbieten

```console
m=audio 52884 RTP/SAVP 111 103 104 9 0 8 106 13 110 112 113 126
a=crypto:0 AES_CM_128_HMAC_SHA1_32 inline:Hr4D2cgUu9+Uza5Igz/JkVx59DAxDbaxJg862ibQ|2^31
a=crypto:1 AES_CM_128_HMAC_SHA1_80 inline:JPEaIxHegfuv53ykBPZk8hV0GO8kTiiqRMfHimEE|2^31
a=rtcp:52884
a=rtcp-mux
```

