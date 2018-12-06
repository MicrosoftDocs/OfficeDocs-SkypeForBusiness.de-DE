---
title: "\"Get-CsAddressBookConfiguration\" für die Adressbuchverwaltung"
TOCTitle: "\"Get-CsAddressBookConfiguration\" für die Adressbuchverwaltung"
ms:assetid: bd62f916-caf3-4e10-ada4-631bbb331ef1
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg429721(v=OCS.15)
ms:contentKeyID: 49295248
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# \"Get-CsAddressBookConfiguration\" für die Adressbuchverwaltung

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Dieses Cmdlet kann von folgenden Benutzern ausgeführt werden: Standardmäßig dürfen Mitglieder der folgenden Gruppen das Cmdlet "Get-CsAddressBookConfiguration" lokal ausführen: RTCUniversalServerAdmins. Geben Sie den folgenden Befehl an der Windows PowerShell-Eingabeaufforderung ein, um eine Liste aller rollenbasierten Zugriffssteuerungsrollen zurückzugeben, die diesem Cmdlet zugewiesen wurden (einschließlich der benutzerdefinierten rollenbasierten Zugriffssteuerungsrollen, die Sie selbst erstellt haben):

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsAddressBookConfiguration"}

Mit dem Cmdlet "Get-CsAddressBookConfiguration" werden Informationen zu einer Konfiguration zurückgegeben, die bereits vorhanden ist.

Beispiel:

    Get-CsAddressBookConfiguration -Identity site:Redmond

Durch den kombinierten Einsatz der Cmdlets "Get-CsAddressBookConfiguration" und "Set-CsAddressBookConfiguration" kann der Administrator zunächst definieren, welche Konfigurationen geändert werden sollen, und die Änderungen anschließend anwenden. Beispiel für die kombinierte Verwendung:

    Get-CsAddressBookConfiguration -Filter site:* | Set-CsAddressBookConfiguration -RunTimeOfDay 23:00

In diesem Beispiel werden alle Konfigurationen an sämtlichen Standorten zurückgegeben, und der Parameter "RunTimeOfDay" wird für alle Konfigurationen auf "23:00" festgelegt.

Eine detaillierte Beschreibung des vollständigen Befehls finden Sie im folgenden Abschnitt der Referenz zu den Windows PowerShell-RTCCmdlets von Lync Server.

## Siehe auch

#### Weitere Ressourcen

[Get-CsAddressBookConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAddressBookConfiguration)

