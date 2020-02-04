---
title: 'Lync Server 2013: Zurücksetzen einer geräteaktualisierungsregel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset a Device Update rule
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994069(v=OCS.15)
ms:contentKeyID: 51803980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36a85ed29f6bf4838428af302904d80a2f792388
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-a-device-update-rule-in-lync-server-2013"></a>Zurücksetzen einer geräteaktualisierungsregel in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Wenn Ihnen die Funktionsweise eines Updates auf Ihren Testgeräten nicht gefällt, können Sie die geräteaktualisierungsregel zurücksetzen, wodurch der Status der Regel ausstehend entfernt und das Update von den Testgeräten deinstalliert wird.

Sie können eine geräteaktualisierungsregel entweder mithilfe der lync Server-Systemsteuerung oder mit Windows PowerShell entfernen.

<div>


> [!NOTE]  
> Wenn Sie eine Regel deinstallieren möchten, die Sie bereits genehmigt haben (also ein Rollup durchgeführt haben), stellen Sie Sie wieder her. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-restore-a-device-update-rule.md">Wiederherstellen einer geräteaktualisierungsregel in lync Server 2013</A>.



</div>

<div>

## <a name="to-reset-a-device-update-rule-by-using-lync-server-control-panel"></a>So setzen Sie eine geräteaktualisierungsregel mithilfe der lync Server-Systemsteuerung zurück

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Schaltfläche **Geräte Update** -Navigation.

4.  Führen Sie auf der Seite **Device Update** eine der folgenden Aktionen aus:
    
      - Um eine Regel zurückzusetzen, wählen Sie die Regel aus, die Sie zurücksetzen möchten.
    
      - Wenn Sie alle Regeln zurücksetzen möchten, klicken Sie im Menü **Bearbeiten** auf **Alles markieren**.
    
      - Wenn Sie alle Regeln für eine Marke zurücksetzen möchten, verwenden Sie das Menü **Marken** Spalte.

5.  Klicken Sie auf **Aktion**und dann auf **ausstehende Updates Abbrechen**.
    
    <div>
    

    > [!TIP]  
    > Wenn Sie sicher sind, dass Sie die von Ihnen stornierten geräteaktualisierungsregeln nie aufrollen möchten, sollten Sie Sie möglicherweise löschen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-remove-a-device-update-rule.md">Entfernen einer geräteaktualisierungsregel in lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="resetting-a-device-update-rule-by-using-windows-powershell-cmdlets"></a>Zurücksetzen einer geräteaktualisierungsregel mithilfe von Windows PowerShell-Cmdlets

Geräteaktualisierungsregeln können auch mithilfe von Windows PowerShell und dem Cmdlet **Reset-CsDeviceUpdateRule** zurückgesetzt werden. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.

<div>


> [!NOTE]  
> Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Remote-PowerShell" unter.



</div>

<div>

## <a name="to-reset-a-specific-device-update-rule-on-a-server"></a>So setzen Sie eine bestimmte geräteaktualisierungsregel auf einem Server zurück

  - Mit dem folgenden Befehl wird die geräteaktualisierungsregel d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 auf dem Webserver ATL-CS-001.litwareinc.com zurückgesetzt:
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-reset-all-the-device-update-rules-on-a-server"></a>So setzen Sie alle geräteaktualisierungsregeln auf einem Server zurück

  - Mit diesem Befehl werden alle geräteaktualisierungsregeln auf dem Webserver ATL-CS-001.litwareinc.com zurückgesetzt:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

</div>

<div>

## <a name="to-reset-all-the-device-updates-rules-that-have-a-specific-brand"></a>So setzen Sie alle Geräteupdate Regeln mit einer bestimmten Marke zurück

  - In diesem Beispiel werden alle Geräte Updates in der gesamten Organisation, die eine Marke von Microsoft aufweisen, zurückgesetzt:
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

</div>

Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) .

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Genehmigen einer geräteaktualisierungsregel in lync Server 2013](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

