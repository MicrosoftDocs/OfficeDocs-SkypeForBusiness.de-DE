---
title: Standortbasiertes Routing für Konferenzen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: Planung für standortbasiertes Routing für Konferenzen in Skype for Business Server Enterprise-VoIP, einschließlich beratender Anruf Übertragungen.
ms.openlocfilehash: d9ca03920fe361cf4d7692fd80031bef01b03b17
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276782"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Standortbasiertes Routing für Konferenzen in Skype for Business Server

Planung für standortbasiertes Routing für Konferenzen in Skype for Business Server Enterprise-VoIP, einschließlich beratender Anruf Übertragungen.

Standortbasiertes Routing ermöglicht das Einschränken des Routings von anrufen zwischen VoIP-Endpunkten und PSTN-Endpunkten basierend auf dem Standort der Gesprächspartner. Standortbasiertes Routing für Konferenzen ermöglicht es Ihnen, standortbasierte Routingregeln für Besprechungen (d. h. Konferenzen) zu erzwingen, um eine PSTN-Maut Umgehung zu verhindern. Die Anwendung überwacht eine aktive Konferenz und erzwingt standortbasierte Routing Einschränkungen basierend auf dem Standort der teilnehmenden Benutzer. Die Anwendung standortbasiertes Routing für Konferenz ermöglicht zudem die Erzwingung standortbasierter Routing Einschränkungen für beratende Übertragungen mit PSTN-Endpunkten.

Die standortbasierte Routing Konferenz Anwendung bietet Skype for Business-Konferenzen einen Mechanismus zur Verhinderung der PSTN-Maut Umgehung. Die Anwendung überwacht aktive Konferenzen und erzwingt standortbasierte Routing Einschränkungen basierend auf dem Standort der teilnehmenden Skype for Business-Benutzer.

Die standortbasierte Routing Konferenz Anwendung bestimmt, ob standortbasiertes Routing in einer Skype for Business-Besprechung erzwungen werden soll, wenn die folgenden Kriterien erfüllt sind:

- Der Besprechungsorganisator ist für standortbasiertes Routing aktiviert. Standortbasierte Routing Einschränkungen werden nur auf Konferenzen angewendet, die von Benutzern organisiert werden, die für standortbasiertes Routing aktiviert sind.

- Mindestens ein Besprechungsteilnehmer befindet sich an einem Endpunkt im öffentlichen Telefonnetz (PSTN). Standortbasierte Routing Einschränkungen gelten nur für Konferenzen, die PSTN-Endpunkte umfassen.

- Der Netzwerkstandort, an dem sich das PSTN-Gateway zum Überbrücken der Konferenz in das PSTN befindet, wird ebenso lokalisiert wie die Netzwerkstandorte, von denen aus die Organisatoren und Teilnehmer die Verbindung herstellen.

Die Anwendung standortbasiertes Routing für Konferenz verhindert die Teilnahme von Skype for Business-Benutzern und PSTN-Endpunkten von verschiedenen Netzwerkstandorten an derselben Konferenz. Wenn der Organisator einer Besprechung für standortbasiertes Routing aktiviert ist, erzwingt die Konferenz Anwendung die folgenden Einschränkungen:

- Die Endpunkte, die an einer Skype for Business-Besprechung teilnehmen können, hängen von den Endpunkten ab, die bereits der Konferenz beigetreten sind, und diese Einschränkung passt sich an, wenn verknüpfte Endpunkte verlassen und neue Endpunkte der Konferenz beitreten Wenn Organisatoren und Teilnehmer an einer Skype for Business-Besprechung von derselben Netzwerk Website, einem PSTN-Endpunkt, einem anderen Teilnehmer desselben Netzwerkstandorts, einem anderen Teilnehmer von einer anderen Netzwerk Website oder einem Teilnehmer von einer unbekannten Netzwerk Website teilnehmen dürfen teilnehmen.

- Wenn Organisatoren und Teilnehmer von unterschiedlichen oder unbekannten Netzwerkstandorten aus an der Besprechung teilnehmen, darf ein Teilnehmer an einem PSTN-Endpunkt nicht an der Besprechung teilnehmen, wenn der PSTN-Anruf von einem SIP-Trunk eingeht, der für das standortbasierte Routing aktiviert ist.

- Wenn Organisatoren und Teilnehmer alle an der Besprechung von der gleichen Netzwerk Website teilnehmen und Teilnehmer der gleichen Besprechung über das PSTN beitreten, ist ein Skype for Business-Endpunkt von einer anderen Netzwerk Website nicht berechtigt, an der Besprechung teilzunehmen.

In der folgenden Tabelle sind diese standortbasierten Routing Einschränkungen für Konferenzen zusammengefasst.

| |

|**Benutzer in einer Konferenz an einem beliebigen Standort**|**Benutzer, die an der Konferenz teilnehmen dürfen**|**Benutzer, die nicht an der Konferenz teilnehmen dürfen**|
|:-----|:-----|:-----|
|Skype for Business-VoIP-Clientbenutzer (s) von einer einzigen Netzwerk Website  <br/> |Skype for Business-VoIP-Clientbenutzer vom gleichen Netzwerkstandort  <br/> Skype for Business-VoIP-Clientbenutzer von einer anderen Netzwerk Website  <br/> Skype for Business-VoIP-Clientbenutzer von einer unbekannten Netzwerk Website  <br/> Partner des Skype for Business-VoIP-Client-Benutzers  <br/> Benutzer, die über PSTN-Endpunkt teilnehmen  <br/> |-  <br/> |
|Skype for Business-VoIP-Clientbenutzer (s) von einer unbekannten Netzwerk Website  <br/> |Skype for Business-VoIP-Clientbenutzer von jeder Website  <br/> Skype for Business-VoIP-Clientbenutzer von einer unbekannten Website  <br/> Partner des Skype for Business-VoIP-Client-Benutzers  <br/> |Benutzer, die über einen PSTN-Endpunkt teilnehmen  <br/> |
|Skype for Business-VoIP-Clientbenutzer von verschiedenen Netzwerkstandorten aus  <br/> |Skype for Business-VoIP-Clientbenutzer von einer beliebigen Netzwerk Website aus  <br/> Skype for Business-VoIP-Clientbenutzer von einer unbekannten Netzwerk Website  <br/> Partner des Skype for Business-VoIP-Client-Benutzers  <br/> |Benutzer, die über einen PSTN-Endpunkt teilnehmen  <br/> |
|Skype for Business-VoIP-Clientbenutzer (s) von einer einzigen Netzwerk Website und Benutzern, die von einem PSTN-Endpunkt beitreten  <br/> |Skype for Business-VoIP-Clientbenutzer vom gleichen Netzwerkstandort  <br/> |Skype for Business-VoIP-Clientbenutzer von einer anderen Netzwerk Website  <br/> Skype for Business-VoIP-Clientbenutzer von einer unbekannten Netzwerk Website  <br/> Partner des Skype for Business-VoIP-Client-Benutzers  <br/> |

Im folgenden sind zusätzliche Merkmale der standortbasierten Routing Anwendung für Konferenzanwendungen zu finden:

- Wenn ein Benutzer nicht berechtigt ist, an einer Konferenz teilzunehmen, wenn standortbasierte Routing Einschränkungen gelten, wird der Anruf an die Konferenz abgelehnt, und der Skype for Business-Client meldet, dass der Anruf nicht abgeschlossen oder beendet wurde.

- Ein PSTN-Endpunkt, der an einer Konferenz mit ortsbasierten Routing Erzwingungen teilnimmt, ist nicht auf die Teilnahme an der Konferenz beschränkt, unabhängig von seinem Zustand, wenn der Endpunkt über einen trunk verbunden wird, der für standortbasiertes Routing nicht aktiviert ist.

- Ein PBX-System, das mit einem Vermittlungs Server über einen SIP-Stamm verbunden ist, der keine Anrufe an das PSTN abruft, hat dieselben erzwungenen wie Skype for Business-Benutzer, die sich am gleichen Netzwerkstandort befinden, an dem der SIP-Stamm definiert ist. So kann beispielsweise ein PSTN-Endpunkt an einer Konferenz mit einem PBX-Benutzer und einem Skype for Business-Benutzer teilnehmen, wenn er sich auf derselben Netzwerk Website befindet. Andernfalls kann der PSTN-Endpunkt nicht an der Konferenz teilnehmen, wenn sich der PBX-Benutzer an einem anderen Netzwerkstandort als der Skype for Business-Benutzer befindet.

> [!NOTE]
> Mit dem kumulativen Update 4 für Skype for Business sollte das Verhalten in der folgenden Tabelle beobachtet werden.

|**Benutzer**|**Andere Teilnehmer**|**Aktion**|**Ergebnis**|
|:-----|:-----|:-----|:-----|
|Skype for Business Mobile  <br/> |Telefonfestnetz (PSTN)  <br/> |Skype for Business Mobile ist in einem PSTN-Anruf. Skype for Business Mobile stuft den Anruf dann zu einem Conference Auto Attendant (CAA) hoch.  <br/> |Der Anruf wird mit einer entsprechenden Fehlermeldung blockiert.  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business-Client oder Verbundbenutzer  <br/> |Der Client oder Verbundbenutzer befindet sich in einem VoIP-Anruf an einem mobilen standortbasierten Skype for Business-Routing Benutzer, und beide Parteien werden zu einem CAA weitergeleitet.  <br/> |Der Eskalationsanruf wird mit einer entsprechenden Fehlermeldung blockiert.  <br/> |

## <a name="consultative-call-transfers"></a>Anrufdurchstellungen mit Ankündigung

Neben der Durchsetzung von Standort basiertem Routing zu Skype for Business-Besprechungen erzwingt die standortbasierte Routing für Konferenz Anwendung standortbasierte Routing Einschränkungen bei Beratenden Anruf Übertragungen, die an PSTN-Endpunkte abgangen. Bei einer beratenden Anrufübertragung handelt es sich um einen Anruf zwischen zwei Parteien, bei dem eine der Parteien den Anruf an einen neuen Nutzer übermittelt. Ein PSTN-Endpunkt ruft beispielsweise Benutzer a an (Skype for Business-Anrufer). Benutzer A bestimmt, dass der PSTN-Benutzer an Benutzer B weitergeleitet werden soll (Skype for Business-Benutzer). Der Benutzer A platziert den Anruf mit dem PSTN-Benutzer in Wartestellung und ruft Benutzer b an, der sich mit dem PSTN-Benutzer unterhalten möchte. Benutzer a übergibt den Anruf in Wartestellung an Benutzer B.

**Anruffluss bei einer Anrufdurchstellung mit Ankündigung**

![Standortbasiertes Routing für Konferenzen (Diagramm)](../../media/LocationBasedRoutingForConferencing.jpg)

Wenn ein Benutzer, der für standortbasiertes Routing aktiviert ist, eine beratende Anrufübertragung eines PSTN-Endpunkts initiiert (wie in der vorhergehenden Abbildung zu sehen ist), werden zwei aktive Anrufe, ein Anruf zwischen dem PSTN-Benutzer und dem Skype for Business-Benutzer a und der andere zwischen Skype für Business-Benutzer a und Skype for Business-Benutzer B. das folgende Verhalten wird durch die standortbasierte Routing für Konferenz Anwendung erzwungen:

- Wenn das SIP Trunk-Routing des PSTN-Anrufs autorisiert ist, den PSTN-Anruf an die Netzwerk Website weiterzuleiten, auf der sich der Skype for Business-Benutzer B (also das Übertragungsziel) befindet, wird die Anrufübertragung zugelassen. Andernfalls wird die Übertragung von beratenden anrufen blockiert. Diese Autorisierung erfolgt auf der Grundlage des Standorts der übertragenen Partei, die sich am gleichen Netzwerkstandort wie der SIP-Stamm befindet, der den aktiven Anruf an den PSTN-Endpunkt weiterleitet.

- Wenn der SIP-Trunk-Routing der eingehende PSTN-Anruf nicht autorisiert ist, Anrufe an die Netzwerk Website weiterzuleiten, auf der sich die übertragene Partei (Skype for Business-Benutzer B) befindet oder sich die übertragene Partei in einer unbekannten Netzwerk Website befindet, wird die beratende Anrufübertragung an der PSTN-Endpunkt (dh Anrufübergabe Ziel) wird blockiert.

In der folgenden Tabelle wird beschrieben, wie standortbasierte Routing Einschränkungen von der standortbasierten Routing für Konferenz Anwendung für beratende Anruf Übertragungen angewendet werden. Zwar sind Nebenstellenanlagenendgeräte nicht direkt einem Netzwerkstandort zugewiesen, aber die SIP-Vermittlungsleitung, an die die jeweilige Nebenstellenanlage angeschlossen ist, kann einem Netzwerkstandort zugewiesen sein. Daher kann ein Nebenstellenanlagenendgerät indirekt einem Netzwerkstandort zugewiesen sein.


|**Netzwerkstandort des Teilnehmers, dessen Anruf durchgestellt wird**|**Netzwerk Website des Anruf Weiterleitungs Ziels**|**Verhalten**|
|:-----|:-----|:-----|
|Endpunkt im öffentlichen Telefonnetz  <br/> |Skype for Business-Benutzer auf derselben Netzwerk Website (also Website 1)  <br/> |Eine beratende Übertragung ist zulässig.  <br/> |
|Endpunkt im öffentlichen Telefonnetz  <br/> |Skype for Business-Benutzer in verschiedenen Netzwerkstandorten (also Standort 2)  <br/> |Eine beratende Übertragung ist nicht zulässig.  <br/> |
|Endpunkt im öffentlichen Telefonnetz  <br/> |Skype for Business-Benutzer in einer unbekannten Netzwerk Website  <br/> |Eine beratende Übertragung ist nicht zulässig.  <br/> |
|Endpunkt im öffentlichen Telefonnetz  <br/> |Federated Skype for Business-Benutzer  <br/> |Eine beratende Übertragung ist nicht zulässig.  <br/> |
|Endpunkt im öffentlichen Telefonnetz  <br/> |PBX-Endpunkt am gleichen Standort (also Standort 1)  <br/> |Eine beratende Übertragung ist zulässig.  <br/> |
|Endpunkt im öffentlichen Telefonnetz  <br/> |PBX-Endpunkt an verschiedenen Standorten (also Standort 2)  <br/> |Eine beratende Übertragung ist nicht zulässig.  <br/> |
|PBX-Endpunkt am gleichen Standort (also Standort 1)  <br/> |Endpunkt im öffentlichen Telefonnetz  <br/> |Eine beratende Übertragung ist zulässig.  <br/> |
|PBX-Endpunkt an einer anderen Website (also Standort 2)  <br/> |Endpunkt im öffentlichen Telefonnetz  <br/> |Eine beratende Übertragung ist nicht zulässig.  <br/> |
|PBX-Endpunkt auf einer beliebigen Website  <br/> |Skype for Business-Benutzer auf derselben Netzwerk Website (also Website 1)  <br/> |Eine beratende Übertragung ist zulässig.  <br/> |
|PBX-Endpunkt auf einer beliebigen Website  <br/> |Skype for Business-Benutzer in verschiedenen Netzwerkstandorten (also Standort 2)  <br/> |Eine beratende Übertragung ist zulässig.  <br/> |
|PBX-Endpunkt auf einer beliebigen Website  <br/> |Skype for Business-Benutzer in einer unbekannten Netzwerk Website  <br/> |Eine beratende Übertragung ist zulässig.  <br/> |
|PBX-Endpunkt auf einer beliebigen Website  <br/> |Federated Skype for Business-Benutzer  <br/> |Eine beratende Übertragung ist zulässig.  <br/> |

## <a name="requirements"></a>Voraussetzungen

Die Anwendung standortbasiertes Routing für Konferenz erfordert, dass das kumulative Update 2 von Skype for Business Server oder lync Server 2013 auf allen Front-End-Pools und Standard Edition-Servern in Ihrer Topologie bereitgestellt wird. Wenn diese Server Versionen auf einigen Servern in Ihrer Topologie nicht installiert sind, können standortbasierte Routing Einschränkungen bei Besprechungen und beratenden Anruf Übertragungen nicht vollständig erzwungen werden.

In der folgenden Tabelle ist die Kombination aus Serverrollen und Versionen aufgeführt, die standortbasiertes Routing unterstützen.


|**Version des Front-End-Pools**|**Mediation Server-Version**|**Unterstützt**|
|:-----|:-----|:-----|
|Kumulatives Update 2 für Skype for Business Server oder lync Server 2013  <br/> |Kumulatives Update 2 für Skype for Business Server oder lync Server 2013  <br/> |Ja  <br/> |
|Lync Server 2013 Kumulatives Update 2  <br/> |Lync Server 2013 Kumulatives Update 1  <br/> |Nein  <br/> |
|Lync Server 2013 Kumulatives Update 2  <br/> |Lync Server 2010  <br/> |Nein  <br/> |
|Lync Server 2013 Kumulatives Update 2  <br/> |Office Communications Server 2007 R2  <br/> |Nein  <br/> |
|Lync Server 2013 Kumulatives Update 1  <br/> |Beliebig  <br/> |Nein  <br/> |
|Lync Server 2010  <br/> |Beliebig  <br/> |Nein  <br/> |
|Office Communications Server 2007 R2  <br/> |Beliebig  <br/> |Nein  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>Konfiguration des standortbasierten Routings für Konferenzen

Die standortbasierte Routing für Konferenz Anwendung basiert auf der Konfiguration des standortbasierten Routings. Die wichtigsten Konfigurationen sind die folgenden:

- Die Position der Teilnehmer, die an einer Besprechung teilnehmen, wird basierend auf Ihrer Netzwerk Website festgelegt. Eine Netzwerk Website und die zugehörigen Netzwerk-Subnetze müssen in Skype for Business Server definiert werden, um standortbasiertes Routing durchzusetzen.

- Um die standortbasierte Weiterleitung von Besprechungen zu erzwingen, müssen Skype for Business-Teilnehmer für standortbasiertes Routing aktiviert sein.

- Zum Erzwingen der standortbasierten Weiterleitung von PSTN-Endpunkten, die an Besprechungen teilnehmen, muss der SIP-Trunk, der zum Verbinden der PSTN-Endpunkte verwendet wird, für standortbasiertes Routing konfiguriert

## <a name="enabling-the-location-based-routing-for-conferencing"></a>Aktivieren des ortsbasierten Routings für Konferenzen

Die Anwendung standortbasiertes Routing für Konferenz ist standardmäßig deaktiviert. Bevor Sie diese Anwendung aktivieren, müssen Sie die richtige Priorität ermitteln, die für die Anwendung zugewiesen werden soll. Führen Sie das folgende Cmdlet in der Skype for Business Server-Verwaltungsshell aus, um diese Priorität zu ermitteln:

Get-CsServerApplication-Identity Service: Registrar:<Pool FQDN>in diesem Cmdlet ist \<Pool-\> FQDN der Pool, in dem die Location-Based Routing für Conferencing-Anwendung aktiviert werden soll.

Dieses Cmdlet gibt die Liste der von Skype for Business Server gehosteten Anwendungen und den Prioritätswert für jeden von Ihnen zurück. Der standortbasierten Routing für Konferenz Anwendung muss ein Prioritätswert zugewiesen werden, der größer als die Anwendung "UdcAgent" und kleiner als die Anwendungen "DefaultRouting", "ExumRouting" und "OutboundRouting" ist. Wir empfehlen, dass Sie dem standortbasierten Routing für Konferenzanwendungen einen Prioritätswert zuweisen, der einen Punkt höher als der Prioritätswert der Anwendung "UdcAgent" ist.

Wenn beispielsweise die Anwendung "UdcAgent" einen Prioritätswert von "2" aufweist, weist die Anwendung "DefaultRouting" einen Prioritätswert von "8" auf, die "ExumRouting"-Anwendung hat einen Prioritätswert von "9", und die Anwendung "OutboundRouting" hat einen Prioritätswert von "10" und dann Sie sollten dem ortsbasierten Routing für die Konferenz Anwendung einen Prioritätswert von "3" zuweisen. Auf diese Weise würde die Priorität der Anwendungen in der folgenden Reihenfolge platziert: andere Anwendungen (Prioritäten: 0 bis 1), "UdcAgent" (Priorität: 2), standortbasierte Routing Konferenz Anwendung (Priorität: 3), andere Anwendungen (Prioritäten: 4 bis 8); " DefaultRouting "(Priorität: 9)," ExumRouting "(Priorität: 10) und" OutboundRouting "(Priorität: 11).

Nachdem Sie den richtigen Prioritätswert für die Anwendung standortbasiertes Routing für Konferenzen gefunden haben, geben Sie das folgende Cmdlet für jeden Front-End-Pool oder Standard Edition-Server ein, auf dem Benutzer für standortbasiertes Routing aktiviert sind:

New-CsServerApplication-Identity Service: Registrierungsstelle`<Pool FQDN`: >/LBRouting- \<Priority\> -aktivierte $true kritische $true-URI<http://www.microsoft.com/LCS/LBRouting> 

Beispiel:

New-CsServerApplication-Identity Service:Registrar:ls2013cu2lbrpool. contoso. com/LBRouting-Priority 3-Enabled $true-Critical $true-URIhttp://www.microsoft.com/LCS/LBRouting 

Nachdem Sie dieses Cmdlet verwendet haben, starten Sie alle Front-End-Server im Pool oder die Standard Edition-Server neu, auf denen die Anwendung standortbasiertes Routing für Konferenz aktiviert wurde.

> [!IMPORTANT]
> Standortbasierte Routing-Erzwingungen zu Konferenzen oder beratenden Übertragungen werden erst erzwungen, wenn alle Front-End-Server in den entsprechenden Pools oder den Standard Edition-Servern neu gestartet werden. Wenn Sie in den vorangehenden Cmdlets "kritisch" **$true** , werden Ihre Skype for Business Server **-** Dienste sofort neu gestartet. Wenn Sie nicht möchten, dass diese Dienste sofort neu gestartet werden **** , legen Sie für jetzt **$false auf** , und verwenden Sie dann **** " **festlegen-CsServerApplication** ", um später zu **$true** , nachdem die Dienste neu gestartet wurden.

Nachdem die standortbasierte Routing für Konferenz Anwendung erfolgreich aktiviert wurde und alle anwendbaren Server neu gestartet wurden, werden alle Konferenzen, die von Skype for Business-Benutzern für standortbasierte Routings organisiert wurden, überwacht, um zu verhindern, dass PSTN-Maut Umgehung


