---
title: Konfigurieren von Netzwerkregionen für die Anrufsteuerung in Lync Server 2013
TOCTitle: Konfigurieren von Netzwerkregionen für die Anrufsteuerung in Lync Server 2013
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg399051(v=OCS.15)
ms:contentKeyID: 49295781
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Netzwerkregionen für die Anrufsteuerung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_


> [!IMPORTANT]
> Wenn Sie bereits Netzwerkregionen für E9-1-1 oder die Medienumgehung erstellt haben, können Sie diesen Netzwerkregionen mithilfe des <STRONG>Set-CsNetworkRegion</STRONG>-Cmdlets Einstellungen für die Anrufsteuerung (Call Admission Control, CAC) hinzufügen. Ein Beispiel für das Ändern einer Netzwerkregion finden Sie unter <A href="lync-server-2013-create-or-modify-a-network-region.md">Erstellen oder Ändern einer Netzwerkregion in Lync Server 2013</A>.



Bei einer *Netzwerkregion* handelt es sich um den Netzwerkhub oder Netzwerkbackbone, der in der Konfiguration von Anrufsteuerung, E9-1-1 und Medienumgehung verwendet wird. Erstellen Sie mithilfe des folgenden Verfahrens Netzwerkregionen gemäß denen in der Beispielnetzwerktopologie für die Anrufsteuerung. Die Beispielnetzwerktopologie finden Sie unter [Beispiel: Zusammenstellen der Anforderungen Ihrer Organisation für die Anrufsteuerung in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in der Planungsdokumentation.

Die Beispielnetzwerktopologie für die Anrufsteuerung umfasst drei Regionen: Nordamerika, EMEA und APAC. Jede Region verfügt über einen eigenen zentralen Standort. Der Name des zentralen Standorts in der Region "North America" lautet CHICAGO. Das folgende Beispiel zeigt, wie Sie die Region "North America" mithilfe des **New-CsNetworkRegion**-Cmdlets erstellen können.


> [!NOTE]
> Im folgenden Verfahren wird die Lync Server-Verwaltungsshell zum Erstellen einer Netzwerkregion verwendet. Ausführliche Informationen zum Verwenden der Lync Server-Systemsteuerung zum Erstellen einer Netzwerkregion finden Sie unter <A href="lync-server-2013-create-or-modify-a-network-region.md">Erstellen oder Ändern einer Netzwerkregion in Lync Server 2013</A>.



## So erstellen Sie eine Netzwerkregion für die Anrufsteuerung

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie für jede Region, die Sie erstellen möchten, das **New-CsNetworkRegion**-Cmdlet aus. Zum Erstellen der Region "North America" führen Sie beispielsweise den folgenden Befehl aus:
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  Wiederholen Sie Schritt 2, um die Netzwerkregionen "EMEA" und "APAC" zu erstellen.

