---
title: Integritätsdashboard für direktes Routing
ms.reviewer: nmurav
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Sie mithilfe des Integritätsdashboards die Verbindung zwischen dem Session Border Controller und dem direkten Routing überwachen.
ms.openlocfilehash: cb5e802d904cd2eb364fd480ebcde385e64cf02b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122229"
---
# <a name="health-dashboard-for-direct-routing"></a>Integritätsdashboard für direktes Routing

Mit dem Integritätsdashboard für Direct-Routing können Sie die Verbindung zwischen Ihrem Session Border Controller (SBC) und der Direct Routing-Schnittstelle überwachen.  Mit Health Dashboard können Sie Informationen über Ihren SBC, den Telefoniedienst und die Netzwerkparameter zwischen Ihrem SBC und der Direct Routing-Schnittstelle überwachen. Diese Informationen können Ihnen dabei helfen, Probleme zu erkennen, einschließlich des Grunds für verworfene Anrufe. Beispielsweise kann der SBC das Senden von Aufrufen beenden, wenn ein Zertifikat auf dem SBC abgelaufen ist oder Netzwerkprobleme auftreten. Sehen Sie sich [die Administratorrollen an,](using-admin-roles.md) um zu erfahren, wer Zugriff auf das Integritätsdashboard hat.

Das Integritätsdashboard überwacht zwei Informationsebenen:

- Gesamtzustand der verbundenen SBCs
- Detaillierte Informationen zu den verbundenen SBCs

Sie können das Integritätsdashboard im Microsoft Teams Skype for Business Admin Center anzeigen.

## <a name="overall-health"></a>Gesamtzustand

Das Integritätsdashboard stellt die folgenden Informationen zum Gesamtzustand der verbundenen SBCs zur Verfügung:

 ![Zeigt Statistiken zum Integritätsdashboard an](media/direct-routing-dashboard-stats1.png)

- **Direct Routing summary** ( Direkte Routingzusammenfassung) – Zeigt die Gesamtzahl der SBCs an, die im System registriert sind. Registration means that the tenant administrator added an SBC by using the New-CsOnlinePSTNGateway command. Wenn der SBC in PowerShell hinzugefügt, aber nie verbunden wurde, zeigt das Integritätsdashboard einen fehlerhaften Status an.

- **SBC** – Der FQDN des gekoppelten SBC.

- **Netzwerkeffektverhältnis (Network Effectiveness Ratio, NER)** – Der NER misst die Fähigkeit eines Netzwerks, Anrufe zu liefern, indem die Anzahl der gesendeten Anrufe im Vergleich zur Anzahl der anrufe gemessen wird, die an einen Empfänger übermittelt wurden.  

   Der NER misst die Fähigkeit von Netzwerken, Anrufe an das Far-End-Terminal zu liefern– ohne Benutzeraktionen, was dazu führt, dass Anrufe abgelehnt werden.  Wenn der Empfänger einen Anruf abgelehnt oder den Anruf an die Voicemail gesendet hat, wird der Anruf als erfolgreiche Zustellung gezählt. Das bedeutet, dass eine Antwortnachricht, ein Beschäftigt-Signal oder ein Klingeln ohne Antwort als erfolgreiche Anrufe angesehen wird.
  
   Nehmen wir beispielsweise an, dass Direct Routing einen Aufruf an den SBC gesendet hat und der SIP-Code "504 Server Time-out - The server attempted to access another server in attempt to process the request and did not receive a prompt response" zurückgibt. Diese Antwort gibt an, dass es auf SBC-Seite ein Problem gibt, und dadurch wird der NER im Integritätsdashboard für diese SBC verringert.
  
   Da die Aktion, die Sie unternehmen, von der Anzahl betroffener Aufrufe abhängig sein kann, zeigt das Integritätsdashboard an, wie viele Aufrufe analysiert wurden, um einen Parameter zu berechnen. Wenn die Anzahl der Anrufe unter 100 liegt, ist der NER möglicherweise recht niedrig, ist aber trotzdem normal.

   Zum Berechnen von NER wird die formel:

   NER = 100 x (Beantwortete Anrufe + Benutzer beschäftigt + Keine Antwort anrufen + Terminalannahmen ablehnen)/Gesamtanrufe

- **Durchschnittliche Anrufdauer** – Informationen zur durchschnittlichen Anrufdauer können Ihnen helfen, die Qualität von Anrufen zu überwachen. Die durchschnittliche Dauer eines 1:1-PSTN-Anrufs beträgt vier bis fünf Minuten.  Für jedes Unternehmen kann dieser Durchschnitt jedoch unterschiedlich sein.  Microsoft empfiehlt, einen Basisplan für die durchschnittliche Anrufdauer für Ihr Unternehmen zu erstellen. Wenn dieser Parameter deutlich unter die Basislinie fällt, kann dies darauf hindeten, dass Ihre Benutzer Probleme mit der Anrufqualität oder Zuverlässigkeit haben und früher als gewohnt hängen. Wenn Sie eine extrem geringe durchschnittliche Anrufdauer sehen, z. B. 15 Sekunden, werden Anrufer möglicherweise hängen, weil Ihr Dienst nicht zuverlässig arbeitet.

   Da die Aktion, die Sie unternehmen, von der Anzahl betroffener Aufrufe abhängig sein kann, zeigt das Integritätsdashboard an, wie viele Aufrufe analysiert wurden, um einen Parameter zu berechnen.

- **TLS-Verbindungsstatus** – TLS-Konnektivität (Transport Layer Security) zeigt den Status der TLS-Verbindungen zwischen Direct-Routing und SBC an. Das Integritätsdashboard analysiert außerdem das Ablaufdatum des Zertifikats und warnt, wenn für ein Zertifikat festgelegt ist, dass es innerhalb von 30 Tagen abläuft, damit Administratoren das Zertifikat verlängern können, bevor der Dienst unterbrochen wird.

   Wenn Sie auf die Warnmeldung klicken, wird auf der rechten Seite in einem Popupfenster eine detaillierte Problembeschreibung und Empfehlungen zum Beheben des Problems angezeigt.

- **SIP-Optionsstatus** – Standardmäßig sendet der SBC jede Minute Optionsnachrichten. Diese Konfiguration kann für verschiedene SBC-Hersteller variieren. Direct Routing warnt Sie, wenn die SIP-Optionen nicht gesendet oder nicht konfiguriert wurden. Weitere Informationen zur Überwachung von SIP-Optionen und zu Bedingungen, unter denen ein SBC als nicht funktionsfähig gekennzeichnet werden kann, finden Sie unter Überwachen und Problembehandlung bei [Direct-Routing.](direct-routing-monitor-and-troubleshoot.md)

- **Detaillierter SIP-Optionsstatus** – Neben dem Anzeigen eines Problems mit dem SIP-Optionsfluss bietet das Health Dashboard auch detaillierte Beschreibungen der Fehler. Sie können auf die Beschreibung zugreifen, indem Sie auf die Meldung "Warnung" klicken. In einem Popupfenster auf der rechten Seite wird die detaillierte Fehlerbeschreibung angezeigt.

   Mögliche Werte für die Statusmeldungen der SIP-Optionen sind wie folgt:

    - Aktiv – Der SBC ist aktiv – Der Microsoft Direct-Routingdienst sieht die Optionen, die in regelmäßigen Abständen aktiv sind.

    - Warnung, keine SIP-Optionen – Der Session Border Controller ist in der Datenbank vorhanden (der Administrator hat ihn mit dem Befehl New-CsOnlinePSTNGateway erstellt). Es ist so konfiguriert, dass SIP-Optionen gesendet werden, aber beim Direct-Routing-Dienst wurden die SIP-Optionen aus diesem SBC nicht angezeigt.

    - Warnung: SIP-Nachrichten sind nicht konfiguriert – die Trunküberwachung mithilfe von SIP-Optionen ist nicht aktiviert. Microsoft Calling System verwendet SIP-Optionen und TLS-Handshakeüberwachung (Transport Layer Security), um den Zustand der verbundenen Session Border Controller (SBCs) auf Anwendungsebene zu ermitteln. Es gibt Probleme, wenn dieser Trunk auf Netzwerkebene (per Ping) erreicht werden kann, das Zertifikat aber abgelaufen ist oder der SIP-Stapel nicht mehr funktioniert. Microsoft empfiehlt, die SIP-Optionen zu aktivieren, damit solche Probleme frühzeitig identifiziert werden können. Lesen Sie die Dokumentation des SBC-Herstellers, um die Sip-Optionen für das Senden zu konfigurieren.

- **Kapazität gleichzeitiger** Aufrufe – Sie können das Limit von gleichzeitigen Aufrufen angeben, die ein SBC verarbeiten kann, indem Sie den Befehl New- oder Set-CsOnlinePSTNGateway mit dem Parameter -MaxConcurrentSessions verwenden. Dieser Parameter berechnet, wie viele Anrufe über Direct-Routing über einen bestimmten SBC gesendet oder empfangen wurden, und vergleicht ihn mit dem festgelegten Grenzwert. Hinweis: Wenn der SBC auch Anrufe an verschiedene PBXs verarbeitet, werden für diese Nummer nicht die tatsächlichen gleichzeitigen Anrufe angezeigt.

## <a name="detailed-information-for-each-sbc"></a>Detaillierte Informationen zu den einzelnen SBC-Daten

Sie können auch die detaillierten Informationen für einen bestimmten SBC anzeigen, wie im folgenden Screenshot dargestellt:

![SBC-Details des Health Dashboards](media/direct-routing-dashboard-SBC-detail1.png)

In der Detailansicht werden die folgenden zusätzlichen Parameter angezeigt:

- **TLS Connectivity-Status** : Dies ist dieselbe Metrik wie auf der Seite "Overall Health".

- **TLS Connectivity-letzter Status** – Zeigt die Uhrzeit an, zu der der SBC eine TLS-Verbindung mit dem Direct-Routingdienst hergestellt hat.

- **Status der SIP-Optionen** – die gleiche Metrik wie auf der Seite "Overall Health".

- **SIP-Optionen zuletzt überprüft:** Zeitpunkt, zu dem die SIP-Optionen das letzte Mal empfangen wurden.

- **SBC-Status** – Gesamtstatus der SBC, basierend auf allen überwachten Parametern.

- **Gleichzeitiger Aufruf:** Zeigt an, wie viele gleichzeitige Aufrufe der SBC verarbeitet wurden. Diese Informationen sind hilfreich, um die Anzahl der benötigten simultanen Kanäle vorherzusagen und den Trend zu erkennen. Sie können die Daten nach der Anzahl der Tage und der Anrufrichtung (ein-/ausgehend/Alle-Datenströme) ziehen.

- **Netzwerkparameter** – Alle Netzwerkparameter werden von der Direct-Routing-Schnittstelle zum Session Border Controller gemessen. Informationen zu den empfohlenen Werten finden Sie unter Vorbereiten des Unternehmensnetzwerks für [Microsoft Teams](./prepare-network.md)und unter Kunden-Edge finden Sie Informationen Microsoft Edge empfohlenen Werte.

   - Jitter – Ist das Maß für die Variation der Verzögerungszeit bei der Netzwerkverteilung in Millisekunden, die mithilfe von RTCP (The RTP Control Protocol) zwischen zwei Endpunkten berechnet wird.

   - Packet Loss – Ist ein Maß für das Paket, das nicht ankommt; wird zwischen zwei Endpunkten berechnet.

   - Latenz (auch als Roundtripzeit bezeichnet) ist die Dauer, die es dauert, bis ein Signal gesendet wird, zuzüglich der Zeit, die es dauert, bis die Bestätigung des Signals empfangen wird. Diese Zeitverzögerung besteht aus den Weitergabezeiten zwischen den beiden Punkten eines Signals.

   Sie können die Daten nach der Anzahl der Tage und der Anrufrichtung (ein-/ausgehend/Alle-Datenströme) ziehen.

**Verhältnis für Netzwerkeffektivität:** Dies ist derselbe Parameter, der im Dashboard Gesamtzustand angezeigt wird, jedoch mit der Option, die Daten nach Zeitreihen oder Anrufrichtung zu segmentieren.