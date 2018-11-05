---
title: 'Lync Server 2013: Erstellen oder Ändern eines Netzwerkstandorts'
TOCTitle: Erstellen oder Ändern eines Netzwerkstandorts
ms:assetid: 14e24856-9996-4da4-9f31-300940bdf5aa
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398218(v=OCS.15)
ms:contentKeyID: 49293267
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern eines Netzwerkstandorts in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-24_

Bereitstellungen mit Anrufsteuerung (Call Admission Control, CAC), E9-1-1 und Medienumgehung stützen sich auf die Konfiguration von *Netzwerkstandorten* , die innerhalb einer Netzwerkregion definiert und stets einer Netzwerkregion zugeordnet sind. Ein Netzwerkstandort repräsentiert einen Zweigstellenstandort, einen Gebäudekomplex oder ein Gelände. Netzwerkstandorte repräsentieren Sammlungen aus Subnetzen mit ähnlicher Bandbreite.

Verwenden Sie die folgenden Verfahren, um Netzwerkstandorte zu erstellen oder zu ändern. Wenn Sie beispielsweise bereits Netzwerkstandorte für eine VoIP-Funktion erstellt haben, müssen Sie keine neuen Netzwerkstandorte erstellen, da dieselben Netzwerkstandorte für weitere VoIP-Funktionen verwendet werden können. Sie müssen jedoch möglicherweise eine vorhandene Netzwerkstandortdefinition ändern, um funktionsspezifische Einstellungen anzuwenden. Wenn Sie beispielsweise einen Netzwerkstandort für E9-1-1 erstellt haben, müssen Sie den Netzwerkstandort während der Bereitstellung der Anrufsteuerung ändern, um ein Bandbreitenrichtlinienprofil anzuwenden.


> [!NOTE]
> Spezifische Beispiele und Anforderungen für Netzwerkstandorte finden Sie ggf. in den Themen zu erweiterten VoIP-Funktionen in der Bereitstellungsdokumentation: 
> <UL>
> <LI>
> <P><A href="lync-server-2013-configure-network-sites-for-cac.md">Konfigurieren von Netzwerkstandorten für die Anrufsteuerung in Lync Server 2013</A></P></LI></UL>



Ausführliche Informationen zum Arbeiten mit Netzwerkstandorten finden Sie in der Lync Server-Verwaltungsshell-Dokumentation für die folgenden Cmdlets:

  - [New-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkSite)

  - [Get-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkSite)

  - [Set-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkSite)

  - [Remove-CsNetworkSite](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkSite)

## Erstellen eines Netzwerkstandorts

Erstellen Sie eine Netzwerkregion, die für Anrufsteuerung, E9-1-1 oder Medienumgehung verwendet werden kann.

## So erstellen Sie einen Netzwerkstandort mithilfe der Verwaltungsshell

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet "New-CsNetworkSite" aus, um Netzwerkstandorte zu erstellen:
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    Beispiel
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    In diesem Beispiel wird ein Netzwerkstandort namens "Chicago" erstellt, der sich in der Netzwerkregion "NorthAmerica" befindet.
    

    > [!NOTE]
    > Die Netzwerkregion "NorthAmerica" muss bereits vorhanden sein, damit dieser Befehl erfolgreich ausgeführt werden kann.



3.  Zum Abschließen der Erstellung von Netzwerkstandorten für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Standorte.

## So erstellen Sie einen Netzwerkstandort mithilfe der Lync Server-Systemsteuerung

1.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** .

3.  Klicken Sie auf die Navigationsschaltfläche **Standort** .

4.  Klicken Sie auf **Neu** .

5.  Klicken Sie auf der Seite **Neuer Standort** auf **Name** , und geben Sie einen Namen für den Netzwerkstandort ein.

6.  Klicken Sie auf **Region** , und klicken Sie dann auf eine Region in der Liste.

7.  Klicken Sie optional auf **Bandbreitenrichtlinie** , und klicken Sie dann auf eine Bandbreitenrichtlinie in der Liste.
    

    > [!NOTE]
    > Eine Bandbreitenrichtlinie ist nur dann erforderlich, wenn Sie die Anrufsteuerung am Standort bereitstellen möchten.



8.  Klicken Sie optional auf **Ortungsrichtlinie** , und klicken Sie dann auf eine Ortungsrichtlinie in der Liste.
    

    > [!NOTE]
    > Eine Ortungsrichtlinie ist nur erforderlich, wenn Sie E9-1-1 am Standort bereitstellen.



9.  Klicken Sie optional auf **Beschreibung** , und geben Sie zusätzliche Informationen zur Beschreibung dieses Netzwerkstandorts ein.

10. Klicken Sie auf **Commit** .

11. Zum Abschließen der Erstellung von Netzwerkstandorten für Ihre Topologie wiederholen Sie die Schritte 4 bis 10 mit Einstellungen für weitere Standorte.

## Ändern eines Netzwerkstandorts

Ändern Sie eine Netzwerkregion, die für Anrufsteuerung, E9-1-1 oder Medienumgehung verwendet werden kann.

## So ändern Sie einen Netzwerkstandort

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet "Set-CsNetworkSite" aus, um Netzwerkstandorte zu ändern:
    
        Set-CsNetworkSite -Identity <string>
    
    Beispiel:
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    In diesem Beispiel wird der Standort "Albuquerque" in die Netzwerkregion "NorthAmerica" verschoben. Bearbeiten Sie zum Ändern der Netzwerkstandortkonfiguration für die Bereitstellung von Anrufsteuerung, E9-1-1 oder Medienumgehung die Netzwerkstandorteinstellungen, indem Sie das Cmdlet "Set-CsNetworkSite" mit dem Parameter "BWPolicyProfileID" oder "LocationPolicy" ausführen.
    

    > [!NOTE]
    > Wenngleich der Parameter "BypassID" für die Medienumgehung vorhanden ist, wird dringend empfohlen, automatisch generierte IDs für die Umgehung nicht außer Kraft zu setzen. Sie müssen keine zusätzlichen Parameter angeben, um einen Netzwerkstandort für die Medienumgehung zu konfigurieren.



3.  Zum Abschließen der Änderung von Netzwerkstandorten für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Standorte.

## So ändern Sie einen Netzwerkstandort mithilfe der Lync Server-Systemsteuerung

1.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** .

3.  Klicken Sie auf die Navigationsschaltfläche **Standort** .

4.  Klicken Sie in der Tabelle auf den Netzwerkstandort, den Sie ändern möchten.

5.  Klicken Sie auf **Bearbeiten** und anschließend auf **Details einblenden...** .

6.  Ändern Sie auf der Seite **Standort bearbeiten** die Werte für die Einstellungen dieses Netzwerkstandorts wie gewünscht ab.

7.  Klicken Sie auf **Commit** .

8.  Zum Abschließen der Änderung von Netzwerkstandorten wiederholen Sie die Schritte 4 bis 7 mit Einstellungen für weitere Standorte.

