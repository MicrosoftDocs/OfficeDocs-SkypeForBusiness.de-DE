---
title: Löschen von vorhandenen Netzwerkregionen
TOCTitle: Löschen von vorhandenen Netzwerkregionen
ms:assetid: c7293a2f-2b49-4c4a-903f-f7edcea2bc5f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721882(v=OCS.15)
ms:contentKeyID: 49890935
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen von vorhandenen Netzwerkregionen

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Eine Netzwerkregion verbindet verschiedene Teile eines Netzwerks, das sich über verschiedene geografische Bereiche erstreckt. Jede Netzwerkregion muss einem zentralen Standort zugeordnet sein. Der zentrale Standort ist der Rechenzentrumsstandort, an dem der Bandbreiten-Richtliniendienst für die Anrufsteuerung ausgeführt wird. Mithilfe der Lync Server-Systemsteuerung können Sie Netzwerkregionen konfigurieren. Netzwerkregionen umfassen Einstellungen, mit denen definiert wird, ob für Audio- und Videoverbindungen alternative Pfade über das Internet zulässig sind. Über die Lync Server-Systemsteuerung können Sie eine Netzwerkregion erstellen, ändern oder löschen. Verwenden Sie dieses Thema zum Löschen vorhandener Netzwerkregionen. Ausführliche Informationen zum Erstellen oder Löschen vorhandener Netzwerkregionen finden Sie unter [Erstellen oder Ändern von Netzwerkregionen](lync-server-2013-creating-or-modifying-network-regions.md).

## So löschen Sie eine Netzwerkregion

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Region**.

4.  Klicken Sie auf der Seite **Region** auf die Region, die Sie löschen möchten.
    

    > [!NOTE]
    > Sie können mehrere Regionen in einem Arbeitsschritt löschen. Drücken Sie hierzu STRG, und wählen Sie bei gedrückter STRG-TASTE mehrere Regionen aus. Wenn Sie alle Regionen auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG>.



5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.
    

    > [!WARNING]
    > Eine Netzwerkregion kann nicht entfernt werden, wenn sie einem Netzwerkstandort zugeordnet ist. Wenn Sie versuchen, eine einem Standort zugeordnete Region zu entfernen, wird eine Fehlermeldung ausgegeben. Um zu überprüfen, ob eine Region einem Standort zugeordnet ist, wählen Sie die Region und klicken im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Details einblenden</STRONG>.



## Siehe auch

#### Aufgaben

[Erstellen oder Ändern von Netzwerkregionen](lync-server-2013-creating-or-modifying-network-regions.md)

