---
title: Standortbasiertes Routing für Konferenzen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: Planung des standortbasierten Routings für Konferenzen in Skype for Business Server Enterprise-VoIP, einschließlich beratender Anruf Übertragungen.
ms.openlocfilehash: decfe8117b3b47c5de4db8a7d0963eca587d0da1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42130178"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Standortbasiertes Routing für Konferenzen in Skype for Business Server

Planung des standortbasierten Routings für Konferenzen in Skype for Business Server Enterprise-VoIP, einschließlich beratender Anruf Übertragungen.

Das standortbasierte Routing ermöglicht das Einschränken des Routings von anrufen zwischen VoIP-Endpunkten und PSTN-Endpunkten basierend auf dem Standort der Parteien im Anruf. Mit dem standortbasierten Routing für Konferenzen können Sie Standortbasierte Routingregeln für Besprechungen (also Konferenzen) erzwingen, um eine PSTN-Maut Umgehung zu verhindern. Die Anwendung überwacht eine aktive Konferenz und erzwingt standortbasierte Routing Einschränkungen basierend auf dem Speicherort der teilnehmenden Benutzer. Das standortbasierte Routing für die Konferenz Anwendung ermöglicht darüber hinaus die Durchsetzung von standortbasierten Routing Einschränkungen auf beratende Übertragungen mit PSTN-Endpunkten.

Die standortbasierte Routing Konferenz Anwendung bietet Skype for Business Konferenzen einen Mechanismus zur Verhinderung der PSTN-Maut Umgehung. Die Anwendung überwacht aktive Konferenzen und erzwingt standortbasierte Routing Einschränkungen basierend auf dem Speicherort der Skype for Business teilnehmenden Benutzer.

Die standortbasierte Routing Konferenz Anwendung bestimmt, ob das standortbasierte Routing für eine Skype for Business Besprechung erzwungen werden soll, wenn die folgenden Kriterien erfüllt sind:

- Der Besprechungsorganisator ist für das standortbasierte Routing aktiviert. Standortbasierte Routing Einschränkungen werden nur auf Konferenzen angewendet, die von Benutzern organisiert werden, die für das standortbasierte Routing aktiviert sind.

- Mindestens ein Besprechungsteilnehmer ist ein PSTN-Endpunkt. Standortbasierte Routing Einschränkungen gelten nur für Konferenzen, die PSTN-Endpunkte enthalten.

- Der Netzwerkstandort, an dem das PSTN-Gateway verwendet wurde, um die Konferenz mit dem PSTN zu überbrücken, befindet sich ebenso wie die Netzwerkstandorte, von denen die Organisatoren und Teilnehmer eine Verbindung herstellen.

Das standortbasierte Routing für die Konferenz Anwendung verhindert die Teilnahme von Skype for Business-und PSTN-Endpunkten von verschiedenen Netzwerkstandorten an dieselbe Konferenz. Wenn der Organisator einer Besprechung für das standortbasierte Routing aktiviert ist, erzwingt die Konferenz Anwendung die folgenden Einschränkungen:

- Die Endpunkte, die an einer Skype for Business Besprechung teilnehmen können, hängen von den Endpunkten ab, die bereits der Konferenz beigetreten sind, und diese Einschränkung wird angepasst, wenn Joined Endpoint Leave und neue Endpunkte der Konferenz beitreten. Wenn Organisatoren und Teilnehmern eine Skype for Business Besprechung vom gleichen Netzwerkstandort aus beitreten, dann ein PSTN-Endpunkt, ein weiterer Teilnehmer desselben Netzwerkstandorts, ein anderer Teilnehmer von einem anderen Netzwerkstandort oder ein Teilnehmer eines unbekannten Netzwerkstandorts. dürfen beitreten.

- Wenn Organisatoren und Teilnehmer von unterschiedlichen oder unbekannten Netzwerkstandorten aus an der Besprechung teilnehmen, kann ein PSTN-Endpunkt nicht an der Besprechung teilnehmen, wenn der PSTN-Anruf von einem für standortbasiertes Routing aktivierten SIP-Trunk abweicht.

- Wenn Organisatoren und Teilnehmer an der Besprechung vom gleichen Netzwerkstandort aus beitreten und Teilnehmer derselben Besprechung aus dem PSTN beitreten, kann ein Skype for Business Endpunkt von einem anderen Netzwerkstandort nicht an der Besprechung teilnehmen.

In der folgenden Tabelle sind die standortbasierten Routing Einschränkungen für Konferenzen zusammengefasst.

| |

|**Benutzer in einer Konferenz zu einem bestimmten Zeitpunkt**|**Benutzer dürfen an der Konferenz teilnehmen**|**Benutzer dürfen nicht an der Konferenz teilnehmen**|
|:-----|:-----|:-----|
|Skype for Business VoIP-Clientbenutzer (n) von einem einzelnen Netzwerkstandort  <br/> |Skype for Business VoIP-Clientbenutzer am gleichen Netzwerkstandort  <br/> Skype for Business VoIP-Clientbenutzer von einem anderen Netzwerkstandort  <br/> Skype for Business VoIP-Clientbenutzer von einem unbekannten Netzwerkstandort  <br/> Verbund Skype for Business VoIP-Clientbenutzer  <br/> Benutzer Beitritt von einem PSTN-Endpunkt  <br/> |Keine  <br/> |
|Skype for Business VoIP-Clientbenutzer (n) von einem unbekannten Netzwerkstandort  <br/> |Skype for Business VoIP-Clientbenutzer von einem beliebigen Standort aus  <br/> Skype for Business VoIP-Clientbenutzer von einer unbekannten Website  <br/> Verbund Skype for Business VoIP-Clientbenutzer  <br/> |Benutzer Beitritt über einen PSTN-Endpunkt  <br/> |
|Skype for Business von VoIP-Client Benutzern von verschiedenen Netzwerkstandorten  <br/> |Skype for Business VoIP-Clientbenutzer von einem beliebigen Netzwerkstandort aus  <br/> Skype for Business VoIP-Clientbenutzer von einem unbekannten Netzwerkstandort  <br/> Verbund Skype for Business VoIP-Clientbenutzer  <br/> |Benutzer Beitritt über einen PSTN-Endpunkt  <br/> |
|Skype for Business VoIP-Clientbenutzer von einem einzelnen Netzwerkstandort aus und Benutzer, die von einem PSTN-Endpunkt beitreten  <br/> |Skype for Business VoIP-Clientbenutzer am gleichen Netzwerkstandort  <br/> |Skype for Business VoIP-Clientbenutzer von einem anderen Netzwerkstandort  <br/> Skype for Business VoIP-Clientbenutzer von einem unbekannten Netzwerkstandort  <br/> Verbund Skype for Business VoIP-Clientbenutzer  <br/> |

Im folgenden sind zusätzliche Merkmale des standortbasierten Routing für die Konferenz Anwendung zu finden:

- Wenn ein Benutzer nicht an einer Konferenz teilnehmen darf, die standortbasierte Routing Einschränkungen hat, wird der Aufruf der Konferenz abgelehnt, und der Skype for Business-Client meldet, dass der Anruf nicht abgeschlossen oder beendet wurde.

- Ein PSTN-Endpunkt, der einer Konferenz mit standortbasierten Routing Erzwingungen Beitritt, wird nicht auf den Beitritt zur Konferenz beschränkt, unabhängig von seinem Status, wenn der Endpunkt über einen trunk Beitritt, der nicht für standortbasiertes Routing aktiviert ist.

- Ein Nebenstellen System, das mit einem Vermittlungsserver über einen SIP-Trunk verbunden ist, das keine ausgehende Anrufe an das PSTN ausführt, hat dieselben Erzwingungen wie Skype for Business Benutzer, die sich am selben Netzwerkstandort befinden, an dem der SIP-Trunk definiert ist. Beispielsweise kann ein PSTN-Endpunkt an einer Konferenz mit einem PBX-Benutzer und einem Skype for Business Benutzer teilnehmen, wenn Sie sich am selben Netzwerkstandort befinden; Andernfalls kann der PSTN-Endpunkt nicht an der Konferenz teilnehmen, wenn sich der PBX-Benutzer an einem anderen Netzwerkstandort als der Skype for Business Benutzer befindet.

> [!NOTE]
> Bei Skype for Business kumulativen Update 4 sollte das Verhalten in der folgenden Tabelle beachtet werden:

|**Benutzer**|**Andere Partei**|**Aktion**|**Ergebnis**|
|:-----|:-----|:-----|:-----|
|Skype for Business Mobil  <br/> |PSTN  <br/> |Skype for Business Mobile befindet sich in einem PSTN-Anruf. Skype for Business Mobile eskaliert dann den Anruf an eine automatische Telefonzentrale (CAA).  <br/> |Der Anruf wird mit einer entsprechenden Fehlermeldung blockiert.  <br/> |
|Skype for Business Mobil  <br/> |Skype for Business Client oder Verbundbenutzer  <br/> |Der Client-oder Verbundbenutzer befindet sich in einem VoIP-Anruf bei einem Skype for Business mobilen standortbasierten Routing Benutzer, und beide Parteien eskalieren an einen CAA.  <br/> |Der Eskalations Anruf wird mit einer entsprechenden Fehlermeldung blockiert.  <br/> |

## <a name="consultative-call-transfers"></a>Beratende Anruf Übertragungen

Zusätzlich zum Erzwingen eines standortbasierten Routings für Skype for Business Besprechungen erzwingt die standortbasierte Weiterleitung von Konferenzanwendungen standortbasierte Routing Einschränkungen für Anrufe, die an PSTN-Endpunkten austreten. Bei einer beratenden Anrufweiterleitung handelt es sich um einen Anruf zwischen zwei Parteien, bei dem eine der Parteien den Anruf an einen neuen Benutzer überträgt. Ein PSTN-Endpunkt ruft beispielsweise Benutzer a (Skype for Business aufgerufen) auf. Benutzer A bestimmt, dass der PSTN-Benutzer an Benutzer B (Skype for Business Benutzer) weitergeleitet werden soll. Benutzer a platziert den Anruf mit dem PSTN-Benutzer in der Warteschleife und ruft Benutzer b an, der mit dem PSTN-Benutzer zu sprechen akzeptiert. Der Benutzer a übergibt den Anruf einhalten an Benutzer B.

**Anruffluss für Anrufweiterleitung mit beratender Funktion**

![Standortbasiertes Routing für Konferenz Diagramm](../../media/LocationBasedRoutingForConferencing.jpg)

Wenn ein Benutzer, der für standortbasiertes Routing aktiviert ist, eine beratende Anrufweiterleitung eines PSTN-Endpunkts initiiert (wie in der obigen Abbildung dargestellt), werden zwei aktive Anrufe, ein Anruf zwischen dem PSTN-Benutzer und Skype for Business Benutzer a und der andere zwischen Skype for Geschäftsbenutzer a und Skype for Business Benutzer B. das folgende Verhalten wird durch die standortbasierte Weiterleitung für die Konferenz Anwendung erzwungen:

- Wenn das SIP-Trunk Routing der PSTN-Anruf autorisiert ist, den PSTN-Anruf an den Netzwerkstandort weiterzuleiten, auf dem sich Skype for Business Benutzer B (dh Übertragungsziel) befindet, wird die Anrufweiterleitung zugelassen. Andernfalls wird die beratende Anrufweiterleitung blockiert. Diese Autorisierung wird basierend auf dem Standort des übertragenen Teilnehmers am gleichen Netzwerkstandort wie der SIP-Trunk ausgeführt, der den aktiven Anruf an den PSTN-Endpunkt weiterleitet.

- Wenn das SIP-Trunk Routing des eingehenden PSTN-Anrufs nicht autorisiert ist, Anrufe an den Netzwerkstandort weiterzuleiten, auf dem sich der übertragene Teilnehmer (Skype for Business Benutzer B) befindet oder sich der übertragene Teilnehmer an einem unbekannten Netzwerkstandort befindet, wird die Anrufweiterleitung an der PSTN-Endpunkt (d. h. Anruf Übertragungsziel) wird blockiert.

In der folgenden Tabelle wird beschrieben, wie standortbasierte Routing Einschränkungen von der standortbasierten Weiterleitung für die Konferenz Anwendung für beratende Anruf Übertragungen angewendet werden. Obwohl PBX-Endpunkte keinem Netzwerkstandort direkt zugeordnet sind, kann dem SIP-Trunk, mit dem die Nebenstellenanlage verbunden ist, ein Netzwerkstandort zugewiesen werden. Daher kann der PBX-Endpunkt indirekt einem Netzwerkstandort zugeordnet werden.


|**Netzwerkstandort der Anruf übertragenden Partei**|**Netzwerkstandort des Anruf Übertragungs Ziels**|**Verhalten**|
|:-----|:-----|:-----|
|PSTN-Endpunkt  <br/> |Skype for Business Benutzer am selben Netzwerkstandort (also Standort 1)  <br/> |Beratende Übertragung wird zugelassen  <br/> |
|PSTN-Endpunkt  <br/> |Skype for Business Benutzer an unterschiedlichen Netzwerkstandorten (also Standort 2)  <br/> |Die beratende Übertragung wird nicht zugelassen.  <br/> |
|PSTN-Endpunkt  <br/> |Skype for Business Benutzer an einem unbekannten Netzwerkstandort  <br/> |Die beratende Übertragung wird nicht zugelassen.  <br/> |
|PSTN-Endpunkt  <br/> |Verbund Skype for Business Benutzer  <br/> |Die beratende Übertragung wird nicht zugelassen.  <br/> |
|PSTN-Endpunkt  <br/> |Nebenstellen Endpunkt am gleichen Standort (Standort 1)  <br/> |Beratende Übertragung wird zugelassen  <br/> |
|PSTN-Endpunkt  <br/> |Nebenstellen Endpunkt an verschiedenen Standorten (also Standort 2)  <br/> |Die beratende Übertragung wird nicht zugelassen.  <br/> |
|Nebenstellen Endpunkt am gleichen Standort (Standort 1)  <br/> |PSTN-Endpunkt  <br/> |Beratende Übertragung wird zugelassen  <br/> |
|Nebenstellen Endpunkt an einem anderen Standort (also Standort 2)  <br/> |PSTN-Endpunkt  <br/> |Die beratende Übertragung wird nicht zugelassen.  <br/> |
|PBX-Endpunkt an einem beliebigen Standort  <br/> |Skype for Business Benutzer am selben Netzwerkstandort (also Standort 1)  <br/> |Beratende Übertragung wird zugelassen  <br/> |
|PBX-Endpunkt an einem beliebigen Standort  <br/> |Skype for Business Benutzer an unterschiedlichen Netzwerkstandorten (also Standort 2)  <br/> |Beratende Übertragung wird zugelassen  <br/> |
|PBX-Endpunkt an einem beliebigen Standort  <br/> |Skype for Business Benutzer an einem unbekannten Netzwerkstandort  <br/> |Beratende Übertragung wird zugelassen  <br/> |
|PBX-Endpunkt an einem beliebigen Standort  <br/> |Verbund Skype for Business Benutzer  <br/> |Beratende Übertragung wird zugelassen  <br/> |

## <a name="requirements"></a>Anforderungen

Für das standortbasierte Routing für die Konferenz Anwendung ist es erforderlich, dass entweder Skype for Business Server oder lync Server 2013 Kumulatives Update 2 auf allen Front-End-Pools und Standard Edition-Servern in Ihrer Topologie bereitgestellt wird. Wenn diese Server Versionen nicht auf einigen Servern in Ihrer Topologie installiert sind, können standortbasierte Routing Einschränkungen nicht vollständig für Besprechungen und Anrufweiterleitungen erzwungen werden.

In der folgenden Tabelle ist die Kombination von Serverrollen und Versionen aufgeführt, die standortbasiertes Routing unterstützen.


|**Version des Front-End-Pools**|**Vermittlungsserver Version**|**Unterstützt**|
|:-----|:-----|:-----|
|Skype for Business Server oder lync Server 2013 Kumulatives Update 2  <br/> |Skype for Business Server oder lync Server 2013 Kumulatives Update 2  <br/> |Ja  <br/> |
|Lync Server 2013 Kumulatives Update 2  <br/> |Lync Server 2013 Kumulatives Update 1  <br/> |Nein  <br/> |
|Lync Server 2013 Kumulatives Update 2  <br/> |Lync Server 2010  <br/> |Nein  <br/> |
|Lync Server 2013 Kumulatives Update 2  <br/> |Office Communications Server 2007 R2  <br/> |Nein  <br/> |
|Lync Server 2013 Kumulatives Update 1  <br/> |Any  <br/> |Nein  <br/> |
|Lync Server 2010  <br/> |Any  <br/> |Nein  <br/> |
|Office Communications Server 2007 R2  <br/> |Any  <br/> |Nein  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>Konfiguration des standortbasierten Routing für Konferenzen

Das standortbasierte Routing für die Konferenz Anwendung beruht auf der Konfiguration des standortbasierten Routings. Die wichtigsten Konfigurationen lauten wie folgt:

- Die Position der Teilnehmer, die einer Besprechung beitreten, wird basierend auf dem Netzwerkstandort bestimmt. Ein Netzwerkstandort und die zugehörigen Netzwerk Subnetze müssen in Skype for Business Server definiert sein, um standortbasiertes Routing erzwingen zu können.

- Um das standortbasierte Routing von Besprechungen zu erzwingen, müssen Skype for Business Teilnehmer für das standortbasierte Routing aktiviert sein.

- Zum Erzwingen eines standortbasierten Routings von PSTN-Endpunkten, die Besprechungen beitreten, muss der SIP-Trunk, der zum Verbinden der PSTN-Endpunkte verwendet wird, für das standortbasierte Routing konfiguriert werden.

## <a name="enabling-the-location-based-routing-for-conferencing"></a>Aktivieren des standortbasierten Routing für Konferenzen

Die standortbasierte Weiterleitung für die Konferenz Anwendung ist standardmäßig deaktiviert. Vor dem Aktivieren dieser Anwendung müssen Sie die richtige Priorität bestimmen, die für die Anwendung zugewiesen werden soll. Um diese Priorität zu ermitteln, führen Sie das folgende Cmdlet in Skype for Business Server Management Shell aus:

Get-CsServerApplication-Identity Service: Registrar:<Pool FQDN>in diesem Cmdlet ist \<Pool FQDN\> der Pool, in dem die standortbasierte Weiterleitung für die Konferenz Anwendung aktiviert werden soll.

Dieses Cmdlet gibt die Liste der von Skype for Business Server gehosteten Anwendungen und den Prioritätswert für jeden von Ihnen zurück. Dem standortbasierten Routing für die Konferenz Anwendung muss ein Prioritätswert zugewiesen werden, der größer als die Anwendung "UdcAgent" und kleiner als die Anwendungen "DefaultRouting", "ExumRouting" und "OutboundRouting" ist. Es wird empfohlen, dem standortbasierten Routing für die Konferenz Anwendung einen Prioritätswert zuzuweisen, der einen Punkt höher ist als der Prioritätswert der Anwendung "UdcAgent".

Wenn die "UdcAgent"-Anwendung beispielsweise den Prioritätswert "2" hat, hat die "DefaultRouting"-Anwendung den Prioritätswert "8", die "ExumRouting"-Anwendung hat den Prioritätswert "9" und die "OutboundRouting"-Anwendung hat den Prioritätswert "10", dann Sie sollten dem standortbasierten Routing für die Konferenz Anwendung einen Prioritätswert von "3" zuweisen. Dadurch wird die Priorität der Anwendungen in der folgenden Reihenfolge platziert: andere Anwendungen (Prioritäten: 0 bis 1), "UdcAgent" (Priorität: 2), standortbasierte Routing Konferenz Anwendung (Priorität: 3), andere Anwendungen (Prioritäten: 4 bis 8), " DefaultRouting "(Priorität: 9)," ExumRouting "(Priorität: 10) und" OutboundRouting "(Priorität: 11).

Nachdem Sie den richtigen Prioritätswert für die Anwendung standortbasiertes Routing für Konferenzen gefunden haben, geben Sie das folgende Cmdlet für jeden Front-End-Pool oder Standard Edition-Server ein, für den Benutzer für standortbasiertes Routing aktiviert sind:

New-CsServerApplication-Identity Service: Registrar:`<Pool FQDN`>/lbrouting-Priority \<\> -Enabled $true-Critical $true-URI für Anwendungspriorität<https://www.microsoft.com/LCS/LBRouting> 

Zum Beispiel:

New-CsServerApplication-Identity Service:Registrar:ls2013cu2lbrpool. contoso. com/LBRouting-Priority 3-Enabled $true-Critical $true-URIhttps://www.microsoft.com/LCS/LBRouting 

Nachdem Sie dieses Cmdlet verwendet haben, starten Sie alle Front-End-Server im Pool oder die Standard Edition-Server neu, auf denen die standortbasierte Weiterleitung für die Konferenz Anwendung aktiviert wurde.

> [!IMPORTANT]
> Standortbasierte Routing-Erzwingungen zu Konferenzen oder beratenden Übertragungen werden erst durchgesetzt, wenn alle Front-End-Server in den entsprechenden Pools oder Standard Edition-Servern neu gestartet werden. Wenn Sie **-Critical** für **$true** in den vorangehenden Cmdlets festlegen, werden Ihre Skype for Business Server Dienste sofort neu gestartet. Wenn Sie nicht möchten, dass diese Dienste sofort neu gestartet werden **, legen Sie den Wert** für jetzt auf **$false** fest, und verwenden Sie dann " **CsServerApplication** ", um später nach dem Neustart der Dienste zu ändern **– kritisch** für **$true** .

Nachdem die standortbasierte Weiterleitung für die Konferenz Anwendung erfolgreich aktiviert wurde und alle entsprechenden Server neu gestartet wurden, werden alle Konferenzen, die von Skype for Business für standortbasiertes Routing aktivierten Benutzern organisiert wurden, überwacht, um zu verhindern PSTN-Maut Umgehung


