---
title: 'Lync Server 2013: Übersicht über das Parken von Anrufen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Call Park
ms:assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205124(v=OCS.15)
ms:contentKeyID: 48184939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acb507ddf7fc47714781e83da0fa77d093f193c0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153265"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-call-park-in-lync-server-2013"></a>Übersicht über das Parken von Anrufen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-29_

Im lync Server 2013 Anwendung zum Parken von anrufen können Enterprise-VoIP-Benutzer eine der folgenden Aktionen ausführen:

  - Halten Sie einen Anruf gedrückt, und rufen Sie dann den Anruf vom gleichen Telefon oder von einem anderen Telefon ab.

  - Halten Sie einen Anruf an, um ihn an eine Abteilung oder einen allgemeinen Bereich zu übertragen (beispielsweise an eine Vertriebsabteilung oder an ein Warehouse, in dem ein Telefon für gemeinsame Bereiche vorhanden ist).

  - Halten Sie einen Anruf gedrückt, und halten Sie das ursprüngliche Anrufbeantworter für andere Anrufe frei.

Wenn ein Benutzer einen Anruf parkt, übergibt lync Server den Anruf an eine temporäre Nummer, die als *Orbit*bezeichnet wird, wobei der Anruf angehalten wird, bis er abgerufen wird oder ein Timeout auftritt. Lync Server sendet den Orbit an den Benutzer, der den Anruf geparkt hat. Zum Abrufen des geparkten Anrufs kann der Benutzer die Umlaufbahn Nummer wählen oder im Unterhaltungsfenster auf den Orbit-Link oder die Orbit-Schaltfläche klicken.

Der Benutzer, der einen Anruf geparkt hat, kann eine Person Benachrichtigen, um den Anruf mithilfe eines externen Mechanismus, beispielsweise Instant Messaging (Sofortnachrichten) oder eines Auslagerungs Systems, abzurufen, um die orbitnummer an eine andere Person zu übermitteln. Der Benutzer, der den Anruf geparkt hat, kann das Unterhaltungsfenster geöffnet lassen, um eine Benachrichtigung zu erhalten, wenn der Anruf abgerufen wird.

Da Umlaufbahn Bereiche global eindeutig sind, können Anrufe von beliebigen lync Server Standort-oder PBX-Telefonen abgerufen werden, wenn das Routing entsprechend konfiguriert ist. Wenn der Anruf nicht innerhalb einer konfigurierbaren Zeitspanne abgerufen wird, klingelt der Anruf an die Person zurück, die ihn geparkt hat. Wenn diese Person den Rückruf nicht beantwortet, wird der Anruf an ein Fallback-Ziel, beispielsweise an einen Operator, übertragen, falls dies konfiguriert ist. Sie können konfigurieren, wie oft der Anruf klingelt, bevor er von ein bis zehn Mal übertragen wird. Wenn niemand einen übertragenen Anruf beantwortet, wird der Anruf getrennt. Die Umlaufbahn wird freigegeben, wenn der Anruf abgerufen oder getrennt wird.

Wenn Sie das Parken von Anrufen bereitstellen, müssen Sie Bereiche für Durchwahlnummern für das Parken von Anrufen reservieren. Diese Erweiterungen müssen virtuelle Erweiterungen sein: Erweiterungen, denen kein Benutzer oder Telefon zugewiesen ist. Anschließend konfigurieren Sie die Orbit-Tabelle für das Parken von Anrufen mit den Bereichen der Durchwahlnummern und geben an, welche Anwendungsdienst die Anwendung zum Parken von Anrufen hostet, die die einzelnen Bereiche behandelt. Jeder Front-End-Pool verfügt auf dem entsprechenden Back-End-Server über eine Parken-Tabelle, die zum Verwalten von Anrufen verwendet wird, die im Pool geparkt sind. Die Liste der orbitbereiche wird im zentralen Verwaltungsspeicher gespeichert und zum Weiterleiten von Umlaufbahnen zum Ziel Pool verwendet. Jeder lync Server Pool, in dem die Anwendung zum Parken von Anrufen bereitgestellt und konfiguriert ist, kann einen oder mehrere Umlaufbahn Bereiche aufweisen. Umlaufbahn Bereiche müssen in der lync Server-Bereitstellung global eindeutig sein.

Sie können auch andere Einstellungen für das Parken von anrufen konfigurieren, beispielsweise, wo Anrufe umgeleitet werden, wenn ein Timeout auftritt und ob die Person auf dem Telefon Musik hört, während Sie geparkt hat. Sie können auch die Musikdatei angeben, die wiedergegeben werden soll, während der Anruf gespeichert wird.

<div>


> [!NOTE]  
> Benutzerdefinierte Musik-on-Hold-Dateien für das Parken von Anrufen werden nicht als Teil des lync Server 2013 Notfall Wiederherstellungsprozesses gesichert und gehen verloren, wenn die in den Pool hochgeladenen Dateien beschädigt, beschädigt oder gelöscht werden. Bewahren Sie immer eine separate Sicherungskopie der angepassten Musikdateien auf, die Sie für das Parken von Anrufen hochgeladen haben.



</div>

Die Anwendung zum Parken von anrufen ist eine Komponente von Enterprise-VoIP. Wenn Sie Enterprise-VoIP bereitstellen, wird das Anwendung zum Parken von Anrufen automatisch installiert und aktiviert. Bevor Sie das Parken von Anrufen verwenden können, muss der Enterprise-VoIP-Administrator es jedoch konfigurieren und für Benutzer über VoIP-Richtlinie aktivieren.

</div>

<span> </span>

</div>

</div>

</div>

