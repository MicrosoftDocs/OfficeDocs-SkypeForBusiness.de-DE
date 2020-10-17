---
title: 'Lync Server 2013: Aktivieren von QoS für Geräte, die nicht auf Windows basieren'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoS for devices that are not based on Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9fe6364e92fc6416a78ec49001e94193ae9731e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500932"
---
# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a>Aktivieren von QoS in lync Server 2013 für Geräte, die nicht auf Windows basieren

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Wenn Sie Microsoft lync Server 2013 installieren, wird Quality of Service (QoS) für keine Geräte aktiviert, die in Ihrer Organisation verwendet werden, die ein anderes Betriebssystem als Windows verwenden. Sie können dies überprüfen, indem Sie den folgenden Befehl in der lync Server 2013 Management-Shell ausführen:

    Get-CsMediaConfiguration

Sofern Sie noch keine Änderungen an den Medienkonfigurationseinstellungen vorgenommen haben, sollten ähnliche Informationen wie die folgenden zurückgegeben werden:

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

Wenn die EnableQoS-Eigenschaft auf false (wie in der vorherigen Ausgabe) festgelegt ist, bedeutet dies, dass die Dienstqualität für Computer und Geräte nicht aktiviert ist, die ein anderes Betriebssystem als Windows verwenden. QoS ist für lync Phone Edition-Geräte standardmäßig aktiviert; Es ist jedoch möglich, die Dienstqualität für lync Phone Edition zu deaktivieren.

Führen Sie den folgenden Befehl in der lync Server-Verwaltungsshell aus, um die Dienstqualität auf globaler Ebene zu aktivieren:

    Set-CsMediaConfiguration -EnableQoS $True

Mit dem obigen Befehl wird QoS auf globaler Ebene aktiviert. Es ist jedoch wichtig, dass die Medienkonfigurationseinstellungen auch auf Standortebene angewendet werden können. Wenn Sie QoS für einen Standort aktivieren möchten, müssen Sie beim Aufruf von Set-CsMediaConfiguration die Identität der Konfigurationseinstellungen angeben. Mit dem folgenden Befehl wird QoS beispielsweise für den Standort Redmond aktiviert:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> Müssen Sie QoS auf Standortebene aktivieren? Das kommt darauf an. Einstellungen auf Standortebene haben Vorrang vor globalen Einstellungen. Angenommen, Sie haben QoS auf globaler Ebene aktiviert, aber auf Standortebene (für den Standort Redmond) deaktiviert. In diesem Fall wird QoS für den Standort Redmond deaktiviert, da die Standorteinstellungen Vorrang haben. Um QoS für den Standort Redmond zu aktivieren, müssen Sie entsprechende Medienkonfigurationseinstellungen auf den Standort anwenden.



</div>

Wenn Sie QoS für alle Medien Konfigurationseinstellungen (unabhängig vom Bereich) gleichzeitig aktivieren möchten, führen Sie diesen Befehl in der lync Server-Verwaltungsshell aus:

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Sie können QoS für Geräte deaktivieren, die ein anderes Betriebssystem als Windows verwenden, indem Sie den Wert der EnableQoS-Eigenschaft auf false festlegen. Zum Beispiel:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Auf diese Weise können Sie QoS in einigen Bereichen des Netzwerks implementieren (z. B. für den Standort Redmond), während QoS für andere Bereiche des Netzwerks deaktiviert bleibt.

QoS kann nur mit Windows PowerShell aktiviert und deaktiviert werden, wenn diese Optionen im lync Server-Systemsteuerung nicht verfügbar sind.

</div>

<span> </span>

</div>

</div>

</div>

