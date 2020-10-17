---
title: 'Lync Server 2013: Erstellen oder Ändern einer netzwerkregion'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network region
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412933(v=OCS.15)
ms:contentKeyID: 48185281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2ddd7a64da7d0939b7b97099cb12878c272766d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508852"
---
# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a>Erstellen oder Ändern einer netzwerkregion in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-19_

Bei einer *Netzwerkregion* handelt es sich um den Netzwerkhub oder Netzwerkbackbone, der in der Konfiguration von Anrufsteuerung, E9-1-1 und Medienumgehung verwendet wird. Verwenden Sie die folgenden Verfahren, um Netzwerkregionen zu erstellen oder zu ändern. Wenn Sie beispielsweise bereits Netzwerkregionen für eine VoIP-Funktion erstellt haben, müssen Sie keine neuen Netzwerkregionen erstellen, da dieselben Netzwerkregionen für weitere Enterprise VoIP-Funktionen verwendet werden können. Sie müssen jedoch möglicherweise eine vorhandene Definition einer Netzwerkregion ändern, um funktionsspezifische Einstellungen anzuwenden. Wenn Sie z. B. Netzwerkregionen für E9-1-1 erstellt haben (denen kein zentraler Standort zugeordnet werden muss) und Sie zu einem späteren Zeitpunkt die Anrufsteuerung bereitstellen, müssen Sie die Definitionen der Netzwerkregionen ändern und einen zentralen Standort angeben. Ausführliche Informationen finden Sie unter [configure Network Regions for CAC in lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).

<div>


> [!NOTE]  
> Funktionsspezifische Anforderungen für die Netzwerkregionendefinitionen sind in den Bereitstellungsthemen der jeweiligen Funktion dokumentiert.



</div>

Ausführliche Informationen zum Arbeiten mit netzwerkregionen finden Sie in der lync Server-Verwaltungsshell Dokumentation für die folgenden Cmdlets:

  - [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Gruppe-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a>Erstellen einer Netzwerkregion

Erstellen Sie eine Netzwerkregion, die für Anrufsteuerung, E9-1-1 oder Medienumgehung verwendet werden kann.

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a>So erstellen Sie eine netzwerkregion mithilfe von lync Server-Verwaltungsshell

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet "New-CsNetworkRegion" aus, um Netzwerkregionen zu erstellen:
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    Beispiel:
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    In diesem Beispiel wird eine Netzwerkregion "NorthAmerica" erstellt, die einem zentralen Standort mit der Standort-ID "CHICAGO" zugeordnet wird.

3.  Zum Abschließen der Erstellung von Netzwerkregionen für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Netzwerkregionen.

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a>So erstellen Sie eine netzwerkregion mithilfe von lync Server-Systemsteuerung

1.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3.  Klicken Sie auf **Region**.

4.  Klicken Sie auf **Neu**.

5.  Klicken Sie auf der Seite **Neue Region** auf **Name**, und geben Sie einen Namen für die Netzwerkregion ein.

6.  Klicken Sie auf **Zentraler Standort** und anschließend auf einen zentralen Standort in der Liste.

7.  Klicken Sie optional auf **Beschreibung**, und geben Sie zusätzliche Informationen zur Beschreibung dieses Netzwerkstandorts ein.

8.  Klicken Sie auf **Commit ausführen**.

9.  Zum Abschließen der Erstellung von Netzwerkregionen für Ihre Topologie wiederholen Sie die Schritte 4 bis 8 mit Einstellungen für weitere Regionen.

</div>

</div>

<div>

## <a name="modify-a-network-region"></a>Ändern einer Netzwerkregion

Ändern Sie die Einstellungen für eine vorhandenen Netzwerkregion in Übereinstimmung mit Änderungen der grundlegenden Regioneninformationen oder Änderungen, die für eine neue Funktion erforderlich sind.

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a>So ändern Sie eine netzwerkregion mithilfe von lync Server-Verwaltungsshell

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet "Set-CsNetworkRegion" aus, um eine vorhandene Netzwerkregion zu ändern:
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    Beispiel:
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    In diesem Beispiel wird die zuvor in diesem Thema erstellte Netzwerkregion "NorthAmerica" bearbeitet, indem die Beschreibung geändert wird. Wenn für die Region "NorthAmerica" bereits eine Beschreibung vorhanden ist, wird diese durch den neuen Wert ersetzt, andernfalls legt dieser Befehl die Beschreibung fest.

3.  Zum Ändern weiterer Netzwerkregionen wiederholen Sie Schritt 2 mit Einstellungen für andere Regionen.

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a>So ändern Sie eine netzwerkregion mithilfe von lync Server-Systemsteuerung

1.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3.  Klicken Sie auf die Navigationsschaltfläche **Region**.

4.  Klicken Sie in der Tabelle auf die Netzwerkregion, die Sie ändern möchten.

5.  Klicken Sie auf **Bearbeiten** und anschließend auf **Details einblenden**.

6.  Ändern Sie auf der Seite **Region bearbeiten** die Werte für die Einstellungen dieser Netzwerkregion wie gewünscht ab.

7.  Klicken Sie auf **Commit ausführen**.

8.  Zum Abschließen der Änderung von Netzwerkregionen wiederholen Sie die Schritte 4 bis 7 mit Einstellungen für weitere Regionen.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

