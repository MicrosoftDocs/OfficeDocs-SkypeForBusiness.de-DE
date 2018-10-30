---
title: 'Lync Server 2013: Replikationsstatus des zentralen Verwaltungsspeichers'
TOCTitle: Replikationsstatus des zentralen Verwaltungsspeichers
ms:assetid: f514f88d-986b-4e45-b79b-e04a7616c1fe
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn720926(v=OCS.15)
ms:contentKeyID: 62240050
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Replikationsstatus des zentralen Verwaltungsspeichers in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-01-26_

Wenn ein Administrator Änderungen an Lync Server vornimmt (z. B. eine neue VoIP-Richtlinie erstellt oder die Konfigurationseinstellungen des Adressbuchservers ändert), wird diese Änderung im zentralen Verwaltungsspeicher aufgezeichnet. Diese Änderung muss dann wiederum auf allen Computern repliziert werden, auf denen Lync Server-Dienste oder -Serverrollen ausgeführt werden.

Zum Replizieren der Daten erstellt der Master-Replikationsdienst (der auf dem zentralen Verwaltungsserver ausgeführt wird) eine Momentaufnahme der geänderten Konfigurationsdaten. Eine Kopie dieser Momentaufnahme wird dann an jeden Computer gesendet, auf dem Lync Server-Dienste oder -Serverrollen ausgeführt werden. Auf diesen Computern erhält ein lokaler Replikations-Agent die Momentaufnahme und lädt die geänderten Daten hoch. Der Agent sendet dann dem Master-Replikationsdienst eine Nachricht mit dem aktuellen Replikationsstatus.

Mit dem Cmdlet „Get-CsManagementStoreReplicationStatus“ können Sie den Replikationsstatus für einzelne oder alle Lync Server-Computer in Ihrer Organisation überprüfen.

Dieses Cmdlet kann von folgenden Benutzern ausgeführt werden: Standardmäßig sind Mitglieder der folgenden Gruppen autorisiert, das Cmdlet „Get-CsManagementStoreReplicationStatus“ lokal auszuführen: RTCUniversalUserAdmins, RTCUniversalServerAdmins.

Geben Sie den folgenden Befehl an der Windows PowerShell-Eingabeaufforderung ein, um eine Liste aller rollenbasierten Zugriffssteuerungsrollen zurückzugeben, die diesem Cmdlet zugewiesen wurden (einschließlich der benutzerdefinierten rollenbasierten Zugriffssteuerungsrollen, die Sie selbst erstellt haben):

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

## Siehe auch

#### Weitere Ressourcen

[Get-CsManagementStoreReplicationStatus](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsManagementStoreReplicationStatus)

