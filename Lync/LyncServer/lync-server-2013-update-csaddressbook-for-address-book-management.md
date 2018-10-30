---
title: "\"Update-CsAddressBook\" für die Adressbuchverwaltung"
TOCTitle: "\"Update-CsAddressBook\" für die Adressbuchverwaltung"
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg429695(v=OCS.15)
ms:contentKeyID: 49293199
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# \"Update-CsAddressBook\" für die Adressbuchverwaltung

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Dieses Cmdlet kann von folgenden Benutzern ausgeführt werden: Standardmäßig sind Mitglieder der folgenden Gruppen autorisiert, das Cmdlet "Update-CsAddressBook" lokal auszuführen: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Geben Sie den folgenden Befehl an der Windows PowerShell-Eingabeaufforderung ein, um eine Liste aller rollenbasierten Zugriffssteuerungsrollen zurückzugeben, die diesem Cmdlet zugewiesen wurden (einschließlich der benutzerdefinierten rollenbasierten Zugriffssteuerungsrollen, die Sie selbst erstellt haben):

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

Das Cmdlet "Update-CsAddressBook" ersetzt den Befehl **abserver.exe –syncNow** aus Office Communications Server. Dieses Cmdlet wird verwendet, um eine Synchronisierung nicht erst zum geplanten Zeitpunkt, sondern umgehend auszuführen. Im ersten Beispielbefehl werden alle Adressbücher in der Organisation aktualisiert. Im zweiten Beispiel wird nur das dem angegebenen Server zugeordnete Adressbuch aktualisiert.


> [!NOTE]
> In Lync Server 2013 erfasst der Lync Server-Benutzerreplikationsdienst die Änderungen aus Active Directory und aktualisiert die Lync Server-Benutzerdatenbank basierend auf einem konfigurierten Intervall. Der Lync Server-Benutzerreplikationsdienst gibt die Änderungen auch schnell an die RTCab-Datenbank weiter, ohne dass der Administrator "Update-CSAddressBook" ausführen muss. Administratoren müssen "Update -CSAddressBook" nur ausführen, wenn der Adressbuch-Dateidownload aktiviert ist.



Beispiel:

    Update-CsAddressBook

   &nbsp;

    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com

Eine detaillierte Beschreibung des vollständigen Befehls finden Sie im folgenden Abschnitt der Referenz zu den Windows PowerShell-RTCCmdlets von Lync Server.

## Siehe auch

#### Weitere Ressourcen

[Update-CsAddressBook](https://docs.microsoft.com/en-us/powershell/module/skype/Update-CsAddressBook)

