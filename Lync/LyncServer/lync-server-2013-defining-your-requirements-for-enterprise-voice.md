---
title: 'Lync Server 2013: Definieren der Enterprise-VoIP-bezogenen Anforderungen für Ihr Unternehmen'
TOCTitle: Definieren der Enterprise-VoIP-bezogenen Anforderungen für Ihr Unternehmen
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425826(v=OCS.15)
ms:contentKeyID: 49293615
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definieren der Enterprise-VoIP-bezogenen Anforderungen für Ihr Unternehmen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-08-07_

Das vorliegende Thema bietet einen Überblick über die Überlegungen, die Sie im Hinblick auf Regionen, Standorte und die Standortverknüpfungen in Ihrer Topologie anstellen müssen, wenn Sie Enterprise-VoIP bereitstellen. Ausführliche Informationen zu diesen Überlegungen finden Sie unter [Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Funktionen in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) in der Planungsdokumentation.

## Standorte und Regionen

Zunächst identifizieren Sie die Standorte in Ihrer Topologie, an denen Sie Enterprise-VoIP bereitstellen, sowie die Netzwerkregionen, denen diese Standorte angehören. Insbesondere müssen Sie überlegen, wie die PSTN-Anbindung (Public Switched Telephone Network) für jeden Standort implementiert wird. Die Zuweisung von Standorten zu Regionen kann aus verwaltungstechnischer und logistischer Sicht ein entscheidender Faktor sein. Sie müssen entscheiden, wo Gateways lokal bereitgestellt, wo Survivable Branch-Anwendungen (SBAs)bereitgestellt und wo Sie SIP-Trunks (entweder lokal oder am zentralen Standort) mit einem Anbieter von Internettelefoniediensten (Internet Telephony Service Provider, ITSP) bereitstellen können.

## Netzwerkverbindungen zwischen Standorten

Sie müssen außerdem die Bandbreitennutzung berücksichtigen, die Sie für die Netzwerkverbindungen zwischen Ihrem zentraler Standort und den Zweigstellenn erwarten. Wenn Sie die Bereitstellung ausfallsicherer WAN-Verbindungen planen, wird die Bereitstellung eines Gateways in jeder Zweigstelle empfohlen, um eine lokale DID-Terminierung (Direct Inward Dialing) für Benutzer an diesen Standorten bereitzustellen. Wenn Sie über ausfallsichere WAN-Verbindungen verfügen, die Bandbreite einer WAN-Verbindung jedoch wahrscheinlich eingeschränkt ist, konfigurieren Sie die Anrufsteuerung für diese Verbindung. Wenn keine ausfallsicheren WAN-Verbindungen zur Verfügung stehen, weniger als 1.000 Benutzer in der Zweigstelle verwaltet werden und lokal keine geschulten Lync Server-Administratoren verfügbar sind, wird die Bereitstellung einer Survivable Branch-Anwendung in der Zweigstelle empfohlen. Wenn in der Zweigstelle zwischen 1.000 und 5.000 Benutzer verwaltet werden, keine ausfallsichere WAN-Verbindung vorhanden ist und geschulte Lync Server-Administratoren verfügbar sind, wird die Bereitstellung eines Survivable Branch-Servers mit einem kleinen Gateway in der Zweigstelle empfohlen. Erwägen Sie auch die Aktivierung der Medienumgehung für Verbindungen mit eingeschränkter Bandbreite, wenn Sie über ein Gatewaypeer mit Unterstützung der Medienumgehung verfügen.

## Siehe auch

#### Konzepte

[Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Funktionen in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)

