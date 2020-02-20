---
title: Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für Geräte Updates
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Device Update configuration settings
ms:assetid: 3e8ce95f-a8c8-417c-b1f7-0f759a567aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994029(v=OCS.15)
ms:contentKeyID: 51803938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 125b8c1f0db938d8870bc1eb5dca67554fffa16a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a>Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für Geräte Updates in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Konfigurationseinstellungen für Geräte Updates können (nur auf Standortebene) mithilfe von Windows PowerShell und dem Cmdlet **New-CsDeviceUpdateConfiguration** erstellt und mithilfe des Cmdlets " **CsDeviceUpdateConfiguration** " geändert werden. Diese Cmdlets können entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.

<div>


> [!NOTE]
> Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>mithilfe von Remote-PowerShell" unter.



</div>

<div>


<div>

## <a name="to-create-device-update-configuration-settings-that-use-the-default-values"></a>So erstellen Sie Konfigurationseinstellungen für Geräte Updates, die die Standardwerte verwenden

  - Mit diesem Befehl wird eine neue Gruppe von Konfigurationseinstellungen für das Geräteupdate für den Standort "Redmond" erstellt:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    Da im vorherigen Befehl keine anderen Parameter als der obligatorische Identity-Parameter angegeben wurden, werden in der neuen Auflistung von Konfigurationseinstellungen die Standardwerte für alle Eigenschaften verwendet.

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-device-update-configuration-settings"></a>So ändern Sie einen einzelnen Eigenschaftswert beim Erstellen von Geräte Aktualisierungs Konfigurationseinstellungen

  - Zum Erstellen von Einstellungen, die verschiedene Eigenschaftswerte verwenden, geben Sie einfach den entsprechenden Parameter und den Parameterwert an. Um beispielsweise eine Sammlung von Konfigurationseinstellungen für Geräte Updates zu erstellen, die standardmäßig alle 21 Tage alte Protokolldateien löschen, verwenden Sie einen Befehl wie den folgenden:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-device-update-configuration-settings"></a>So ändern Sie beim Erstellen von Geräte Aktualisierungs Konfigurationseinstellungen mehrere Eigenschaftswerte

  - Mehrere Eigenschaftswerte können durch die Angabe mehrerer Parameter geändert werden. Mit dem folgenden Befehl wird beispielsweise das Intervall für die Protokoll Bereinigung auf 21 Tage und das Protokoll leer Intervall auf 30 Minuten festgelegt:
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

</div>

Ausführliche Informationen zum Ändern vorhandener Geräte Konfigurationseinstellungen finden Sie im Hilfethema für das Cmdlet " [Sets-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15)) ". Ausführliche Informationen zum Erstellen von Auflistungen von Konfigurationseinstellungen finden Sie im Hilfethema für das [New-CsDeviceUpdateConfiguration-](https://technet.microsoft.com/library/Gg425761(v=OCS.15)) Cmdlet.

</div>

</div>

<span> </span>

</div>

</div>

</div>

