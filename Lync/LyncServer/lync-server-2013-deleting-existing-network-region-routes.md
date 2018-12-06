---
title: Löschen von vorhandenen Netzwerkregionsrouten
TOCTitle: Löschen von vorhandenen Netzwerkregionsrouten
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49890770
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen von vorhandenen Netzwerkregionsrouten

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Jede Region in einer CAC-Konfiguration (Call Admission Control, Anrufsteuerung) muss über eine Möglichkeit verfügen, auf jede andere Region zuzugreifen. Während die Regionenverbindungen Bandbreiteneinschränkungen für Verbindungen zwischen Regionen festlegen und auch die physischen Verbindungen darstellen, bestimmt eine Route, welchen Pfad die Verbindung von einer Region zur anderen nimmt. Mithilfe der Lync Server-Systemsteuerung können Sie Netzwerkregionenrouten konfigurieren. In der Lync Server-Systemsteuerung können Sie eine Netzwerkregionenroute erstellen, ändern oder löschen. In diesem Thema wird beschrieben, wie vorhandene Netzwerkregionenrouten gelöscht werden. Nähere Informationen über das Erstellen oder Ändern von Netzwerkregionenrouten finden Sie unter [Erstellen oder Ändern von Netzwerkregionsrouten](lync-server-2013-creating-or-modifying-network-region-routes.md).

## So löschen Sie eine Netzwerkregionenroute

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regionenroute**.

4.  Klicken Sie auf der Seite **Regionenroute** auf die Regionenroute, die Sie löschen möchten.
    

    > [!NOTE]
    > Sie können mehrere Regionenrouten in einem Arbeitsschritt löschen. Wählen Sie dazu mit gedrückter STRG-TASTE mehrere Regionenrouten aus. Wenn Sie alle Regionenrouten auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG>.



5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.

## Siehe auch

#### Aufgaben

[Erstellen oder Ändern von Netzwerkregionsrouten](lync-server-2013-creating-or-modifying-network-region-routes.md)  

#### Konzepte

[Konfigurieren einer Netzwerkregionenroute](https://technet.microsoft.com/de-de/library/gg133706\(v=ocs.15\))  

#### Weitere Ressourcen

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterRegionRoute)

