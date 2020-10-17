---
title: 'Lync Server 2013: Anzeigen von Informationen zum Netzwerk-Subnetz'
description: 'Lync Server 2013: Anzeigen von Netzwerk-Subnetz-Informationen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network subnet information
ms:assetid: 46f165f2-efe3-4cc1-9fee-a78b7f2ed41e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688044(v=OCS.15)
ms:contentKeyID: 49733636
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 313135c43318817391d54f2fa3e73dd318f7a11f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546151"
---
# <a name="viewing-network-subnet-information-in-lync-server-2013"></a>Anzeigen von Informationen zum Netzwerk-Subnetz in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Mit dem folgenden Verfahren können Sie ein Netzwerksubnetz anzeigen. Im lync Server-Systemsteuerung können Sie ein Netzwerk-Subnetz erstellen, ändern oder löschen. Ausführliche Informationen zum Erstellen oder Ändern von Netzwerksubnetzen finden Sie unter [Create or Modify Network subsubnets in lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).

<div>

## <a name="to-view-a-network-subnet"></a>So zeigen Sie ein Netzwerksubnetz an

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Subnetz**.

4.  Klicken Sie auf der Seite **Subnetz** auf das Subnetz, das Sie anzeigen möchten.
    
    <div>
    

    > [!NOTE]  
    > Sie können nur jeweils ein Subnetz anzeigen.

    
    </div>

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

</div>

<div>

## <a name="viewing-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Netzwerk-Subnetz-Konfigurationsinformationen mithilfe von Windows PowerShell-Cmdlets

Informationen zum Netzwerksubnetz können mithilfe von Windows PowerShell und dem Get-CsNetworkSubnet-Cmdlet angezeigt werden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-network-subnet-information"></a>So zeigen Sie Netzwerk-Subnetz-Informationen an

  - Geben Sie zum Anzeigen von Informationen zu allen Netzwerksubnetzen den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsNetworkSubnet
    
    Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0

</div>

Weitere Informationen finden Sie im Hilfethema für das Cmdlet [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen oder Ändern von Netzwerk-Subnetzen in lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md)  
[Löschen von Netzwerk Subnetzen in lync Server 2013](lync-server-2013-deleting-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

