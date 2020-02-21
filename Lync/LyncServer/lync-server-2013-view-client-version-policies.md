---
title: 'Lync Server 2013: Anzeigen von clientversionsrichtlinien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version policies
ms:assetid: 6cd9a897-c694-4d6a-8259-2d3c01fce275
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898479(v=OCS.15)
ms:contentKeyID: 50873759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79eae7471760b31e300cdc310b33c44a80587215
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-client-version-policies-in-lync-server-2013"></a>Anzeigen von clientversionsrichtlinien in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Clientversionsrichtlinien werden verwendet, um eine Reihe von Regeln für die Client Versionsverwaltung auf globaler Ebene oder auf einen bestimmten Standort, einen Pool oder eine Gruppe von Benutzern anzuwenden. Sie können die clientversionsrichtlinien, die in ihrer lync Server 2013 Umgebung konfiguriert wurden, über lync Server 2013 Systemsteuerung oder lync Server 2013 Verwaltungsshell anzeigen.

<div>

## <a name="to-view-client-version-policies-by-using-lync-server-control-panel"></a>So zeigen Sie clientversionsrichtlinien mithilfe von lync Server-Systemsteuerung an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Client Versionsrichtlinie** .

4.  Wenn Sie die Regeln für eine clientversionsrichtlinie anzeigen möchten, doppelklicken Sie auf der Seite **clientversionsrichtlinie** auf die Richtlinie, die Sie anzeigen möchten.

</div>

<div>

## <a name="viewing-client-version-policies-by-using-windows-powershell-cmdlets"></a>Anzeigen von Client Versionsrichtlinien mithilfe von Windows PowerShell-Cmdlets

Sie können clientversionsrichtlinien anzeigen, indem Sie das Cmdlet **Get-CsClientVersionPolicy** verwenden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>

## <a name="to-view-client-version-policies"></a>So zeigen Sie clientversionsrichtlinien an

  - Um Informationen zu allen clientversionsrichtlinien anzuzeigen, geben Sie den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsClientVersionPolicy
    
    Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:
    
        Identity    : Global
        Rules       : {RuleId=2336c611-a243-4c5d-994b-eea8a524d0e4;
                      Description=;Action=Block;ActionUrl=;MajorVersion=1;
                      MinorVersion=3;BuildNumber=;QfeNumber=;
                      UserAgent=RTC;UserAgentFullName=;Enabled=True;
                      CompareOp=LEQ, RuleId=342c9b90-4cef-483a-a73a-
                      4fe75c88711d;Description=;Action=Block;ActionUrl=;
                      MajorVersion=5;MinorVersion=;BuildNumber=;QfeNumber=;
                      UserAgent=WM;UserAgentFullName=;Enabled=True;
                      CompareOp=LEQ,RuleId=ea03af61-9db5-4bf9-af3f-042
                      ab8dd9994;Description=;Action=Block;ActionUrl=;
                      MajorVersion=3;MinorVersion=5;BuildNumber=6907;
                      QfeNumber=83;UserAgent=OC;UserAgentFullName=;
                      Enabled=True;CompareOp=LEQ, RuleId=831edb68-
                      e482-4431-a10e-add365ba8099;Description=;
                      Action=Block;ActionUrl=;MajorVersion=2;MinorVersion=0;
                      BuildNumber=5999;QfeNumber=;UserAgent=UCCP;
                      UserAgentFullName=;Enabled=True;CompareOp=LEQ...}
        Description :

</div>

Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

