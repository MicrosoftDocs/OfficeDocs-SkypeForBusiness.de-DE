---
title: 'Lync Server 2013: Überwachung lync Server Leistung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Lync Server 2013 performance
ms:assetid: 2acfd720-6120-4816-a2d4-30476bd5cd0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720910(v=OCS.15)
ms:contentKeyID: 63969592
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb8f57d25f02102cd407a320ffc11f3e8ff9497c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-lync-server-2013-performance"></a>Überwachen der lync Server 2013 Leistung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-05-15_

Lync Server 2013 Leistung wird durch verschiedene Faktoren wie Benutzerprofile, Systemarchitektur, Software, Hardwarekomponenten, Drittanbieter-Integrationspunkte wie Gateways und Telefoniegeräte, Netzwerkkonnektivität und Leistung, Windows Active Directory Dienstkonfiguration und-Leistung zusätzlich zu den Funktionen des Windows-Betriebssystems.

Im Mittelpunkt der Leistung einer lync Server 2013-Bereitstellungen steht die Server Software und-Hardware, auf der Sie implementiert ist. Ein Front-End-Server muss beispielsweise über ausreichende Hardwareressourcen verfügen, um die erwartete (kurzzeitige) Benutzerlast zu bewältigen. Wenn ein jeweiliger Front-End-Server für die Bereitstellung von Diensten für 10000-Benutzer erforderlich ist, muss ein entsprechend konfigurierter Server die erwarteten Ladeanforderungen erfüllen, um letztendlich die bestmögliche Endbenutzererfahrung sicherzustellen.

Die Überwachung der Serverleistung ist daher äußerst wichtig, um zu überprüfen, ob die implementierte Serverinfrastruktur über geeignete Hardwareressourcen für die täglichen Spitzenlastanforderungen verfügt. Die Überwachung der Serverleistung hilft bei der Ermittlung von Systemengpässen, mit denen Administratoren korrigierende Aktionen durchsetzen können, bevor die Endbenutzerumgebung betroffen ist. Die Leistungsdaten sollten für die langfristige Kapazitätsplanung verwendet werden.

Während detaillierte Informationen zu allen zu beachtenden Leistungsobjekten und Leistungsindikatoren in [Monitoring lync Server 2013 mit System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)verknüpft sind, können einige Leistungsindikatoren, denen Sie folgen sollten, Administratoren einen schnellen Überblick über die Systemleistung geben:

  - Zum Nachverfolgen des allgemeinen Systemzustands des Front-End-Servers ist ein guter Ausgangspunkt,\\Prozessorzeit Prozessor% zu überprüfen. Der Wert sollte immer unter 80 Prozent liegen.

  - Überwachen Sie die folgenden Leistungsindikatoren, um die Leistung der vom Front-End-Pool verwendeten Back-End-SQL Server Datenbanksoftware-Instanz nachzuverfolgen:
    
    LC: USrv – 00 – DBStore\\USrv – 002 – Warteschlangen Wartezeit (MS)
    
    LC: USrv – 00 – DBStore\\USrv – 0 04 – Wartezeit in der Warte Prozedur (MS)
    
    Der fehlerfreie Server im stationären Zustand \<sollte 100 MS-Latenzwerte anzeigen. Der Einschränkungsmechanismus wird aktiviert, wenn die Wartezeit 12 Sekunden erreicht, was bedeutet, dass der Front-End-Server die Einschränkungsanforderungen an das Back-End startet. Dies bewirkt, dass Clients beginnen, eine zu beschäftigte Fehlermeldung mit 503 Server zu erhalten.

  - Überwachen Sie den folgenden Leistungsindikator, um die Verarbeitungszeit auf dem Front-End-Server nachzuverfolgen:
    
    LC: SIP-07-laden Verwaltung\\SIP-000 – durchschnittliche Aufbewahrungszeit für eingehende Nachrichten
    
    Hierbei handelt es sich um einen weiteren Einschränkungsmechanismus für die Front-End-Server, und zwar ab dem Zeitpunkt, zu dem die Verarbeitungszeit auf dem Front-End hoch ist. Wenn die durchschnittliche Verarbeitungszeit mehr als sechs Sekunden beträgt, wechselt der Server in den Drosselungs Modus und ermöglicht nur eine ausstehende Transaktion pro Clientverbindung.

  - Überwachen Sie den folgenden Leistungsindikator, um Arbeitsspeicherprobleme auf dem SQL-Back-End-Server nachzuverfolgen:
    
    Lebenserwartung von\\SQL Server Puffer-Manager-Seite
    
    Ein niedriger Wert unterhalb von 3600 Sekunden (zusammen mit Schreibvorgängen mit hoher Latenz/s und Prüf Punkt Seiten/Sek.) weist auf den arbeitsspeicherdruck hin.

<div>

## <a name="additional-counters-to-view"></a>Anzeigen zusätzlicher Leistungsindikatoren

Es gibt mehrere wichtige Indikatoren, die gute Indikatoren für die allgemeine Integrität auf dem Front-End-Server sind. Dies ist keine umfassende Liste, die nicht dazu dient, die Ursache zu ermitteln. Mit diesen Leistungsindikatoren können Sie eine schnelle Überprüfung ihrer Serverintegrität durchführen. Es wird empfohlen, diese Leistungsindikatoren auf jedem Server im Pool zu überprüfen. Es ist wichtig zu verstehen, was diese Indikatorwerte sind, wenn Ihr Serverfehler frei ist. Ein Basisplan ist erforderlich, um zu verstehen, was geändert wurde, wenn die Benutzeroberfläche beeinträchtigt wird.

Der Front-End-Server kann auf Probleme hindeuten, die möglicherweise durch Engpässe an anderen Stellen im System verursacht werden. Dies bedeutet, dass dies der beste Ausgangspunkt ist, wenn Sie sich die Gesamtsystem Integrität ansehen.

Es folgen zwei zusätzliche Indikatoren, die Sie zuerst überprüfen können:

LC: USrv-00-DBStore\\USrv-002 – Warteschlangen Wartezeit (MS)

LC: USrv-00-DBStore\\USrv-004-Wartezeit für die Warte Prozedur (MS)

Der Indikator Warteschlangen Wartezeit stellt die Zeit dar, die eine in der Warteschlange verbrachte Anforderung an das Back-End und die Wartezeit für die Prozedur die Zeit darstellt, die für das Back-End zum Verarbeiten der Anforderung benötigt wurde. Wenn der Datenträger, der Arbeitsspeicher, das Netzwerk und der Prozessor auf dem Back-End aus irgendeinem Grund in Schwierigkeiten geraten, ist der Indikator für Warteschlangen Wartezeit hoch.

Es kann auch hoch sein, wenn es eine hohe Netzwerkwartezeit zwischen dem Front-End und dem Back-End gibt. Was ist also eine akzeptable Warteschlangen Wartezeit?

Bei 12 Sekunden beginnen die Front-End-Server mit Einschränkungsanforderungen an die Back-End-Server. Dies bedeutet, dass die Server mit dem Zurückgeben des Servers zu beschäftigt beginnen – 503 Fehler für die Clients. Ein fehlerfreier Server sollte weniger als 100 MS DBStore Warteschlangen Latenzen im stationären Zustand haben, aber in Zeiten, in denen der Server gerade online geschaltet wurde und sich Benutzer alle gleichzeitig anmelden, kann dieser Indikator sehr hoch sein, und Sie können sogar mehrere Sekunden drücken.

Möglicherweise verfügen Sie über eine Konfiguration mit Lastenausgleich, bei der ein Pool mit mehreren Front-End-Servern und einem Lastenausgleichsmodul bereitgestellt wird, das für "least number of Connections" konfiguriert ist. In diesem Fall wird, wenn ein Front-End-Server neu gestartet wird, alle Benutzer, die versuchen, eine erneute Verbindung herzustellen, auf den neu gestarteten Server verwiesen, da dieser Server im Vergleich zu den anderen Poolmitgliedern weniger Verbindungen haben wird. Während dieser Zeit ist der jeweilige Front-End-Server möglicherweise überlastet, während die anderen Poolmitglieder nicht sind.

Es wird empfohlen, dass Sie Wartungsarbeiten außerhalb der Arbeitszeiten durchführen, um die Leistung zu verringern, da Benutzer nicht alle gleichzeitig eine Verbindung mit dem Server herstellen.

Wenn die beiden vorherigen Leistungsindikatoren hoch sind, ist der wahrscheinlichste Engpass der SQL-Back-End-Server. Die folgenden Komponenten zur Bestätigung lauten wie folgt:

  - Ist die SQL Server CPU zu hoch? Handelt es sich beispielsweise um mehr als 80 Prozent?

  - Ist die Datenträgerwartezeit hoch?

In einer idealen Welt haben Sie genügend Arbeitsspeicher, um sowohl die RTC-als auch die RTCDYN-Datenbank im Arbeitsspeicher zu haben. Der einzige Grund dafür, dass der Server auf den Datenträger zugreift, besteht darin, in die Protokolldateien zu schreiben und in die Datenbanken zu leeren. Tests haben gezeigt, dass 12 GB RAM für 100.000-Benutzer Bereitstellungen ausreicht. Dabei wird davon ausgegangen, dass die Größe der RTC-und RTCDYN-Datenbanken weniger als 12 GB beträgt. Wenn Ihre Datenbanken größer sind, benötigen Sie möglicherweise zusätzlichen Arbeitsspeicher.

Sie können ermitteln, ob Ihre SQL Server zusätzlichen Arbeitsspeicher erfordert, indem Sie den Leistungsindikator SQL Server Buffer Manager-Seite für die Lebenserwartung der Puffer Prüfung anzeigen. Ein Wert kleiner als 3.600 gibt arbeitsspeicherdruck an. Sie sollten auch wenig bis gar keine Lesevorgänge auf dem Datenbanklaufwerk sehen, wenn Sie über ausreichend Arbeitsspeicher verfügen, da SQL Server nur in die Datenbank schreiben sollten.

Es gibt einen zusätzlichen Einschränkungsmechanismus in einer lync Server 2013 Front-End-Server, der gestartet wird, wenn die Server Verarbeitungszeit hoch ist. Die DBStore-Latenz Drosselung ist nur aktiviert, wenn die Wartezeit für die SQL Server hoch ist. Ein Beispiel für die Aktivierung einer solchen Einschränkung ist, wenn der Front-End-Server CPU-gebunden ist.

Wenn die durchschnittliche Verarbeitungszeit **(LC: SIP-07-Last Management\\SIP-000 – durchschnittliche Aufbewahrungszeit für eingehende Nachrichten)** auf dem Server sechs Sekunden überschreitet, wechselt der Server in den Drosselungs Modus und gibt Benutzern nur eine ausstehende Transaktion pro Clientverbindung. Sobald die Verarbeitungszeit auf drei Sekunden abfällt, fällt der Server aus dem Drosselungs Modus und gibt Benutzern bis zu 20 ausstehende Transaktionen pro Clientverbindung. Wenn die Anzahl der Transaktionen für eine bestimmte Verbindung den oben genannten Schwellenwert überschreitet, wird die Verbindung als Fluss gesteuert markiert. Das Ergebnis ist, dass der Server keine erhält, und der Indikator **LC: SIP-01-Peers\\Flow Controlled Connections** wird inkrementiert. Wenn eine Verbindung länger als eine Minute in einem flusskontrollierten Zustand verbleibt, wird Sie vom Server geschlossen. Es tut so träge. Wenn Sie die Möglichkeit zum Überprüfen der Verbindung hat, bestimmt Sie, ob Sie zu lange gedrosselt wurde, und schließt Sie, wenn Sie mehr als eine Minute hat.

Hierbei handelt es sich um die beiden Einschränkungs Mechanismen, und es gibt einen Leistungsindikator, der zusammenfasst, was, wenn überhaupt, die Drosselung des Servers ausführt.

**LC: SIP-04-Responses\\SIP-053-lokale 503 Antworten/Sek.**

  - Der Ausdruck "local" im vorherigen Leistungsindikator bezieht sich auf lokal generierte Antworten.

  - Der 503-Code entspricht dem Server, der nicht verfügbar ist und auf dem keine 503-Codes auf einem fehlerfreien Server angezeigt werden sollten. Während des Zeitraums, nach dem ein Server gerade online geschaltet wurde, werden möglicherweise einige 503-Codes angezeigt. Wenn sich alle Benutzer wieder anmelden und der Server in einen stabilen Zustand wechselt, sollten keine zusätzlichen 503-Codes vorhanden sein.

**LC: SIP-04-Responses\\SIP-074-lokale 504 Antworten/Sek.**

Dieser Leistungsindikator weist auf Verbindungsprobleme mit anderen Servern hin und kann auf Fehler beim Herstellen einer Verbindung oder auf Verzögerungen beim Verbinden hindeuten. Wenn 504 Fehler angezeigt werden, sollte der folgende Leistungsindikator überprüft werden.

**LC: SIP-01-Peers\\SIP-017-Sends Outstanding**

Dieser Indikator gibt die Anzahl der ausgehenden Anforderungen und Antworten in der Warteschlange an. Wenn dieser Leistungsindikator hoch ist, ist das Problem wahrscheinlich nicht auf dem lokalen Server. Beachten Sie, dass dieser Indikator hoch sein kann, wenn es Probleme mit der Netzwerkwartezeit gibt. Dies kann auch auf Probleme mit dem lokalen Netzwerkadapter hindeuten, wird jedoch wahrscheinlich durch ein Problem auf einem Remoteserver verursacht. Dieser Leistungsindikator wäre höchstwahrscheinlich auf einem Director-Server hoch, wenn der Pool, mit dem er kommunizieren möchte, überlastet ist. Der Schlüssel mit diesem Indikator besteht darin, die Instanzen zu betrachten, nicht nur die Summe.

</div>

</div>

<span> </span>

</div>

</div>

</div>

