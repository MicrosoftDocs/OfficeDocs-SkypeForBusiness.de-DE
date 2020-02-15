---
title: 'Lync Server 2013: Informationen zur lync Phone Edition-Konfigurationseinstellungen anzeigen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Lync Phone Edition configuration settings information
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49733564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 509bc25e6466e4e6f90271645b2a3a8ff271bd84
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a>Anzeigen von Informationen zu lync Phone Edition Konfigurationseinstellungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Sie können Konfigurationsinformationen zu Geräten anzeigen, auf denen lync Phone Edition ausführt. Die Informationen sind in Auflistungen angeordnet. Wenn Sie lync Server installieren, erhalten Sie eine Sammlung von lync Phone Edition-Einstellungen, die für alle Geräte gelten, auf denen lync Phone Edition in Ihrer Bereitstellung ausführt. Sie können auch neuen Auflistungen von Einstellungen für einen bestimmten Standort erstellen. Standorteinstellungen haben Vorrang vor globalen Einstellungen. Jede Auflistung von Einstellungen besteht aus einem Namen, dem Bereich (global oder Standort), der SIP-Sicherheitseinstellung, dem Protokolliergrad, der VoIP-Dienstqualitätsebene, der Telefonsperreinstellung und Details zur Telefonsperre, d. h., die Mindestlänge der PIN zum Entsperren und die Zeit bis zur Sperrung des Telefons.

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a>So zeigen Sie Konfigurationsinformationen zu Geräten an, auf denen lync Phone Edition

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf die Navigationsschaltfläche **Gerätekonfiguration**.

4.  Klicken Sie auf der Seite **Gerätekonfiguration** auf die Auflistung von Einstellungen, zu der Sie Informationen anzeigen möchten. Der Name, der Bereich, die SIP-Sicherheitseinstellung, die VoIP-Qualitätsebene und die Telefonsperreinstellung werden auf der Hauptseite aufgeführt. Zum Anzeigen des Protokolliergrads und der Details zur Telefonsperre klicken Sie auf das Menü **Bearbeiten** und dann auf **Details anzeigen**.

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von lync Phone Edition-Konfigurationsinformationen mithilfe von Windows PowerShell-Cmdlets

Sie können lync Phone Edition-Konfigurationseinstellungen mithilfe von lync Server-Verwaltungsshell und dem Cmdlet **Get-CsUCPhoneConfiguration** anzeigen. Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a>So zeigen Sie lync Phone Edition-Konfigurationsinformationen an

  - Wenn Sie Informationen zu allen lync Phone Edition-Konfigurationseinstellungen anzeigen möchten, geben Sie den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsUCPhoneConfiguration
    
    Der Befehl gibt ähnliche Informationen wie die Folgenden zurück:
    
        Identity             : Global
        CalendarPollInterval : 00:03:00
        EnforcePhoneLock     : True
        PhoneLockTimeout     : 00:10:00
        MinPhonePinLength    : 6
        SIPSecurityMode      : High
        VoiceDiffServTag     : 40
        Voice8021p           : 0
        LoggingLevel         : Off

</div>

Ausführliche Informationen finden Sie unter [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen oder Ändern einer Sammlung von lync Phone Edition Konfigurationseinstellungen in lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[Löschen einer vorhandenen Sammlung von lync Phone Edition Konfigurationseinstellungen in lync Server 2013](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Konfigurieren von Sicherheitseinstellungen für lync Phone Edition in lync Server 2013](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Erzwingen der Telefonsperre in lync Server 2013](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

