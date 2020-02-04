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
ms.openlocfilehash: 3cca8df1ea3c4c2458851da24ab8b39dbbab2d3d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734445"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-bandwidth-in-lync-server-2013"></a>Konfigurieren der Videobandbreite in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

Lync Server 2013 umfasst verschiedene Einstellungen für die Verwaltung von Video für zwei-Parteien-Anrufe und Mehrparteienkonferenzen. Wenn Sie lync Server 2013 bereitstellen, sollten Sie überprüfen, ob die Standardeinstellungen für Ihre Organisation geeignet sind, und Sie bei Bedarf ändern.

Die in diesem Abschnitt beschriebenen Parameter gelten sowohl für zwei-Parteien-Anrufe als auch für mehr Parteien-Konferenzen. Sie können diese Einstellungen mithilfe eines der folgenden Cmdlets anzeigen oder ändern:

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

Überprüfen Sie die folgenden Einstellungen in ihrer konferenzrichtlinie:

  - **VideoBitRateKb**   diese Einstellung gibt die maximale Video-Bitrate in Kbit/s (Kbit/s) für Video an, die von einem Benutzer gesendet wird. Der Standardwert ist 50000 Kbit/s. Gültige Werte sind 0 bis 50000.
    
    Diese Einstellung gilt separat für Haupt-und Panorama Video.
    
    Beispiel: Wenn Sie 2000 Kbit/s angeben, kann lync Server 2000 Kbit/s für den Haupt Videostream und 2000 Kbit/s für den Panorama-Videostream senden.
    
    <div>
    

    > [!NOTE]  
    > Die maximale Video Netzwerkbandbreite für einen lync 2013-Endpunkt beträgt 8000 kBit/s für das Hauptvideo und 2500 Kbit/s für Panorama Video. Diese Höchstwerte werden nur erreicht, wenn mehrere Videos empfangen oder gesendet werden. Ausführliche Informationen finden Sie im Abschnitt "Verwendung des Medien Verkehrs Netzwerks" unter <A href="lync-server-2013-network-bandwidth-requirements-for-media-traffic.md">Netzwerkbandbreite für den Mediendatenverkehr in lync Server 2013</A>. In diesem Abschnitt werden die maximale und typische Videodatenstrom Bandbreite für alle unterstützten Auflösungen aufgeführt.

    
    </div>

  - **TotalReceiveVideoBitRateKb**   diese Einstellung, die in lync Server 2013 neu ist, gibt die maximal zulässige Bitrate (in Kbit/s) für alle Videodatenströme an, die von einem Client empfangen werden. Das bedeutet, dass die kombinierte Gesamtsumme für alle Videostreams, mit Ausnahme von Panorama-Videostreams, angegeben wird, die ein Client empfangen kann. Wenn Sie beispielsweise 1500 kBit/s angeben, kann ein Client bis zu 1500 kBit/s des Videos empfangen, das aus mehreren Videoströmen oder einem einzelnen Videostream bestehen kann. Diese Einstellung gilt nur für lync Server 2013-Clients.
    
    Der Standardwert für **TotalReceiveVideoBitRateKb** ist 50000 Kbit/s. Wenn die **EnableMultiviewJoin** -Einstellung für die Katalogansicht auf "true" festgelegt ist, darf **TotalReceiveVideoBitRateKb** nicht unter 420 Kbit/s festgelegt werden. Wenn die **EnableMultiviewJoin** -Einstellung für die Katalogansicht auf "false" festgelegt ist, darf **TotalReceiveVideoBitRateKb** nicht unter 100 kbit/s festgelegt werden. Wenn **EnableMultiviewJoin** auf "true" festgelegt ist und Sie den Wert unter 420 Kbit/s festlegen, werden die Werte standardmäßig auf den Schwellenwert festgelegt. Dieser Grenzwert hilft bei der Vermeidung versehentlicher Fehlkonfiguration, die zu einer schlechten Benutzererfahrung führen kann.
    
    <div>
    

    > [!NOTE]  
    > Details zur <STRONG>EnableMultiviewJoin</STRONG> -Einstellung finden Sie unter <A href="lync-server-2013-configuring-gallery-view.md">Konfigurieren der Katalogansicht in lync Server 2013</A>.

    
    </div>

  - **MaxVideoConferencingResolution**   dieser Parameter wird für lync Server 2013-Clients in lync Server 2013-Konferenzen nicht mehr verwendet. Lync Server 2013-Konferenzen verwenden die Bitraten Steuerelemente, die weiter oben in diesem Abschnitt beschrieben wurden. Diese Einstellung wird weiterhin für Legacy-Clients verwendet, die einer lync Server 2013-Konferenz beitreten. Dieser Parameter bestimmt die maximale Auflösung, die für Legacyclients in Konferenzen zulässig ist, die von Benutzern organisiert werden, die in lync Server 2013 verwaltet werden. Legacy-Clients werden also genauso behandelt wie in früheren Versionen von lync Server oder Office Communications Server.

Überprüfen Sie zusätzlich zu den Einstellungen für Konferenzrichtlinien, die für Benutzer gelten, die Einstellungen für die Medienkonfiguration. Sie können diese Einstellungen mithilfe eines der folgenden Cmdlets anzeigen oder ändern:

  - **Get-CsMediaConfiguration**

  - **Satz-CsMediaConfiguration**

  - **Neu – CsMediaConfiguration**

Überprüfen Sie die folgende Einstellung:

  - **MaxVideoRateAllowed**   diese pro-Pool-Einstellung gibt die maximale Rate an, mit der Videosignale an den Clientendpunkten übertragen werden. Sie gilt nur für frühere Versionen von lync Server-Clients.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013-Clients ignorieren diese Einstellung und verwenden stattdessen die TotalReceiveVideoBitRateKb-Einstellung in Konferenzrichtlinien.

    
    </div>
    
    Der Standardwert ist 720p. Gültige Werte sind HD720p15M, VGA600K und CIF250K.
    
    Beispiel: Wenn Sie 1500 kBit/s angeben, können alle Legacyclients im Pool bis zu 1500 kBit/s Video in zwei-oder Mehrparteienkonferenzen empfangen.

Die folgenden Verfahren sind Beispiele für die Verwendung der lync Server-Verwaltungsshell zum Ändern der in diesem Abschnitt beschriebenen Einstellungen.

<div>

## <a name="to-modify-conferencing-policy-for-video-settings"></a>So ändern Sie die konferenzrichtlinie für Videoeinstellungen

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie in der Befehlszeile das folgende Cmdlet aus, um die konferenzrichtlinie zu bearbeiten:
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -VideoBitRateKb 2000 -TotalReceiveVideoBitRateKb 2000 

</div>

<div>

## <a name="to-modify-media-configuration-for-legacy-clients"></a>So ändern Sie die Medienkonfiguration für Legacy-Clients

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie in der Befehlszeile das folgende Cmdlet aus, um die Medienkonfiguration zu bearbeiten:
    
        Set-CsMediaConfiguration -Identity site:Redmond01 -MaxVideoRateAllowed CIF250K

</div>

</div>

<span> </span>

</div>

</div>

</div>

