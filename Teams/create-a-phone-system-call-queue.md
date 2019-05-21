---
title: Erstellen einer Anrufwarteschlange
ms.author: crowe
author: CarolynRowe
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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Hier erfahren Sie, wie Sie das Telefon System für Cloud-Anrufwarteschlangen einrichten, damit Sie eine organisatorische Begrüßung, Musik in Wartestellung und Umleiten von Anrufen an Anruf-Agents in Verteilerlisten und Sicherheitsgruppen erhalten. You can also set the maximum queue size, time out, and call handling options.
ms.openlocfilehash: 63dc71d6fad4fa82e1a335b20612e60c3b56ac91
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281947"
---
# <a name="create-a-cloud-call-queue"></a>Erstellen einer Cloudanrufwarteschleife

Zu den Cloud-Anrufwarteschlangen gehören Begrüßungen, die verwendet werden, wenn sich jemand an eine Telefonnummer für Ihre Organisation anmeldet, die Möglichkeit, die Anrufe automatisch zu halten, und die Möglichkeit, nach dem nächsten verfügbaren Anruf Agenten zu suchen, um den Anruf zu führen, während die Anrufteilnehmer Musik hören in Wartestellung. Sie können eine oder mehrere Anrufwarteschlangen für Ihre Organisation erstellen.
  
Cloud-Anrufwarteschlangen können Folgendes bereitstellen:
  
- Eine Begrüßung der Organisation
- Musik, während die wartenden Anrufer gehalten werden
- Umleiten von Anrufen an Anruf-Agents in e-Mail-aktivierten Verteilerlisten und Sicherheitsgruppen.
- Einstellungen für die maximale Größe, das Timeout und die Anruf Behandlungsoptionen für die Anrufwarteschlange

Wenn sich jemand über ein [Ressourcenkonto](manage-resource-accounts.md)an eine Telefonnummer anmeldet, die mit einer Anrufwarteschlange verbunden ist, hören Sie zuerst eine Begrüßung (sofern vorhanden), und Sie werden dann in die Warteschlange gestellt und auf den nächsten verfügbaren Anruf Agenten gewartet. Die Einberufungs Person hört Musik, während Sie in Wartestellung sind, und die Anrufe werden den Anruf-Agents in *First in First Out* (FIFO)-Reihenfolge angeboten.
  
Alle in der Warteschlange wartenden Anrufe werden mithilfe einer der folgenden Methoden verteilt:
  
- Beim Attendant-Routing klingelt der erste Anruf in der Warteschlange alle Agents gleichzeitig.
- Mit seriellem Routing (serial routing) wird der erste Aufruf in der Warteschleife alle Telefonisten nacheinander anrufen.
- Bei Round Robin wird das Routing von eingehenden Anrufen ausgeglichen, damit jeder Anruf-Agent die gleiche Anzahl von Anrufen aus der Warteschlange erhält.

    > [!NOTE]
    > Telefonisten, die **Offline**sind, ihre Anwesenheit auf **Nicht stören** festgelegt haben, oder haben sich von der Warteschleife abgemeldet haben, werden nicht angerufen.
  
- Es wird nur jeweils eine Benachrichtigung über einen eingehenden Anruf (für den ersten Anruf in der Warteschleife) an die Telefonisten gesendet.
- Wenn ein Telefonist den Anruf angenommen hat, klingelt der nächste eingehende Anruf aus der Warteschleife bei den Telefonisten.

> [!NOTE]
> Dieser Artikel bezieht sich auf Microsoft Teams und Skype for Business Online.

## <a name="step-1---get-started"></a>Schritt 1 – erste Schritte

Die folgenden Punkte sind bei Ihrem Einstieg in die Verwendung von Anrufwarteschleifen wichtig:
  
- Für eine Anrufwarteschlange ist ein zugeordnetes Ressourcenkonto erforderlich. Details zu Ressourcenkonten finden Sie unter [Verwalten von Ressourcenkonten in Teams](manage-resource-accounts.md) .
- Wenn Sie eine direkte Routing Nummer zuweisen möchten, müssen Sie die folgenden Lizenzen für Ihre Ressourcenkonten \(Office 365 Enterprise E1, E3 oder E5 mit dem Add-on\)Phone System erwerben und zuweisen.
- Wenn Sie stattdessen eine Microsoft-Dienstnummer zuweisen, müssen Sie dem Ressourcenkonto \(Office 365 Enterprise E1, E3 oder E5 mit dem Telefon System-Add-on und einem Anrufplan die folgenden Lizenzen erwerben und zuweisen\).
- Sie müssen die Ressourcenkonten nur mit einer Telefonnummer lizenzieren, die Ihnen zugewiesen ist. In einer geschachtelten automatischen Telefonzentrale oder Anrufwarteschlange müssen Sie die restlichen automatischen Telefonzentralen oder Anrufwarteschlangen nicht lizenzieren, wenn Ihnen keine Telefonnummern zugeordnet sind. 

> [!NOTE] 
> Direct Routing-Dienstnummern für die automatische Telefonzentrale und Anrufwarteschlangen werden nur für Microsoft Teams-Benutzer und-Agents unterstützt.

> [!NOTE] 
> Microsoft arbeitet an einem kostenlosen Lizenzierungsmodell für Anwendungen wie automatische Cloud-Telefonzentralen und Anrufwarteschlangen, denn jetzt müssen Sie das Benutzer Lizenzierungsmodell verwenden.

> [!NOTE]
> Um Anrufe an Personen in Ihrer Organisation umzuleiten, die Online sind, müssen Sie über eine **Telefon System** Lizenz verfügen und für Enterprise-VoIP aktiviert sein oder über Office 365-Anrufpläne verfügen. Weitere Informationen finden Sie unter [Zuweisen von Skype for Business-Lizenzen](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) oder [Zuweisen von Microsoft Teams-Lizenzen](assign-teams-licenses.md). Um diese Lizenzen für Enterprise-VoIP zu aktivieren, können Sie die Windows PowerShell verwenden. Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Weitere Informationen zu Office 365-Anrufplänen finden Sie unter [Telefon System-und Anrufpläne](calling-plan-landing-page.md) sowie [Anrufpläne für Office 365](calling-plans-for-office-365.md).

- Sie können nur gebührenpflichtige und gebührenfreie Telefonnummern für Dienstleistungen zuweisen, die Sie im **Microsoft Teams Admin Center** erhalten oder von einem anderen Dienstanbieter zu Cloud-Anrufwarteschlangen übertragen haben. Um gebührenfreie Servicenummern zu erhalten müssen Sie Communication Credits einrichten.

    > [!NOTE]
    > Telefonnummern von Benutzern (Abonnenten) können Anrufwarteschleifen nicht zugewiesen werden - es können nur gebührenpflichtige oder gebührenfreie Telefonnummern verwendet werden.
  
- Wenn Sie die eingehenden Anrufe aus einer Cloud-Anrufwarteschlange verteilen, werden diese Clients für Anruf-Agents unterstützt:

  - Desktopclient von Skype for Business 2016 (32- und 64-Bit-Version)

  - Desktopclient von Lync 2013 (32- und 64-Bit-Version)

  - Alle IP-Telefonmodelle, die für Microsoft Teams unterstützt werden. Weitere Informationen finden Sie unter [Kauf von Telefonen für Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).

  - Mac Skype for Business-Client (Version 16.8.196 und höher)

  - Android Skype for Business-Client (Version 6.16.0.9 und höher)

  - iPhone Skype for Business-Client (Version 6.16.0 und höher)

  - Mac Skype for Business-Client (Version 6.16.0 und höher)

  - Microsoft Teams Windows-Client (32- und 64-Bit-Versionen)

  - Microsoft Teams Mac-Client

  - Microsoft Teams-iPhone-App

  - Microsoft Teams Android-App

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Schritt 2 - Beziehen oder Übertragen von gebührenpflichtigen oder gebührenfreien Servicenummern

Bevor Sie Ihre Anrufwarteschleifen erstellen und einrichten können, müssen Sie Ihre bestehenden kostenpflichtigen oder gebührenfreien Servicenummern einrichten oder übertragen. Nachdem Sie die gebührenpflichtigen oder gebührenfreien Service-Telefonnummern erhalten haben, werden Sie in den **Microsoft Teams Admin Center** > **sprach** > **Telefonnummern**angezeigt, und der angegebene **Nummerntyp** wird als " **Dienst gebührenfrei**" aufgeführt. Informationen zum Abrufen Ihrer Dienstnummern finden Sie unter [Abrufen von Dienst](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) Telefonnummern oder wenn Sie eine vorhandene Servicenummer übertragen möchten, finden Sie unter [übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Wenn Sie sich außerhalb der Vereinigten Staaten befinden, können Sie das Microsoft Teams Admin Center nicht verwenden, um Dienstnummern zu erhalten. Wechseln Sie zu [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) , anstatt zu erfahren, wie Sie von außerhalb der Vereinigten Staaten aus Vorgehen.

Wenn Sie auch automatische Telefonzentralen einrichten, müssen Sie möglicherweise nur dem Ressourcenkonto der primären automatischen Telefonzentrale eine Telefonnummer zuweisen und dann Anrufer an Ihre Anrufwarteschlange weiterleiten. Wenn dies der Fall ist, muss die Anrufwarteschlange erstellt werden, bevor Sie eine Option in der automatischen Telefonzentrale erstellen können, mit der die Anrufwarteschlange ausgewählt wird.
  
## <a name="step-3---create-a-new-call-queue"></a>Schritt 3 – Erstellen einer neuen Anrufwarteschlange

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> Für jede Anrufwarteschlange ist ein zugeordnetes [Ressourcenkonto](manage-resource-accounts.md)erforderlich. Sie müssen zuerst das Ressourcenkonto erstellen, dann können Sie es der Anrufwarteschlange zuordnen.

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams admin Centers

Klicken Sie im **Microsoft Teams Admin Center**auf Warteschlangen für **sprach** >  **Anrufe**und dann auf **+ Neu hinzufügen**:

### <a name="set-the-call-queue-display-name-and-resource-account"></a>Einrichten des Anzeige namens und des Ressourcenkontos für die Anrufwarteschlange

![Setting up a call queue.](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

![](media/sfbcallout1.png)
**Name** der Nummer 1 geben Sie einen beschreibenden Anzeigenamen für die Anrufwarteschlange ein. Der Name ist erforderlich und kann maximal 64 Zeichen einschließlich Leerzeichen enthalten.

 Dieser Name wird in der Benachrichtigung über den eingehenden Anruf angezeigt.

* * *

![Nummer 2](media/sfbcallout2.png)

**Hinzufügen von Konten** Wählen Sie ein Ressourcenkonto aus. Das Ressourcenkonto ist möglicherweise mit einer Dienst gebührenpflichtigen oder gebührenfreien Telefonnummer für die Anrufwarteschlange verknüpft, aber für jede Anrufwarteschlange ist ein zugeordnetes Ressourcenkonto erforderlich.

Wenn keine Liste aufgeführt ist, müssen Sie Dienstnummern abrufen und Sie einem Ressourcenkonto zuweisen, bevor Sie diese Anrufwarteschlange wie zuvor beschrieben erstellen können. Informationen zum Abrufen Ihrer Dienstnummern finden Sie unter [Abrufen von Telefonnummern für Dienstleistungen](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json). Sie müssen ein Ressourcenkonto erstellen, wie unter [Verwalten von Ressourcenkonten in Teams](manage-resource-accounts.md) beschrieben, wenn Sie möchten, dass Ihre Anrufwarteschlange über eine zugeordnete Telefonnummer verfügt.

> [!NOTE]
> Wenn Sie eine **Domäne** zuweisen möchten, sollten Sie dies tun, indem Sie Sie dem Ressourcenkonto für die Anrufwarteschlange zuweisen.

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Festlegen der Begrüßung und der Wartemusik, die wiedergegeben werden soll

![Setting up a call queue.](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
* * *

![Nummer 1](media/sfbcallout1.png)

**Begrüßung** ist optional. Hierbei handelt es sich um die Ansage, die für Personen abgespielt wird, die die Anruf Warteschlangennummer anrufen.

Sie können eine Audiodatei (WAV-, MP3-oder WMA-Formate) hochladen.

![Nummer 2](media/sfbcallout2.png)

**Musik in Warte** Stellung Sie können entweder die standardmäßige Musik in der Warteschlange für die Anrufwarteschlange verwenden, oder Sie können eine Audiodatei in WAV-, MP3-oder WMA-Formaten hochladen, um Sie als benutzerdefinierte Musik in Wartestellung zu verwenden.

* * *

### <a name="select-the-call-answering-options"></a>Wählen Sie die Optionen für die Anrufannahme aus.

![Zeigt die Optionen für Anruf-Verteilungsmethoden an](media/5d249515-d532-4af2-90da-011404028b89.png)

![Nummer 1](media/sfbcallout1.png)

Sie können bis zu 200 Anruf-Agents auswählen, die zu bestimmten Mailinglisten oder Gruppen gehören. Anruf-Agents müssen entweder:

- Ein Online-Benutzer mit einer **Telefonsystem**-Lizenz und Enterprise Voice oder einem Anrufplan.

  > [!NOTE]
  > Um Anrufe an Personen in Ihrer Organisation umzuleiten, die Online sind, müssen Sie über eine **Telefon System** Lizenz verfügen und für Enterprise-VoIP aktiviert sein oder über einen Anrufplan verfügen. Weitere Informationen finden Sie unter [Zuweisen von Skype for Business-Lizenzen](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) oder [Zuweisen von Microsoft Teams-Lizenzen](assign-teams-licenses.md).

 Um diese Lizenzen für Enterprise-VoIP zu aktivieren, können Sie die Windows PowerShell verwenden. Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- Online-Benutzer mit einer **Telefonsystem**-Lizenz und einem Anrufplan, die einer Office 365-Gruppe, einer e-Mail-Verteilerliste oder einer Sicherheitsgruppe hinzugefügt worden sind. Es kann bis zu 3 Stunden dauern, bis ein neuer Agent für eine Verteilerliste oder eine Sicherheitsgruppe hinzugefügt wurde, um mit dem Empfang von Anrufen aus einer Anrufwarteschlange zu beginnen. Eine neu erstellte Verteilerliste oder Sicherheitsgruppe kann bis zu 48 Stunden dauern, bis Sie für die Verwendung mit Anrufwarteschlangen verfügbar ist. Neu erstellte Office 365-Gruppen sind fast sofort verfügbar.

![Set up call queues.](media/skype-for-business-add-agents-to-call-queue.png)

![Nummer 2](media/sfbcallout2.png)

**Routing Methode** Sie können für Ihre Verteilungsmethode für die Anrufwarteschlange entweder **Attendant**, **seriell**oder **Round Robin** auswählen. Alle neuen und vorhandenen Anrufwarteschleifen sind standardmäßig auf Teilnehmer-Routing (attendant routing) eingestellt. Wenn Attendant-Routing verwendet wird, klingelt der erste Anruf in der Warteschlange alle Anruf-Agents gleichzeitig. Der Anruf wird vom ersten Anruf Agenten abgeholt.

- Das **Attendant-Routing** bewirkt, dass der erste Anruf in der Warteschlange alle Anruf-Agents gleichzeitig klingelt. Der Anruf wird vom ersten Anruf Agenten abgeholt.
- Bei der seriellen weiter **Leitung** von eingehenden Anrufen werden die Anruf-Agents einzeln und ab dem Anfang der Anruf Agentenliste angerufen. Agents können nicht in der Liste der Anruf-Agents bestellt werden. Wenn ein Telefonist einen Anruf ablehnt oder nicht annimmt, wird der nächste Telefonist auf der Liste angerufen und ein Telefonist nach dem anderen versucht, bis der Anruf angenommen wird oder die maximale Zeit in der Warteschleife erreicht hat.
  > [!NOTE]
  > Serielles Routing überspringt Telefonisten, die **Offline** sind, ihren Anwesenheitsstatus auf **Nicht stören**festgelegt haben oder sich von Anrufen aus dieser Anrufwarteschleife**abgemeldet haben**.
- **Round Robin** balanciert das Routing von eingehenden Anrufen aus, damit jeder Anruf-Agent die gleiche Anzahl von Anrufen aus der Warteschlange erhält. Dies kann in einer eingehenden Vertriebsumgebung sehr wünschenswert sein, um die Chancengleichheit zwischen allen Anruf Agenten zu gewährleisten.

### <a name="select-an-agent-opt-out-option"></a>Wählen Sie eine Option für das Abmelden von Telefonisten

![Zeigt das Abmeldungs-Kontrollkästchen des Telefonisten](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
* * *

![Nummer 1](media/sfbcallout1.png)

**Option Abmeldung für Telefonisten** Sie können es Telefonisten erlauben, sich von Anrufen von einer bestimmten Anrufwarteschleife abzumelden, indem Sie die **Option Abmeldung für Telefonisten** auswählen.

Wenn Sie diese Option aktivieren, können alle Agents in dieser Warteschlange die Anrufe von dieser Anrufwarteschlange nach befolgen starten oder beenden. Sie können das die Möglichkeit, sich von Anrufen abzumelden, durch Deaktivieren des Kontrollkästchens jederzeit sperren, wodurch Telefonisten automatisch wieder für diese Anrufwarteschleife angemeldet werden (die Standardeinstellung für alle Telefonisten).

Um auf die Abmeldungsfunktion zuzugreifen können Telefonisten folgendes tun:

 1. Öffnen Sie **Optionen** in Skype for Business-Client auf ihrem Desktop.
 2. Klicken Sie in der Registerkarte **Anrufweiterleitung** auf den Link **Online-Einstellungen bearbeiten**.
 3. Klicken Sie auf der Einstellungsseite für Benutzer auf **Anrufwarteschleifen** und deaktivieren Sie die Kontrollkästchen für alle Warteschleifen, von denen sie sich abmelden möchten.

    > [!NOTE]
    > Agents, die apps oder Endpunkte mit Ausnahme von Skype for Business Desktop verwenden, können über das Benutzer Einstellungs [https://aka.ms/cqsettings](https://aka.ms/cqsettings)Portal auf die Option "ablehnen" zugreifen.

![Nummer 2](media/sfbcallout2.png)
-**Agent-Warnungseinstellung**

Damit wird festgelegt, wie lange ein Agent über einen Anruf benachrichtigt wird, bevor die seriellen oder Round Robin-Routingmethoden zum nächsten Agenten wechseln.

Die Standardeinstellung ist 30 Sekunden, kann aber für bis zu 3 Minuten festgelegt werden.

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a>Einrichten der Optionen für den Anruf Überlauf und die Timeout Behandlung

![Set up a call queue.](media/3f018734-16fe-458b-827d-71fc25155cde.png)
  
* * *

![Nummer 1](media/sfbcallout1.png)

**Maximale Anrufe in der Warteschlange**: Legen Sie mit dieser Option fest, wie lange Anrufe maximal in der Warteschleife warten können, bis es zu einem Timeout kommt. Der Standardwert ist 50, aber er kann zwischen 0 und 200 liegen. Wenn dieses Limit erreicht ist, wird der Anruf gemäß Ihrer Angabe für die Einstellung **Wenn die maximale Anzahl der Anrufe erreicht ist** (siehe unten) behandelt.

* * *

![Nummer 2](media/sfbcallout2.png)

**Wenn die maximale Anzahl von Anrufen erreicht ist** Wenn die Anrufwarteschlange die maximale Größe erreicht (festgelegt mit den **maximalen anrufen in der Warteschlangen** Einstellung), können Sie auswählen, was mit neuen eingehenden Anrufen geschieht.

- **Trennen**: Der Anruf wird getrennt.
- **Umleitung zu** Wenn Sie diese Option auswählen, wählen Sie eine der folgenden Optionen aus:

  - **Person in Ihrem Unternehmen** Einen Online Benutzer mit einer **Telefon System** Lizenz, der für Enterprise-VoIP aktiviert ist oder einen Anrufplan hat. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Wählen Sie dazu eine **Person in Ihrem Unternehmen** aus, und legen Sie fest, dass Ihre Anrufe direkt an Voicemail weitergeleitet werden.

  Informationen zur Lizenzierung, die für Voicemail erforderlich ist, finden Sie unter [Einrichten von Cloud-Voicemail](set-up-phone-system-voicemail.md).

  - **Sprachanwendung** Wählen Sie den Namen einer Anrufwarteschlange oder einer automatischen Telefonzentrale aus, die bereits erstellt wurde.

* * *

![Nummer 3](media/sfbcallout3.png)

**Anruf Timeout: maximale Wartezeit** Sie können auch entscheiden, wie viel Zeit ein Anruf in der Warteschlange halten kann, bevor er ein Zeitlimit überschritten hat, und er muss umgeleitet oder getrennt werden. Wohin der Anruf umgeleitet wird, hängt von Ihrer Einstellung für **Wenn das Zeitlimit eines Anrufs überschritten ist** ab. Sie können eine Dauer von 0 bis 45 Minuten festlegen.

Der Timeoutwert kann in Sekunden in Intervallen von 15 Sekunden festgelegt werden. Dadurch können Sie den Anruffluss mit feinerer Granularität bearbeiten. So können Sie beispielsweise festlegen, dass alle Anrufe, die von einem Agenten nicht innerhalb von 30 Sekunden beantwortet werden, zu einer automatischen Telefonzentrale für Verzeichnis suchen wechseln.

![Nummer 4](media/sfbcallout4.png)

**Beim Timeout** des Anrufs Wenn der Anruf den Grenzwert erreicht, den Sie für die **Wartezeit in der Warteschlangen** Einstellung festgelegt haben, können Sie auswählen, was mit diesem Anruf geschieht:

- **Trennen**: Der Anruf wird getrennt.
- **Diesen Anruf umleiten an** Wenn Sie diese Option auswählen, haben Sie folgende Optionen:
  - **Person in Ihrem Unternehmen** Einen Online Benutzer mit einer **Telefon System** Lizenz, der für Enterprise-VoIP aktiviert ist oder Anrufpläne hat. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Wählen Sie dazu eine **Person in Ihrem Unternehmen** aus, und legen Sie fest, dass Ihre Anrufe direkt an Voicemail weitergeleitet werden.

  Informationen zur Lizenzierung, die für Voicemail erforderlich ist, finden Sie unter [Einrichten von Cloud-Voicemail](set-up-phone-system-voicemail.md).

  - **Sprachanwendung** Wählen Sie den Namen einer Anrufwarteschlange oder einer automatischen Telefonzentrale aus, die bereits erstellt wurde.

## <a name="changing-a-users-caller-id-for-outbound-calls"></a>Ändern der Rufnummernanzeige eines Benutzers für ausgehende Anrufe 

Sie können die Identität eines Benutzers schützen, indem Sie dessen Rufnummernanzeige für ausgehende Anrufe an eine Anrufwarteschlange, eine automatische Telefonzentrale oder eine beliebige Dienstnummer ändern, indem Sie stattdessen eine Richtlinie mit dem Cmdlet **New-CsCallingLineIdentity** erstellen.

Führen Sie dazu die folgenden Aktionen aus:

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Wenden Sie die Richtlinie für den Benutzer mit dem Cmdlet **Grant-CallingLineIdentity** an. Führen Sie dazu die folgenden Aktionen aus:
  
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Weitere Informationen zum vornehmen von Änderungen an den Einstellungen für die Rufnummernanzeige in Ihrer Organisation finden Sie im Artikel [wie kann die Rufnummernanzeige in Ihrer Organisation verwendet werden](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization).
  
## <a name="want-to-know-more"></a>Möchten Sie mehr wissen?

Sie können auch Windows PowerShell verwenden, um automatische Telefonzentralen zu erstellen und einzurichten.
  
### <a name="call-queue-cmdlets"></a>Cmdlets für Anrufwarteschleifen

Zum Verwalten einer Anrufwarteschleife benötigen Sie die folgenden Cmdlets.
  
- [Neu – CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [Satz-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [Get-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a>Weitere Informationen zu Windows PowerShell

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 und Microsoft Teams mit einem zentralen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

  - [Einführung in Windows PowerShell und Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Warum Sie Office 365 PowerShell verwenden müssen](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell bietet zahlreiche Vorteile in Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft Teams Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Einstellungsänderungen vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:

  - [Verwalten von Office 365 mit Windows PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Verwandte Themen

[Das Telefonsystem in Office 365 bietet Ihnen Folgendes](here-s-what-you-get-with-phone-system.md)

[Abrufen von Diensttelefonnummern](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)

[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Neu – CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
