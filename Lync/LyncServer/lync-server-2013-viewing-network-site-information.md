---
title: Anzeigen von Informationen zu Netzwerkstandorten
TOCTitle: Anzeigen von Informationen zu Netzwerkstandorten
ms:assetid: 24a97d98-b168-4016-81bf-c2c478092b87
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ687996(v=OCS.15)
ms:contentKeyID: 49890665
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Informationen zu Netzwerkstandorten

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Netzwerkstandorte sind Niederlassungen oder Standorte, die in jeder Region einer Anrufsteuerungs- oder E9-1-1-Bereitstellung konfiguriert sind. You can view network site information in either Systemsteuerung für Lync Server 2013 or Lync Server-Verwaltungsshell . For details about creating or modifying network sites, see [Erstellen oder Ändern von Netzwerkstandorten](lync-server-2013-creating-or-modifying-network-sites.md).

## So zeigen Sie Netzwerkstandortinformationen in der Lync Server-Systemsteuerung an

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Standort**.

4.  Klicken Sie auf der Seite **Website** auf die Website, die Sie anzeigen möchten.
    

    > [!NOTE]
    > Sie können jeweils nur Informationen für einen Standort anzeigen.



5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

## So zeigen Sie Netzerkstandortinformationen mithilfe der Cmdlets der Lync Server-Verwaltungsshell an

Sie können Netzwerkstandortinformationen mithilfe des Cmdlets "Get-CsNetworkSite" anzeigen. Das Cmdlet kann über die Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So zeigen Sie Netzwerkstandortinformationen an

  - Geben Sie zum Anzeigen von Informationen zu allen Netzwerkstandorten den folgenden Befehl in die Lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsNetworkSite
    
    Es werden Informationen der folgenden Art zurückgegeben:
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkSite).

## Siehe auch

#### Aufgaben

[Erstellen oder Ändern von Netzwerkstandorten](lync-server-2013-creating-or-modifying-network-sites.md)  
[Löschen eines vorhandenen Netzwerkstandorts](lync-server-2013-deleting-an-existing-network-site.md)

