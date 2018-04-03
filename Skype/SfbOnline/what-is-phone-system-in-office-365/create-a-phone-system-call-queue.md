---
title: Erstellen einer Telefonsystem Anruf Warteschleife
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.date: 01/22/2018
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: 'Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options. '
ms.openlocfilehash: a6eac4b7fec191d9e897f41e3c32b270ab21abcf
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2018
---
# <a name="create-a-phone-system-call-queue"></a>Erstellen einer Telefonsystem Anruf Warteschleife

System-Telefonanruf Warteschlangen enthalten Ansage, die verwendet werden, wenn angerufen eine Rufnummer für Ihre Organisation die Möglichkeit, die Anrufe automatisch gehalten wird und für den nächsten verfügbaren Anruf-Agent zum Verarbeiten des Anrufs beim Personen die Möglichkeit zum Suchen, die Anruf Musik in der Warteschleife hören sind. Sie können einzelne oder mehrere Anruf Warteschlangen für Ihre Organisation erstellen.
  
Telefon System Anruf Warteschlangen bieten:
  
- Eine Begrüßung der Organisation
    
- Musik, während die wartenden Anrufer gehalten werden
    
- Umleiten von Anrufen Agents in e-Mail-aktivierte Verteilerlisten und Sicherheitsgruppen aufrufen.
    
- Einstellungen für Anruf Warteschlange maximale Größe, Timeout und Optionen für die Behandlung Anruf tätigen.
    
Wenn angerufen werden an eine Telefonnummer, die festgelegt wird von oben mit einer Warteschlange Anruf sie hören eine Begrüßung erste (sofern eine eingerichtet ist), und anschließend wird in die Warteschlange aufgenommen werden und für den nächsten verfügbaren Anruf Agent warten. Die Person Aufrufen in werden Musik hören, während sie sind in der Warteschleife warten, und die Anrufe, um den Anruf-Agenten auf die Weise *First In, First Out* (FIFO angeboten werden).
  
Alle Anrufe, die in der Warteschlange werden mit einer attendant routing oder serielles routing Modus verteilt werden:
  
- Mit attendant routing wird der erste Aufruf in der Warteschlange alle Agents gleichzeitig anrufen.
    
- Mit serielles routing verwendet, wird der erste Aufruf in der Warteschlange alle Anruf Agents nacheinander anrufen.
    
    > [!NOTE]
    > Call-Agenten, die **Offline**sind, ihre Anwesenheit auf **nicht stören,** festgelegt haben, oder haben sich entschieden, aus der Warteschlange Anruf werden nicht aufgerufen.
  
- Es wird nur jeweils eine Benachrichtigung über einen eingehenden Anruf (für den ersten Anruf in der Warteschleife) an die Telefonisten gesendet.
    
- Wenn ein Telefonist den Anruf angenommen hat, klingelt der nächste eingehende Anruf aus der Warteschleife bei den Telefonisten.
    
## <a name="step-1---getting-started"></a>Schritt 1 - Erste Schritte

Die folgenden Punkte sind bei Ihrem Einstieg in die Verwendung von Anrufwarteschleifen wichtig:
  
- Ihre Organisation muss eine Lizenz Enterprise E3 plus **Telefonsystem** oder einer E5 Enterprise-Lizenz (mindestens) verfügen. Die Anzahl der **Telefonsystem** Benutzerlizenzen, die zugewiesen sind, wirkt sich auf die Anzahl der Dienst Zahlen, die für Anruf Warteschlangen zu verwendende verfügbar sind. Die Anzahl der Anruf Warteschlangen haben Sie können ist abhängig von der Anzahl der **Telefonsystem** und **Audiokonferenzen** Lizenzen, die in Ihrer Organisation zugewiesen sind. Weitere Informationen zu Lizenzierung, klicken Sie [hier](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!NOTE]
    > Zum Umleiten von Anrufen an Personen in Ihrer Organisation, die Online sind, sie benötigen eine Lizenz **Telefonsystem** und für Enterprise-VoIP aktiviert sein oder Office 365 aufrufen Plans. Siehe [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Um diese Lizenzen für Enterprise-VoIP zu aktivieren, können Sie die Windows PowerShell verwenden. Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Weitere Informationen zu Office 365 aufrufen plant, finden Sie unter [Was sind in Office 365-Pläne aufrufen?](../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md) und [Aufrufen von Pläne für Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/calling-plans-for-office-365.md).
    
    > [!NOTE]
    > Benutzer: lokal gehostet werden nicht mithilfe von Lync Server 2010 als ein Anruf Warteschlange Agents unterstützt. 
  
- Sie können nur zuweisen gebührenpflichtige oder gebührenfreie Service Telefonnummern, die Sie haben Sie in der **Skype für Business Administrationscenter** oder aus einem anderen Dienstanbieter in Telefonsystem Anruf Warteschlangen übertragen. Zum Abrufen und gebührenfreie Service Zahlen verwenden, müssen Sie Communications haben einrichten.
    
    > [!NOTE]
    > Telefonnummern von Benutzern (Abonnenten) können Anrufwarteschleifen nicht zugewiesen werden - es können nur gebührenpflichtige oder gebührenfreie Telefonnummern verwendet werden. 
  
- Wenn Sie eingehende Anrufe von einer Telefonsystem Anruf Warteschlange verteilen, werden diese Clients für Call-Agenten unterstützt:
    
  - Desktopclient von Skype for Business 2016 (32- und 64-Bit-Version)
    
  - Desktopclient von Lync 2013 (32- und 64-Bit-Version)
    
  - Für Skype for Business Online werden alle IP-Telefonmodell unterstützt. Weitere Informationen finden Sie unter [Kauf von Telefonen für Skype for Business Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).
    
  - Mac Skype für Business-Client (Version 16.8.196 und höher) 
    
  - Android Skype für Business-Client (Version 6.16.0.9 und höher)
    
  - iPhone Skype für Business-Client (Version 6.16.0 und höher)
    
  - iPad Skype für Business-Client (Version 6.16.0 und höher)
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Schritt 2 - Beziehen oder Übertragen von gebührenpflichtigen oder gebührenfreien Servicenummern

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. Nachdem Sie die gebührenpflichtige oder gebührenfreie Service Telefonnummern erhalten möchten, sie werden angezeigt, in **Skype für Business Administrationscenter** > **VoIP** > **Telefonnummern**und **Datentyp Zahl** aufgeführt wird als **-Dienst - gebührenfreie Rufnummer aufgeführt werden **. Wenn die Rufnummern Service erhalten möchten, finden Sie unter [Getting Service Rufnummern für Skype für Unternehmen und die Microsoft-Teams,](getting-service-phone-numbers.md) oder für Übertragung und vorhandenen Service-Nummer, finden Sie unter [Übertragen von Telefonnummern zu Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Wenn Sie sich außerhalb der USA sind, können der Skype für Business Administrationscenter Sie um Service Zahlen zu erhalten. Wechseln Sie zum [Verwalten von Rufnummern für Ihre Organisation](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) stattdessen, wie Sie von außerhalb der USA finden Sie unter.
  
## <a name="step-3---create-a-new-call-queue"></a>Schritt 3 - Erstellen einer neuen Anrufwarteschleife

Klicken Sie im **Skype for Business Admin Center** auf **Anrufweiterleitung** > **Anrufwarteschleifen** und dann auf **Neu hinzufügen**:
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a>Festlegen des Anzeigenamens, der Telefonnummer und gegebenenfalls der Domäne für die Anrufwarteschleife

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
![Nummer 1](../images/sfbcallout1.png)<br/>
**Name**: Geben Sie einen aussagekräftigen Anzeigenamen für die Anrufwarteschleife ein. Der Name ist erforderlich und kann maximal 64 Zeichen einschließlich Leerzeichen enthalten.<br/> Dieser Name wird in der Benachrichtigung über den eingehenden Anruf angezeigt.
***
![Nummer 2](../images/sfbcallout2.png)<br/>**Telefonnummer** Wählen Sie eine gebührenpflichtige oder gebührenfreie Servicenummer für die Anrufwarteschleife aus. Optional. <br/> Wenn keine Servicenummern aufgelistet sind, müssen Sie sich diese besorgen, damit Sie diese Anrufwarteschleife erstellen können. Um die Rufnummern Service erhalten möchten, finden Sie unter [Getting Service Rufnummern für Skype für Unternehmen und die Microsoft-Teams](getting-service-phone-numbers.md)
***
![Nummer 3](../images/sfbcallout3.png)<br/>**Domäne**: Wenn diese Option verfügbar ist, wählen Sie die Office 365-Domäne aus, die Sie verwenden möchten. Diese Option ist nur verfügbar, wenn Sie mehrere Domänen für Office 365 verwenden. Wenn mehrere Domänen vorhanden sind, müssen Sie den Domänennamen in der Liste auswählen.<br/> Ihre Domäne könnte beispielsweise so heißen:  _contoso.com or redmond.contoso.com_
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Festlegen der Begrüßung und der Wartemusik, die wiedergegeben werden soll

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/>**Begrüßung** ist optional. Dies ist die Ansage, die für Personen, die in Aufrufen an die Warteschlange Anrufnummer wiedergegeben wird. <br/> Sie können eine Audiodatei (WAV-, MP3 oder WMA-Format) hochladen.
***
![Nummer 2](../images/sfbcallout2.png)<br/>**Musik in der Warteschleife** Sie können entweder übernehmen Sie die Musik in der Warteschleife, die mit der Warteschlange Anruf bereitgestellt, oder Sie können Hochladen einer Audiodatei in WAV, mp3 oder WMA-Formate, die als Ihre benutzerdefinierte Musik in der Warteschleife verwendet. 
   

### <a name="select-the-call-distribution-method"></a>Wählen Sie die Anruf Verteilung-Methode

![Zeigt den Aufruf Verteilungsoptionen-Methode](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/>**Rufen Sie Verteilungsmethode** Sie können für Ihre Anruf Warteschlange Verteilungsmethode **Attendant** oder **seriellen** auswählen. Alle neuen und vorhandenen Anruf Warteschlangen werden attendant routing standardmäßig ausgewählt haben. Wenn serielles routing verwenden möchten, müssen Sie explizit die **seriellen** routing-Option in der Benutzeroberfläche und -Cmdlets auswählen. <br/><br/> Wenn serielles routing ausgewählt wird, und die Warteschlange Anruf wird gespeichert, klingelt der Aufrufe aus der Warteschlange der Agents nacheinander ab dem Anfang der Liste Agent. Wenn ein Agent schließt oder nicht von einem Aufruf aufzunehmen, wird der Anruf klingelt den nächsten Agenten in der Liste und versucht, alle Agents nacheinander, bis es aufgenommene oder Timeout warten in der Warteschlange.  <br/><br/>  **Hinweis:** Serielles routing überspringt Agents, die sind **Offline**, deren Anwesenheitsstatus auf **nicht stören**festgelegt haben, oder der erste Anrufe aus dieser Warteschlange **bestätigt** .  
   
### <a name="select-an-agent-opt-out-option"></a>Wählen Sie einen Agent Aufheben der Bestätigung für option

![Zeigt der Agent kündigen Sie das Kontrollkästchen](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/>**Agent Aufheben der Bestätigung für option** Sie können auswählen, Anruf Warteschleife Agents zum Annehmen von Anrufen aus einer bestimmten Warteschlange durch Auswählen von **Agent Aufheben der Bestätigung für Option**abwählen können.  <br/> Durch Aktivieren dieser Option ermöglicht, dass alle Agents in dieser Warteschlange zum Starten oder beenden annehmen von Anrufen aus dieser Warteschlange Anruf am wird. Sie können das Agent zielorientierten Recht sperren jederzeit durch Deaktivieren des Kontrollkästchens, verursacht Agents automatisch für diese Warteschlange erneut (die Standardeinstellung für alle Agents) eingeschlossen werden.  <br/><br/> Zugriff auf die Option Abmeldung Möglichkeiten Agents folgende:
 1. Öffnen Sie **Optionen** in ihren desktop Skype für Business-Client. 
 2. Klicken Sie auf der Registerkarte **Anrufweiterleitung** auf den Link **online Einstellungen bearbeiten** .
 3. Klicken Sie auf der Einstellungsseite für Benutzer klicken Sie auf **Aufrufen, Warteschlangen**, und deaktivieren Sie die Kontrollkästchen für alle Warteschlangen für die sie kündigen möchten.
 
    > [!NOTE] 
    > Mithilfe der Mac-Agenten, Mobile Lync 2013-Clients oder Hybrid-VoIP-Benutzer gehostet lokalen mithilfe von Skype für Business 2015 Server gelangen zu [https://aka.ms/cqsettings](https://aka.ms/cqsettings) der lehnen Sie die Option Zugriff auf.
   
### <a name="add-call-agents-to-a-call-queue"></a>Hinzufügen von Telefonisten zu einer Anrufwarteschleife

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/><br/>Call-Agenten (maximal 50) sind möglich:
*    Ein Online-Benutzer mit einer Lizenz **Telefonsystem** und aktiviert für Enterprise-VoIP oder mit einem Aufruf von planen. <br/><br/> **Hinweis:**  Zum Umleiten von Anrufen an Personen in Ihrer Organisation, die Online sind, sie benötigen eine Lizenz **Telefonsystem** und für Enterprise-VoIP aktiviert sein oder aufrufen planen. Siehe [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Um diese Lizenzen für Enterprise-VoIP zu aktivieren, können Sie die Windows PowerShell verwenden. Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` <br/><br/>
*    Online-Benutzer mit einem mit einer Lizenz **Telefonsystem** und ein Aufruf von planen, die ein Office 365-Gruppe, einer e-Mail-Verteilerliste oder einer Sicherheitsgruppe hinzugefügt werden. Es kann bis zu 30 Minuten dauern, bis ein neuer Telefonist zu einer Verteilerliste oder Sicherheitsgruppe hinzugefügt wird und Anrufe aus einer Anrufwarteschleife empfangen kann. Eine neu erstellte Liste oder eine Sicherheitsgruppe Verteilergruppe kann die Verwendung mit dem Anruf Warteschlangen verfügbar bis zu 48 Stunden dauern. Neu erstellte sind Office 365 Gruppen fast sofort verfügbar. <br/> 

    > [!NOTE] 
    > Benutzer gehostet: lokal mit Lync Server 2010 werden nicht unterstützt.           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a>Festlegen der maximalen Warteschleifengröße und der maximalen Wartezeit

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/><br/>**Maximale Anrufe in der Warteschlange**: Legen Sie mit dieser Option fest, wie lange Anrufe maximal in der Warteschleife warten können, bis es zu einem Timeout kommt. Der Standardwert ist 50, aber es kann im Bereich von 0 bis 200. wenn dieser Grenzwert erreicht ist, der Anruf verarbeitet werden in die Möglichkeit, die Sie auf die Einstellung **gewählt wird die maximale Anzahl von Anrufen erreicht** haben.
***
![Nummer 2](../images/sfbcallout2.png)<br/><br/>**Wenn die maximale Anzahl von Anrufen erreicht wird** Wenn die Anruf Warteschlange die maximale Größe (unter Verwendung der Einstellung **Maximum von Anrufen in der Warteschlange** festgelegt) erreicht, können Sie auswählen, was passiert, um neue eingehende Anrufe.
*    **Mit Besetztzeichen trennen**: Der Anruf wird getrennt.
*    **In diesem Anruf weiterleiten an** Wenn Sie diese Option wählen, müssen Sie diese Optionen:
     *    **Person in Ihrem Unternehmen** Ein Online-Benutzer mit einer Lizenz **Telefonsystem** und für Enterprise-VoIP aktiviert sein oder aufrufen planen. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Zu diesem Zweck wählen Sie eine **Person in Ihrem Unternehmen** , und legen Sie diese Person ihre Anrufe an die Voicemail weitergeleitet werden. <br/> <br/>Informationen zur Lizenzierung für Voicemail erforderlich sind, finden Sie unter [Einrichten von Voicemail Telefonsystem](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md). 
     
        > [!Note]
        > Benutzer gehostet: lokal mit Lync Server 2010 werden nicht unterstützt.<br/>
     
     *    **Aufrufen der Warteschlange** Müssen Sie bereits erstellt haben andere Warteschleife der Anruf, aber nach dem Sie dies tun, können Sie diese Warteschlange Anruf auswählen.
     *    **Automatische Telefonzentrale** Sie müssen bereits erstellt haben eine automatische Telefonzentrale, aber nach dem Sie dies tun, können Sie diese automatische Telefonzentrale auswählen. Finden Sie unter [Einrichten von einer Telefonzentrale Telefonsystem](set-up-a-phone-system-auto-attendant.md).
***
![Nummer 3](../images/sfbcallout3.png)<br/><br/>**Wie lange ein Anruf in der Warteschlange warten kann**: Sie können auch entscheiden, wie lange ein Anruf in der Warteschleife gehalten werden kann, bis es zu einem Timeout kommt und der Anruf umgeleitet werden muss. Wohin der Anruf umgeleitet wird, hängt von Ihrer Einstellung für **Wenn das Zeitlimit eines Anrufs überschritten ist** ab. Sie können eine Dauer von 0 bis 45 Minuten festlegen. <br/><br/> Der Timeoutwert kann in Sekunden in Intervallen von 15 Sekunden festgelegt werden. Dadurch können Sie den Anruffluss mit feinere Granularität bearbeiten. Beispielsweise könnten Sie angeben, dass alle Anrufe, die nicht innerhalb von 30 Sekunden von einem Agent beantwortet werden zu einer Directory Search-Telefonzentrale wechseln. 

***
![Nummer 4](../images/sfbcallout4.png)<br/><br/>**Wenn das Zeitlimit eines Anrufs überschritten ist**: Wenn der Anruf das Limit erreicht, das Sie für die Einstellung **Wie lange ein Anruf in der Warteschlange warten kann** festgelegt haben, können Sie auswählen, was mit den in der Anrufwarteschleife wartenden Anrufen geschieht:
*    **Trennen**: Der Anruf wird getrennt.
*    **In diesem Anruf weiterleiten an** Wenn Sie diese Option wählen, müssen Sie diese Optionen:
     *    **Person in Ihrem Unternehmen** Ein Online-Benutzer mit einer Lizenz **Telefonsystem** und für Enterprise-VoIP aktiviert sein oder plant aufrufen. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Zu diesem Zweck wählen Sie eine **Person in Ihrem Unternehmen** , und legen Sie diese Person ihre Anrufe an die Voicemail weitergeleitet werden. </br><br/>  Informationen zur Lizenzierung für Voicemail erforderlich sind, finden Sie unter [Einrichten von Voicemail Telefonsystem](../what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail.md). 

        > [!Note]
        > Benutzer gehostet: lokal mit Lync Server 2010 werden nicht unterstützt.<br/>

     *    **Aufrufen der Warteschlange** Müssen Sie bereits erstellt haben andere Warteschleife der Anruf, aber nach dem Sie dies tun, können Sie diese Warteschlange Anruf auswählen.
     *    **Automatische Telefonzentrale** Sie müssen bereits erstellt haben eine automatische Telefonzentrale, aber nach dem Sie dies tun, können Sie diese automatische Telefonzentrale auswählen. Finden Sie unter [Einrichten von einer Telefonzentrale Telefonsystem](set-up-a-phone-system-auto-attendant.md).
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Ändern der Anrufer-ID des Benutzers, um einen Anruf Warteschlange Telefonnummer werden sollen

Sie können die Identität eines Benutzers schützen, durch ihre Anrufer-ID für die ausgehende Anrufe an eine Warteschleife Anruf stattdessen durch Erstellen einer Richtlinie mit dem Cmdlet **New-CallingLineIdentity** ändern.
  
Zu diesem Zweck führen Sie Folgendes aus:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Wenden Sie die Richtlinie für den Benutzer mit dem Cmdlet **Grant-CallingLineIdentity** . Zu diesem Zweck führen Sie Folgendes aus:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Erhalten Sie weitere Informationen zum Anrufer-ID-Einstellungen in Ihrer Organisation ändern [hier](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="want-to-know-more"></a>Möchten Sie mehr wissen?

Sie können auch Windows PowerShell verwenden, um automatische Telefonzentralen zu erstellen und einzurichten.
  
### <a name="call-queue-cmdlets"></a>Cmdlets für Anrufwarteschleifen

Zum Verwalten einer Anrufwarteschleife benötigen Sie die folgenden Cmdlets.
  
- [Neue CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [Set-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [Get-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [Remove-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### <a name="more-about-windows-powershell"></a>Weitere Informationen zu Windows PowerShell

- In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See Also
[Das bietet Ihnen das Telefonsystem in Office 365](here-s-what-you-get-with-phone-system.md)

[Anfordern von Servicenummern für Skype for Business und Microsoft Teams](getting-service-phone-numbers.md)

[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

  
 