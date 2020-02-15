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
ms.openlocfilehash: 74aec0a6fe0edc288dfaae57a146c52cf9a0babe
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037113"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a>Planen der Notfallwiederherstellung für das Parken von Anrufen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-30_

In diesem Abschnitt werden einige Möglichkeiten beschrieben, wie Sie die Anwendung zum Parken von Anrufen für die Notfallwiederherstellung und einige Überlegungen für den Notfall Wiederherstellungsprozess vorbereiten.

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a>Vorbereiten der Notfallwiederherstellung für das Parken von Anrufen

Beachten Sie bei der Vorbereitung und Durchführung von Notfallwiederherstellungsverfahren Folgendes.

  - Planen Sie die Notfallwiederherstellung gleichzeitig mit der Kapazitätsplanung. Für die Notfall Wiederherstellungs Kapazität sollte jeder Pool in einem gekoppelten Pool in der Lage sein, die Arbeitslasten der Dienste zum Parken von Anrufen in beiden Pools zu verarbeiten. Ausführliche Informationen zur Kapazitätsplanung für das Parken von Anrufen finden Sie unter [Kapazitätsplanung für das Parken von Anrufen in lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).

  - Während der Notfallwiederherstellung verwenden Benutzer, die im Rahmen des Failovers an den Sicherungspool umgeleitet wurden, den Dienst zum Parken von anrufen, der im Sicherungspool ausgeführt wird. Unterstützung für das Parken von Anrufen während der Notfallwiederherstellung erfordert daher, dass die Anwendung zum Parken von Anrufen sowohl im primären Pool als auch im Sicherungspool bereitgestellt und aktiviert wird.

  - Jeder Pool muss über einen gültigen Bereich von Orbit-Nummern für Benutzer verfügen, die in diesem Pool verwaltet werden und für das Parken von Anrufen verwendet werden.

  - Halten Sie immer eine separate Sicherungskopie aller benutzerdefinierten Wartemusik, die für das Parken von Anrufen hochgeladen wurde. Diese Dateien werden nicht als Teil des lync Server 2013 Notfall Wiederherstellungsprozesses gesichert und gehen verloren, wenn die in den Pool hochgeladenen Dateien beschädigt, beschädigt oder gelöscht werden.

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a>Überlegungen zur Notfallwiederherstellung beim Parken von Anrufen

Sie können nur eine Gruppe von Anwendung zum Parken von Anrufen Konfigurationseinstellungen und eine benutzerdefinierte Audiodatei pro Pool definieren. Zu diesen Einstellungen gehören der Schwellenwert für Timeout, Wartemusik, maximale Anzahl von Anruf Angriffen und Timeout-URI. Führen Sie das Cmdlet **Get-CsCpsConfiguration** aus, um diese Konfigurationseinstellungen anzuzeigen. Ausführliche Informationen zum Cmdlet **Get-CsCpsConfiguration** finden Sie unter [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).

Während der Notfallwiederherstellung verwendet das Parken von Anrufen die Anwendung zum Parken von Anrufen im Sicherungspool, daher werden Einstellungen im primären Pool nicht gesichert. Wenn der primäre Pool nicht wiederhergestellt werden kann und Sie einen neuen Pool zum Ersetzen des primären Pools bereitstellen, gehen die Einstellungen aus dem primären Pool verloren, und Sie müssen die Einstellungen für das Parken von Anrufen und alle angepassten Musikdateien im neuen Pool neu konfigurieren.

Wenn Sie einen neuen Pool mit einem anderen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) bereitstellen, um den primären Pool zu ersetzen, müssen Sie alle Bereiche des Orbits für das Parken von anrufen, die dem primären Pool zugeordnet sind, dem FQDN des neuen Pools zuweisen. Um orbitbereiche erneut dem neuen Pool zuzuweisen, können Sie entweder lync Server-Systemsteuerung oder das Cmdlet " **Sets-CsCallParkOrbit** " verwenden. Ausführliche Informationen zum Cmdlet " **CsCallParkOrbit** " finden Sie unter [festlegen-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).

</div>

</div>

<span> </span>

</div>

</div>

</div>

