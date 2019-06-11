---
title: 'Lync Server 2013: Konfigurieren von Sicherheitseinstellungen für lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure security settings for Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521014(v=OCS.15)
ms:contentKeyID: 48184464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7bd44b5d3f466728ac1dbe928c08b1f4786f8fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a>Konfigurieren von Sicherheitseinstellungen für lync Phone Edition in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Verbessern Sie die Sicherheit von Geräten, auf denen lync Phone Edition ausgeführt wird, über Ihre SIP-Sicherheitseinstellung und die Einstellungen für die Telefonsperre.

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a>So konfigurieren Sie die Sicherheitseinstellungen für lync Phone Edition

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf **Gerätekonfiguration**.

4.  Doppelklicken Sie auf der Seite **Device Configuration** in der Liste der Gerätekonfigurationen auf die Konfiguration, für die Sie die Sicherheitseinstellungen ändern möchten.

5.  Geben Sie unter **Gerätekonfiguration bearbeiten**in **SIP-Sicherheit**die SIP-Sicherheitsstufe an. Die Standardstufe ist **hoch**, was wir empfehlen.

6.  Aktivieren oder deaktivieren Sie unter **Gerätekonfiguration bearbeiten**unter **Telefonsperre**das Kontrollkästchen **Gerätesperre erzwingen** (standardmäßig aktiviert), und geben Sie die minimale PIN-Länge (standardmäßig 6 Zeichen) und einen Timeoutzeitraum (standardmäßig 10 Minuten) an. Wir empfehlen, diese Standardeinstellungen zu verwenden oder die PIN-Länge zu erhöhen und/oder den Timeoutzeitraum zu verringern.
    
    <div>
    

    > [!NOTE]  
    > Ausführliche Informationen finden Sie unter <A href="lync-server-2013-enforce-phone-locking.md">erzwingen der Telefon Sperrung in lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a>Konfigurieren von Sicherheitseinstellungen für lync Phone Edition-Telefone mithilfe von Windows PowerShell-Cmdlets

Sicherheitseinstellungen können mithilfe der lync Server-Verwaltungsshell und des Cmdlets **Get-CsUCPhoneConfiguration** verwaltet werden. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-modify-the-sip-security-mode"></a>So ändern Sie den SIP-Sicherheitsmodus

  - Dieser Befehl legt den SIPSecurityMode für die globale Sammlung von UC-Telefoneinstellungen auf Mittel fest. SIP-Sicherheit kann auch auf "Low" oder "hoch" (der Standardwert) festgesetzt werden.
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a>So ändern Sie die minimale PIN-Länge

  - In diesem Beispiel werden alle UC-Telefoneinstellungen so geändert, dass eine minimale PIN-Länge von 7 Ziffern erforderlich ist.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

Ausführliche Informationen finden Sie unter [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Verwalten der lync Server 2013-Authentifizierung](lync-server-2013-managing-lync-server-authentication.md)  


[Verwalten von Geräten, Telefonen und Clientanwendungen in Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

