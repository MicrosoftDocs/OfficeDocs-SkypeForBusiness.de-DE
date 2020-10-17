---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren von Push-Benachrichtigungen für iPhones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling push notifications for iPhones
ms:assetid: 8bbf531a-807f-4a8f-814a-94bfed8f97ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688122(v=OCS.15)
ms:contentKeyID: 49733719
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c942a9f12727a73125809113080a25ddd11a3f5d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515462"
---
# <a name="enabling-or-disabling-push-notifications-for-iphones-in-lync-server-2013"></a>Aktivieren oder Deaktivieren von Push-Benachrichtigungen für iPhones in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Push-Benachrichtigungen in Form von Abzeichen, Symbolen oder Warnungen können an ein iPhone gesendet werden, auch wenn die Mobile Anwendung inaktiv ist. Mit Pushbenachrichtigungen werden Benutzer über Ereignisse informiert, beispielsweise neue oder entgangene Chateinladungen oder Voicemail. Sie können Push-Benachrichtigungen für iPhone aktivieren oder deaktivieren, indem Sie entweder lync Server 2013 Systemsteuerung oder lync Server 2013 Management Shell verwenden.

<div>

## <a name="to-enable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a>So aktivieren Sie Push-Benachrichtigungen für das iPhone mithilfe von lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Pushbenachrichtigungskonfiguration**.

4.  Klicken Sie auf der Seite **Konfiguration der Push-Benachrichtigung** auf die Website, die Sie bearbeiten möchten, klicken Sie auf das Menü **Bearbeiten** , und klicken Sie dann auf **Details anzeigen**.

5.  Aktivieren Sie das Kontrollkästchen **Apple-Pushbenachrichtigungen aktivieren**.

6.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a>So deaktivieren Sie Push-Benachrichtigungen für das iPhone mithilfe von lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Pushbenachrichtigungskonfiguration**.

4.  Klicken Sie auf der Seite **Konfiguration der Push-Benachrichtigung** auf die Website, die Sie bearbeiten möchten, klicken Sie auf das Menü **Bearbeiten** , und klicken Sie dann auf **Details anzeigen**.

5.  Deaktivieren Sie das Kontrollkästchen **Apple-Pushbenachrichtigungen aktivieren**.

6.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-to-iphone-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren von Push-Benachrichtigungen für das iPhone mithilfe von Windows PowerShell-Cmdlets

Push-Benachrichtigungen an Apple iPhone können mithilfe des Cmdlets " **CsPushNotificationConfiguration** " aktiviert oder deaktiviert werden. Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-enable-push-notifications-for-iphone"></a>So aktivieren Sie Push-Benachrichtigungen für das iPhone

  - So aktivieren Sie Push-Benachrichtigungen für iPhone legen Sie den Wert der EnableApplePushNotificationService-Eigenschaft auf true ($true) fest. Zum Beispiel:
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone"></a>So deaktivieren Sie Push-Benachrichtigungen für das iPhone

  - So deaktivieren Sie Push-Benachrichtigungen für iPhone legen Sie den Wert der EnableApplePushNotificationService-Eigenschaft auf false ($false) fest. Zum Beispiel:
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False

</div>

Weitere Informationen dazu finden Sie im Hilfethema für das Cmdlet [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren von Push-Benachrichtigungen in lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

