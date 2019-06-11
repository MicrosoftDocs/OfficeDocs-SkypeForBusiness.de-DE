---
title: 'Lync Server 2013: Entfernen einer geräteaktualisierungsregel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove a Device Update rule
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994066(v=OCS.15)
ms:contentKeyID: 51803977
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3776fe2b80e301e02c099f3c6154afc1c382d0d7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-device-update-rule-in-lync-server-2013"></a>Entfernen einer geräteaktualisierungsregel in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Wenn Sie eine geräteaktualisierungsregel entfernen, wird Sie endgültig aus der Geräte Aktualisierungs Warteschlange entfernt.

Das Entfernen einer Regel unterscheidet sich von der Deinstallation eines Updates von den Geräten in Ihrer Bereitstellung oder von ihren Testgeräten. Wenn Sie ein genehmigtes Update von Ihrer Bereitstellung deinstallieren möchten, stellen Sie die geräteaktualisierungsregel *wieder her* . Ausführliche Informationen finden Sie unter [Wiederherstellen einer geräteaktualisierungsregel in lync Server 2013](lync-server-2013-restore-a-device-update-rule.md). Wenn Sie ein Update deinstallieren möchten, das Sie nicht von ihren Testgeräten genehmigt haben, setzen Sie es *zurück* . Ausführliche Informationen finden Sie unter [Zurücksetzen einer geräteaktualisierungsregel in lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).

Sie können eine geräteaktualisierungsregel entweder mithilfe der lync Server-Systemsteuerung oder mit Windows PowerShell entfernen.

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a>So entfernen Sie geräteaktualisierungsregeln mithilfe der lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Schaltfläche **Geräte Update** -Navigation.

4.  Führen Sie auf der Seite **Device Update** eine der folgenden Aktionen aus:
    
      - Um eine Regel zu entfernen, wählen Sie die Regel aus, die Sie löschen möchten.
    
      - Um alle Regeln zu entfernen, klicken Sie auf das Menü **Bearbeiten** , und klicken Sie dann auf **Alle auswählen**.

5.  Klicken Sie auf **Bearbeiten** und anschließend auf **Löschen**.

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a>Entfernen von Geräte Update Regeln mithilfe von Windows PowerShell-Cmdlets

Geräteaktualisierungsregeln können auch mithilfe von Windows PowerShell und dem Cmdlet **Remove-CsDeviceUpdateRule** entfernt werden. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a>So entfernen Sie eine einzelne geräteaktualisierungsregel von einem Server

  - Mit dem folgenden Befehl wird die geräteaktualisierungsregel d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 vom Webserver auf ATL-CS-001.litwareinc.com entfernt.
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a>So entfernen Sie alle geräteaktualisierungsregeln von einem Server

  - Dieser Befehl entfernt alle geräteaktualisierungsregeln vom Webserver auf ATL-CS-001.litwareinc.com.
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) .

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

