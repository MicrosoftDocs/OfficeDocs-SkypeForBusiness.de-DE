---
title: 'Lync Server 2013: Beginnen des Planungsprozesses'
TOCTitle: Beginnen des Planungsprozesses
ms:assetid: df3722b3-f859-49e1-b3ff-ee6863483731
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398986(v=OCS.15)
ms:contentKeyID: 49295645
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Beginnen des Planungsprozesses für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Die Planung einer lokalen Unified Communications-Bereitstellung mag kompliziert erscheinen, Lync Server stellt jedoch zwei nützliche Tools zu Ihrer Unterstützung bereit:

  - **Das Planungstool** ist ein Assistent, der Ihnen eine Reihe von Fragen zu Ihrer Organisation, den gewünschten Lync Server-Features und Ihren Anforderungen an die Kapazitätsplanung stellt. Basierend auf Ihren Antworten erstellt das Tool eine empfohlene Bereitstellungstopologie und generiert ein Microsoft Visio-Diagramm dieser Bereitstellung.

  - Der **Topologie-Generator** ist eine Installationskomponente von Lync Server. Sie verwenden den Topologie-Generator, um Ihre geplante Topologie zu erstellen, sie anzupassen und zu veröffentlichen. Darüber hinaus überprüft der Topologie-Generator Ihre Topologie, bevor Sie mit den Serverinstallationen beginnen. Einzelne Server, auf denen Lync Server installiert wird, lesen die veröffentlichte Topologie im Rahmen des Installationsprozesses, und das Installationsprogramm stellt den Server gemäß Festlegung in der Topologie bereit.

## Lync Server-Planungstool

Das Planungstool verwendet die von Ihnen im Tool bereitgestellten Antworten, um basierend auf Lync Server-Richtlinien und bewährten Methoden eine Topologie zu generieren. Auf Grundlage Ihrer Antworten bietet das Planungstool zudem verschiedene Ansichten einer Bereitstellung. Es stellt sowohl eine globale Ansicht aller Standorte (einschließlich der zentralen Standorte und Zweigstellen) als auch detaillierte Ansichten der Server und weiterer Komponenten an jedem Standort bereit.

Durch eine Ausführung des Planungstools werden Sie nicht auf eine spezifische Bereitstellung festgelegt, und es werden keinerlei Prozesse gestartet. Tatsächlich kann die Ausführung des Planungstools noch vor dem Ausarbeiten eines festen Plans sehr aufschlussreich sein, da die gestellten Fragen Sie darauf hinweisen, welche Punkte bei der Planung berücksichtigt werden müssen.

Sie können das Planungstool mehrfach ausführen, die Fragen auf unterschiedliche Weise beantworten und die Ergebnisse vergleichen. Wenn Sie einen für Ihre Anforderungen geeigneten Entwurf gefunden haben, jedoch noch Änderungen vornehmen möchten, können Sie zum Planungstool zurückkehren, den Entwurf laden und wie gewünscht ändern. Der einmalige Durchlauf des Planungstools dauert etwa 15 Minuten.

Wenn Sie mit dem Ergebnis zufrieden sind, können Sie mit dem Planungstool ein Diagramm der geplanten Bereitstellung erstellen. Dieses Diagramm können Sie beim Erstellen der Bereitstellung im Topologie-Generator verwenden.


> [!NOTE]
> Bei dem in dieser Version von Lync Server 2013 enthaltenen Planungstool handelt es sich um eine Vorabversion. Beachten Sie, dass die Kapazitätsplanungswerte im Planungstool vorläufig sind und nicht für die finale Version unterstützt werden.



## Lync Server-Topologie-Generator

Nachdem Sie den Bereitstellungsplan festgelegt haben, verwenden Sie den Topologie-Generator, um mit der Bereitstellung zu beginnen. Anschließend können Sie die Topologie mit dem Topologie-Generator überprüfen und die Topologie nach erfolgreicher Validierung veröffentlichen. Wenn Sie die Topologie veröffentlichen, stellt Lync Server die Topologie in den zentralen Verwaltungsspeicher ein. Falls dieser bei Veröffentlichung der Topologie noch nicht vorhanden ist, wird er zu diesem Zeitpunkt erstellt. Wenn Sie Lync Server auf jedem Server in Ihrer Bereitstellung installieren, liest der Server die Topologie aus dem zentralen Verwaltungsspeicher und installiert sich selbst, um seine Funktion gemäß Ihrer Bereitstellung zu übernehmen.

Wenn Sie mit Lync Server bereits umfassend vertraut sind und keine ausführliche Anleitung benötigen, können Sie das Planungstool überspringen und alternativ die Assistenten im Topologie-Generator für den anfänglichen Entwurf Ihrer Bereitstellung sowie zum Überprüfen und Veröffentlichen der Topologie verwenden.

Zum Planen und Veröffentlichen der Topologie ist der Topologie-Generator zwingend erforderlich. Sie können den Topologie-Generator nicht überspringen und Lync Server einzeln auf den Servern in Ihrer Bereitstellung installieren. Jeder Server muss die Konfigurationsdaten aus einer validierten, veröffentlichten Topologie im zentralen Verwaltungsspeicher lesen.

## Grundlegende Schritte bei der Planung

Es wird empfohlen, bei der Planung Ihrer Lync Server-Bereitstellung unter Verwendung der Dokumentation und des Planungstools die folgenden allgemeinen Schritte auszuführen.

1.  Falls Sie mit früheren Versionen von Lync Server vertraut sind, lesen Sie den Abschnitt [Neue Funktionen in Lync Server 2013](lync-server-2013-new-features.md), um sich mit den neuen Features und Anforderungen in Lync Server 2013 vertraut zu machen.

2.  Lesen Sie die weiteren Themen in diesem Abschnitt der Dokumentation: [Topologiegrundlagen, die Sie vor der Planung für Lync Server 2013 kennen sollten](lync-server-2013-topology-basics-you-must-know-before-planning.md), [Referenztopologien in Lync Server 2013](lync-server-2013-reference-topologies.md), [Anfängliche Planungsentscheidungen für Lync Server 2013](lync-server-2013-initial-planning-decisions.md) und [Clients für Lync Server 2013](lync-server-2013-clients.md). Beachten Sie die unter [Referenztopologien in Lync Server 2013](lync-server-2013-reference-topologies.md) beschriebenen Planungsentscheidungen.

3.  Nachdem Sie sich mit den Features von Lync Server vertraut gemacht haben und die Fragen kennen, die Sie sich stellen müssen, führen Sie erneut das Planungstool aus und sehen sich die generierte Topologie und die zugehörigen Details an. Stellen Sie sicher, dass die Topologie den speziellen Anforderungen Ihrer Organisation entspricht.

4.  Wenn Sie an bestimmten Arbeitsauslastungen oder Features besonders interessiert sind oder mehr darüber erfahren möchten, lesen Sie die entsprechenden Abschnitte unter [Planung](lync-server-2013-planning.md).

5.  Führen Sie nochmals das Planungstool aus. Sie können mit der in Schritt 3 erstellten Bereitstellung beginnen und die Ergebnisse ändern, oder Sie beginnen ganz von vorne.
    
    Führen Sie das Planungstool ggf. ein drittes Mal aus, und wiederholen Sie den Vorgang, bis Sie mit den Ergebnissen zufrieden sind.

6.  Wenn Sie den Topologieplan fertig gestellt haben, verwenden Sie das Planungstool zum Erstellen und Drucken eines Visio-Diagramms Ihrer Topologie. Diesen Ausdruck können Sie beim Arbeiten mit dem Topologie-Generator zur Eingabe Ihrer Topologie heranziehen.

7.  Lesen Sie vor Beginn der Bereitstellung die Abschnitte [Ermitteln Ihrer Systemanforderungen für Lync Server 2013](lync-server-2013-determining-your-system-requirements.md) und [Ermitteln Ihrer Infrastrukturanforderungen für Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md), um sich mit den Voraussetzungen und der erforderlichen Infrastruktur für Lync Server vertraut zu machen. Lesen Sie unter [Planung](lync-server-2013-planning.md) außerdem alle Abschnitte, die sich auf die Arbeitsauslastungen und Funktionen beziehen, die Sie bereitstellen möchten.

## Migration von früheren Versionen

Wenn Sie eine Migration von einer früheren Version zu Lync Server durchführen, lesen Sie die Dokumentation zur [Migration](migration.md), die genaue Anweisungen für Migration und Bereitstellung enthält.

