---
title: Einrichten eines Sicherungs- und Wiederherstellungsplans
TOCTitle: Einrichten eines Sicherungs- und Wiederherstellungsplans
ms:assetid: 9f562ef1-3804-41e2-b3e4-d45b2e8c63c9
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh202183(v=OCS.15)
ms:contentKeyID: 52056397
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Einrichten eines Sicherungs- und Wiederherstellungsplans

 

_**Letztes Änderungsdatum des Themas:** 2013-02-17_

Das Erstellen eines Sicherungs- und Wiederherstellungsplans beinhaltet die folgenden Schritte:

  - Entwickeln des Plans

  - Implementieren des Plans

  - Verwalten des Plans

## Entwickeln eines Sicherungs- und Wiederherstellungsplans

Nachdem Sie eine Sicherungs- und Wiederherstellungsstrategie für Lync Server entwickelt haben, dokumentieren Sie damit einen ausführlichen Sicherungs- und Wiederherstellungsplan. In diesem Plan sollten die Prioritäten und Anforderungen zum Sichern von Daten und Einstellungen eindeutig festgehalten sein. Die Informationen in [Einrichten einer Sicherungs- und Wiederherstellungsstrategie](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) und die Arbeitsblätter in [Arbeitsblätter zur Sicherung und Wiederherstellung](lync-server-2013-backup-and-restoration-worksheets.md) können Sie beim Dokumentieren Ihrer Strategie heranziehen. Ihr Plan sollte außerdem Kriterien enthalten, wann und wie die Serverbereitschaft wiederhergestellt werden soll.

Beim Entwickeln Ihres Plans müssen Sie Folgendes berücksichtigen:

  - Wie Server auf neuer Hardware wiederhergestellt werden

  - Wie Dienste wiederhergestellt werden, an denen mehrere Unternehmensbereiche oder Abteilungen involviert sind

  - Wie Ersatzserver schnell beschafft werden können

  - Den Zeitaufwand für die Wiederherstellung mithilfe Ihrer Strategie. Berücksichtigen Sie die Anforderungen Ihrer Organisation bei der Zielsetzung für die Wiederherstellungsdauer.

Passen Sie die Sicherungs- und Wiederherstellungsverfahren in diesem Thema an, und fügen Sie in Abhängigkeit von den Servern und Komponenten Ihrer Bereitstellung Verfahren hinzu bzw. löschen Sie Verfahren. Sie können den entsprechenden Verfahren auch Informationen wie z. B. den Sicherungszeitplan hinzufügen, um dafür zu sorgen, dass diese Informationen nicht übersehen werden.


> [!NOTE]
> Es empfiehlt sich, Skripts für möglichst viele Schritte zu erstellen, um die Qualität und Reproduzierbarkeit von Verfahren sicherzustellen.



Geben Sie in Ihrem Plan an, wer für das Überprüfen des Plans, für das Testen und Überprüfen neuer Verfahren oder Tools sowie für das Genehmigen jeglicher Änderungen am Plan und an zugehörigen Verfahren zuständig ist.

Um sicherzustellen, dass Ihr Sicherungs- und Wiederherstellungsplan alle aufgestellten Ziele und Prioritäten in vollem Umfang erfüllt, holen Sie sich die Genehmigung der entsprechenden Geschäftsentscheidungsträger und der Entscheidungsträger für technische Angelegenheiten in Ihrer Organisation ein, bevor Sie den Plan implementieren.

## Implementieren des Sicherungs- und Wiederherstellungsplans

Das Implementieren eines Sicherungs- und Wiederherstellungsplans beinhaltet die folgenden Schritte:

  - Testen und Überprüfen des Plans

  - Vermitteln des Plans

  - Überprüfen der Sicherungs- und Wiederherstellungsvorgänge

## Testen und Überprüfen des Plans

Die hier beschriebenen Verfahren wurden in einer Laborumgebung getestet und geprüft. Um sicherzustellen, dass bei diesen oder anderen Verfahren in Ihrer Umgebung keine Fehler auftreten, sollten Sie jedes Verfahren, das Sie zu implementieren beabsichtigen, testen und überprüfen. Schließen Sie das Testen und Überprüfen ab, bevor Sie Ihren Plan zur endgültigen Genehmigung vorlegen.

## Vermitteln des Plans

In Ihrem Sicherungs- und Wiederherstellungsplan sollten die Personen, die Verfahren implementieren, sowie die schrittweisen Anleitungen zum Ausführen der Verfahren eindeutig beschrieben sein. Sie sollten sicherstellen, dass alle Personen, die für einen Aspekt der Sicherung und Wiederherstellung zuständig sind, den Plan verstehen und wissen, wie dieser implementiert wird und was ihre Aufgabe ist. Dies beinhaltet alle Implementierungsanforderungen für Folgendes:

  - Pool- und Serversicherung

  - Wiederherstellung der Serverbereitschaft

**Pool- und Serversicherung**

Der Sicherungs- und Wiederherstellungsplan sollte alle erforderlichen Informationen beinhalten, um Sicherungsverfahren fortlaufend auszuführen. Dies sind die wichtigsten Informationen, welche die zuständigen Teammitglieder benötigen:

  - Das Team oder die Person (Angabe als Einzelperson oder Rolle), das bzw. die für das Sichern der einzelnen Server zuständig ist

  - Spezielle Zeitpläne zum Sichern der einzelnen Server

  - Sicherungsspeicherorte für jeden Datentyp (Einstellungen, Datenbank und Dateifreigaben)

  - Zu verwendende Sicherungsverfahren, einschließlich der erforderlichen Tools zum Ausführen der einzelnen Verfahren

  - Erforderliche Informationen zum Ausführen von Sicherungen gemäß [Arbeitsblätter zur Sicherung und Wiederherstellung](lync-server-2013-backup-and-restoration-worksheets.md)

  - Zu verwendende Prüfmethoden, um sicherzustellen, dass Daten und Einstellungen ordnungsgemäß gesichert werden und für die Wiederherstellung verfügbar sind, was regelmäßige Prüfungen und Testwiederherstellungen beinhalten kann

**Wiederherstellung der Serverbereitschaft**

Der Sicherungs- und Wiederherstellungsplan sollte alle erforderlichen Informationen beinhalten, um die Bereitschaft von ausgefallenen Servern wiederherzustellen. Dies sind die wichtigsten Informationen, welche die zuständigen Teammitglieder benötigen:

  - Das Team oder die Person (Angabe als Einzelperson oder Rolle), das bzw. die entscheidet, wann die Serverbereitschaft wiederhergestellt werden muss und welche Verfahren dabei verwendet werden. Außerdem das Team oder die Person, das bzw. die für das Implementieren der Verfahren für jedes Wiederherstellungsszenario zuständig ist.

  - Kriterien, um die für eine bestimmte Situation geeignetsten Wiederherstellungsverfahren zu bestimmen.

  - Der geschätzte Zeitaufwand für die Wiederherstellung der Serverbereitschaft und die Zielsetzung für die Wiederherstellungsdauer für jedes Wiederherstellungsszenario.

  - Zu verwendende Wiederherstellungsverfahren, einschließlich der erforderlichen Tools zum Ausführen der einzelnen Verfahren.

  - Erforderliche Informationen zum Wiederherstellen von Daten und Einstellungen. Die Arbeitsblätter gibt es unter [Arbeitsblätter zur Sicherung und Wiederherstellung](lync-server-2013-backup-and-restoration-worksheets.md).

## Überprüfen der Sicherungs- und Wiederherstellungsvorgänge

Nach Abschluss der ersten Sicherungsschritte in Ihrer Produktionsumgebung und in den angegebenen Intervallen (gemäß Sicherungs- und Wiederherstellungsplan) sollten Sie Folgendes überprüfen:

  - Sicherungen erfolgen bedarfsgemäß.

  - Auf gesicherte Daten und Einstellungen kann zugegriffen werden.

  - Wiederherstellungsverfahren können innerhalb des im Sicherungs- und Wiederherstellungsplan angegebenen Zeitraums der Zielsetzung für die Wiederherstellungsdauer ausgeführt werden, und die Ergebnisse erfüllen alle Unternehmensanforderungen.

  - Sicherungsarbeitsblätter wurden ausgefüllt und geprüft und sind an einem sicheren Speicherort gespeichert. Die Arbeitsblätter gibt es unter [Arbeitsblätter zur Sicherung und Wiederherstellung](lync-server-2013-backup-and-restoration-worksheets.md).

  - Wiederherstellungsverfahren wurden getestet und geprüft, um sicherzustellen, dass sie gemäß Sicherungs- und Wiederherstellungsplan ausgeführt werden.

## Verwalten des Sicherungs- und Wiederherstellungsplans

Eine Lync Server-Topologie ist eine dynamische Umgebung, die wie Ihre Organisation Änderungen unterworfen ist. Bewerten Sie Ihren Sicherungs- und Wiederherstellungsplan neu, wenn es in Ihrer Organisation Änderungen gibt, und überprüfen Sie ihn regelmäßig, um sicherzustellen, dass er auch weiterhin die Anforderungen Ihres Unternehmens erfüllt.

