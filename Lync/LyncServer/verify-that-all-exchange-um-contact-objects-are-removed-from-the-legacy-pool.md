---
title: Überprüfen der vollständigen Entfernung aller Exchange UM-Kontaktobjekte aus dem Legacypool
TOCTitle: Überprüfen der vollständigen Entfernung aller Exchange UM-Kontaktobjekte aus dem Legacypool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49890761
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überprüfen der vollständigen Entfernung aller Exchange UM-Kontaktobjekte aus dem Legacypool

 

_**Letztes Änderungsdatum des Themas:** 2012-09-26_

Überprüfen Sie mit dem **OCSUmUtil**-Tool oder mit dem **Get-CsExumContact**-Cmdlet, ob die Exchange UM-Kontaktobjekte aus dem älteren Office Communications Server 2007 R2-Pool entfernt wurden. **OCSUmUtil** befindet sich im folgenden Ordner:

%Programme%\\Gemeinsame Dateien\\ Lync Server 2013\\Support\\OcsUMUtil.exe

**OCSUmUtil** muss von einem Benutzerkonto mit folgenden Rollen und Rechten ausgeführt werden:

  - Mitgliedschaft in der RTCUniversalServerAdmins- und in der RTCUniversalUserAdmins-Gruppe (einschließlich der Rechte zum Lesen von Exchange Server Unified Messaging-Einstellungen)

  - Domänenrechte zum Erstellen von Kontaktobjekten im angegebenen Container für die Organisationseinheit

Nähere Informationen zur Verwendung des **Get-CsExumContact**-Cmdlets finden Sie in der Lync Server-Verwaltungsshell-Dokumentation unter [Get-CsExUmContact](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExUmContact).

