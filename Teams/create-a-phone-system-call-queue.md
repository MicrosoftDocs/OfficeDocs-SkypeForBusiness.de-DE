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
description: Hier erfahren Sie, wie Sie das Telefon System für Cloud-Anrufwarteschlangen mit Microsoft Teams einrichten.
ms.openlocfilehash: e4fa0b5ab5e5dd248d79286d071d9f5dcaed061f
ms.sourcegitcommit: fd5d48b36d70e3f42e029572fe003ee397db090d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2019
ms.locfileid: "36473362"
---
# <a name="create-a-cloud-call-queue"></a>Erstellen einer Cloudanrufwarteschleife

Cloud-Anrufwarteschlangen können Folgendes bereitstellen:

- Eine Grußnachricht.
- Musik, während die wartenden Anrufer gehalten werden
- Umleitung von Anrufen an Telefonisten in die von E-Mail-aktivierten Verteilerlisten und Sicherheitsgruppen
- Festlegen unterschiedlicher Parameter wie maximale Größe der Warteschlange, Timeout und Anruf Behandlungsoptionen.

Sie würden einer Anrufwarteschlange mithilfe eines [Ressourcenkontos](manage-resource-accounts.md)eine Telefonnummer zuweisen. Eine Anrufwarteschlange kann direkt gewählt oder über eine Auswahl in einer automatischen Telefonzentrale aufgerufen werden.

Der Anrufer hört Musik, während Sie in Wartestellung sind, und der Anruf stellt eine Verbindung mit den Anruf-Agents in *First in, First Out* (FIFO)-Reihenfolge her.

Alle Anrufe in der Warteschlange werden mithilfe einer der folgenden Methoden an Agents gesendet:

- Beim Attendant-Routing klingelt der erste Anruf in der Warteschlange alle Agents gleichzeitig.
- Beim seriellen Routing klingelt der erste Anruf in der Warteschlange alle Anruf-Agents einzeln.
- Bei Round Robin wird das Routing von eingehenden Anrufen ausgeglichen, damit jeder Anruf-Agent die gleiche Anzahl von Anrufen aus der Warteschlange erhält.

    > [!NOTE]
    > Anruf-Agents, die **Offline**sind, ihre Anwesenheit auf " **nicht stören** " festgelegt haben oder die Anrufwarteschlange deaktiviert haben, werden keine Anrufe empfangen.

- Nur eine Benachrichtigung über eingehende Anrufe (für den Anruf am Kopf der Warteschlange) geht zu einem Zeitpunkt an die Anruf Agenten.
- Wenn ein Telefonist den Anruf angenommen hat, klingelt der nächste eingehende Anruf aus der Warteschleife bei den Telefonisten.

> [!NOTE]
> Dieser Artikel bezieht sich auf Microsoft Teams und Skype for Business Online.

## <a name="step-1--get-started"></a>Schritt 1 – erste Schritte

Die folgenden Punkte sind bei Ihrem Einstieg in die Verwendung von Anrufwarteschleifen wichtig:

- Für eine Anrufwarteschlange ist ein zugeordnetes Ressourcenkonto erforderlich. Details zu Ressourcenkonten finden Sie unter [Verwalten von Ressourcenkonten in Teams](manage-resource-accounts.md) .
- Wenn Sie einem Ressourcenkonto eine Telefonnummer zuweisen, können Sie jetzt die ﻿kostenlose [virtuelle Benutzerlizenz](teams-add-on-licensing/virtual-user.md)für das Telefon System verwenden. Telefon System ermöglicht Telefonnummern auf Organisationsebene zur Verwendung mit kostengünstigen automatischen Telefonzentralen und Anrufwarteschlangen-Diensten.

> [!NOTE]
> Direct Routing-Dienstnummern für Anrufwarteschlangen werden nur für Microsoft Teams-Benutzer und-Agents unterstützt.

> [!NOTE]
> Um Anrufe an Personen in Ihrer Organisation umzuleiten, die Online sind, müssen Sie über eine **Telefon System** Lizenz verfügen und für Enterprise-VoIP aktiviert sein oder über Office 365-Anrufpläne verfügen. Weitere Informationen finden Sie unter [Zuweisen von Skype for Business-Lizenzen](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) oder [Zuweisen von Microsoft Teams-Lizenzen](assign-teams-licenses.md). Um diese Lizenzen für Enterprise-VoIP zu aktivieren, können Sie die Windows PowerShell verwenden. Führen Sie beispielsweise Folgendes aus:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- Weitere Informationen zu Office 365-Anrufplänen finden Sie unter [Telefon System-und Anrufpläne](calling-plan-landing-page.md) sowie [Anrufpläne für Office 365](calling-plans-for-office-365.md).

- Sie können nur Cloud-Anrufwarteschlangen gebührenpflichtige und gebührenfreie Service-Telefonnummern zuweisen, die Sie im **Microsoft Teams Admin Center** erhalten haben oder von einem anderen Dienstanbieter übertragen wurden. Für gebührenfreie Servicenummern sind Kommunikationsguthaben erforderlich.

    > [!NOTE]
    > Telefonnummern von Benutzern (Abonnenten) können Anrufwarteschleifen nicht zugewiesen werden - es können nur gebührenpflichtige oder gebührenfreie Telefonnummern verwendet werden.

- Die folgenden Clients werden für Anruf-Agents unterstützt, die einer Cloud-Anrufwarteschlange zugeordnet sind:

  - Skype for Business-Desktop Client 2016 (32-Bit-und 64-Bit-Versionen)

  - Lync-Desktop Client 2013 (32-Bit-und 64-Bit-Versionen)

  - Alle IP-Telefonmodelle, die für Microsoft Teams unterstützt werden. Weitere Informationen finden Sie unter [Kauf von Telefonen für Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).

  - Mac Skype for Business-Client (Version 16.8.196 und höher)

  - Android Skype for Business-Client (Version 6.16.0.9 und höher)

  - iPhone Skype for Business-Client (Version 6.16.0 und höher)

  - Mac Skype for Business-Client (Version 6.16.0 und höher)

  - Microsoft Teams Windows-Client (32-Bit-und 64-Bit-Versionen)

  - Microsoft Teams Mac-Client

  - Microsoft Teams-iPhone-App

  - Microsoft Teams Android-App

## <a name="step-2--getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>Schritt 2: Abrufen oder übertragen von gebührenpflichtigen oder gebührenfreien Telefonnummern für Dienstleistungen

Bevor Sie Ihre Anrufwarteschlangen erstellen und einrichten können, müssen Sie Ihre vorhandenen gebührenpflichtigen oder gebührenfreien Servicenummern abrufen oder übertragen. Nachdem Sie die gebührenpflichtigen oder gebührenfreien Service**** > -Telefonnummern erhalten haben, werden Sie in den **Microsoft Teams Admin Center** > **-Legacy-Portal** > -**Telefonnummern**angezeigt, und der **Nummerntyp** wird als **Service – gebührenfrei**. Informationen zum Abrufen Ihrer Dienstnummern finden Sie unter [Abrufen von Dienst](getting-service-phone-numbers.md) Telefonnummern oder wenn Sie eine vorhandene Servicenummer übertragen möchten, finden Sie unter [übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).

> [!NOTE]
> Wenn Sie sich außerhalb der Vereinigten Staaten befinden, können Sie das Microsoft Teams Admin Center nicht verwenden, um Dienstnummern zu erhalten. Wechseln Sie zu [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) , anstatt zu erfahren, wie Sie von außerhalb der Vereinigten Staaten aus Vorgehen.

Wenn Sie mehrere automatische Telefonzentralen einrichten, können Sie dem Hauptkonto der automatischen Telefonzentrale nur eine Telefonnummer zuweisen, mit der Anrufer an Ihre Anrufwarteschlangen oder geschachtelte automatische Telefonzentralen weitergeleitet werden können. In diesen Situationen erstellen Sie alle automatischen Telefonzentralen und Anrufwarteschlangen in Ihrem System, ohne dass Sie die Optionen für die Wähltasten zuweisen, und bearbeiten die Einstellungen später. Dies ist erforderlich, da Sie keine Option erstellen können, die mit einer Anrufwarteschlange oder einer automatischen Telefonzentrale verknüpft ist, die noch nicht vorhanden ist.

## <a name="step-3--create-a-new-call-queue"></a>Schritt 3: Erstellen einer neuen Anrufwarteschlange

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> Für jede Anrufwarteschlange ist ein zugeordnetes [Ressourcenkonto](manage-resource-accounts.md)erforderlich. Sie müssen zuerst das Ressourcenkonto erstellen, dann können Sie es der Anrufwarteschlange zuordnen.

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams admin Centers

Klicken Sie im **Microsoft Teams Admin Center**auf Warteschlangen für **sprach** > **Anrufe**und dann auf **+ Neu hinzufügen**:

### <a name="set-the-call-queue-display-name-and-resource-account"></a>Einrichten des Anzeige namens und des Ressourcenkontos für die Anrufwarteschlange

![Screenshot einer neuen Anrufwarteschlange mit nummerierten Beschriftungen](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

![Symbol der Zahl 1, die auf eine Legende im vorherigen Screenshot](media/sfbcallout1.png)
-**Namen** verweist, geben Sie einen beschreibenden Anzeigenamen für die Anrufwarteschlange ein. Dieser Name ist erforderlich und kann bis zu 64 Zeichen enthalten, einschließlich Leerzeichen.

 Dieser Name wird in der Benachrichtigung für den eingehenden Anruf angezeigt.

* * *

![Symbol der Zahl 2, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout2.png)

**Hinzufügen von Konten** Wählen Sie ein Ressourcenkonto aus. Das Ressourcenkonto ist möglicherweise mit einer Dienst gebührenpflichtigen oder gebührenfreien Telefonnummer für die Anrufwarteschlange verknüpft, aber für jede Anrufwarteschlange ist ein zugeordnetes Ressourcenkonto erforderlich.

Wenn keine Liste aufgeführt ist, müssen Sie Dienstnummern abrufen und Sie einem Ressourcenkonto zuweisen, bevor Sie diese Anrufwarteschlange wie zuvor beschrieben erstellen können. Informationen zum Abrufen Ihrer Dienstnummern finden Sie unter [Abrufen von Telefonnummern für Dienstleistungen](getting-service-phone-numbers.md). Sie erstellen ein Ressourcenkonto, wie unter [Verwalten von Ressourcenkonten in Teams](manage-resource-accounts.md) beschrieben, wenn Sie möchten, dass Ihre Anrufwarteschlange über eine zugeordnete Telefonnummer verfügt.

> [!NOTE]
> Wenn Sie eine **Domäne** zuweisen möchten, sollten Sie dies tun, indem Sie Sie dem Ressourcenkonto für die Anrufwarteschlange zuweisen.

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Festlegen der Begrüßung und der Wartemusik, die wiedergegeben werden soll

![Screenshot der Optionen für Begrüßung und Musik mit nummerierten Beschriftungen](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

![Symbol der Zahl 1, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout1.png)

**Begrüßung** ist optional. Hierbei handelt es sich um die Ansage, die für Personen abgespielt wird, die die Anruf Warteschlangennummer anrufen.

Sie können eine Audiodatei (WAV-, MP3-oder WMA-Formate) hochladen.

![Symbol der Zahl 2, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout2.png)

**Musik in Warte** Stellung Sie können entweder die standardmäßige Musik in der Warteschlange für die Anrufwarteschlange verwenden, oder Sie können eine Audiodatei in WAV-, MP3-oder WMA-Formaten hochladen, um Sie als benutzerdefinierte Musik in Wartestellung zu verwenden.

* * *

### <a name="select-the-call-answering-options"></a>Wählen Sie die Optionen für die Anrufannahme aus.

![Screenshot der Optionen für die Anrufannahme mit nummerierten Beschriftungen](media/5d249515-d532-4af2-90da-011404028b89.png)

![Symbol der Zahl 1, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout1.png)

Sie können bis zu 200-Anruf-Agents auswählen, die zu einer der folgenden Mailinglisten oder-Gruppen gehören:

- Office 365-Gruppe
- Sicherheitsgruppe
- Verteilerliste

Ausgewählte Anruf-Agents müssen **entweder** Online-Benutzer mit einer **Telefon System** Lizenz und Enterprise-VoIP sein **oder** über einen Anrufplan verfügen.

  > [!NOTE]
  > Dies gilt auch, wenn Sie Anrufe an Personen in Ihrer Organisation umleiten möchten, die Online sind. Diese Personen müssen über eine **Telefon System** Lizenz und Enterprise-VoIP verfügen **oder** über einen Anrufplan verfügen. Weitere Informationen finden Sie unter [Zuweisen von Lizenzen für Skype for Business](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [Zuweisen von Microsoft Teams-Lizenzen](https://docs.microsoft.com/microsoftteams/assign-teams-licenses)oder [der richtige Anrufplan für Sie?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)

 Um einen Agenten für Enterprise-VoIP zu aktivieren, können Sie Windows PowerShell verwenden. Führen Sie beispielsweise Folgendes aus:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- Benutzer mit einer **Telefon System** Lizenz oder einem Anrufplan, die einer Office 365-Gruppe hinzugefügt werden eine e-Mail-aktivierte Verteilerliste oder eine Sicherheitsgruppe. Es kann bis zu drei Stunden dauern, bis ein neu hinzugefügter Agent in einer Verteilerliste oder einer Sicherheitsgruppe Anrufe von einer Anrufwarteschlange empfängt. Eine neu erstellte Verteilerliste oder Sicherheitsgruppe kann bis zu 48 Stunden dauern, bis Sie für die Verwendung mit Anrufwarteschlangen verfügbar ist. Neu erstellte Office 365-Gruppen sind fast sofort verfügbar.

- Wenn Ihre Agents die Microsoft Teams-App zum Annehmen von Anruf Warteschlangen anrufen verwenden, müssen Sie sich im TeamsOnly-Modus befinden.

![Screenshot des Bereichs "Anruf-Agents hinzufügen"](media/skype-for-business-add-agents-to-call-queue.png)

![Symbol der Zahl 2, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout2.png)

**Routing Methode** Sie können für Ihre Verteilungsmethode für die Anrufwarteschlange entweder **Attendant**, **seriell**oder **Round Robin** auswählen. Alle neuen und vorhandenen Anrufwarteschleifen sind standardmäßig auf Teilnehmer-Routing (attendant routing) eingestellt. Wenn Attendant-Routing verwendet wird, klingelt der erste Anruf in der Warteschlange alle Anruf-Agents gleichzeitig. Der Anruf wird vom ersten Anruf Agenten abgeholt.

- Das **Attendant-Routing** bewirkt, dass der erste Anruf in der Warteschlange alle Anruf-Agents gleichzeitig klingelt. Der Anruf wird vom ersten Anruf Agenten abgeholt.
- **Serielles Routing** eingehende Anrufe Klingeln die Anruf-Agents einzeln, beginnend mit dem Anfang der Anruf Agentenliste. Agents können nicht in der Liste der Anruf-Agents bestellt werden. Wenn ein Telefonist einen Anruf ablehnt oder nicht annimmt, wird der nächste Telefonist auf der Liste angerufen und ein Telefonist nach dem anderen versucht, bis der Anruf angenommen wird oder die maximale Zeit in der Warteschleife erreicht hat.
  > [!NOTE]
  > Serielles Routing überspringt Telefonisten, die **Offline** sind, ihren Anwesenheitsstatus auf **Nicht stören**festgelegt haben oder sich von Anrufen aus dieser Anrufwarteschleife**abgemeldet haben**.
- **Round Robin** balanciert das Routing von eingehenden Anrufen aus, damit jeder Anruf-Agent die gleiche Anzahl von Anrufen aus der Warteschlange erhält. Dies kann in einer eingehenden Vertriebsumgebung wünschenswert sein, um die Chancengleichheit zwischen allen Anruf Agenten zu gewährleisten.

### <a name="select-an-agent-opt-out-option"></a>Auswählen einer Option für den Agenten Ausstieg

![Screenshot der Optionen für das ablehnen von Agents mit nummerierten Beschriftungen](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

![Symbol der Zahl 1, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout1.png)

**Der Agent kann das Abrufen von Anrufen ablehnen** Sie können festlegen, dass Anruf Warteschlangen-Agents das ablehnen von Anrufen aus einer bestimmten Warteschlange zulassen, indem Sie diese Option aktivieren.

Wenn Sie diese Option aktivieren, können alle Agents in dieser Warteschlange die Anrufe von dieser Anrufwarteschlange nach befolgen starten oder beenden. Sie können das die Möglichkeit, sich von Anrufen abzumelden, durch Deaktivieren des Kontrollkästchens jederzeit sperren, wodurch Telefonisten automatisch wieder für diese Anrufwarteschleife angemeldet werden (die Standardeinstellung für alle Telefonisten).

Um auf die Abmeldungsfunktion zuzugreifen können Telefonisten folgendes tun:

 1. Öffnen Sie **Optionen** in Skype for Business-Client auf ihrem Desktop.
 2. Klicken Sie in der Registerkarte **Anrufweiterleitung** auf den Link **Online-Einstellungen bearbeiten**.
 3. Klicken Sie auf der Seite Benutzereinstellungen auf **Anrufwarteschlangen**, und deaktivieren Sie dann die Kontrollkästchen für alle Warteschlangen, für die Sie sich abmelden möchten.

    > [!NOTE]
    > Agents, die apps oder Endpunkte außer Skype for Business Desktop verwenden, können auf die Option "ablehnen" im [https://aka.ms/cqsettings](https://aka.ms/cqsettings)Portal "Benutzereinstellungen" zugreifen.

![Symbol der Zahl 2, die auf eine Legende in der vorherigen](media/sfbcallout2.png)
**Benachrichtigungseinstellung** des Screenshot-Agents verweist

Damit wird festgelegt, wie lange ein Agent über einen Anruf benachrichtigt wird, bevor die seriellen oder Round Robin-Routingmethoden zum nächsten Agenten wechseln.

Die Standardeinstellung ist 30 Sekunden, kann aber für bis zu 3 Minuten festgelegt werden.

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a>Einrichten der Optionen für den Anruf Überlauf und die Timeout Behandlung

![Screenshot der Überlauf Behandlungsoptionen mit nummerierten Beschriftungen](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

![Symbol der Zahl 1, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout1.png)

**Maximale Anrufe in der Warteschlange**: Legen Sie mit dieser Option fest, wie lange Anrufe maximal in der Warteschleife warten können, bis es zu einem Timeout kommt. Der Standardwert ist 50, aber er kann zwischen 0 und 200 liegen. Wenn dieser Grenzwert erreicht ist, wird der Anruf so gehandhabt, wie Sie den Wert für die **Maximale Anzahl von Anrufen** festgelegt haben.

* * *

![Symbol der Zahl 2, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout2.png)

**Wenn die maximale Anzahl von Anrufen erreicht ist** Wenn die Anrufwarteschlange die maximale Größe erreicht (festgelegt mit den **maximalen anrufen in der Warteschlangen** Einstellung), können Sie auswählen, was mit neuen eingehenden Anrufen geschieht.

- **Verbindung trennen** Der Anruf wird getrennt.
- **Umleitung zu** Wenn Sie diese Option auswählen, wählen Sie eine der folgenden Optionen aus:

  - **Person in Ihrem Unternehmen** Einen Online Benutzer mit einer **Telefon System** Lizenz, der für Enterprise-VoIP aktiviert ist oder einen Anrufplan hat. Sie können es so einrichten, dass der Anrufer an Voicemail gesendet werden kann. Wählen Sie dazu eine **Person in Ihrem Unternehmen** aus, und legen Sie fest, dass Ihre Anrufe direkt an Voicemail weitergeleitet werden.

  Informationen zu den für Voicemail erforderlichen Lizenzen finden Sie unter [Einrichten von Cloud-Voicemail](set-up-phone-system-voicemail.md).

  - **Sprachanwendung** Wählen Sie den Namen eines Ressourcenkontos aus, das entweder einer Anrufwarteschlange oder einer automatischen Telefonzentrale zugeordnet ist, die bereits erstellt wurde.

* * *

![Symbol der Zahl 3, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout3.png)

**Anruf Timeout: maximale Wartezeit** Sie können auch entscheiden, wie viel Zeit ein Anruf in der Warteschlange halten kann, bevor er ein Zeitlimit überschritten hat, und er muss umgeleitet oder getrennt werden. Die Stelle, an der Sie umgeleitet wird, basiert auf der Festlegung des Timeouts für **einen Anruf** . Sie können eine Dauer von 0 bis 45 Minuten festlegen.

Der Timeoutwert kann in Sekunden in Intervallen von 15 Sekunden festgelegt werden. Dadurch können Sie den Anruffluss mit feinerer Granularität bearbeiten. So können Sie beispielsweise festlegen, dass alle Anrufe, die von einem Agenten nicht innerhalb von 30 Sekunden beantwortet werden, zu einer automatischen Telefonzentrale für Verzeichnis suchen wechseln.

![Symbol der Zahl 4, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout4.png)

**Beim Timeout** des Anrufs Wenn der Anruf den Grenzwert erreicht, den Sie für die **Wartezeit in der Warteschlangen** Einstellung festgelegt haben, können Sie auswählen, was mit diesem Anruf geschieht:

- **Verbindung trennen** Der Anruf wird getrennt.
- **Diesen Anruf umleiten an** Wenn Sie diese Option auswählen, haben Sie folgende Möglichkeiten:
  - **Person in Ihrem Unternehmen** Einen Online Benutzer mit einer **Telefon System** Lizenz, der für Enterprise-VoIP aktiviert ist oder Anrufpläne hat. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Wählen Sie dazu eine **Person in Ihrem Unternehmen** aus, und legen Sie fest, dass Ihre Anrufe direkt an Voicemail weitergeleitet werden.

  Informationen zur Lizenzierung, die für Voicemail erforderlich ist, finden Sie unter [Einrichten von Cloud-Voicemail](set-up-phone-system-voicemail.md).

  - **Sprachanwendung** Wählen Sie den Namen eines Ressourcenkontos aus, das entweder einer Anrufwarteschlange oder einer automatischen Telefonzentrale zugeordnet ist, die bereits erstellt wurde.

## <a name="change-a-users-caller-id-for-outbound-calls"></a>Ändern der Rufnummernanzeige eines Benutzers für ausgehende Anrufe

Sie können die Identität eines Benutzers schützen, indem Sie die Rufnummernanzeige für ausgehende Anrufe an eine Anrufwarteschlange, eine automatische Telefonzentrale oder eine beliebige Dienstnummer anstelle des Cmdlets **New-CsCallingLineIdentity** ändern.

Führen Sie dazu die folgenden Aktionen aus:

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Wenden Sie die Richtlinie für den Benutzer mit dem Cmdlet **Grant-CallingLineIdentity** an. Führen Sie dazu die folgenden Aktionen aus:

``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Weitere Informationen zum Festlegen von Einstellungen für die Rufnummernanzeige in Ihrer Organisation finden Sie im Artikel [wie kann die Rufnummernanzeige in Ihrer Organisation verwendet werden](/microsoftteams/how-can-caller-id-be-used-in-your-organization).

## <a name="call-queue-cmdlets"></a>Cmdlets für Anrufwarteschleifen

Sie können auch Windows PowerShell verwenden, um automatische Telefonzentralen zu erstellen und einzurichten. Hier sind die Cmdlets, mit denen Sie eine Anrufwarteschlange verwalten.

- [Neu – CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [Satz-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [Get-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a>Weitere Informationen zu Windows PowerShell

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 und Microsoft Teams mit einem zentralen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

  - [Einführung in Windows PowerShell und Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Warum Sie Office 365 PowerShell verwenden müssen](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell bietet zahlreiche Vorteile in Geschwindigkeit, Einfachheit und Produktivität über das Microsoft Teams Admin Center, beispielsweise wenn Sie für viele Benutzer gleichzeitig Einstellungsänderungen vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:

  - [Verwalten von Office 365 mit Windows PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Verwandte Themen

[Das Telefonsystem in Office 365 bietet Ihnen Folgendes](here-s-what-you-get-with-phone-system.md)

[Abrufen von Diensttelefonnummern](getting-service-phone-numbers.md)

[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Neu – CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
