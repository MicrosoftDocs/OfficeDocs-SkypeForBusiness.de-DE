---
title: 'Lync Server 2013: Löschen einer vorhandenen clientversionsrichtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing client version policy
ms:assetid: b88aaa25-97ff-4eb6-bd34-b97332cd6890
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923064(v=OCS.15)
ms:contentKeyID: 50675349
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0adc3ab47b3b441eff900c6a9202a782e524c22c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832622"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-client-version-policy-in-lync-server-2013"></a>Löschen einer vorhandenen clientversionsrichtlinie in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Wenn Sie eine zuvor konfigurierte clientversionsrichtlinie löschen möchten, können Sie Sie aus der lync Server 2013-Systemsteuerung oder der lync Server 2013-Verwaltungsshell löschen.

<div>

## <a name="to-delete-client-version-policies-by-using-lync-server-control-panel"></a>So löschen Sie clientversionsrichtlinien mithilfe der lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Schaltfläche für die **Client Versionsrichtlinien** -Navigation.

4.  Wählen Sie auf der Seite **clientversionsrichtlinie** die clientversionsrichtlinie oder Richtlinien aus, die Sie löschen möchten, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Löschen**.

</div>

<div>

## <a name="deleting-client-version-policies-by-using-windows-powershell-cmdlets"></a>Löschen von Client Versionsrichtlinien mithilfe von Windows PowerShell-Cmdlets

Sie können clientversionsrichtlinien mithilfe des Cmdlets **Remove-CsClientVersionPolicy** löschen. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-remove-a-specific-client-version-policy"></a>So entfernen Sie eine bestimmte clientversionsrichtlinie

  - Mit diesem Befehl wird die auf die Redmond-Website angewendete clientversionsrichtlinie gelöscht:
    
        Remove-CsClientVersionPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-client-version-policies-applied-to-the-site-scope"></a>So entfernen Sie alle auf den Website Bereich angewendeten clientversionsrichtlinien

  - Mit diesem Befehl werden alle auf dem Website Bereich konfigurierten clientversionsrichtlinien entfernt:
    
        Get-CsClientVersionPolicy -Fiter "site:*" | Remove-CsClientVersionPolicy

</div>

<div>

## <a name="to-remove-client-version-policies-that-do-not-include-a-specific-user-agent"></a>So entfernen Sie clientversionsrichtlinien, die keinen bestimmten Benutzer-Agent enthalten

  - Und mit diesem Befehl werden alle clientversionsrichtlinien entfernt, die keine Regel für den Windows Phone lync (WPLync)-Benutzer-Agent enthalten:
    
        Get-CsClientVersionPolicy | Where-Object {$_.Rules -notmatch "UserAgent=WPLync" | Remove-CsClientVersionPolicy

</div>

Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

