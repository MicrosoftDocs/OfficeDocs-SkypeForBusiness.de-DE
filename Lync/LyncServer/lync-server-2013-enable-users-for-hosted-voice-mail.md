---
title: 'Lync Server 2013: Aktivieren von Benutzern für gehostete Voicemail'
TOCTitle: Aktivieren von Benutzern für gehostete Voicemail
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg413062(v=OCS.15)
ms:contentKeyID: 49295969
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren von Benutzern für gehostete Voicemail in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-24_

Führen Sie die Schritte in diesem Verfahren aus, um Lync Server 2013-Benutzerkonten für Voicemailfunktionen in einem gehosteten Exchange Unified Messaging-Dienst (UM) zu aktivieren.

Ausführliche Informationen finden Sie unter [Benutzerverwaltung für gehostete Exchange-Dienste in Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) in der Planungsdokumentation.

Ausführliche Informationen zur Verwendung des [Set-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsUser)-Cmdlets finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.


> [!IMPORTANT]
> Bevor ein Lync Server 2013-Benutzerkonto für gehostete Voicemail aktiviert werden kann, muss eine Richtlinie für gehostete Voicemail bereitgestellt werden, die auf das entsprechende Benutzerkonto angewendet wird. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-hosted-voice-mail-policies.md">Richtlinien für gehostete Voicemail in Lync Server 2013</A>.



## So aktivieren Sie Benutzer für gehostete Voicemail

1.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

2.  Führen Sie das Cmdlet "Set-CsUser" aus, um das Benutzerkonto für gehostete Voicemail zu konfigurieren. Führen Sie beispielsweise den folgenden Befehl aus:
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    Im oben stehenden Beispiel werden folgende Parameter festgelegt:
    
      - **HostedVoiceMail** ermöglicht das Weiterleiten von Voicemailanrufen eines Benutzers zum gehosteten Exchange UM-Dienst. Dieser Parameter weist Microsoft Lync 2013 außerdem an, die Anzeige "Voicemail anrufen" zu aktivieren.
    
      - **Identity** gibt die Identität des zu ändernden Benutzerkontos an. Der Wert "Identity" kann unter Verwendung eines der folgenden Formate angegeben werden:
        
          - SIP-Adresse des Benutzers
        
          - Active Directory-Benutzerprinzipalname des Benutzers
        
          - Domänenanmeldename des Benutzers (zum Beispiel "contoso\\kenmyer")
        
          - AD DS-Anzeigename des Benutzers (zum Beispiel "Ken Myer"). Wenn der Anzeigename als Identitätswert verwendet wird, können Sie das Sternchen (\*) als Platzhalterzeichen nutzen. Der Identitätswert "\* Smith" gibt beispielsweise alle Benutzer zurück, deren Anzeigename auf den Zeichenfolgenwert "Smith" endet.
        

        > [!NOTE]
        > Der Active Directory-SAM-Kontoname eines Benutzers kann nicht als Identitätswert verwendet werden, da dieser Name innerhalb der Gesamtstruktur nicht unbedingt eindeutig ist.


