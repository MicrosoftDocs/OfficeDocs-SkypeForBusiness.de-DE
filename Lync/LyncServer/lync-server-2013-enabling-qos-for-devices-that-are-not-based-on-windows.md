---
title: 'Lync Server 2013: Aktivieren von QoS für Geräte, die nicht auf Windows basieren'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: QoS for devices that are not based on Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d993a6905dfad9f5f2eda10a48553f2ae29b58ef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a>Aktivieren von QoS in lync Server 2013 für Geräte, die nicht auf Windows basieren

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Wenn Sie Microsoft lync Server 2013 installieren, wird Quality of Service (QoS) nicht für alle in Ihrer Organisation verwendeten Geräte aktiviert, die ein anderes Betriebssystem als Windows verwenden. Sie können dies überprüfen, indem Sie in der lync Server 2013-Verwaltungsshell den folgenden Befehl ausführen:

    Get-CsMediaConfiguration

Angenommen, Sie haben keine Änderungen an Ihren Medien Konfigurationseinstellungen vorgenommen, sollten Sie Informationen ähnlich wie in diesem Fall wieder finden:

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

Wenn die EnableQoS-Eigenschaft auf "false" (wie in der vorhergehenden Ausgabe) festgelegt ist, bedeutet dies, dass die Dienstqualität für Computer und Geräte, die ein anderes Betriebssystem als Windows verwenden, nicht aktiviert ist. QoS ist standardmäßig für lync Phone Edition-Geräte aktiviert. Es ist jedoch möglich, die Quality of Service für lync Phone Edition zu deaktivieren.

Führen Sie den folgenden Befehl in der lync Server-Verwaltungsshell aus, um Quality of Service im globalen Bereich zu aktivieren:

    Set-CsMediaConfiguration -EnableQoS $True

Der obige Befehl aktiviert QoS im globalen Bereich; Beachten Sie jedoch, dass die Einstellungen für die Medienkonfiguration auch auf den Website Bereich angewendet werden können. Wenn Sie die Dienstqualität für eine Website aktivieren müssen, müssen Sie beim Aufrufen von "CsMediaConfiguration" die Identität der Konfigurationseinstellungen angeben. Mit diesem Befehl wird beispielsweise QoS für die Website "Redmond" aktiviert:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> Müssen Sie QoS im Website Bereich aktivieren? Das hängt davon ab. Dem Website Bereich zugewiesene Einstellungen haben Vorrang vor den dem globalen Bereich zugewiesenen Einstellungen. Angenommen, Sie haben QoS im globalen Bereich aktiviert, aber für den Website Bereich deaktiviert (für die Website "Redmond"). In diesem Fall ist die Dienstqualität für die Website "Redmond" deaktiviert; Das liegt daran, dass die Websiteeinstellungen Vorrang haben. Um QoS für die Redmond-Website zu aktivieren, müssen Sie die Medien Konfigurationseinstellungen verwenden, die auf diese Website angewendet werden.



</div>

Wenn Sie QoS für alle Medien Konfigurationseinstellungen (unabhängig vom Bereich) gleichzeitig aktivieren möchten, führen Sie diesen Befehl in der lync Server-Verwaltungsshell aus:

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

Sie können QoS für Geräte deaktivieren, die ein anderes Betriebssystem als Windows verwenden, indem Sie den Wert der EnableQoS-Eigenschaft auf false festlegen. Beispiel:

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

Dadurch haben Sie die Möglichkeit, QoS in einigen Teilen Ihres Netzwerks (beispielsweise auf der Website "Redmond") zu implementieren, während Sie die Dienstqualität für andere Teile Ihres Netzwerks deaktiviert lassen.

QoS kann nur mithilfe von Windows PowerShell aktiviert und deaktiviert werden diese Optionen stehen in der lync Server-Systemsteuerung nicht zur Verfügung.

</div>

<span> </span>

</div>

</div>

</div>

