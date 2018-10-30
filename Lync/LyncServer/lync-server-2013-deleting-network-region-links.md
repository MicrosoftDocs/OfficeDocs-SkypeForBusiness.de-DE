---
title: Löschen von Netzwerkregionenverbindungen
TOCTitle: Löschen von Netzwerkregionenverbindungen
ms:assetid: 839273cd-d23f-4b38-84e6-d2dc972f49cd
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688114(v=OCS.15)
ms:contentKeyID: 49890815
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen von Netzwerkregionenverbindungen

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Sie können im Rahmen der Anrufsteuerung Verbindungen zwischen zwei Netzwerkregionen konfigurieren. Regionen in einem Netzwerk sind über eine physische WAN-Verbindung (Wide Area Network, Fernnetz) verbunden. Sie können die Lync Server-Systemsteuerung verwenden, um eine vorhandene Verbindung zwischen zwei Netzwerkregionen zu löschen. Ausführliche Informationen zum Erstellen oder Änderungen von Verbindungen zwischen Netzwerkregionen finden Sie unter [Konfigurieren von Netzwerkregionenverbindungen](lync-server-2013-configuring-network-region-links.md)

## So löschen Sie eine Netzwerkregionenverbindung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regionenverbindung**.

4.  Klicken Sie auf der Seite **Regionenverbindung** auf die Regionenverbindung, die Sie löschen möchten.
    

    > [!NOTE]
    > Sie können mehrere Regionenverbindungen in einem Arbeitsschritt löschen. Drücken Sie hierzu die STRG-TASTE, und wählen Sie bei gedrückter STRG-TASTE mehrere Netzwerkregionen aus. Wenn Sie alle Netzwerkregionen auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG>.



5.  Wählen Sie im Menü **Bearbeiten** die Option **Löschen** aus.

6.  Klicken Sie auf **OK**.

## Siehe auch

#### Aufgaben

[Konfigurieren von Netzwerkregionenverbindungen](lync-server-2013-configuring-network-region-links.md)

