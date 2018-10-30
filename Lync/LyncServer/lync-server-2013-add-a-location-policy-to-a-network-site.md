---
title: Hinzufügen einer Ortungsrichtlinie zu einem Netzwerkstandort in Lync Server 2013
TOCTitle: Hinzufügen einer Ortungsrichtlinie zu einem Netzwerkstandort in Lync Server 2013
ms:assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425936(v=OCS.15)
ms:contentKeyID: 49293838
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Hinzufügen einer Ortungsrichtlinie zu einem Netzwerkstandort in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-24_

Das folgende Beispiel zeigt, wie Sie die im Abschnitt [Erstellen von Ortungsrichtlinien in Lync Server 2013](lync-server-2013-create-location-policies.md) definierte Ortungsrichtlinie **Redmond** einem vorhandenen Netzwerkstandort hinzufügen, und wie Sie einen neuen Netzwerkstandort erstellen, der die Ortungsrichtlinie **Redmond** verwendet.

Ausführliche Informationen zum Arbeiten mit Netzwerkstandorten finden Sie in der Lync Server-Verwaltungsshell-Dokumentation für die folgenden Cmdlets:

  - **New-CsNetworkSite**

  - **Get-CsNetworkSite**

  - **Set-CsNetworkSite**

  - **Remove-CsNetworkSite**

## So weisen Sie eine Ortungsrichtlinie einem vorhandenen Netzwerkstandort zu

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie die folgenden Cmdlets aus, um einen vorhandenen Netzwerkstandort zu ändern.
    
    Weisen Sie die Ortungsrichtlinie mit dem Tag **Redmond** einem vorhandenen Netzwerkstandort namens **Redmond** zu.
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

## So weisen Sie eine Ortungsrichtlinie einem neuen Netzwerkstandort zu

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie das folgende Cmdlet aus, um einen neuen Netzwerkstandort zu erstellen.
    
    Erstellen Sie einen neuen Netzwerkstandort in der Netzwerkregion, und weisen Sie diesem Standort die Ortungsrichtlinie mit dem Tag **Redmond** zu.
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

