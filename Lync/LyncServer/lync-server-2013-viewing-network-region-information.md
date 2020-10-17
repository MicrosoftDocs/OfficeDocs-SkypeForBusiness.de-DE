---
title: 'Lync Server 2013: Anzeigen von Informationen zur netzwerkregion'
description: 'Lync Server 2013: Anzeigen von Informationen zur netzwerkregion.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region information
ms:assetid: 665740d0-a3ed-460f-8337-5ed945f90589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688076(v=OCS.15)
ms:contentKeyID: 49733672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 225cafc392b9b9d0c23f3882d530ad6d2b59f165
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565371"
---
# <a name="viewing-network-region-information-in-lync-server-2013"></a>Anzeigen von Informationen zur netzwerkregion in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Eine Netzwerkregion verbindet verschiedene Teile eines Netzwerks, das sich über verschiedene geografische Bereiche erstreckt. Jede Netzwerkregion muss einem zentralen Standort zugeordnet sein. Der zentrale Standort ist der Rechenzentrumsstandort, an dem der Bandbreitenrichtliniendienst für die Anrufsteuerung ausgeführt wird. Sie können lync Server-Systemsteuerung zum Anzeigen von netzwerkregionen verwenden. Netzwerkregionen beinhalten Einstellungen, die festlegen, ob für Audio- und Videoverbindungen alternative Pfade über das Internet zulässig sind. In diesem Thema wird erklärt, wie vorhandene Netzwerkregionen angezeigt werden. Ausführliche Informationen zum Erstellen oder Ändern vorhandener netzwerkregionen finden Sie unter [erstellen oder Ändern von netzwerkregionen in lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).

<div>

## <a name="to-view-information-about-a-network-region-with-lync-server-control-panel"></a>So zeigen Sie Informationen zu einer netzwerkregion mit lync Server-Systemsteuerung an

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Region**.

4.  Klicken Sie auf der Seite **Region** auf die Region, die Sie anzeigen möchten.
    
    <div>
    

    > [!NOTE]  
    > Sie können immer nur eine Region anzeigen.

    
    </div>

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

</div>

<div>

## <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Informationen zu netzwerkregionen mithilfe von Windows PowerShell-Cmdlets

Sie können Informationen zu netzwerkregionen mithilfe von Windows PowerShell und dem Cmdlet **Get-CsNetworkRegion** anzeigen. Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-network-region-information"></a>So zeigen Sie Informationen zu netzwerkregionen an

  - Geben Sie zum Anzeigen von Informationen zu allen netzwerkregionen den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsNetworkRegion
    
    Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

</div>

Weitere Informationen finden Sie im Hilfethema für das [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)-Cmdlet.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen oder Ändern von netzwerkregionen in lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md)  
[Löschen vorhandener netzwerkregionen in lync Server 2013](lync-server-2013-deleting-existing-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

