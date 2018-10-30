---
title: "\"Remove-CsWebServiceConfiguration\" für die Adressbuchverwaltung"
TOCTitle: "\"Remove-CsWebServiceConfiguration\" für die Adressbuchverwaltung"
ms:assetid: 91947cad-5cdd-41b9-83e1-650703c55879
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg429713(v=OCS.15)
ms:contentKeyID: 49294757
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# \"Remove-CsWebServiceConfiguration\" für die Adressbuchverwaltung

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Dieses Cmdlet kann von folgenden Benutzern ausgeführt werden: Standardmäßig dürfen Mitglieder der folgenden Gruppe das Cmdlet "Remove-CsWebServiceConfiguration" lokal ausführen: RTCUniversalServerAdmins. Geben Sie den folgenden Befehl an der Windows PowerShell-Eingabeaufforderung ein, um eine Liste aller rollenbasierten Zugriffssteuerungsrollen zurückzugeben, die diesem Cmdlet zugewiesen wurden (einschließlich der benutzerdefinierten rollenbasierten Zugriffssteuerungsrollen, die Sie selbst erstellt haben):

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Remove-CsWebServiceConfiguration"}

Über das Cmdlet "Remove-CsWebServiceConfiguration" kann ein Administrator eine zuvor erstellte Webdienstekonfiguration entfernen. Die globale Webdienstekonfiguration kann mit diesem Cmdlet nicht entfernt werden.

Beispiel:

    Remove-CsWebServiceConfiguration -Identity site:Redmond

Eine detaillierte Beschreibung des vollständigen Befehls finden Sie im folgenden Abschnitt der Referenz zu den Windows PowerShell-RTCCmdlets von Lync Server.

## Siehe auch

#### Weitere Ressourcen

[Remove-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsWebServiceConfiguration)

