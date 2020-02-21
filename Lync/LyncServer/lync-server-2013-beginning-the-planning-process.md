---
title: 'Lync Server 2013: Starten des Planungsprozesses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Beginning the planning process
ms:assetid: df3722b3-f859-49e1-b3ff-ee6863483731
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398986(v=OCS.15)
ms:contentKeyID: 48185618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04bc27b965da5d4761e3283ea3106a8a3b90ebf8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="beginning-the-planning-process-for-lync-server-2013"></a>Beginnen des Planungsprozesses für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-24_

Während die Planung einer lokalen Unified Communications-Bereitstellung möglicherweise beängstigend wirkt, bietet lync Server zwei wertvolle Tools, die Ihnen helfen:

  - Bei **dem Planungs Tool** handelt es sich um einen Assistenten, der eine Reihe von Fragen zu Ihrer Organisation, zu den lync Server Funktionen, die Sie aktivieren möchten, und den Anforderungen an die Kapazitätsplanung stellt. Basierend auf Ihren Antworten erstellt das Tool eine empfohlene Bereitstellungstopologie und generiert ein Microsoft Visio-Diagramm dieser Bereitstellung.

  - Der **Topologie-Generator** ist eine Installationskomponente von lync Server. Verwenden Sie den Topologie-Generator, um die geplante Topologie zu erstellen, anzupassen und zu veröffentlichen. Darüber hinaus überprüft der Topologie-Generator Ihre Topologie, bevor Sie mit den Serverinstallationen beginnen. Wenn Sie lync Server auf einzelnen Servern installieren, lesen die Server die veröffentlichte Topologie als Teil des Installationsvorgangs, und das Installationsprogramm stellt den Server wie in der Topologie weitergeleitet bereit.

<div>

## <a name="lync-server-planning-tool"></a>Lync Server Planungs Tool

Das Planungstool verwendet Ihre Antworten auf die Fragen im Tool und generiert eine Topologie basierend auf lync Server Richtlinien und bewährten Methoden. Auf Grundlage Ihrer Antworten bietet das Planungstool zudem verschiedene Ansichten einer Bereitstellung. Es stellt sowohl eine globale Ansicht aller Standorte (einschließlich der zentralen Standorte und Zweigstellen) als auch detaillierte Ansichten der Server und weiterer Komponenten an jedem Standort bereit.

Durch das Ausführen des Planungstools werden Sie nicht zu einer bestimmten Bereitstellung verpflichtet oder keine Prozesse initiieren. Tatsächlich kann das Ausführen des Planungstools noch bevor Sie einen festen Plan im Hinterkopf haben, eine sehr lehrreiche Möglichkeit sein, sich mit den Fragen vertraut zu machen, die Sie in Ihrem Planungsprozess überdenken müssen.

Sie können das Planungs Tool mehrmals ausführen, Fragen anders beantworten und die Ergebnisse vergleichen. Wenn Sie über einen Entwurf verfügen, mit dem Sie überwiegend zufrieden sind, an dem Sie jedoch Änderungen vornehmen müssen, können Sie zum Planungs Tool zurückkehren, den Entwurf laden und die Änderungen vornehmen. Es dauert ungefähr 15 Minuten, bis Sie das Planungs Tool einmal abgeschlossen haben.

Nachdem Sie zufrieden sind, können Sie das Planungs Tool verwenden, um ein Diagramm Ihrer geplanten Bereitstellung zu erstellen. Sie können dieses Diagramm beim Erstellen der Bereitstellung im Topologie-Generator verwenden.

<div>


> [!NOTE]  
> Das in dieser Version von lync Server 2013 enthaltene Planungs Tool ist eine Vorabversion. Beachten Sie, dass die Kapazitätsplanungswerte im Planungstool vorläufig sind und nicht für die finale Version unterstützt werden.



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a>Lync Server Topologie-Generator

Nachdem Sie sich für den Bereitstellungsplan entschieden haben, verwenden Sie den Topologie-Generator, um mit der Bereitstellung zu beginnen. Wenn Sie fertig sind, verwenden Sie den Topologie-Generator, um die Topologie zu überprüfen, und wenn Sie dann übergeben wird, können Sie die Topologie veröffentlichen. Wenn Sie die Topologie veröffentlichen, stellt lync Server die Topologie in den zentralen Verwaltungsspeicher, der zu diesem Zeitpunkt erstellt wird, wenn er noch nicht vorhanden ist. Wenn Sie lync Server auf jedem Server in Ihrer Bereitstellung installieren, liest der Server die Topologie aus dem zentralen Verwaltungsspeicher und installiert sich selbst so, dass Sie in ihre Rolle in Ihrer Bereitstellung passt.

Alternativ können Sie, wenn Sie mit lync Server sehr vertraut sind und eine geringere normative Anleitung benötigen, das Planungs Tool überspringen und die Assistenten im Topologie-Generator für den ersten Entwurf Ihrer Bereitstellung und auch für die Schritte zur Validierung und Veröffentlichung verwenden.

Die Planung und Veröffentlichung einer Topologie mithilfe des Topologie-Generators ist ein erforderlicher Schritt. Sie können den Topologie-Generator nicht umgehen und lync Server einzeln auf den Servern in Ihrer Bereitstellung installieren. Jeder Server muss die Topologie aus einer validierten, veröffentlichten Topologie im zentralen Verwaltungsspeicher lesen.

</div>

<div>

## <a name="high-level-planning-process"></a>Grundlegende Schritte bei der Planung

Wir empfehlen den folgenden allgemeinen Prozess für die Verwendung der Dokumentation und des Planungstools, um Ihre lync Server-Bereitstellung zu planen.

1.  Wenn Sie mit früheren Versionen von lync Server vertraut sind, lesen Sie [neue Features in lync Server 2013](lync-server-2013-new-features.md) , um sich mit den neuen Features und Anforderungen in lync Server 2013 vertraut zu machen.

2.  Lesen Sie die anderen Themen in diesem Abschnitt der Dokumentation: [Grundlagen der Topologie, die Sie vor der Planung von lync Server 2013 kennen müssen](lync-server-2013-topology-basics-you-must-know-before-planning.md), [Referenz Topologien in lync Server 2013](lync-server-2013-reference-topologies.md), [anfängliche Planungsentscheidungen für lync Server 2013](lync-server-2013-initial-planning-decisions.md)und [Clients für lync Server 2013](lync-server-2013-clients.md). Beachten Sie die Planungsentscheidungen, die in [Referenz Topologien in lync Server 2013](lync-server-2013-reference-topologies.md)dargestellt werden.

3.  Nachdem Sie sich mit lync Server Features und den Fragen, die beantwortet werden müssen, vertraut gemacht haben, führen Sie das Planungs Tool aus, und zeigen Sie die sich ergebende Topologie und deren Details an. Stellen Sie sicher, dass die Topologie den speziellen Anforderungen Ihrer Organisation entspricht.

4.  Wenn es bestimmte Arbeitslasten oder Features gibt, an denen Sie interessiert sind oder die Sie kennen müssen, lesen Sie die entsprechenden Abschnitte der [Planung für lync Server 2013](lync-server-2013-planning.md).

5.  Führen Sie das Planungs Tool erneut aus. Sie können mit der in Schritt 3 erstellten Bereitstellung beginnen und die Ergebnisse ändern, oder Sie beginnen ganz von vorne.
    
    Führen Sie bei Bedarf das Planungs Tool ein drittes Mal aus, und wiederholen Sie den Vorgang, bis Sie mit der Ausgabe zufrieden sind.

6.  Wenn Sie den Topologieplan abgeschlossen haben, verwenden Sie das Planungs Tool, um ein Visio-Diagramm Ihrer Topologie zu erstellen und zu drucken. Sie können diesen Ausdruck beim Arbeiten mit dem Topologie-Generator verwenden, um Ihre Topologie einzugeben.

7.  Bevor Sie mit der Bereitstellung beginnen, lesen Sie [Ermitteln der Systemanforderungen für lync Server 2013](lync-server-2013-determining-your-system-requirements.md) und [bestimmen der Infrastrukturanforderungen für lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) , um sich mit den Voraussetzungen und der erforderlichen Infrastruktur für lync Server vertraut zu machen. Stellen Sie außerdem sicher, dass Sie alle Abschnitte der [Planung für lync Server 2013](lync-server-2013-planning.md) gelesen haben, die für die Arbeitsauslastungen und Features gelten, die Sie bereitstellen möchten.

</div>

<div>

## <a name="migrating-from-previous-versions"></a>Migration von früheren Versionen

Wenn Sie zu lync Server einer früheren Version migrieren, finden Sie in der [Migrations](migration.md) Dokumentation spezifische Anweisungen für die Migration und Bereitstellung.

</div>

</div>

<span> </span>

</div>

</div>

</div>

