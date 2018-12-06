---
title: 'Lync Server 2013: Planen der Notfallwiederherstellung für das Parken von Anrufen'
TOCTitle: Planen der Notfallwiederherstellung für das Parken von Anrufen
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205395(v=OCS.15)
ms:contentKeyID: 49295945
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planen der Notfallwiederherstellung für das Parken von Anrufen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-30_

In diesem Abschnitt werden einige Möglichkeiten beschrieben, wie Sie die Anwendung zum Parken von Anrufen für die Notfallwiederherstellung vorbereiten können. Außerdem werden Überlegungen zum Prozess der Notfallwiederherstellung geschildert.

## Vorbereiten der Anwendung zum Parken von Anrufen für die Notfallwiederherstellung

Beachten Sie die folgenden Hinweise, wenn Sie Verfahren für die Notfallwiederherstellung vorbereiten und durchführen.

  - Planen Sie für die Notfallwiederherstellung bereits dann voraus, wenn Sie die Kapazitätsplanung vornehmen. Was die Kapazität für die Notfallwiederherstellung betrifft, so sollte jeder Pool in einem Poolpaar in der Lage sein, die Arbeitslasten der Dienste der Anwendung zum Parken von Anrufen in beiden Pools zu verarbeiten. Ausführliche Informationen zur Kapazitätsplanung für das Parken von Anrufen finden Sie unter [Kapazitätsplanung für das Parken von Anrufen in Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).

  - Während der Notfallwiederherstellung verwenden Benutzer, die im Rahmen des Failoverprozesses in den Sicherungspool umgeleitet worden sind, den Dienst zum Parken von Anrufen, der im Sicherungspool ausgeführt wird. Daher muss die Anwendung zum Parken von Anrufen sowohl im primären als auch im Sicherungspool bereitgestellt und aktiviert sein, damit das Parken von Anrufen während der Notfallwiederherstellung unterstützt wird.

  - Jeder Pool muss einen gültigen Bereich von Orbitnummern für Benutzer enthalten, die in diesem Pool verwaltet werden, die für das Parken von Anrufen verwendet werden können.

  - Bewahren Sie immer eine separate Kopie von benutzerdefinierter Wartemusik auf, die für das Parken von Anrufen hochgeladen worden ist. Diese Dateien werden nicht im Rahmen des Lync Server 2013-Prozesses für die Notfallwiederherstellung gesichert und gehen folglich verloren, wenn die in den Pool hochgeladenen Dateien beschädigt oder gelöscht werden.

## Überlegungen zur Notfallwiederherstellung für die Anwendung zum Parken von Anrufen

Sie können pro Pool nur einen (1) Satz Konfigurationseinstellungen für die Anwendung zum Parken von Anrufen und eine (1) Audiodatei für benutzerdefinierte Wartemusik definieren. Zu diesen Einstellungen gehören der Timeoutschwellenwert, die Wartemusik, die maximale Zahl der Anrufannahmeversuche und der Timeout-URI. Zum Anzeigen dieser Konfigurationseinstellungen führen Sie das **Get-CsCpsConfiguration**-Cmdlet aus. Ausführliche Informationen zum **Get-CsCpsConfiguration**-Cmdlet finden Sie unter [Get-CsCpsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCpsConfiguration).

Während der Notfallwiederherstellung verwendet Parken von Anrufen die Anwendung zum Parken von Anrufen im Sicherungspool, sodass die Einstellungen im primären Pool nicht gesichert werden. Wenn der primäre Pool nicht wiederhergestellt werden kann und Sie ersatzweise einen neuen Pool bereitstellen, gehen die Einstellungen im primären Pool verloren. Das heißt, Sie müssen die Einstellungen für die Anwendung zum Parken von Anrufen und etwaige Audiodateien für benutzerdefinierte Wartemusik im neuen Pool neu konfigurieren .

Wenn Sie einen neuen Pool mit einem anderen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) bereitstellen, der den primären Pool ersetzt, müssen Sie alle Orbitnummernbereiche der Anwendung zum Parken von Anrufen, die dem primären Pool zugeordnet waren, dem FQDN des neuen Pools zuweisen. Zum Zuweisen von Orbitnummernbereichen zum neuen Pool können Sie entweder die Lync Server-Systemsteuerung oder das **Set-CsCallParkOrbit**-Cmdlet verwenden. Ausführliche Informationen zum **Set-CsCallParkOrbit**-Cmdlet finden Sie unter [Set-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkOrbit).

