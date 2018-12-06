---
title: Markieren einer MSPL-Serveranwendung (Microsoft SIP Processing Language) als kritisch oder nicht kritisch
TOCTitle: Markieren einer MSPL-Serveranwendung (Microsoft SIP Processing Language) als kritisch oder nicht kritisch
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182598(v=OCS.15)
ms:contentKeyID: 49295648
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Markieren einer MSPL-Serveranwendung (Microsoft SIP Processing Language) als kritisch oder nicht kritisch

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

MSPL-Serveranwendungen (Microsoft SIP Processing Language) sind Nur-Skript-Anwendungen, die anstelle der Microsoft Lync 2010-API eine Skriptsprache verwenden. Einige MSPL-Serveranwendungen werden als kritisch eingestuft. Wenn ein Skript als kritisch eingestuft wird, muss es beim Systemstart gestartet werden, damit Lync Server 2013 gestartet werden kann. Wenn während der Ausführung von Lync Server ein Fehler im Skript auftritt, wird der Server nicht heruntergefahren, er sendet jedoch keinen weiteren Datenverkehr an die Anwendung und schreibt Fehler in das Ereignisprotokoll.

Sie können mit der Lync Server-Systemsteuerung MSPL-Serveranwendungen als kritisch markieren oder die Markierung aufheben.

Nicht alle Skripts unterstützen diese Option. Beispielsweise ist das DefaultRouting-Skript als kritisch markiert, und diese Option kann für "DefaultRouting" nicht geändert werden.

## So markieren Sie eine MSPL-Serveranwendung als kritisch oder heben die Markierung auf

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer des Netzwerks an, in dem Sie Lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Serveranwendung**.

4.  Klicken Sie auf der Seite **Serveranwendung** auf eine Spaltenüberschrift, um die Anwendungen ggf. zu sortieren, und klicken Sie dann auf die Serveranwendung, die Sie ändern möchten.

5.  Klicken Sie auf **Aktion**.

6.  Klicken Sie auf **Als kritisch markieren** oder **Markierung aufheben** (sofern das Skript diese Option unterstützt).

## Siehe auch

#### Aufgaben

[Aktivieren oder Deaktivieren einer MSPL-Serveranwendung (Microsoft SIP Processing Language)](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  

#### Konzepte

[Anzeigen von MSPL-Serveranwendungen (Microsoft SIP Processing Language) in Lync Server 2013](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  

#### Weitere Ressourcen

[Verwalten der Lync Server 2013-Topologie](lync-server-2013-managing-the-lync-server-topology.md)

