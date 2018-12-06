---
title: Anzeigen von Informationen zu Netzwerkregionsverbindungen
TOCTitle: Anzeigen von Informationen zu Netzwerkregionsverbindungen
ms:assetid: 7b6b2ea2-83d8-4376-afb2-70e5d2cf6444
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688102(v=OCS.15)
ms:contentKeyID: 49890802
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Informationen zu Netzwerkregionsverbindungen

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Sie können im Rahmen der Anrufsteuerung Verbindungen zwischen zwei Netzwerkregionen anzeigen. Regionen in einem Netzwerk sind über eine physische WAN-Verbindung (Wide Area Network, Fernnetz) verbunden. Mithilfe der Lync Server-Systemsteuerung können Sie eine bestehende Verbindung zwischen zwei Netzwerkregionen anzeigen. Ausführliche Informationen zum Erstellen und Ändern einer Netzwerkregionenverbindung finden Sie unter [Konfigurieren von Netzwerkregionenverbindungen](lync-server-2013-configuring-network-region-links.md).

## So zeigen Sie eine Netzwerkregionenverbindung in Lync Server-Systemsteuerung an

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regionenverbindung**.

4.  Klicken Sie auf der Seite **Regionenverbindung** auf die Regionenverbindung, die Sie anzeigen möchten.
    

    > [!NOTE]
    > Es können in einem Arbeitsschritt nur Informationen zu einer Regionenverbindung angezeigt werden.



5.  Wählen Sie im Menü **Bearbeiten** die Option **Details anzeigen** aus.

## Anzeigen der Informationen zu Netzwerkregionenverbindungen mithilfe der Lync Server-Verwaltungsshell-Cmdlets

Sie können die Netzwerkregionenverbindungen auch anzeigen, indem Sie die Lync Server-Verwaltungsshell und das Cmdlet **Get-CsNetworkRegionLink** verwenden. Sie können dieses Cmdlet über die Verwaltungsshell für Lync Server 2013 oder über eine Remote-Sitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So zeigen Sie die Informationen zu einer Netzwerkregionenverbindung an

  - Sie können die Informationen zu Netzwerkregionenverbindungen anzeigen, indem Sie in der Lync Server-Verwaltungsshell den folgenden Befehl eingeben und die EINGABETASTE drücken:
    
        Get-CsNetworkRegionLink
    
    Mit diesem Befehl werden Informationen nach folgendem Muster zurückgegeben:
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

Für weitere Informationen, siehe [Get-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink).

## Siehe auch

#### Aufgaben

[Konfigurieren von Netzwerkstandortverknüpfungen](lync-server-2013-configuring-network-site-links.md)

