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
description: Erfahren Sie, wie Sie mithilfe des Integritätsdashboards die Verbindung zwischen dem Session Border Controller und dem Direct Routing überwachen.
ms.openlocfilehash: cb5e802d904cd2eb364fd480ebcde385e64cf02b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122229"
---
# <a name="health-dashboard-for-direct-routing"></a>Integritätsdashboard für direktes Routing

Mit dem Integritätsdashboard für Direct Routing können Sie die Verbindung zwischen ihrem Session Border Controller (SBC) und der Direct Routing-Schnittstelle überwachen.  Mit dem Integritätsdashboard können Sie Informationen zu Ihrem SBC, dem Telefoniedienst und den Netzwerkparametern zwischen Ihrem SBC und der Direct Routing-Schnittstelle überwachen. Diese Informationen können Ihnen helfen, Probleme zu identifizieren, einschließlich des Grunds für verworfene Anrufe. Der SBC kann z. B. das Senden von Anrufen beenden, wenn ein Zertifikat für den SBC abgelaufen ist oder Netzwerkprobleme auftreten. In den [Administratorrollen erfahren](using-admin-roles.md) Sie, wer Zugriff auf das Integritätsdashboard hat.

Das Integritätsdashboard überwacht zwei Informationsebenen:

- Gesamtzustand der verbundenen SBCs
- Detaillierte Informationen zu den verbundenen SBCs

Sie können das Integritätsdashboard im Microsoft Teams und Skype for Business Admin Center anzeigen.

## <a name="overall-health"></a>Gesamtzustand

Das Integritätsdashboard enthält die folgenden Informationen zum Gesamtzustand der verbundenen SBCs:

 ![Zeigt Statistiken zum Integritätsdashboard an](media/direct-routing-dashboard-stats1.png)

- **Direkte Routingzusammenfassung** : Zeigt die Gesamtanzahl der im System registrierten SBCs an. Registrierung bedeutet, dass der Mandantenadministrator einen SBC mithilfe des Befehls New-CsOnlinePSTNGateway hinzugefügt hat. Wenn der SBC in PowerShell hinzugefügt, aber nie verbunden wurde, wird er im Integritätsdashboard in einem fehlerhaften Status angezeigt.

- **SBC** – Der FQDN des gekoppelten SBC.

- **NER (Network Effectiveness Ratio)** – Das NER misst die Fähigkeit eines Netzwerks, Anrufe zu senden, indem die Anzahl der an einen Empfänger gesendeten Anrufe im Vergleich zur Anzahl der an einen Empfänger übermittelten Anrufe gemessen wird.  

   Der NER misst die Fähigkeit von Netzwerken, Anrufe an das endende Terminal zu führen– ohne Benutzeraktionen, die zu Anrufverweigerungen führen.  Wenn der Empfänger einen Anruf abgelehnt oder den Anruf an die Voicemail gesendet hat, wird der Anruf als erfolgreiche Zustellung gezählt. Dies bedeutet, dass eine Antwortnachricht, ein gebuchtes Signal oder ein Ring ohne Antwort als erfolgreiche Anrufe betrachtet werden.
  
   Angenommen, Direct Routing hat einen Aufruf an den SBC gesendet, und der SBC gibt SIP-Code "504 Server-Time-out - Der Server hat versucht, auf einen anderen Server zu zugreifen, um die Anforderung zu verarbeiten, und hat keine Aufforderung erhalten". Diese Antwort gibt an, dass es ein Problem auf der SBC-Seite gibt, und dadurch wird der NER im Integritätsdashboard für diesen SBC verringert.
  
   Da die von Ihnen getroffene Aktion von der Anzahl der betroffenen Aufrufe abhängig sein kann, zeigt das Integritätsdashboard an, wie viele Aufrufe analysiert wurden, um einen Parameter zu berechnen. Wenn die Anzahl der Anrufe kleiner als 100 ist, ist der NER möglicherweise recht niedrig, ist aber trotzdem normal.

   Die Formel zum Berechnen von NER ist:

   NER = 100 x (Beantwortete Anrufe + Benutzer beschäftigt + Anruf keine Antwort + Terminalannahmen ablehnen)/Gesamtanrufe

- **Durchschnittliche Anrufdauer** – Informationen zur durchschnittlichen Anrufdauer können Ihnen helfen, die Qualität von Anrufen zu überwachen. Die durchschnittliche Dauer eines 1:1-PSTN-Anrufs beträgt vier bis fünf Minuten.  Für jedes Unternehmen kann dieser Durchschnitt jedoch unterschiedlich sein.  Microsoft empfiehlt, einen Basisplan für die durchschnittliche Anrufdauer für Ihr Unternehmen zu erstellen. Wenn dieser Parameter deutlich unter den Basisplan fällt, kann er darauf hinweisen, dass Ihre Benutzer Probleme mit der Anrufqualität oder Zuverlässigkeit haben und früher als üblich hängen. Wenn eine extrem niedrige durchschnittliche Anrufdauer angezeigt wird, z. B. 15 Sekunden, hängen Anrufer möglicherweise auf, weil Ihr Dienst nicht zuverlässig funktioniert.

   Da die von Ihnen getroffene Aktion von der Anzahl der betroffenen Aufrufe abhängig sein kann, zeigt das Integritätsdashboard an, wie viele Aufrufe analysiert wurden, um einen Parameter zu berechnen.

- **TLS-Konnektivitätsstatus** – Die TLS-Konnektivität (Transport Layer Security) zeigt den Status der TLS-Verbindungen zwischen Direct Routing und dem SBC an. Das Integritätsdashboard analysiert außerdem das Ablaufdatum des Zertifikats und warnt, wenn ein Zertifikat innerhalb von 30 Tagen ablaufen soll, damit Administratoren das Zertifikat verlängern können, bevor der Dienst unterbrochen wird.

   Wenn Sie auf die Warnmeldung klicken, wird eine detaillierte Problembeschreibung in einem Popupfenster auf der rechten Seite sowie Empfehlungen zum Beheben des Problems angezeigt.

- **Status der SIP-Optionen** – Standardmäßig sendet der SBC jede Minute Optionsnachrichten. Diese Konfiguration kann für unterschiedliche SBC-Anbieter variieren. Direct Routing warnt, wenn die SIP-Optionen nicht gesendet oder nicht konfiguriert sind. Weitere Informationen zur Überwachung von SIP-Optionen und Bedingungen, unter denen ein SBC als nicht funktionsfähig gekennzeichnet werden kann, finden Sie unter Überwachen und Behandeln [von Problemen mit Direct Routing.](direct-routing-monitor-and-troubleshoot.md)

- **Detaillierter Status** der SIP-Optionen – Das Integritätsdashboard enthält nicht nur ein Problem mit dem Fluss von SIP-Optionen, sondern auch detaillierte Beschreibungen der Fehler. Sie können auf die Beschreibung zugreifen, indem Sie auf die Meldung "Warnung" klicken. In einem Popupfenster auf der rechten Seite wird die detaillierte Fehlerbeschreibung angezeigt.

   Mögliche Werte für Statusmeldungen zu SIP-Optionen sind wie folgt:

    - Aktiv – Der SBC ist aktiv – Der Microsoft Direct Routing-Dienst sieht die Optionen, die in einem normalen Intervall fließen.

    - Warnung, keine SIP-Optionen – Der Session Border Controller ist in der Datenbank vorhanden (der Administrator hat ihn mit dem Befehl New-CsOnlinePSTNGateway erstellt). Sie ist für das Senden von SIP-Optionen konfiguriert, aber der Direct Routing-Dienst hat nie gesehen, dass die SIP-Optionen von diesem SBC zurückkommen.

    - Warnung: SIP-Nachrichten sind nicht konfiguriert – Die Trunküberwachung mithilfe von SIP-Optionen ist nicht aktiviert. Microsoft Calling System verwendet SIP-Optionen und die TLS-Handshakeüberwachung (Transport Layer Security), um den Zustand der verbundenen Session Border Controller (SBCs) auf Anwendungsebene zu erkennen. Sie haben Probleme, wenn dieser Trunk auf Netzwerkebene (per Ping) erreicht werden kann, das Zertifikat aber abgelaufen ist oder der SIP-Stapel nicht funktioniert. Um solche Probleme frühzeitig zu erkennen, empfiehlt Microsoft, das Senden von SIP-Optionen zu aktivieren. Überprüfen Sie die Dokumentation des SBC-Herstellers, um die Senden von SIP-Optionen zu konfigurieren.

- **Kapazität für** gleichzeitige Aufrufe: Sie können den Grenzwert für gleichzeitige Aufrufe angeben, die ein SBC mit dem Befehl New- oder Set-CsOnlinePSTNGateway mit dem Parameter -MaxConcurrentSessions verarbeiten kann. Dieser Parameter berechnet, wie viele Anrufe per Direct Routing mit einem bestimmten SBC gesendet oder empfangen wurden, und vergleicht ihn mit dem Grenzwertsatz. Hinweis: Wenn der SBC auch Anrufe an unterschiedliche PBXs verarbeitet, werden die tatsächlichen gleichzeitigen Anrufe unter dieser Nummer nicht angezeigt.

## <a name="detailed-information-for-each-sbc"></a>Detaillierte Informationen für jeden SBC

Sie können auch die detaillierten Informationen für einen bestimmten SBC anzeigen, wie im folgenden Screenshot gezeigt:

![SBC-Details des Integritätsdashboards](media/direct-routing-dashboard-SBC-detail1.png)

In der Detailansicht werden die folgenden zusätzlichen Parameter angezeigt:

- **TLS-Verbindungsstatus** – Dies ist die gleiche Metrik wie auf der Seite "Gesamtstatus".

- **TLS Connectivity last status** – zeigt die Uhrzeit an, zu der der SBC eine TLS-Verbindung mit dem Direct Routing-Dienst hergestellt hat.

- **Status der SIP-Optionen** – die gleiche Metrik wie auf der Seite "Gesamtstatus".

- **SIP-Optionen zuletzt aktiviert** – Zeitpunkt, zu dem die SIP-Optionen das letzte Mal empfangen wurden.

- **SBC-Status** – Gesamtstatus des SBC, basierend auf allen überwachten Parametern.

- **Gleichzeitiger Anruf**: Zeigt an, wie viele gleichzeitige Anrufe der SBC verarbeitet hat. Diese Informationen sind hilfreich, um die Anzahl der benötigten parallelen Kanäle vorherzusagen und den Trend zu sehen. Sie können die Daten nach Anzahl der Tage und Anrufrichtung (ein-/ausgehend/Alle Datenströme) verschieben.

- **Netzwerkparameter** : Alle Netzwerkparameter werden von der Direct Routing-Schnittstelle bis zum Session Border Controller gemessen. Informationen zu den empfohlenen Werten finden Sie unter Vorbereiten des Netzwerks Ihrer Organisation für [Microsoft Teams,](./prepare-network.md)und sehen Sie sich die empfohlenen Werte von Customer Edge zu Microsoft Edge an.

   - Jitter – Ist das Millisekundenmaß für die Variation der Verzögerungszeit für die Netzwerkweitergabe, die zwischen zwei Endpunkten mithilfe von RTCP (RtP-Steuerelementprotokoll) berechnet wird.

   - Paketverlust – Ist ein Maß für das Paket, das nicht eintrifft; es wird zwischen zwei Endpunkten berechnet.

   - Latenz – (auch als Roundtripzeit bezeichnet) ist die Dauer, die es dauert, bis ein Signal gesendet wird, zuzüglich der Zeit, die es dauert, bis die Bestätigung dieses Signals empfangen wird. Diese Zeitverzögerung besteht aus den Übertragungszeiten zwischen den beiden Punkten eines Signals.

   Sie können die Daten nach Anzahl der Tage und Anrufrichtung (ein-/ausgehend/Alle Datenströme) verschieben.

**Netzwerkeffektivitätsverhältnis** – Dies ist derselbe Parameter, der auf dem Dashboard "Gesamter Integrität" angezeigt wird, aber mit der Option, die Daten nach Zeitreihen oder Anrufrichtung zu segmentieren.