---
title: "\"New-CsWebServiceConfiguration\" für die Adressbuchverwaltung"
TOCTitle: "\"New-CsWebServiceConfiguration\" für die Adressbuchverwaltung"
ms:assetid: 49e4ecc5-aa3e-4dd4-a32c-b0dea3758fab
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg429703(v=OCS.15)
ms:contentKeyID: 49293909
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# \"New-CsWebServiceConfiguration\" für die Adressbuchverwaltung

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Dieses Cmdlet kann von folgenden Benutzern ausgeführt werden: Standardmäßig dürfen Mitglieder der folgenden Gruppen das Cmdlet "New-CsWebServiceConfiguration" lokal ausführen: RTCUniversalServerAdmins. Geben Sie den folgenden Befehl an der Windows PowerShell-Eingabeaufforderung ein, um eine Liste aller rollenbasierten Zugriffssteuerungsrollen zurückzugeben, die diesem Cmdlet zugewiesen wurden (einschließlich der benutzerdefinierten rollenbasierten Zugriffssteuerungsrollen, die Sie selbst erstellt haben):

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsWebServiceConfiguration"}

Das Cmdlet "New-CsWebServiceConfiguration" definiert eine neue Konfiguration für Webdienste in Ihrer Organisation. Die Webdienstekonfiguration kann nur auf Standort- oder auf Dienstebene erfolgen. Auf globaler Ebene kann keine neue Webdienstekonfiguration erstellt werden. Für das Adressbuch ist vor allem das Attribut "EnableGroupExansion" interessant. Ist dieses auf "True" gesetzt, können die Webdienste auf Anforderungen zur Gruppenerweiterung reagieren.

Beispiel:

    New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True

Eine detaillierte Beschreibung des vollständigen Befehls finden Sie im folgenden Abschnitt der Referenz zu den Windows PowerShell-RTCCmdlets von Lync Server.

## Siehe auch

#### Weitere Ressourcen

[New-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsWebServiceConfiguration)

