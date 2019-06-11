---
title: 'Lync Server 2013: Anzeigen von Informationen zur Konfiguration der lync Phone Edition-Einstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View Lync Phone Edition configuration settings information
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49733564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 213b9775b22818c34eb8f7896ea02a4872182a42
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a>Anzeigen von Informationen zu den lync Phone Edition-Konfigurationseinstellungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Sie können Konfigurationsinformationen zu Geräten, auf denen lync Phone Edition ausgeführt wird, anzeigen. Die Informationen sind in Sammlungen gegliedert. Wenn Sie lync Server installieren, erhalten Sie eine Sammlung von lync Phone Edition-Einstellungen, die für alle Geräte gelten, die lync Phone Edition in Ihrer Bereitstellung ausführen. Sie können auch neue Sammlungen von Einstellungen für eine bestimmte Website erstellen. Websiteeinstellungen haben Vorrang vor globalen Einstellungen. Jede Sammlung von Einstellungen besteht aus einem Namen, dem Bereich (Global oder Website), SIP-Sicherheitseinstellung, Protokollierungsstufe, Sprachdienst Qualität (QoS)-Ebene, Festlegung der Telefonsperre und Details der Telefonsperre, also der Mindestlänge der persönlichen Identifikations Sperre Nummer (PIN) und Zeit, bevor sich das Telefon selbst sperrt.

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a>So zeigen Sie Konfigurationsinformationen zu Geräten mit lync Phone Edition an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Gerätekonfiguration** .

4.  Klicken Sie auf der Seite **Device Configuration** auf die Sammlung von Einstellungen, über die Sie Informationen anzeigen möchten. Der Name, der Bereich, die SIP-Sicherheitseinstellung, die sprach Qualitätsstufe und die Einstellung der Telefonsperre sind auf der Hauptseite aufgeführt. Klicken Sie auf das Menü **Bearbeiten** , und klicken Sie dann auf **Details anzeigen**, um die Details für Protokollierungsstufe und Telefonsperre anzuzeigen.

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Informationen zur lync Phone Edition-Konfiguration mithilfe von Windows PowerShell-Cmdlets

Sie können die lync Phone Edition-Konfigurationseinstellungen mithilfe der lync Server-Verwaltungsshell und dem Cmdlet **Get-CsUCPhoneConfiguration** anzeigen. Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a>So zeigen Sie die lync Phone Edition-Konfigurationsinformationen an

  - Wenn Sie Informationen zu allen ihren lync Phone Edition-Konfigurationseinstellungen anzeigen möchten, geben Sie den folgenden Befehl in der lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsUCPhoneConfiguration
    
    Der Befehl gibt Informationen ähnlich der folgenden zurück:
    
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


[Erstellen oder Ändern einer Sammlung von lync Phone Edition-Konfigurationseinstellungen in lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[Löschen einer vorhandenen Sammlung von lync Phone Edition-Konfigurationseinstellungen in lync Server 2013](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Konfigurieren von Sicherheitseinstellungen für lync Phone Edition in lync Server 2013](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Erzwingen der Telefon Sperrung in lync Server 2013](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

