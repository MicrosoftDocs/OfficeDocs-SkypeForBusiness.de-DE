---
title: Konfigurieren von Netzwerkstandorten für die Anrufsteuerung in Lync Server 2013
TOCTitle: Konfigurieren von Netzwerkstandorten für die Anrufsteuerung in Lync Server 2013
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412840(v=OCS.15)
ms:contentKeyID: 49295105
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Netzwerkstandorten für die Anrufsteuerung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-05_


> [!IMPORTANT]
> Wenn Sie bereits Netzwerkstandorte für E9-1-1 oder die Medienumgehung erstellt haben, können Sie mithilfe des Cmdlets <STRONG>Set-CsNetworkSite</STRONG> die vorhandenen Netzwerkstandorte ändern, um ein Bandbreitenrichtlinienprofil anzuwenden. Ein Beispiel für die Änderung eines Netzwerkstandorts finden Sie unter <A href="lync-server-2013-create-or-modify-a-network-site.md">Erstellen oder Ändern eines Netzwerkstandorts in Lync Server 2013</A>.



Bei *Netzwerkstandorten* handelt es sich um Büros oder Zweigstellen innerhalb der einzelnen Netzwerkregionen von Bereitstellungen mit Anrufsteuerung (Call Admission Control, CAC), E9-1-1 und Medienumgehung. Erstellen Sie mithilfe der folgenden Verfahren Netzwerkstandorte gemäß denen in der Beispielnetzwerktopologie für CAC. Diese Verfahren zeigen die Erstellung und Konfiguration von Netzwerkstandorten, deren WAN-Bandbreite eingeschränkt ist und die daher Bandbreitenrichtlinien zur Begrenzung des in Echtzeit übertragenen Audio- und Videodatenverkehrs erfordern.

In der CAC-Beispielbereitstellung weist die Region "Nordamerika" sechs Standorte auf. An drei dieser Standorte ist die WAN-Bandbreite eingeschränkt: "Reno", "Portland" und "Albuquerque". Die WAN-Bandbreite der anderen drei Standorte ist *nicht* eingeschränkt: "New York", "Chicago" und "Detroit". Ein Beispiel für die Erstellung oder Änderung dieser Netzwerkstandorte finden Sie unter [Erstellen oder Ändern eines Netzwerkstandorts in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).

Die Beispielnetzwerktopologie finden Sie unter [Beispiel: Zusammenstellen der Anforderungen Ihrer Organisation für die Anrufsteuerung in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in der Planungsdokumentation.


> [!NOTE]
> Im folgenden Verfahren wird die Lync Server-Verwaltungsshell zum Erstellen eines Netzwerkstandorts verwendet. Ausführliche Informationen zur Verwendung der Lync Server-Systemsteuerung zum Erstellen eines Netzwerkstandorts finden Sie unter <A href="lync-server-2013-create-or-modify-a-network-site.md">Erstellen oder Ändern eines Netzwerkstandorts in Lync Server 2013</A>.



## So erstellen Sie einen Netzwerkstandort für die Anrufsteuerung

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet **New-CsNetworkSite** aus, um Netzwerkstandorte zu erstellen und ein geeignetes Bandbreitenrichtlinienprofil auf jeden Standort anzuwenden. Führen Sie beispielsweise den folgenden Befehl aus:
    
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link

       &nbsp;
    
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link

       &nbsp;
    
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link

3.  Zum Abschließen der Erstellung von Netzwerkstandorten für die gesamte Beispieltopologie wiederholen Sie Schritt 2 für die Netzwerkstandorte mit Bandbreiteneinschränkungen in den Regionen "EMEA" und "APAC".

