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
description: 'Erfahren Sie, wie Sie Telefonsysteme für Office 365 (Cloud PBX) Anrufwarteschleifen mit einer Begrüßung der Organisation und der Weiterleitung von Anrufen an Telefonisten in Verteilersystem und Sicherheitsgruppen einrichten. Optionen für maximale Warteschleifenengröße, Zeitüberschreitung und Anrufbearbeitung können ebenfalls festgelegt werden. '
ms.openlocfilehash: 1952d6d180f5b9662b1e598ceb9d0b8d230640c2
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375149"
---
# <a name="create-a-phone-system-call-queue"></a>Erstellen einer Telefonsystem-Anrufwarteschleife

Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.
  
Telefonsystem-Anrufwarteschleifen bieten:
  
- Eine Begrüßung der Organisation
    
- Musik, während die wartenden Anrufer gehalten werden
    
- Umleiten von Anrufen Agents in e-Mail-aktivierte Verteilerlisten und Sicherheitsgruppen aufrufen.
    
- Einstellungen für Anruf Warteschlange maximale Größe, Timeout und Optionen für die Behandlung Anruf tätigen.
    
When someone calls in to a phone number that is set up up with a call queue, they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent. The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in the  *First In, First Out*  (FIFO) manner.
  
Alle Anrufe, die in der Warteschlange werden mit einer attendant routing oder serielles routing Modus verteilt werden:
  
- Mit attendant routing wird der erste Aufruf in der Warteschlange alle Agents gleichzeitig anrufen.
    
- Mit seriellem Routing (serial routing) wird der erste Aufruf in der Warteschleife alle Telefonisten nacheinander anrufen.
    
    > [!NOTE]
    > Telefonisten, die **Offline**sind, ihre Anwesenheit auf **Nicht stören** festgelegt haben, oder haben sich von der Warteschleife abgemeldet haben, werden nicht angerufen.
  
- Es wird nur jeweils eine Benachrichtigung über einen eingehenden Anruf (für den ersten Anruf in der Warteschleife) an die Telefonisten gesendet.
    
- Wenn ein Telefonist den Anruf angenommen hat, klingelt der nächste eingehende Anruf aus der Warteschleife bei den Telefonisten.
    
## <a name="step-1---getting-started"></a>Schritt 1 - Erste Schritte

Die folgenden Punkte sind bei Ihrem Einstieg in die Verwendung von Anrufwarteschleifen wichtig:
  
- Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license. The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for call queues. The number of call queues you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization. To learn more about licensing, go [here](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!NOTE]
    > To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Weitere Informationen zu Office 365 Anrufplänen finden Sie unter [Was sind Anrufpläne in Office 365?](/microsoftteams/what-are-calling-plans-in-office-365) und [Anrufpläne für Office 365](/microsoftteams/calling-plans-for-office-365).
    
    > [!NOTE]
    > Benutzer: lokal gehostet werden nicht mithilfe von Lync Server 2010 als ein Anruf Warteschlange Agents unterstützt. 
  
- You can only assign toll and toll-free service phone numbers that you got in the **Skype for Business admin center** or transferred from another service provider to Phone System call queues. To get and use toll-free service numbers, you need to set up Communications Credits.
    
    > [!NOTE]
    > Telefonnummern von Benutzern (Abonnenten) können Anrufwarteschleifen nicht zugewiesen werden - es können nur gebührenpflichtige oder gebührenfreie Telefonnummern verwendet werden. 
  
- Wenn Sie eingehende Anrufe von einer Telefonsystem Anruf Warteschlange verteilen, werden diese Clients für Call-Agenten unterstützt:
    
  - Desktopclient von Skype for Business 2016 (32- und 64-Bit-Version)
    
  - Desktopclient von Lync 2013 (32- und 64-Bit-Version)
    
  - All IP phone models supported for Skype for Business Online. See [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).
    
  - Mac Skype for Business-Client (Version 16.8.196 und höher) 
    
  - Android Skype for Business-Client (Version 6.16.0.9 und höher)
    
  - iPhone Skype for Business-Client (Version 6.16.0 und höher)
    
  - Mac Skype for Business-Client (Version 6.16.0 und höher)

  - Microsoft Teams Windows-Client (32- und 64-Bit-Versionen)

  - Microsoft Teams Mac-Client

  - Microsoft-Teams, iPhone-app

  - Microsoft-Teams, Android-app
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Schritt 2 - Beziehen oder Übertragen von gebührenpflichtigen oder gebührenfreien Servicenummern

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).
  
> [!NOTE]
> If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.
  
## <a name="step-3---create-a-new-call-queue"></a>Schritt 3 - Erstellen einer neuen Anrufwarteschleife

![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter**

Klicken Sie im **Skype for Business Admin Center** auf **Anrufweiterleitung** > **Anrufwarteschleifen** und dann auf **Neu hinzufügen**:
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>Festlegen des Anzeigenamens, der Telefonnummer und gegebenenfalls der Domäne für die Anrufwarteschleife

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![Nummer 1](../images/sfbcallout1.png)<br/>
**Name**: Geben Sie einen aussagekräftigen Anzeigenamen für die Anrufwarteschleife ein. Der Name ist erforderlich und kann maximal 64 Zeichen einschließlich Leerzeichen enthalten.<br/> Dieser Name wird in der Benachrichtigung über den eingehenden Anruf angezeigt.
***
![Nummer 2](../images/sfbcallout2.png)<br/>**Phone number** Select a service toll or toll-free phone number for the call queue. This is optional. <br/> If there aren't any listed, you need to get service numbers before you can create this call queue. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md)
***
![Nummer 3](../images/sfbcallout3.png)<br/>**Domäne**: Wenn diese Option verfügbar ist, wählen Sie die Office 365-Domäne aus, die Sie verwenden möchten. Diese Option ist nur verfügbar, wenn Sie mehrere Domänen für Office 365 verwenden. Wenn mehrere Domänen vorhanden sind, müssen Sie den Domänennamen in der Liste auswählen. <br/> Ihre Domäne könnte beispielsweise so heißen:  _contoso.com or redmond.contoso.com_
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Festlegen der Begrüßung und der Wartemusik, die wiedergegeben werden soll

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/>**Greeting** is optional. This is the greeting that is played for people who call in to the call queue number. <br/> Sie können eine Audiodatei (WAV-, MP3 oder WMA-Format) hochladen.
***
![Nummer 2](../images/sfbcallout2.png)<br/>**Musik in der Warteschleife** Sie können entweder übernehmen Sie die Musik in der Warteschleife, die mit der Warteschlange Anruf bereitgestellt, oder Sie können Hochladen einer Audiodatei in WAV, mp3 oder WMA-Formate, die als Ihre benutzerdefinierte Musik in der Warteschleife verwendet. 
   

### <a name="select-the-call-distribution-method"></a>Wählen Sie die Anruf-Verteilungsmethode

![Zeigt die Optionen für Anruf-Verteilungsmethoden an](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/>**Call distribution method** You can choose either **Attendant** or **Serial** for your call queue distribution method. All new and existing call queues will have attendant routing selected by default. To use serial routing, you must explicitly choose the **Serial** routing option in UI and cmdlets. <br/><br/> When serial routing is chosen and the call queue is saved, the calls from the queue will ring your agents one by one, starting from the beginning of the agent list. If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.   

> [!NOTE]
> Serielles Routing überspringt Telefonisten, die **Offline** sind, ihren Anwesenheitsstatus auf **Nicht stören**festgelegt haben oder sich von Anrufen aus dieser Anrufwarteschleife**abgemeldet haben**. 
   
### <a name="select-an-agent-opt-out-option"></a>Wählen Sie eine Option für das Abmelden von Telefonisten

![Zeigt das Abmeldungs-Kontrollkästchen des Telefonisten](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/>**Option Abmeldung für Telefonisten** Sie können es Telefonisten erlauben, sich von Anrufen von einer bestimmten Anrufwarteschleife abzumelden, indem Sie die **Option Abmeldung für Telefonisten** auswählen.  <br/> Enabling this option allows all agents in this queue to start or stop receiving call from this call queue at will. You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).  <br/><br/> Um auf die Abmeldungsfunktion zuzugreifen können Telefonisten folgendes tun:
 1. Öffnen Sie **Optionen** in Skype for Business-Client auf ihrem Desktop. 
 2. Klicken Sie in der Registerkarte **Anrufweiterleitung** auf den Link **Online-Einstellungen bearbeiten**.
 3. Klicken Sie auf der Einstellungsseite für Benutzer auf **Anrufwarteschleifen** und deaktivieren Sie die Kontrollkästchen für alle Warteschleifen, von denen sie sich abmelden möchten.
 
    > [!NOTE] 
    > Mithilfe der Mac-, Mobile oder Lync 2013-Clients oder Hybrid-VoIP-Benutzern, die lokal auf einem Skype for Business 2015 Server gehostet werden, können Telefonisten die Abmeldungsoption über [https://aka.ms/cqsettings](https://aka.ms/cqsettings) aufrufen.
   
### <a name="add-call-agents-to-a-call-queue"></a>Hinzufügen von Telefonisten zu einer Anrufwarteschleife

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/><br/>Telefonisten (maximal 50) können sein:
* Ein Online-Benutzer mit einer **Telefonsystem**-Lizenz und Enterprise Voice oder einem Anrufplan. <br/><br/> **Note:**  To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
* Online users with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group. It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue. A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues. Newly created Office 365 Groups are available almost immediately. <br/> 

  > [!NOTE] 
  > Benutzer gehostet: lokal mit Lync Server 2010 werden nicht unterstützt.           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>Festlegen der maximalen Warteschleifengröße und der maximalen Wartezeit

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/><br/>**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time. The default is 50, but it can range from 0 to 200.When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.
***
![Nummer 2](../images/sfbcallout2.png)<br/><br/>**Wenn die maximale Anzahl von Anrufen erreicht wird** Wenn die Anruf Warteschlange die maximale Größe (unter Verwendung der Einstellung **Maximum von Anrufen in der Warteschlange** festgelegt) erreicht, können Sie auswählen, was passiert, um neue eingehende Anrufe.
* **Mit Besetztzeichen trennen**: Der Anruf wird getrennt.
* **In diesem Anruf weiterleiten an** Wenn Sie diese Option wählen, müssen Sie diese Optionen:
  * **Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. <br/> <br/>Informationen zur erforderlichen Lizenzierung für Voicemail finden Sie unter [Einrichten von Telefonsystem-Voicemail](/microsoftteams/set-up-phone-system-voicemail). 
     
    > [!Note]
    > Benutzer gehostet: lokal mit Lync Server 2010 werden nicht unterstützt.<br/>
     
  * **Aufrufen der Warteschlange** Müssen Sie bereits erstellt haben andere Warteschleife der Anruf, aber nach dem Sie dies tun, können Sie diese Warteschlange Anruf auswählen.
  * **Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).
***
![Nummer 3](../images/sfbcallout3.png)<br/><br/>**Wie lange ein Anruf in der Warteschlange warten kann**: Sie können auch entscheiden, wie lange ein Anruf in der Warteschleife gehalten werden kann, bis es zu einem Timeout kommt und der Anruf umgeleitet werden muss. Wohin der Anruf umgeleitet wird, hängt von Ihrer Einstellung für **Wenn das Zeitlimit eines Anrufs überschritten ist** ab. Sie können eine Dauer von 0 bis 45 Minuten festlegen. <br/><br/> The timeout value can be set in seconds, at 15-second intervals. This allows you to manipulate the call flow with finer granularity. For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search Auto Attendant. 

***
![Nummer 4](../images/sfbcallout4.png)<br/><br/>**Wenn das Zeitlimit eines Anrufs überschritten ist**: Wenn der Anruf das Limit erreicht, das Sie für die Einstellung **Wie lange ein Anruf in der Warteschlange warten kann** festgelegt haben, können Sie auswählen, was mit den in der Anrufwarteschleife wartenden Anrufen geschieht:
* **Trennen**: Der Anruf wird getrennt.
* **In diesem Anruf weiterleiten an** Wenn Sie diese Option wählen, müssen Sie diese Optionen:
  * **Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. </br><br/>  Informationen zur erforderlichen Lizenzierung für Voicemail finden Sie unter [Einrichten von Telefonsystem-Voicemail](/microsoftteams/set-up-phone-system-voicemail). 

    > [!Note]
    > Benutzer gehostet: lokal mit Lync Server 2010 werden nicht unterstützt.<br/>

  * **Aufrufen der Warteschlange** Müssen Sie bereits erstellt haben andere Warteschleife der Anruf, aber nach dem Sie dies tun, können Sie diese Warteschlange Anruf auswählen.
  * **Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Ändern der Anrufer-ID des Benutzers zu einer Rufnummer der Anrufwarteschleife

Sie können die Identität eines Benutzers schützen, indem Sie seine Anrufer-ID für ausgehende Anrufe zu einer Rufnummer der Warteschleife ändern. Dazu müssen Sie mit dem Cmdlet **New-CallingLineIdentity** eine Richtlinie erstellen.
  
Zu diesem Zweck führen Sie Folgendes aus:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet. To do this, run:
  
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

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:
    
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

  
 
