---
title: 'Lync Server 2013: Anzeigen von Richtlinienprofil Informationen für Netzwerkbandbreite'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network bandwidth policy profile information
ms:assetid: eed453fc-04e9-4971-959c-6fad54bf1c96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721931(v=OCS.15)
ms:contentKeyID: 49733866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08b8b984b1fd0c468f5ca340880ec294bf870e0e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518312"
---
# <a name="viewing-network-bandwidth-policy-profile-information-in-lync-server-2013"></a>Anzeigen von Richtlinienprofil Informationen für Netzwerkbandbreite in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Im Rahmen der Anrufsteuerung wird eine Bandbreitenrichtlinie dazu verwendet, Bandbreiteneinschränkungen für bestimmte Modalitäten zu definieren. In Microsoft lync Server 2013 können nur Audio-und Video Modalitäten Bandbreiteneinschränkungen zugewiesen werden. Sie können allgemeine Bandbreiteneinschränkungen und Sitzungseinschränkungen festlegen. Sie können das lync Server-Systemsteuerung verwenden, um ein Container Profil für diese Richtlinien zu erstellen, zu ändern oder zu löschen. Jedes Bandbreitenrichtlinienprofil kann einem oder mehreren Netzwerkstandorten zugeordnet werden. Verwenden Sie die folgenden Verfahren, um ein Bandbreitenrichtlinienprofil anzuzeigen. Informationen zum Erstellen oder Ändern eines Richtlinienprofils für Bandbreiten finden Sie unter [erstellen oder Ändern von Bandbreitenrichtlinien Profilen in lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).

<div>

## <a name="to-view-a-bandwidth-policy-profile"></a>So zeigen Sie ein bandbreitenrichtlinienprofil an

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Bandbreitenrichtlinie**.

4.  Klicken Sie auf der Seite **bandbreitenrichtlinie** auf das bandbreitenrichtlinienprofil, das Sie anzeigen möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details einblenden**.

</div>

<div>

## <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Richtlinienprofil Informationen für Netzwerkbandbreite mithilfe von Windows PowerShell-Cmdlets

Netzwerkbandbreiten-Profile können mithilfe von Windows PowerShell und dem Get-CsNetworkBandwidthPolicyProfile-Cmdlet angezeigt werden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-network-bandwidth-policy-profile-information"></a>So zeigen Sie Informationen zum Netzwerkband breiten Richtlinienprofil an

  - Wenn Sie Informationen zu allen Richtlinienprofilen für die Netzwerkbandbreite anzeigen möchten, geben Sie den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsNetworkBandwidthPolicyProfile
    
    Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :

</div>

Weitere Informationen finden Sie in dem Hilfethema zum [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)-Cmdlet.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen oder Ändern von Bandbreitenrichtlinien Profilen in lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[Löschen von Richtlinienprofilen für Netzwerkbandbreite in lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[Konfigurieren der Anrufsteuerung in lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

