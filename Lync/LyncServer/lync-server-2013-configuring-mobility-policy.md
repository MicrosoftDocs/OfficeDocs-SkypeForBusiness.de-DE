---
title: 'Lync Server 2013: Konfigurieren der Mobilitätsrichtlinie'
TOCTitle: Konfigurieren der Mobilitätsrichtlinie
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh690018(v=OCS.15)
ms:contentKeyID: 49294090
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der Mobilitätsrichtlinie in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-13_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 stellt Mobilitätsrichtlinien bereit, die bestimmen, wer Mobilitätsfeatures und wer die Features "Geschäftlich anrufen", VoIP oder Video verwenden kann, und ob für VoIP oder Video WLAN erforderlich ist. Mit dem Feature "Geschäftlich anrufen" können mobile Benutzer auf einem Mobiltelefon unter der geschäftlichen Telefonnummer anstatt unter der Mobiltelefonnummer Anrufe tätigen und entgegennehmen. Mit diesem Feature wird verhindert, dass der angerufene Gesprächspartner die Mobiltelefonnummer des Anrufers sieht und dass für den Benutzer Gebühren für ausgehende Anrufe anfallen. Das Konfigurieren von VoIP und Video ermöglicht Benutzern das Tätigen und Empfangen von VoIP- und Videoanrufen. Mit den Einstellungen für die WLAN-Verwendung wird festgelegt, ob das Gerät eines Benutzers ein WLAN-Netzwerk statt einer mobilen Datenverbindung nutzen muss.

Standardmäßig sind sowohl das Mobilitätsfeature als auch die Features "Geschäftlich anrufen", VoIP und Video aktiviert. Die Einstellungen, die WLAN für VoIP und Video erfordern sind deaktiviert. Administratoren können durch Ausführen eines Cmdlets bestimmen, wer Zugriff auf diese Features hat. Sie können die Optionen global, nach Standort oder nach Benutzer deaktivieren.

Benutzer müssen die beiden folgenden Voraussetzungen erfüllen, um die Mobilitätsfeatures und das Feature "Geschäftlich anrufen" verwenden zu können:

  - Benutzer müssen für Lync Server 2013 aktiviert sein.

  - Benutzer müssen für Enterprise-VoIP aktiviert sein.

  - Benutzern muss eine Mobilitätsrichtlinie zugewiesen sein, für die die Option **EnableMobility** auf TRUE gesetzt ist.

Zum Verwenden des Features Geschäftlich anrufen müssen Benutzer zudem die beiden folgenden Voraussetzungen erfüllen:

  - Benutzern muss eine VoIP-Richtlinie zugewiesen sein, für die die Option **Gleichzeitiges Klingeln von Telefonen aktivieren** aktiviert ist.

  - Benutzern muss eine Mobilitätsrichtlinie mit der Option **EnableOutsideVoice** und dem Wert "True" zugewiesen werden.


> [!NOTE]
> Benutzer, die nicht für Enterprise-VoIP aktiviert sind, können mithilfe ihres mobilen Geräts VoIP-Anrufe von Lync an Lync tätigen oder an Konferenzen teilnehmen, indem sie auf ihrem mobilen Gerät auf den entsprechenden Link klicken. Hierzu müssen Sie diesen Benutzern die entsprechenden Optionen für die VoIP-Richtlinie zuweisen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-defining-your-mobility-requirements.md">Definieren der Mobilitätsanforderungen für Lync Server 2013</A>.



Ausführliche Informationen zum Aktivieren von Benutzern für Lync Server 2013 finden Sie unter [Aktivieren oder Reaktivieren von Benutzerkonten für Lync Server](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). Ausführliche Informationen zum Aktivieren von Benutzern für Enterprise-VoIP finden Sie unter [Aktivieren von Benutzern für Enterprise-VoIP in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md). Ausführliche Informationen zum Einrichten von VoIP-Richtlinienoptionen finden Sie unter [Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).

## So ändern Sie die globale Mobilitätsrichtlinie

1.  Melden Sie sich an einem Computer, auf dem Lync Server-Verwaltungsshell und Ocscore installiert sind, als Mitglied der Rolle "CsAdministrator" an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Deaktivieren Sie den Zugriff auf die Mobilität und Geschäftlich anrufen global. Geben Sie an der Befehlszeile Folgendes ein:
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    

    > [!NOTE]
    > Sie können auch nur den Zugriff auf das Feature Geschäftlich anrufen deaktivieren, ohne den Zugriff auf die Mobilität zu deaktivieren. Es ist jedoch nicht möglich, den Zugriff auf die Mobilität deaktivieren, ohne auch den Zugriff auf Geschäftlich anrufen zu deaktivieren.



## So ändern Sie die Mobilitätsrichtlinie nach Standort

1.  Melden Sie sich an einem Computer, auf dem Lync Server-Verwaltungsshell und Ocscore installiert sind, als Mitglied der Rolle "CsAdministrator" an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Erstellen Sie eine Richtlinie auf Standortebene, deaktivieren Sie den Zugriff auf VoIP und Video, und aktivieren Sie je nach Standort die Einstellungen, die WLAN für IP-Audio und -Video erfordern. Geben Sie an der Befehlszeile Folgendes ein:
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

## So ändern Sie die Mobilitätsrichtlinie nach Benutzer

1.  Melden Sie sich an einem Computer, auf dem Lync Server-Verwaltungsshell und Ocscore installiert sind, als Mitglied der Rolle "CsAdministrator" an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Erstellen Sie Mobilitätsrichtlinien auf Benutzerebene, und deaktivieren Sie den Zugriff auf die Mobilität und Geschäftlich anrufen nach Benutzer. Geben Sie an der Befehlszeile Folgendes ein:
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    Sie können auch nur den Zugriff auf das Feature Geschäftlich anrufen deaktivieren, ohne den Zugriff auf die Mobilität zu deaktivieren. Es ist jedoch nicht möglich, den Zugriff auf die Mobilität deaktivieren, ohne auch den Zugriff auf Geschäftlich anrufen zu deaktivieren.
    
    Beispiel:
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

## Siehe auch

#### Aufgaben

[Aktivieren oder Reaktivieren von Benutzerkonten für Lync Server](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[Aktivieren von Benutzern für Enterprise-VoIP in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)  
[Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  

#### Konzepte

[Definieren der Mobilitätsanforderungen für Lync Server 2013](lync-server-2013-defining-your-mobility-requirements.md)  

#### Weitere Ressourcen

[New-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMobilityPolicy)  
[Set-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMobilityPolicy)  
[Get-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMobilityPolicy)  
[Grant-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsMobilityPolicy)  
[Remove-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsMobilityPolicy)

