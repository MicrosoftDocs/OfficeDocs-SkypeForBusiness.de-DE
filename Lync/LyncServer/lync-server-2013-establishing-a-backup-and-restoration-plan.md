---
title: 'Lync Server 2013: Einrichten eines Sicherungs-und Wiederherstellungsplans'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Establishing a backup and restoration plan
ms:assetid: 9f562ef1-3804-41e2-b3e4-d45b2e8c63c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202183(v=OCS.15)
ms:contentKeyID: 51541499
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b3516e63a7cbada4a89fad3540406e38b299fef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a>Einrichten eines Sicherungs-und Wiederherstellungsplans für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-17_

Das Erstellen eines Sicherungs-und Wiederherstellungsplans umfasst die folgenden Schritte:

  - Entwickeln des Plans

  - Implementieren des Plans

  - Den Plan pflegen.

<div>

## <a name="developing-a-backup-and-restoration-plan"></a>Entwickeln eines Sicherungs-und Wiederherstellungsplans

Nachdem Sie Ihre Sicherungs-und Wiederherstellungsstrategie für lync Server entwickelt haben, verwenden Sie diese, um einen detaillierten Sicherungs-und Wiederherstellungsplan zu dokumentieren. In Ihrem Plan sollten die Prioritäten und Anforderungen für das Sichern von Daten und Einstellungen eindeutig vermittelt werden. Sie können die Informationen beim [Einrichten einer Sicherungs-und Wiederherstellungsstrategie für lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) und der Arbeitsblätter in [Arbeitsblättern für die Sicherung und Wiederherstellung für lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) verwenden, um die Dokumentation Ihrer Strategie zu vereinfachen. Ihr Plan sollte auch Kriterien für die Entscheidung enthalten, wann und wie der Dienst wiederhergestellt werden soll.

Wenn Sie Ihren Plan entwickeln, müssen Sie Folgendes berücksichtigen:

  - So können Sie Server auf neuer Hardware wiederherstellen.

  - Hier erfahren Sie, wie Sie Dienste wiederherstellen, für die ein Tätigwerden mehrerer Geschäftsbereiche oder Abteilungen erforderlich ist.

  - So können Sie Ersatzserver schnell erwerben.

  - Die Zeit, die für die Wiederherstellung mithilfe ihrer Strategie benötigt wird. Bedenken Sie die Anforderungen Ihrer Organisation an Recovery Time Objective (RTO).

Ändern Sie die Sicherungs-und Wiederherstellungsverfahren in diesem Thema, indem Sie die erforderlichen Schritte hinzufügen und löschen, um die Server und Komponenten in Ihrer Bereitstellung wiederzugeben. Sie können auch geeignete Details wie den Sicherungszeitplan zu den entsprechenden Verfahren hinzufügen, um sicherzustellen, dass die Informationen nicht übersehen werden.

<div>


> [!NOTE]  
> Es empfiehlt sich, Skripts für so viele Schritte wie möglich zu erstellen, um die Qualität und Reproduzierbarkeit der Verfahren zu gewährleisten.



</div>

Geben Sie in Ihrem Plan an, wer für die Überprüfung des Plans verantwortlich ist, wer für das Testen und Überprüfen neuer Verfahren oder Tools verantwortlich ist und wer alle Änderungen am Plan und den zugehörigen Verfahren genehmigen muss.

Wenn Sie sicherstellen möchten, dass Ihr Sicherungs-und Wiederherstellungsplan alle festgelegten Ziele und Prioritäten in vollem Umfang erfüllt, besorgen Sie sich die Genehmigung der zuständigen Entscheidungsträger und technischen Entscheidungsträger in Ihrer Organisation, bevor Sie den Plan implementieren.

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a>Implementieren des Sicherungs-und Wiederherstellungsplans

Für die Implementierung eines Sicherungs-und Wiederherstellungsplans sind die folgenden Schritte erforderlich:

  - Testen und Überprüfen des Plans

  - Den Plan kommunizieren.

  - Überprüfen von Sicherungs-und Wiederherstellungsvorgängen

<div>

## <a name="testing-and-validating-the-plan"></a>Testen und Überprüfen des Plans

Die hier beschriebenen Verfahren wurden in einer Lab-Umgebung getestet und validiert. Wenn Sie sicherstellen möchten, dass diese oder andere Verfahren in Ihrer Umgebung funktionieren, sollten Sie jede Prozedur testen und überprüfen, die Sie implementieren möchten. Führen Sie die Tests und die Validierung durch, bevor Sie Ihren Plan zur endgültigen Genehmigung übermitteln.

</div>

<div>

## <a name="communicating-the-plan"></a>Kommunizieren des Plans

In Ihrem Sicherungs-und Wiederherstellungsplan sollte klar beschrieben werden, wer Prozeduren und schrittweise Anleitungen zum Durchführen der Verfahren implementiert. Sie sollten sicherstellen, dass jeder, der für einen Aspekt der Sicherung und Wiederherstellung verantwortlich ist, den Plan, die Art der Implementierung und deren Rolle versteht. Dazu gehören alle Implementierungsanforderungen für Folgendes:

  - Pool-und Serversicherung

  - Wiederherstellung des Diensts.

**Pool-und Serversicherung**

Der Sicherungs-und Wiederherstellungsplan sollte alle Informationen umfassen, die erforderlich sind, um Sicherungsverfahren kontinuierlich abzuschließen. Die primären Informationen, die den Verantwortlichen Teammitgliedern mitgeteilt werden, umfassen Folgendes:

  - Team oder Person (als Einzelperson oder Rolle angegeben), die für die Sicherung der einzelnen Server verantwortlich ist.

  - Spezifische Zeitpläne zum Sichern der einzelnen Server.

  - Sicherungsspeicherorte für die einzelnen Datentypen (Einstellungen, Datenbank und Dateifreigaben).

  - Zu verwendende Sicherungsverfahren, einschließlich der Tools, die für die Ausführung der einzelnen Verfahren erforderlich sind.

  - Informationen, die erforderlich sind, um Sicherungen abzuschließen, wie in den [Arbeitsblättern für die Sicherung und Wiederherstellung für lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)behandelt.

  - Überprüfungsmethoden, die verwendet werden, um sicherzustellen, dass Daten und Einstellungen entsprechend gesichert und für die Wiederherstellung verfügbar sind, die regelmäßige Überprüfungen und Testwiederherstellungen enthalten können.

**Wiederherstellung des Diensts**

Der Sicherungs-und Wiederherstellungsplan sollte alle zum Wiederherstellen des Diensts erforderlichen Informationen enthalten, falls auf einem oder mehreren Servern ein Verlust auftritt, der den Dienst nicht verfügbar macht. Die primären Informationen, die den Verantwortlichen Teammitgliedern mitgeteilt werden, umfassen Folgendes:

  - Team oder Person (als Einzelperson oder Rolle angegeben), die für die Bestimmung der Notwendigkeit der Wiederherstellung des Diensts sowie der für die Wiederherstellung des Diensts zu verwendenden Verfahren sowie für das Team oder die Person verantwortlich ist, die für die Implementierung der jeweiligen Verfahren verantwortlich ist Wiederherstellungsszenario

  - Kriterien zum ermitteln, welche Wiederherstellungsverfahren für eine bestimmte Situation am besten geeignet sind.

  - Zeitschätzungen für die Wiederherstellung des Dienst-und Wiederherstellungszeit Ziels (RTO) in jedem Wiederherstellungsszenario.

  - Zu verwendende Wiederherstellungsverfahren, einschließlich der Tools, die für die Ausführung der einzelnen Verfahren erforderlich sind.

  - Informationen, die zum Wiederherstellen von Daten und Einstellungen erforderlich sind. Arbeitsblätter werden in [Arbeitsblättern zur Sicherung und Wiederherstellung für lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)bereitgestellt.

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a>Überprüfen von Sicherungs-und Wiederherstellungsvorgängen

Nachdem Sie die anfänglichen Sicherungsbemühungen in Ihrer Produktionsumgebung und in bestimmten Intervallen abgeschlossen haben (wie in Ihrem Sicherungs-und Wiederherstellungsplan beschrieben), sollten Sie Folgendes überprüfen:

  - Backups erfolgen nach Bedarf.

  - Auf gesicherte Daten und Einstellungen kann zugegriffen werden.

  - Wiederherstellungsverfahren können innerhalb der im Sicherungs-und Wiederherstellungsplan angegebenen RTO-Zeiten (Recovery Time Objective) ausgeführt werden, und die Ergebnisse erfüllen alle Geschäftsanforderungen.

  - Backup-Arbeitsblätter wurden abgeschlossen und überprüft, und Sie werden an einem sicheren Ort gespeichert. Diese Arbeitsblätter werden in [Arbeitsblättern zur Sicherung und Wiederherstellung für lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)bereitgestellt.

  - Wiederherstellungsverfahren wurden getestet und überprüft, wie in Ihrem Sicherungs-und Wiederherstellungsplan angegeben, wie erwartet funktioniert.

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a>Verwalten des Sicherungs-und Wiederherstellungsplans

Eine lync Server-Topologie ist eine dynamische Umgebung, die sich in Ihrer Organisation ändert. Überprüfen Sie den Sicherungs-und Wiederherstellungsplan, während sich die Organisation ändert, und überprüfen Sie ihn regelmäßig, um sicherzustellen, dass er weiterhin den Anforderungen Ihres Unternehmens entspricht.

</div>

</div>

<span> </span>

</div>

</div>

</div>

