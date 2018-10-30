---
title: Starten oder Beenden von Lync Server 2013-Diensten
TOCTitle: Starten oder Beenden von Lync Server 2013-Diensten
ms:assetid: 1c70b4ec-9de5-4f7a-a3c9-c0eb76710505
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg520958(v=OCS.15)
ms:contentKeyID: 49293351
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Starten oder Beenden von Lync Server 2013-Diensten

 

_**Letztes Änderungsdatum des Themas:** 2014-02-05_

Sie können die Lync Server-Systemsteuerung dazu verwenden, alle Lync Server 2013-Dienste zu starten oder zu beenden, die auf einem bestimmten Computer ausgeführt werden, oder um einen bestimmten Dienst zu starten oder zu beenden.

## So starten oder beenden Sie alle Lync Server-Dienste auf einem Computer

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer des Netzwerks an, in dem Sie Lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.

4.  Sortieren oder durchsuchen Sie die Liste auf der Seite **Status**, und ermitteln Sie so den Computer, auf dem die Dienste ausgeführt werden, die Sie starten oder beenden möchten. Klicken Sie anschließend auf den Computer.

5.  Klicken Sie auf **Aktion**.

6.  Klicken Sie auf **Alle Dienste starten** bzw. auf **Alle Dienste beenden**.

## So starten oder beenden Sie einen bestimmten Dienst

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Status**.

4.  Sortieren oder durchsuchen Sie die Liste auf der Seite **Status**, um den Computer zu ermitteln, auf dem der Dienst ausgeführt wird, den Sie starten oder beenden möchten. Klicken Sie anschließend auf den Computer.

5.  Klicken Sie auf **Eigenschaften**.

6.  Sortieren Sie ggf. die Liste der Dienste, und klicken Sie auf den Dienst, den Sie starten oder beenden möchten.

7.  Klicken Sie auf **Aktion**.

8.  Klicken Sie auf **Dienst starten** bzw. auf **Dienst beenden**.

9.  Klicken Sie auf **Schließen**.

## Siehe auch

#### Aufgaben

[Verhindern von Sitzungen für Dienste in Lync Server 2013](lync-server-2013-prevent-sessions-for-services.md)  

#### Weitere Ressourcen

[Verwalten der Lync Server 2013-Topologie](lync-server-2013-managing-the-lync-server-topology.md)

