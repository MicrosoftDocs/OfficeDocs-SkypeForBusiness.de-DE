---
title: 'Lync Server 2013: Konfigurieren von Sicherheitseinstellungen für lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure security settings for Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521014(v=OCS.15)
ms:contentKeyID: 48184464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68fad5a47f8b56bd97386dcab49aef9671c6f99e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035227"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a>Konfigurieren von Sicherheitseinstellungen für lync Phone Edition in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Verbessern Sie die Sicherheit von Geräten, auf denen lync Phone Edition, über Ihre SIP-Sicherheitseinstellung und Einstellungen für die Telefonsperre.

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a>So konfigurieren Sie Sicherheitseinstellungen für lync Phone Edition

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf **Gerätekonfiguration**.

4.  Doppelklicken Sie auf der Seite **Gerätekonfiguration** in der Liste der Gerätekonfigurationen auf diejenige Konfiguration, deren Sicherheitseinstellungen Sie ändern möchten.

5.  Geben Sie in **Gerätekonfiguration bearbeiten** in **SIP-Sicherheit** die SIP-Sicherheitsebene an. Die Standardebene, die auch empfohlen wird, lautet **Hoch**.

6.  Aktivieren oder deaktivieren Sie in **Gerätekonfiguration bearbeiten** unter **Telefonsperre** das Kontrollkästchen **Gerätesperre erzwingen** (standardmäßig ausgewählt), und geben Sie die minimale PIN-Länge (standardmäßig 6 Zeichen) und die Timeoutdauer (standardmäßig 10 Minuten) an. Es wird empfohlen, die genannten Standardwerte zu verwenden oder die PIN-Länge zu erhöhen bzw. die Timeoutdauer herabzusetzen.
    
    <div>
    

    > [!NOTE]  
    > Ausführliche Informationen finden Sie unter <A href="lync-server-2013-enforce-phone-locking.md">erzwingen der Telefonsperre in lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a>Konfigurieren von Sicherheitseinstellungen für lync Phone Edition Telefone mithilfe von Windows PowerShell-Cmdlets

Sicherheitseinstellungen können mithilfe von lync Server-Verwaltungsshell und dem Cmdlet **Get-CsUCPhoneConfiguration** verwaltet werden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>

## <a name="to-modify-the-sip-security-mode"></a>So ändern Sie den SIP-Sicherheitsmodus

  - Der folgende Befehl legt für die Eigenschaft "SIPSecurityMode" für die globale Auflistung UC-Telefoneinstellungen "Mittel" fest. Die SIP-Sicherheit kann auch auf "Niedrig" oder "Hoch" (den Standardwert) gesetzt werden.
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a>So ändern Sie die minimale PIN-Länge

  - In diesem Beispiel werden alle UC-Telefoneinstellungen so geändert, dass eine minimale PIN-Länge von sieben Ziffern erforderlich ist.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

Ausführliche Informationen finden Sie unter [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Verwalten der lync Server 2013 Authentifizierung](lync-server-2013-managing-lync-server-authentication.md)  


[Verwalten von Geräten, Telefonen und Clientanwendungen in lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

