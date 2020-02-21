---
title: 'Lync Server 2013: Löschen einer vorhandenen clientversionsrichtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing client version policy
ms:assetid: b88aaa25-97ff-4eb6-bd34-b97332cd6890
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923064(v=OCS.15)
ms:contentKeyID: 50675349
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a5a35bf5b6d669d25cd5c91fe318c3de6bcdd03
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-client-version-policy-in-lync-server-2013"></a>Löschen einer vorhandenen clientversionsrichtlinie in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Wenn Sie eine zuvor konfigurierte clientversionsrichtlinie löschen möchten, können Sie Sie aus lync Server 2013 Systemsteuerung oder aus lync Server 2013 Verwaltungsshell löschen.

<div>

## <a name="to-delete-client-version-policies-by-using-lync-server-control-panel"></a>So löschen Sie clientversionsrichtlinien mithilfe von lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Client Versionsrichtlinie** .

4.  Wählen Sie auf der Seite **clientversionsrichtlinie** die clientversionsrichtlinie oder Richtlinien aus, die Sie löschen möchten, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Löschen**.

</div>

<div>

## <a name="deleting-client-version-policies-by-using-windows-powershell-cmdlets"></a>Löschen von Client Versionsrichtlinien mithilfe von Windows PowerShell-Cmdlets

Sie können clientversionsrichtlinien mithilfe des Cmdlets **Remove-CsClientVersionPolicy** löschen. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>

## <a name="to-remove-a-specific-client-version-policy"></a>So entfernen Sie eine bestimmte clientversionsrichtlinie

  - Mit diesem Befehl wird die clientversionsrichtlinie gelöscht, die auf den Standort "Redmond" angewendet wird:
    
        Remove-CsClientVersionPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-client-version-policies-applied-to-the-site-scope"></a>So entfernen Sie alle auf den Website Bereich angewendeten clientversionsrichtlinien

  - Mit diesem Befehl werden alle clientversionsrichtlinien entfernt, die auf Standortebene konfiguriert sind:
    
        Get-CsClientVersionPolicy -Fiter "site:*" | Remove-CsClientVersionPolicy

</div>

<div>

## <a name="to-remove-client-version-policies-that-do-not-include-a-specific-user-agent"></a>So entfernen Sie clientversionsrichtlinien, die keinen bestimmten Benutzer-Agent enthalten

  - Mit diesem Befehl werden alle clientversionsrichtlinien entfernt, die keine Regel für den Windows Phone lync-Benutzer-Agent (WPLync) enthalten:
    
        Get-CsClientVersionPolicy | Where-Object {$_.Rules -notmatch "UserAgent=WPLync" | Remove-CsClientVersionPolicy

</div>

Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

