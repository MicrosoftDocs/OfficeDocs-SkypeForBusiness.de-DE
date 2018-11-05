---
title: 'Lync Server 2013: Übersicht über die Medienumgehung'
TOCTitle: Übersicht über die Medienumgehung
ms:assetid: 9ea090b3-f607-46f7-97dd-2510052524e5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412740(v=OCS.15)
ms:contentKeyID: 49294916
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Übersicht über die Medienumgehung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Die Medienumgehung ist nützlich, wenn Sie die Anzahl von bereitgestellten Vermittlungsservern reduzieren möchten. Üblicherweise wird ein Vermittlungsserverpool an einem zentralen Standort bereitgestellt und steuert die Gateways an den Zweigstellenstandorten. Durch Aktivierung der Medienumgehung können Mediendaten für PSTN-Anrufe (Telefonfestnetz) von Clients an Zweigstellenstandorten direkt durch die Gateways an diesen Standorten geleitet werden. Lync Server 2013-Routen für ausgehende Anrufe und Enterprise-VoIP-Richtlinien müssen ordnungsgemäß konfiguriert sein, damit PSTN-Anrufe von Clients an einem Zweigstellenstandort zum richtigen Gateway geroutet werden.

In Wi-Fi-Netzwerken treten üblicherweise mehr Paketverluste auf als in verkabelten Netzwerken. Die Wiederherstellung der Daten aus diesen Paketen kann normalerweise nicht mithilfe von Gateways durchgeführt werden. Daher wird empfohlen, die Qualität eines Wi-Fi-Netzwerks auszuwerten, bevor Sie entscheiden, ob die Medienumgehung für ein Funksubnetz aktiviert werden soll. Darüber hinaus muss erwogen werden, ob eine geringere Latenz zu Lasten der Dateiwiederherstellung nach Paketverlusten akzeptabel ist. RTAudio - ein Codec für Anrufe, die den Vermittlungsserver nicht umgehen - eignet sich besser für die Verarbeitung von Paketverlusten.

Nachdem Sie die Enterprise-VoIP-Struktur eingerichtet haben, ist die Planung der Medienumgehung recht einfach.

  - Wenn Sie über eine zentralisierte Topologie ohne WAN-Verbindungen mit Zweigstellenstandorten verfügen, können Sie die globale Medienumgehung aktivieren, da eine genaue Steuerung nicht erforderlich ist.

  - Wenn Sie dagegen eine verteilte Topologie mit mehreren Netzwerkregionen und zugehörigen Zweigstellenstandorten eingerichtet haben, müssen Sie sich die folgenden Fragen stellen:
    
      - Können die Vermittlungsserverpeers die für die Medienumgehung erforderlichen Funktionen unterstützen?
    
      - Welche Standorte in den jeweiligen Netzwerkregionen verfügen über eine gute Verbindung?
    
      - Welche Kombination aus Medienumgehung und Anrufsteuerung eignet sich für Ihr Netzwerk?

Wenn Sie die Medienumgehung aktivieren, wird automatisch eine eindeutige Umgehungs-ID für eine Netzwerkregion und für alle Netzwerkstandorte ohne Bandbreiteneinschränkungen innerhalb dieser Region generiert. Standorte mit Bandbreiteneinschränkungen innerhalb der Region und Standorte, die über WAN-Verbindungen mit Bandbreiteneinschränkungen mit der Region verbunden sind, erhalten jeweils eine eigene eindeutige Umgehungs-IDs.

Wenn ein Benutzer einen Anruf an das PSTN tätigt, vergleicht der Vermittlungsserver die Umgehungs-ID des Clientsubnetzes mit der Umgehungs-ID des Gatewaysubnetzes. Wenn die beiden Umgehungs-IDs übereinstimmen, wird für den Anruf die Medienumgehung verwendet. Stimmen sie nicht überein, müssen die Medien für den Anruf durch den Vermittlungsserver fließen.

Erhält ein Benutzer einen Anruf aus dem PSTN, vergleicht der Client des Benutzers seine Umgehungs-ID mit der des PSTN-Gateways. Stimmen die beiden Umgehungs-IDs überein, werden die Medien direkt vom Gateway an den Client übermittelt und umgehen den Vermittlungsserver.

Nur Clients und Geräte ab Lync 2010 unterstützen die Interaktionen zur Medienumgehung mit einem Vermittlungsserver.


> [!IMPORTANT]
> Zusätzlich zur globalen Aktivierung der Medienumgehung müssen Sie die Medienumgehung auf jedem PSTN-Trunk einzeln aktivieren. Wenn die Umgehung zwar global, jedoch für einen bestimmten PSTN-Trunk nicht aktiviert wurde, wird sie für Anrufe über diesen PSTN-Trunk nicht ausgelöst. Darüber hinaus müssen Sie alle routingfähigen Subnetze den Standorten zuordnen, in denen sie sich befinden, wenn die Medienumgehung auf <STRONG>Informationen zu Standort und Region verwenden</STRONG> festgelegt ist. Routingfähige Subnetze in einem Standort, für den eine Medienumgehung nicht gewünscht wird, sollten vor Aktivierung der Umgehung in einem neuen Standort gruppiert werden. Auf diese Weise stellen Sie sicher, dass den nicht routingfähigen Subnetzen eine andere Umgehungs-ID zugewiesen wird.



## Siehe auch

#### Konzepte

[Modi für die Medienumgehung in Lync Server 2013](lync-server-2013-media-bypass-modes.md)  
[Medienumgehung und Anrufsteuerung in Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)  
[Technische Anforderungen für die Medienumgehung in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)

