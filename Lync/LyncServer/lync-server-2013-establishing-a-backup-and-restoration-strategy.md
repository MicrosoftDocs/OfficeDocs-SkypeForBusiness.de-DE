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
ms.openlocfilehash: 5ee1a13667e28ad374f538d61f6cfd941d31fade
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a>Einrichten einer Sicherungs-und Wiederherstellungsstrategie für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-26_

Bevor Sie einen Sicherungs-und Wiederherstellungsplan für lync Server entwickeln können, müssen Sie eine Strategie entwickeln, die den Zielen Ihrer Organisation entspricht. Zur Entwicklung einer effektiven Sicherungs-und Wiederherstellungsstrategie müssen Sie Folgendes ausführen:

  - Unternehmensprioritäten festlegen

  - Ermitteln von Sicherungs-und Wiederherstellungsanforderungen

<div>

## <a name="establishing-business-priorities"></a>Einrichten von Unternehmensprioritäten

Bewerten Sie die geschäftlichen Prioritäten Ihrer Organisation. In der Regel sind die primären Unternehmensprioritäten, die sich auf Ihre Sicherungs-und Wiederherstellungsstrategie auswirken, wie folgt:

  - Business Continuity-Anforderungen

  - Datenvollständigkeit

  - Daten kritisch

  - Portabilitäts Anforderungen

  - Kosteneinschränkungen

Geschäftliche Anforderungen wie diese helfen bei der Bestimmung der Service Level Agreements (SLAs), die Sie mit ihren Kunden entwickeln. Service Level Agreements beeinflussen Ihre Sicherungs-und Wiederherstellungsstrategie erheblich.

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a>Identifizieren von Sicherungs-und Wiederherstellungsanforderungen

Ihre Geschäftsprioritäten und Service Level Agreements dienen dazu, die Anforderungen Ihrer Organisationen für das Sichern und Wiederherstellen von lync Server zu ermitteln. Ermitteln und dokumentieren Sie Ihre Anforderungen für Folgendes:

  - **Häufigkeit von Sicherungen**   Informationen zu den bewährten Methoden für die Sicherungshäufigkeit finden Sie unter [bewährte Methoden für die Sicherung und Wiederherstellung für lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).

  - **Zu den Sicherungs-und Wiederherstellungstools**   gehören die Personen, die die Tools verwenden sollen, und auf welchen Computern. Details zu den in diesem Thema und den erforderlichen Berechtigungen besprochenen Tools finden Sie unter [Sicherungs-und Wiederherstellungsanforderungen in lync Server 2013: Tools und Berechtigungen](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).

  - **Sicherungsspeicherort**   ermitteln Sie, ob die Sicherungen lokal oder Remote aufbewahrt werden, wobei Sicherheit und Barrierefreiheit berücksichtigt werden. Geben Sie das für die Sicherungen zu verwendende Medium an.

  - **Hardware-und Softwareanforderungen**   identifizieren und dokumentieren ihre spezifischen Hardware-und Softwareanforderungen, einschließlich Hardware für den Sicherungsspeicher und die Wiederherstellung bestimmter Komponenten sowie alle Software-und Netzwerkverbindungen, die für die Unterstützung von Backup und Wiederherstellung erforderlich sind. Berücksichtigen Sie bei der Entwicklung Ihrer Hardware-und Softwareanforderungen die verschiedenen Wiederherstellungsszenarien, die Folgen.

  - **Wiederherstellungsszenarien**   hier sind die Wiederherstellungsprozesse für die folgenden Szenarien:
    
      - Ein lync Server-Pool schlägt fehl. Für dieses Szenario muss jeder Server im Pool neu erstellt werden.
    
      - Ein Standard Edition-Server schlägt fehl. Für dieses Szenario muss der Server auf einem neuen oder sauberen Computer neu erstellt und Datenbanken wiederhergestellt werden.
    
      - Verlust des zentralen Verwaltungsspeichers. Dieses Szenario erfordert mindestens das Wiederherstellen und Veröffentlichen des zentralen Verwaltungsspeichers.
    
      - Verlust eines Back-End-Servers, wenn der zentrale Verwaltungsspeicher weiterhin normal funktioniert. Für dieses Szenario muss der Server auf einem neuen oder sauberen Computer neu erstellt und Datenbanken wiederhergestellt werden.
    
      - Ein Server, der Mitglied eines lync Server-Pools ist, schlägt fehl. Für dieses Szenario muss der Server auf einem neuen oder sauberen Computer neu erstellt werden.
    
      - Ein Dateispeicher schlägt fehl. Für dieses Szenario muss der Dateiserver oder der Dateicluster wiederhergestellt werden.
    
      - Eine Datenbank zum Archivieren, überwachen oder beständigen Chat schlägt fehl. Für dieses Szenario müssen die Datenbanken neu erstellt werden, und wenn die Daten für Ihre Organisation wichtig sind, müssen Sie die Daten wiederherstellen. Archivierungs-, Überwachungs-und beständige Chat Daten sind nicht erforderlich, um lync Server wieder in Betrieb zu nehmen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

