---
title: 'Lync Server 2013: Konfigurieren von Pushbenachrichtigungen'
TOCTitle: Konfigurieren von Pushbenachrichtigungen
ms:assetid: d77f2c06-0fe6-45d5-8f08-808ab871b3e0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh690047(v=OCS.15)
ms:contentKeyID: 49295561
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Pushbenachrichtigungen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-12_

Pushbenachrichtigungen in Form von Signalen, Symbolen oder Warnungen können an ein mobiles Gerät gesendet werden, auch wenn die mobile Anwendung inaktiv ist. Mit Pushbenachrichtigungen werden Benutzer über Ereignisse informiert, beispielsweise über neue oder entgangene Chateinladungen und Voicemail. Der Lync Server 2013-Mobilitätsdienst sendet Benachrichtigungen an den cloudbasierten Lync Server-Pushbenachrichtigungsdienst, der die Benachrichtigungen dann an den Apple-Pushbenachrichtigungsdienst (APNS) (für ein Apple-Gerät, auf dem der Lync 2010 Mobile-Client ausgeführt wird) oder an den Microsoft-Pushbenachrichtigungsdienst (MPNS) sendet (für ein Windows Phone, auf dem Lync 2010 Mobile oder der mobile Lync 2013-Client ausgeführt wird).


> [!IMPORTANT]
> Wenn Sie das Windows Phone mit Lync 2010 Mobile oder dem mobilen Lync 2013-Client verwenden, sind Pushbenachrichtigungen eine wichtige Überlegung.<BR>Wenn Sie Lync 2010 Mobile auf Apple-Geräten verwenden, sind Pushbenachrichtigungen eine wichtige Überlegung.<BR>Wenn Sie Lync 2013 Mobile auf Apple-Geräten verwenden, benötigen Sie keine Pushbenachrichtigungen mehr.



Gehen Sie wie folgt vor, um die Topologie zur Unterstützung von Pushbenachrichtigungen zu konfigurieren:

  - Wenn Ihre Umgebung einen Lync Server 2010- oder Lync Server 2013- Edgeserver enthält, müssen Sie einen neuen Hostinganbieter, Microsoft Lync Online, hinzufügen und dann den Hostinganbieter-Partnerverbund zwischen Ihrer Organisation und Lync Online einrichten.

  - Wenn Ihre Umgebung einen Office Communications Server 2007 R2Edgeserver enthält, müssen Sie einen direkten SIP-Partnerverbund mit "push.lync.com" einrichten.
    

    > [!NOTE]
    > Push.lync.com ist eine Microsoft Office&nbsp;365-Domäne für den Pushbenachrichtigungsdienst.



  - Zur Aktivierung von Pushbenachrichtigungen müssen Sie das **Set-CsPushNotificationConfiguration**-Cmdlet ausführen. Pushbenachrichtigungen sind standardmäßig deaktiviert.

  - Testen Sie die Partnerverbundkonfiguration und die Pushbenachrichtigungen.

## So konfigurieren Sie die Unterstützung von Pushbenachrichtigungen mit einem Lync Server 2013- oder Lync Server 2010- Edgeserver

1.  Melden Sie sich an einem Computer, auf dem Lync Server-Verwaltungsshell und Ocscore installiert sind, als Mitglied der Gruppe "RtcUniversalServerAdmins" an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Fügen Sie einen Lync Server-Onlinehostinganbieter hinzu. Geben Sie an der Befehlszeile Folgendes ein:
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    Beispiel:
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    

    > [!NOTE]
    > Es kann nur maximal eine Partnerverbundbeziehung mit einem einzelnen Hostinganbieter bestehen. Wenn Sie also bereits einen Hostinganbieter eingerichtet haben, der eine Partnerverbundbeziehung mit "sipfed.online.lync.com" hat, fügen Sie keinen weiteren Hostinganbieter hinzu, auch wenn die Identität des Hostinganbieters nicht "LyncOnline" ist.



4.  Einrichten eines Hostinganbieter-Partnerverbunds zwischen Ihrer Organisation und dem Pushbenachrichtigungsdienst bei Lync Online. Geben Sie an der Befehlszeile Folgendes ein:
    
        New-CsAllowedDomain -Identity "push.lync.com"

## So konfigurieren Sie die Unterstützung von Pushbenachrichtigungen mit einem Office Communications Server 2007 R2- Edgeserver

1.  Melden Sie sich am Edgeserver als Mitglied der Gruppe "RtcUniversalServerAdmins" an.

2.  Klicken Sie nacheinander auf **Start** , **Alle Programme** , **Verwaltung** und **Computerverwaltung** .

3.  Erweitern Sie in der Konsolenstruktur **Dienste und Anwendungen** , klicken Sie mit der rechten Maustaste auf **Microsoft Office Communications Server 2007 R2** , und klicken Sie dann auf **Eigenschaften** .

4.  Klicken Sie auf der Registerkarte **Zulassen** auf **Hinzufügen** .

5.  Gehen Sie im Dialogfeld **Verbundpartner hinzufügen** wie folgt vor:
    
      - Geben Sie im Feld **Domänenname des Verbundpartners** den Namen **push.lync.com** ein.
    
      - Geben Sie **sipfed.online.lync.com** im Feld **Zugriffs-Edgeserver des Verbundpartners** ein.
    
      - Klicken Sie auf **OK** .

## So aktivieren Sie Pushbenachrichtigungen

1.  Melden Sie sich an einem Computer, auf dem Lync Server-Verwaltungsshell und Ocscore installiert sind, als Mitglied der Rolle "CsAdministrator" an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Aktivieren Sie Pushbenachrichtigungen. Geben Sie an der Befehlszeile Folgendes ein:
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  Aktivieren Sie den Partnerverbund. Geben Sie an der Befehlszeile Folgendes ein:
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

## So testen Sie den Partnerverbund und die Pushbenachrichtigungen

1.  Melden Sie sich an einem Computer, auf dem Lync Server-Verwaltungsshell und Ocscore installiert sind, als Mitglied der Rolle "CsAdministrator" an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Testen Sie die Partnerverbundkonfiguration. Geben Sie an der Befehlszeile Folgendes ein:
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    Beispiel:
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  Testen Sie die Pushbenachrichtigungen. Geben Sie an der Befehlszeile Folgendes ein:
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    Beispiel:
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

## Siehe auch

#### Weitere Ressourcen

[Test-CsFederatedPartner](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsFederatedPartner)  
[Test-CsMcxPushNotification](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsMcxPushNotification)

