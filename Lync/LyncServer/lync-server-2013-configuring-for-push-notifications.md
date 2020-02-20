---
title: 'Lync Server 2013: Konfigurieren von Push-Benachrichtigungen'
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
ms.openlocfilehash: 50b2cc9facfc93868abeb85ca02e8cb17a6803a9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151435"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-for-push-notifications-in-lync-server-2013"></a>Konfigurieren von Push-Benachrichtigungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-12_

Pushbenachrichtigungen in Form von Signalen, Symbolen oder Warnungen können an ein mobiles Gerät gesendet werden, auch wenn die mobile Anwendung inaktiv ist. Mit Pushbenachrichtigungen werden Benutzer über Ereignisse informiert, beispielsweise neue oder entgangene Chateinladungen oder Voicemail. Der lync Server 2013 Mobilitätsdienst sendet die Benachrichtigungen an den cloudbasierten lync Server Push-Benachrichtigungsdienst, der dann die Benachrichtigungen an den Apple Push Notification Service (APNS) (für ein Apple-Gerät, das den lync 2010 Mobile Client ausführt) oder den Microsoft Push Notification Service (MPNS) (für ein Windows Phone Gerät, auf dem die lync 2010 Mobile oder der lync 2013 Mobile Client) läuft.

<div>


> [!IMPORTANT]  
> Wenn Sie Windows Phone mit lync 2010 Mobile oder lync 2013 mobilen Clients verwenden, ist die Push-Benachrichtigung eine wichtige Überlegung.<BR>Wenn Sie lync 2010 Mobile auf Apple-Geräten verwenden, ist die Push-Benachrichtigung eine wichtige Überlegung.<BR>Wenn Sie lync 2013 Mobile auf Apple-Geräten verwenden, benötigen Sie keine Push-Benachrichtigungen mehr.



</div>

Gehen Sie wie folgt vor, um die Topologie zur Unterstützung von Pushbenachrichtigungen zu konfigurieren:

  - Wenn Ihre Umgebung über eine lync Server 2010 oder lync Server 2013 Edgeserver verfügt, müssen Sie einen neuen Hostinganbieter, Microsoft lync Online, hinzufügen und dann den Anbieter Verbund für den Hostinganbieter zwischen Ihrer Organisation und lync Online einrichten.

  - Wenn Ihre Umgebung über eine Office Communications Server 2007 R2 Edgeserver verfügt, müssen Sie den direkten SIP-Partnerverbund mit Push.lync.com einrichten.
    
    <div>
    

    > [!NOTE]  
    > Push.lync.com ist eine Microsoft Office 365-Domäne für den Pushbenachrichtigungsdienst.

    
    </div>

  - Zur Aktivierung von Pushbenachrichtigungen müssen Sie das **Set-CsPushNotificationConfiguration**-Cmdlet ausführen. Pushbenachrichtigungen sind standardmäßig deaktiviert.

  - Testen Sie die Partnerverbundkonfiguration und die Pushbenachrichtigungen.

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a>So konfigurieren Sie Push-Benachrichtigungen mit lync Server 2013 oder lync Server 2010 Edgeserver

1.  Melden Sie sich an einem Computer an, auf dem lync Server-Verwaltungsshell und OCSCore als Mitglied der RtcUniversalServerAdmins-Gruppe installiert sind.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Fügen Sie einen lync Server Online Hosting-Anbieter hinzu. Geben Sie in die Befehlszeile Folgendes ein:
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    Zum Beispiel:
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > Es kann nur maximal eine Partnerverbundbeziehung mit einem einzelnen Hostinganbieter bestehen. Wenn Sie also bereits einen Hostinganbieter eingerichtet haben, der eine Partnerverbundbeziehung mit "sipfed.online.lync.com" hat, fügen Sie keinen weiteren Hostinganbieter hinzu, auch wenn die Identität des Hostinganbieters nicht "LyncOnline" ist.

    
    </div>

4.  Einrichten eines Hostinganbieter-Partnerverbunds zwischen Ihrer Organisation und dem Pushbenachrichtigungsdienst bei Lync Online. Geben Sie an der Befehlszeile Folgendes ein:
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a>So konfigurieren Sie für Push-Benachrichtigungen mit Office Communications Server 2007 R2 Edgeserver

1.  Melden Sie sich beim Edgeserver als Mitglied der RtcUniversalServerAdmins-Gruppe an.

2.  Klicken Sie nacheinander auf **Start**, **Alle Programme**, **Verwaltung** und **Computerverwaltung**.

3.  Erweitern Sie in der Konsolenstruktur **Dienste und Anwendungen**, klicken Sie mit der rechten Maustaste auf **Microsoft Office Communications Server 2007 R2**, und klicken Sie dann auf **Eigenschaften**.

4.  Klicken Sie auf der Registerkarte **Zulassen** auf **Hinzufügen**.

5.  Gehen Sie im Dialogfeld **Verbundpartner hinzufügen** wie folgt vor:
    
      - Geben Sie im Feld **Domänenname des Verbundpartners** den Namen **push.lync.com** ein.
    
      - Geben Sie **sipfed.online.lync.com** im Feld **Zugriffs-Edgeserver des Verbundpartners** ein.
    
      - Klicken Sie auf **OK**.

</div>

<div>

## <a name="to-enable-push-notifications"></a>So aktivieren Sie Pushbenachrichtigungen

1.  Melden Sie sich an einem Computer an, auf dem lync Server-Verwaltungsshell und OCSCore als Mitglied der CsAdministrator-Rolle installiert sind.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Aktivieren Sie Pushbenachrichtigungen. Geben Sie an der Befehlszeile Folgendes ein:
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  Aktivieren Sie den Partnerverbund. Geben Sie an der Befehlszeile Folgendes ein:
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a>So testen Sie den Partnerverbund und die Pushbenachrichtigungen

1.  Melden Sie sich an einem Computer an, auf dem lync Server-Verwaltungsshell und OCSCore als Mitglied der CsAdministrator-Rolle installiert sind.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Testen Sie die Partnerverbundkonfiguration. Geben Sie an der Befehlszeile Folgendes ein:
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    Beispiel:
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  Testen Sie die Pushbenachrichtigungen. Geben Sie an der Befehlszeile Folgendes ein:
    
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

