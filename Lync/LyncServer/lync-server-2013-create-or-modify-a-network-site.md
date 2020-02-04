---
title: 'Lync Server 2013: Erstellen oder Ändern eines Netzwerkstandorts'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network site
ms:assetid: 14e24856-9996-4da4-9f31-300940bdf5aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398218(v=OCS.15)
ms:contentKeyID: 48183488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed721a48b12a497b25d58e7ebb65ff3a91980904
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-site-in-lync-server-2013"></a>Erstellen oder Ändern eines Netzwerkstandorts in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-24_

Die Bereitstellung von Anrufannahme Steuerung (CAC), E9-1-1 und medienumgehung basiert auf der Konfiguration von *Netzwerk Websites* , die in einer netzwerkregion definiert sind und immer mit dieser verbunden sind. Eine Netzwerk Website steht für einen Zweigstellenstandort, einen Satz von Gebäuden oder einen Campus. Netzwerk Websites stellen Auflistungen von Subnetzen mit ähnlicher Bandbreite dar.

Gehen Sie wie folgt vor, um Netzwerk Websites zu erstellen oder zu ändern. Wenn Sie beispielsweise bereits Netzwerk Websites für eine Sprachfunktion erstellt haben, müssen Sie keine neuen Netzwerk Websites erstellen. für andere Sprachfeatures werden dieselben Websites verwendet. Sie müssen jedoch möglicherweise eine vorhandene Definition eines Netzwerkstandorts ändern, um funktionsspezifische Einstellungen anzuwenden. Wenn Sie z. B. einen Netzwerkstandort für E9-1-1 erstellt haben, müssen Sie den Netzwerkstandort während der Bereitstellung der Anrufsteuerung ändern, um ein Bandbreitenrichtlinienprofil anzuwenden.

<div>


> [!NOTE]  
> Wo Sie vorhanden sind, finden Sie spezifische Beispiele und Anforderungen für Netzwerk Websites in Bezug auf eine erweiterte Sprachfunktion in der Bereitstellungsdokumentation für die einzelnen Features: 
> <UL>
> <LI>
> <P><A href="lync-server-2013-configure-network-sites-for-cac.md">Konfigurieren von Netzwerk Websites für CAC in lync Server 2013</A></P></LI></UL>



</div>

Details zum Arbeiten mit Netzwerk Websites finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:

  - [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

  - [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)

  - [Set-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

  - [Remove-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)

<div>

## <a name="create-a-network-site"></a>Erstellen einer Netzwerk Website

Erstellen Sie einen Netzwerkbereich, der von der Anrufsteuerung, E9-1-1 oder Media Bypass verwendet werden kann.

<div>

## <a name="to-create-a-network-site-by-using-management-shell"></a>So erstellen Sie eine Netzwerk Website mithilfe der Verwaltungsshell

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet New-CsNetworkSite aus, um Netzwerkstandorte zu erstellen:
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    Beispiel:
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    In diesem Beispiel wird ein Netzwerkstandort namens „Chicago“ erstellt, der sich in der Netzwerkregion „NorthAmerica“ befindet.
    
    <div>
    

    > [!NOTE]  
    > Die Netzwerkregion „NorthAmerica“ muss bereits vorhanden sein, damit dieser Befehl erfolgreich ausgeführt werden kann.

    
    </div>

3.  Zum Abschließen der Erstellung von Netzwerkstandorten für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Standorte.

</div>

<div>

## <a name="to-create-a-network-site-by-using-lync-server-control-panel"></a>So erstellen Sie eine Netzwerk Website mithilfe der lync Server-Systemsteuerung

1.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3.  Klicken Sie auf die Navigationsschaltfläche **Standort**.

4.  Klicken Sie auf **Neu**.

5.  Klicken Sie auf der Seite **Neuer Standort** auf **Name** und geben Sie einen Namen für den Netzwerkstandort ein.

6.  Klicken Sie auf **Region** und klicken Sie dann auf eine Region in der Liste.

7.  Klicken Sie optional auf **Bandbreitenrichtlinie** und klicken Sie dann auf eine Bandbreitenrichtlinie in der Liste.
    
    <div>
    

    > [!NOTE]  
    > Eine Bandbreitenrichtlinie ist nur dann erforderlich, wenn Sie die Anrufsteuerung am Standort bereitstellen möchten.

    
    </div>

8.  Klicken Sie optional auf **Ortungsrichtlinie** und klicken Sie dann auf eine Ortungsrichtlinie in der Liste.
    
    <div>
    

    > [!NOTE]  
    > Eine Ortungsrichtlinie ist nur erforderlich, wenn Sie E9-1-1 am Standort bereitstellen.

    
    </div>

9.  Klicken Sie optional auf **Beschreibung** und geben Sie zusätzliche Informationen zur Beschreibung dieses Netzwerkstandorts ein.

10. Klicken Sie auf **Commit ausführen**.

11. Zum Abschließen der Erstellung von Netzwerkstandorten für Ihre Topologie wiederholen Sie die Schritte 4 bis 10 mit Einstellungen für weitere Standorte.

</div>

</div>

<div>

## <a name="modify-a-network-site"></a>Ändern einer Netzwerk Website

Sie können einen Netzwerkbereich ändern, der von der Anrufannahme Steuerung, E9-1-1 oder Media Bypass verwendet werden kann.

<div>

## <a name="to-modify-a-network-site"></a>So ändern Sie eine Netzwerk Website

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet Set-CsNetworkSite aus, um Netzwerkstandorte zu ändern:
    
        Set-CsNetworkSite -Identity <string>
    
    Beispiel:
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    In diesem Beispiel wird der Standort „Albuquerque“ in die Netzwerkregion „NorthAmerica“ verschoben. Bearbeiten Sie zum Ändern der Netzwerkstandortkonfiguration für die Bereitstellung von Anrufsteuerung, E9-1-1 oder Medienumgehung die Netzwerkstandorteinstellungen, indem Sie das Cmdlet Set-CsNetworkSite mit dem Parameter BWPolicyProfileID oder LocationPolicy ausführen.
    
    <div>
    

    > [!NOTE]  
    > Wenngleich der Parameter BypassID für die Medienumgehung vorhanden ist, wird dringend empfohlen, automatisch generierte IDs für die Umgehung nicht außer Kraft zu setzen. Sie müssen keine zusätzlichen Parameter angeben, um einen Netzwerkstandort für die Medienumgehung zu konfigurieren.

    
    </div>

3.  Zum Abschließen der Änderung von Netzwerkstandorten für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Standorte.

</div>

<div>

## <a name="to-modify-a-network-site-by-using-lync-server-control-panel"></a>So ändern Sie eine Netzwerk Website mithilfe der lync Server-Systemsteuerung

1.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3.  Klicken Sie auf die Navigationsschaltfläche **Standort**.

4.  Klicken Sie in der Tabelle auf den Netzwerkstandort, den Sie ändern möchten.

5.  Klicken Sie auf **Bearbeiten** und anschließend auf **Details einblenden**.

6.  Ändern Sie auf der Seite **Standort bearbeiten** die Werte für die Einstellungen dieses Netzwerkstandorts wie gewünscht ab.

7.  Klicken Sie auf **Commit ausführen**.

8.  Zum Abschließen der Änderung von Netzwerkstandorten wiederholen Sie die Schritte 4 bis 7 mit Einstellungen für weitere Standorte.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

