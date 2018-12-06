---
title: Anzeigen von Informationen zu Netzwerksubnetzen
TOCTitle: Anzeigen von Informationen zu Netzwerksubnetzen
ms:assetid: 46f165f2-efe3-4cc1-9fee-a78b7f2ed41e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688044(v=OCS.15)
ms:contentKeyID: 49890730
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Informationen zu Netzwerksubnetzen

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Mit dem folgenden Verfahren können Sie ein Netzwerksubnetz anzeigen. In Lync Server-Systemsteuerung können Sie Netzwerksubnetze erstellen, bearbeiten oder löschen. Nähere Informationen zum Erstellen oder Bearbeiten von Netzwerksubnetzen finden Sie unter [Erstellen oder Ändern von Netzwerksubnetzen](lync-server-2013-create-or-modify-network-subnets.md).

## So zeigen Sie ein Netzwerksubnetz an

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Subnetz**.

4.  Klicken Sie auf der Seite **Subnetz** auf das Subnetz, das Sie anzeigen möchten.
    

    > [!NOTE]
    > Sie können nur jeweils ein Subnetz anzeigen.



5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

## Anzeigen von Netzwerksubnetz-Konfigurationsinformationen mit den Lync Server PowerShell-Cmdlets

Netzwerksubnetzinformationen können auch mit Lync Server PowerShell und dem Get-CsNetworkSubnet-Cmdlet angezeigt werden. Dieses Cmdlet kann über Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Anzeigen von Netzwerksubnetzinformationen

  - Um Informationen über alle Netzwerksubnetze anzuzeigen, geben Sie den folgenden Befehl in Lync Server-Verwaltungsshell ein, und drücken Sie die EINGABETASTE:
    
        Get-CsNetworkSubnet
    
    Dadurch werden Informationen wie die folgenden zurückgegeben:
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0

Weitere Informationen finden Sie im Hilfethema für das Cmdlet [Get-CsNetworkSubnet](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkSubnet).

## Siehe auch

#### Aufgaben

[Erstellen oder Ändern von Netzwerksubnetzen](lync-server-2013-create-or-modify-network-subnets.md)  
[Löschen von Netzwerksubnetzen](lync-server-2013-deleting-network-subnets.md)

