---
title: 'Lync Server 2013: Konfiguration von standortbasiertem Routing für Konferenzen'
TOCTitle: Konfiguration von standortbasiertem Routing für Konferenzen
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56269353
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfiguration von standortbasiertem Routing für Konferenzen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Die Anwendung für standortbasiertes Routing für Konferenzen setzt auf der Konfiguration des standortbasierten Routings von Lync Server 2013 auf. Es gibt die folgenden Hauptkonfigurationen:

  - Der Standort von Teilnehmern, die an einer Besprechung teilnehmen, wird anhand ihres Netzwerkstandorts ermittelt. Ein Netzwerkstandort und dessen zugehörige Netzwerksubnetze müssen in Lync Server definiert sein, damit standortbasiertes Routing erzwungen werden kann.

  - Damit standortbasiertes Routing für Besprechungen erzwungen werden kann, müssen Lync-Teilnehmer für standortbasiertes Routing aktiviert sein.

  - Damit standortbasiertes Routing von Telefonfestnetzendstellen, die an Besprechungen teilnehmen, erzwungen werden kann, muss die SIP-Fernvermittlungsleitung (SIP-Trunk), über die die Telefonfestnetzendstelle angeschlossen sind, für standortbasiertes Routing konfiguriert sein.

Weitere Informationen zum Bereitstellen und Konfigurieren von standortbasiertem Routing für Lync Server 2013 finden Sie unter [Konfigurieren von standortbasiertem Routing](lync-server-2013-configuring-location-based-routing.md).

## Aktivieren der Anwendung für standortbasiertes Routing für Konferenzen

Die Anwendung für standortbasiertes Routing für Konferenzen ist standardmäßig deaktiviert. Bevor Sie diese Anwendung aktivieren, müssen Sie die richtige Priorität ermitteln, die für die Anwendung zugewiesen werden muss. Um diese Priorität zu ermitteln, führen Sie das folgende Cmdlet in Lync Server-Verwaltungsshell aus:

Get-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\>

In diesem Cmdlet gibt **\<Pool FQDN\>** den Pool an, in dem die Anwendung für standortbasiertes Routing für Konferenzen aktiviert werden muss.

Dieses Cmdlet gibt die Liste der Anwendungen, die von Lync Server gehostet werden, sowie den Prioritätswert für jede der Anwendungen zurück. Der Anwendung für standortbasiertes Routing für Konferenzen muss ein Prioritätswert zugewiesen werden, der größer als der für die Anwendung **UdcAgent** und kleiner als der für die Anwendungen **DefaultRouting** , **ExumRouting** und **OutboundRouting** ist. Es empfiehlt sich, der Anwendung für standortbasiertes Routing für Konferenzen einen Prioritätswert zuzuweisen, der einen Punkt höher ist als der Prioritätswert der Anwendung **UdcAgent** .

Wenn die Anwendung **UdcAgent** beispielsweise den Prioritätswert **2** , die Anwendung **DefaultRouting** den Prioritätswert **8** , die Anwendung **ExumRouting** den Prioritätswert **9** und die Anwendung **OutboundRouting** den Prioritätswert **10** hat, sollten Sie der Anwendung für standortbasiertes Routing für Konferenzen den Prioritätswert **3** zuweisen. Dadurch ergibt sich aus den Prioritäten der Anwendungen diese Reihenfolge: andere Anwendungen (Prioritäten: 0 bis 1), **UdcAgent** (Priorität: 2), Anwendung für standortbasiertes Routing für Konferenzen (Priorität: 3), andere Anwendungen (Prioritäten: 4 to 8), **DefaultRouting** (Priorität: 9), **ExumRouting** (Priorität 10) und **OutboundRouting** (Priorität: 11).

Nachdem Sie die richtige Priorität für die Anwendung für standortbasiertes Routing für Konferenzen ermittelt haben, geben Sie das folgende Cmdlet für jeden Front-End-Server des Pools oder jeden Standard Edition-Server ein, auf dem Benutzer verwaltet werden, für die standortbasiertes Routing aktiviert ist:

New-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\>/LBRouting -Priority \<Application Priority\> -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting

Beispiel:

New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting

Nachdem Sie dieses Cmdlet ausgeführt haben, starten Sie alle Front-End-Server des Pools oder die Standard Edition-Server neu, auf denen die Anwendung für standortbasiertes Routing für Konferenzen aktiviert wurde.


> [!IMPORTANT]
> Standortbasiertes Routing für Konferenzen oder Gesprächsübergaben wird erst erzwungen, wenn alle Front-End-Server in den entsprechenden Pools oder die Standard Edition-Server neu gestartet wurden. Wenn Sie in den vorangehenden Cmdlets <STRONG>–Critical</STRONG> auf <STRONG>$true</STRONG> festlegen, werden Ihre Lync-Dienste sofort neu gestartet. Wenn diese Dienste nicht sofort neu gestartet werden sollen, legen Sie vorerst <STRONG>–Critical</STRONG> auf <STRONG>$false</STRONG> fest und verwenden Sie dann <STRONG>Set-CsServerApplication</STRONG>, um <STRONG>-Critical</STRONG> nach dem Neustart der Dienste auf <STRONG>$true</STRONG> festzulegen.



Sobald die Anwendung für standortbasiertes Routing für Konferenzen erfolgreich aktiviert wurde und alle entsprechenden Lync-Server neu gestartet wurden, werden alle Konferenzen, die von Lync-Benutzern organisiert werden, für die standortbasiertes Routing aktiviert ist, überwacht, um ein Umgehen von Gebühren für das Telefonfestnetz zu verhindern.

