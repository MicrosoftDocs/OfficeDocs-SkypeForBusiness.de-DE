---
title: 'Lync Server 2013: Wiederherstellen einer geräteaktualisierungsregel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restore a Device Update rule
ms:assetid: ac490baf-c7a0-48d9-8fd0-ba5729489341
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994061(v=OCS.15)
ms:contentKeyID: 51803972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90eeb82e710b6ea65bc32184685497494dbef8d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restore-a-device-update-rule-in-lync-server-2013"></a>Wiederherstellen einer geräteaktualisierungsregel in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Wenn Sie eine geräteaktualisierungsregel von den Geräten in Ihrer Bereitstellung deinstallieren möchten, stellen Sie Sie wieder her. Durch das Wiederherstellen einer geräteaktualisierungsregel wird das Update deinstalliert und die vorherige Version dieser Regel neu installiert.

Sie können eine geräteaktualisierungsregel entweder mithilfe der lync Server-Systemsteuerung oder mit Windows PowerShell wiederherstellen.

<div>

## <a name="to-restore-device-update-rules-by-using-lync-server-control-panel"></a>So stellen Sie geräteaktualisierungsregeln mithilfe der lync Server-Systemsteuerung wieder her

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Schaltfläche **Geräte Update** -Navigation.

4.  Führen Sie auf der Seite **Device Update** eine der folgenden Aktionen aus:
    
      - Wenn Sie eine Regel wiederherstellen möchten, wählen Sie diese Regel aus.
    
      - Wenn Sie alle Regeln wiederherstellen möchten, klicken Sie auf **Bearbeiten**und dann auf **Alle auswählen**.

5.  Klicken Sie auf das Menü **Aktion** und dann auf **Wiederherstellen**.

</div>

<div>

## <a name="restoring-device-update-rules-by-using-windows-powershell-cmdlets"></a>Wiederherstellen von geräteaktualisierungsregeln mithilfe von Windows PowerShell-Cmdlets

Geräteupdate Regeln können auch mithilfe von Windows PowerShell und dem Cmdlet **Restore-CsDeviceUpdateRule** wiederhergestellt werden. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.

<div>


> [!NOTE]  
> Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Remote-PowerShell" unter.



</div>

<div>

## <a name="to-restore-a-single-device-update-rule-on-a-server"></a>So stellen Sie eine einzelne geräteaktualisierungsregel auf einem Server wieder her

  - Mit dem folgenden Befehl wird die geräteaktualisierungsregel d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 auf dem Webserver ATL-CS-001.litwareinc.com wiederhergestellt:
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-restore-all-the-device-update-rules-on-a-server"></a>So stellen Sie alle geräteaktualisierungsregeln auf einem Server wieder her

  - Mit diesem Befehl werden alle geräteaktualisierungsregeln auf dem Webserver ATL-CS-001.litwareinc.com wiederhergestellt:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

</div>

Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Restore-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

