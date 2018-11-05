---
title: Anzeigen von Informationen zu Netzwerkregionen
TOCTitle: Anzeigen von Informationen zu Netzwerkregionen
ms:assetid: 665740d0-a3ed-460f-8337-5ed945f90589
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688076(v=OCS.15)
ms:contentKeyID: 49890771
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Informationen zu Netzwerkregionen

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Eine Netzwerkregion verbindet mehrere Teile eines Netzwerks, das sich über verschiedene geografische Bereiche erstreckt. Jede Netzwerkregion muss einem zentralen Standort zugeordnet sein. Der zentrale Standort ist der Standort des Rechenzentrums, in dem der Bandbreitenrichtliniendienst für die Anrufsteuerung ausgeführt wird. Mithilfe der Lync Server-Systemsteuerung können Sie Netzwerkregionen anzeigen. Netzwerkregionen beinhalten Einstellungen, die festlegen, ob für Audio- und Videoverbindungen alternative Pfade über das Internet zulässig sind. In diesem Thema wird erklärt, wie vorhandene Netzwerkregionen angezeigt werden. Nähere Informationen über das Erstellen oder Ändern vorhandener Netzwerkregionen finden Sie unter [Erstellen oder Ändern von Netzwerkregionen](lync-server-2013-creating-or-modifying-network-regions.md).

## So zeigen Sie mit der Lync Server-Systemsteuerung Informationen zu einer Netzwerkregion an

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Region**.

4.  Klicken Sie auf der Seite **Region** auf die Region, die Sie anzeigen möchten.
    

    > [!NOTE]
    > Sie können immer nur eine Region anzeigen.



5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

## Anzeigen von Informationen zur Netzwerkregion mithilfe von Windows PowerShell-Cmdlets

Informationen zur Netzwerkregion können Sie mit der Windows PowerShell und dem Cmdlet **Get-CsNetworkRegion** anzeigen. Dieses Cmdlet können Sie entweder über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So zeigen Sie Informationen zur Netzwerkregion an

  - Geben Sie zum Anzeigen von Informationen über all Ihre Netzwerkregionen den folgenden Befehl in der Lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsNetworkRegion
    
    Die zurückgegebenen Informationen sehen wie folgt aus:
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

Weitere Informationen finden Sie im Hilfethema für das [Get-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink)-Cmdlet.

## Siehe auch

#### Aufgaben

[Erstellen oder Ändern von Netzwerkregionen](lync-server-2013-creating-or-modifying-network-regions.md)  
[Löschen von vorhandenen Netzwerkregionen](lync-server-2013-deleting-existing-network-regions.md)

