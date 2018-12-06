---
title: 'Lync Server 2013: Erstellen oder Ändern einer Netzwerkregion'
TOCTitle: Erstellen oder Ändern einer Netzwerkregion
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412933(v=OCS.15)
ms:contentKeyID: 49295266
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern einer Netzwerkregion in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Bei einer *Netzwerkregion* handelt es sich um den Netzwerkhub oder Netzwerkbackbone, der in der Konfiguration von Anrufsteuerung, E9-1-1 und Medienumgehung verwendet wird. Verwenden Sie die folgenden Verfahren, um Netzwerkregionen zu erstellen oder zu ändern. Wenn Sie beispielsweise bereits Netzwerkregionen für eine VoIP-Funktion erstellt haben, müssen Sie keine neuen Netzwerkregionen erstellen, da dieselben Netzwerkregionen für weitere Enterprise VoIP-Funktionen verwendet werden können. Sie müssen jedoch möglicherweise eine vorhandene Definition einer Netzwerkregion ändern, um funktionsspezifische Einstellungen anzuwenden. Wenn Sie z. B. Netzwerkregionen für E9-1-1 erstellt haben (denen kein zentraler Standort zugeordnet werden muss) und Sie zu einem späteren Zeitpunkt die Anrufsteuerung bereitstellen, müssen Sie die Definitionen der Netzwerkregionen ändern und einen zentralen Standort angeben. Ausführliche Informationen finden Sie unter [Konfigurieren von Netzwerkregionen für die Anrufsteuerung in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).


> [!NOTE]
> Funktionsspezifische Anforderungen für die Netzwerkregionendefinitionen sind in den Bereitstellungsthemen der jeweiligen Funktion dokumentiert.



Ausführliche Informationen zum Arbeiten mit Netzwerkregionen finden Sie in der Lync Server-Verwaltungsshell-Dokumentation für die folgenden Cmdlets:

  - [New-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkRegion)

  - [Get-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkRegion)

  - [Remove-CsNetworkRegion](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkRegion)

## Erstellen einer Netzwerkregion

Erstellen Sie eine Netzwerkregion, die für Anrufsteuerung, E9-1-1 oder Medienumgehung verwendet werden kann.

## So erstellen Sie eine Netzwerkregion mithilfe der Lync Server-Verwaltungsshell

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet "New-CsNetworkRegion" aus, um Netzwerkregionen zu erstellen:
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    Beispiel:
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    In diesem Beispiel wird eine Netzwerkregion "NorthAmerica" erstellt, die einem zentralen Standort mit der Standort-ID "CHICAGO" zugeordnet wird.

3.  Zum Abschließen der Erstellung von Netzwerkregionen für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Netzwerkregionen.

## So erstellen Sie eine Netzwerkregion mithilfe der Lync Server-Systemsteuerung

1.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** .

3.  Klicken Sie auf **Region** .

4.  Klicken Sie auf **Neu** .

5.  Klicken Sie auf der Seite **Neue Region** auf **Name** , und geben Sie einen Namen für die Netzwerkregion ein.

6.  Klicken Sie auf **Zentraler Standort** und anschließend auf einen zentralen Standort in der Liste.

7.  Klicken Sie optional auf **Beschreibung** , und geben Sie zusätzliche Informationen zur Beschreibung dieses Netzwerkstandorts ein.

8.  Klicken Sie auf **Commit** .

9.  Zum Abschließen der Erstellung von Netzwerkregionen für Ihre Topologie wiederholen Sie die Schritte 4 bis 8 mit Einstellungen für weitere Regionen.

## Ändern einer Netzwerkregion

Ändern Sie die Einstellungen für eine vorhandenen Netzwerkregion in Übereinstimmung mit Änderungen der grundlegenden Regioneninformationen oder Änderungen, die für eine neue Funktion erforderlich sind.

## So ändern Sie eine Netzwerkregion mithilfe der Lync Server-Verwaltungsshell

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet "Set-CsNetworkRegion" aus, um eine vorhandene Netzwerkregion zu ändern:
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    Beispiel:
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    In diesem Beispiel wird die zuvor in diesem Thema erstellte Netzwerkregion "NorthAmerica" bearbeitet, indem die Beschreibung geändert wird. Wenn für die Region "NorthAmerica" bereits eine Beschreibung vorhanden ist, wird diese durch den neuen Wert ersetzt, andernfalls legt dieser Befehl die Beschreibung fest.

3.  Zum Ändern weiterer Netzwerkregionen wiederholen Sie Schritt 2 mit Einstellungen für andere Regionen.

## So ändern Sie eine Netzwerkregion mithilfe der Lync Server-Systemsteuerung

1.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** .

3.  Klicken Sie auf die Navigationsschaltfläche **Region** .

4.  Klicken Sie in der Tabelle auf die Netzwerkregion, die Sie ändern möchten.

5.  Klicken Sie auf **Bearbeiten** und anschließend auf **Details einblenden** .

6.  Ändern Sie auf der Seite **Region bearbeiten** die Werte für die Einstellungen dieser Netzwerkregion wie gewünscht ab.

7.  Klicken Sie auf **Commit** .

8.  Zum Abschließen der Änderung von Netzwerkregionen wiederholen Sie die Schritte 4 bis 7 mit Einstellungen für weitere Regionen.

