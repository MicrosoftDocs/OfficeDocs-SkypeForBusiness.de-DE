---
title: 'Lync Server 2013: deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 502b4cc9c6ed70d0a418dbed7e844064939809d9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a>Deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-04-04_

Mit dem folgenden Verfahren können Sie ein zuvor aktiviertes Benutzerkonto in lync Server 2013 deaktivieren, ohne die lync Server Einstellungen zu verlieren, die Sie für das Benutzerkonto konfiguriert haben. Da die lync Server Benutzerkontoeinstellungen nicht verloren gehen, können Sie ein zuvor aktiviertes Benutzerkonto erneut aktivieren, ohne das Benutzerkonto neu konfigurieren zu müssen.

<div>


> [!WARNING]  
> Durch einfaches Deaktivieren eines Benutzerkontos in Active Directory <STRONG>wird</STRONG> verhindert, dass Benutzer sich anmelden oder lync Server verwenden können. Dies liegt daran, dass lync die Zertifikatauthentifizierung verwendet, die den Authentifizierungsprozess optimiert, und diese Clientzertifikate sind 180 Tage gültig. Wenn Sie deaktivierte Active Directory Konten beenden möchten, die für lync mit Zugriff auf lync Server aktiviert wurden, müssen Sie das Cmdlet <STRONG>Disable-CsUser</STRONG> verwenden oder die <STRONG>lync Server-Systemsteuerung</STRONG> wie in diesem Artikel dargelegt verwenden. Nachdem der Benutzer in lync deaktiviert wurde und der zentrale Verwaltungsspeicher in der Umgebung repliziert wurde, können sich die Benutzer nicht mehr anmelden. Außerdem werden Benutzer, die angemeldet sind, getrennt.



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a>So deaktivieren oder wieder aktivieren Sie ein zuvor aktiviertes Benutzerkonto für lync Server

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das deaktiviert oder erneut aktiviert werden soll, und klicken Sie dann auf **Suchen**.

5.  Klicken Sie in der Tabelle auf das Benutzerkonto, das deaktiviert oder erneut aktiviert werden soll.

6.  Führen Sie im Menü **Aktion** einen der folgenden Schritte aus:
    
      - Wenn Sie das Benutzerkonto für lync Server 2013 vorübergehend deaktivieren möchten, klicken Sie auf **vorübergehend für lync Server deaktivieren**.
    
      - Klicken Sie zum Aktivieren des Benutzerkontos für lync Server 2013 auf **für lync Server erneut aktivieren**.

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Verwenden von Windows PowerShell zum Deaktivieren oder erneuten Aktivieren von Benutzerkonten

Benutzerkonten können vorübergehend deaktiviert und später erneut aktiviert werden, indem das Cmdlet " **CsUser** " verwendet wird. Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>

## <a name="to-disable-a-user-account"></a>So deaktivieren Sie ein Benutzerkonto

  - Zum vorübergehenden Deaktivieren eines Benutzerkontos setzen Sie den Wert der Eigenschaft "Enabled" auf "False" ($False). Zum Beispiel:
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a>So aktivieren Sie ein Benutzerkonto erneut

  - Zum erneuten Aktivieren eines deaktivierten Benutzerkontos setzen Sie den Wert der Eigenschaft "Enabled" auf "True" ($True). Beispiel:
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) ".

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

