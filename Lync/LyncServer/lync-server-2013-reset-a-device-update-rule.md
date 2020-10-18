---
title: 'Lync Server 2013: Zurücksetzen einer geräteaktualisierungsregel'
description: 'Lync Server 2013: Zurücksetzen einer geräteaktualisierungsregel.'
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
ms.openlocfilehash: 8a4d42b6aee8f4cb3fd93839b4a8575059ba71cb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577841"
---
# <a name="reset-a-device-update-rule-in-lync-server-2013"></a>Zurücksetzen einer geräteaktualisierungsregel in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Wenn Ihnen die Art und Weise, wie ein Update auf Ihren Testgeräten funktioniert, nicht gefällt, können Sie die geräteaktualisierungsregel zurücksetzen, die den ausstehenden Status der Regel entfernt und das Update von den Testgeräten deinstalliert.

Sie können eine geräteaktualisierungsregel entweder mithilfe von lync Server-Systemsteuerung oder Windows PowerShell entfernen.

<div>


> [!NOTE]  
> Um eine Regel zu deinstallieren, die Sie bereits genehmigt haben (Dies ist ein Rollback), stellen Sie Sie wieder her. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-restore-a-device-update-rule.md">Wiederherstellen einer geräteaktualisierungsregel in lync Server 2013</A>.



</div>

<div>

## <a name="to-reset-a-device-update-rule-by-using-lync-server-control-panel"></a>So setzen Sie eine geräteaktualisierungsregel mithilfe von lync Server-Systemsteuerung zurück

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Geräte Update** .

4.  Führen Sie auf der Seite **Geräte Update** einen der folgenden Schritte aus:
    
      - Um eine Regel zurückzusetzen, wählen Sie die Regel aus, die Sie zurücksetzen möchten.
    
      - Klicken Sie im Menü **Bearbeiten** auf **Alle auswählen**, um alle Regeln zurückzusetzen.
    
      - Wenn Sie alle Regeln für eine Marke zurücksetzen möchten, verwenden Sie das Menü **Marken** Spalte.

5.  Klicken Sie auf **Aktion**, und klicken Sie dann auf **ausstehende Updates Abbrechen**.
    
    <div>
    

    > [!TIP]  
    > Wenn Sie sicher sind, dass Sie die von Ihnen abgebrochenen geräteaktualisierungsregeln nie Ausrollen möchten, können Sie Sie möglicherweise löschen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-remove-a-device-update-rule.md">Entfernen einer geräteaktualisierungsregel in lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="resetting-a-device-update-rule-by-using-windows-powershell-cmdlets"></a>Zurücksetzen einer geräteaktualisierungsregel mithilfe von Windows PowerShell-Cmdlets

Geräteaktualisierungsregeln können auch mithilfe von Windows PowerShell und dem Cmdlet **Reset-CsDeviceUpdateRule** zurückgesetzt werden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.

<div>


> [!NOTE]  
> Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .



</div>

<div>

## <a name="to-reset-a-specific-device-update-rule-on-a-server"></a>So setzen Sie eine bestimmte geräteaktualisierungsregel auf einem Server zurück

  - Mit dem folgenden Befehl wird die geräteaktualisierungsregel d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 "auf dem Webserver ATL-CS-001.litwareinc.com zurückgesetzt:
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-reset-all-the-device-update-rules-on-a-server"></a>So setzen Sie alle geräteaktualisierungsregeln auf einem Server zurück

  - Mit diesem Befehl werden alle geräteaktualisierungsregeln auf dem Webserver ATL-CS-001.litwareinc.com zurückgesetzt:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

</div>

<div>

## <a name="to-reset-all-the-device-updates-rules-that-have-a-specific-brand"></a>So setzen Sie alle Geräteupdate Regeln zurück, die eine bestimmte Marke aufweisen

  - In diesem Beispiel werden alle Geräte Updates in der gesamten Organisation zurückgesetzt, deren Marke Microsoft entspricht:
    
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

