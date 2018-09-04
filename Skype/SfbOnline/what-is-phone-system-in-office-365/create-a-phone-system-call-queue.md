---
title: Erstellen einer Telefonsystem-Anrufwarteschleife
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: 'Erfahren Sie, wie Sie Telefonsysteme für Office 365 (Cloud PBX) Anrufwarteschleifen mit einer Begrüßung der Organisation und der Weiterleitung von Anrufen an Telefonisten in Verteilersystem und Sicherheitsgruppen einrichten. Optionen für maximale Warteschleifenengröße, Zeitüberschreitung und Anrufbearbeitung können ebenfalls festgelegt werden. '
ms.openlocfilehash: 5a3ace77542a86aea1dd77e1ddcf594f61abb738
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780423"
---
# <a name="create-a-phone-system-call-queue"></a>Erstellen einer Telefonsystem-Anrufwarteschleife

Telefonsystem-Anrufwarteschleifen beinhalten die beim Wählen einer Telefonnummer Ihrer Organisation verwendeten Begrüßungen, die Option, den Anruf automatisch zu halten und die Option, nach dem nächsten verfügbaren Telefonisten zu suchen, der den Anruf entgegen nimmt. Die Anrufer hören während dieser Zeit Musik. Sie können eine einzelne oder mehrere Anrufwarteschleifen für Ihre Organisation einrichten.
  
Telefonsystem-Anrufwarteschleifen bieten:
  
- Eine Begrüßung der Organisation
    
- Musik, während die wartenden Anrufer gehalten werden
    
- Umleitung von Anrufen an Telefonisten in E-Mail-aktivierten Verteilerlisten und Sicherheitsgruppen.
    
- Erstellen von Einstellungen für die max. Größe von Anrufwarteschleifen, für Zeitüberschreitungen und für Anrufbehandlungsoptionen.
    
Personen, die eine Telefonnummer anrufen, für die eine Anrufwarteschleife eingerichtet ist, hören zuerst eine Begrüßung (sofern eine solche eingerichtet ist). Anschließend werden sie in die Warteschleife eingereiht und warten auf den nächsten verfügbaren Telefonisten. Während die wartenden Anrufer gehalten werden, hören sie Musik. Die Anrufe werden den Telefonisten nach dem  *FIFO*-Prinzip (First In, First Out) angeboten.
  
Alle in der Warteschleife wartenden Anrufe werden in einem Weiterleitungsmodus an die Telefonzentralen verteilt:
  
- Mit Teilnehmer-Routing (attendant routing) wird der erste Aufruf in der Warteschleife alle Telefonisten gleichzeitig anrufen.
    
- Mit seriellem Routing (serial routing) wird der erste Aufruf in der Warteschleife alle Telefonisten nacheinander anrufen.
    
    > [!NOTE]
    > Telefonisten, die **Offline**sind, ihre Anwesenheit auf **Nicht stören** festgelegt haben, oder haben sich von der Warteschleife abgemeldet haben, werden nicht angerufen.
  
- Es wird nur jeweils eine Benachrichtigung über einen eingehenden Anruf (für den ersten Anruf in der Warteschleife) an die Telefonisten gesendet.
    
- Wenn ein Telefonist den Anruf angenommen hat, klingelt der nächste eingehende Anruf aus der Warteschleife bei den Telefonisten.
    
## <a name="step-1---getting-started"></a>Schritt 1 - Erste Schritte

Die folgenden Punkte sind zu bedenken, wenn Sie beginnen, Anrufwarteschleifen zu verwenden:
  
- Ihre Organisation benötigt (mindestens) eine Enterprise E3 plus **Telefonsystem**-Lizenz oder eine E5 Enterprise-Lizenz. Die Anzahl der zugewiesenen **Telefonsystem**-Benutzerlizenzen beeinflusst die Anzahl der Servicenummern, die zur Verwendung für Anrufwarteschleifen verfügbar sind. Die Anzahl der Anrufwarteschleifen, die Ihnen zur Verfügung gestellt werden, ist abhängig von der Anzahl der **Telefonsystem**- und **Audiokonferenz**-Lizenzen, die in Ihrer Organisation zugewiesen sind. Weitere Informationen zu Lizenzierung finden Sie [hier](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!NOTE]
    > Zum Umleiten von Anrufen an Personen in Ihrer Organisation, die Online sind, benötigen diese eine **Telefonsystem**-Lizenz und müssen entweder für Enterprise Voice aktiviert sein oder einen Office 365 Anrufplan besitzen. Siehe [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Um diese Lizenzen für Enterprise-VoIP zu aktivieren, können Sie die Windows PowerShell verwenden. Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Weitere Informationen zu Office 365 Anrufplänen finden Sie unter [Was sind Anrufpläne in Office 365?](/microsoftteams/what-are-calling-plans-in-office-365) und [Anrufpläne für Office 365](/microsoftteams/calling-plans-for-office-365).
    
    > [!NOTE]
    > Benutzer, die mit Lync Server 2010 lokal gehostet werden, werden nicht als Telefonisten für Anrufwarteschleifen unterstützt. 
  
- Nur gebührenpflichtige oder gebührenfreie Servicenummern, die Ihnen im**Skype for Business Administrationscenter** zur Verfügung stehen oder die ein anderer Anbieter an Sie übertragen hat, können an Telefonsystem-Anrufwarteschleifen zugewiesen werden. Um gebührenfreie Servicenummern zu erhalten müssen Sie Communication Credits einrichten.
    
    > [!NOTE]
    > Telefonnummern von Benutzern (Abonnenten) können Anrufwarteschleifen nicht zugewiesen werden - es können nur gebührenpflichtige oder gebührenfreie Telefonnummern verwendet werden. 
  
- Wenn Sie eingehende Anrufe von einer Telefonsystem-Anrufwarteschleife verteilen, werden diese Clients für Telefonisten unterstützt:
    
  - Desktopclient von Skype for Business 2016 (32- und 64-Bit-Version)
    
  - Desktopclient von Lync 2013 (32- und 64-Bit-Version)
    
  - Alle IP-Telefon-Modelle für Skype for Business Online werden unterstützt. Sehen Sie auch [Telefonsystem für Skype for Business Online einrichten](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).
    
  - Mac Skype for Business-Client (Version 16.8.196 und höher) 
    
  - Android Skype for Business-Client (Version 6.16.0.9 und höher)
    
  - iPhone Skype for Business-Client (Version 6.16.0 und höher)
    
  - Mac Skype for Business-Client (Version 6.16.0 und höher)

  - Microsoft Teams Windows-Client (32- und 64-Bit-Versionen)

  - Microsoft Teams Mac-Client

  - Microsoft Teams, iPhone-Anwendung

  - Microsoft Teams, Android-Anwendung
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Schritt 2 - Beziehen oder Übertragen von gebührenpflichtigen oder gebührenfreien Servicenummern

Bevor Sie Ihre Anrufwarteschleifen erstellen und einrichten können, müssen Sie Ihre bestehenden kostenpflichtigen oder gebührenfreien Servicenummern einrichten oder übertragen. Nachdem Sie die gebührenfreien Service-Telefonnummern erhalten haben, werden diese in **Skype for Business Admin Center** > **Voice** > **Telefonnummern** angezeigt, und der **Nummerntyp** wird als **Service - gebührenfrei** aufgelistet. Um Ihre Servicerufnummern zu erhalten, sehen Sie [Servicerufnummern für Skype for Business und Microsoft Teams](getting-service-phone-numbers.md), oder, falls Sie eine bestehende Servicerufnummer übertragen möchten, sehen Sie[Rufnummern zu Office 365 übertragen](/microsoftteams/transfer-phone-numbers-to-office-365).
  
> [!NOTE]
> Wenn Sie sich außerhalb der USA befinden, können Sie Servicenummern nicht über das Skype for Business Admin Center beziehen. Lesen Sie stattdessen unter [Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization) nach, wie Sie außerhalb der USA vorgehen müssen.
  
## <a name="step-3---create-a-new-call-queue"></a>Schritt 3 - Erstellen einer neuen Anrufwarteschleife

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Nutzung des Skype for Business Admin Centers**

Klicken Sie im **Skype for Business Admin Center** auf **Anrufweiterleitungs/** > **Anrufwarteschleifen** und dann auf **Neu hinzufügen**:
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>Festlegen des Anzeigenamens, der Telefonnummer und gegebenenfalls der Domäne für die Anrufwarteschleife

![Einrichten einer Anrufwarteschleife.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![Nummer 1](../images/sfbcallout1.png)<br/>
**Name**: Geben Sie einen aussagekräftigen Anzeigenamen für die Anrufwarteschleife ein. Der Name ist erforderlich und kann maximal 64 Zeichen einschließlich Leerzeichen enthalten. <br/> Dieser Name wird in der Benachrichtigung über den eingehenden Anruf angezeigt.
***
![Nummer 2](../images/sfbcallout2.png)<br/>**Telefonnummer** Wählen Sie eine gebührenpflichtige oder gebührenfreie Servicenummer für die Anrufwarteschleife aus. Dies ist optional. <br/> Wenn keine Servicenummern aufgelistet sind, müssen Sie sich diese besorgen, damit Sie diese Anrufwarteschleife erstellen können. Um Ihre Servicenummern zu erhalten sehen Sie [Einrichten von Servicenummern für Skype for Business und Microsoft Teams](getting-service-phone-numbers.md)
***
![Nummer 3](../images/sfbcallout3.png)<br/>**Domäne**: Wenn diese Option verfügbar ist, wählen Sie die Office 365-Domäne aus, die Sie verwenden möchten. Diese Option ist nur verfügbar, wenn Sie mehrere Domänen für Office 365 verwenden. Wenn mehrere Domänen vorhanden sind, müssen Sie den Domänennamen in der Liste auswählen. <br/> Ihre Domäne könnte beispielsweise so heißen:  _contoso.com or redmond.contoso.com_
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Festlegen der Begrüßung und der Wartemusik, die wiedergegeben werden soll

![Einrichten einer Anrufwarteschleife.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/>**Begrüßung** ist optional. Dabei handelt es sich um die Musik, die für Anrufer wiedergegeben wird, die sich in der Anrufwarteschleife befinden. <br/> Sie können eine Audiodatei (im WAV-, MP3- oder WMA-Format) hochladen.
***
![Nummer 2](../images/sfbcallout2.png)<br/>**Wartemusik**: Sie können die Standardwartemusik verwenden, die für die Anrufwarteschleife bereitgestellt wird, oder Sie können eine Audiodatei im WAV-, MP3- oder WMA-Format hochladen und diese als benutzerdefinierte Wartemusik verwenden. 
   

### <a name="select-the-call-distribution-method"></a>Wählen Sie die Anruf-Verteilungsmethode

![Zeigt die Optionen für Anruf-Verteilungsmethoden an](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/>**Anruf-Verteilungsmethode** Sie können für Ihre Anrufwarteschleife die Verteilungsmethoden **Teilnehmer (attendant)** oder **Serielle (serial)** auswählen. Alle neuen und vorhandenen Anrufwarteschleifen sind standardmäßig auf Teilnehmer-Routing (attendant routing) eingestellt. Wenn Sie serielles Routing (serial routing) verwenden möchten, müssen Sie explizit die **serielles** Routing-Option in der Benutzeroberfläche und Cmdlets auswählen. <br/><br/> Wenn serielles Routing ausgewählt und die Anrufwarteschleife gespeichert wird, werden Ihre Telefonisten nacheiner angerufen, wobei mit dem ersten Telefonisten auf der Telefonisten-Liste begonnen wird. Wenn ein Telefonist einen Anruf ablehnt oder nicht annimmt, wird der nächste Telefonist auf der Liste angerufen und ein Telefonist nach dem anderen versucht, bis der Anruf angenommen wird oder die maximale Zeit in der Warteschleife erreicht hat.   

> [!NOTE]
> Serielles Routing überspringt Telefonisten, die **Offline** sind, ihren Anwesenheitsstatus auf **Nicht stören**festgelegt haben oder sich von Anrufen aus dieser Anrufwarteschleife**abgemeldet haben**. 
   
### <a name="select-an-agent-opt-out-option"></a>Wählen Sie eine Option für das Abmelden von Telefonisten

![Zeigt das Abmeldungs-Kontrollkästchen des Telefonisten](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/>**Option Abmeldung für Telefonisten** Sie können es Telefonisten erlauben, sich von Anrufen von einer bestimmten Anrufwarteschleife abzumelden, indem Sie die **Option Abmeldung für Telefonisten** auswählen.  <br/> Durch die Aktivierung dieser Option wird es allen Telefonisten in dieser Anrufwarteschleife ermöglicht, sich nach Wunsch vom Erhalt von Anrufen aus dieser Warteschleife abzumelden. Sie können das die Möglichkeit, sich von Anrufen abzumelden, durch Deaktivieren des Kontrollkästchens jederzeit sperren, wodurch Telefonisten automatisch wieder für diese Anrufwarteschleife angemeldet werden (die Standardeinstellung für alle Telefonisten).  <br/><br/> Um auf die Abmeldungsfunktion zuzugreifen können Telefonisten folgendes tun:
 1. Öffnen Sie **Optionen** in Skype for Business-Client auf ihrem Desktop. 
 2. Klicken Sie in der Registerkarte **Anrufweiterleitung** auf den Link **Online-Einstellungen bearbeiten**.
 3. Klicken Sie auf der Einstellungsseite für Benutzer auf **Anrufwarteschleifen** und deaktivieren Sie die Kontrollkästchen für alle Warteschleifen, von denen sie sich abmelden möchten.
 
    > [!NOTE] 
    > Mithilfe der Mac-, Mobile oder Lync 2013-Clients oder Hybrid-VoIP-Benutzern, die lokal auf einem Skype for Business 2015 Server gehostet werden, können Telefonisten die Abmeldungsoption über [https://aka.ms/cqsettings](https://aka.ms/cqsettings) aufrufen.
   
### <a name="add-call-agents-to-a-call-queue"></a>Hinzufügen von Telefonisten zu einer Anrufwarteschleife

![Anrufwarteschleifen einrichten.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/><br/>Telefonisten (maximal 50) können sein:
*    Ein Online-Benutzer mit einer **Telefonsystem**-Lizenz und Enterprise Voice oder einem Anrufplan. <br/><br/> **Hinweis:** Zum Umleiten von Anrufen an Personen in Ihrer Organisation, die Online sind, benötigen diese eine **Telefonsystem**-Lizenz und müssen entweder für Enterprise Voice aktiviert sein oder einen Anrufplan besitzen. Siehe [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Um diese Lizenzen für Enterprise-VoIP zu aktivieren, können Sie die Windows PowerShell verwenden. Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
*    Online-Benutzer mit einer **Telefonsystem**-Lizenz und einem Anrufplan, die einer Office 365-Gruppe, einer e-Mail-Verteilerliste oder einer Sicherheitsgruppe hinzugefügt worden sind. Es kann bis zu 30 Minuten dauern, bis ein neuer Telefonist zu einer Verteilerliste oder Sicherheitsgruppe hinzugefügt wird und Anrufe aus einer Anrufwarteschleife empfangen kann. Es kann bis zu 48 Stunden dauern, bis eine neu erstellte Verteilerliste oder Sicherheitsgruppe zur Verwendung mit Anrufwarteschleifen zur Verfügung steht. Neu erstellte Office 365-Gruppen sind fast sofort verfügbar. <br/> 

    > [!NOTE] 
    > Benutzer, die mit Lync Server 2010 lokal gehostet werden, werden nicht unterstützt.           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>Festlegen der maximalen Warteschleifengröße und der maximalen Wartezeit

![Eine Anrufwarteschleife einrichten.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/><br/>**Maximale Anrufe in der Warteschlange**: Legen Sie mit dieser Option fest, wie lange Anrufe maximal in der Warteschleife warten können, bis es zu einem Timeout kommt. Der Standardwert ist 50, aber kann im Bereich von 0 bis 200 liegen. Wenn dieser Grenzwert erreicht ist, wird der Anruf so behandelt, wie Sie es  **Wenn die maximale Anzahl von Anrufen erreicht ist** eingestellt haben.
***
![Nummer 2](../images/sfbcallout2.png)<br/><br/>**Wenn die maximale Anzahl von Anrufen erreicht ist**: Wenn die maximale Größe der Warteschleife erreicht ist (die Sie mit der Einstellung **Maximale Anrufe in der Warteschlange** festgelegt haben), können Sie auswählen, was mit neuen eingehenden Anrufen geschehen soll.
*    **Mit Besetztzeichen trennen**: Der Anruf wird getrennt.
*    **Weiterleiten an**: Wenn Sie diese Einstellung auswählen, haben Sie die folgenden Optionen:
     *    **Person in Ihrem Unternehmen** Ein Online-Benutzer mit einer**Telefonsystem**-Lizenz, für den Enterprise Voice aktiviert ist oder der einen Anrufplan hat. Sie können einrichten, dass Anrufer an die Voicemail geleitet werden. Dazu wählen Sie eine **Person in Ihrem Unternehmen** aus, deren Anrufe dann direkt an die Voicemail weitergeleitet werden. <br/> <br/>Informationen zur erforderlichen Lizenzierung für Voicemail finden Sie unter [Einrichten von Telefonsystem-Voicemail](/microsoftteams/set-up-phone-system-voicemail). 
     
        > [!Note]
        > Benutzer, die mit Lync Server 2010 lokal gehostet werden, werden nicht unterstützt.<br/>
     
     *    **Anrufwarteschleife**: Sie müssen zuvor eine weitere Anrufwarteschleife eingerichtet haben, die Sie dann hier auswählen können.
     *    **Automatische Telefonzentrale**: Sie müssen zurvor eine automatische Telefonzentrale eingerichtet haben, die Sie dann hier auswählen können. Sehen Sie [Einrichten einer automatischen Telefonzentrale für das Telefonsystem](set-up-a-phone-system-auto-attendant.md).
***
![Nummer 3](../images/sfbcallout3.png)<br/><br/>**Wie lange ein Anruf in der Warteschlange warten kann**: Sie können auch entscheiden, wie lange ein Anruf in der Warteschleife gehalten werden kann, bis es zu einem Timeout kommt und der Anruf umgeleitet werden muss. Wohin der Anruf umgeleitet wird, hängt von Ihrer Einstellung für **Wenn das Zeitlimit eines Anrufs überschritten ist** ab. Sie können eine Dauer von 0 bis 45 Minuten festlegen. <br/><br/> Der Timeoutwert kann in Sekunden in Intervallen von 15 Sekunden festgelegt werden. Dadurch können Sie den Anruffluss mit feinerer Granularität bearbeiten. Beispielsweise könnten Sie angeben, dass alle Anrufe, die nicht innerhalb von 30 Sekunden von einem Telefonisten beantwortet werden, zu einer Directory Search-Telefonzentrale wechseln. 

***
![Nummer 4](../images/sfbcallout4.png)<br/><br/>**Wenn das Zeitlimit eines Anrufs überschritten ist**: Wenn der Anruf das Limit erreicht, das Sie für die Einstellung **Wie lange ein Anruf in der Warteschlange warten kann** festgelegt haben, können Sie auswählen, was mit den in der Anrufwarteschleife wartenden Anrufen geschieht:
*    **Trennen**: Der Anruf wird getrennt.
*    **Weiterleiten an**: Wenn Sie diese Einstellung auswählen, haben Sie die folgenden Optionen:
     *    **Person in Ihrem Unternehmen** Ein Online-Benutzer mit einer**Telefonsystem**-Lizenz, für den Enterprise Voice aktiviert ist oder der einen Anrufplan hat. Sie können einrichten, dass Anrufer an die Voicemail geleitet werden. Dazu wählen Sie eine **Person in Ihrem Unternehmen** aus, deren Anrufe dann direkt an die Voicemail weitergeleitet werden. </br><br/>  Informationen zur erforderlichen Lizenzierung für Voicemail finden Sie unter [Einrichten von Telefonsystem-Voicemail](/microsoftteams/set-up-phone-system-voicemail). 

        > [!Note]
        > Benutzer, die mit Lync Server 2010 lokal gehostet werden, werden nicht unterstützt.<br/>

     *    **Anrufwarteschleife**: Sie müssen zuvor eine weitere Anrufwarteschleife eingerichtet haben, die Sie dann hier auswählen können.
     *    **Automatische Telefonzentrale**: Sie müssen zurvor eine automatische Telefonzentrale eingerichtet haben, die Sie dann hier auswählen können. Sehen Sie [Einrichten einer automatischen Telefonzentrale für das Telefonsystem](set-up-a-phone-system-auto-attendant.md).
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Ändern der Anrufer-ID des Benutzers zu einer Rufnummer der Anrufwarteschleife

Sie können die Identität eines Benutzers schützen, indem Sie seine Anrufer-ID für ausgehende Anrufe zu einer Rufnummer der Warteschleife ändern. Dazu müssen Sie mit dem Cmdlet **New-CallingLineIdentity** eine Richtlinie erstellen.
  
Zu diesem Zweck führen Sie Folgendes aus:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Wenden Sie die Richtlinie für den Benutzer mit dem Cmdlet **Grant-CallingLineIdentity** an. Zu diesem Zweck führen Sie Folgendes aus:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Weitere Informationen zum Ändern der Anrufer-ID-Einstellungen in Ihrer Organisation finden Sie [hier](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="want-to-know-more"></a>Möchten Sie mehr wissen?

Sie können auch Windows PowerShell verwenden, um automatische Telefonzentralen zu erstellen und einzurichten.
  
### <a name="call-queue-cmdlets"></a>Cmdlets für Anrufwarteschleifen

Zum Verwalten einer Anrufwarteschleife benötigen Sie die folgenden Cmdlets.
  
- [New-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [Set-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [Get-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [Remove-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### <a name="more-about-windows-powershell"></a>Weitere Informationen zu Windows PowerShell

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Dinge zu tun haben. Siehe folgende Themen, um Windows PowerShell zu verwenden:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Warum Sie Office 365 PowerShell verwenden sollten](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Verwandte Themen
[Das bekommen Sie mit Telefonsystem in Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Anfordern von Servicenummern für Skype for Business und Microsoft Teams](getting-service-phone-numbers.md)

[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
