---
title: 'Lync Server 2013: Konfigurieren der Videobandbreite'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video bandwidth in Lync Server
ms:assetid: 446bed91-b26f-4ab2-b2f5-36e6810b405b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204842(v=OCS.15)
ms:contentKeyID: 48183984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed1dfd2e8879776733e6ca6fbd8d6024533ef622
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a>Konfigurieren der Videobandbreite in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-02_

Lync Server 2013 enthält verschiedene Einstellungen für die Verwaltung von Videos für Anrufe mit zwei Teilnehmern und Konferenzen mit mehreren Teilnehmern. Wenn Sie lync Server 2013 bereitstellen, sollten Sie überprüfen, ob die Standardeinstellungen für Ihre Organisation geeignet sind, und Sie bei Bedarf ändern.

Die in diesem Abschnitt beschriebenen Parameter gelten für Anrufe mit zwei und Konferenzen mit mehreren Teilnehmern. Sie können diese Einstellungen mithilfe eines der folgenden Cmdlets anzeigen oder ändern:

  - **Get-CsConferencingPolicy**

  - **Gruppe-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

Überprüfen Sie in Ihrer Konferenzrichtlinie die folgenden Einstellungen:

  - **VideoBitRateKb**   mit dieser Einstellung wird die maximale Video Bitrate (Kbit/s) angegeben, die für von einem Benutzer gesendete Videodaten verwendet wird. Der Standardwert ist 50.000 KBit/s. Gültige Werte sind 0 bis 50.000 KBit/s.
    
    Diese Einstellung gilt separat für Haupt- und Panoramavideo.
    
    Beispiel: Wenn Sie 2000 Kbit/s angeben, können lync Server 2000 Kbit/s für den Haupt-Videodatenstrom und 2000 Kbit/s für den Panorama-Videostream senden.
    
    <div>
    

    > [!NOTE]  
    > Die maximale Video Netzwerkbandbreite für einen lync 2013 Endpunkt beträgt 8000 kBit/s für das Hauptvideo und 2500 Kbit/s für Panorama Video. Diese Höchstwerte werden nur erreicht, wenn mehrere Videos gesendet oder empfangen werden. Ausführliche Informationen finden Sie im Abschnitt "Verwendung des Medien Verkehrs Netzwerks" unter Anforderungen an die <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Netzwerkbandbreite für Mediendatenverkehr in lync Server 2013</A>. In diesem Abschnitt sind die maximale und typische Videostream-Bandbreite für alle unterstützen Auflösungen aufgeführt.

    
    </div>

  - **TotalReceiveVideoBitRateKb**   diese Einstellung, die neu in lync Server 2013 ist, gibt die maximal zulässige Bitrate (in Kbit/s) für alle Videodatenströme an, die von einem Client empfangen werden. Dies bedeutet, dass damit der kombinierte Gesamtwert für alle Videostreams mit Ausnahme der Panoramavideo-Streams angegeben wird, die ein Client empfangen kann. Wenn Sie beispielsweise 1.500 KBit/s angeben, kann ein Client bis zu 1.500 KBit/s an Videoinhalten empfangen, die aus einem einzelnen oder mehreren Videostreams bestehen können. Diese Einstellung gilt nur für lync Server 2013 Clients.
    
    Der Standardwert für **TotalReceiveVideoBitRateKb** ist 50.000 KBit/s. Wenn die **EnableMultiviewJoin**-Einstellung für die Katalogansicht auf "True" festgelegt ist, darf **TotalReceiveVideoBitRateKb** nicht auf weniger als 420 KBit/s festgelegt sein. Wenn die **EnableMultiviewJoin**-Einstellung für die Katalogansicht auf "True" festgelegt ist, darf **TotalReceiveVideoBitRateKb** nicht auf weniger als 100 KBit/s festgelegt sein. Wenn **EnableMultiviewJoin** auf "True" festgelegt ist und Sie den Wert auf weniger als 420 KBit/s festlegen, werden die Werte standardmäßig auf den Schwellenwert festgelegt. Dieser Schwellenwert verhindert versehentliche Fehlkonfigurationen, die eine schlechte Benutzererfahrung zur Folge haben könnten.
    
    <div>
    

    > [!NOTE]  
    > Ausführliche Informationen zur <STRONG>EnableMultiviewJoin</STRONG> -Einstellung finden Sie unter <A href="lync-server-2013-configuring-gallery-view.md">Configuring Gallery View in lync Server 2013</A>.

    
    </div>

  - **MaxVideoConferencingResolution**   dieser Parameter wird nicht mehr für lync Server 2013 Clients in lync Server 2013 Konferenzen verwendet. In lync Server 2013 Konferenzen werden die weiter oben in diesem Abschnitt beschriebenen Bitraten Steuerelemente verwendet. Diese Einstellung wird weiterhin für Legacyclients verwendet, die einer lync Server 2013 Konferenz beitreten. Dieser Parameter bestimmt die maximal zulässige Auflösung für Legacyclients in Konferenzen, die von Benutzern organisiert werden, die in lync Server 2013 verwaltet werden. Ältere Clients werden also genauso behandelt wie in früheren Versionen von lync Server oder Office Communications Server.

Überprüfen Sie zusätzlich zu den für Benutzer geltenden Einstellungen für Konferenzrichtlinien die Medienkonfigurationseinstellungen. Sie können diese Einstellungen mithilfe eines der folgenden Cmdlets anzeigen oder ändern:

  - **Get-CsMediaConfiguration**

  - **Gruppe-CsMediaConfiguration**

  - **New-CsMediaConfiguration**

Überprüfen Sie die folgenden Einstellungen:

  - **MaxVideoRateAllowed**   diese pro-Pool-Einstellung gibt die maximale Rate an, mit der Videosignale an den Clientendpunkten übertragen werden. Sie gilt nur für frühere Versionen von lync Server Clients.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 Clients ignorieren diese Einstellung und verwenden stattdessen die TotalReceiveVideoBitRateKb-Einstellung in der konferenzrichtlinie.

    
    </div>
    
    Der Standardwert ist HD720P. Gültige Werte sind HD720p15M, VGA600K und CIF250K.
    
    Beispiel: Wenn Sie 1.500 KBit/s angeben, können alle Clients von Vorversionen im Pool in Konferenzen mit zwei oder mehr Teilnehmern bis zu 1.500 KBit/s an Videoinhalten empfangen.

Die folgenden Verfahren sind Beispiele für die Verwendung von lync Server-Verwaltungsshell zum Ändern der in diesem Abschnitt beschriebenen Einstellungen.

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a>So ändern Sie die Einstellungen der Konferenzrichtlinie für Videos

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie an der Befehlszeile das folgende Cmdlet aus, um die Konferenzrichtlinie zu bearbeiten:
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a>So ändern Sie die Medienkonfiguration für Clients von Vorversionen

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie an der Befehlszeile das folgende Cmdlet aus, um die Medienklonfiguration zu bearbeiten:
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

