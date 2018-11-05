---
title: "\"Test-CsAddressBookWebQuery\" für die Adressbuchverwaltung"
TOCTitle: "\"Test-CsAddressBookWebQuery\" für die Adressbuchverwaltung"
ms:assetid: 977a9c1f-5f4e-4539-9a26-8748b61a57d8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg429716(v=OCS.15)
ms:contentKeyID: 49294829
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# \"Test-CsAddressBookWebQuery\" für die Adressbuchverwaltung

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Dieses Cmdlet kann von folgenden Benutzern ausgeführt werden: Standardmäßig dürfen Mitglieder der folgenden Gruppen das Cmdlet "Test-CsAddressBookWebQuery" ausführen: RTCUniversalServerAdmins. Geben Sie den folgenden Befehl an der Windows PowerShell-Eingabeaufforderung ein, um eine Liste aller rollenbasierten Zugriffssteuerungsrollen zurückzugeben, die diesem Cmdlet zugewiesen wurden (einschließlich der benutzerdefinierten rollenbasierten Zugriffssteuerungsrollen, die Sie selbst erstellt haben):

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Test-CsAddressBookService"}

Ähnlich wie die synthetische Transaktion "Test-CsAddressBookService" führt "Test-CsAddressBookWebQuery" eine Abfrage beim Adressbuch-Webabfragedienst durch, um sicherzustellen, dass dieser ordnungsgemäß ausgeführt wird. Das Cmdlet stellt eine Verbindung mit dem Webticketdienst zur Authentifizierung her und legt die in "–UserCredential" angegebenen Anmeldeinformationen vor. Nach der Authentifizierung übergibt das Cmdlet die Informationen in "–TargetSipAddress". Das Cmdlet sollte eine erfolgreiche Ausführung melden, wenn die Informationen zum Kontakt abgerufen werden konnten.

Beispiel:

    Test-CsAddressBookWebQuery -TargetFqdn atl-cs-001.contoso.com -UserCredential contoso\bob -UserSipAddress "sip:bob@contoso.com" -TargetSipAddress "sip:bob@contoso.com"

Eine detaillierte Beschreibung des vollständigen Befehls finden Sie im folgenden Abschnitt der Referenz zu den Windows PowerShell-RTCCmdlets von Lync Server.

## Siehe auch

#### Weitere Ressourcen

[Test-CsAddressBookWebQuery](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsAddressBookWebQuery)

