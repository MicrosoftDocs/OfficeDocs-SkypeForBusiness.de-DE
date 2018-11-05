---
title: Erstellen von standortübergreifenden Netzwerkrichtlinien in Lync Server 2013
TOCTitle: Erstellen von standortübergreifenden Netzwerkrichtlinien in Lync Server 2013
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412844(v=OCS.15)
ms:contentKeyID: 49295111
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen von standortübergreifenden Netzwerkrichtlinien in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Eine *standortübergreifende Netzwerkrichtlinie* definiert Bandbreiteneinschränkungen zwischen Standorten, die über direkte WAN-Verbindungen miteinander verbunden sind.

Ausführliche Informationen finden Sie in der Lync Server-Verwaltungsshell-Dokumentation zu den folgenden Cmdlets:

  - [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkInterSitePolicy)


> [!IMPORTANT]
> Eine standortübergreifende Netzwerkrichtlinie ist <EM>nur</EM> erforderlich, wenn eine standortübergreifende Direktverbindung zwischen zwei Netzwerkstandorten besteht.



In der Region "Nordamerika" der Beispieltopologie besteht eine direkte Verbindung zwischen den Standorten "Reno" und "Albuquerque". Für diese beiden Standorte ist eine standortübergreifende Richtlinie erforderlich, die ein geeignetes Bandbreitenrichtlinienprofil anwendet. Im folgenden Beispiel wird das Profil "20Mb\_Link" angewendet.

## So erstellen Sie eine standortübergreifende Netzwerkrichtlinie

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet "New-CsNetworkInterSitePolicy" aus, um für zwei Standorte mit standortübergreifender Direktverbindung standortübergreifende Netzwerkrichtlinien zu erstellen und ein geeignetes Bandbreitenrichtlinienprofil anzuwenden. Führen Sie beispielsweise den folgenden Befehl aus:
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  Wiederholen Sie bei Bedarf Schritt 2, um standortübergreifende Netzwerkrichtlinien für alle Netzwerkstandorte mit standortübergreifender Direktverbindung zu erstellen.

