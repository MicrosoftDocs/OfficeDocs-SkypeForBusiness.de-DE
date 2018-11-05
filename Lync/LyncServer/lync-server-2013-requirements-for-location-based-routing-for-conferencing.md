---
title: Anforderungen für das standortbasierte Routing für Konferenzen
TOCTitle: Anforderungen für das standortbasierte Routing für Konferenzen
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56269293
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anforderungen für das standortbasierte Routing für Konferenzen

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Im Folgenden werden die Anforderungen für die Installation und Konfiguration der Anwendung für das standortbasierten Routing von Konferenzen zusammengefasst:

  - Lync Server 2013, kumulatives Update 2, muss auf allen Servern oder Pools in Ihrer Topologie installiert sein.


> [!NOTE]
> Wenn auf einem Lync-Server oder -Pool in Ihrer Topologie das kumulative Update 2 oder höher für Lync Server 2013 nicht installiert ist, gibt es keine Garantie, dass das standortbasierte Routing von Lync-Besprechungen erzwungen werden kann.



  - Das Feature für standortbasiertes Routing von Lync Server 2013 ist eine Voraussetzung für die Anwendung für das standortbasierte Routing von Konferenzen. Weitere Informationen zum Konfigurieren des Features für standortbasiertes Routing von Lync Server 2013 finden Sie unter [Konfigurieren von standortbasiertem Routing](lync-server-2013-configuring-location-based-routing.md).

  - Die Anforderungen für die Anwendung für das standortbasierte Routing von Konferenzen sind die gleichen wie für das Lync Server 2013-Feature für standortbasiertes Routing. Weitere Informationen finden Sie unter [Planung des standortbasierten Routings](lync-server-2013-planning-for-location-based-routing.md).

## Unterstützte Server

Die Anwendung für das standortbasierte Routing von Konferenzen setzt voraus, dass das kumulative Update 2 für Lync Server auf allen Front-End-Pools und Standard Edition-Servern in Ihrer Topologie bereitgestellt wurde. Wenn das kumulative Update 2 für Lync Server 2013 auf einigen Lync-Servern in der Topologie nicht installiert ist, können die Einschränkungen für das standortbasierte Routing bei Lync-Besprechungen und bei Anrufdurchstellung nach Rücksprache nicht vollständig durchgesetzt werden.

In der folgenden Tabelle ist die Kombination aus Serverrolle und -version angegeben, die standortbasiertes Routing unterstützt.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Version des Front-End-Pools</p></td>
<td><p>Version des Vermittlungsservers</p></td>
<td><p>Unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013, kumulatives Update 2</p></td>
<td><p>Lync Server 2013, kumulatives Update 2</p></td>
<td><p>Ja</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013, kumulatives Update 2</p></td>
<td><p>Lync Server 2013, kumulatives Update 1</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013, kumulatives Update 2</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013, kumulatives Update 2</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013, kumulatives Update 1</p></td>
<td><p>Jede</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010</p></td>
<td><p>Jede</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="even">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>Jede</p></td>
<td><p>Nein</p></td>
</tr>
</tbody>
</table>


## Unterstützte Clients

Die Lync-Clients, die das standortbasierte Routing von Lync-Besprechungen unterstützen, sind die gleichen wie die, die das Lync Server 2013-Feature für standortbasiertes Routing unterstützen. Weitere Informationen finden Sie unter [Planung des standortbasierten Routings](lync-server-2013-client-and-server-support-for-location-based-routing.md).

## Anforderungen des Vermittlungsservers für Anrufdurchstellung nach Rücksprache

Die Anwendung für das standortbasierte Routing von Konferenzen setzt die Bereitstellung von eigenständigen Vermittlungsservern voraus, damit die Einschränkungen für das standortbasierte Routing bei Anrufdurchstellung nach Rücksprache erzwungen werden kann.

Um das standortbasierte Routing für die Anrufdurchstellung nach Rücksprache zu erzwingen, darf der Vermittlungsserver in Netzwerkregionen, in denen das standortbasierte Routing erforderlich ist, nur einem Vermittlungsserver-Peer (d. h. Nebenstellenanlage, SIP-Gateway usw.) zugeordnet sein. Wenn in der gleichen Netzwerkregion weitere Vermittlungsserver bereitgestellt wurden, muss der Vermittlungsserver-Peer eine anderen Vermittlungsserver zugeordnet werden. Im Detail sieht diese Anforderung wie folgt aus:

  - Einzelner Vermittlungsserver pro mehrere Vermittlungsserver-Peers – Wenn eine Anrufdurchstellung nach Rücksprache an einen Vermittlungsserver-Peer über einen Vermittlungsserver geroutet wird, der mit mehreren SIP-Trunks zu mehreren Peers (d. h. Nebenstellenanlagen und Gateways) konfiguriert ist, wird die Anrufdurchstellung nach Rücksprache blockiert, um Gebührenumgehungen in öffentlichen Telefonnetzen zu vermeiden, wenn die Anrufdurchstellung nach Rücksprache von einigen SIP-Trunks durchgelassen, von anderen SIP-Trunks jedoch nicht durchgelassen wurde.
    
    Ein Beispiel: Wenn ein einzelner Vermittlungsserver ein PSTN-Gateway als Vermittlungsserver-Peer und eine Nebenstellenanlage als Vermittlungsserver-Peer bedient, lässt sich das folgende Verhalten beobachten:
    
      - Wenn ein Lync-Benutzer von einem gegebenen Standort (d. h. Standort 1) versucht, einen Anruf mit einem PSTN-Endpunkt an einen Lync-Benutzer an einem anderen Standort (d. h. Standort 2) per Anrufdurchstellung nach Rücksprache durchzustellen, wird der Anruf nicht zugelassen, um Gebührenumgehungen in öffentlichen Telefonnetzen zu vermeiden.
    
      - Wenn ein Lync-Benutzer von einem gegebenen Standort (d. h. Standort 1) versucht, einen Anruf mit einem Endpunkt an einer Nebenstellenanlage an einen Lync-Benutzer am gleichen Standort (Standort 1) per Anrufdurchstellung nach Rücksprache durchzustellen, wird der Anruf auch dann nicht zugelassen, wenn es dadurch nicht zu potenziellen Gebührenumgehungen in öffentlichen Telefonnetzen kommt.

  - Separate Vermittlungsserver pro Vermittlungsserver-Peer
    
    Wenn eine Anrufdurchstellung nach Rücksprache einen Vermittlungsserver-Peer zum Ziel hat, wird die Durchstellung nach Rücksprache von dem einzelnen Vermittlungsserver-Peer geprüft, der von dem Vermittlungsserver bedient wird. Der Anruf wird basierend auf seinem Potenzial zur Verursachung von Gebührenumgehungen in öffentlichen Telefonnetzen zugelassen oder nicht zugelassen, und zwar ungeachtet aller anderen Vermittlungsserver-Peers am Standort, da diese von anderen Vermittlungsservern bedient werden.
    
    Ein Beispiel: Wenn ein separater Vermittlungsserver ein PSTN-Gateway als Vermittlungsserver-Peer und eine Nebenstellenanlage als Vermittlungsserver-Peer bedient, lässt sich das folgende Verhalten beobachten:
    
      - Wenn ein Lync-Benutzer von einem gegebenen Standort (d. h. Standort 1) versucht, einen Anruf mit einem PSTN-Endpunkt an einen Lync-Benutzer an einem anderen Standort (d. h. Standort 2) per Anrufdurchstellung nach Rücksprache durchzustellen, wird der Anruf nicht zugelassen, um Gebührenumgehungen in öffentlichen Telefonnetzen zu vermeiden.
    
      - Wenn ein Lync-Benutzer von einem gegebenen Standort (d. h. Standort 1) versucht, einen Anruf mit einem Endpunkt an einer Nebenstellenanlage an einen Lync-Benutzer am gleichen Standort (Standort 1) per Anrufdurchstellung nach Rücksprache durchzustellen, wird der Anruf zugelassen, da er keine potenziellen Gebührenumgehungen in öffentlichen Telefonnetzen verursacht.

## Funktionen, die von der Anwendung für das standortbasierte Routing von Konferenzen nicht unterstützt werden

Die folgenden Funktionen werden von der Anwendung für das standortbasierte Routing von Konferenzen nicht unterstützt:

  - Einwahlkonferenzen. Das standortbasierte Routing kann nicht für Einwahlkonferenzen erzwungen werden. Jede Einwahlanforderung für eine gegebene Konferenz wird auch dann nicht vom standortbasierten Routing eingeschränkt, wenn der Konferenzorganisator ein Lync-Benutzer ist, für den das standortbasierte Routing aktiviert wurde.

  - Es empfiehlt sich, eine Konferenzzugriffsnummern in Regionen bereitzustellen, in denen Einschränkungen für das standortbasierte Routing erzwungen werden müssen.

