---
title: Erstellen einer Warteschlange für das Telefonsystem
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options.
ms.openlocfilehash: f22b840bfde011937305732e61748d8a1feae390
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "30633274"
---
# <a name="create-a-phone-system-call-queue"></a>Erstellen einer Warteschlange für das Telefonsystem

System-Telefonanruf Warteschlangen enthalten Ansage, die verwendet werden, wenn angerufen eine Rufnummer für Ihre Organisation die Möglichkeit, die Anrufe automatisch gehalten wird und für den nächsten verfügbaren Anruf-Agent zum Verarbeiten des Anrufs beim Personen die Möglichkeit zum Suchen, die Anruf Musik in der Warteschleife hören sind. Sie können einzelne oder mehrere Anruf Warteschlangen für Ihre Organisation erstellen.
  
Telefonsystem-Anrufwarteschleifen bieten:
  
- Eine Begrüßung der Organisation
- Musik, während die wartenden Anrufer gehalten werden
- Umleiten von Anrufen Agents in e-Mail-aktivierte Verteilerlisten und Sicherheitsgruppen aufrufen.
- Einstellungen für Anruf Warteschlange maximale Größe, Timeout und Optionen für die Behandlung Anruf tätigen.

Wenn Sie an eine Telefonnummer angerufen werden, das eine Warteschlange Anruf über ein [Benutzerkonto Ressource](manage-resource-accounts.md)zugeordnet ist, hören sie eine Begrüßung erste (sofern eine eingerichtet ist), und anschließend wird in die Warteschlange aufgenommen werden und für den nächsten verfügbaren Anruf Agent warten. Die Person einwählen, werden Musik hören, während sie sind in der Warteschleife warten, und die Anrufe, um den Anruf-Agenten auf *First In, First Out* (FIFO) Reihenfolge angeboten werden.
  
Alle Anrufe, die in der Warteschlange werden mit einer attendant routing oder serielles routing Modus verteilt werden:
  
- Mit attendant routing wird der erste Aufruf in der Warteschlange alle Agents gleichzeitig anrufen.
- Mit seriellem Routing (serial routing) wird der erste Aufruf in der Warteschleife alle Telefonisten nacheinander anrufen.

    > [!NOTE]
    > Telefonisten, die **Offline**sind, ihre Anwesenheit auf **Nicht stören** festgelegt haben, oder haben sich von der Warteschleife abgemeldet haben, werden nicht angerufen.
  
- Es wird nur jeweils eine Benachrichtigung über einen eingehenden Anruf (für den ersten Anruf in der Warteschleife) an die Telefonisten gesendet.
- Wenn ein Telefonist den Anruf angenommen hat, klingelt der nächste eingehende Anruf aus der Warteschleife bei den Telefonisten.

> [!NOTE]
> Dieser Artikel bezieht sich auf Microsoft-Teams und Skype für Business Online.

## <a name="step-1---get-started"></a>Schritt 1: Erste Schritte

Die folgenden Punkte sind bei Ihrem Einstieg in die Verwendung von Anrufwarteschleifen wichtig:
  
- Ihre Organisation muss eine Lizenz Enterprise E3 plus **Telefonsystem** oder einer E5 Enterprise-Lizenz (mindestens) verfügen. Die Anzahl der **Telefonsystem** Benutzerlizenzen, die zugewiesen sind, wirkt sich auf die Anzahl der Dienst Zahlen, die für Anruf Warteschlangen zu verwendende verfügbar sind. Die Anzahl der Anruf Warteschlangen haben Sie können ist abhängig von der Anzahl der **Telefonsystem** und **Audiokonferenzen** Lizenzen, die in Ihrer Organisation zugewiesen sind. Weitere Informationen zu Lizenzierung finden Sie unter [Skype für Business Add-on Lizenzierung](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing) oder [Microsoft-Teams, Add-On-Lizenzierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) .

    > [!NOTE]
    > Zum Umleiten von Anrufen an Personen in Ihrer Organisation, die Online sind, sie benötigen eine Lizenz **Telefonsystem** und für Enterprise-VoIP aktiviert sein oder Office 365 aufrufen Plans. Finden Sie unter [Skype für Business Lizenzen zuweisen](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) oder [Lizenzen für Microsoft-Teams zuweisen](assign-teams-licenses.md). Um diese Lizenzen für Enterprise-VoIP zu aktivieren, können Sie die Windows PowerShell verwenden. Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Weitere Informationen zu Office 365 Anrufplänen finden Sie unter [Was sind Anrufpläne in Office 365?](what-are-calling-plans-in-office-365.md) und [Anrufpläne für Office 365](calling-plans-for-office-365.md).

    > [!NOTE]
    > Benutzer: lokal gehostet werden nicht mithilfe von Lync Server 2010 als Anruf Warteschlange Agents unterstützt.
  
- Sie können nur zuweisen gebührenpflichtige oder gebührenfreie Service Telefonnummern, die Sie haben Sie in der **Microsoft-Teams, Administrationscenter** oder aus einem anderen Dienstanbieter in Telefonsystem Anruf Warteschlangen übertragen. Um gebührenfreie Servicenummern zu erhalten müssen Sie Communication Credits einrichten.

    > [!NOTE]
    > Telefonnummern von Benutzern (Abonnenten) können Anrufwarteschleifen nicht zugewiesen werden - es können nur gebührenpflichtige oder gebührenfreie Telefonnummern verwendet werden.
  
- Wenn Sie eingehende Anrufe von einer Telefonsystem Anruf Warteschlange verteilen, werden diese Clients für Call-Agenten unterstützt:

  - Desktopclient von Skype for Business 2016 (32- und 64-Bit-Version)

  - Desktopclient von Lync 2013 (32- und 64-Bit-Version)

  - Alle IP-Telefon-Modelle für die Microsoft-Teams, unterstützt. Weitere Informationen finden Sie unter [Kauf von Telefonen für Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).

  - Mac Skype for Business-Client (Version 16.8.196 und höher)

  - Android Skype for Business-Client (Version 6.16.0.9 und höher)

  - iPhone Skype for Business-Client (Version 6.16.0 und höher)

  - Mac Skype for Business-Client (Version 6.16.0 und höher)

  - Microsoft Teams Windows-Client (32- und 64-Bit-Versionen)

  - Microsoft Teams Mac-Client

  - Microsoft-Teams, iPhone-app

  - Microsoft-Teams, Android-app

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Schritt 2 - Beziehen oder Übertragen von gebührenpflichtigen oder gebührenfreien Servicenummern

Bevor Sie Ihre Anrufwarteschleifen erstellen und einrichten können, müssen Sie Ihre bestehenden kostenpflichtigen oder gebührenfreien Servicenummern einrichten oder übertragen. Nachdem Sie die gebührenpflichtige oder gebührenfreie Service Telefonnummern erhalten möchten, sie werden angezeigt, in der **Microsoft-Teams, Administrationscenter** > **VoIP** > **Telefonnummern**und die **Typ-Nummer** aufgeführt wird als **Dienst - gebührenfreie**aufgeführt werden. Um die Rufnummern Service erhalten möchten, finden Sie unter [Getting Service Rufnummern](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) oder wenn Sie eine vorhandene Servicenummer durchstellen möchten, finden Sie unter [Weiterleiten von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Wenn Sie sich außerhalb der USA sind, können das Microsoft-Teams, Administrationscenter Sie um Service Zahlen zu erhalten. Wechseln Sie zum [Verwalten von Rufnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) stattdessen, wie Sie von außerhalb der USA finden Sie unter.

Wenn Sie auch automatische Telefonzentralen festlegen, müssen Sie nur die wichtigsten Telefonzentrale Ressourcenkonto weisen Sie eine Telefonnummer ein, und klicken Sie dann direkte Anrufer an die Warteschlange Anruf. Wenn dies der Fall ist, müssen die Anruf-Warteschlange erstellt werden, bevor Sie eine Option in der automatischen Telefonzentrale erstellen können, die die Warteschlange Anruf auswählt.
  
## <a name="step-3---create-a-new-call-queue"></a>Schritt 3: Erstellen einer neuen Warteschleife der Anruf

> [!IMPORTANT]
> Jeder Anruf Warteschlange ist erforderlich, um einer zugeordneten [Ressource-Konto](manage-resource-accounts.md)haben. Sie müssen das Ressourcenkonto erstellen und dann können Sie es an die Warteschlange Anruf zuordnen.

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden das Microsoft-Teams, Administrationscenter

In der **Microsoft-Teams, Administrationscenter**, **VoIP** >  **aufrufen, Warteschlangen**, klicken Sie dann auf **+ Neues hinzufügen**:

### <a name="set-the-call-queue-display-name-and-resource-account"></a>Festlegen des Anruf Warteschlange Display Name und Ressource-Kontos

![Setting up a call queue.](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

![Nummer 1](media/sfbcallout1.png)
**Name** Geben Sie einen aussagekräftigen Anzeigenamen für die Warteschlange Anruf. Der Name ist erforderlich und kann maximal 64 Zeichen einschließlich Leerzeichen enthalten.

 Dieser Name wird in der Benachrichtigung über den eingehenden Anruf angezeigt.

* * *

![Nummer 2](media/sfbcallout2.png)

**Hinzufügen von Konten** Wählen Sie eine Ressourcenkonto. Das Ressourcenkonto kann oder keiner Service gebührenpflichtige oder gebührenfreie Telefonnummer für die Warteschlange Anruf zugeordnet werden, aber jeder Anruf Warteschlange einer zugeordneten Ressourcenkonto erforderlich.

Wenn keine vorhanden sind aufgeführt, Sie müssen Service Zahlen und weisen Sie diesem Kontakt ein Ressourcenkonto vor der Erstellung dieser Warteschlange Anruf wie oben beschrieben. Um die Rufnummern Service erhalten möchten, finden Sie unter [Getting Service Rufnummern](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json). Sie müssen ein Ressourcenkonto wie unter [Verwalten Ressourcenkonten in Teams](manage-resource-accounts.md) , wenn Sie Ihre Anruf Warteschlange eine jeweilige Rufnummer haben soll erstellen.

> [!NOTE]
> Wenn Sie möchten oder einer **Domäne zuweisen müssen** würden Sie dazu das Ressourcenkonto für die Warteschlange Anruf zuweisen.

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Festlegen der Begrüßung und der Wartemusik, die wiedergegeben werden soll

![Setting up a call queue.](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
* * *

![Nummer 1](media/sfbcallout1.png)

**Begrüßung** ist optional. Dies ist die Ansage, die für Personen, die in Aufrufen an die Warteschlange Anrufnummer wiedergegeben wird.

Sie können eine Audiodatei (WAV-, MP3 oder WMA-Format) hochladen.

![Nummer 2](media/sfbcallout2.png)

**Musik in der Warteschleife** Sie können entweder übernehmen Sie die Musik in der Warteschleife, die mit der Warteschlange Anruf bereitgestellt, oder Sie können Hochladen einer Audiodatei in WAV, mp3 oder WMA-Formate, die als Ihre benutzerdefinierte Musik in der Warteschleife verwendet.

* * *

### <a name="select-the-call-answering-options"></a>Wählen Sie die Optionen für die Anrufbeantwortung

![Zeigt die Optionen für Anruf-Verteilungsmethoden an](media/5d249515-d532-4af2-90da-011404028b89.png)

![Nummer 1](media/sfbcallout1.png)

Sie können bis zu 200 Anruf Agents, die angegebene Verteilerlisten oder Gruppen auswählen. Call-Agenten müssen Folgendes sein:

- Ein Online-Benutzer mit einer **Telefonsystem**-Lizenz und Enterprise Voice oder einem Anrufplan.

  > [!NOTE]
  > Zum Umleiten von Anrufen an Personen in Ihrer Organisation, die Online sind, sie benötigen eine Lizenz **Telefonsystem** und für Enterprise-VoIP aktiviert sein oder aufrufen planen. Finden Sie unter [Skype für Business Lizenzen zuweisen](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) oder [Lizenzen für Microsoft-Teams zuweisen](assign-teams-licenses.md).

 Um diese Lizenzen für Enterprise-VoIP zu aktivieren, können Sie die Windows PowerShell verwenden. Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- Online-Benutzer mit einer **Telefonsystem**-Lizenz und einem Anrufplan, die einer Office 365-Gruppe, einer e-Mail-Verteilerliste oder einer Sicherheitsgruppe hinzugefügt worden sind. Es kann bis zu 30 Minuten dauern, bis ein neuer Telefonist zu einer Verteilerliste oder Sicherheitsgruppe hinzugefügt wird und Anrufe aus einer Anrufwarteschleife empfangen kann. Eine neu erstellte Liste oder eine Sicherheitsgruppe Verteilergruppe kann die Verwendung mit dem Anruf Warteschlangen verfügbar bis zu 48 Stunden dauern. Neu erstellte Office 365-Gruppen sind fast sofort verfügbar.

  > [!NOTE]
  > Benutzer gehostet: lokal mit Lync Server 2010 werden nicht unterstützt.

![Set up call queues.](media/skype-for-business-add-agents-to-call-queue.png)

![Nummer 2](media/sfbcallout2.png)

**Routingmethode** Sie können entweder **Attendant**, **seriellen**oder **Roundrobin** für Ihre Anruf Warteschlange Verteilungsmethode auswählen. Alle neuen und vorhandenen Anrufwarteschleifen sind standardmäßig auf Teilnehmer-Routing (attendant routing) eingestellt. Wenn attendant routing verwendet wird, wird der erste Aufruf in der Warteschlange alle Agents Anruf gleichzeitig Anrufen aus. Der erste Aufruf Agent den Anruf übernehmen Ruft den Anruf ab.

- **Attendant routing** bewirkt, dass den ersten Aufruf in der Warteschlange alle Anruf Agents gleichzeitig angeboten werden soll. Der erste Aufruf Agent den Anruf übernehmen Ruft den Anruf ab.
- **Serielles routing** bewirkt, dass eingehende Anrufe Call-Agenten jeweils ab dem Anfang der Anrufliste Agent angeboten werden soll. Wenn ein Telefonist einen Anruf ablehnt oder nicht annimmt, wird der nächste Telefonist auf der Liste angerufen und ein Telefonist nach dem anderen versucht, bis der Anruf angenommen wird oder die maximale Zeit in der Warteschleife erreicht hat.
  > [!NOTE]
  > Serielles Routing überspringt Telefonisten, die **Offline** sind, ihren Anwesenheitsstatus auf **Nicht stören**festgelegt haben oder sich von Anrufen aus dieser Anrufwarteschleife**abgemeldet haben**.
- **Round-Robin** ausgeglichen routing eingehender Anrufe, sodass jeder Anruf-Agent die gleiche Anzahl von Anrufen aus der Warteschlange abgerufen wird. Dies kann in einer eingehenden sales-Umgebung um die gleiche Chancen zwischen den Call-Agenten sicherzustellen sehr wünschenswert sein.

### <a name="select-an-agent-opt-out-option"></a>Wählen Sie eine Option für das Abmelden von Telefonisten

![Zeigt das Abmeldungs-Kontrollkästchen des Telefonisten](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
* * *

![Nummer 1](media/sfbcallout1.png)

**Option Abmeldung für Telefonisten** Sie können es Telefonisten erlauben, sich von Anrufen von einer bestimmten Anrufwarteschleife abzumelden, indem Sie die **Option Abmeldung für Telefonisten** auswählen.

Durch Aktivieren dieser Option ermöglicht, dass alle Agents in dieser Warteschlange zum Starten oder beenden annehmen von Anrufen aus dieser Warteschlange Anruf am wird. Sie können das die Möglichkeit, sich von Anrufen abzumelden, durch Deaktivieren des Kontrollkästchens jederzeit sperren, wodurch Telefonisten automatisch wieder für diese Anrufwarteschleife angemeldet werden (die Standardeinstellung für alle Telefonisten).

Um auf die Abmeldungsfunktion zuzugreifen können Telefonisten folgendes tun:

 1. Öffnen Sie **Optionen** in Skype for Business-Client auf ihrem Desktop.
 2. Klicken Sie in der Registerkarte **Anrufweiterleitung** auf den Link **Online-Einstellungen bearbeiten**.
 3. Klicken Sie auf der Einstellungsseite für Benutzer auf **Anrufwarteschleifen** und deaktivieren Sie die Kontrollkästchen für alle Warteschleifen, von denen sie sich abmelden möchten.

    > [!NOTE]
    > Mithilfe der Mac-, Mobile oder Lync 2013-Clients oder Hybrid-VoIP-Benutzern, die lokal auf einem Skype for Business 2015 Server gehostet werden, können Telefonisten die Abmeldungsoption über [https://aka.ms/cqsettings](https://aka.ms/cqsettings) aufrufen.

![Nummer 2](media/sfbcallout2.png)
**Agent Alert Einstellung**

Hierdurch wird die Dauer der Agent eines Aufrufs vor seriell benachrichtigt wird, oder verschieben Sie Roundrobin Routingmethoden zum nächsten Agenten.

Die Standardeinstellung ist 30 Sekunden, aber sie können für bis zu drei Minuten festgelegt werden.

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a>Legen Sie den Anruf Überlauf und Timeout Behandlung-Optionen

![Set up a call queue.](media/3f018734-16fe-458b-827d-71fc25155cde.png)
  
* * *

![Nummer 1](media/sfbcallout1.png)

**Maximale Anrufe in der Warteschlange**: Legen Sie mit dieser Option fest, wie lange Anrufe maximal in der Warteschleife warten können, bis es zu einem Timeout kommt. Der Standardwert ist 50, aber es kann im Bereich von 0 bis 200. Wenn dieses Limit erreicht ist, wird der Anruf gemäß Ihrer Angabe für die Einstellung **Wenn die maximale Anzahl der Anrufe erreicht ist** (siehe unten) behandelt.

* * *

![Nummer 2](media/sfbcallout2.png)

**Wenn die maximale Anzahl von Anrufen erreicht wird** Wenn die Anruf Warteschlange die maximale Größe (unter Verwendung der Einstellung **Maximum von Anrufen in der Warteschlange** festgelegt) erreicht, können Sie auswählen, was passiert, um neue eingehende Anrufe.

- **Trennen**: Der Anruf wird getrennt.
- **Umleiten an** Wenn Sie diese Option wählen, wählen Sie eine der folgenden:

  - **Person in Ihrem Unternehmen** Ein Online-Benutzer mit einer Lizenz **Telefonsystem** und für Enterprise-VoIP aktiviert sein oder aufrufen planen. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Zu diesem Zweck wählen Sie eine **Person in Ihrem Unternehmen** , und legen Sie diese Person ihre Anrufe an die Voicemail weitergeleitet werden.

  Informationen zur erforderlichen Lizenzierung für Voicemail finden Sie unter [Einrichten von Telefonsystem-Voicemail](set-up-phone-system-voicemail.md).

    > [!Note]
    > Benutzer gehostet: lokal mit Lync Server 2010 werden nicht unterstützt.
  - **VoIP-Anwendung** Wählen Sie den Namen des entweder eine Warteschlange Anruf oder automatische um-Telefonzentrale, die bereits erstellt worden ist.

* * *

![Nummer 3](media/sfbcallout3.png)

**Timeout aufrufen: maximale Wartezeit** Sie können auch bestimmen, wie lange ein Anruf in der Warteschleife in der Warteschlange werden kann bevor es Timeout und umgeleitet oder getrennt werden muss. Wohin der Anruf umgeleitet wird, hängt von Ihrer Einstellung für **Wenn das Zeitlimit eines Anrufs überschritten ist** ab. Sie können eine Dauer von 0 bis 45 Minuten festlegen.

Der Timeoutwert kann in Sekunden in Intervallen von 15 Sekunden festgelegt werden. Dadurch können Sie den Anruffluss mit feinerer Granularität bearbeiten. Beispielsweise könnten Sie angeben, dass alle Anrufe, die nicht innerhalb von 30 Sekunden von einem Agent beantwortet werden zu einer Verzeichnissuche Telefonzentrale wechseln.

![Nummer 4](media/sfbcallout4.png)

**Wenn ein Anruf Timeout** Wenn der Aufruf den Grenzwert, den Sie für die Einstellung für **wie lange ein Anruf in der Warteschlange warten kann** festlegen erreicht, können Sie auswählen, was geschieht, um dieses Anrufs:

- **Trennen**: Der Anruf wird getrennt.
- **Dieser Aufruf umleiten** Wenn Sie diese Option wählen, müssen Sie diese Optionen:
  - **Person in Ihrem Unternehmen** Ein Online-Benutzer mit einer Lizenz **Telefonsystem** und für Enterprise-VoIP aktiviert sein oder plant aufrufen. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Zu diesem Zweck wählen Sie eine **Person in Ihrem Unternehmen** , und legen Sie diese Person ihre Anrufe an die Voicemail weitergeleitet werden.

  Informationen zur erforderlichen Lizenzierung für Voicemail finden Sie unter [Einrichten von Telefonsystem-Voicemail](set-up-phone-system-voicemail.md).

    > [!Note]
    > Benutzer gehostet: lokal mit Lync Server 2010 werden nicht unterstützt.

  - **VoIP-Anwendung** Wählen Sie den Namen des entweder eine Warteschlange Anruf oder automatische um-Telefonzentrale, die bereits erstellt worden ist.

## <a name="changing-a-users-caller-id-to-be-a-call-queues-phone-number"></a>Ändern der Anrufer-ID des Benutzers, um einen Anruf Warteschlange Telefonnummer werden sollen

Sie können die Identität eines Benutzers schützen, indem Sie seine Anrufer-ID für ausgehende Anrufe zu einer Rufnummer der Warteschleife ändern. Dazu müssen Sie mit dem Cmdlet **New-CallingLineIdentity** eine Richtlinie erstellen.

Zu diesem Zweck führen Sie Folgendes aus:

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Wenden Sie die Richtlinie für den Benutzer mit dem Cmdlet **Grant-CallingLineIdentity** an. Zu diesem Zweck führen Sie Folgendes aus:
  
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Sie erhalten weitere Informationen zum Anrufer-ID-Einstellungen in Ihrer Organisation im Artikel [wie kann Anrufer-ID verwendet werden in Ihrer Organisation](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization)zu ändern.
  
## <a name="want-to-know-more"></a>Möchten Sie mehr wissen?

Sie können auch Windows PowerShell verwenden, um automatische Telefonzentralen zu erstellen und einzurichten.
  
### <a name="call-queue-cmdlets"></a>Cmdlets für Anrufwarteschleifen

Zum Verwalten einer Anrufwarteschleife benötigen Sie die folgenden Cmdlets.
  
- [New-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796459.aspx)

- [Set-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796457.aspx)

- [Get-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796458.aspx)

- [Remove-CsHuntgroup](https://technet.microsoft.com/en-us/library/mt796456.aspx)

### <a name="more-about-windows-powershell"></a>Weitere Informationen zu Windows PowerShell

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 und eine zentrale Verwaltung Ihrer täglichen Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen, die mit Microsoft-Teams verwalten. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

  - [Einführung in Windows PowerShell und Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Warum Sie Office 365 PowerShell verwenden müssen](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell hat viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität über nur mithilfe der Verwaltungskonsole Microsoft-Teams, beispielsweise wenn Sie ändert sich die Einstellung für viele Benutzer gleichzeitig durchführen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:

  - [Verwalten von Office 365 mit Windows PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Verwandte Themen

[Das Telefonsystem in Office 365 bietet Ihnen Folgendes](here-s-what-you-get-with-phone-system.md)

[Abrufen von Diensttelefonnummern](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)

[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Neue CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
