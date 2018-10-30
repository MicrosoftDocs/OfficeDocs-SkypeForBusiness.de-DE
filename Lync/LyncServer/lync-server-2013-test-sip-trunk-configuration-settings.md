---
title: Testen von Konfigurationseinstellungen für SIP-Trunks in Lync Server 2013
TOCTitle: Testen von Konfigurationseinstellungen für SIP-Trunks in Lync Server 2013
ms:assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721880(v=OCS.15)
ms:contentKeyID: 49890934
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Testen von Konfigurationseinstellungen für SIP-Trunks in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

SIP-Trunk-Konfigurationseinstellungen definieren die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Nebenstellenanlage (Private Branch Exchange, PBX) oder einem SBC (Session Border Controller) des Dienstanbieters. Diese Einstellungen bestimmen Folgendes:

  - Ob die Medienumgehung für die Trunks aktiviert werden soll.

  - Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control Protocol) gesendet werden.

  - Ob die sichere SRTP-Verschlüsselung (Secure Real-Time Transport Protocol) für jeden Trunk erforderlich ist.

Bei der Installation von Microsoft Lync Server 2013 wird eine globale Auflistung von SIP-Trunk-Konfigurationseinstellungen erstellt. Darüber hinaus können Administratoren benutzerdefinierte Auflistungen mit Einstellungen auf Standort- oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst). Administratoren können außerdem mit dem Test-CsTrunkConfiguration-Cmdlet überprüfen, ob ein Trunk eine von einem Benutzer gewählte Rufnummer in eine für das Gateway kompatible Rufnummer konvertieren kann.

Trunk-Konfigurationseinstellungen können nur mit Windows PowerShell und dem [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration)-Cmdlet getestet werden. Dieses Cmdlet können Sie entweder über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Testen der Trunk-Konfigurationseinstellungen

  - Mit dem folgenden Befehl wird überprüft, ob mit den Trunk-Konfigurationseinstellungen für den Standort "Redmond" die gewählte Rufnummer 4255551212 ordnungsgemäß konvertiert werden kann.
    
        $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
        Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk

