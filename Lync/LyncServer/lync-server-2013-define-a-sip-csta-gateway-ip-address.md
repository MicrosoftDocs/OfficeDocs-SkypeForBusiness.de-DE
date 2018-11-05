---
title: 'Lync Server 2013: Definieren der IP-Adresse für ein SIP/CSTA-Gateway'
TOCTitle: Definieren der IP-Adresse für ein SIP/CSTA-Gateway
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg602125(v=OCS.15)
ms:contentKeyID: 49295087
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definieren der IP-Adresse für ein SIP/CSTA-Gateway in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Wenn Lync Server eine Verbindung mit dem SIP/CSTA-Gateway herstellt, das Sie für die Remoteanrufsteuerung mithilfe einer TCP-Verbindung (Transmission Control Protocol) bereitgestellt haben, müssen Sie die IP-Adresse des Gateways im Topologie-Generator definieren. Dieser Schritt ist für Gateways, die TLS-Verbindungen (Transport Layer Security) unterstützen, nicht erforderlich. Für Gateways, die TLS-Verbindungen unterstützen, können Sie dieses Verfahren überspringen und die Bereitstellung der Remoteanrufsteuerung fortsetzen, indem Sie die Schritte unter [Aktivieren von Lync-Benutzern für die Remoteanrufsteuerung in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md) ausführen.

## So definieren Sie die IP-Adresse des SIP/CSTA-Gateways mithilfe des Topologie-Generators

1.  Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

2.  Starten des Topologie-Generators: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.

3.  Wählen Sie die Option zum Herunterladen einer vorhandenen Topologie.

4.  Erweitern Sie den Knoten **Vertrauenswürdige Anwendungsserver** .

5.  Klicken Sie mit der rechten Maustaste auf den vertrauenswürdigen Anwendungspool, den Sie gemäß [Konfigurieren eines Eintrags einer vertrauenswürdigen Anwendung für die Remoteanrufsteuerung in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md) erstellt haben, und klicken Sie dann auf **Eigenschaften bearbeiten** .

6.  Deaktivieren Sie das Kontrollkästchen **Replikation von Konfigurationsdaten in diesen Pool aktivieren** .

7.  Klicken Sie auf **Dienstverwendung auf ausgewählte IP-Adressen begrenzen** . Die Standardeinstellung ist **Alle konfigurierten IP-Adressen verwenden** .

8.  Geben Sie in das Textfeld **Primäre IP-Adresse** die IP-Adresse des SIP/CSTA-Gateways ein.

9.  Klicken Sie zum Aktualisieren der Topologie im zentralen Verwaltungsspeicher in der Konsolenstruktur auf **Lync Server 2010** , und klicken Sie dann im Bereich **Aktionen** auf **Veröffentlichen** .

## Siehe auch

#### Aufgaben

[Konfigurieren einer statischen Route für die Remoteanrufsteuerung in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[Konfigurieren eines Eintrags einer vertrauenswürdigen Anwendung für die Remoteanrufsteuerung in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)

