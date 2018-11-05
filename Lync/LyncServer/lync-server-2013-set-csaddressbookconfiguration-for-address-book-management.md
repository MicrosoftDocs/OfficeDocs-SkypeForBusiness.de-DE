---
title: "\"Set-CsAddressBookConfiguration\" für die Adressbuchverwaltung"
TOCTitle: "\"Set-CsAddressBookConfiguration\" für die Adressbuchverwaltung"
ms:assetid: 3a64ceb1-9f79-4f3b-bf33-eaf346dbd60d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg429700(v=OCS.15)
ms:contentKeyID: 49293719
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# \"Set-CsAddressBookConfiguration\" für die Adressbuchverwaltung

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Dieses Cmdlet kann von folgenden Benutzern ausgeführt werden: Standardmäßig dürfen Mitglieder der folgenden Gruppen das Cmdlet "Set-CsAddressBookConfiguration" lokal ausführen: RTCUniversalServerAdmins. Geben Sie den folgenden Befehl an der Windows PowerShell-Eingabeaufforderung ein, um eine Liste aller rollenbasierten Zugriffssteuerungsrollen zurückzugeben, die diesem Cmdlet zugewiesen wurden (einschließlich der benutzerdefinierten rollenbasierten Zugriffssteuerungsrollen, die Sie selbst erstellt haben):

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsAddressBookConfiguration"}

"Set-CsAddressBookConfiguration" ähnelt dem Cmdlet "New-CsAddressBookConfiguration", wird jedoch zum Ändern einer vorhandenen Konfiguration verwendet.

Beispiel:

    Set-CsAddressBookConfiguration -identity site:Redmond -RunTimeOfDay 23:00

Eine detaillierte Beschreibung des vollständigen Befehls finden Sie im folgenden Abschnitt der Referenz zu den Windows PowerShell-RTCCmdlets von Lync Server.

## Siehe auch

#### Weitere Ressourcen

[Set-CsAddressBookConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsAddressBookConfiguration)

