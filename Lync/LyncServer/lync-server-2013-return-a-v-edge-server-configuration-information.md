---
title: Zurückgeben von Konfigurationsinformationen für den A/V-Edgeserver
TOCTitle: Zurückgeben von Konfigurationsinformationen für den A/V-Edgeserver
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49890889
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zurückgeben von Konfigurationsinformationen für den A/V-Edgeserver

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Der A/V-Edgeserverdienst bietet eine Möglichkeit für Ihre internen Benutzer (in Ihrem Organisationsnetzwerk angemeldete Benutzer), Audio- und Videodateien für externe Benutzer (nicht in Ihrem Organisationsnetzwerk angemeldete Benutzer) freizugeben. Der A/V-Edgeserverdienst wird primär durch die Verwendung von A/V-Edge-Konfigurationseinstellungen verwaltet; Einstellung, die über die Standort- oder die Dienstebene konfiguriert werden kann (d. h., sie kann für einen einzelnen A/V-Edgeserver konfiguriert werden).

Sie müssen die Communications Server-Verwaltungsshell und das Cmdlet Get-CsAVEdgeConfiguration verwenden, um Informationen über die in Ihrer Organisation verwendeten A/V-Edge-Konfigurationseinstellungen zurückzugeben. Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAVEdgeConfiguration).

Vom Cmdlet Get-CsAVEdgeConfiguration zurückgegebene Informationen sehen in etwa so aus:

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

## Zurückgeben von Informationen für alle Ihre A/V-Edge-Konfigurationseinstellungen

  - Der folgende Befehl gibt Informationen über alle derzeit in Ihrer Organisation verwendeten A/V-Edge-Konfigurationseinstellungen zurück:
    
        Get-CsAVEdgeConfiguration

## Zurückgeben von Informationen für A/V-Edge-Konfigurationseinstellungen auf Standortebene

  - Geben Sie zum Zurückgeben von Informationen über eine bestimmte Sammlung von A/V-Edge-Konfigurationseinstellungen die Identität der Sammlung an, wenn das Cmdlet Get-CsAVEdgeConfiguration ausgeführt wird. Beispielsweise gibt dieser Befehl nur Informationen für die Einstellungen zurück, die im Standort Redmond angewendet wurden:
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

## Zurückgeben von Informationen für A/V-Edge-Konfigurationseinstellungen auf Dienstebene

  - Und dieser Befehl gibt nur Informationen für Einstellungen zurück, die auf einem bestimmten A/V-Edgeserver angewendet wurden:
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

## Siehe auch

#### Aufgaben

[Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für A/V-Edgeserver](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[Löschen einer vorhandenen Auflistung von Konfigurationseinstellungen für A/V-Edgeserver](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  

#### Weitere Ressourcen

[A/V-Edgeserver in Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)

