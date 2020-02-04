---
title: 'Lync Server 2013: Erstellen von Bandbreitenrichtlinien Profilen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create bandwidth policy profiles
ms:assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412785(v=OCS.15)
ms:contentKeyID: 48185086
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d3eef3ea6dfb349f0f712c1127adb8310d90c27
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-bandwidth-policy-profiles-in-lync-server-2013"></a>Erstellen von Bandbreitenrichtlinien Profilen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

*Bandbreitenrichtlinien* definieren Einschränkungen zur Bandbreitenauslastung für in Echtzeit übertragene Audio- und Videodaten. Bandbreitenrichtlinien werden auf *Bandbreitenrichtlinienprofile* angewendet, die zur Anrufsteuerung auf mehrere Netzwerkstandorte angewendet werden können.

Richtlinien darüber, welche Bandbreitengrenzwerte in ihrer CAC-Bereitstellung festgelegt werden sollten, finden Sie unter [Definieren Ihrer Anforderungen für die Anrufsteuerung in lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) in der Planungsdokumentation.

Details zum Arbeiten mit Bandbreitenrichtlinien und Richtlinienprofilen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:

  - [New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)

  - [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

  - [Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)

  - [Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

Die im folgenden Verfahren erstellten Beispielrichtlinien legen Einschränkungen für den Audiodatenverkehr insgesamt, einzelne Audiositzungen, den Videodatenverkehr insgesamt und einzelne Videositzungen fest. So legt das Profil mit\_dem 5MB-Link-bandbreitenrichtlinienprofil die folgenden Grenzwerte fest:

  - Grenzwert für Audio: 2.000 KBit/s

  - Grenzwert für Audiositzung: 200 KBit/s

  - Grenzwert für Video: 1.400 KBit/s

  - Grenzwert für Videositzung: 700 KBit/s

<div class=" ">


> [!NOTE]  
> Der Mindestgrenzwert für Audiositzungen ist 40 KBit/s. Der Mindestgrenzwert für Videositzungen ist 100 KBit/s.



</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-management-shell"></a>So erstellen Sie bandbreitenrichtlinienprofile mithilfe der Verwaltungsshell

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

2.  Führen Sie für jedes Bandbreitenrichtlinienprofil, das Sie erstellen möchten, das Cmdlet „New-CsNetworkBandwidthPolicyProfile“ aus. Führen Sie beispielsweise den folgenden Befehl aus:
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400  -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
       ```

</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-lync-server-control-panel"></a>So erstellen Sie bandbreitenrichtlinienprofile mithilfe der lync Server-Systemsteuerung

1.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.

3.  Klicken Sie auf die Navigationsschaltfläche **Richtlinienprofil**.

4.  Klicken Sie auf **Neu**.

5.  Klicken Sie auf der Seite **Neues Richtlinienprofil** auf **Name** und geben Sie einen Namen für das Bandbreitenrichtlinienprofil ein.

6.  Klicken Sie auf **Audiolimit** und geben Sie die Höchstzahl an KBit/s ein, die für alle Audiositzungen insgesamt zulässig sein soll.

7.  Klicken Sie auf **Grenzwert für Audiositzung** und geben Sie die Höchstzahl an KBit/s ein, die für jede einzelne Audiositzung zulässig sein soll.

8.  Klicken Sie auf **Videolimit** und geben Sie die Höchstzahl an KBit/s ein, die für alle Videositzungen insgesamt zulässig sein soll.

9.  Klicken Sie auf **Grenzwert für Videositzung** und geben Sie die Höchstzahl an KBit/s ein, die für jede einzelne Videositzung zulässig sein soll.

10. Klicken Sie optional auf **Beschreibung** und geben Sie zusätzliche Informationen zur Beschreibung dieses Bandbreitenrichtlinienprofils ein.

11. Klicken Sie auf **Commit ausführen**.

12. Wiederholen Sie die Schritte 4 bis 11 mit Einstellungen für andere Bandbreitenrichtlinienprofile, um die Erstellung von Bandbreitenrichtlinienprofilen für Ihre Topologie abzuschließen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

