---
title: Erstellen einer Telefonsystem-Anrufwarteschleife
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options. '
ms.openlocfilehash: 53d3eee97ba5fc396b47396b969fef6f2e899df1
ms.sourcegitcommit: 60e8365281ec6d780f1b2439bedef0bd71f002d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2019
ms.locfileid: "30046738"
---
# <a name="create-a-phone-system-call-queue"></a>Erstellen einer Telefonsystem-Anrufwarteschleife

System-Telefonanruf Warteschlangen enthalten Ansage, die verwendet werden, wenn angerufen eine Rufnummer für Ihre Organisation die Möglichkeit, die Anrufe automatisch gehalten wird und für den nächsten verfügbaren Anruf-Agent zum Verarbeiten des Anrufs beim Personen die Möglichkeit zum Suchen, die Anruf Musik in der Warteschleife hören sind. Sie können einzelne oder mehrere Anruf Warteschlangen für Ihre Organisation erstellen.
  
Telefonsystem-Anrufwarteschleifen bieten:
  
- Eine Begrüßung der Organisation
- Musik, während die wartenden Anrufer gehalten werden
- Umleiten von Anrufen Agents in e-Mail-aktivierte Verteilerlisten und Sicherheitsgruppen aufrufen.
- Einstellungen für Anruf Warteschlange maximale Größe, Timeout und Optionen für die Behandlung Anruf tätigen.

Wenn Sie an eine Telefonnummer angerufen werden, die mit einer Warteschlange Anruf eingerichtet ist, hören sie eine Begrüßung erste (sofern eine eingerichtet ist), und anschließend wird in die Warteschlange aufgenommen werden und für den nächsten verfügbaren Anruf Agent warten. Die Person Aufrufen in werden Musik hören, während sie sind in der Warteschleife warten, und die Anrufe, um den Anruf-Agenten auf die Weise *First In, First Out* (FIFO angeboten werden).
  
Alle Anrufe, die in der Warteschlange werden mit einer attendant routing oder serielles routing Modus verteilt werden:
  
- Mit attendant routing wird der erste Aufruf in der Warteschlange alle Agents gleichzeitig anrufen.
- Mit seriellem Routing (serial routing) wird der erste Aufruf in der Warteschleife alle Telefonisten nacheinander anrufen.

    > [!NOTE]
    > Telefonisten, die **Offline**sind, ihre Anwesenheit auf **Nicht stören** festgelegt haben, oder haben sich von der Warteschleife abgemeldet haben, werden nicht angerufen.
  
- Es wird nur jeweils eine Benachrichtigung über einen eingehenden Anruf (für den ersten Anruf in der Warteschleife) an die Telefonisten gesendet.
- Wenn ein Telefonist den Anruf angenommen hat, klingelt der nächste eingehende Anruf aus der Warteschleife bei den Telefonisten.

## <a name="step-1---getting-started"></a>Schritt 1 - Erste Schritte

Die folgenden Punkte sind bei Ihrem Einstieg in die Verwendung von Anrufwarteschleifen wichtig:
  
- Ihre Organisation muss eine Lizenz Enterprise E3 plus **Telefonsystem** oder einer E5 Enterprise-Lizenz (mindestens) verfügen. Die Anzahl der **Telefonsystem** Benutzerlizenzen, die zugewiesen sind, wirkt sich auf die Anzahl der Dienst Zahlen, die für Anruf Warteschlangen zu verwendende verfügbar sind. Die Anzahl der Anruf Warteschlangen haben Sie können ist abhängig von der Anzahl der **Telefonsystem** und **Audiokonferenzen** Lizenzen, die in Ihrer Organisation zugewiesen sind. Weitere Informationen zu Lizenzierung finden Sie [hier](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

    > [!NOTE]
    > Zum Umleiten von Anrufen an Personen in Ihrer Organisation, die Online sind, sie benötigen eine Lizenz **Telefonsystem** und für Enterprise-VoIP aktiviert sein oder Office 365 aufrufen Plans. Siehe [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Um diese Lizenzen für Enterprise-VoIP zu aktivieren, können Sie die Windows PowerShell verwenden. Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Weitere Informationen zu Office 365 Anrufplänen finden Sie unter [Was sind Anrufpläne in Office 365?](/microsoftteams/what-are-calling-plans-in-office-365) und [Anrufpläne für Office 365](/microsoftteams/calling-plans-for-office-365).

    > [!NOTE]
    > Benutzer: lokal gehostet werden nicht mithilfe von Lync Server 2010 als ein Anruf Warteschlange Agents unterstützt. 
  
- Nur gebührenpflichtige oder gebührenfreie Servicenummern, die Ihnen im**Skype for Business Administrationscenter** zur Verfügung stehen oder die ein anderer Anbieter an Sie übertragen hat, können an Telefonsystem-Anrufwarteschleifen zugewiesen werden. Um gebührenfreie Servicenummern zu erhalten müssen Sie Communication Credits einrichten.

    > [!NOTE]
    > Telefonnummern von Benutzern (Abonnenten) können Anrufwarteschleifen nicht zugewiesen werden - es können nur gebührenpflichtige oder gebührenfreie Telefonnummern verwendet werden. 
  
- Wenn Sie eingehende Anrufe von einer Telefonsystem Anruf Warteschlange verteilen, werden diese Clients für Call-Agenten unterstützt:

  - Desktopclient von Skype for Business 2016 (32- und 64-Bit-Version)

  - Desktopclient von Lync 2013 (32- und 64-Bit-Version)

  - Für Skype for Business Online werden alle IP-Telefonmodell unterstützt. Weitere Informationen finden Sie unter [Kauf von Telefonen für Skype for Business Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).

  - Mac Skype for Business-Client (Version 16.8.196 und höher) 

  - Android Skype for Business-Client (Version 6.16.0.9 und höher)

  - iPhone Skype for Business-Client (Version 6.16.0 und höher)

  - Mac Skype for Business-Client (Version 6.16.0 und höher)

  - Microsoft Teams Windows-Client (32- und 64-Bit-Versionen)

  - Microsoft Teams Mac-Client

  - Microsoft-Teams, iPhone-app

  - Microsoft-Teams, Android-app

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Schritt 2 - Beziehen oder Übertragen von gebührenpflichtigen oder gebührenfreien Servicenummern

Bevor Sie Ihre Anrufwarteschleifen erstellen und einrichten können, müssen Sie Ihre bestehenden kostenpflichtigen oder gebührenfreien Servicenummern einrichten oder übertragen. Nachdem Sie die gebührenfreien Service-Telefonnummern erhalten haben, werden diese in **Skype for Business Admin Center** > **Voice** > **Telefonnummern** angezeigt, und der **Nummerntyp** wird als **Service - gebührenfrei** aufgelistet. Wenn die Rufnummern Service erhalten möchten, finden Sie unter [Getting Service Rufnummern für Skype für Unternehmen und die Microsoft-Teams,](getting-service-phone-numbers.md) oder für Übertragung und vorhandenen Service-Nummer, finden Sie unter [Übertragen von Telefonnummern zu Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).
  
> [!NOTE]
> Wenn Sie sich außerhalb der USA sind, können der Skype für Business Administrationscenter Sie um Service Zahlen zu erhalten. Wechseln Sie zum [Verwalten von Rufnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization) stattdessen, wie Sie von außerhalb der USA finden Sie unter.
  
## <a name="step-3---create-a-new-call-queue"></a>Schritt 3 - Erstellen einer neuen Anrufwarteschleife

 **Verwenden das Microsoft-Teams, Administrationscenter**

Klicken Sie in der **Microsoft-Teams, Administrationscenter**auf ![Sfb-Logo-30x30.png](../images/sfb-logo-30x30.png) **Legacy-Portal** >  **Anrufrouting** > **aufrufen, Warteschlangen**, klicken Sie dann auf **+ Neues hinzufügen**:
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>Festlegen des Anzeigenamens, der Telefonnummer und gegebenenfalls der Domäne für die Anrufwarteschleife

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![Nummer 1](../images/sfbcallout1.png)<br/>
**Name**: Geben Sie einen aussagekräftigen Anzeigenamen für die Anrufwarteschleife ein. Der Name ist erforderlich und kann maximal 64 Zeichen einschließlich Leerzeichen enthalten.<br/> Dieser Name wird in der Benachrichtigung über den eingehenden Anruf angezeigt.
***
![Nummer 2](../images/sfbcallout2.png)<br/>**Telefonnummer** Wählen Sie eine gebührenpflichtige oder gebührenfreie Servicenummer für die Anrufwarteschleife aus. Optional. <br/> Wenn keine Servicenummern aufgelistet sind, müssen Sie sich diese besorgen, damit Sie diese Anrufwarteschleife erstellen können. Um Ihre Servicenummern zu erhalten sehen Sie [Einrichten von Servicenummern für Skype for Business und Microsoft Teams](getting-service-phone-numbers.md)
***
![Nummer 3](../images/sfbcallout3.png)<br/>**Domäne**: Wenn diese Option verfügbar ist, wählen Sie die Office 365-Domäne aus, die Sie verwenden möchten. Diese Option ist nur verfügbar, wenn Sie mehrere Domänen für Office 365 verwenden. Wenn mehrere Domänen vorhanden sind, müssen Sie den Domänennamen in der Liste auswählen. <br/> Ihre Domäne könnte beispielsweise so heißen:  _contoso.com or redmond.contoso.com_

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Festlegen der Begrüßung und der Wartemusik, die wiedergegeben werden soll

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/>**Begrüßung** ist optional. Dies ist die Ansage, die für Personen, die in Aufrufen an die Warteschlange Anrufnummer wiedergegeben wird. <br/> Sie können eine Audiodatei (WAV-, MP3 oder WMA-Format) hochladen.
***
![Nummer 2](../images/sfbcallout2.png)<br/>**Musik in der Warteschleife** Sie können entweder übernehmen Sie die Musik in der Warteschleife, die mit der Warteschlange Anruf bereitgestellt, oder Sie können Hochladen einer Audiodatei in WAV, mp3 oder WMA-Formate, die als Ihre benutzerdefinierte Musik in der Warteschleife verwendet.

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

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/><br/>Call-Agenten (maximal 200) sind möglich:
* Ein Online-Benutzer mit einer **Telefonsystem**-Lizenz und Enterprise Voice oder einem Anrufplan. <br/><br/> **Hinweis:**  Zum Umleiten von Anrufen an Personen in Ihrer Organisation, die Online sind, sie benötigen eine Lizenz **Telefonsystem** und für Enterprise-VoIP aktiviert sein oder aufrufen planen. Siehe [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Um diese Lizenzen für Enterprise-VoIP zu aktivieren, können Sie die Windows PowerShell verwenden. Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
* Online-Benutzer mit einer **Telefonsystem**-Lizenz und einem Anrufplan, die einer Office 365-Gruppe, einer e-Mail-Verteilerliste oder einer Sicherheitsgruppe hinzugefügt worden sind. Es kann bis zu 30 Minuten dauern, bis ein neuer Telefonist zu einer Verteilerliste oder Sicherheitsgruppe hinzugefügt wird und Anrufe aus einer Anrufwarteschleife empfangen kann. Eine neu erstellte Liste oder eine Sicherheitsgruppe Verteilergruppe kann die Verwendung mit dem Anruf Warteschlangen verfügbar bis zu 48 Stunden dauern. Neu erstellte Office 365-Gruppen sind fast sofort verfügbar. <br/> 

  > [!NOTE] 
  > Benutzer gehostet: lokal mit Lync Server 2010 werden nicht unterstützt.

### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>Festlegen der maximalen Warteschleifengröße und der maximalen Wartezeit

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/><br/>**Maximale Anrufe in der Warteschlange**: Legen Sie mit dieser Option fest, wie lange Anrufe maximal in der Warteschleife warten können, bis es zu einem Timeout kommt. Der Standardwert ist 50, aber es kann im Bereich von 0 bis 200. wenn dieser Grenzwert erreicht ist, der Anruf verarbeitet werden in die Möglichkeit, die Sie auf die Einstellung **gewählt wird die maximale Anzahl von Anrufen erreicht** haben.
***
![Nummer 2](../images/sfbcallout2.png)<br/><br/>**Wenn die maximale Anzahl von Anrufen erreicht wird** Wenn die Anruf Warteschlange die maximale Größe (unter Verwendung der Einstellung **Maximum von Anrufen in der Warteschlange** festgelegt) erreicht, können Sie auswählen, was passiert, um neue eingehende Anrufe.
* **Mit Besetztzeichen trennen**: Der Anruf wird getrennt.
* **In diesem Anruf weiterleiten an** Wenn Sie diese Option wählen, müssen Sie diese Optionen:
  * **Person in Ihrem Unternehmen** Ein Online-Benutzer mit einer Lizenz **Telefonsystem** und für Enterprise-VoIP aktiviert sein oder aufrufen planen. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Zu diesem Zweck wählen Sie eine **Person in Ihrem Unternehmen** , und legen Sie diese Person ihre Anrufe an die Voicemail weitergeleitet werden. <br/> <br/>Informationen zur erforderlichen Lizenzierung für Voicemail finden Sie unter [Einrichten von Telefonsystem-Voicemail](/microsoftteams/set-up-phone-system-voicemail). 

    > [!Note]
    > Benutzer gehostet: lokal mit Lync Server 2010 werden nicht unterstützt.<br/>

  * **Aufrufen der Warteschlange** Müssen Sie bereits erstellt haben andere Warteschleife der Anruf, aber nach dem Sie dies tun, können Sie diese Warteschlange Anruf auswählen.
  * **Automatische Telefonzentrale** Sie müssen bereits erstellt haben eine automatische Telefonzentrale, aber nach dem Sie dies tun, können Sie diese automatische Telefonzentrale auswählen. Finden Sie unter [Einrichten von einer Telefonzentrale Telefonsystem](set-up-a-phone-system-auto-attendant.md).
***
![Nummer 3](../images/sfbcallout3.png)<br/><br/>**Wie lange ein Anruf in der Warteschlange warten kann**: Sie können auch entscheiden, wie lange ein Anruf in der Warteschleife gehalten werden kann, bis es zu einem Timeout kommt und der Anruf umgeleitet werden muss. Wohin der Anruf umgeleitet wird, hängt von Ihrer Einstellung für **Wenn das Zeitlimit eines Anrufs überschritten ist** ab. Sie können eine Dauer von 0 bis 45 Minuten festlegen. <br/><br/> Der Timeoutwert kann in Sekunden in Intervallen von 15 Sekunden festgelegt werden. Dadurch können Sie den Anruffluss mit feinerer Granularität bearbeiten. Beispielsweise könnten Sie angeben, dass alle Anrufe, die nicht innerhalb von 30 Sekunden von einem Telefonisten beantwortet werden, zu einer Directory Search-Telefonzentrale wechseln. 

***
![Nummer 4](../images/sfbcallout4.png)<br/><br/>**Wenn das Zeitlimit eines Anrufs überschritten ist**: Wenn der Anruf das Limit erreicht, das Sie für die Einstellung **Wie lange ein Anruf in der Warteschlange warten kann** festgelegt haben, können Sie auswählen, was mit den in der Anrufwarteschleife wartenden Anrufen geschieht:
* **Trennen**: Der Anruf wird getrennt.
* **In diesem Anruf weiterleiten an** Wenn Sie diese Option wählen, müssen Sie diese Optionen:
  * **Person in Ihrem Unternehmen** Ein Online-Benutzer mit einer Lizenz **Telefonsystem** und für Enterprise-VoIP aktiviert sein oder plant aufrufen. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Zu diesem Zweck wählen Sie eine **Person in Ihrem Unternehmen** , und legen Sie diese Person ihre Anrufe an die Voicemail weitergeleitet werden. </br><br/>  Informationen zur erforderlichen Lizenzierung für Voicemail finden Sie unter [Einrichten von Telefonsystem-Voicemail](/microsoftteams/set-up-phone-system-voicemail). 

    > [!Note]
    > Benutzer gehostet: lokal mit Lync Server 2010 werden nicht unterstützt.<br/>

  * **Aufrufen der Warteschlange** Müssen Sie bereits erstellt haben andere Warteschleife der Anruf, aber nach dem Sie dies tun, können Sie diese Warteschlange Anruf auswählen.
  * **Automatische Telefonzentrale** Sie müssen bereits erstellt haben eine automatische Telefonzentrale, aber nach dem Sie dies tun, können Sie diese automatische Telefonzentrale auswählen. Finden Sie unter [Einrichten von einer Telefonzentrale Telefonsystem](set-up-a-phone-system-auto-attendant.md).
   
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

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 und Skype verwalten, für die Business Online verwenden eine zentrale Verwaltung, die Ihrer täglichen Arbeit vereinfachen können, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:

  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>See Also
[Das bekommen Sie mit Telefonsystem in Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Anfordern von Servicenummern für Skype for Business und Microsoft Teams](getting-service-phone-numbers.md)

[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
