---
title: 'Lync Server 2013: Konfigurieren von Netzwerkstandort Links'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network site links
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48184622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50457100f1ba476fd3ddfa923b73acd6bfe6d843
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-network-site-links-in-lync-server-2013"></a>Konfigurieren von Netzwerkstandort Links in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Innerhalb einer Anrufsteuerung (Call Admission Control, CAC) können Sie standortübergreifende Netzwerkrichtlinien erstellen, die Bandbreiteneinschränkungen zwischen Websites definieren, die direkt verknüpft sind. Wenn Netzwerkstandorte eine direkte Verbindung teilen, können Bandbreiteneinschränkungen für Audio- und Videoverbindungen zwischen diesen zwei Standorten definiert werden. Sie können die lync Server-Systemsteuerung nicht zum Konfigurieren von Netzwerkstandort Richtlinien verwenden, dies kann nur mithilfe von Cmdlets aus dem lync Server-Verwaltungsshell erfolgen. Sie können eine netzwerkstandortverknüpfung (auch als standortübergreifende Netzwerkrichtlinie bezeichnet) aus dem lync Server-Verwaltungsshell erstellen, ändern und entfernen.

<div>

## <a name="to-create-a-network-site-link"></a>So erstellen Sie eine Netzwerkstandortverknüpfung

1.  Melden Sie sich an dem Computer an, auf dem lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Geben Sie an der Eingabeaufforderung den folgenden Befehl ein, und verwenden Sie dabei die für Ihre Konfiguration gültigen Werte:
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    In diesem Beispiel wird eine neue netzwerkstandortverknüpfung namens\_Reno Portland erstellt, die Bandbreiteneinschränkungen zwischen den Netzwerkstandorten "Reno" und "Portland" festlegt. Die Netzwerkstandorte und das Bandbreitenrichtlinienprofil müssen bereits vorhanden sein, bevor Sie diesen Befehl ausführen.

Ausführliche Parameterbeschreibungen finden Sie unter [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) in der lync Server-Verwaltungsshell Dokumentation. Zum Abrufen einer Liste der Bandbreitenrichtlinienprofile, die auf die Netzwerkstandortverknüpfung angewendet werden können, verwenden Sie das Cmdlet **Get-CsNetworkBandwidthPolicyProfile**. Ausführliche Informationen finden Sie unter [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) in der lync Server-Verwaltungsshell Dokumentation.

</div>

<div>

## <a name="to-modify-a-network-site-link"></a>So ändern Sie eine Netzwerkstandortverknüpfung

1.  Melden Sie sich an dem Computer an, auf dem lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Verwenden Sie das Cmdlet **Set-CsNetworkInterSitePolicy**, um die Eigenschaften einer Netzwerkstandortverknüpfung zu ändern. Sie können entweder einen oder beide verbundenen Standorte ändern, und Sie können das der Verknüpfung zugeordnete Bandbreitenrichtlinienprofil bearbeiten. Hier ist ein Beispiel für das Ändern des bandbreitenrichtlinienprofils einer Website Verknüpfung namens\_Reno Portland:
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

Ausführliche Parameterbeschreibungen finden Sie unter " [CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) " in der lync Server-Verwaltungsshell Dokumentation.

</div>

<div>

## <a name="to-delete-a-network-site-link"></a>So löschen Sie eine Netzwerkstandortverknüpfung

1.  Melden Sie sich an dem Computer an, auf dem lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Verwenden Sie das Cmdlet **Remove-CsNetworkInterSitePolicy**, um eine Netzwerkstandortverknüpfung zu löschen. Im folgenden Beispiel wird der Link\_für die Portland-Netzwerk Site von Reno gelöscht:
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

Ausführliche Parameterbeschreibungen finden Sie unter [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) in der lync Server-Verwaltungsshell Dokumentation.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Cmdlets für die Anrufsteuerung in lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)  


[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[Gruppe-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

