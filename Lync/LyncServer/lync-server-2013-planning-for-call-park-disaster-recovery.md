---
title: 'Lync Server 2013: Planen der Notfallwiederherstellung für das Parken von Anrufen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Call Park disaster recovery
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205395(v=OCS.15)
ms:contentKeyID: 48185867
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a76052297e527e24fd3daf0c03d02661c7ddc255
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41754455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a>Planen der Notfallwiederherstellung für das Parken von Anrufen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-30_

In diesem Abschnitt werden einige Möglichkeiten beschrieben, wie Sie die Anwendung für den Parken von Anrufen für die Disaster Recovery und einige Überlegungen für den Disaster Recovery-Prozess vorbereiten.

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a>Vorbereiten der Disaster Recovery für den Anruf Park

Beachten Sie bei der Vorbereitung und Durchführung von Disaster Recovery-Verfahren Folgendes:

  - Planen Sie die Disaster Recovery, wenn Sie Ihre Kapazitätsplanung durchführen. Für die Disaster Recovery-Kapazität sollte jeder Pool in einem gekoppelten Pool in der Lage sein, die Arbeitslasten der Anruf Park Dienste in beiden Pools zu bewältigen. Details zur Kapazitätsplanung des Anruf Parks finden Sie unter [Kapazitätsplanung für den Parken von Anrufen in lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).

  - Während der Disaster Recovery verwenden Benutzer, die im Rahmen des Failovers an den Sicherungspool umgeleitet wurden, den Anruf Park Dienst, der im Sicherungspool ausgeführt wird. Daher erfordert die Unterstützung für den Parken von Anrufen während der Disaster Recovery, dass die Anwendung für den Parken von Anrufen sowohl im primären Pool als auch im Sicherungspool bereitgestellt und aktiviert wird.

  - Jeder Pool muss über einen gültigen Bereich von Orbit-Nummern für Benutzer verfügen, die in diesem Pool verwaltet werden, um Sie für Park Anrufe zu verwenden.

  - Bewahren Sie immer eine separate Sicherungskopie jeder angepassten Musik auf, die für den Anruf Park hochgeladen wurde. Diese Dateien werden im Rahmen des lync Server 2013-Wiederherstellungsprozesses nicht gesichert und gehen verloren, wenn die Dateien, die in den Pool hochgeladen wurden, beschädigt, beschädigt oder gelöscht wurden.

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a>Überlegungen zur Disaster Recovery in Park anrufen

Pro Pool können Sie nur einen Satz von Einstellungen für die Anwendungskonfiguration des Anruf Parks und eine angepasste Musik-zu-halten-Audiodatei definieren. Zu diesen Einstellungen gehören der Schwellenwert für Timeout, Musik in Wartestellung, maximale Anruf Abzugs Versuche und Timeout-URI. Führen Sie das Cmdlet " **Get-CsCpsConfiguration** " aus, um diese Konfigurationseinstellungen anzuzeigen. Details zum Cmdlet **Get-CsCpsConfiguration** finden Sie unter [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).

Bei der Wiederherstellung des Notfalls verwendet Call Park die Anwendung "Parken" im Backup-Pool, sodass die Einstellungen im primären Pool nicht gesichert werden. Wenn der primäre Pool nicht wiederhergestellt werden kann und Sie einen neuen Pool zum Ersetzen des primären Pools bereitstellen, gehen die Einstellungen des primären Pools verloren, und Sie müssen die Einstellungen für den Anruf Park und alle angepassten Music-on-halten-Audiodateien im neuen Pool neu konfigurieren.

Wenn Sie einen neuen Pool mit einem anderen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) bereitstellen, um den primären Pool zu ersetzen, müssen Sie dem FQDN des neuen Pools alle orbitbereiche für den Anruf Bereich zuweisen, die dem primären Pool zugeordnet waren. Wenn Sie dem neuen Pool Umlaufbahn Bereiche erneut zuweisen möchten, können Sie entweder die lync Server-Systemsteuerung oder das Cmdlet " **Satz-CsCallParkOrbit** " verwenden. Details zum Cmdlet " **setCsCallParkOrbit** " finden Sie unter [Satz-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).

</div>

</div>

<span> </span>

</div>

</div>

</div>

