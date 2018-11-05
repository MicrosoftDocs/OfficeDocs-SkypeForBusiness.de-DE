---
title: Konfigurieren der Medienumgehung zur dauerhaften Umgehung des Vermittlungsservers
TOCTitle: Konfigurieren der Medienumgehung zur dauerhaften Umgehung des Vermittlungsservers
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425846(v=OCS.15)
ms:contentKeyID: 49293663
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der Medienumgehung zur dauerhaften Umgehung des Vermittlungsservers

 

_**Letztes Änderungsdatum des Themas:** 2013-02-25_


> [!NOTE]
> In diesem Thema wird davon ausgegangen, dass Sie die Medienumgehung für Trunkverbindungen mit einem Peer (PSTN-Gateway, IP-Nebenstellenanlage oder Session Border Controller [SBC] des Anbieters von Internettelefoniediensten [Internet Telephony Service Provider, ITSP]) bereits für einen bestimmten Standort oder Dienst konfiguriert haben, für den die Medienverarbeitung durch den Vermittlungsserver umgangen werden soll.<BR>Sie können keine dauerhafte Umgehung der Mediendatenverarbeitung durch den Vermittlungsserver konfigurieren, wenn Sie gleichzeitig die Anrufsteuerung (Call Admission Control, CAC) aktivieren. Diese Einstellungen sind inkompatibel, und deshalb schließen sich die Einstellungen in der Lync Server-Systemsteuerung gegenseitig aus.



Zusätzlich zur Aktivierung der Medienumgehung für einzelne Trunkverbindungen, die einem Peer zum Vermittlungsserver zugeordnet sind, müssen Sie auch die globalen Einstellungen für die Medienumgehung konfigurieren. Wenn Sie die globalen Einstellungen für die Medienumgehung mithilfe der in diesem Thema beschriebenen Schritte konfigurieren, wird von einer guten Konnektivität zwischen den Lync-Endpunkten und beliebigen Peers ausgegangen, für die Sie die Medienumgehung für Trunkverbindungen konfigurieren.

Wenn zwischen den Lync Server-Endpunkten und allen Peers zum Vermittlungsserver, deren Trunkverbindungen für die Medienumgehung aktiviert wurden, keine gute Konnektivität vorliegt, müssen Sie die globalen Einstellungen für die Medienumgehung so konfigurieren, dass bei Entscheidungen zur Medienumgehung Informationen zu Standorten und Regionen herangezogen werden. Auf diese Weise kann die Umgehung der Mediendatenverarbeitung durch den Vermittlungsserver besser gesteuert werden. Verwenden Sie für diese Konfiguration stattdessen die Schritte unter [Konfigurieren der globalen Einstellungen für die Medienumgehung zur Verwendung von Standort- und Regionsinformationen](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) und [Zuordnen eines Subnetzes zu einem Netzwerkstandort in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

## So aktivieren Sie die Medienumgehung global zur dauerhaften Umgehung des Vermittlungsservers

1.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3.  Doppelklicken Sie in der Liste auf die Konfiguration **Global**.

4.  Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Medienumgehung aktivieren**.

5.  Klicken Sie auf **Immer umgehen**.

6.  Klicken Sie auf **Commit**.

## Siehe auch

#### Konzepte

[Konfigurieren der Medienumgehung in Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Optionen für die globale Medienumgehung in Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
[Medienumgehung und Vermittlungsserver in Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)  

#### Weitere Ressourcen

[Planung der Medienumgehung in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

