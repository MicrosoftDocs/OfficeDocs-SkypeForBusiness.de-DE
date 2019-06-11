---
title: 'Lync Server 2013: deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7944af89ffae7545ba3a2593c7617fc944a7916e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a>Deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-04-04_

Mit dem folgenden Verfahren können Sie ein zuvor aktiviertes Benutzerkonto in lync Server 2013 deaktivieren, ohne die lync-Server Einstellungen zu verlieren, die Sie für das Benutzerkonto konfiguriert haben. Da die Einstellungen für das lync Server-Benutzerkonto nicht verloren gehen, können Sie ein zuvor aktiviertes Benutzerkonto erneut aktivieren, ohne das Benutzerkonto neu konfigurieren zu müssen.

<div>


> [!WARNING]  
> Durch einfaches Deaktivieren eines Benutzerkontos in Active Directory wird verhindert, dass ein Benutzer sich <STRONG>nicht</STRONG> anmelden oder lync Server verwenden kann. Dies liegt daran, dass lync die Zertifikatauthentifizierung verwendet, die den Authentifizierungsprozess optimiert, und diese Clientzertifikate sind für 180 Tage gültig. Wenn Sie die deaktivierten Active Directory-Konten, die für lync aktiviert wurden, nicht mehr auf lync Server zugreifen möchten, müssen Sie das Cmdlet <STRONG>Disable-CsUser</STRONG> verwenden oder die <STRONG>lync Server-System</STRONG> Steuerung verwenden, wie in diesem Artikel dargelegt. Nachdem der Benutzer in lync deaktiviert wurde und der zentrale Verwaltungsspeicher in der Umgebung repliziert wurde, können sich die Benutzer nicht mehr anmelden. Außerdem werden Benutzer, die angemeldet sind, getrennt.



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a>So deaktivieren oder erneutes Aktivieren eines zuvor aktivierten Benutzerkontos für lync Server

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Geben Sie im Feld **Benutzer suchen** den gesamten oder den ersten Teil des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontos (Security Accounts Manager), der SIP-Adresse oder des Uniform Resource Identifier (URI) des Benutzerkontos ein, das Sie deaktivieren oder erneut aktivieren möchten. und klicken Sie dann auf **Suchen**.

5.  Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie deaktivieren oder erneut aktivieren möchten.

6.  Führen Sie im Menü **Aktion** eine der folgenden Aktionen aus:
    
      - Wenn Sie das Benutzerkonto für lync Server 2013 vorübergehend deaktivieren möchten, klicken Sie auf **vorübergehend für lync Server deaktivieren**.
    
      - Wenn Sie das Benutzerkonto für lync Server 2013 aktivieren möchten, klicken Sie auf **für lync Server erneut aktivieren**.

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Verwenden von Windows PowerShell zum Deaktivieren oder erneuten Aktivieren von Benutzerkonten

Mithilfe des Cmdlets " **Satz-CsUser** " können Benutzerkonten vorübergehend deaktiviert und später erneut aktiviert werden. Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-disable-a-user-account"></a>So deaktivieren Sie ein Benutzerkonto

  - Wenn Sie ein Benutzerkonto vorübergehend deaktivieren möchten, legen Sie den Wert der Enabled-Eigenschaft auf false ($false) fest. Beispiel:
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a>So aktivieren Sie ein Benutzerkonto erneut

  - Wenn Sie ein deaktiviertes Benutzerkonto erneut aktivieren möchten, legen Sie den Wert der Enabled-Eigenschaft auf true ($true) fest. Beispiel:
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) ".

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Hinzufügen und Aktivieren des Benutzerkontos für lync Server 2013](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[Aktivieren und Deaktivieren von Benutzern für lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

