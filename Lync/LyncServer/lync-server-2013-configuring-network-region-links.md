---
title: Konfigurieren von Netzwerkregionenverbindungen
TOCTitle: Konfigurieren von Netzwerkregionenverbindungen
ms:assetid: 952bc93e-e6aa-4539-85c7-2b15f14eb382
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182551(v=OCS.15)
ms:contentKeyID: 49294791
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Netzwerkregionenverbindungen

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Sie können im Rahmen der Anrufsteuerung Verbindungen zwischen zwei Netzwerkregionen konfigurieren. Regionen in einem Netzwerk sind über eine physische WAN-Verbindung (Wide Area Network, Fernnetz) verbunden. Mithilfe der Lync Server-Systemsteuerung können Sie eine Verbindung zwischen zwei Netzwerkregionen definieren und die Bandbreiteneinschränkungen für Audio- und Videoverbindungen zwischen diesen Regionen festlegen. Ausführliche Informationen zum Löschen eines vorhandenen Netzwerkregionlinks finden Sie unter [Löschen von Netzwerkregionenverbindungen](lync-server-2013-deleting-network-region-links.md).

## So erstellen Sie eine Netzwerkregionenverbindung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regionenverbindung**.

4.  Klicken Sie auf der Seite **Regionenverbindung** auf **Neu**.

5.  Geben Sie im Abschnitt **Neue Regionenverbindung** im Feld **Name** einen Wert ein.
    

    > [!NOTE]
    > Dieser Wert muss innerhalb der Lync Server 2013-Bereitstellung eindeutig sein.



6.  Wählen Sie in der Dropdownliste **Netzwerkregion 1** eine der zwei Regionen aus, die verknüpft werden sollen.

7.  Wählen Sie in der Dropdownliste **Netzwerkregion 2** die andere Region aus, die verknüpft werden soll. Diese Region muss sich von der für Netzwerkregion 1 ausgewählten Region unterscheiden.

8.  (Optional) Wenn Sie Bandbreitenbeschränkungen für Audio- oder Videoanrufe zwischen diesen Regionen festlegen möchten, wählen Sie ein Bandbreitenrichtlinienprofil in der Dropdownliste **Bandbreitenrichtlinie** aus.

9.  Klicken Sie auf **Commit**.

## So ändern Sie eine Netzwerkregionenverbindung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regionenverbindung**.

4.  Klicken Sie auf der Seite **Regionenverbindung** auf die Regionenverbindung, die Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Im Abschnitt **Regionenverbindung bearbeiten** können Sie die verknüpften Regionen oder das Bandbreitenrichtlinienprofil für diese Region ändern.

7.  Klicken Sie auf **Commit**.

## Siehe auch

#### Aufgaben

[Löschen von Netzwerkregionenverbindungen](lync-server-2013-deleting-network-region-links.md)  

#### Weitere Ressourcen

[New-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkRegionLink)  
[Set-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkRegionLink)  
[Remove-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkRegionLink)  
[Get-CsNetworkRegionLink](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink)

