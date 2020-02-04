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
ms.openlocfilehash: 6e26b67aba2bf792b3248e7771f938a8bced1668
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a>Anzeigen von Informationen zu Geräte Update Regeln in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Anzeigen von Details zu geräteaktualisierungsregeln, die bereits importiert wurden, einschließlich Typ, Modell und Marke der Geräte, auf die das Update angewendet wird; Version und Art des Updates; und das Gebietsschema und den Pool für das Update. Informationen stehen für alle importierten geräteaktualisierungsregeln zur Verfügung – für diejenigen, die genehmigt, bereitgestellt (genehmigt), zurückgerufen (wiederhergestellt) sind und die Sie nicht verwenden möchten (Reset). Greifen Sie entweder in der lync Server-Systemsteuerung oder in Windows PowerShell auf diese Informationen zu.

<div>


> [!NOTE]  
> Details zum Importieren, genehmigen, zurücksetzen, wiederherstellen und Entfernen von Regeln finden Sie in den Themen unter <A href="lync-server-2013-device-update-rules.md">Geräte Update Regeln in lync Server 2013</A>.



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a>So zeigen Sie geräteaktualisierungsregeln mithilfe der lync Server-Systemsteuerung an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Schaltfläche **Geräte Update** -Navigation. Importierte Regeln werden auf der Seite **Device Update** aufgelistet.

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a>Anzeigen von geräteaktualisierungsregeln mithilfe von Windows PowerShell-Cmdlets

Detaillierte Informationen zu allen Geräteupdate Regeln können auch mithilfe von Windows PowerShell und dem Cmdlet **Get-CsDeviceUpdateRule** angezeigt werden. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.

<div>


> [!NOTE]  
> Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Remote-PowerShell" unter.



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a>So zeigen Sie alle geräteaktualisierungsregeln an

  - Mit dem folgenden Befehl werden Informationen zu allen Geräteupdate Regeln zurückgegeben, die für die Verwendung in Ihrer Organisation konfiguriert sind:
    
        Get-CsDeviceUpdateRule
    
    Der Befehl gibt für jede Ihrer geräteaktualisierungsregeln Informationen zurück, die den folgenden ähneln:
    
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

  - Wenn Sie die geräteaktualisierungsregeln auf einem bestimmten Computer anzeigen möchten, verwenden Sie den Parameter Filter, gefolgt von der Serveridentität und\*dem Platzhalterzeichen (). Beispiel:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

