---
title: Verschieben der verbleibenden Benutzer zu Lync Server 2013
TOCTitle: Verschieben der verbleibenden Benutzer zu Lync Server 2013
ms:assetid: 0eb990f0-f720-47a7-aaee-437fbd4c4c33
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ687968(v=OCS.15)
ms:contentKeyID: 49890624
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verschieben der verbleibenden Benutzer zu Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-26_

Sie können Benutzer entweder mithilfe der Lync Server-Systemsteuerung oder mit der Lync Server-Verwaltungsshell in die neue Lync Server 2013-Bereitstellung verschieben. Für eine reibungslose Umstellung auf Lync Server 2013 müssen bestimmte Voraussetzungen erfüllt sein. Ausführliche Informationen zu den Voraussetzungen für die Verfahren in diesem Thema finden Sie unter [Konfigurieren von Clients für die Migration](configure-clients-for-migration_1.md). Eine ausführliche Beschreibung zum Verschieben von Benutzern finden Sie unter [Phase 6: Verschieben von Benutzern in den Pilotpool](phase-6-move-users-to-the-pilot-pool.md).


> [!IMPORTANT]
> Sie können nicht das Snap-In ”Active Directory-Benutzer und -Computer” oder die Verwaltungstools von Microsoft Office Communications Server 2007 R2 verwenden, um Benutzer aus der Vorgängerumgebung nach Lync Server 2013 zu verschieben.




> [!IMPORTANT]
> Die Verwendung des <STRONG>Move-CsLegacyUser</STRONG> -Cmdlets setzt voraus, dass Benutzernamen im korrekten Format ohne vorangestellte oder nachgestellte Leerzeichen vorliegen. Sie können ein Benutzerkonto nicht mithilfe des <STRONG>Move-CsLegacyUser</STRONG> -Cmdlets verschieben, wenn der Name vorangestellte oder nachgestellte Leerzeichen enthält.



Wenn Sie einen Benutzer in einen Lync Server 2013-Pool verschieben, werden die Daten für den Benutzer in die Back-End-Datenbank verschoben, die dem neuen Pool zugeordnet ist.


> [!IMPORTANT]
> Hierzu gehören die aktiven Besprechungen, die der Benutzer der Vorgängerversion erstellt hat. Wenn ein Benutzer der Vorgängerversion beispielsweise eine Konferenz vom Typ <STRONG>Meine Besprechung</STRONG> konfiguriert hat, ist diese Konferenz nach dem Verschieben des Benutzers im neuen Lync Server 2013-Pool weiterhin vorhanden. Die Details für den Zugriff auf diese Besprechung sind die gleiche <STRONG>Konferenz-URL und Konferenz-ID</STRONG> wie vorher. Der einzige Unterschied besteht darin, dass die Konferenz-ID jetzt im Lync Server 2013-Pool und nicht mehr im Office Communications Server 2007 R2-Pool gehostet wird.




> [!NOTE]
> Das Verwalten von Benutzern in Lync Server 2013 erfordert nicht, dass Sie gleichzeitig geupgradete Clients bereitstellen. Neue Funktionen stehen den Benutzern nur dann zur Verfügung, wenn sie ein Upgrade auf die neue Clientsoftware durchgeführt haben.



## Aufgaben nach der Migration

1.  Überprüfen Sie nach dem Verschieben der Benutzer die ihnen zugeordnete Konferenzrichtlinie.

2.  Damit sichergestellt ist, dass Besprechungen, die von in Lync Server 2013 verwalteten Benutzern organisiert wurden, reibungslos mit Partnerverbundbenutzern funktionieren, die in Office Communications Server 2007 R2 verwaltet werden, sollte die den migrierten Benutzern zugeordnete Konferenzrichtlinie anonyme Teilnehmer zulassen.

3.  Bei Konferenzrichtlinien, die anonyme Teilnehmer zulassen, ist in der Systemsteuerung für Lync Server 2013 die Option **Teilnehmer dürfen anonyme Benutzer einladen** aktiviert und in der Ausgabe des **Get-CsConferencingPolicy** -Cmdlets in der Lync Server-Verwaltungsshell der Parameter **AllowAnonymousParticipantsInMeetings** auf **True** festgelegt.

4.  Ausführliche Informationen zum Konfigurieren der Konferenzrichtlinie mithilfe der Lync Server-Verwaltungsshell finden Sie unter [Set-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsConferencingPolicy) in der Dokumentation zur Lync Server-Verwaltungsshell.

