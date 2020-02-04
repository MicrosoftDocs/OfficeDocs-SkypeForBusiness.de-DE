---
title: 'Lync Server 2013: Konfigurieren von Pushbenachrichtigungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring for push notifications
ms:assetid: d77f2c06-0fe6-45d5-8f08-808ab871b3e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690047(v=OCS.15)
ms:contentKeyID: 48185574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c34b49d6c968effa46005a01df286d14fcff394c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-for-push-notifications-in-lync-server-2013"></a>Konfigurieren von Pushbenachrichtigungen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-12_

Push-Benachrichtigungen in Form von Signalen, Symbolen oder Benachrichtigungen können auch dann an ein mobiles Gerät gesendet werden, wenn die Mobile Anwendung inaktiv ist. Push-Benachrichtigungen benachrichtigt einen Benutzer über Ereignisse wie eine neue oder verpasste Chat Einladung und Voicemail. Der lync Server 2013-Mobilitätsdienst sendet die Benachrichtigungen an den cloudbasierten lync Server-Push-Benachrichtigungsdienst, der dann die Benachrichtigungen an den Apple Push Notification Service (APNS) sendet (für ein Apple-Gerät, auf dem der lync 2010-Mobilclient ausgeführt wird) oder die Microsoft Push Notification Service (MPNS) (für ein Windows Phone-Gerät, auf dem lync 2010 Mobile oder der lync 2013-Mobilclient ausgeführt wird)

<div>


> [!IMPORTANT]  
> Wenn Sie Windows Phone mit lync 2010 Mobile-oder lync 2013-Mobilclient verwenden, ist eine Push-Benachrichtigung eine wichtige Überlegung.<BR>Wenn Sie lync 2010 Mobile auf Apple-Geräten verwenden, ist eine Push-Benachrichtigung eine wichtige Überlegung.<BR>Wenn Sie lync 2013 Mobile auf Apple-Geräten verwenden, benötigen Sie keine Push-Benachrichtigung mehr.



</div>

Konfigurieren Sie Ihre Topologie so, dass Push-Benachrichtigungen unterstützt werden, indem Sie wie folgt vorgehen:

  - Wenn Ihre Umgebung über einen lync Server 2010-oder lync Server 2013-Edgeserver verfügt, müssen Sie einen neuen Hostinganbieter, Microsoft lync Online, hinzufügen und dann den Anbieter Verbund für den Hostinganbieter zwischen Ihrer Organisation und lync Online einrichten.

  - Wenn Ihre Umgebung über einen Office Communications Server 2007 R2 Edge-Server verfügt, müssen Sie Direct SIP Federation mit Push.lync.com einrichten.
    
    <div>
    

    > [!NOTE]  
    > Push.lync.com ist eine Microsoft Office 365-Domäne für den Push-Benachrichtigungsdienst.

    
    </div>

  - Um Push-Benachrichtigungen zu aktivieren, müssen Sie das Cmdlet " **setCsPushNotificationConfiguration** " ausführen. Pushbenachrichtigungen sind standardmäßig deaktiviert.

  - Testen Sie die Föderations Konfiguration und die Push-Benachrichtigungen.

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a>So konfigurieren Sie für Push-Benachrichtigungen mit lync Server 2013 oder lync Server 2010 Edge-Server

1.  Melden Sie sich bei einem Computer an, auf dem die lync Server-Verwaltungsshell und OCSCore als Mitglied der RtcUniversalServerAdmins-Gruppe installiert sind.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Hinzufügen eines lync Server Online-Hostinganbieter. Geben Sie in der Befehlszeile Folgendes ein:
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    Beispiel:
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > Es ist nicht möglich, mehr als eine Verbundbeziehung mit einem einzelnen Hostinganbieter zu haben. Wenn Sie bereits einen Hostinganbieter eingerichtet haben, der über eine Verbundbeziehung zu sipfed.online.lync.com verfügt, fügen Sie keinen weiteren Hostinganbieter hinzu, auch wenn die Identität des Hostinganbieter etwas anderes als LyncOnline ist.

    
    </div>

4.  Einrichten des Anbieters von Hostinganbieter zwischen Ihrer Organisation und dem Push-Benachrichtigungsdienst bei lync Online Geben Sie in der Befehlszeile Folgendes ein:
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a>So konfigurieren Sie für Push-Benachrichtigungen mit Office Communications Server 2007 R2-Edgeserver

1.  Melden Sie sich beim Edgeserver als Mitglied der RtcUniversalServerAdmins-Gruppe an.

2.  Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **Computer Verwaltung**.

3.  Erweitern Sie in der Konsolenstruktur **Dienste und Anwendungen**, klicken Sie mit der rechten Maustaste auf **Microsoft Office Communications Server 2007 R2**, und klicken Sie dann auf **Eigenschaften**.

4.  Klicken Sie auf der Registerkarte **zulassen** auf **Hinzufügen**.

5.  Führen Sie im Dialogfeld **Federated-Partner hinzufügen** die folgenden Aktionen aus:
    
      - Geben Sie im **Domänennamen des Verbundpartners** **Push.lync.com**ein.
    
      - Geben Sie im **Access-Edgeserver für Federated-Partner** **sipfed.online.lync.com**.
    
      - Klicken Sie auf **OK**.

</div>

<div>

## <a name="to-enable-push-notifications"></a>So aktivieren Sie Push-Benachrichtigungen

1.  Melden Sie sich bei einem Computer an, auf dem die lync Server-Verwaltungsshell und OCSCore als Mitglied der CsAdministrator-Rolle installiert sind.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Aktivieren von Push-Benachrichtigungen Geben Sie in der Befehlszeile Folgendes ein:
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  Föderation aktivieren Geben Sie in der Befehlszeile Folgendes ein:
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a>So testen Sie Föderations-und Push-Benachrichtigungen

1.  Melden Sie sich bei einem Computer an, auf dem die lync Server-Verwaltungsshell und OCSCore als Mitglied der CsAdministrator-Rolle installiert sind.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Testen Sie die Verbund Konfiguration. Geben Sie in der Befehlszeile Folgendes ein:
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    Beispiel:
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  Testen von Push-Benachrichtigungen Geben Sie in der Befehlszeile Folgendes ein:
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    Beispiel:
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

