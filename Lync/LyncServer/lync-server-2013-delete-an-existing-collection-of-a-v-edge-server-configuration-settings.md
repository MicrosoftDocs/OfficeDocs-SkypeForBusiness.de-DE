---
title: Löschen einer vorhandenen Auflistung von Konfigurationseinstellungen für A/V-Edgeserver
TOCTitle: Löschen einer vorhandenen Auflistung von Konfigurationseinstellungen für A/V-Edgeserver
ms:assetid: 668d3613-e464-4b68-967a-cfff90b9ce4b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688077(v=OCS.15)
ms:contentKeyID: 49890772
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Löschen einer vorhandenen Auflistung von Konfigurationseinstellungen für A/V-Edgeserver

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Der A/V-Edgedienst ermöglicht es Ihren internen Benutzern (d. h. Benutzern, die in Ihren Unternehmensnetzwerk angemeldet sind), Audio- und Videoinhalte für externe Benutzer (d. h. Benutzer, die nicht in Ihren Unternehmensnetzwerk angemeldet sind) freizugeben. Der A/V-Edgedienst wird hauptsächlich über A/V-Edge-Konfigurationseinstellungen verwaltet, die auf Standort- oder Dienstebene (d. h. für einen bestimmten A/V-Edgeserver) konfiguriert werden können.

Bei der Installation von Lync Server wird eine globale Auflistung von A/V-Edge-Konfigurationseinstellungen erstellt, die nicht gelöscht werden kann. Sie können jedoch die Lync Server-Verwaltungsshell und das Remove-CsAVEdgeConfiguration-Cmdlet verwenden, um die globale Auflistung "zurückzusetzen", was bedeutet, dass die Werte aller Eigenschaften aus der globalen Auflistung einfach auf ihre Standardwerte zurückgesetzt werden. Wenn Sie zum Beispiel die Eigenschaft "MaxTokenLifetime" auf 16 Stunden festgelegt haben, wird diese Eigenschaft auf ihren Standardwert von 8 Stunden zurückgesetzt.

Ihre auf Standort- oder Dienstebene erstellten benutzerdefinierten Einstellungsauflistungen können Sie jedoch mit dem Remove-CsAVEdgeConfiguration-Cmdlet löschen. Wenn Sie Standorteinstellungen löschen, werden die an diesem Standort befindlichen A/V-Edgeserver anhand der globalen Einstellungen verwaltet. Wenn Sie auf Dienstebene festgelegte Einstellungen löschen, wird der Server dann gemäß den Einstellungen für seinen Standort oder (wenn diese nicht vorhanden sind) anhand der globalen Einstellungen verwaltet.

Weitere Informationen dazu finden Sie im Hilfethema für das [Remove-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsAVEdgeConfiguration)-Cmdlet.

## Zurücksetzen der globalen Auflistung

  - Mit dem folgenden Befehl wird die globale Auflistung von A/V-Edge-Konfigurationseinstellungen zurückgesetzt:
    
        Remove-CsAVEdgeConfiguration -Identity "global"

## Entfernen einer Auflistung auf Standortebene

  - Mit diesem Befehl werden die A/V-Edge-Konfigurationseinstellungen entfernt, die für den Standort "Redmond" gelten:
    
        Remove-CsAVEdgeConfiguration -Identity "site:Redmond"

## Entfernen einer Auflistung auf Dienstebene

  - Mit diesem Befehl werden die Einstellungen entfernt, die für den A/V-Edgeserver "atl-edge-001.litwareinc.com" gelten:
    
        Remove-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

## Siehe auch

#### Aufgaben

[Zurückgeben von Konfigurationsinformationen für den A/V-Edgeserver](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für A/V-Edgeserver](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  

#### Weitere Ressourcen

[A/V-Edgeserver in Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[Remove-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsAVEdgeConfiguration)

