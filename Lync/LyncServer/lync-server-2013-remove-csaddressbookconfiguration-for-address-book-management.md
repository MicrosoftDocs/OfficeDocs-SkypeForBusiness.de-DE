---
title: "\"Remove-CsAddressBookConfiguration\" für die Adressbuchverwaltung"
TOCTitle: "\"Remove-CsAddressBookConfiguration\" für die Adressbuchverwaltung"
ms:assetid: 5d173ebe-ec4d-4640-8432-a25071ea9cc5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg429705(v=OCS.15)
ms:contentKeyID: 49294137
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# \"Remove-CsAddressBookConfiguration\" für die Adressbuchverwaltung

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Dieses Cmdlet kann von folgenden Benutzern ausgeführt werden: Standardmäßig dürfen Mitglieder der folgenden Gruppen das Cmdlet "Remove-CsAddressBookConfiguration" lokal ausführen: RTCUniversalServerAdmins. Geben Sie den folgenden Befehl an der Windows PowerShell-Eingabeaufforderung ein, um eine Liste aller rollenbasierten Zugriffssteuerungsrollen zurückzugeben, die diesem Cmdlet zugewiesen wurden (einschließlich der benutzerdefinierten rollenbasierten Zugriffssteuerungsrollen, die Sie selbst erstellt haben):

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsAddressBookConfiguration"}

Wie der Name besagt, entfernt "Remove-CsAddressBookConfiguration" die Konfiguration basierend auf der definierten Standortidentität.

Beispiel:

    Remove-CsAddressBookConfiguration -Identity site:Redmond

Eine detaillierte Beschreibung des vollständigen Befehls finden Sie im folgenden Abschnitt der Referenz zu den Windows PowerShell-RTCCmdlets von Lync Server.

## Siehe auch

#### Weitere Ressourcen

[Remove-CsAddressBookConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsAddressBookConfiguration)

