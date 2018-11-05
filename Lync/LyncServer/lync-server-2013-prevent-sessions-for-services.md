---
title: Verhindern von Sitzungen für Dienste in Lync Server 2013
TOCTitle: Verhindern von Sitzungen für Dienste in Lync Server 2013
ms:assetid: 977dcc5c-2aac-48ef-86a1-a8d47b4d9e74
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182553(v=OCS.15)
ms:contentKeyID: 49294830
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verhindern von Sitzungen für Dienste in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Sie können die Lync Server-Systemsteuerung dazu verwenden, neue Sitzungen für alle Lync Server 2013-Dienste zu verhindern, die auf einem bestimmten Computer ausgeführt werden, oder um neue Sitzungen für einen bestimmten Lync Server 2013-Dienst zu verhindern.

## So verhindern Sie neue Sitzungen für alle Lync Server-Dienste auf einem Computer

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer des Netzwerks an, in dem Sie Lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.

4.  Sortieren oder durchsuchen Sie auf der Seite **Status** die Liste, um den Computer zu ermitteln, auf dem die Dienste ausgeführt werden, für die Sie neue Sitzungen verhindern möchten. Klicken Sie anschließend auf den Computer.

5.  Klicken Sie auf **Aktion**.

6.  Klicken Sie auf **Neue Sitzungen für alle Dienste verhindern**.

## So verhindern Sie neue Sitzungen für einen bestimmten Dienst

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer des Netzwerks an, in dem Sie Lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.

4.  Sortieren oder durchsuchen Sie die Liste auf der Seite **Status**, um den Computer zu ermitteln, auf dem der Dienst ausgeführt wird, den Sie starten oder beenden möchten. Klicken Sie anschließend auf den Computer.

5.  Klicken Sie auf **Eigenschaften**.

6.  Sortieren Sie ggf. die Liste der Dienste, und klicken Sie auf den Dienst, für den Sie neue Sitzungen verhindern möchten.

7.  Klicken Sie auf **Aktion**.

8.  Klicken Sie auf **Neue Sitzungen für Dienst verhindern**.

9.  Klicken Sie auf **Schließen**.

## Siehe auch

#### Weitere Ressourcen

[Verwalten der Lync Server 2013-Topologie](lync-server-2013-managing-the-lync-server-topology.md)

