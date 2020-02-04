---
title: 'Lync Server 2013: Erstellen oder Ändern eines Netzwerkbereichs'
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
ms.openlocfilehash: 75011a28567da8a6e386c42f272ee1510b8ceddc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a>Erstellen oder Ändern eines Netzwerkbereichs in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

*Netzwerkregionen* sind die Netzwerkhubs oder Backbones, die in der Konfiguration der Anruf Zulassungs Steuerung, E9-1-1 und medienumgehung verwendet werden. Gehen Sie wie folgt vor, um netzwerkregionen zu erstellen oder zu ändern. Wenn Sie beispielsweise bereits netzwerkregionen für ein Sprachfeature erstellt haben, müssen Sie keine neuen netzwerkregionen erstellen. für andere erweiterte Enterprise-VoIP-Features werden dieselben netzwerkregionen verwendet. Sie müssen jedoch möglicherweise eine vorhandene Definition einer Netzwerkregion ändern, um funktionsspezifische Einstellungen anzuwenden. Wenn Sie z. B. Netzwerkregionen für E9-1-1 erstellt haben (denen kein zentraler Standort zugeordnet werden muss) und Sie zu einem späteren Zeitpunkt die Anrufsteuerung bereitstellen, müssen Sie die Definitionen der Netzwerkregionen ändern und einen zentralen Standort angeben. Ausführliche Informationen finden Sie unter [Konfigurieren von netzwerkregionen für CAC in lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).

<div>


> [!NOTE]  
> Alle funktionsspezifischen Anforderungen für Netzwerkbereichs Definitionen sind in den Bereitstellungsthemen für das Feature dokumentiert.



</div>

Details zum Arbeiten mit netzwerkregionen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:

  - [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a>Erstellen eines Netzwerkbereichs

Erstellen Sie einen Netzwerkbereich, der von der Anrufsteuerung, E9-1-1 oder Media Bypass verwendet werden kann.

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a>So erstellen Sie einen Netzwerkbereich mithilfe der lync Server-Verwaltungsshell

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet New-CsNetworkRegion aus, um Netzwerkregionen zu erstellen:
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    Beispiel:
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    In diesem Beispiel wird eine Netzwerkregion NorthAmerica erstellt, die einem zentralen Standort mit der Standort-ID CHICAGO zugeordnet wird.

3.  Zum Abschließen der Erstellung von Netzwerkregionen für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Netzwerkregionen.

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a>So erstellen Sie einen Netzwerkbereich mithilfe der lync Server-Systemsteuerung

1.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3.  Klicken Sie auf **Region**.

4.  Klicken Sie auf **Neu**.

5.  Klicken Sie auf der Seite **Neue Region** auf **Name** und geben Sie einen Namen für die Netzwerkregion ein.

6.  Klicken Sie auf **Zentraler Standort** und anschließend auf einen zentralen Standort in der Liste.

7.  Klicken Sie optional auf **Beschreibung** und geben Sie zusätzliche Informationen zur Beschreibung dieses Netzwerkstandorts ein.

8.  Klicken Sie auf **Commit ausführen**.

9.  Zum Abschließen der Erstellung von Netzwerkregionen für Ihre Topologie wiederholen Sie die Schritte 4 bis 8 mit Einstellungen für weitere Regionen.

</div>

</div>

<div>

## <a name="modify-a-network-region"></a>Ändern eines Netzwerkbereichs

Ändern Sie die Einstellungen für einen vorhandenen Netzwerkbereich, um Änderungen an den grundlegenden Bereichs Informationen oder Änderungen anzupassen, die für ein neues Feature erforderlich sind.

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a>So ändern Sie einen Netzwerkbereich mithilfe der lync Server-Verwaltungsshell

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet Set-CsNetworkRegion aus, um eine vorhandene Netzwerkregion zu ändern:
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    Beispiel:
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    In diesem Beispiel wird die zuvor in diesem Thema erstellte Netzwerkregion „NorthAmerica“ bearbeitet, indem die Beschreibung geändert wird. Wenn für die Region „NorthAmerica“ bereits eine Beschreibung vorhanden ist, wird diese durch den neuen Wert ersetzt, andernfalls legt dieser Befehl die Beschreibung fest.

3.  Zum Ändern weiterer Netzwerkregionen wiederholen Sie Schritt 2 mit Einstellungen für andere Regionen.

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a>So ändern Sie einen Netzwerkbereich mithilfe der lync Server-Systemsteuerung

1.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3.  Klicken Sie auf die Navigationsschaltfläche **Region**.

4.  Klicken Sie in der Tabelle auf die Netzwerkregion, die Sie ändern möchten.

5.  Klicken Sie auf **Bearbeiten** und anschließend auf **Details einblenden**.

6.  Ändern Sie auf der Seite **Region bearbeiten** die Werte für die Einstellungen dieser Netzwerkregion wie gewünscht ab.

7.  Klicken Sie auf **Commit ausführen**.

8.  Zum Abschließen der Änderung von Netzwerkregionen wiederholen Sie die Schritte 4 bis 7 mit Einstellungen für weitere Regionen.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

