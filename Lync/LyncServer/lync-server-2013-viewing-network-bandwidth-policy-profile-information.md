---
title: 'Lync Server 2013: Anzeigen von Profilinformationen für die Netzwerkbandbreite'
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
ms.openlocfilehash: c497ad849135e5bdfea4a3f001e86e65c269dca8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-bandwidth-policy-profile-information-in-lync-server-2013"></a>Anzeigen von Profilinformationen zu Netzwerkbandbreiten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Im Rahmen der Anrufannahme Steuerung (CAC) wird eine bandbreitenrichtlinie verwendet, um Bandbreiteneinschränkungen für bestimmte Modalitäten festzulegen. In Microsoft lync Server 2013 können nur den Audio-und Video-Modalitäten Bandbreiteneinschränkungen zugewiesen werden. Sie können allgemeine Bandbreiteneinschränkungen und Sitzungs Einschränkungen einstellen. Sie können die lync Server-Systemsteuerung verwenden, um ein Container Profil für diese Richtlinien zu erstellen, zu ändern oder zu löschen. Jedes bandbreitenrichtlinienprofil kann einem oder mehreren Netzwerkstandorten zugeordnet sein. Gehen Sie wie folgt vor, um ein bandbreitenrichtlinienprofil anzuzeigen. Informationen zum Erstellen oder Ändern eines Profils für Bandbreitenrichtlinien finden Sie unter [erstellen oder Ändern von Bandbreitenrichtlinien Profilen in lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).

<div>

## <a name="to-view-a-bandwidth-policy-profile"></a>So zeigen Sie ein bandbreitenrichtlinienprofil an

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **bandbreitenrichtlinie**.

4.  Klicken Sie auf der Seite **bandbreitenrichtlinie** auf das bandbreitenrichtlinienprofil, das Sie anzeigen möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

</div>

<div>

## <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Profilinformationen für die Netzwerkbandbreite mithilfe von Windows PowerShell-Cmdlets

Netzwerkbandbreiten Profile können mithilfe von Windows PowerShell und dem Cmdlet Get-CsNetworkBandwidthPolicyProfile angezeigt werden. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-view-network-bandwidth-policy-profile-information"></a>So zeigen Sie Profilinformationen zu Netzwerkbandbreiten an

  - Wenn Sie Informationen zu allen Richtlinienprofilen für Netzwerkbandbreite anzeigen möchten, geben Sie den folgenden Befehl in der lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsNetworkBandwidthPolicyProfile
    
    Es werden etwa folgende Informationen zurückgegeben:
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) .

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen oder Ändern von Bandbreitenrichtlinien Profilen in lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[Löschen von Netzwerkbandbreite-Richtlinienprofilen in lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[Konfigurieren der Anrufsteuerung in lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

