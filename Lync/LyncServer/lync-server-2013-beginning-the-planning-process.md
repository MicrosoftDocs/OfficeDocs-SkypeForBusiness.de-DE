---
title: 'Lync Server 2013: Beginnen des Planungsprozesses'
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
ms.openlocfilehash: a9da1c5535f190a6f57aa76b78a04845d4a073e2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="beginning-the-planning-process-for-lync-server-2013"></a>Beginnen des Planungsprozesses für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-24_

Bei der Planung einer lokalen Unified Communications-Bereitstellung mag Einschüchterungen auftreten, lync Server bietet zwei nützliche Tools, die Ihnen helfen können:

  - **Das Planungs Tool** ist ein Assistent, der eine Reihe von Fragen zu Ihrer Organisation, zu den lync-Server Features, die Sie aktivieren möchten, und Ihren Anforderungen an die Kapazitätsplanung stellt. Anschließend erstellt Sie eine empfohlene Bereitstellungstopologie auf der Grundlage ihrer Antworten und erstellt ein Microsoft Visio-Diagramm dieser Bereitstellung.

  - Der **Topologie-Generator** ist eine Installationskomponente von lync Server. Sie verwenden den Topologie-Generator zum Erstellen, anpassen und Veröffentlichen Ihrer geplanten Topologie. Darüber hinaus wird Ihre Topologie überprüft, bevor Sie mit Server Installationen beginnen. Wenn Sie lync Server auf einzelnen Servern installieren, lesen die Server die veröffentlichte Topologie als Teil des Installationsvorgangs, und das Installationsprogramm stellt den Server in der Topologie bereit.

<div>

## <a name="lync-server-planning-tool"></a>Lync Server-Planungs Tool

Das Planungstool nimmt Ihre Antworten auf die Fragen im Tool auf und generiert eine Topologie basierend auf den Richtlinien und bewährten Methoden von lync Server. Darüber hinaus werden auf Grundlage ihrer Antworten mehrere Ansichten einer Bereitstellung bereitgestellt. Sie zeigt sowohl eine globale Ansicht aller Ihrer Websites (also sowohl zentrale Websites als auch Zweigstellenstandorte) sowie detaillierte Ansichten mit den Servern und anderen Komponenten an den einzelnen Standorten.

Durch Ausführen des Planungstools werden Sie nicht zu einer bestimmten Bereitstellung oder zum Initiieren von Prozessen verpflichtet. Das Ausführen des Planungstools, bevor Sie einen festen Plan haben, kann in der Tat eine sehr lehrreiche Möglichkeit sein, die Art der Fragen zu verstehen, die Sie in Ihrem Planungsprozess berücksichtigen müssen.

Sie können das Planungs Tool mehrmals ausführen, Fragen anders beantworten und die Ergebnisse vergleichen. Wenn Sie über ein Design verfügen, mit dem Sie überwiegend zufrieden sind, aber Änderungen vornehmen müssen, können Sie zum Planungs Tool zurückkehren, das Design laden und die Änderungen vornehmen. Es dauert etwa 15 Minuten, bis das Planungs Tool einmal abgeschlossen ist.

Nachdem Sie zufrieden sind, können Sie das Planungs Tool verwenden, um ein Diagramm Ihrer geplanten Bereitstellung zu erstellen. Sie können dieses Diagramm verwenden, während Sie die Bereitstellung im Topologie-Generator erstellen.

<div>


> [!NOTE]  
> Das in dieser Version von lync Server 2013 enthaltene Planungs Tool ist eine Vorabversion. Beachten Sie, dass die Kapazitätsplanungswerte im Planungstool vorläufig sind und nicht für die finale Version unterstützt werden.



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a>Lync Server Topology Builder

Nachdem Sie sich für Ihren Bereitstellungsplan entschieden haben, verwenden Sie den Topologie-Generator, um mit der Bereitstellung zu beginnen. Wenn Sie den Vorgang beenden, verwenden Sie den Topologie-Generator, um die Topologie zu überprüfen, und wenn Sie erfolgreich ist, können Sie die Topologie veröffentlichen. Wenn Sie die Topologie veröffentlichen, platziert lync Server die Topologie in den zentralen Verwaltungsspeicher, der zu diesem Zeitpunkt erstellt wird, wenn er noch nicht vorhanden ist. Wenn Sie lync Server auf jedem Server in Ihrer Bereitstellung installieren, liest der Server die Topologie aus dem zentralen Verwaltungsspeicher und installiert sich selbst, damit er in ihre Rolle in Ihrer Bereitstellung passt.

Wenn Sie mit lync Server sehr vertraut sind und eine geringere normative Anleitung benötigen, können Sie das Planungs Tool überspringen und die Assistenten im Topologie-Generator verwenden, um den anfänglichen Entwurf Ihrer Bereitstellung und auch die Schritte für die Validierung und Veröffentlichung zu verwenden.

Die Verwendung des Topologie-Generators zum Planen und Veröffentlichen einer Topologie ist ein erforderlicher Schritt. Sie können den Topologie-Generator nicht umgehen und lync Server auf den Servern in Ihrer Bereitstellung einzeln installieren. Jeder Server muss die Topologie aus einer validierten, veröffentlichten Topologie im zentralen Verwaltungsspeicher lesen.

</div>

<div>

## <a name="high-level-planning-process"></a>Planungsprozess auf oberster Ebene

Wir empfehlen die folgenden allgemeinen Verfahren für die Verwendung der Dokumentation und des Planungstools zum Planen Ihrer lync Server-Bereitstellung.

1.  Wenn Sie mit früheren Versionen von lync Server vertraut sind, lesen Sie [neue Features in lync Server 2013](lync-server-2013-new-features.md) , um sich mit den neuen Features und Anforderungen in lync Server 2013 vertraut zu machen.

2.  Lesen Sie die anderen Themen in diesem Abschnitt der Dokumentation: [Topologie-Grundlagen, die Sie kennen müssen, bevor Sie lync Server 2013 planen](lync-server-2013-topology-basics-you-must-know-before-planning.md), [Referenz Topologien in lync Server 2013](lync-server-2013-reference-topologies.md), [erste Planungsentscheidungen für lync Server 2013](lync-server-2013-initial-planning-decisions.md)und [Clients für lync Server 2013](lync-server-2013-clients.md). Beachten Sie die Planungsentscheidungen, die in [Referenz Topologien in lync Server 2013](lync-server-2013-reference-topologies.md)dargestellt werden.

3.  Nachdem Sie sich nun mit den lync Server-Features und den Arten von Fragen vertraut gemacht haben, die beantwortet werden müssen, führen Sie das Planungs Tool aus, und zeigen Sie die resultierende Topologie und deren Details an. Stellen Sie sicher, dass die Topologie den eindeutigen Anforderungen für Ihre Organisation entspricht.

4.  Wenn es bestimmte Arbeitsauslastungen oder Features gibt, an denen Sie interessiert sind oder die Sie kennen müssen, lesen Sie die entsprechenden Abschnitte der [Planung für lync Server 2013](lync-server-2013-planning.md).

5.  Führen Sie das Planungs Tool erneut aus. Sie können mit der Bereitstellung beginnen, die Sie in Schritt 3 erstellt haben, und die Ergebnisse ändern oder von vorn beginnen.
    
    Führen Sie bei Bedarf das Planungs Tool ein drittes Mal aus, und wiederholen Sie den Vorgang, bis Sie mit der Ausgabe zufrieden sind.

6.  Wenn Sie den Topologieplan abgeschlossen haben, verwenden Sie das Planungs Tool zum Erstellen und Drucken eines Visio-Diagramms Ihrer Topologie. Sie können diesen Ausdruck während der Arbeit mit dem Topologie-Generator verwenden, um Ihre Topologie einzugeben.

7.  Bevor Sie mit der Bereitstellung beginnen, lesen Sie [Ermitteln der Systemanforderungen für lync Server 2013](lync-server-2013-determining-your-system-requirements.md) und [Ermitteln der Infrastrukturanforderungen für lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) , um sich mit den Voraussetzungen und der erforderlichen Infrastruktur für lync Server vertraut zu machen. Stellen Sie außerdem sicher, dass Sie alle Abschnitte der [Planning für lync Server 2013](lync-server-2013-planning.md) gelesen haben, die für die Arbeitslasten und Features gelten, die Sie bereitstellen möchten.

</div>

<div>

## <a name="migrating-from-previous-versions"></a>Migrieren von vorherigen Versionen

Wenn Sie von einer früheren Version zu lync Server migrieren, finden Sie in der [Migrations](migration.md) Dokumentation spezifische Anweisungen für Ihre Migration und Bereitstellung.

</div>

</div>

<span> </span>

</div>

</div>

</div>

