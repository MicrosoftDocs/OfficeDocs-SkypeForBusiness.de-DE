---
title: 'Lync Server 2013: Anzeigen von Informationen zu geräteaktualisierungsregeln'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about Device Update rules
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994077(v=OCS.15)
ms:contentKeyID: 51803988
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79fef5d58116da6b8cbc07ce2b16f3dd4f6b28ac
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506382"
---
# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a>Anzeigen von Informationen zu geräteaktualisierungsregeln in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Anzeigen von Details zu geräteaktualisierungsregeln, die bereits importiert wurden, einschließlich Typ, Modell und Gerätemarke, für die das Update gilt; Version und Typ der Aktualisierung; und das Gebietsschema und der Pool für das Update. Informationen stehen für alle importierten geräteaktualisierungsregeln zur Verfügung, die für die Genehmigung ausstehen, bereitgestellt (genehmigt), abgerufen (wiederhergestellt) wurden und die Sie nicht verwenden möchten (zurücksetzen). Greifen Sie entweder lync Server-Systemsteuerung oder Windows PowerShell auf diese Informationen zu.

<div>


> [!NOTE]  
> Ausführliche Informationen zum Importieren, genehmigen, zurücksetzen, wiederherstellen und Entfernen von Regeln finden Sie in den unter <A href="lync-server-2013-device-update-rules.md">Geräte Update Regeln in lync Server 2013</A>aufgeführten Themen.



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a>So zeigen Sie geräteaktualisierungsregeln mithilfe von lync Server-Systemsteuerung an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Geräte Update** . Importierte Regeln werden auf der Seite **Geräteaktualisierung** aufgeführt.

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a>Anzeigen von geräteaktualisierungsregeln mithilfe von Windows PowerShell-Cmdlets

Ausführliche Informationen zu allen geräteaktualisierungsregeln können Sie auch mit Windows PowerShell und dem Cmdlet **Get-CsDeviceUpdateRule** anzeigen. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.

<div>


> [!NOTE]  
> Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a>So zeigen Sie alle Geräteupdate Regeln an

  - Der folgende Befehl gibt Informationen zu allen Geräteupdate Regeln zurück, die für die Verwendung in Ihrer Organisation konfiguriert sind:
    
        Get-CsDeviceUpdateRule
    
    Der Befehl gibt für jede Geräteupdate Regel Informationen zurück, die den folgenden ähneln:
    
        Identity        : Service:WebServer:pool0.vdomain.com/2de8cbf6-9441-4f61-b755-1e4bef1effde
        Id              : 2de8cbf6-9441-4f61-b755-1e4bef1effde
        DeviceType      : UCPhone
        Brand           : Microsoft
        Model           : CPE
        Revision        : A
        Locale          : ENU
        UpdateType      : CPE
        ApprovedVersion :
        RestoreVersion  :
        PendingVersion  : 4.0.7577.4066

</div>

<div>

## <a name="to-view-all-the-device-update-rules-on-a-specific-web-server"></a>So zeigen Sie alle geräteaktualisierungsregeln auf einem bestimmten Webserver an

  - Verwenden Sie zum Anzeigen der geräteaktualisierungsregeln auf einem bestimmten Computer den Parameter Filter, gefolgt von der Serveridentität und dem Platzhalterzeichen ( \* ). Zum Beispiel:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

