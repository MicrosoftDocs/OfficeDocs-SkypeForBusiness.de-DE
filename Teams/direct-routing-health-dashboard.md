---
title: Status-Dashboard für direktes Routing
ms.reviewer: nmurav
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Erfahren Sie, wie Sie mithilfe des Integritäts Dashboards die Verbindung zwischen dem Sitzungs Grenz Controller und dem direkten Routing überwachen.
ms.openlocfilehash: 352b23f320a4e2adaa9819952a6e489791294630
ms.sourcegitcommit: 1a768e470a9509139eeb24034def12630acb7914
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/13/2019
ms.locfileid: "34920268"
---
# <a name="health-dashboard-for-direct-routing"></a>Status-Dashboard für direktes Routing

Mit dem Integritäts-Dashboard für das direkte Routing können Sie die Verbindung zwischen dem SBC (Session Border Controller) und der direkten Routingschnittstelle überwachen.  Mit dem Status-Dashboard können Sie Informationen zu Ihrem SBC, dem Telefoniedienst und den Netzwerkparametern zwischen Ihrem SBC und der direkten Routing Schnittstelle überwachen. Diese Informationen können Ihnen helfen, Probleme zu erkennen, einschließlich des Grunds für gelöschte Anrufe. Beispielsweise kann der SBC das Senden von Anrufen beenden, wenn ein Zertifikat auf dem SBC abgelaufen ist oder wenn es Netzwerkprobleme gibt.  

Das Status-Dashboard überwacht zwei Informationsebenen:

- Gesamtzustand des verbundenen SBCS
- Detaillierte Informationen zu den verbundenen SBCS

Sie können das Status-Dashboard in Microsoft Teams und Skype for Business Admin Center anzeigen.


## <a name="overall-health"></a>Allgemeiner Status

Das Integritäts Dashboard bietet die folgenden Informationen im Zusammenhang mit dem allgemeinen Zustand des verbundenen SBCS:

 ![Zeigt Statistiken zu Health Dashboards](media/direct-routing-dashboard-stats1.png)

- **Direkte Routing Zusammenfassung** – zeigt die Gesamtzahl der im System registrierten SBCS an. Registrierung bedeutet, dass der mandantenadministrator einen SBC mithilfe des Befehls New-CsOnlinePSTNGateway hinzugefügt hat. Wenn der SBC in PowerShell hinzugefügt, aber nie verbunden wurde, wird er im Integritäts Dashboard in einem fehlerhaften Status angezeigt.

- **SBC** – der FQDN des gekoppelten SBC.

- **Netzwerk-Effektivitäts-Verhältnis (ner)** – das ner misst die Fähigkeit eines Netzwerks, Anrufe zu übermitteln, indem es die Anzahl der Anrufe im Vergleich zur Anzahl der an einen Empfänger zugestellten Anrufe misst.  

   Das ner misst die Möglichkeit von Netzwerken, Anrufe an das Ferne Endgerät zu übertragen – ausgenommen Benutzeraktionen, die zu Anruf Ablehnungen führen.  Wenn der Empfänger einen Anruf abgelehnt oder den Anruf an die Voicemail gesendet hat, wird der Anruf als erfolgreiche Zustellung gezählt. Das bedeutet, dass eine Antwortnachricht, ein Besetztzeichen oder ein Ring ohne Antwort alle als erfolgreiche Anrufe angesehen werden. 
  
   Angenommen, das direkte Routing hat einen Anruf an den SBC gesendet, und der SBC gibt den SIP-Code "504-Servertimeout zurück – der Server hat versucht, auf einen anderen Server zuzugreifen, um die Anforderung zu verarbeiten, und hat keine Antwort auf eine Aufforderung erhalten". Diese Antwort zeigt an, dass ein Problem auf der SBC-Seite vorliegt, und dadurch wird die ner auf dem Integritäts Dashboard für diesen SBC verringert. 
  
   Da die von Ihnen getroffene Aktion möglicherweise von der Anzahl der betroffenen Anrufe abhängt, zeigt Health Dashboard an, wie viele Aufrufe analysiert wurden, um einen Parameter zu berechnen. Wenn die Anzahl der Anrufe kleiner als 100 ist, ist die ner möglicherweise relativ gering, aber dennoch normal. 

   Die für calcuate ner verwendete Formel lautet:

   NER = beantwortete Anrufe + Benutzer beschäftigt + Ring keine Antwort + Terminal Reject Anfälle x 100

 
- **Durchschnittliche Anrufdauer** – Informationen zur durchschnittlichen Anrufdauer können Ihnen dabei helfen, die Qualität von Anrufen zu überwachen. Die durchschnittliche Dauer eines 1:1-PSTN-Anrufs beträgt vier bis fünf Minuten.  Für jedes Unternehmen kann dieser Mittelwert jedoch unterschiedlich sein.  Microsoft empfiehlt die Einrichtung eines Basisplans für die durchschnittliche Anrufdauer für Ihr Unternehmen. Wenn dieser Parameter deutlich unter dem Basisplan liegt, kann dies darauf hindeuten, dass Ihre Benutzer Probleme mit der Anrufqualität oder Zuverlässigkeit haben und früher als üblich auflegen. Wenn Sie eine extrem niedrige Durchschnittliche Anrufdauer sehen, beispielsweise 15 Sekunden, hängen Anrufer möglicherweise auf, weil Ihr Dienst nicht zuverlässig abläuft. 

   Da die von Ihnen getroffene Aktion möglicherweise von der Anzahl der betroffenen Anrufe abhängt, zeigt Health Dashboard an, wie viele Aufrufe analysiert wurden, um einen Parameter zu berechnen.

- **TLS-Verbindungsstatus** – TLS (Transport Layer Security)-Konnektivität zeigt den Status der TLS-Verbindungen zwischen direktem Routing und SBC an. Das Integritäts Dashboard analysiert auch das Ablaufdatum des Zertifikats und warnt, wenn ein Zertifikat so eingestellt ist, dass es innerhalb von 30 Tagen abläuft, damit Administratoren das Zertifikat erneuern können, bevor der Dienst gestört wird.

   Wenn Sie auf die Warnmeldung klicken, wird eine detaillierte Problembeschreibung in einem Popupfenster auf der rechten Seite sowie Empfehlungen zur Behebung des Problems angezeigt.

- **Status der SIP-Optionen** – Standardmäßig sendet der SBC jede Minute Options Nachrichten. Diese Konfiguration kann für verschiedene SBC-Anbieter variieren. Direktes Routing warnt, wenn die SIP-Optionen nicht gesendet wurden oder nicht konfiguriert sind. Weitere Informationen zur Überwachung der SIP-Optionen und zu den Bedingungen, wenn ein SBC als nicht funktionsfähig gekennzeichnet werden kann, finden Sie unter [überwachen und Problembehandlung des direkten Routings](direct-routing-monitor-and-troubleshoot.md).

- **Detaillierter Status der SIP-Optionen** – zusätzlich zu der Anzeige, dass ein Problem mit dem SIP-Options Fluss vorliegt, enthält das Integritäts Dashboard auch ausführliche Beschreibungen der Fehler. Sie können auf die Beschreibung zugreifen, indem Sie auf die Meldung "Warnung" klicken. In einem Popupfenster auf der rechten Seite wird die detaillierte Fehlerbeschreibung angezeigt.

   Mögliche Werte für Statusmeldungen für SIP-Optionen lauten wie folgt:

    - Aktiv – der SBC ist aktiv – der Microsoft Direct-Routing Dienst sieht die Optionen, die in einem regelmäßigen Intervall fließen.

    - Warnung, keine SIP-Optionen – der Session Border Controller ist in der Datenbank vorhanden (Ihr Administrator hat ihn mit dem Befehl New-CsOnlinePSTNGateway erstellt). Sie ist so konfiguriert, dass SIP-Optionen gesendet werden, aber der Direct Routing-Dienst hat nie die SIP-Optionen gesehen, die von diesem SBC zurückkommen.

    - Warnung: SIP-Nachrichten werden nicht konfiguriert – trunk-Überwachung über SIP-Optionen ist nicht aktiviert. Das Microsoft-Anruf System verwendet SIP-Optionen und TLS-Handshake-Überwachung (Transport Layer Security), um die Integrität der verbundenen Session Border Controller (SBCS) auf Anwendungsebene zu erkennen. Sie haben Probleme, wenn dieser trunk auf Netzwerkebene (per Ping) erreicht werden kann, das Zertifikat aber abgelaufen ist oder der SIP-Stack nicht funktioniert. Um solche Probleme frühzeitig zu erkennen, empfiehlt Microsoft die Aktivierung des Sendens von SIP-Optionen. Überprüfen Sie Ihre SBC-Herstellerdokumentation, um das Senden von SIP-Optionen zu konfigurieren. 

- **Kapazität für gleichzeitige Anrufe** -Sie können die Grenze für gleichzeitige Anrufe angeben, die ein SBC behandeln kann, indem Sie den Befehl New-oder CsOnlinePSTNGateway mit dem-MaxConcurrentSessions-Parameter verwenden. Dieser Parameter berechnet, wie viele Anrufe durch direkte Weiterleitung mit einem bestimmten SBC gesendet oder empfangen wurden, und vergleicht diese mit dem festgelegten Grenzwert. Hinweis: Wenn der SBC auch Anrufe an verschiedene PBX-Anlagen abwickelt, werden bei dieser Nummer nicht die tatsächlichen gleichzeitigen Anrufe angezeigt.


## <a name="detailed-information-for-each-sbc"></a>Detaillierte Informationen zu jedem SBC

Sie können auch die detaillierten Informationen zu einem bestimmten SBC anzeigen, wie im folgenden Screenshot dargestellt:

![Informationen zum Status-Dashboard SBC](media/direct-routing-dashboard-SBC-detail1.png)


In der Detailansicht werden die folgenden zusätzlichen Parameter angezeigt:

- **TLS-Verbindungsstatus** – Dies ist dieselbe Metrik wie auf der Seite "allgemeine Integrität";

- **Letzter Status der TLS-Konnektivität** – zeigt die Zeit an, zu der der SBC eine TLS-Verbindung mit dem Direct Routing-Dienst hergestellt hat.

- **Status der SIP-Optionen** – dieselbe Metrik wie auf der Seite "allgemeine Integrität".

- **SIP-Optionen zuletzt überprüft** – Zeitpunkt, zu dem die SIP-Optionen beim letzten Mal empfangen wurden.

- **SBC-Status** – Gesamtstatus des SBC, basierend auf allen überwachten Parametern.

- **Gleichzeitiger Anruf**– zeigt an, wie viele gleichzeitige Anrufe der SBC verarbeitet hat. Diese Informationen sind hilfreich, um die Anzahl der gleichzeitig benötigten Kanäle vorherzusagen und den Trend zu sehen. Sie können die Daten nach Anzahl der Tage und in der Anrufrichtung (eingehend/ausgehend/alle Streams) verschieben.

- **Netzwerkparameter** – alle Netzwerkparameter werden von der direkten Routing Schnittstelle zum Session Border Controller gemessen. Informationen zu den empfohlenen Werten finden Sie unter [Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/prepare-network)und untersuchen der empfohlenen Werte für den Kunden Rand zu Microsoft Edge.

   - Jitter – ist das Millisekunden-Maß der Variation in der Verzögerungszeit für die Netzwerk Propagierung, die zwischen zwei Endpunkten mithilfe von RTCP (dem RTP-steuerelementprotokoll) berechnet wird.

   - Paketverlust – ist ein Maß für ein Paket, das nicht ankommt; Sie wird zwischen zwei Endpunkten berechnet.

   - Latancy-(auch als "Roundtrip-Zeit" bezeichnet) ist die Zeitdauer, die für das Senden eines Signals benötigt wird, sowie die Zeitdauer, die für die Empfangsbestätigung des Signals benötigt wird. Diese Zeitverzögerung besteht aus den Ausbreitungs Zeiten zwischen den beiden Punkten eines Signals.

   Sie können die Daten nach Anzahl der Tage und in der Anrufrichtung (eingehend/ausgehend/alle Streams) verschieben.

**Netzwerk-Effektivitäts Verhältnis** – Dies ist derselbe Parameter, der im allgemeinen Status-Dashboard angezeigt wird, jedoch mit der Option, Daten nach Zeitreihen oder in der Anrufrichtung zu segmentieren.




