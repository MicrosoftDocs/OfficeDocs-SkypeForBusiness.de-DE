---
title: Location-Based von Konferenzen in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Planen des standortbasierten Routings für Konferenzen in Skype for Business Server Enterprise-VoIP einschließlich Anrufüberleitungen mit Anrufen.
ms.openlocfilehash: 744f4b313f7ea458013aa0e45cff37ebbf85068a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825575"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Location-Based von Konferenzen in Skype for Business Server

Planen des standortbasierten Routings für Konferenzen in Skype for Business Server Enterprise-VoIP einschließlich Anrufüberleitungen mit Anrufen.

Location-Based Routing ermöglicht das Einschränken des Routings von Anrufen zwischen VoIP-Endpunkten und PSTN-Endpunkten basierend auf dem Standort der Anrufbesprechungen. Location-Based routing for Conferencing ermöglicht es Ihnen, Location-Based Routingregeln für Besprechungen (d. h. Konferenzen) zu erzwingen, um eine gebührenpflichtige Umgehung im öffentlichen Telefonnetz zu verhindern. Die Anwendung überwacht eine aktive Konferenz und erzwingt Location-Based Routingeinschränkungen basierend auf dem Standort der teilnehmenden Benutzer. Die Location-Based routing for Conferencing-Anwendung ermöglicht darüber hinaus die Durchsetzung von Location-Based Routingeinschränkungen für öffentlichen Übertragungen, an denen Endpunkte des öffentlichen Telefonnetz beteiligt sind.

Die Location-Based routing conferencing application provides to Skype for Business Conferences a mechanism for the prevention of PSTN toll bypass. Die Anwendung überwacht aktive Konferenzen und erzwingt Location-Based Routingeinschränkungen basierend auf dem Standort der teilnehmenden Skype for Business-Benutzer.

Die Location-Based routing conferencing application determines whether Location-Based Routing is to be enforced on a Skype for Business meeting if the following criteria are met:

- Der Besprechungsorganisator ist für das Location-Based aktiviert. Location-Based routing restrictions will be applied only to conferences that are organized by users who are enabled for Location-Based Routing.

- Mindestens ein Besprechungsteilnehmer ist ein PSTN-Endpunkt. Location-Based routing restrictions are applicable only for conferences that include PSTN endpoints.

- Der Netzwerkstandort, an dem sich das ZUM Überbrücken der Konferenz mit dem PSTN verwendete PSTN-Gateway befindet, sowie die Netzwerkstandorte, von denen die Organisatoren und Teilnehmer eine Verbindung herstellen.

Die Location-Based Routing for Conferencing-Anwendung verhindert die Teilnahme von Skype for Business-Benutzern und -PSTN-Endpunkten von verschiedenen Netzwerkstandorten an derselben Konferenz. Wenn der Organisator einer Besprechung für das Location-Based aktiviert ist, erzwingt die Konferenzanwendung die folgenden Einschränkungen:

- Die Endpunkte, die an einer Skype for Business-Besprechung teilnehmen können, hängen von den Endpunkten ab, die der Konferenz bereits beigetreten sind, und diese Einschränkung passt sich an, wenn die beigetretenen Endpunkte die Konferenz verlassen und neue Endpunkte der Konferenz beitreten. Wenn Organisatoren und Teilnehmer von demselben Netzwerkstandort aus an einer Skype for Business-Besprechung teilnehmen, können ein PSTN-Endpunkt, ein anderer Teilnehmer vom gleichen Netzwerkstandort, ein anderer Teilnehmer von einem anderen Netzwerkstandort oder ein Teilnehmer von einem unbekannten Netzwerkstandort teilnehmen.

- Wenn Organisatoren und Teilnehmer von unterschiedlichen oder unbekannten Netzwerkstandorten aus an der Besprechung teilnehmen, darf ein Endpunkt des Telefonnetzes nicht an der Besprechung teilnehmen, wenn der Festnetzanruf von einem für das Routing aktivierten Location-Based wird.

- Wenn Organisatoren und Teilnehmer von demselben Netzwerkstandort aus an der Besprechung teilnehmen und teilnehmer aus dem PSTN an der gleichen Besprechung teilnehmen, darf ein Skype for Business-Endpunkt von einem anderen Netzwerkstandort nicht an der Besprechung teilnehmen.

Diese Konferenzeinschränkungen Location-Based Routing sind in der folgenden Tabelle zusammengefasst.

|Benutzer in einer Konferenz zu einem beliebigen Zeitpunkt|Benutzer, die an der Konferenz teilnehmen dürfen|Benutzer, die nicht an der Konferenz teilnehmen dürfen|
|:-----|:-----|:-----|
|Skype for Business VoIP-Clientbenutzer von einem einzelnen Netzwerkstandort  <br/> |Skype for Business-VoIP-Clientbenutzer vom gleichen Netzwerkstandort  <br/> Skype for Business-VoIP-Clientbenutzer von einem anderen Netzwerkstandort  <br/> Skype for Business-VoIP-Clientbenutzer von einem unbekannten Netzwerkstandort  <br/> Skype for Business-VoIP-Client-Partnerbenutzer  <br/> Benutzer, der über einen Endpunkt im öffentlichen Telefonnetz beitritt  <br/> |Keine  <br/> |
|Skype for Business VoIP-Clientbenutzer von einem unbekannten Netzwerkstandort  <br/> |Skype for Business-VoIP-Clientbenutzer von einem beliebigen Standort  <br/> Skype for Business-VoIP-Clientbenutzer von einem unbekannten Standort  <br/> Skype for Business-VoIP-Client-Partnerbenutzer  <br/> |Benutzer, die über einen Endpunkt im öffentlichen Telefonnetz beitreten  <br/> |
|Skype for Business-VoIP-Clientbenutzer von verschiedenen Netzwerkstandorten  <br/> |Skype for Business-VoIP-Clientbenutzer von einem beliebigen Netzwerkstandort  <br/> Skype for Business-VoIP-Clientbenutzer von einem unbekannten Netzwerkstandort  <br/> Skype for Business-VoIP-Client-Partnerbenutzer  <br/> |Benutzer, der über einen Endpunkt im öffentlichen Telefonnetz beitritt  <br/> |
|Skype for Business-VoIP-Clientbenutzer von einem einzelnen Netzwerkstandort und Benutzer, die über einen Endpunkt im öffentlichen Telefonnetz beitreten  <br/> |Skype for Business-VoIP-Clientbenutzer vom gleichen Netzwerkstandort  <br/> |Skype for Business-VoIP-Clientbenutzer von einem anderen Netzwerkstandort  <br/> Skype for Business-VoIP-Clientbenutzer von einem unbekannten Netzwerkstandort  <br/> Skype for Business-VoIP-Client-Partnerbenutzer  <br/> |

Im Folgenden finden Sie weitere Merkmale der Location-Based Routing for Conferencing-Anwendung:

- Wenn ein Benutzer aufgrund von Location-Based Routingeinschränkungen nicht an einer Konferenz teilnehmen darf, wird der Anruf an die Konferenz abgelehnt, und der Skype for Business-Client berichtet, dass der Anruf nicht abgeschlossen oder beendet wurde.

- Ein PSTN-Endpunkt, der einer Konferenz mit Location-Based Routing-Erzwingungen beitritt, ist unabhängig vom Status nicht auf den Beitritt zur Konferenz beschränkt, wenn der Endpunkt über einen Trunk beitritt, der nicht für Location-Based ist.

- Ein nebengeschaltetes Nebenstellensystem, das über einen SIP-Trunk mit einem Vermittlungsserver verbunden ist und keine Anrufe an das Telefonnetz übernimmt, hat die gleichen Erzwingungen wie Skype for Business-Benutzer, die sich am gleichen Netzwerkstandort befinden, an dem der SIP-Trunk definiert ist. Beispielsweise kann ein #A0 einer Konferenz mit einem #A1 und einem Skype for #A2 beitreten, wenn er sich am gleichen Netzwerkstandort befindet. Andernfalls kann der Endpunkt des Telefonnetzes nicht an der Konferenz teilnehmen, wenn sich der Benutzer der Nebenstellenanlage an einem anderen Netzwerkstandort als der Skype for Business-Benutzer befindet.

> [!NOTE]
> Mit dem kumulativen Update 4 für Skype for Business sollte das Verhalten in der folgenden Tabelle beobachtet werden:

|Benutzer|Andere Partei|Aktion|Ergebnis|
|:-----|:-----|:-----|:-----|
|Skype for Business Mobile  <br/> |PSTN  <br/> |Skype for Business Mobile ist in einem Festnetzanruf. Skype for Business Mobile eskaliert dann den Anruf an eine automatische Telefonzentrale (CaA).  <br/> |Der Anruf wird mit einer entsprechenden Fehlermeldung blockiert.  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business Client oder Partnerbenutzer  <br/> |Der Client oder Partnerbenutzer ist an einem VoIP-Anruf an einen Skype for Business Mobile Location-Based Routing-Benutzer, und beide Parteien eskalieren an eine Zertifizierungsstelle.  <br/> |Der Eskalationsaufruf wird mit einer entsprechenden Fehlermeldung blockiert.  <br/> |

## <a name="consultative-call-transfers"></a>Anrufüberweisungen mit Anrufen

Zusätzlich zur Erzwingung von Location-Based Routing zu Skype for Business-Besprechungen erzwingt die Location-Based Routing for Conferencing-Anwendung einschränkungen für das Location-Based Routing bei Anrufübergangen mit Öffentlichen Telefonkonferenzen, die an Endpunkte des öffentlichen Telefonnetz (PSTN) geleitet werden. Eine Anrufdurchsetzung mit Anruf ist ein Anruf zwischen zwei Parteien, bei dem eine der Parteien den Anruf an einen neuen Benutzer weitergibt. Ein Endpunkt im öffentlichen Telefonnetz ruft z. B. Benutzer A (Skype for Business-Anrufe) an. Benutzer A bestimmt, dass der Benutzer im öffentlichen Telefonnetz an Benutzer B (Skype for Business-Benutzer) weitergeleitet werden soll. Benutzer A platziert den Anruf mit dem PSTN-Benutzer in der Warteschleife und ruft Benutzer B an. Benutzer B stimmt zu, mit dem Benutzer im Telefonnetz zu sprechen. Benutzer A überträgt den Anruf in der Warteschleife an Benutzer B.

**Anruffluss bei Anrufdurchführung mit Beratungsanruf**

![Standortbasiertes Routing für Konferenzdiagramm](../../media/LocationBasedRoutingForConferencing.jpg)

Wenn ein für Location-Based Routing aktivierter Benutzer eine Anrufdurchleitung mit Öffentlichen Telefonnetzanrufen (wie in der vorherigen Abbildung dargestellt) initiiert, werden zwei aktive Anrufe erstellt: ein Anruf zwischen dem Festnetzbenutzer und Skype for Business-Benutzer A und der andere zwischen Skype for Business-Benutzer A und Skype for Business-Benutzer B. Das folgende Verhalten wird durch die Anwendung Location-Based Routing for Conferencing erzwungen:

- Wenn das #A0 für das Routing des #A1 autorisiert ist, den #A2 erneut an den Netzwerkstandort weiterleite, an dem sich Skype for #A3 B (d. h. Übertragungsziel) befindet, ist die Anrufüberleitung zulässig. andernfalls wird die Anrufüberweisung mit Anruf blockiert. Diese Autorisierung wird basierend auf dem Standort des übertragenen Partei am gleichen Netzwerkstandort wie der SIP-Trunk ausgeführt, der den aktiven Anruf an den Endpunkt pstN weiterleite.

- Wenn das SIP-Trunk-Routing des eingehenden Festnetzanrufs nicht autorisiert ist, Anrufe an den Netzwerkstandort weiterleite, an dem sich der übertragene Parteien (Skype for Business-Benutzer B) befindet, oder der übertragene Partei sich an einem unbekannten Netzwerkstandort befindet, wird die Anrufüberleitung mit Öffentlichen Telefonfestnetz (d. h. anrufübergangsziel) blockiert.

In der folgenden Tabelle wird beschrieben, Location-Based Routingeinschränkungen von der Anwendung Location-Based Routing for Conferencing für anrufverkn nungsverkn nen angewendet werden. Obwohl Nebenstellenanlagenendpunkte nicht direkt einem Netzwerkstandort zugeordnet sind, kann dem SIP-Trunk, mit dem die Nebenstellenanlage verbunden ist, ein Netzwerkstandort zugewiesen werden. Daher kann der Endpunkt der Nebenstellenanlage indirekt einem Netzwerkstandort zugeordnet werden.


|Netzwerkstandort des übertragenen Anrufs|Netzwerkstandort des Anrufübergangsziels|Verhalten|
|:-----|:-----|:-----|
|Endpunkt des öffentlichen Telefonnetz (PSTN)  <br/> |Skype for Business-Benutzer am gleichen Netzwerkstandort (d. h. Standort 1)  <br/> |Mit Weisungsübersetzung ist dies zulässig.  <br/> |
|Endpunkt des öffentlichen Telefonnetz (PSTN)  <br/> |Skype for Business-Benutzer an unterschiedlichen Netzwerkstandorten (d. h. Standort 2)  <br/> |Die Bezusendungsübergang mit Weisung ist nicht zulässig.  <br/> |
|Endpunkt des öffentlichen Telefonnetz (PSTN)  <br/> |Skype for Business-Benutzer an einem unbekannten Netzwerkstandort  <br/> |Die Bezusendungsübergang mit Weisung ist nicht zulässig.  <br/> |
|Endpunkt des öffentlichen Telefonnetz (PSTN)  <br/> |Skype for Business-Partnerbenutzer  <br/> |Die Bezusendungsübergang mit Weisung ist nicht zulässig.  <br/> |
|Endpunkt des öffentlichen Telefonnetz (PSTN)  <br/> |Endpunkt der Nebenstellenanlage am gleichen Standort (d. h. Standort 1)  <br/> |Mit Weisungsübersetzung ist dies zulässig.  <br/> |
|Endpunkt des öffentlichen Telefonnetz (PSTN)  <br/> |Endpunkt der Nebenstellenanlage an einem anderen Standort (d. h. Standort 2)  <br/> |Die Bezusendungsübergang mit Weisung ist nicht zulässig.  <br/> |
|Endpunkt der Nebenstellenanlage am gleichen Standort (d. h. Standort 1)  <br/> |Endpunkt des öffentlichen Telefonnetz (PSTN)  <br/> |Mit Weisungsübersetzung ist dies zulässig.  <br/> |
|Endpunkt der Nebenstellenanlage an einem anderen Standort (d. h. Standort 2)  <br/> |Endpunkt des öffentlichen Telefonnetz (PSTN)  <br/> |Die Bezusendungsübergang mit Weisung ist nicht zulässig.  <br/> |
|Endpunkt der Nebenstellenanlage an einem beliebigen Standort  <br/> |Skype for Business-Benutzer am gleichen Netzwerkstandort (d. h. Standort 1)  <br/> |Mit Weisungsübersetzung ist dies zulässig.  <br/> |
|Endpunkt der Nebenstellenanlage an einem beliebigen Standort  <br/> |Skype for Business-Benutzer an unterschiedlichen Netzwerkstandorten (d. h. Standort 2)  <br/> |Mit Weisungsübersetzung ist dies zulässig.  <br/> |
|Endpunkt der Nebenstellenanlage an einem beliebigen Standort  <br/> |Skype for Business-Benutzer an einem unbekannten Netzwerkstandort  <br/> |Mit Weisungsübersetzung ist dies zulässig.  <br/> |
|Endpunkt der Nebenstellenanlage an einem beliebigen Standort  <br/> |Skype for Business-Partnerbenutzer  <br/> |Mit Weisungsübersetzung ist dies zulässig.  <br/> |

## <a name="requirements"></a>Anforderungen

Die Location-Based Routing for Conferencing-Anwendung erfordert, dass skype for Business Server oder Lync Server 2013 Kumulatives Update 2 auf allen Front-End-Pools und Standard Edition-Servern in Ihrer Topologie bereitgestellt wird. Wenn diese Serverversionen auf einigen Servern in Ihrer Topologie nicht installiert sind, können Location-Based Routingeinschränkungen für Besprechungen und Anrufübertragungen mit Beanrufen mit Beanrufen nicht vollständig erzwungen werden.

In der folgenden Tabelle ist die Kombination aus Serverrollen und Versionen aufgeführt, die Location-Based unterstützen.


|Front-End Poolversion|Vermittlungsserverversion|Unterstützt|
|:-----|:-----|:-----|
|Kumulatives Update 2 für Skype for Business Server oder Lync Server 2013  <br/> |Kumulatives Update 2 für Skype for Business Server oder Lync Server 2013  <br/> |Ja  <br/> |
|Lync Server 2013 Kumulatives Update 2  <br/> |Lync Server 2013 Kumulatives Update 1  <br/> |Nein  <br/> |
|Lync Server 2013 Kumulatives Update 2  <br/> |Lync Server 2010  <br/> |Nein  <br/> |
|Lync Server 2013 Kumulatives Update 2  <br/> |Office Communications Server 2007 R2  <br/> |Nein  <br/> |
|Lync Server 2013 Kumulatives Update 1  <br/> |Beliebig  <br/> |Nein  <br/> |
|Lync Server 2010  <br/> |Beliebig  <br/> |Nein  <br/> |
|Office Communications Server 2007 R2  <br/> |Beliebig  <br/> |Nein  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>Konfiguration des Location-Based für Konferenzen

Die Location-Based routing for Conferencing application basiert auf der Konfiguration des Location-Based Routing. Die wichtigsten Konfigurationen sind:

- Der Ort der Teilnehmer, die einer Besprechung beitreten, wird basierend auf ihrem Netzwerkstandort bestimmt. Ein Netzwerkstandort und die zugehörigen Netzwerksubnetze müssen in Skype for Business Server definiert werden, um das Routing Location-Based erzwingen.

- Um das Location-Based von Besprechungen zu erzwingen, müssen Skype for Business-Teilnehmer für das Location-Based aktiviert sein.

- Zum Erzwingen Location-Based Routing von PSTN-Endpunkten, die an Besprechungen teilnehmen, muss der zum Verbinden der Endpunkte im öffentlichen Telefonnetz verwendete SIP-Trunk für das Location-Based konfiguriert werden.

## <a name="enabling-the-location-based-routing-for-conferencing"></a>Aktivieren des Location-Based für Konferenzen

Die Location-Based A0 für Konferenzen ist standardmäßig deaktiviert. Bevor Sie diese Anwendung aktivieren, müssen Sie die richtige Priorität für die Anwendung bestimmen. Führen Sie das folgende Cmdlet in der Skype for Business Server-Verwaltungsshell aus, um diese Priorität zu ermitteln:

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

In diesem Cmdlet ist dies der Pool, in dem \<Pool FQDN\> Location-Based routing for Conferencing application aktiviert werden soll.

Dieses Cmdlet gibt die Liste der von Skype for Business Server gehosteten Anwendungen und den Prioritätswert für jede dieser Anwendungen zurück. Der Location-Based Routing for Conferencing-Anwendung muss ein Prioritätswert zugewiesen werden, der größer als die Anwendung "UdcAgent" und kleiner als die Anwendungen "DefaultRouting", "ExumRouting" und "OutboundRouting" ist. Es wird empfohlen, der Location-Based Routing for Conferencing-Anwendung einen Prioritätswert zuzuordnen, der einen Punkt über dem Prioritätswert der Anwendung "UdcAgent" liegt.

Wenn die Anwendung "UdcAgent" beispielsweise den Prioritätswert "2" hat, die Anwendung "DefaultRouting" den Prioritätswert "8", die Anwendung "ExumRouting" den Prioritätswert "9" und die Anwendung "OutboundRouting" den Prioritätswert "10" hat, sollten Sie der Location-Based Routing for Conferencing-Anwendung den Prioritätswert "3" zuweisen. Dadurch wird die Priorität der Anwendungen in der folgenden Reihenfolge festgelegt: Andere Anwendungen (Prioritäten: 0 bis 1), "UdcAgent" (Priorität: 2), Location-Based Routingkonferenzanwendung (Priorität: 3), andere Anwendungen (Prioritäten: 4 bis 8), "DefaultRouting" (Priorität: 9), "ExumRouting" (Priorität: 10) und "OutboundRouting" (Priorität: 11).

Nachdem Sie den richtigen Prioritätswert für die Location-Based Routing for Conferencing-Anwendung finden, geben Sie das folgende Cmdlet für jeden Front-End-Pool oder Standard Edition-Server ein, auf dem benutzer, die für das routing aktiviert sind, Location-Based sind:

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri <http://www.microsoft.com/LCS/LBRouting>
```

Beispiel:

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

Starten Sie nach Verwendung dieses Cmdlets alle Front-End-Server im Pool oder auf den Standard Edition-Servern neu, auf denen die Location-Based Routing for Conferencing-Anwendung aktiviert wurde.

> [!IMPORTANT]
> Location-Based routing enforcements to conferences or consultative transfers won't be enforced until all the Front End Servers in the applicable pools or the Standard Edition Servers are restarted. Wenn Sie **"-Critical"** **$true** vorherigen Cmdlets festlegen, werden Ihre Skype for Business Server-Dienste sofort neu gestartet. Wenn Sie nicht möchten, dass diese Dienste sofort neu gestartet werden, legen Sie **"-Critical"** vorerst auf **$false,** und verwenden Sie **"Set-CsServerApplication",** um **"-Critical"** zu **$true** zu ändern, nachdem die Dienste neu gestartet wurden.

Nachdem die Location-Based Routing for Conferencing-Anwendung erfolgreich aktiviert und alle entsprechenden Server neu gestartet wurden, werden alle Konferenzen überwacht, die von Skype for Business-Benutzern organisiert wurden, die für Location-Based Routing aktiviert sind, um eine gebührenpflichtige Umgehung des Telefonnetz zu verhindern.


