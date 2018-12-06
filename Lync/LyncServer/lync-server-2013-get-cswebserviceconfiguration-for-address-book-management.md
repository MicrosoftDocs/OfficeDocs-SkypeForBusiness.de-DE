---
title: "\"Get-CsWebServiceConfiguration\" für die Adressbuchverwaltung"
TOCTitle: "\"Get-CsWebServiceConfiguration\" für die Adressbuchverwaltung"
ms:assetid: 0b223733-5224-47d1-9b47-2109e6f135c9
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg429692(v=OCS.15)
ms:contentKeyID: 49293132
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# \"Get-CsWebServiceConfiguration\" für die Adressbuchverwaltung

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Dieses Cmdlet kann von folgenden Benutzern ausgeführt werden: Standardmäßig sind Mitglieder der folgenden Gruppen autorisiert, das Cmdlet "Get-CsWebServiceConfiguration" lokal auszuführen: RTCUniversalUserAdmins, RTCUniversalServerAdmins. Geben Sie den folgenden Befehl an der Windows PowerShell-Eingabeaufforderung ein, um eine Liste aller rollenbasierten Zugriffssteuerungsrollen zurückzugeben, die diesem Cmdlet zugewiesen wurden (einschließlich der benutzerdefinierten rollenbasierten Zugriffssteuerungsrollen, die Sie selbst erstellt haben):

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsWebServiceConfiguration"}

"Get-CsWebServiceConfiguration" gibt Informationen zur Webdienstekonfiguration zurück, die gegenwärtig in Ihrer Organisation verwendet wird. Für den Adressbuchdienst ist der Status der Funktion zur Verteilerlistenerweiterung relevant. Wenn das Attribut "EnableGroupExpansion" auf "True" gesetzt ist, ist die Gruppenerweiterung in Ihrer Organisation gegenwärtig zulässig.

Beispiel:

    Get-CsWebServiceConfiguration -Identity site:Redmond

Eine detaillierte Beschreibung des vollständigen Befehls finden Sie im folgenden Abschnitt der Referenz zu den Windows PowerShell-RTCCmdlets von Lync Server.

## Siehe auch

#### Weitere Ressourcen

[Get-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWebServiceConfiguration)

