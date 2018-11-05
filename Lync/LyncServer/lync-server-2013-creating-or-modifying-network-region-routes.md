---
title: Erstellen oder Ändern von Netzwerkregionsrouten
TOCTitle: Erstellen oder Ändern von Netzwerkregionsrouten
ms:assetid: 76993daa-76c2-4cec-8363-de8aebef0145
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg521016(v=OCS.15)
ms:contentKeyID: 49294456
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern von Netzwerkregionsrouten

 

_**Letztes Änderungsdatum des Themas:** 2012-10-08_

Jede Region mit konfigurierter Anrufsteuerung muss über eine Möglichkeit verfügen, auf jede andere Region zuzugreifen. Während die Regionenverbindungen Bandbreiteneinschränkungen für Verbindungen zwischen Regionen festlegen und auch die physischen Verbindungen darstellen, bestimmt eine Route, welchen Pfad die Verbindung von einer Region zur anderen nimmt. Mithilfe der Lync Server-Systemsteuerung können Sie Netzwerkregionenrouten konfigurieren. Über die Lync Server-Systemsteuerung können Sie eine Netzwerkregionenroute erstellen, ändern oder löschen. Ausführliche Informationen zum Löschen bestehender Netzwerkregionenrouten finden Sie unter [Löschen von vorhandenen Netzwerkregionsrouten](lync-server-2013-deleting-existing-network-region-routes.md).

## So erstellen Sie eine Netzwerkregionenroute

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regionenroute**.

4.  Klicken Sie auf der Seite **Regionenroute** auf **Neu**.

5.  Geben Sie im Abschnitt **Neue Regionenroute** im Feld **Name** einen Wert ein.
    

    > [!NOTE]
    > Dieser Wert muss innerhalb der Microsoft Lync Server 2013-Bereitstellung eindeutig sein.



6.  Wählen Sie in der Dropdownliste **Netzwerkregion 1** eine der zwei Regionen aus, die über diese Route verbunden werden sollen.

7.  Wählen Sie in der Dropdownliste **Netzwerkregion 2** die andere Region für diese Route aus. Diese Region muss sich von der für Netzwerkregion 1 ausgewählten Region unterscheiden.

8.  Fügen Sie der Route über das Listenfeld **Netzwerkregionenverbindungen** Regionenverbindungen hinzu. Klicken Sie auf die Schaltfläche **Hinzufügen**, um die Seite **Regionenverbindung** anzuzeigen. Klicken Sie auf eine Regionenverbindung, die Sie dieser Route hinzufügen möchten, und klicken Sie anschließend auf **OK**.
    

    > [!NOTE]
    > Klicken Sie erneut auf die Schaltfläche <STRONG>Hinzufügen</STRONG>, um weitere Verbindungen hinzuzufügen, oder wählen Sie eine Verbindung aus, und klicken Sie auf <STRONG>Entfernen</STRONG>, um eine Verbindung zu entfernen.



9.  Klicken Sie auf **Commit**.

## So ändern Sie eine Netzwerkregionenroute

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regionenroute**.

4.  Klicken Sie auf der Seite **Regionenroute** auf die Regionenroute, die Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  In **Regionenroute bearbeiten** können Sie die über diese Route verbundenen Regionen und die der Route zugeordneten Regionenverbindungen ändern.

7.  Klicken Sie auf **Commit**.

## Siehe auch

#### Aufgaben

[Löschen von vorhandenen Netzwerkregionsrouten](lync-server-2013-deleting-existing-network-region-routes.md)

