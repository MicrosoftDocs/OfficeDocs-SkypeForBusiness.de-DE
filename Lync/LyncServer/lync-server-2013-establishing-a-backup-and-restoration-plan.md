---
title: 'Lync Server 2013: Einrichten eines Sicherungs-und Wiederherstellungsplans'
description: 'Lync Server 2013: Einrichten eines Sicherungs-und Wiederherstellungsplans.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration plan
ms:assetid: 9f562ef1-3804-41e2-b3e4-d45b2e8c63c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202183(v=OCS.15)
ms:contentKeyID: 51541499
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06d93c713364bf6b5f230b255b68a2c1dfe1d04a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555051"
---
# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a>Einrichten eines Sicherungs-und Wiederherstellungsplans für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-17_

Das Erstellen eines Sicherungs- und Wiederherstellungsplans beinhaltet die folgenden Schritte:

  - Entwickeln des Plans.

  - Implementieren des Plans.

  - Verwalten des Plans.

<div>

## <a name="developing-a-backup-and-restoration-plan"></a>Entwickeln eines Sicherungs- und Wiederherstellungsplans

Nachdem Sie die Sicherungs-und Wiederherstellungsstrategie für lync Server entwickelt haben, verwenden Sie diese, um einen detaillierten Sicherungs-und Wiederherstellungsplan zu dokumentieren. In diesem Plan sollten die Prioritäten und Anforderungen zum Sichern von Daten und Einstellungen eindeutig festgehalten sein. Sie können die Informationen unter [Einrichten einer Sicherungs-und Wiederherstellungsstrategie für lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) und der Arbeitsblätter in [Sicherungs-und Wiederherstellungs Arbeitsblättern für lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) verwenden, um die Dokumentation Ihrer Strategie zu vereinfachen. Ihr Plan sollte außerdem Kriterien enthalten, wann und wie die Serverbereitschaft wiederhergestellt werden soll.

Während Sie Ihren Plan entwickeln, müssen Sie Folgendes berücksichtigen und berücksichtigen:

  - Wie Server auf neuer Hardware wiederhergestellt werden

  - Wie Dienste wiederhergestellt werden, an denen mehrere Unternehmensbereiche oder Abteilungen involviert sind

  - Wie Ersatzserver schnell beschafft werden können

  - Den Zeitaufwand für die Wiederherstellung mithilfe Ihrer Strategie Überprüfen Sie die Anforderungen Ihrer Organisation an die RTO (Recovery Time Objective).

Ändern Sie die Sicherungs-und Wiederherstellungsverfahren in diesem Thema, indem Sie Verfahren entsprechend hinzufügen und löschen, um die Server und Komponenten in Ihrer Bereitstellung widerzuspiegeln. Sie können den entsprechenden Verfahren auch entsprechende Details wie den Sicherungszeitplan hinzufügen, um sicherzustellen, dass die Informationen nicht außer acht lassen.

<div>


> [!NOTE]  
> Es empfiehlt sich, Skripts für so viele Schritte wie möglich zu erstellen, um die Qualität und Reproduzierbarkeit von Verfahren sicherzustellen.



</div>

Geben Sie in Ihrem Plan an, wer für die Überprüfung des Plans zuständig ist, wer für das Testen und validieren neuer Verfahren oder Tools zuständig ist und welche Änderungen am Plan und den dazugehörigen Verfahren genehmigt werden müssen.

Um sicherzustellen, dass Ihr Sicherungs-und Wiederherstellungsplan alle festgelegten Ziele und Prioritäten vollständig erfüllt, müssen Sie vor der Implementierung des Plans die Genehmigung der entsprechenden geschäftlichen Entscheidungsträger und technischen Entscheidungsträger in Ihrer Organisation einholen.

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a>Implementieren des Sicherungs- und Wiederherstellungsplans

Die Implementierung eines Sicherungs-und Wiederherstellungsplans erfordert die folgenden Schritte:

  - Testen und Überprüfen des Plans.

  - Kommunizieren des Plans.

  - Überprüfen der Sicherungs-und Wiederherstellungsvorgänge

<div>

## <a name="testing-and-validating-the-plan"></a>Testen und Überprüfen des Plans

Die hier beschriebenen Verfahren wurden in einer Testumgebung getestet und validiert. Um sicherzustellen, dass diese oder andere Verfahren in Ihrer Umgebung funktionieren, sollten Sie die einzelnen Verfahren testen und validieren, die Sie implementieren möchten. Schließen Sie die Tests und die Überprüfung ab, bevor Sie Ihren Plan zur endgültigen Genehmigung übermitteln.

</div>

<div>

## <a name="communicating-the-plan"></a>Vermitteln des Plans

In Ihrem Sicherungs- und Wiederherstellungsplan sollten die Personen, die Verfahren implementieren, sowie die schrittweisen Anleitungen zum Ausführen der Verfahren eindeutig beschrieben sein. Sie sollten sicherstellen, dass jeder, der für alle Aspekte der Sicherung und Wiederherstellung verantwortlich ist, den Plan, die Implementierung und die Rolle des Plans versteht. Dies beinhaltet alle Implementierungsanforderungen für Folgendes:

  - Pool-und Serversicherung.

  - Wiederherstellung des Diensts.

**Pool- und Serversicherung**

Der Sicherungs- und Wiederherstellungsplan sollte alle erforderlichen Informationen beinhalten, um Sicherungsverfahren fortlaufend auszuführen. Dies sind die wichtigsten Informationen, welche die zuständigen Teammitglieder benötigen:

  - Team oder Person (als Person oder Rolle angegeben), die für die Sicherung der einzelnen Server verantwortlich ist.

  - Bestimmte Zeitpläne für die Sicherung der einzelnen Server.

  - Sicherungsspeicherorte für die einzelnen Datentypen (Einstellungen, Datenbanken und Dateifreigaben).

  - Zu verwendende Sicherungsverfahren, einschließlich der Tools, die zum Abschließen der einzelnen Verfahren erforderlich sind.

  - Informationen, die zum Abschließen von Sicherungen erforderlich sind, wie in [Sicherungs-und Wiederherstellungs Arbeitsblättern für lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)behandelt.

  - Validierungsmethoden, die verwendet werden, um sicherzustellen, dass Daten und Einstellungen ordnungsgemäß gesichert und für die Wiederherstellung verfügbar sind, die regelmäßige Überprüfungen und Testwiederherstellungen umfassen kann.

**Wiederherstellung der Serverbereitschaft**

Der Sicherungs-und Wiederherstellungsplan sollte alle Informationen enthalten, die zum Wiederherstellen des Diensts erforderlich sind, für den Fall, dass ein oder mehrere Server einen Verlust erfahren, der den Dienst nicht verfügbar machen kann. Dies sind die wichtigsten Informationen, welche die zuständigen Teammitglieder benötigen:

  - Das Team oder die Person (Angabe als Einzelperson oder Rolle), das bzw. die entscheidet, wann die Serverbereitschaft wiederhergestellt werden muss und welche Verfahren dabei verwendet werden. Außerdem das Team oder die Person, das bzw. die für das Implementieren der Verfahren für jedes Wiederherstellungsszenario zuständig ist.

  - Kriterien, um die für eine bestimmte Situation geeignetsten Wiederherstellungsverfahren zu bestimmen.

  - Zeitschätzungen für die Wiederherstellung des Dienst-und Wiederherstellungszeit Ziels (RTO) in jedem Wiederherstellungsszenario.

  - Zu verwendende Wiederherstellungsverfahren, einschließlich der erforderlichen Tools zum Ausführen der einzelnen Verfahren.

  - Erforderliche Informationen zum Wiederherstellen von Daten und Einstellungen. Arbeitsblätter werden in [Sicherungs-und Wiederherstellungs Arbeitsblättern für lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)bereitgestellt.

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a>Überprüfen der Sicherungs- und Wiederherstellungsvorgänge

Nach Abschluss der ersten Sicherungsschritte in Ihrer Produktionsumgebung und in den angegebenen Intervallen (gemäß Sicherungs- und Wiederherstellungsplan) sollten Sie Folgendes überprüfen:

  - Sicherungen erfolgen bedarfsgemäß.

  - Auf gesicherte Daten und Einstellungen kann zugegriffen werden.

  - Wiederherstellungsverfahren können innerhalb der im Sicherungs-und Wiederherstellungsplan angegebenen RTO-Zeiten (Recovery Time Object) durchgeführt werden, und die Ergebnisse erfüllen alle geschäftlichen Anforderungen.

  - Sicherungsarbeitsblätter wurden ausgefüllt und geprüft und sind an einem sicheren Speicherort gespeichert. Diese Arbeitsblätter werden in [Sicherungs-und Wiederherstellungs Arbeitsblättern für lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)bereitgestellt.

  - Wiederherstellungsverfahren wurden getestet und geprüft, um sicherzustellen, dass sie gemäß Sicherungs- und Wiederherstellungsplan ausgeführt werden.

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a>Verwalten des Sicherungs- und Wiederherstellungsplans

Eine lync Server Topologie ist eine dynamische Umgebung, die sich in Ihrer Organisation ändert. Überprüfen Sie den Sicherungs-und Wiederherstellungsplan, wenn sich Ihre Organisation ändert, und überprüfen Sie ihn regelmäßig, um sicherzustellen, dass er weiterhin den Anforderungen Ihres Unternehmens entspricht.

</div>

</div>

<span> </span>

</div>

</div>

</div>

