---
title: Optionen für die globale Medienumgehung in Lync Server 2013
TOCTitle: Optionen für die globale Medienumgehung in Lync Server 2013
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398255(v=OCS.15)
ms:contentKeyID: 49293344
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Optionen für die globale Medienumgehung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_


> [!NOTE]
> In diesem Thema wird davon ausgegangen, dass Sie die Medienumgehung für Trunkverbindungen mit einem Peer (PSTN-Gateway, IP-Nebenstellenanlage oder Session Border Controller [SBC] des Anbieters von Internettelefoniediensten) bereits für einen bestimmten Standort oder Dienst konfiguriert haben, für den die Medienverarbeitung durch den Vermittlungsserver umgangen werden soll.



Zusätzlich zur Aktivierung der Medienumgehung für einzelne Trunkverbindungen, die einem Peer zugeordnet sind, müssen Sie die Medienumgehung auch global aktivieren. Über globale Einstellungen für die Medienumgehung können Sie entweder angeben, dass die Medienumgehung auf Anrufe über das Telefonfestnetz immer angewendet wird, oder dass die Medienumgehung auf der Grundlage von Zuordnungen von Subnetzen zu Netzwerkstandorten und Netzwerkregionen angewendet wird – ähnlich wie bei der Anrufsteuerung, einer anderen erweiterten VoIP-Funktion. Wenn sowohl die Medienumgehung als auch die Anrufsteuerung aktiviert wurden, werden die Informationen zu Netzwerkregionen, Netzwerkstandorten und Subnetzen, die für die Anrufsteuerung konfiguriert wurden, automatisch für Entscheidungen zur Verwendung der Medienumgehung herangezogen. Dies bedeutet, dass Sie die Medienumgehung nicht auf alle Anrufe über das Telefonfestnetz anwenden können, wenn die Anrufsteuerung aktiviert ist.

Im vorliegenden Thema wird beschrieben, wie Sie mithilfe der Lync Server-Systemsteuerung und der Lync Server-Verwaltungsshell die globalen Einstellungen für die Medienumgehung konfigurieren können.


> [!NOTE]
> Wenn Sie diese Schritte zum Konfigurieren der Medienumgehung verwenden, wird von einer guten Konnektivität zwischen Clients und dem Vermittlungsserverpeer ausgegangen (z.&nbsp;B. einem PSTN-Gateway, einer IP-Nebenstellenanlage oder einem SBC beim SIP-Trunking-Anbieter). Wenn für die Verbindung Bandbreiteneinschränkungen gelten, kann die Medienumgehung nicht auf den Anruf angewendet werden. Medienumgehung funktioniert nicht mit allen PSTN-Gateways, IP-Nebenstellenanlagen und SBCs. Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit IP-Nebenstellenanlagen von Cisco durchgeführt. Die Medienumgehung wird nur für die Produkte und Versionen unterstützt, die auf der Webseite für das Unified Communications Open Interoperability Program – Lync Server unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=214406%26clcid=0x407">http://go.microsoft.com/fwlink/?linkid=214406&amp;clcid=0x407</A> aufgelistet werden.



## Nächste Schritte: Auswählen von globalen Einstellungen für die Medienumgehung

Nachdem Sie für spezifische Standorte oder Dienste die Medienumgehung für beliebige Trunkverbindungen aktiviert haben, können Sie folgendermaßen fortfahren:

  - Aktivieren Sie die Medienumgehung dauerhaft, wie unter [Konfigurieren der Medienumgehung zur dauerhaften Umgehung des Vermittlungsservers](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md) beschrieben.

  - Oder konfigurieren Sie die Medienumgehung so, dass sie Standort-und Regionsinformationen verwendet, wie unter [Konfigurieren der globalen Einstellungen für die Medienumgehung zur Verwendung von Standort- und Regionsinformationen](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) beschrieben.

## Siehe auch

#### Aufgaben

[Konfigurieren eines Trunks mit Medienumgehung in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[Zuordnen eines Subnetzes zu einem Netzwerkstandort in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)  

#### Konzepte

[Konfigurieren der Medienumgehung in Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Medienumgehung und Vermittlungsserver in Lync Server 2013](lync-server-2013-media-bypass-and-mediation-server.md)

