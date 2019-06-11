---
title: 'Lync Server 2013: Überwachen der lync Server-Leistung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring Lync Server 2013 performance
ms:assetid: 2acfd720-6120-4816-a2d4-30476bd5cd0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720910(v=OCS.15)
ms:contentKeyID: 63969592
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9610dddfa9748b7d28dfe040a36214f3f969826
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-lync-server-2013-performance"></a>Überwachen der lync Server 2013-Leistung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-05-15_

Die Leistung von lync Server 2013 ist von verschiedenen Faktoren wie Benutzerprofilen, Systemarchitektur, Software, Hardwarekomponenten, Drittanbieter-Integrationspunkten wie Gateways und Telefonanlagen, Netzwerkkonnektivität und-Leistung, Windows Konfiguration und Leistung des Active Directory-Diensts zusätzlich zur Funktionalität des Windows-Betriebssystems.

Im Mittelpunkt der Leistung einer lync Server 2013-Bereitstellung steht die Server Software und-Hardware, auf der Sie implementiert ist. Beispielsweise muss ein Front-End-Server über genügend Hardwareressourcen verfügen, um die erwartete (kurzfristige) Benutzerauslastung bewältigen zu können. Wenn ein jeweiliger Front-End-Server für die Bereitstellung von Diensten für 10000-Benutzer erforderlich ist, muss ein ausreichend konfigurierter Server den erwarteten Ladeanforderungen genügen, um letztendlich die bestmögliche Benutzererfahrung zu gewährleisten.

Das Überwachen der Serverleistung ist daher äußerst wichtig, um zu ermitteln, ob die implementierte Serverinfrastruktur über geeignete Hardwareressourcen für die täglichen Spitzenlastanforderungen verfügt. Die Überwachung der Serverleistung hilft, Systemengpässe zu erkennen, die es Administratoren ermöglichen, korrigierende Aktionen anzuwenden, bevor die Benutzererfahrung beeinträchtigt wird. Die Leistungsdaten sollten für die langfristige Kapazitätsplanung verwendet werden.

Während detaillierte Informationen zu allen zu beobachtenden Leistungsobjekten und Leistungsindikatoren beim Überwachen von [lync Server 2013 mit System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)verknüpft sind, können einige Leistungsindikatoren, denen Sie folgen sollten, Administratoren eine Schnellansicht zur Verfügung stellen. der Systemleistung:

  - Um die Gesamtsystem Integrität des Front-End-Servers nachvollziehen zu können, ist es ein guter\\Ausgangspunkt, Prozessor% Prozessorzeit zu überprüfen. Der Wert sollte immer unter 80 Prozent liegen.

  - Überwachen Sie die folgenden Leistungsindikatoren, um die Leistung der vom Front-End-Pool verwendeten SQL Server-Datenbanksoftware-Instanz für die Back-End-Datenbank zu verfolgen:
    
    LC: USrv – 00 – DBStore\\USrv – 002 – Warteschlangen Latenz (MS)
    
    LC: USrv – 00 – DBStore\\USrv – 0 04 – Latenz Wartezeit (MS)
    
    Der fehlerfreie Server im stationären Zustand \<sollte 100 MS-Latenzwerte anzeigen. Der Drosselungsmechanismus wird aktiviert, wenn die Wartezeit 12 Sekunden erreicht, was bedeutet, dass der Front-End-Server die Drosselung von Anforderungen an das Back-End startet. Dies bewirkt, dass Clients mit dem Empfang einer zu stark ausgelasteten 503-Server-Fehlermeldung beginnen.

  - Wenn Sie die Verarbeitungszeit auf dem Front-End-Server nachverfolgen möchten, überwachen Sie den folgenden Indikator:
    
    LC: SIP-07-Load Management\\SIP-000-durchschnittliche Aufbewahrungszeit für eingehende Nachrichten
    
    Hierbei handelt es sich um einen weiteren Drosselungsmechanismus auf den Front-End-Servern, der ab diesem Zeitpunkt gestartet wird, wenn die Verarbeitungszeit im Front-End-Bereich höher ist. Wenn die durchschnittliche Verarbeitungszeit mehr als sechs Sekunden beträgt, wechselt der Server in den Drosselungs Modus und ermöglicht nur eine ausstehende Transaktion pro Clientverbindung.

  - Zum Nachverfolgen von Speicherproblemen am SQL-Back-End-Server überwachen Sie den folgenden Indikator:
    
    Lebenserwartung der SQL\\Server-Puffer-Manager-Seite
    
    Ein niedriger Wert unter 3600 Sekunden (zusammen mit den Schreibvorgängen für höhere Latenzen/Sek. und Prüfpunkt-Seiten/Sek.) zeigt den arbeitsspeicherdruck an.

<div>

## <a name="additional-counters-to-view"></a>Weitere zu anzeigende Leistungsindikatoren

Es gibt mehrere wichtige Indikatoren, die gute Indikatoren für den allgemeinen Zustand vom Front-End-Server sind. Hierbei handelt es sich nicht um eine umfassende Liste, die nicht dazu dient, die Ursache zu identifizieren. Mithilfe dieser Leistungsindikatoren können Sie die Serverintegrität schnell überprüfen. Wir empfehlen, diese Leistungsindikatoren auf jedem Server im Pool zu überprüfen. Es ist wichtig zu verstehen, was diese Leistungsindikatorwerte sind, wenn Ihr Serverfehler frei ist. Ein Basisplan ist erforderlich, um zu verstehen, was sich geändert hat, wenn die Benutzeroberfläche beeinträchtigt wird.

Der Front-End-Server kann auf Probleme hindeuten, die durch Engpässe an anderen Stellen im System verursacht werden können. Dies bedeutet, dass es der beste Ausgangspunkt ist, wenn Sie sich den allgemeinen Systemzustand anschauen.

Zwei weitere zu überprüfende Leistungsindikatoren sind wie folgt:

LC: USrv-00-DBStore\\USrv-002-Warteschlangen Latenz (MS)

LC: USrv-00-DBStore\\USrv-004-Latenz Wartezeit (MS)

Der Indikator Warteschlangen Latenz stellt die Zeit dar, die eine in der Warteschlange verbrachte Anforderung an das Back-End und die Latenz Wartezeit für das Back-End für die Verarbeitung der Anforderung darstellt. Wenn sich der Datenträger, der Arbeitsspeicher, das Netzwerk und der Prozessor auf dem Back-End-Gerät aus irgendeinem Grund in Schwierigkeiten befinden, ist der Warteschlangen Latenz-Indikator sehr groß.

Sie kann auch bei einer großen Netzwerklatenz zwischen dem Front-End und dem Back-End sehr groß sein. Was ist also eine akzeptable Warteschlangen Wartezeit?

Bei 12 Sekunden starten die Front-End-Server die Drosselung von Anforderungen an die Back-End-Server. Dies bedeutet, dass die Server den Server zu ausgelastet zurückgeben – 503-Fehler für die Clients. Bei einem fehlerfreien Server sollten die Warteschlangen Latenzen von weniger als 100 Millisekunden im stationären Zustand liegen, doch in Zeiten, in denen der Server gerade online ist und sich alle Benutzer gleichzeitig anmelden, kann dieser Zähler sehr hoch sein, und Sie können sogar sehen, dass er mehrere Sekunden erreicht hat.

Möglicherweise verfügen Sie über eine Konfiguration mit Lastenausgleich, bei der ein Pool mit mehreren Front-End-Servern und einem Lastenausgleichsmodul bereitgestellt wird, das für "kleinste Anzahl von Verbindungen" konfiguriert ist. Wenn in diesem Fall ein Front-End-Server neu gestartet wird, werden alle Benutzer, die eine erneute Verbindung herstellen möchten, auf den neu gestarteten Server hinweisen, da dieser Server im Vergleich zu den anderen Poolmitgliedern weniger Verbindungen aufweist. Während dieser Zeit kann der jeweilige Front-End-Server überladen sein, während die anderen Pool-Mitglieder dies nicht tun.

Wir empfehlen, dass Sie Wartungsarbeiten außerhalb von Stunden durchführen, um die Leistung zu verringern, da die Benutzer nicht alle mit der Verbindung zum Server gleichzeitig konkurrieren können.

Wenn die beiden vorherigen Leistungsindikatoren stark sind, ist der wahrscheinlichste Engpass der SQL-Back-End-Server. Die nächsten zu bestätigenden Komponenten lauten wie folgt:

  - Ist die SQL Server-CPU zu groß? Handelt es sich beispielsweise um einen Wert von mehr als 80 Prozent?

  - Ist die Datenträgerlatenz höchst?

In einer idealen Welt verfügen Sie über genügend Arbeitsspeicher, um sowohl die RTC-als auch die RTCDYN-Datenbank im Arbeitsspeicher zu haben. Der einzige Grund, warum der Server auf den Datenträger zugreifen würde, besteht darin, in die Protokolldateien zu schreiben und in die Datenbanken zu leeren. Tests haben gezeigt, dass 12 GB Arbeitsspeicher für 100.000-Benutzer Bereitstellungen ausreichend sind. Dabei wird davon ausgegangen, dass die RTC-und RTCDYN-Datenbanken eine Gesamtgröße von weniger als 12 GB aufweisen. Wenn Ihre Datenbanken größer sind, benötigen Sie möglicherweise zusätzlichen Arbeitsspeicher.

Sie können feststellen, ob Ihr SQL Server zusätzlichen Arbeitsspeicher erfordert, indem Sie den Leistungsindikator "Lebenserwartung" der SQL Server-Puffer-Manager-Seite überprüfen. Ein Wert kleiner als 3.600 gibt den arbeitsspeicherdruck an. Wenn Sie über genügend Arbeitsspeicher verfügen, sollten Sie auch wenig bis gar keine Lesevorgänge auf dem Datenbanklaufwerk sehen, da SQL Server nur in die Datenbank geschrieben werden sollte.

In einem lync Server 2013-Front-End-Server gibt es einen zusätzlichen Drosselungsmechanismus, der gestartet wird, wenn die Server Verarbeitungszeit sehr groß ist. Die DBStore-Latenz Drosselung ist nur aktiviert, wenn die Wartezeit für SQL Server sehr groß ist. Ein Beispiel, bei dem eine solche Drosselung aktiviert ist, ist, wenn der Front-End-Server CPU-gebunden ist.

Wenn die durchschnittliche Verarbeitungszeit **(LC: SIP-07-Load Management\\SIP-000-durchschnittliche Aufbewahrungszeit für eingehende Nachrichten)** auf dem Server sechs Sekunden überschreitet, wechselt der Server in den Drosselungs Modus und gibt Benutzern nur eine ausstehende Transaktion pro Clientverbindung. Sobald die Verarbeitungszeit auf drei Sekunden sinkt, sinkt der Server den Drosselungs Modus und gibt Benutzern bis zu 20 ausstehende Transaktionen pro Clientverbindung. Wenn die Anzahl der Transaktionen für eine bestimmte Verbindung den oben genannten Schwellenwert überschreitet, wird die Verbindung als Fluss gesteuert markiert. Das Ergebnis ist, dass der Server keine empfangenen Beiträge bereitstellt, und der Zähler **LC: SIP-01-\\Peers Flow Controlled Connections** inkrementiert wird. Wenn eine Verbindung länger als eine Minute in einem Flow-Controlled-Zustand verbleibt, wird Sie vom Server geschlossen. Es tut so faul. Wenn Sie die Möglichkeit hat, die Verbindung zu überprüfen, bestimmt Sie, ob Sie zu lange gedrosselt wurde, und schließt Sie, wenn Sie mehr als eine Minute hat.

Hierbei handelt es sich um die beiden Drosselungs Mechanismen, und es gibt einen Leistungsindikator, der zusammenfasst, was, wenn überhaupt, die Drosselung des Servers ausführt.

**LC: SIP-04-Antworten\\SIP-053-lokale 503-Antworten/Sek.**

  - Der Ausdruck "local" im vorherigen Leistungsindikator bezieht sich auf lokal generierte Antworten.

  - Der 503-Code entspricht dem Server, der nicht verfügbar ist, wobei keine 503-Codes auf einem fehlerfreien Server angezeigt werden sollten. Während des Zeitraums, nachdem ein Server gerade online geschaltet wurde, werden möglicherweise einige 503-Codes angezeigt. Wenn sich alle Benutzer wieder anmelden und der Server in einen stabilen Zustand zurückkehrt, sollten keine zusätzlichen 503-Codes vorhanden sein.

**LC: SIP-04-Antworten\\SIP-074-lokale 504-Antworten/Sek.**

Dieser Leistungsindikator zeigt Verbindungsprobleme mit anderen Servern an und kann auf Verbindungsfehler oder Verzögerungen bei der Verbindung hindeuten. Wenn 504-Fehler angezeigt werden, sollte der folgende Leistungsindikator überprüft werden.

**LC: SIP-01-Peers\\SIP-017-sendet hervorragende**

Dieser Leistungsindikator zeigt die Anzahl der ausgehenden Warteschlangenanforderungen und Antworten an. Wenn dieser Leistungsindikator höher ist, liegt das Problem höchstwahrscheinlich nicht auf dem lokalen Server. Beachten Sie, dass dieser Leistungsindikator bei Problemen mit der Netzwerklatenz sehr groß sein kann. Sie kann auch auf Probleme mit dem lokalen Netzwerkadapter hindeuten, ist aber wahrscheinlicher auf ein Problem auf einem Remoteserver zurückzuführen. Dieser Leistungsindikator wäre höchstwahrscheinlich auf einem Director-Server zu groß, wenn der Pool, mit dem er kommunizieren möchte, überlastet ist. Der Schlüssel für diesen Leistungsindikator besteht darin, die Instanzen zu betrachten, nicht nur die Summe.

</div>

</div>

<span> </span>

</div>

</div>

</div>

