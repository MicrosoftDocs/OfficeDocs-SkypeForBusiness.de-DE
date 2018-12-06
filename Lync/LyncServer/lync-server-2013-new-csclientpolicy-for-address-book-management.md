---
title: "\"New-CsClientPolicy\" für die Adressbuchverwaltung"
TOCTitle: "\"New-CsClientPolicy\" für die Adressbuchverwaltung"
ms:assetid: ef4415fc-82c4-4dc8-97d1-37a084553343
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg429726(v=OCS.15)
ms:contentKeyID: 49295832
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# \"New-CsClientPolicy\" für die Adressbuchverwaltung

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Dieses Cmdlet kann von folgenden Benutzern ausgeführt werden: Standardmäßig dürfen Mitglieder der folgenden Gruppen das **New-CsClientPolicy**-Cmdlet ausführen: **RTCUniversalServerAdmins**. Geben Sie den folgenden Befehl an der Windows PowerShell-Eingabeaufforderung ein, um eine Liste aller rollenbasierten Zugriffssteuerungsrollen zurückzugeben, die diesem Cmdlet zugewiesen wurden (einschließlich der benutzerdefinierten rollenbasierten Zugriffssteuerungsrollen, die Sie selbst erstellt haben):

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsClientPolicy"}

Das **New-CsClientPolicy**-Cmdlet definiert zahlreiche Einstellungen für die Bereitstellung von Clients für Funktionen, die in Lync Server 2013 zur Verfügung stehen. Für den Adressbuchdienst ist der **AddressBookAvailability**-Parameter von Bedeutung. Dieser Parameter, der sich direkt auf die für die Clients verfügbaren Optionen auswirkt, bietet drei mögliche Optionen:

  - WebSearchAndFileDownload

  - WebSearchOnly

  - FileDownloadOnly

Dieser Parameter, sofern definiert, gibt an, wie durch Clients auf das Adressbuch zugegriffen wird. Wenn Sie diesen Parameter definieren, müssen Sie eine der Optionen festlegen. Wenn Sie diese Einstellung nicht ändern, bleibt der Standardwert "WebSearchAndFileDownload" in Kraft.

Beispiel:

    New-CsClientPolicy -Identity RedmondClientPolicy -DisableCalendarPresence $True -DisablePhonePresence $True -DisplayPhoto "PhotosFromADOnly" -AddressBookAvailability "WebSearchOnly"

## Siehe auch

#### Weitere Ressourcen

[New-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientPolicy)

