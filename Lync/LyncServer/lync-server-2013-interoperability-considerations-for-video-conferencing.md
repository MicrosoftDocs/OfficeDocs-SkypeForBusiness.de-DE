---
title: Überlegungen zur Interoperabilität von Videokonferenzen
TOCTitle: Überlegungen zur Interoperabilität von Videokonferenzen
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204790(v=OCS.15)
ms:contentKeyID: 49293603
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überlegungen zur Interoperabilität von Videokonferenzen

 

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

In diesem Abschnitt wird die Benutzererfahrung in der Koexistenzphase der Migration beschrieben, in der eine Interoperabilität zwischen Legacyclients und einem Lync Server 2013-Pool oder Lync Server 2013-Clients und einem Legacypool besteht.

## Lync Server 2013-Pools

Benutzer stellen das folgende Verhalten fest, wenn ein Legacyclient in einem Lync Server 2013-Pool verwendet wird:

  - Bei Gesprächen mit zwei Teilnehmern ist die Videoauflösung mit der im Legacypool identisch.

  - Bei Konferenzen mit mehreren Teilnehmern entsprechen Videoauflösung und Videokonferenzfeatures denen im Legacypool. Profilfotoansicht und hohe Auflösung sind nicht verfügbar.

## Legacypools

Benutzer stellen das folgende Verhalten fest, wenn ein Lync Server 2013-Client in einem Legacypool verwendet wird:

  - Bei Gesprächen mit zwei Teilnehmern können in Lync Server 2013-Clients die folgenden neuen Features verwendet werden:
    
      - H.264 ist verfügbar, wenn beide Teilnehmer Lync Server 2013-Clients verwenden.
    
      - Der Lync Server 2013-Client verwendet den Standardwert für **TotalReceiveVideoBitRateKb**, da der Legacyserver diese Informationen nicht mit In-Band-Bereitstellung sendet.

  - Bei Konferenzen mit mehreren Teilnehmern entsprechen Videoauflösung und Videokonferenzfeatures denen eines Legacyclients im Legacypool.


> [!NOTE]
> Wenn ein Legacyserver einen Lync Server 2013-Client hostet, können Sie die Videokonferenzbandbreite konfigurieren, sodass alle Benutzer im Pool nur Videos mit niedriger Auflösung erhalten, aber Videos mit hoher Auflösung senden. Beispielsweise kann <STRONG>MaxVideoRateAllowed</STRONG> in der Medienkonfiguration auf <STRONG>CIF-250K</STRONG> und <STRONG>VideoBitRateKb</STRONG> in der Konferenzrichtlinie auf <STRONG>2000 KBit/s</STRONG> festgelegt werden. Das Resultat in dieser Situation ist, dass für Benutzer im Pool keine hohe Auflösung möglich ist.<BR>Da <STRONG>MaxVideoRateAllowed</STRONG> nicht mehr für Lync Server 2013-Clients verwendet wird, kann nicht verhindert werden, dass Lync Server 2013-Clients Videos mit hoher Auflösung anfordern. Legen Sie stattdessen <STRONG>VideoBitRateKb</STRONG> in der Konferenzrichtlinie für alle Benutzer im Pool auf denselben Wert wie <STRONG>MaxVideoRateAllowed</STRONG> fest (d.&nbsp;h. CIF ist auf 250 KBit/s, VGA ist auf 600 KBit/s oder HD ist auf 1500 KBit/s festgelegt).


