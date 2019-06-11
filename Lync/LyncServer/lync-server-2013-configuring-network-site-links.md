---
title: 'Lync Server 2013: Konfigurieren von Netzwerkstandort Links'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring network site links
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48184622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd0ddd5e28cd37cd31e28e5c6427b9b700b5a4c9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-site-links-in-lync-server-2013"></a>Konfigurieren von Netzwerkstandort Links in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Innerhalb einer Anruf Steuerungskonfiguration können Sie netzwerkübergreifende Richtlinien erstellen, die Bandbreiteneinschränkungen zwischen Websites definieren, die direkt verknüpft sind. Wenn Netzwerk Websites einen direkten Link verwenden, können Bandbreiteneinschränkungen für Audio-und Videoverbindungen zwischen diesen beiden Websites definiert werden. Sie können die lync Server-Systemsteuerung nicht zum Konfigurieren von Netzwerk Website Richtlinien verwenden, dies kann nur mithilfe von Cmdlets aus der lync Server-Verwaltungsshell erfolgen. Sie können einen Netzwerkstandort Link (auch bekannt als netzwerkübergreifende Website Richtlinie) aus der lync Server-Verwaltungsshell erstellen, ändern und entfernen.

<div>

## <a name="to-create-a-network-site-link"></a>So erstellen Sie einen Netzwerkstandort Link

1.  Melden Sie sich bei dem Computer an, auf dem die lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter Delegieren von [Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Geben Sie an der Eingabeaufforderung den folgenden Befehl ein, und ersetzen Sie Werte, die für Ihre Konfiguration gültig sind:
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    In diesem Beispiel wird eine neue netzwerkstandortverknüpfung namens\_Reno Portland erstellt, die Bandbreiteneinschränkungen zwischen den Netzwerkstandorten Reno und Portland festlegt. Die Netzwerk Websites und das bandbreitenrichtlinienprofil müssen bereits vorhanden sein, bevor Sie diesen Befehl ausführen.

Ausführliche Informationen zu den Parametern finden Sie unter [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) in der Dokumentation zur lync Server-Verwaltungsshell. Rufen Sie das Cmdlet **Get-CsNetworkBandwidthPolicyProfile** auf, um eine Liste der bandbreitenrichtlinienprofile abzurufen, die auf den Link Netzwerk Website angewendet werden können. Ausführliche Informationen finden Sie unter [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) in der Dokumentation zur lync Server-Verwaltungsshell.

</div>

<div>

## <a name="to-modify-a-network-site-link"></a>So ändern Sie einen Link für eine Netzwerk Website

1.  Melden Sie sich bei dem Computer an, auf dem die lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter Delegieren von [Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Verwenden Sie das Cmdlet " **Satz-CsNetworkInterSitePolicy** ", um die Eigenschaften einer bestimmten netzwerkstandortverknüpfung zu ändern. Sie können entweder (oder beide) oder die verbundenen Websites ändern, und Sie können das dem Link zugeordnete bandbreitenrichtlinienprofil ändern. Nachfolgend finden Sie ein Beispiel für das Ändern des bandbreitenrichtlinienprofils einer Standort\_Verknüpfung mit dem Namen Reno Portland:
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

Ausführliche Beschreibungen der Parameter finden Sie unter CsNetworkInterSitePolicy in der lync Server [-](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) Verwaltungsshell.

</div>

<div>

## <a name="to-delete-a-network-site-link"></a>So löschen Sie einen Netzwerkstandort Link

1.  Melden Sie sich bei dem Computer an, auf dem die lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter Delegieren von [Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Verwenden Sie das Cmdlet **Remove-CsNetworkInterSitePolicy** , um einen Netzwerkstandort Link zu entfernen. Im folgenden Beispiel wird der Link\_zur Portland-Netzwerk Website von Reno gelöscht:
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

Ausführliche Beschreibungen der Parameter finden Sie unter [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) in der lync Server-Verwaltungsshell.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Cmdlets für die Anrufsteuerung in lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)  


[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

