---
title: Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für A/V-Edgeserver
TOCTitle: Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für A/V-Edgeserver
ms:assetid: 43899518-59c6-4be4-8892-d6f6207bfaab
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688039(v=OCS.15)
ms:contentKeyID: 49890725
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für A/V-Edgeserver

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Mit A/V-Edgeservern können interne Benutzer (Benutzer, die bei Ihrem internen Netzwerk angemeldet sind) Audio- und Videoinhalte für externe Benutzer (d. h. Benutzer, die nicht beim Netzwerk Ihrer Organisation angemeldet sind) freigeben. Der A/V-Edgedienst wird hauptsächlich mithilfe der Konfigurationseinstellungen für A/V-Edgeserver verwaltet, die auf Standort- oder Dienstebene (d. h. für einen einzelnen A/V-Edgeserver) konfiguriert werden können.

Während der Installation von Lync Server wird eine globale Auflistung von Konfigurationseinstellungen für A/V-Edgeserver erstellt. Zusätzlich dazu können Sie mit den Cmdlets Lync Server-Verwaltungsshell und New-CsAVEdgeConfiguration neue Einstellungen auf Standort- oder Dienstebene erstellen (d. h. für einen einzelnen A/V-Edgeserver). Beachten Sie bei der Erstellung neuer Einstellungen Folgendes:

  - Auf Dienstebene (d. h. auf einem einzelnen Server) konfigurierte Einstellungen haben Vorrang vor allen anderen.

  - Einstellungen auf Standortebene haben Vorrang vor globalen Einstellungen, werden jedoch von Einstellungen auf Dienstebene ersetzt.

  - Einstellungen auf globaler Ebene werden nur verwendet, wenn keine Diensteinstellungen auf dem einzelnen Server konfiguriert wurden und keine Standorteinstellungen für den Standort, an dem sich der Server befindet, vorhanden sind.

Anschließend können all Ihre Einstellungen mit dem Cmdlet Set-CsAVEdgeConfiguration bearbeitet werden. Weitere Informationen finden Sie in den Hilfethemen zu den Cmdlets [New-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAVEdgeConfiguration) und [Set-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsAVEdgeConfiguration).

## Erstellen neuer Konfigurationseinstellungen für A/V-Edgeserver auf Standortebene

  - Der folgende Befehl erstellt eine neue Auflistung von Konfigurationseinstellungen für A/V-Edgeserver für den Standort "Redmond".
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond"

## Erstellen benutzerdefinierter Konfigurationseinstellungen für A/V-Edgeserver auf Standortebene

  - Da keine weiteren Parameter vorhanden sind, verwenden diese neuen Einstellungen die Standardwerte für den A/V-Edgedienst. Alternativ können Sie zusätzliche Parameter und Parameterwerte verwenden, um eine benutzerdefinierte Auflistung zu erstellen. Der folgende Befehl legt beispielsweise die Eigenschaft "MaxTokenLifetime" auf vier Stunden (04 Stunden : 00 Minuten : 00 Sekunden) fest:
    
        New-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "04:00:00"

## Erstellen benutzerdefinierter Konfigurationseinstellungen für A/V-Edgeserver auf Dienstebene

  - Dieser Befehl erstellt eine ähnliche Auflistung, die auf den A/V-Edgeserver "atl-edge-001.litwareinc.com" angewendet wird:
    
        New-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -MaxTokenLifetime "04:00:00"

## Bearbeiten bestehender Konfigurationseinstellungen für A/V-Edgeserver

  - In diesem Beispiel wird das Cmdlet Set-CsAVEdgeConfiguration verwendet, um die maximale Gültigkeitsdauer von Token für den Standort Redmond auf zwölf Stunden festzulegen:
    
        Set-CsAVEdgeConfiguration -Identity "site:Redmond" -MaxTokenLifetime "12:00:00"

## Siehe auch

#### Aufgaben

[Zurückgeben von Konfigurationsinformationen für den A/V-Edgeserver](lync-server-2013-return-a-v-edge-server-configuration-information.md)  
[Löschen einer vorhandenen Auflistung von Konfigurationseinstellungen für A/V-Edgeserver](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  

#### Weitere Ressourcen

[A/V-Edgeserver in Lync Server 2013](lync-server-2013-audio-video-a-v-edge-servers.md)  
[New-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsAVEdgeConfiguration)  
[Set-CsAVEdgeConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsAVEdgeConfiguration)

