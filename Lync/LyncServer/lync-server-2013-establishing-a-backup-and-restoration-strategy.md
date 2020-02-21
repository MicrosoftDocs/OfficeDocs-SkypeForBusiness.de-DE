---
title: 'Lync Server 2013: Einrichten einer Sicherungs-und Wiederherstellungsstrategie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration strategy
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202195(v=OCS.15)
ms:contentKeyID: 51541532
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a65dd081cacd9952ce1b9a7f0917209532a28cf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204791"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a>Einrichten einer Sicherungs-und Wiederherstellungsstrategie für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-26_

Bevor Sie einen Sicherungs-und Wiederherstellungsplan für lync Server entwickeln können, müssen Sie eine Strategie entwickeln, die in die Ziele Ihrer Organisation passt. Um eine effektive Sicherungs-und Wiederherstellungsstrategie zu entwickeln, müssen Sie Folgendes tun:

  - Festlegen von Geschäftsprioritäten

  - Ermitteln der Sicherungs-und Wiederherstellungsanforderungen

<div>

## <a name="establishing-business-priorities"></a>Einrichten von Geschäftsprioritäten

Bewerten Sie die geschäftlichen Prioritäten Ihrer Organisation. Normalerweise sind die folgenden primären Geschäftsprioritäten für Ihre Sicherungs-und Wiederherstellungsstrategie relevant:

  - Anforderungen an die Geschäftskontinuität

  - Datenvollständigkeit

  - Daten kritisch

  - Portabilitäts Anforderungen

  - Kosteneinschränkungen

Geschäftliche Anforderungen wie diese helfen bei der Bestimmung der Vereinbarungen zum Service Level (Service Level Agreements, SLAs), die Sie mit ihren Kunden entwickeln. Vereinbarungen zum Service Level beeinflussen die Sicherungs-und Wiederherstellungsstrategie stark.

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a>Identifizieren der Sicherungs-und Wiederherstellungsanforderungen

Ihre geschäftlichen Prioritäten und Vereinbarungen zum Service Level dienen der Bestimmung der Anforderungen Ihrer Organisation zum Sichern und Wiederherstellen von lync Server. Identifizieren und dokumentieren Sie Ihre Anforderungen für Folgendes:

  - **Häufigkeit von Sicherungen**   ausführliche Informationen zu bewährten Methoden für die Sicherungshäufigkeit finden Sie unter [bewährte Methoden für die Sicherung und Wiederherstellung für lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).

  - **Zu den Sicherungs-und Wiederherstellungstools**   gehören die Benutzer, die die Tools verwenden sollen, und auf welchen Computern. Ausführliche Informationen zu den in diesem Thema und den erforderlichen Berechtigungen beschriebenen Tools finden Sie unter [Sicherungs-und Wiederherstellungsanforderungen in lync Server 2013: Tools and Permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).

  - **Sicherungsspeicherort**   ermitteln Sie, ob die Sicherungen lokal oder Remote aufbewahrt werden, wobei Sicherheit und Barrierefreiheit berücksichtigt werden. Geben Sie die Medien an, die für die Sicherungen verwendet werden sollen.

  - **Hardware-und Softwareanforderungen**   identifizieren und dokumentieren ihre spezifischen Hardware-und Softwareanforderungen, einschließlich der Hardware für den Sicherungsspeicher und der Wiederherstellung bestimmter Komponenten sowie der erforderlichen Software-und Netzwerkkonnektivität zur Unterstützung von Sicherung und Wiederherstellung. Beachten Sie bei der Entwicklung Ihrer Hardware-und Softwareanforderungen die verschiedenen Wiederherstellungsszenarien, die befolgt werden.

  - **Wiederherstellungsszenarien**   sind hier die Wiederherstellungsprozesse für die folgenden Szenarien:
    
      - Ein lync Server Pool schlägt fehl. In diesem Szenario ist es erforderlich, jeden Server im Pool neu zu erstellen.
    
      - Ein Standard Edition-Server schlägt fehl. In diesem Szenario ist es erforderlich, den Server auf einem neuen oder sauberen Computer neu zu erstellen und Datenbanken wiederherzustellen.
    
      - Verlust des zentralen Verwaltungsspeichers. Dieses Szenario erfordert mindestens die Wiederherstellung und Veröffentlichung des zentralen Verwaltungsspeichers.
    
      - Verlust eines Back-End-Servers, wenn der zentrale Verwaltungsspeicher noch normal funktioniert. In diesem Szenario ist es erforderlich, den Server auf einem neuen oder sauberen Computer neu zu erstellen und Datenbanken wiederherzustellen.
    
      - Ein Server, der Mitglied eines lync Server Pools ist, schlägt fehl. In diesem Szenario ist es erforderlich, den Server auf einem neuen oder sauberen Computer neu zu erstellen.
    
      - Ein Dateispeicher schlägt fehl. In diesem Szenario muss der Dateiserver oder der Dateicluster wiederhergestellt werden.
    
      - Eine Datenbank für Archivierung, Überwachung oder beständigen Chat schlägt fehl. Dieses Szenario erfordert das Neuerstellen der Datenbanken und, wenn die Daten für Ihre Organisation wichtig sind, die Wiederherstellung der Daten. Das Archivieren, überwachen und beständigen Chat Daten ist nicht erforderlich, um lync Server Sicherung und Ausführung zu erhalten.

</div>

</div>

<span> </span>

</div>

</div>

</div>

