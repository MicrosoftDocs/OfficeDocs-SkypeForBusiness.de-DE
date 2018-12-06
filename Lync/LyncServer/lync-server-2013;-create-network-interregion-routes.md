---
title: Erstellen von regionenübergreifenden Netzwerkrouten in Lync Server 2013
TOCTitle: Erstellen von regionenübergreifenden Netzwerkrouten in Lync Server 2013
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398368(v=OCS.15)
ms:contentKeyID: 49294040
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen von regionenübergreifenden Netzwerkrouten in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-20_

Eine *regionenübergreifende Netzwerkroute* definiert die Route zwischen zwei Netzwerkregionen. Für jedes Netzwerkregionenpaar in Ihrer Anrufsteuerungsbereitstellung ist eine regionenübergreifende Netzwerkroute erforderlich. So kann jede Netzwerkregion innerhalb der Bereitstellung auf alle anderen Regionen zugreifen.

Während die Regionenverbindungen Bandbreiteneinschränkungen für Verbindungen zwischen Regionen festlegen, bestimmt eine regionenübergreifende Route, welchen Verknüpfungspfad die Verbindung von einer Region zur anderen nimmt.

Ausführliche Informationen zum Arbeiten mit regionenübergreifenden Netzwerkrouten finden Sie in der Lync Server-Verwaltungsshell-Dokumentation für die folgenden Cmdlets:

  - [New-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

In der Beispieltopologie müssen für jedes der drei Regionenpaare regionenübergreifende Netzwerkrouten definiert werden: "North America/EMEA", "EMEA/APAC" und "North America/APAC".

## So erstellen Sie regionenübergreifende Netzwerkrouten mithilfe der Lync Server-Verwaltungsshell

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet **New-CsNetworkInterRegionRoute** aus, um die erforderlichen Routen zu definieren. Führen Sie beispielsweise den folgenden Befehl aus:
    
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"

       &nbsp;
    
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"

       &nbsp;
    
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
    

    > [!NOTE]
    > Für die regionenübergreifende Netzwerkroute "North America/APAC" werden zwei Netzwerkregionenverbindungen benötigt, da zwischen diesen beiden Regionen keine direkte Netzwerkregionenverbindung vorhanden ist.



## So erstellen Sie regionenübergreifende Netzwerkrouten mithilfe der Lync Server-Systemsteuerung

1.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3.  Klicken Sie auf die Navigationsschaltfläche **Regionenroute**.

4.  Klicken Sie auf **Neu**.

5.  Klicken Sie auf der Seite **Neue Regionenroute** auf **Name**, und geben Sie einen Namen für die regionenübergreifende Netzwerkroute ein.

6.  Klicken Sie auf **Netzwerkregion 1** und anschließend auf eine Netzwerkregion in der Liste, für die eine Route zu Netzwerkregion 2 erstellt werden soll.

7.  Klicken Sie auf **Netzwerkregion 2** und anschließend auf eine Netzwerkregion in der Liste, für die eine Route zu Netzwerkregion 1 erstellt werden soll.

8.  Klicken Sie neben dem Feld **Netzwerkregionenverbindungen** auf **Hinzufügen**, und fügen Sie eine Netzwerkregionenverbindung hinzu, die in der regionenübergreifenden Netzwerkroute verwendet werden soll.
    

    > [!NOTE]
    > Wenn Sie eine Route für zwei Netzwerkregionen erstellen, die nicht über eine direkte Netzwerkregionenverbindung verbunden sind, müssen alle erforderlichen Verbindungen zum Vervollständigen der Route hinzugefügt werden. Für die regionenübergreifende Netzwerkroute "North America/APAC" werden beispielsweise zwei Netzwerkregionenverbindungen benötigt, da zwischen diesen beiden Regionen keine direkte Netzwerkregionenverbindung vorhanden ist.



9.  Klicken Sie auf **Commit**.

10. Wiederholen Sie die Schritte 4 bis 9 mit Einstellungen für andere regionenübergreifende Netzwerkrouten, um die Erstellung von regionenübergreifenden Netzwerkrouten für Ihre Topologie abzuschließen.

