---
title: Konfigurieren der globalen Einstellungen für die Medienumgehung zur Verwendung von Standort- und Regionsinformationen
TOCTitle: Konfigurieren der globalen Einstellungen für die Medienumgehung zur Verwendung von Standort- und Regionsinformationen
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398150(v=OCS.15)
ms:contentKeyID: 49293119
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der globalen Einstellungen für die Medienumgehung zur Verwendung von Standort- und Regionsinformationen

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_


> [!NOTE]
> In diesem Thema wird davon ausgegangen, dass Sie die Medienumgehung bereits für Trunkverbindungen zwischen dem Vermittlungsserver und einem Peer (PSTN)-Gateway, einer IP-Nebenstellenanlage oder dem Session Border Controller (SBC) eines Anbieters von Internettelefoniediensten (ITSP) für einen bestimmten Standort oder Dienst konfiguriert haben, für den die Medienverarbeitung durch den Vermittlungsserver umgangen werden soll.<BR>In diesem Thema wird außerdem angenommen, dass Sie alle zentralen Standorte und Zweigstellenstandorte im Topologie-Generator so konfiguriert haben, dass sie der Konfiguration für Netzwerkregion, Netzwerkstandort und Subnetz entsprechen, die Sie gemäß den Schritten in <A href="lync-server-2013-create-or-modify-a-network-region.md">Erstellen oder Ändern einer Netzwerkregion in Lync Server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">Erstellen oder Ändern eines Netzwerkstandorts in Lync Server 2013</A> und <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Zuordnen eines Subnetzes zu einem Netzwerkstandort in Lync Server 2013</A> durchgeführt haben. Falls die Konfigurationen nicht übereinstimmen, ist die Medienumgehung nicht erfolgreich.



Zusätzlich zur Aktivierung der Medienumgehung für einzelne Trunkverbindungen, die einem Peer zugeordnet sind, müssen Sie auch die globalen Einstellungen konfigurieren. Wenn Sie die globalen Einstellungen für die Medienumgehung anhand der hier beschriebenen Schritte durchführen, wird vorausgesetzt, dass eine der folgenden Bedingungen für Ihre Konfiguration zutrifft:

  - Es besteht *keine* gute Verbindung zwischen Lync Server-Endpunkten und beliebigen Peers, für die Sie eine Medienumgehung für die Trunkverbindung konfiguriert haben.

  - Die Anrufsteuerung (Call Admission Control, CAC) zur Bandbreitenverwaltung ist aktiviert.
    

    > [!NOTE]
    > Ausführliche Informationen zu den Überlegungen im Hinblick auf Anrufsteuerung und Medienumgehung finden Sie im Abschnitt zur Anrufsteuerung von PSTN-Verbindungen unter <A href="lync-server-2013-media-bypass-and-mediation-server.md">Medienumgehung und Vermittlungsserver in Lync Server 2013</A> in der Planungsdokumentation.



Die Informationen zu Netzwerkregionen und Netzwerkstandorten werden sowohl für die Anrufsteuerung als auch für die Medienumgehung verwendet, wenn beide der erweiterten Enterprise-VoIP-Funktionen aktiviert sind. Wenn Sie daher die Anrufsteuerung bereits konfiguriert haben, müssen Sie das folgende Verfahren zum Bearbeiten von Standort- und Regioneninformationen nicht speziell für die Medienumgehung ausführen. Führen Sie die Schritte des folgenden Verfahrens aus, wenn Sie noch keine Netzwerkregionen und Standorte für die Anrufsteuerung konfiguriert haben und die Einstellungen für die Medienumgehung ändern möchten.

Oder führen Sie diese Schritte aus, wenn die Informationen zu Standorten und Regionen für Entscheidungen zur Medienumgehung herangezogen werden sollen, Sie jedoch nicht die Anrufsteuerung aktivieren möchten. In diesem Fall müssen Verbindungen mit Bandbreitenbeschränkungen weiterhin mithilfe von standortübergreifenden Netzwerkrichtlinien angegeben werden, wie beschrieben unter [Erstellen von standortübergreifenden Netzwerkrichtlinien in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md). Die tatsächlichen Bandbreiteneinschränkungen sind hierbei weniger wichtig, da die Anrufsteuerung nicht aktiviert wurde. Stattdessen werden diese Verbindungen zur Partitionierung von Subnetzen verwendet, um Verbindungen mit Bandbreitenbeschränkungen anzugeben, die für die Medienumgehung eingesetzt werden können. Beachten Sie, dass dies auch gilt, wenn sowohl die Anrufsteuerung als auch die Medienumgehung aktiviert wurden.

Zur ordnungsgemäßen Funktion der Medienumgehung muss die Definition eines Standorts im Topologie-Generator mit dessen Definition in der Konfiguration von Netzwerkregionen und Netzwerkstandorten konsistent sein. Wenn Sie beispielsweise über einen Zweigstellenstandort verfügen, den Sie im Topologie-Generator als einen Standort mit nur einem PSTN-Gateway angegeben haben, dann muss dieser Zweigstellenstandort mit einer Enterprise-VoIP-Richtlinie konfiguriert werden, die es Zweigstellenbenutzern erlaubt, dass ihre PSTN-Anrufe über das PSTN-Gateway am Zweigstellenstandort geroutet werden.

## So konfigurieren Sie Informationen zu Standorten und Regionen für die Medienumgehung

1.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3.  Doppelklicken Sie in der Tabelle auf die Konfiguration **Global**.

4.  Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Medienumgehung aktivieren**.

5.  Klicken Sie auf **Konfiguration von Standorten und Regionen verwenden**.

6.  Falls erforderlich, aktivieren Sie das Kontrollkästchen **Umgehung für nicht zugeordnete Standorte aktivieren**.
    

    > [!NOTE]
    > Aktivieren Sie dieses Kontrollkästchen nur dann, wenn Sie über einen oder mehrere große Standorte ohne Bandbreiteneinschränkungen verfügen (z.&nbsp;B. ein großer Hauptstandort), die einer bestimmten Region zugeordnet sind, und Sie außerdem über einige Zweigstellen mit Bandbreiteneinschränkungen verfügen, die derselben Region zugeordnet sind. Wenn Sie die Umgehung für nicht zugeordnete Standorte aktivieren, wird die Konfiguration optimiert, da Sie nur die den Zweigstandorten zugeordneten Subnetze angeben, statt sämtliche, allen Standorten zugeordnete Subnetze angeben zu müssen. Es wird empfohlen, dieses Kontrollkästchen nicht zu aktivieren, wenn die Anrufsteuerung aktiviert wurde.



7.  Klicken Sie auf **Commit**.

Fügen Sie anschließend Subnetze zum Netzwerkstandort hinzu, wie in [Zuordnen von Subnetzen zu Netzwerkstandorten für die Medienumgehung](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md) beschrieben. (Die tatsächlich durchzuführenden Schritte zum Zuordnen von Subnetzen zu Netzwerkstandorten werden im Abschnitt [Zuordnen eines Subnetzes zu einem Netzwerkstandort in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) beschrieben.) Nachdem Sie alle Subnetze zu Netzwerkstandorten zugeordnet haben, ist die Bereitstellung der Medienumgehung abgeschlossen.


> [!IMPORTANT]
> Wenn Sie noch keine Netzwerkregionen und Netzwerkstandorte erstellt haben, müssen Sie dies nachholen, bevor Sie mit der Bereitstellung der Medienumgehung fortfahren können. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-create-or-modify-a-network-region.md">Erstellen oder Ändern einer Netzwerkregion in Lync Server 2013</A> und <A href="lync-server-2013-create-or-modify-a-network-site.md">Erstellen oder Ändern eines Netzwerkstandorts in Lync Server 2013</A>.



## Siehe auch

#### Konzepte

[Zuordnen von Subnetzen zu Netzwerkstandorten für die Medienumgehung](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)

