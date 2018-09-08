---
title: Standortbasierte Weiterleitung für Konferenzen in Skype für Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
description: Überträgt die Planung für standortbasierte für Konferenzen in Skype für Business Server Enterprise-VoIP-routing, einschließlich konsultieren Anruf.
ms.openlocfilehash: 97ceaeb4f7e6e24cdffe3f1fd8c737de2e429e17
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23888360"
---
# <a name="location-based-routing-for-conferencing-in-skype-for-business-server"></a>Standortbasierte Weiterleitung für Konferenzen in Skype für Business Server

Überträgt die Planung für standortbasierte für Konferenzen in Skype für Business Server Enterprise-VoIP-routing, einschließlich konsultieren Anruf.

Speicherortbasierte Routing ermöglicht das routing von Anrufen zwischen VoIP-Endpunkten und PSTN-Endgeräten basierend auf den Speicherort der Parteien in den Anruf zu beschränken. Standortbasierte Weiterleitung für Konferenzen können Sie auf Standortbasierte Routing Regeln erzwingen Besprechungen (d. h. Konferenzen), um zu verhindern, dass PSTN gebührenpflichtige umgehen. Die Anwendung eine aktive Konferenz überwacht und erzwingt Routing speicherortbasierte Einschränkungen basierend auf den Speicherort der Benutzer teilnehmen. Speicherortbasierte Routing für Konferenzen Anwendung können Sie zusätzlich die Durchsetzung der speicherortbasierte Routing Einschränkungen zu konsultieren im Zusammenhang mit PSTN-Endpunkten übertragen.

Die Standortbasierte Weiterleitung Conferencing-Anwendung enthält Skype für Business-Konferenzen, die ein Mechanismus für die Vermeidung von PSTN-Gebühren zu umgehen. Die Anwendung überwacht aktive Konferenzen und erzwingt Routing speicherortbasierte Einschränkungen basierend auf den Speicherort der der Skype für Unternehmensbenutzer teilnehmen.

Die Standortbasierte Weiterleitung Conferencing-Anwendung bestimmt, ob speicherortbasierte Routing für einen Skype für Business Besprechung erzwungen werden, wenn die folgenden Kriterien erfüllt sind:

- Der Organisator der Besprechung ist für standortbasierte Routing aktiviert. Speicherortbasierte Routing Einschränkungen werden nur für Konferenzen angewendet, die von Benutzern organisiert werden, die für das Routing speicherortbasierte aktiviert sind.

- Mindestens ein Besprechungsteilnehmer befindet sich an einem Endpunkt im öffentlichen Telefonnetz (PSTN). Speicherortbasierte Routing Einschränkungen gelten nur für Konferenzen, die PSTN-Endgeräten enthalten.

- Der Netzwerkstandort, an dem sich das PSTN-Gateway zum Überbrücken der Konferenz in das PSTN befindet, wird ebenso lokalisiert wie die Netzwerkstandorte, von denen aus die Organisatoren und Teilnehmer die Verbindung herstellen.

Speicherortbasierte Routing für Live Meeting-Anwendung verhindert, dass die Beteiligung von Skype für Geschäftsbenutzer und PSTN-Endpunkten aus verschiedenen Netzwerkstandorten zur gleichen Konferenz. Wenn der Organisator einer Besprechung für standortbasierte Routing aktiviert ist, erzwingt die Live Meeting-Anwendung die folgenden Einschränkungen:

- Die Endpunkte, die ein Skype für Business Besprechung beitreten können hängen von der Endpunkte, die bereits an der Konferenz Teil und diese Einschränkung passt als verlassen einer verknüpften Endpunkte und neue Endpunkte an der Konferenz teilnehmen. Wenn eine Skype für Business Besprechung über den gleichen Netzwerkstandort, und klicken Sie dann einen PSTN-Endpunkt, einen anderen Teilnehmer aus der gleichen Netzwerkstandort, einen anderen Teilnehmer aus einem anderen Netzwerkstandort oder eines Teilnehmers aus einem unbekannten Netzwerkstandort Organisatoren und Teilnehmer beitreten dürfen zur Teilnahme an.

- Wenn Organisatoren und Teilnehmer von unterschiedlichen oder unbekannten Netzwerkstandorten aus an der Besprechung teilnehmen, darf ein Teilnehmer an einem PSTN-Endpunkt nicht an der Besprechung teilnehmen, wenn der PSTN-Anruf von einem SIP-Trunk eingeht, der für das standortbasierte Routing aktiviert ist.

- Wenn die Organisatoren und Teilnehmer alle an der Besprechung aus der gleichen Network-Website teilzunehmen werden und Teilnehmer an der gleichen Besprechung aus dem Telefonfestnetz vorhanden sind, ist eine Skype für Business-Endpunkt, von einem anderen Netzwerkstandort nicht zulässig, an der Besprechung teilnehmen.

Diese Konferenzen speicherortbasierte Routing Einschränkungen sind in der folgenden Tabelle zusammengefasst.

| |
|**Benutzer in einer Konferenz an einem beliebigen Standort**|**Benutzer, die an der Konferenz teilnehmen dürfen**|**Benutzer, die nicht an der Konferenz teilnehmen dürfen**|
|:-----|:-----|:-----|
|Skype für Business VoIP-Client-Benutzer aus einer Website für die einzelnen Netzwerk  <br/> |Skype für Business VoIP-Client-Benutzer aus der gleichen Network-Website  <br/> Skype für Business VoIP-Client-Benutzer aus einer anderen Netzwerk-Website  <br/> Skype für Business VoIP-Client-Benutzer aus einem unbekannten Netzwerkstandort  <br/> Verbundpartner Skype Business VoIP-Client-Benutzers  <br/> Benutzer, die über PSTN-Endpunkt teilnehmen  <br/> |-  <br/> |
|Skype für Business VoIP-Client-Benutzer aus einem unbekannten Netzwerkstandort  <br/> |Skype für Business VoIP-Client-Benutzer aus einer beliebigen Website  <br/> Skype für Business VoIP-Client-Benutzer aus einem unbekannten Standort  <br/> Verbundpartner Skype Business VoIP-Client-Benutzers  <br/> |Benutzer, die über einen PSTN-Endpunkt teilnehmen  <br/> |
|Skype für Business VoIP-Clientbenutzer aus verschiedenen Netzwerkstandorten  <br/> |Skype für Business VoIP-Client-Benutzer aus einer beliebigen Network-Website  <br/> Skype für Business VoIP-Client-Benutzer aus einem unbekannten Netzwerkstandort  <br/> Verbundpartner Skype Business VoIP-Client-Benutzers  <br/> |Benutzer, die über einen PSTN-Endpunkt teilnehmen  <br/> |
|Skype für Business VoIP-Client-Benutzer aus einem einzelnen Netzwerkstandort und Benutzern, die von einem PSTN-Endpunkt beitreten  <br/> |Skype für Business VoIP-Client-Benutzer aus der gleichen Network-Website  <br/> |Skype für Business VoIP-Client-Benutzer aus einer anderen Netzwerk-Website  <br/> Skype für Business VoIP-Client-Benutzer aus einem unbekannten Netzwerkstandort  <br/> Verbundpartner Skype Business VoIP-Client-Benutzers  <br/> |

Im folgenden sind zusätzliche Merkmale des speicherortbasierte Routing für Live Meeting-Anwendung:

- Wenn ein Benutzer nicht zulässig ist, Teilnahme an einer Konferenz speicherortbasierte Routing Einschränkungen angegeben, der Anruf an der Konferenz abgelehnt, und es die Skype für Business-Client wird Bericht, der der Anruf nicht wurde abgeschlossen oder beendet wurde.

- Ein PSTN Endpunkt teilnehmen an eine Konferenz mit Routing speicherortbasierte Bescheide nicht werden eingeschränkte ungeachtet des Zustands die Konferenz beitreten, wenn der Endpunkt über einen Trunk zugeordnet wird, die für das Routing speicherortbasierte nicht aktiviert ist.

- Ein PBX-System über einen SIP-Trunk, die keine Anrufe an das Telefonfestnetz egress auf einen Vermittlungsserver verbunden haben dieselbe Bescheide als Skype für Unternehmensbenutzer befindet sich in der gleichen Network-Website, in der SIP-Trunk definiert ist. Ein PSTN-Endpunkt werden beispielsweise zur Teilnahme an einer Konferenz mit einem PBX-Benutzer und einen Skype für Geschäftsbenutzer, wenn sie auf der gleichen Website Netzwerk befinden können; andernfalls, die der PSTN-Endpunkt nicht zulässig an der Konferenz teilnehmen, wenn der PBX-Benutzer in einem anderen Netzwerkstandort als die Skype für Geschäftsbenutzer ist.

> [!NOTE]
> Mit dem kumulativen Update 4 für Skype for Business sollte das Verhalten in der folgenden Tabelle beobachtet werden.

|**User**|**Andere Teilnehmer**|**Aktion**|**Ergebnis**|
|:-----|:-----|:-----|:-----|
|Skype for Business Mobile  <br/> |Telefonfestnetz (PSTN)  <br/> |Skype for Business Mobile ist in einem PSTN-Anruf. Skype for Business Mobile stuft den Anruf dann zu einem Conference Auto Attendant (CAA) hoch.  <br/> |Der Anruf wird mit einer entsprechenden Fehlermeldung blockiert.  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business-Client oder Verbundbenutzer  <br/> |Der Client oder zum Verbund gehörenden Benutzer ist auf einen VoIP-Anruf an einen Skype für Benutzer Business Mobile Location-Based Routing und Kommunikationspartner eskaliert, um eine CAA.  <br/> |Der Eskalationsanruf wird mit einer entsprechenden Fehlermeldung blockiert.  <br/> |

## <a name="consultative-call-transfers"></a>Anrufdurchstellungen mit Ankündigung

Zusätzlich zum Erzwingen von speicherortbasierte Routing zu Skype für Business Besprechungen, erzwingt speicherortbasierte Routing für Konferenzen Anwendung standortbasierte Routing Einschränkungen auf konsultieren Call gehandelt, die egress mit PSTN-Endgeräten. Übertragung konsultieren Anruf ist ein zwischen zwei Parteien, in dem eine der Parteien den Anruf an einen neuen Benutzer überträgt, hergestellt wird. Zum Beispiel ruft ein PSTN-Endpunkt Benutzer (Skype für Business aufgerufenen). Benutzer A bestimmt, dass der PSTN-Benutzer an Benutzer B (Skype für Geschäftsbenutzer) weitergeleitet werden sollen. Benutzer A platziert, die der Anruf mit dem PSTN-Benutzer in der Warteschleife und Anrufe Benutzer b Benutzer B zustimmt an das PSTN-Benutzer sprechen. Benutzer A überträgt den Anruf auf Haltestatus an Benutzer B.

**Anruffluss bei einer Anrufdurchstellung mit Ankündigung**

![Standortbasiertes Routing für Konferenzen (Diagramm)](../../media/LocationBasedRoutingForConferencing.jpg)

Wenn ein Benutzer für standortbasierte Routing initiiert Übertragung konsultieren Anruf von einem PSTN-Endpunkt (wie in der vorherigen Abbildung gezeigt) aktiviert, erstellt zwei aktive Anrufe, einen Anruf zwischen dem PSTN-Benutzer und Skype für Business Benutzer A und andere zwischen Skype für Geschäftsbenutzer A und Skype für Geschäftsbenutzer b das folgende Verhalten wird durch die standortbasierte Routing für Konferenzen Anwendung erzwungen:

- Wenn der SIP-Trunk-routing PSTN aufrufen ist autorisiert, eine Route weitergeleitet PSTN-Anruf auf den Netzwerkstandort, in dem Skype für Geschäftsbenutzer B (d. h. Übertragung Ziel) befindet, dann den Anruf weiterleiten kann; Andernfalls wird die Weiterleitung konsultieren Anruf blockiert. Diese Autorisierung erfolgt basierend auf der übertragenen Partei Speicherort wird in der gleichen Network-Website als den SIP-Trunk, der der aktiven Anruf an den Endpunkt PSTN weitergeleitet wurde.

- Wenn der SIP-Trunk-routing eingehenden PSTN-Anruf ist nicht autorisiert, für das Anrufrouting auf den Netzwerkstandort, in dem die übertragene Partei (Skype für Business Benutzer B) gespeichert ist, oder die übertragene Partei befindet sich in einem unbekannten Netzwerkstandort, klicken Sie dann der konsultieren Anruf weiterleiten an der PSTN-Endpunkt (d. h. Anruf weiterleiten Ziel) werden blockiert.

In der folgenden Tabelle wird beschrieben, wie standortbasierte Routing Einschränkungen durch die standortbasierte Routing für Konferenzen Anwendung für konsultieren Call gehandelt angewendet werden. Zwar sind Nebenstellenanlagenendgeräte nicht direkt einem Netzwerkstandort zugewiesen, aber die SIP-Vermittlungsleitung, an die die jeweilige Nebenstellenanlage angeschlossen ist, kann einem Netzwerkstandort zugewiesen sein. Daher kann ein Nebenstellenanlagenendgerät indirekt einem Netzwerkstandort zugewiesen sein.


|**Netzwerkstandort des Teilnehmers, dessen Anruf durchgestellt wird**|**Netzwerkstandort des Ziels der Anrufdurchstellung**|**Verhalten**|
|:-----|:-----|:-----|
|Endpunkt im öffentlichen Telefonnetz  <br/> |Skype für Geschäftsbenutzer im gleichen Netzwerkstandort (d. h. Website 1)  <br/> |Anrufdurchstellung mit Ankündigung wird zugelassen  <br/> |
|Endpunkt im öffentlichen Telefonnetz  <br/> |Skype für Geschäftsbenutzer in verschiedenen Netzwerkstandorten (d. h. Website 2)  <br/> |Anrufdurchstellung mit Ankündigung wird nicht zugelassen  <br/> |
|Endpunkt im öffentlichen Telefonnetz  <br/> |Skype für Benutzer in einem unbekannten Netzwerkstandort Business  <br/> |Anrufdurchstellung mit Ankündigung wird nicht zugelassen  <br/> |
|Endpunkt im öffentlichen Telefonnetz  <br/> |Verbundpartner Skype für Geschäftsbenutzer  <br/> |Anrufdurchstellung mit Ankündigung wird nicht zugelassen  <br/> |
|Endpunkt im öffentlichen Telefonnetz  <br/> |Nebenstellenanlagenendgerät am selben Standort (d. h. Standort 1)  <br/> |Anrufdurchstellung mit Ankündigung wird zugelassen  <br/> |
|Endpunkt im öffentlichen Telefonnetz  <br/> |Nebenstellenanlagenendgerät an einem anderen Standort (d. h. Standort 2)  <br/> |Anrufdurchstellung mit Ankündigung wird nicht zugelassen  <br/> |
|Nebenstellenanlagenendgerät am selben Standort (d. h. Standort 1)  <br/> |Endpunkt im öffentlichen Telefonnetz  <br/> |Anrufdurchstellung mit Ankündigung wird zugelassen  <br/> |
|Nebenstellenanlagenendgerät in einem anderen Standort (d. h. Standort 2)  <br/> |Endpunkt im öffentlichen Telefonnetz  <br/> |Anrufdurchstellung mit Ankündigung wird nicht zugelassen  <br/> |
|Nebenstellenanlagenendgerät in einem beliebigen Standort  <br/> |Skype für Geschäftsbenutzer im gleichen Netzwerkstandort (d. h. Website 1)  <br/> |Anrufdurchstellung mit Ankündigung wird zugelassen  <br/> |
|Nebenstellenanlagenendgerät in einem beliebigen Standort  <br/> |Skype für Geschäftsbenutzer in verschiedenen Netzwerkstandorten (d. h. Website 2)  <br/> |Anrufdurchstellung mit Ankündigung wird zugelassen  <br/> |
|Nebenstellenanlagenendgerät in einem beliebigen Standort  <br/> |Skype für Benutzer in einem unbekannten Netzwerkstandort Business  <br/> |Anrufdurchstellung mit Ankündigung wird zugelassen  <br/> |
|Nebenstellenanlagenendgerät in einem beliebigen Standort  <br/> |Verbundpartner Skype für Geschäftsbenutzer  <br/> |Anrufdurchstellung mit Ankündigung wird zugelassen  <br/> |

## <a name="requirements"></a>Voraussetzungen

Speicherortbasierte Routing für Konferenzen Anwendung erfordert, dass entweder Skype für Business Server oder Lync Server 2013 kumulative Update 2 auf allen Front-End-Pools und Standard Edition-Servern in Ihrer Topologie bereitgestellt wird. Dieser Serverversionen nicht auf manchen Servern in Ihrer Topologie installiert sind, können nicht speicherortbasierte Routing Einschränkungen werden, vollständig auf Besprechungen erzwungene und Beratung Übertragungen aufrufen.

Die folgende Tabelle zeigt die Kombination von Serverrollen und Versionen, die standortbasierte Routing zu unterstützen.


|**Version des Front-End-Pools**|**Version des Vermittlungsservers**|**Unterstützt**|
|:-----|:-----|:-----|
|Skype für Business Server oder für Lync Server 2013 Kumulatives Update 2  <br/> |Skype für Business Server oder für Lync Server 2013 Kumulatives Update 2  <br/> |Ja  <br/> |
|Lync Server 2013, kumulatives Update 2  <br/> |Lync Server 2013, kumulatives Update 1  <br/> |Nein  <br/> |
|Lync Server 2013, kumulatives Update 2  <br/> |Lync Server 2010  <br/> |Nein  <br/> |
|Lync Server 2013, kumulatives Update 2  <br/> |Office Communications Server 2007 R2  <br/> |Nein  <br/> |
|Lync Server 2013, kumulatives Update 1  <br/> |Beliebig  <br/> |Nein  <br/> |
|Lync Server 2010  <br/> |Beliebig  <br/> |Nein  <br/> |
|Office Communications Server 2007 R2  <br/> |Beliebig  <br/> |Nein  <br/> |

## <a name="configuration-of-location-based-routing-for-conferencing"></a>Konfiguration der Standortbasierte Weiterleitung für Konferenzen

Speicherortbasierte Routing für Konferenzen Anwendung nutzt die Konfiguration der speicherortbasierte Routing. Es gibt folgende Hauptkonfigurationen:

- Der Standort von Teilnehmern, die an einer Besprechung teilnehmen, wird anhand ihres Netzwerkstandorts ermittelt. Einem Netzwerkstandort und die zugehörigen Netzwerksubnetzen müssen in Skype für Business Server, um die standortbasierte Routing erzwingen definiert werden.

- Zum Erzwingen der speicherortbasierte Routing von Besprechungen muss Skype für Business Teilnehmer für standortbasierte Routing aktiviert sein.

- Zum Erzwingen der speicherortbasierte Routing von PSTN-Endpunkten teilnehmen an Besprechungen muss der SIP-Trunk hergestellt PSTN-Endpunkten für standortbasierte Routing konfiguriert werden.

## <a name="enabling-the-location-based-routing-for-conferencing"></a>Aktivieren die Standortbasierte Weiterleitung für Konferenzen

Speicherortbasierte Routing für Live Meeting-Anwendung ist standardmäßig deaktiviert. Bevor Sie diese App aktivieren, müssen Sie die korrekte Priorität ermitteln, die für die App zugewiesen werden muss. Wenn dieser Priorität ermitteln möchten, führen Sie das folgende Cmdlet in Skype für Business Server-Verwaltungsshell:

Get-CsServerApplication-Identity Service: Registrar:<Pool FQDN>In dieses Cmdlet \<Pool-FQDN\> wird von der Pool, in dem die standortbasierte Routing für Konferenzen Anwendung aktiviert werden soll.

Dieses Cmdlet gibt die Liste der von Skype für Business Server und der Prioritätswert für jede von ihnen gehosteten Anwendungen zurück. Speicherortbasierte Routing für Konferenzen Anwendung muss einen Wert größer als die Anwendung "UdcAgent" und kleiner als die Anwendungen "DefaultRouting", "ExumRouting" und "OutboundRouting" zugewiesen werden. Es wird empfohlen, dass Sie die standortbasierte Routing für Live Meeting-Anwendung einen Prioritätswert zuweisen, der ein Punkt höher ist als der Wert der Anwendung "UdcAgent" ist.

Beispielsweise, wenn die Anwendung "UdcAgent" den Prioritätswert "2" hat, die Anwendung "DefaultRouting" hat den Prioritätswert "8", die Anwendung "ExumRouting" hat den Prioritätswert "9" und die Anwendung "OutboundRouting" hat einen Prioritätswert "10" Sie sollten die standortbasierte Routing für Konferenzen Anwendung der Prioritätswert "3" zuweisen. Auf diese Weise würde setzen die Priorität der Anwendungen in der folgenden Reihenfolge: andere Anwendungen (Prioritäten: 0 bis 1), "UdcAgent" (Priorität: 2), speicherortbasierte Routing Conferencing-Anwendung (Priorität: 3), andere Anwendungen (Prioritäten: 4 bis 8), " DefaultRouting"(Priorität: 9),"ExumRouting"(Priorität: 10) und"OutboundRouting"(Priorität: 11).

Nachdem Sie den richtigen Prioritätswert für standortbasierte Routing für Konferenzen Anwendung ermittelt wird, geben Sie das folgende Cmdlet für jeden Front-End-Pool oder Standard Edition-Server, die für das Routing speicherortbasierte Hause Benutzer aktiviert:

New-CsServerApplication-Identity Service: Registrar:<Pool FQDN>/LBRouting-Priorität <Application Priority> -aktiviert $true-kritische $true - Uri https://www.microsoft.com/LCS/LBRoutingFor Beispiel:

New-CsServerApplication-Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting-Priorität 3 - aktivierten $true-kritische $true - Uri https://www.microsoft.com/LCS/LBRoutingAfter mit diesem Cmdlet alle Front-End-Server im Pool oder Standard Edition-Server neu starten, auf dem die Speicherortbasierte Routing für Konferenzen, die Anwendung aktiviert wurde.

> [!IMPORTANT]
> Speicherortbasierte Routing Bescheide zu Konferenzen oder Beratung Übertragungen wird nicht erzwungen, bis alle Front-End-Servern in der entsprechenden-Pools oder Standard Edition-Servern neu gestartet werden. Wenn Sie festlegen **-kritische** auf **$true** in der vorstehenden-Cmdlets, die Skype für Business Server-Dienste werden sofort neu gestartet. Wenn Sie keine Dienste, um sofort neu zu starten möchten, legen Sie **-kritische** auf **$false** für jetzt und anschließend mithilfe von **Set-CsServerApplication** ändern **-kritische** auf **$true** später, nach dem Neustart der Dienste.

Sobald speicherortbasierte Routing für Konferenzen Anwendung erfolgreich aktiviert wurde und alle entsprechenden Server neu gestartet wurde, werden alle von Skype für Unternehmensbenutzer für standortbasierte Routing aktiviert organisierte Konferenzen überwacht werden, um zu verhindern, dass PSTN-gebührenpflichtige umgehen


