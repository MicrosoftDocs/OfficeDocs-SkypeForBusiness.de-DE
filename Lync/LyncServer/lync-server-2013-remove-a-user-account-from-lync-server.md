---
title: 'Lync Server 2013: Entfernen eines Benutzerkontos aus lync Server'
description: 'Lync Server 2013: Entfernen eines Benutzerkontos aus lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a user account from Lync Server
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49733596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 201eb8a7ba620792b92e2c7983890047c249ce86
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555751"
---
# <a name="remove-a-user-account-from-lync-server-2013"></a>Entfernen eines Benutzerkontos aus lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-22_

Mit dem folgenden Verfahren können Sie ein zuvor hinzugefügtes Benutzerkonto in lync Server 2013 entfernen.

<div>


> [!NOTE]  
> Wenn Sie einen Benutzer entfernen, gehen alle Einstellungen verloren, die Sie für das Benutzerkonto konfiguriert haben. Wenn Sie stattdessen ein Benutzerkonto vorübergehend deaktivieren möchten, lesen Sie das Thema <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server 2013</A>.



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a>So entfernen Sie ein Benutzerkonto mithilfe von lync Server-Verwaltungsshell

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager, Sicherheitskonto-Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das deaktiviert oder erneut aktiviert werden soll, und klicken Sie dann auf **Suchen**.

5.  Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie entfernen möchten.

6.  Klicken Sie im Menü **Aktion** auf **Aus Lync Server entfernen**. Daraufhin wird ein Dialogfeld angezeigt.

7.  Wählen Sie im Dialogfeld**OK** aus, um den Benutzer zu entfernen.

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a>Entfernen von Benutzerkonten mithilfe von Windows PowerShell-Cmdlets

Sie können Benutzerkonten mithilfe des Disable-CsUser-Cmdlets entfernen. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-remove-a-user-account"></a>So entfernen Sie ein Benutzerkonto

  - Sie können das Cmdlet Disable-CsUser verwenden, um ein Benutzerkonto zu entfernen. Beispiel:
    
        Disable-CsUser -Identity "Ken Myer"
    
    Nachdem dieser Befehl ausgeführt wurde, gibt es keine Möglichkeit, das Konto erneut zu aktivieren und die vorherigen Kontoeinstellungen wiederherzustellen. Stattdessen müssen Sie das Cmdlet Enable-CsUser- verwenden, um für Ken Myer ein ganz neues Konto zu erstellen.

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) .

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[Aktivieren und Deaktivieren von Benutzern für lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

