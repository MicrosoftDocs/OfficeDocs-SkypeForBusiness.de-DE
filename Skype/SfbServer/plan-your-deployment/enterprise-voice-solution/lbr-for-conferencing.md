---
title: Location-Based Routing für Konferenzen in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: 'Planung des standortbasierten Routings für Konferenzen in Skype for Business Server Enterprise-VoIP, einschließlich Anrufdurchstellungen mit Beratungsgesprächen.'
---

# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Location-Based Routing für Konferenzen in Skype for Business Server

Planung des standortbasierten Routings für Konferenzen in Skype for Business Server Enterprise-VoIP, einschließlich Anrufdurchstellungen mit Beratungsgesprächen.

Location-Based Routing ermöglicht es, das Routing von Anrufen zwischen VoIP-Endpunkten und PSTN-Endpunkten basierend auf dem Standort der Anrufbeteiligten einzuschränken. Location-Based Routing für Konferenzen ermöglicht es Ihnen, Location-Based Routingregeln für Besprechungen (z. B. Konferenzen) zu erzwingen, um die Gebührenumgehung im öffentlichen Telefonnetz zu verhindern. Die Anwendung überwacht eine aktive Konferenz und erzwingt Location-Based Routingeinschränkungen basierend auf dem Standort der teilnehmenden Benutzer. Die Location-Based Routing für Konferenzanwendung ermöglicht darüber hinaus die Erzwingung Location-Based Routingeinschränkungen für beratende Übertragungen, die PSTN-Endpunkte betreffen.

Die Location-Based-Routingkonferenzanwendung bietet Skype for Business Konferenzen einen Mechanismus zur Verhinderung von Gebührenumgehungen im öffentlichen Telefonnetz. Die Anwendung überwacht aktive Konferenzen und erzwingt Location-Based Routingeinschränkungen basierend auf dem Standort der Skype for Business teilnehmenden Benutzer.

Die Location-Based Routingkonferenzanwendung bestimmt, ob Location-Based Routing in einer Skype for Business Besprechung erzwungen werden soll, wenn die folgenden Kriterien erfüllt sind:

- Der Besprechungsorganisator ist für Location-Based Routing aktiviert. Location-Based Routingeinschränkungen werden nur auf Konferenzen angewendet, die von Benutzern organisiert werden, die für Location-Based Routing aktiviert sind.

- Mindestens ein Besprechungsteilnehmer ist ein PSTN-Endpunkt. Location-Based Routingeinschränkungen gelten nur für Konferenzen, die PSTN-Endpunkte enthalten.

- Der Netzwerkstandort, an dem das PSTN-Gateway zum Überbrücken der Konferenz mit dem PSTN verwendet wird, sowie die Netzwerkstandorte, von denen die Organisatoren und Teilnehmer eine Verbindung herstellen.

Die Location-Based Routing für Konferenzanwendung verhindert die Teilnahme von Skype for Business Benutzern und PSTN-Endpunkten von unterschiedlichen Netzwerkstandorten an derselben Konferenz. Wenn der Organisator einer Besprechung für Location-Based Routing aktiviert ist, erzwingt die Konferenzanwendung die folgenden Einschränkungen:

- Die Endpunkte, die an einer Skype for Business Besprechung teilnehmen können, sind von den Endpunkten abhängig, die bereits der Konferenz beigetreten sind. Diese Einschränkung wird angepasst, wenn verbundene Endpunkte verlassen und neue Endpunkte der Konferenz beitreten. Wenn Organisatoren und Teilnehmer an einer Skype for Business Besprechung vom gleichen Netzwerkstandort teilnehmen, kann ein PSTN-Endpunkt, ein anderer Teilnehmer vom gleichen Netzwerkstandort, ein anderer Teilnehmer von einem anderen Netzwerkstandort oder ein Teilnehmer von einem unbekannten Netzwerkstandort teilnehmen.

- Wenn Organisatoren und Teilnehmer von verschiedenen oder unbekannten Netzwerkstandorten an der Besprechung teilnehmen, kann ein PSTN-Endpunkt nicht an der Besprechung teilnehmen, wenn der PSTN-Anruf von einem SIP-Trunk ausgeht, der für Location-Based Routing aktiviert ist.

- Wenn Organisatoren und Teilnehmer von demselben Netzwerkstandort aus an der Besprechung teilnehmen und Teilnehmer aus dem PSTN an der gleichen Besprechung teilnehmen, kann ein Skype for Business Endpunkt von einem anderen Netzwerkstandort nicht an der Besprechung teilnehmen.

Diese Einschränkungen für konferenzende Location-Based Routing werden in der folgenden Tabelle zusammengefasst.

|Benutzer in einer Konferenz zu einem bestimmten Zeitpunkt|Benutzer, die an der Konferenz teilnehmen dürfen|Benutzer dürfen nicht an der Konferenz teilnehmen|
|:-----|:-----|:-----|
|Skype for Business VoIP-Clientbenutzer von einem einzigen Netzwerkstandort  <br/> |Skype for Business VoIP-Clientbenutzer vom selben Netzwerkstandort  <br/> Skype for Business VoIP-Clientbenutzer von einem anderen Netzwerkstandort  <br/> Skype for Business VoIP-Clientbenutzer von einem unbekannten Netzwerkstandort  <br/> Verbund-Skype for Business VoIP-Clientbenutzer  <br/> Benutzerbeitritt von einem PSTN-Endpunkt aus  <br/> |None  <br/> |
|Skype for Business VoIP-Clientbenutzer von einem unbekannten Netzwerkstandort  <br/> |Skype for Business VoIP-Clientbenutzer von einer beliebigen Website  <br/> Skype for Business VoIP-Clientbenutzer von einer unbekannten Website  <br/> Verbund-Skype for Business VoIP-Clientbenutzer  <br/> |Benutzerbeitritt über einen PSTN-Endpunkt  <br/> |
|Skype for Business VoIP-Clientbenutzer von unterschiedlichen Netzwerkstandorten  <br/> |Skype for Business VoIP-Clientbenutzer von einem beliebigen Netzwerkstandort  <br/> Skype for Business VoIP-Clientbenutzer von einem unbekannten Netzwerkstandort  <br/> Verbund-Skype for Business VoIP-Clientbenutzer  <br/> |Benutzerbeitritt über einen PSTN-Endpunkt  <br/> |
|Skype for Business VoIP-Clientbenutzer von einem einzigen Netzwerkstandort und Benutzer, die von einem PSTN-Endpunkt beitreten  <br/> |Skype for Business VoIP-Clientbenutzer vom selben Netzwerkstandort  <br/> |Skype for Business VoIP-Clientbenutzer von einem anderen Netzwerkstandort  <br/> Skype for Business VoIP-Clientbenutzer von einem unbekannten Netzwerkstandort  <br/> Verbund-Skype for Business VoIP-Clientbenutzer  <br/> |

Im Folgenden finden Sie weitere Merkmale der Location-Based-Anwendung "Routing für Konferenzen":

- Wenn ein Benutzer aufgrund Location-Based Routingeinschränkungen nicht an einer Konferenz teilnehmen darf, wird der Anruf an der Konferenz abgelehnt, und der Skype for Business-Client meldet, dass der Anruf nicht abgeschlossen wurde oder beendet wurde.

- Ein PSTN-Endpunkt, der einer Konferenz mit Location-Based Routingerzwingungen beitritt, kann unabhängig vom Status der Konferenz nicht teilnehmen, wenn der Endpunkt über einen Trunk beitritt, der nicht für Location-Based Routing aktiviert ist.

- Eine Nebenstellenanlage, die über einen SIP-Trunk mit einem Vermittlungsserver verbunden ist und keine Anrufe an das PSTN ausgibt, hat dieselben Erzwingungen wie Skype for Business Benutzer, die sich an demselben Netzwerkstandort befinden, an dem der SIP-Trunk definiert ist. Beispielsweise kann ein PSTN-Endpunkt einer Konferenz mit einem PBX-Benutzer und einem Skype for Business-Benutzer beitreten, wenn er sich am gleichen Netzwerkstandort befindet. Andernfalls kann der PSTN-Endpunkt nicht an der Konferenz teilnehmen, wenn sich der PBX-Benutzer an einem anderen Netzwerkstandort befindet als der Skype for Business Benutzer.

> [!NOTE]
> Mit Skype for Business kumulativen Update 4 sollte das Verhalten in der folgenden Tabelle beobachtet werden:

|Benutzer|Andere Partei|Aktion|Result|
|:-----|:-----|:-----|:-----|
|Skype for Business Mobile  <br/> |Telefonfestnetz (Public Switched Telephone Network, PSTN)  <br/> |Skype for Business Mobile befindet sich in einem PSTN-Anruf. Skype for Business Mobile eskaliert dann den Anruf an eine automatische Telefonzentrale (Caa).  <br/> |Der Aufruf wird mit einer entsprechenden Fehlermeldung blockiert.  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business Client oder Verbundbenutzer  <br/> |Der Client- oder Verbundbenutzer befindet sich in einem VoIP-Anruf bei einem Skype for Business Mobile Location-Based Routingbenutzer, und eine der beiden Parteien eskaliert an ein CAA.  <br/> |Der Eskalationsaufruf wird mit einer entsprechenden Fehlermeldung blockiert.  <br/> |

## <a name="consultative-call-transfers"></a>Anrufdurchstellung mit Beratungsanruf

Zusätzlich zum Erzwingen von Location-Based Routing zu Skype for Business Besprechungen erzwingt die Location-Based Routing für Konferenzanwendung Location-Based Routingeinschränkungen für Anrufdurchstellungen mit Beratungsgesprächen, die an PSTN-Endpunkte übermittelt werden. Bei einer Anrufdurchstellung handelt es sich um einen Anruf zwischen zwei Parteien, bei dem eine der Parteien den Anruf an einen neuen Benutzer überträgt. Ein PSTN-Endpunkt ruft beispielsweise Benutzer A (Skype for Business Angerufenen) auf. Benutzer A bestimmt, dass der PSTN-Benutzer an Benutzer B (Skype for Business Benutzer) weitergeleitet werden soll. Benutzer A setzt den Anruf mit dem PSTN-Benutzer in die Warteschleife, und der Benutzer B. Benutzer B stimmt zu, mit dem PSTN-Benutzer zu sprechen. Benutzer A überträgt die Warteschleife des Anrufs an Benutzer B.

**Anruffluss bei Anrufdurchstellung mit Ankündigung**

![Standortbasiertes Routing für Konferenzdiagramm.](../../media/LocationBasedRoutingForConferencing.jpg)

Wenn ein Benutzer, der für Location-Based Routing aktiviert ist, eine Anrufdurchstellung eines PSTN-Endpunkts initiiert (wie in der obigen Abbildung dargestellt), werden dadurch zwei aktive Anrufe erstellt, ein Anruf zwischen dem PSTN-Benutzer und Skype for Business Benutzer A und der andere zwischen Skype for Business Benutzer A und Skype for Business  Benutzer B. Das folgende Verhalten wird von der Location-Based Routing für Konferenzanwendung erzwungen:

- Wenn das SIP-Trunkrouting des PSTN-Anrufs autorisiert ist, den PSTN-Anruf an den Netzwerkstandort umzuleiten, an dem sich Skype for Business Benutzer B (d. h. das Übertragungsziel) befindet, wird die Anrufübertragung zugelassen. Andernfalls wird die Anrufdurchstellung blockiert. Diese Autorisierung erfolgt basierend auf dem Standort der übertragenen Partei, der sich am gleichen Netzwerkstandort wie der SIP-Trunk befindet, der den aktiven Anruf an den PSTN-Endpunkt weiterleite.

- Wenn das SIP-Trunkrouting des eingehenden PSTN-Anrufs nicht berechtigt ist, Anrufe an den Netzwerkstandort weiterzuleiten, an dem sich die übertragene Partei (Skype for Business Benutzer B) befindet, oder die übertragene Partei sich an einem unbekannten Netzwerkstandort befindet, wird die Anrufweiterleitung an den PSTN-Endpunkt (d. h. das Ziel der Anrufdurchstellung) blockiert.

In der folgenden Tabelle wird beschrieben, wie Location-Based Routingeinschränkungen von der Anwendung Location-Based Routing für Konferenzen für Anrufdurchstellungen angewendet werden. Obwohl PBX-Endpunkte nicht direkt mit einem Netzwerkstandort verbunden sind, kann dem SIP-Trunk, mit dem die Nebenstellenanlage verbunden ist, ein Netzwerkstandort zugewiesen werden. Daher kann der PBX-Endpunkt indirekt einem Netzwerkstandort zugeordnet werden.


|Netzwerkstandort des anrufversetzten Teilnehmers|Netzwerkstandort des Anrufübertragungsziels|Verhalten|
|:-----|:-----|:-----|
|PSTN-Endpunkt  <br/> |Skype for Business Benutzer am selben Netzwerkstandort (d. h. Standort 1)  <br/> |Die Übertragung durch Die Vermittlung ist zulässig.  <br/> |
|PSTN-Endpunkt  <br/> |Skype for Business Benutzer an verschiedenen Netzwerkstandorten (d. h. Standort 2)  <br/> |Die Übertragung mit Ankündigung ist nicht zulässig.  <br/> |
|PSTN-Endpunkt  <br/> |Skype for Business Benutzer an einem unbekannten Netzwerkstandort  <br/> |Die Übertragung mit Ankündigung ist nicht zulässig.  <br/> |
|PSTN-Endpunkt  <br/> |Partnerbenutzer Skype for Business  <br/> |Die Übertragung mit Ankündigung ist nicht zulässig.  <br/> |
|PSTN-Endpunkt  <br/> |PBX-Endpunkt am selben Standort (d. h. Standort 1)  <br/> |Die Übertragung durch Die Vermittlung ist zulässig.  <br/> |
|PSTN-Endpunkt  <br/> |PBX-Endpunkt an einem anderen Standort (d. h. Standort 2)  <br/> |Die Übertragung mit Ankündigung ist nicht zulässig.  <br/> |
|PBX-Endpunkt am selben Standort (d. h. Standort 1)  <br/> |PSTN-Endpunkt  <br/> |Die Übertragung durch Die Vermittlung ist zulässig.  <br/> |
|PBX-Endpunkt an einem anderen Standort (d. h. Standort 2)  <br/> |PSTN-Endpunkt  <br/> |Die Übertragung mit Ankündigung ist nicht zulässig.  <br/> |
|PBX-Endpunkt an einem beliebigen Standort  <br/> |Skype for Business Benutzer am selben Netzwerkstandort (d. h. Standort 1)  <br/> |Die Übertragung durch Die Vermittlung ist zulässig.  <br/> |
|PBX-Endpunkt an einem beliebigen Standort  <br/> |Skype for Business Benutzer an verschiedenen Netzwerkstandorten (d. h. Standort 2)  <br/> |Die Übertragung durch Die Vermittlung ist zulässig.  <br/> |
|PBX-Endpunkt an einem beliebigen Standort  <br/> |Skype for Business Benutzer an einem unbekannten Netzwerkstandort  <br/> |Die Übertragung durch Die Vermittlung ist zulässig.  <br/> |
|PBX-Endpunkt an einem beliebigen Standort  <br/> |Partnerbenutzer Skype for Business  <br/> |Die Übertragung durch Die Vermittlung ist zulässig.  <br/> |

## <a name="requirements"></a>Anforderungen

Die Location-Based Routing für Konferenzanwendung erfordert, dass Skype for Business Server oder das kumulative Update 2013 von Lync Server 2013 auf allen Front-End Pools und Standard Edition Servern in Ihrer Topologie bereitgestellt wird. Wenn diese Serverversionen nicht auf einigen Servern in Ihrer Topologie installiert sind, können Location-Based Routingeinschränkungen bei Besprechungen und Anrufdurchstellungen mit Beratungsgesprächen nicht vollständig erzwungen werden.

In der folgenden Tabelle ist die Kombination aus Serverrollen und Versionen aufgeführt, die Location-Based Routing unterstützen.


|Front-End Poolversion|Version des Vermittlungsservers|Unterstützt|
|:-----|:-----|:-----|
|Skype for Business Server oder kumulatives Update 2 für Lync Server 2013  <br/> |Skype for Business Server oder kumulatives Update 2 für Lync Server 2013  <br/> |Ja  <br/> |
|Kumulatives Update 2 für Lync Server 2013  <br/> |Kumulatives Update 1 für Lync Server 2013  <br/> |Nein  <br/> |
|Kumulatives Update 2 für Lync Server 2013  <br/> |Lync Server 2010  <br/> |Nein  <br/> |
|Kumulatives Update 2 für Lync Server 2013  <br/> |Office Communications Server 2007 R2  <br/> |Nein  <br/> |
|Kumulatives Update 1 für Lync Server 2013  <br/> |Any  <br/> |Nein  <br/> |
|Lync Server 2010  <br/> |Any  <br/> |Nein  <br/> |
|Office Communications Server 2007 R2  <br/> |Any  <br/> |Nein  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>Konfiguration von Location-Based Routing für Konferenzen

Die Location-Based Routing für Konferenzanwendung basiert auf der Konfiguration von Location-Based Routing. Die hauptkonfigurationen sind die folgenden:

- Der Ort der Teilnehmer, die an einer Besprechung teilnehmen, wird basierend auf ihrem Netzwerkstandort bestimmt. Ein Netzwerkstandort und die zugehörigen Netzwerksubnetze müssen in Skype for Business Server definiert werden, um Location-Based Routing zu erzwingen.

- Um Location-Based Routing von Besprechungen zu erzwingen, müssen Skype for Business Teilnehmer für Location-Based Routing aktiviert sein.

- Um Location-Based Routing von PSTN-Endpunkten zu erzwingen, die an Besprechungen teilnehmen, muss der ZUM Verbinden der PSTN-Endpunkte verwendete SIP-Trunk für Location-Based Routing konfiguriert werden.

## <a name="enabling-the-location-based-routing-for-conferencing"></a>Aktivieren des Location-Based Routings für Konferenzen

Die Location-Based-Anwendung "Routing für Konferenzen" ist standardmäßig deaktiviert. Bevor Sie diese Anwendung aktivieren, müssen Sie die richtige Priorität für die Anwendung bestimmen. Führen Sie das folgende Cmdlet in Skype for Business Server Verwaltungsshell aus, um diese Priorität zu ermitteln:

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

In diesem Cmdlet ist der Pool, \<Pool FQDN\> in dem die Location-Based Routing für Konferenzanwendung aktiviert werden soll.

Dieses Cmdlet gibt die Liste der von Skype for Business Server gehosteten Anwendungen und den Prioritätswert für jede von ihnen zurück. Der Location-Based Routing für Konferenzanwendung muss ein Prioritätswert zugewiesen werden, der größer als die Anwendung "UdcAgent" und kleiner als die Anwendungen "DefaultRouting", "ExumRouting" und "OutboundRouting" ist. Es wird empfohlen, der Location-Based Routing für Konferenzanwendung einen Prioritätswert zuzuweisen, der um einen Punkt höher als der Prioritätswert der Anwendung "UdcAgent" ist.

Wenn die Anwendung "UdcAgent" beispielsweise den Prioritätswert "2" aufweist, die Anwendung "DefaultRouting" den Prioritätswert "8", die Anwendung "ExumRouting" den Prioritätswert "9" und die Anwendung "OutboundRouting" den Prioritätswert "10" hat, sollten Sie der Location-Based Routing für Konferenzanwendung den Prioritätswert "3" zuweisen. Auf diese Weise würde die Priorität der Anwendungen in der folgenden Reihenfolge platziert: Andere Anwendungen (Prioritäten: 0 bis 1), "UdcAgent" (Priorität: 2), Location-Based Routingkonferenzanwendung (Priorität: 3), andere Anwendungen (Prioritäten: 4 bis 8), "DefaultRouting" (Priorität: 9), "ExumRouting" (Priorität: 10) und "Ausgehendes Routing" (Priorität: 11).

Nachdem Sie den richtigen Prioritätswert für die Location-Based Routing für Konferenzanwendung gefunden haben, geben Sie das folgende Cmdlet für jeden Front-End Pool oder Standard Edition Server ein, auf dem Benutzer für Location-Based Routing aktiviert sind:

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri <http://www.microsoft.com/LCS/LBRouting>
```

Beispiel:

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

Starten Sie nach Der Verwendung dieses Cmdlets alle Front-End-Server im Pool oder die Standard Edition Server neu, auf denen die Location-Based Routing für Konferenzanwendung aktiviert wurde.

> [!IMPORTANT]
> Location-Based routing enforcements to conferences or consultative transfers won't be enforced until all the Front End Servers in the applicable pools or the Standard Edition Servers are restarted. Wenn Sie **"-Critical**" auf **$true** in den vorherigen Cmdlets festlegen, werden ihre Skype for Business Server Dienste sofort neu gestartet. Wenn Sie nicht möchten, dass diese Dienste sofort neu gestartet werden, legen Sie **"-Critical** " auf **"$false** " fest, und verwenden Sie " **Set-CsServerApplication** ", um **"-Critical** " zu **$true** später zu ändern, nachdem die Dienste neu gestartet wurden.

Nachdem die Location-Based Routing für Konferenzanwendung erfolgreich aktiviert wurde und alle entsprechenden Server neu gestartet wurden, werden alle Konferenzen, die von Skype for Business Benutzern organisiert werden, die für Location-Based Routing aktiviert sind, überwacht, um die Umgehung der Gebühren für das Festnetz zu verhindern.


