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
ms.openlocfilehash: 11ad625834682e8d5d6a820c999a14a19e79b863
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-site-in-lync-server-2013"></a>Erstellen oder Ändern eines Netzwerkstandorts in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-24_

Bereitstellungen mit Anrufsteuerung (Call Admission Control, CAC), E9-1-1 und Medienumgehung stützen sich auf die Konfiguration von *Netzwerkstandorten*, die innerhalb einer Netzwerkregion definiert und stets einer Netzwerkregion zugeordnet sind. Ein Netzwerkstandort stellt einen Zweigstellenstandort, einen Gebäudekomplex oder einen Campus dar. Netzwerkstandorte repräsentieren Sammlungen aus Subnetzen mit ähnlicher Bandbreite.

Verwenden Sie die folgenden Verfahren, um Netzwerkstandorte zu erstellen oder zu ändern. Wenn Sie beispielsweise bereits Netzwerkstandorte für eine VoIP-Funktion erstellt haben, müssen Sie keine neuen Netzwerkstandorte erstellen, da dieselben Netzwerkstandorte für weitere VoIP-Funktionen verwendet werden können. Sie müssen jedoch möglicherweise eine vorhandene Netzwerkstandortdefinition ändern, um funktionsspezifische Einstellungen anzuwenden. Wenn Sie beispielsweise einen Netzwerkstandort für E9-1-1 erstellt haben, müssen Sie den Netzwerkstandort während der Bereitstellung der Anrufsteuerung ändern, um ein Bandbreitenrichtlinienprofil anzuwenden.

<div>


> [!NOTE]  
> Spezifische Beispiele und Anforderungen für Netzwerkstandorte finden Sie ggf. in den Themen zu erweiterten VoIP-Funktionen in der Bereitstellungsdokumentation: 
> <UL>
> <LI>
> <P><A href="lync-server-2013-configure-network-sites-for-cac.md">Konfigurieren von Netzwerkstandorten für die Anrufsteuerung in lync Server 2013</A></P></LI></UL>



</div>

Ausführliche Informationen zum Arbeiten mit Netzwerkstandorten finden Sie in der lync Server-Verwaltungsshell Dokumentation für die folgenden Cmdlets:

  - [New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

  - [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)

  - [Gruppe-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

  - [Remove-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)

<div>

## <a name="create-a-network-site"></a>Erstellen eines Netzwerkstandorts

Erstellen Sie eine Netzwerkregion, die für Anrufsteuerung, E9-1-1 oder Medienumgehung verwendet werden kann.

<div>

## <a name="to-create-a-network-site-by-using-management-shell"></a>So erstellen Sie einen Netzwerkstandort mithilfe der Verwaltungsshell

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet "New-CsNetworkSite" aus, um Netzwerkstandorte zu erstellen:
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    Zum Beispiel:
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    In diesem Beispiel wird ein Netzwerkstandort namens "Chicago" erstellt, der sich in der Netzwerkregion "NorthAmerica" befindet.
    
    <div>
    

    > [!NOTE]  
    > Die Netzwerkregion "NorthAmerica" muss bereits vorhanden sein, damit dieser Befehl erfolgreich ausgeführt werden kann.

    
    </div>

3.  Zum Abschließen der Erstellung von Netzwerkstandorten für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Standorte.

</div>

<div>

## <a name="to-create-a-network-site-by-using-lync-server-control-panel"></a>So erstellen Sie einen Netzwerkstandort mithilfe der Lync Server-Systemsteuerung

1.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3.  Klicken Sie auf die Navigationsschaltfläche **Standort**.

4.  Klicken Sie auf **Neu**.

5.  Klicken Sie auf der Seite **Neuer Standort** auf **Name**, und geben Sie einen Namen für den Netzwerkstandort ein.

6.  Klicken Sie auf **Region**, und klicken Sie dann auf eine Region in der Liste.

7.  Klicken Sie optional auf **Bandbreitenrichtlinie**, und klicken Sie dann auf eine Bandbreitenrichtlinie in der Liste.
    
    <div>
    

    > [!NOTE]  
    > Eine Bandbreitenrichtlinie ist nur dann erforderlich, wenn Sie die Anrufsteuerung am Standort bereitstellen möchten.

    
    </div>

8.  Klicken Sie optional auf **Ortungsrichtlinie**, und klicken Sie dann auf eine Ortungsrichtlinie in der Liste.
    
    <div>
    

    > [!NOTE]  
    > Eine Ortungsrichtlinie ist nur erforderlich, wenn Sie E9-1-1 am Standort bereitstellen.

    
    </div>

9.  Klicken Sie optional auf **Beschreibung**, und geben Sie zusätzliche Informationen zur Beschreibung dieses Netzwerkstandorts ein.

10. Klicken Sie auf **Commit ausführen**.

11. Zum Abschließen der Erstellung von Netzwerkstandorten für Ihre Topologie wiederholen Sie die Schritte 4 bis 10 mit Einstellungen für weitere Standorte.

</div>

</div>

<div>

## <a name="modify-a-network-site"></a>Ändern eines Netzwerkstandorts

Ändern Sie eine Netzwerkregion, die für Anrufsteuerung, E9-1-1 oder Medienumgehung verwendet werden kann.

<div>

## <a name="to-modify-a-network-site"></a>So ändern Sie einen Netzwerkstandort

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet "Set-CsNetworkSite" aus, um Netzwerkstandorte zu ändern:
    
        Set-CsNetworkSite -Identity <string>
    
    Beispiel:
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    In diesem Beispiel wird der Standort "Albuquerque" in die Netzwerkregion "NorthAmerica" verschoben. Bearbeiten Sie zum Ändern der Netzwerkstandortkonfiguration für die Bereitstellung von Anrufsteuerung, E9-1-1 oder Medienumgehung die Netzwerkstandorteinstellungen, indem Sie das Cmdlet "Set-CsNetworkSite" mit dem Parameter "BWPolicyProfileID" oder "LocationPolicy" ausführen.
    
    <div>
    

    > [!NOTE]  
    > Wenngleich der Parameter "BypassID" für die Medienumgehung vorhanden ist, wird dringend empfohlen, automatisch generierte IDs für die Umgehung nicht außer Kraft zu setzen. Sie müssen keine zusätzlichen Parameter angeben, um einen Netzwerkstandort für die Medienumgehung zu konfigurieren.

    
    </div>

3.  Zum Abschließen der Änderung von Netzwerkstandorten für Ihre Topologie wiederholen Sie Schritt 2 mit Einstellungen für weitere Standorte.

</div>

<div>

## <a name="to-modify-a-network-site-by-using-lync-server-control-panel"></a>So ändern Sie einen Netzwerkstandort mithilfe der Lync Server-Systemsteuerung

1.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3.  Klicken Sie auf die Navigationsschaltfläche **Standort**.

4.  Klicken Sie in der Tabelle auf den Netzwerkstandort, den Sie ändern möchten.

5.  Klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.

6.  Ändern Sie auf der Seite **Standort bearbeiten** die Werte für die Einstellungen dieses Netzwerkstandorts wie gewünscht ab.

7.  Klicken Sie auf **Commit**.

8.  Zum Abschließen der Änderung von Netzwerkstandorten wiederholen Sie die Schritte 4 bis 7 mit Einstellungen für weitere Standorte.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

