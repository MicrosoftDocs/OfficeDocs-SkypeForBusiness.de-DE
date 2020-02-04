---
title: 'Lync Server 2013: Anzeigen von Informationen zu Einstellungen für die Push-Benachrichtigung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing information about push notification settings
ms:assetid: be5c6b01-4294-4d17-9772-fed40201e8a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721868(v=OCS.15)
ms:contentKeyID: 49733801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22d79d16980c29907aa4e254d4be7eaee2fcfaae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-information-about-push-notification-settings-in-lync-server-2013"></a>Anzeigen von Informationen zu Einstellungen für die Push-Benachrichtigung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Push-Benachrichtigungen in Form von Signalen, Symbolen oder Benachrichtigungen können auch dann an ein mobiles Gerät gesendet werden, wenn die Mobile Anwendung inaktiv ist. Push-Benachrichtigungen benachrichtigt einen Benutzer über Ereignisse wie eine neue oder verpasste Chat Einladung und Voicemail. Sie können Informationen zu den Push-Benachrichtigungseinstellungen für mobile Geräte anzeigen, indem Sie entweder die lync Server 2013-Systemsteuerung oder die lync Server 2013-Verwaltungsshell verwenden.

<div>

## <a name="to-view-push-notification-information-from-lync-server-control-panel"></a>So zeigen Sie Informationen zur Push-Benachrichtigung in der lync Server-Systemsteuerung an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Schaltfläche Navigations **Benachrichtigungskonfiguration** .

4.  Klicken Sie auf der Seite **Konfiguration der Push-Benachrichtigung** auf die Website, die Sie anzeigen möchten, klicken Sie auf das Menü **Bearbeiten** , und klicken Sie dann auf **Details anzeigen**.

</div>

<div>

## <a name="viewing-push-notification-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Informationen zur Push-Benachrichtigung mithilfe von Windows PowerShell-Cmdlets

Sie können die Konfigurationseinstellungen für die Push-Benachrichtigung mithilfe von Windows PowerShell und dem Cmdlet **Get-CsPushNotificationConfiguration** anzeigen. Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-view-push-notification-configuration-information"></a>So zeigen Sie Informationen zur Push-Benachrichtigungskonfiguration an

  - Wenn Sie Informationen zu allen Ihren Konfigurationseinstellungen für die Push-Benachrichtigung anzeigen möchten, geben Sie den folgenden Befehl in der lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsPushNotificationConfiguration
    
    Es werden etwa folgende Informationen zurückgegeben:
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration) .

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren von Pushbenachrichtigungen in Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

