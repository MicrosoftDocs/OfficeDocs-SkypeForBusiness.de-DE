---
title: Aktivieren oder Deaktivieren einer MSPL-Serveranwendung (Microsoft SIP Processing Language)
TOCTitle: Aktivieren oder Deaktivieren einer MSPL-Serveranwendung (Microsoft SIP Processing Language)
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182573(v=OCS.15)
ms:contentKeyID: 49295130
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren oder Deaktivieren einer MSPL-Serveranwendung (Microsoft SIP Processing Language)

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Sie können mithilfe der Lync Server-Systemsteuerung MSPL-Serveranwendungen (Microsoft SIP Processing Language) aktivieren oder deaktivieren, die in Ihrer Lync Server 2013-Umgebung ausgeführt werden. Bei diesen Anwendungen handelt es sich um Nur-Skript-Anwendungen, die anstelle der Microsoft Lync 2013 Preview-API eine Skriptsprache verwenden.

Nicht alle Skripts können aktiviert oder deaktiviert werden. Beispielsweise ist das DefaultRouting-Skript aktiviert, und diese Option kann für "DefaultRouting" nicht geändert werden.

## So aktivieren oder deaktivieren Sie eine MSPL-Serveranwendung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer des Netzwerks an, in dem Sie Lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Serveranwendung**.

4.  Klicken Sie auf der Seite **Serveranwendung** auf eine Spaltenüberschrift, um die Anwendungen ggf. zu sortieren, und klicken Sie dann auf die Serveranwendung, die Sie ändern möchten.

5.  Klicken Sie auf **Aktion**.

6.  Klicken Sie auf **Anwendung aktivieren** oder **Anwendung deaktivieren** (sofern das Skript diese Option unterstützt).

## Siehe auch

#### Aufgaben

[Markieren einer MSPL-Serveranwendung (Microsoft SIP Processing Language) als kritisch oder nicht kritisch](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  

#### Konzepte

[Anzeigen von MSPL-Serveranwendungen (Microsoft SIP Processing Language) in Lync Server 2013](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  

#### Weitere Ressourcen

[Verwalten der Lync Server 2013-Topologie](lync-server-2013-managing-the-lync-server-topology.md)

