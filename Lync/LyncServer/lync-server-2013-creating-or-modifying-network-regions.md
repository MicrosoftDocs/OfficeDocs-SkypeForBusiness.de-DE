---
title: Erstellen oder Ändern von Netzwerkregionen
TOCTitle: Erstellen oder Ändern von Netzwerkregionen
ms:assetid: bd08bb66-5976-4ece-b45c-7de19569f814
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182579(v=OCS.15)
ms:contentKeyID: 49295243
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern von Netzwerkregionen

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Eine Netzwerkregion verbindet verschiedene Teile eines Netzwerks, das sich über verschiedene geografische Bereiche erstreckt. Jede Netzwerkregion muss einem zentralen Standort zugeordnet sein. Der zentrale Standort ist der Rechenzentrumsstandort, an dem der Bandbreitenrichtliniendienst für die Anrufsteuerung ausgeführt wird. Mithilfe der Lync Server-Systemsteuerung können Sie Netzwerkregionen konfigurieren. Netzwerkregionen umfassen Einstellungen, mit denen definiert wird, ob für Audio- und Videoverbindungen alternative Pfade über das Internet zulässig sind. Über die Lync Server-Systemsteuerung können Sie eine Netzwerkregion erstellen, ändern oder löschen. Verwenden Sie dieses Thema zum Erstellen und Ändern von Netzwerkregionen. Ausführliche Informationen zu Löschen vorhandener Netzwerkregionen finden Sie unter [Löschen von vorhandenen Netzwerkregionen](lync-server-2013-deleting-existing-network-regions.md).

## So erstellen Sie eine Netzwerkregion

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Region**.

4.  Klicken Sie auf der Seite **Region** auf **Neu**.

5.  Geben Sie auf der Seite **Neue Region** im Feld **Name** einen Wert ein. Dieser Wert muss innerhalb der Microsoft Lync Server 2013-Bereitstellung eindeutig sein.

6.  Wählen Sie in der Dropdownliste **Zentraler Standort** den zentralen Standort für diese Netzwerkregion aus.

7.  Das Kontrollkästchen **Alternativen Audiopfad aktivieren** ist standardmäßig aktiviert. Diese Einstellung legt fest, ob Audioanrufe über einen alternativen Pfad weitergeleitet werden, wenn der primäre Pfad keine angemessene Bandbreite bietet. Deaktivieren Sie dieses Kontrollkästchen nur dann, wenn alternative Pfade im Internet deaktiviert werden müssen. Wenn Internetanrufe vorgesehen sind, muss dieses Kontrollkästchen unabhängig von den Bandbreiteneinstellungen aktiviert sein.

8.  Das Kontrollkästchen **Alternativen Videopfad aktivieren** ist standardmäßig aktiviert. Diese Einstellung legt fest, ob Videoanrufe über einen alternativen Pfad weitergeleitet werden, wenn der primäre Pfad keine angemessene Bandbreite bietet. Deaktivieren Sie dieses Kontrollkästchen nur dann, wenn alternative Pfade im Internet deaktiviert werden müssen. Wenn Internetanrufe vorgesehen sind, muss dieses Kontrollkästchen unabhängig von den Bandbreiteneinstellungen aktiviert sein.

9.  (Optional) Geben Sie im Feld **Beschreibung** einen Wert zum Bereitstellen weiterer Informationen zu dieser Region ein, die nicht durch den Namen allein vermittelt werden können.

10. Klicken Sie auf **Commit ausführen**.

Die Tabelle **Zugeordnete Standorte** wird zum Erstellen einer Netzwerkregion nicht verwendet. Sie ordnen einer Region einen Standort zu, wenn Sie den Standort erstellen oder ändern. Ausführliche Informationen finden Sie unter [Erstellen oder Ändern von Netzwerkstandorten](lync-server-2013-creating-or-modifying-network-sites.md).

## So ändern Sie eine Netzwerkregion

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Region**.

4.  Klicken Sie auf der Seite **Region** auf die Region, die Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details einblenden**.

6.  Auf der Seite **Region bearbeiten** können Sie die Einstellungen zum Aktivieren und Deaktivieren von alternativen Pfaden für Audio und Video ändern, und Sie können die Beschreibung bearbeiten (ausführliche Informationen finden Sie unter "So erstellen Sie eine Netzwerkregion" weiter oben in diesem Thema).

7.  Klicken Sie auf **Commit ausführen**.

Sie können die Option **Zugeordnete Standorte** auf dieser Seite nicht ändern. Die Liste der zugeordneten Standorte wird zu Referenzzwecken angezeigt, damit Sie wissen, auf welche Standorte sich die Änderung der Regioneneinstellungen auswirkt.

## Siehe auch

#### Aufgaben

[Löschen von vorhandenen Netzwerkregionen](lync-server-2013-deleting-existing-network-regions.md)  
[Konfigurieren von Netzwerkregionen für die Anrufsteuerung in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md)  

#### Weitere Ressourcen

[New-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkRegion)  
[Set-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkRegion)  
[Remove-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkRegion)  
[Get-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink)

