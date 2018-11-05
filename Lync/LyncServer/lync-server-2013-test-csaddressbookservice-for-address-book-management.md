---
title: "\"Test-CsAddressBookService\" für die Adressbuchverwaltung"
TOCTitle: "\"Test-CsAddressBookService\" für die Adressbuchverwaltung"
ms:assetid: b88cea74-41fd-4c0e-9284-7135bff27a27
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg429720(v=OCS.15)
ms:contentKeyID: 49295194
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# \"Test-CsAddressBookService\" für die Adressbuchverwaltung

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Dieses Cmdlet kann von folgenden Benutzern ausgeführt werden: Standardmäßig dürfen Mitglieder der folgenden Gruppen das Cmdlet "Test-CsAddressBookService" ausführen: RTCUniversalServerAdmins. Geben Sie den folgenden Befehl an der Windows PowerShell-Eingabeaufforderung ein, um eine Liste aller rollenbasierten Zugriffssteuerungsrollen zurückzugeben, die diesem Cmdlet zugewiesen wurden (einschließlich der benutzerdefinierten rollenbasierten Zugriffssteuerungsrollen, die Sie selbst erstellt haben):

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

Lync Server 2013 umfasst verschiedene Cmdlets, die synthetische Befehle initiieren, um den ordnungsgemäßen Betrieb einer Funktion zu überprüfen. Mit "Test-CsAddressBookService" wird sichergestellt, dass ein definierter Benutzer sich verbinden und die lokalen Dateien vom Adressbuchwebdienst anfordern kann.

Beispiel:

    Test-CsAddressBookService -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com"

## Siehe auch

#### Weitere Ressourcen

[Test-CsAddressBookService](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsAddressBookService)

