---
title: Erstellen einer Anrufwarteschlange
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: Hier erfahren Sie, wie Sie das Telefon System für Cloud-Anrufwarteschlangen mit Microsoft Teams einrichten, die eine Grußnachricht bereitstellen, Musik, Anrufumleitung und andere Funktionen enthalten.
ms.openlocfilehash: 9c2593f657ae66a1dcde825ac7a783df10cd96d8
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2020
ms.locfileid: "44523788"
---
# <a name="create-a-cloud-call-queue"></a>Erstellen einer Cloudanrufwarteschleife

Cloud-Anrufwarteschlangen können Folgendes bereitstellen:

- Eine Grußnachricht.
- Musik, während die wartenden Anrufer gehalten werden
- Umleitung von Anrufen an Telefonisten in die von E-Mail-aktivierten Verteilerlisten und Sicherheitsgruppen
- Festlegen unterschiedlicher Parameter wie maximale Größe der Warteschlange, Timeout und Anruf Behandlungsoptionen.
- Voicemail für Anrufer freigegeben, um eine Nachricht für eine Organisation zu hinterlassen.

Eine Telefonnummer wird nicht direkt einer Anrufwarteschlange zugeordnet, sondern die Telefonnummer ist mit einem [Ressourcenkonto](manage-resource-accounts.md)verknüpft. Eine Anrufwarteschlange kann direkt gewählt oder über eine Auswahl in einer automatischen Telefonzentrale aufgerufen werden.

Der Anrufer hört Musik, während Sie in Wartestellung sind, und der Anruf stellt eine Verbindung mit den Anruf-Agents in *First in, First Out* (FIFO)-Reihenfolge her.

Alle Anrufe in der Warteschlange werden mithilfe einer der folgenden Methoden an Agents gesendet:

- Beim Attendant-Routing klingelt der erste Anruf in der Warteschlange alle Agents gleichzeitig.
- Beim seriellen Routing klingelt der erste Anruf in der Warteschlange alle Anruf-Agents einzeln.
- Bei Round Robin wird das Routing von eingehenden Anrufen ausgeglichen, damit jeder Anruf-Agent die gleiche Anzahl von Anrufen aus der Warteschlange erhält.

Mit einer der oben genannten Methoden können Sie Optionen für die Anrufbehandlung festlegen, wie beispielsweise die Option zum Deaktivieren des Agents, Anwesenheits basiertes Routing, Wartezeiten für Anrufe und Anruf Timeouts.

Nur eine Benachrichtigung über eingehende Anrufe (für den Anruf am Kopf der Warteschlange) geht zu einem Zeitpunkt an die Anruf Agenten. Wenn ein Telefonist den Anruf angenommen hat, klingelt der nächste eingehende Anruf aus der Warteschleife bei den Telefonisten.

> [!NOTE]
> Dieser Artikel bezieht sich auf Microsoft Teams und Skype for Business Online.

## <a name="step-1--get-started"></a>Schritt 1 – erste Schritte

Die folgenden Punkte sind bei Ihrem Einstieg in die Verwendung von Anrufwarteschleifen wichtig:

- Für eine Anrufwarteschlange ist ein zugeordnetes Ressourcenkonto erforderlich. Details zu Ressourcenkonten finden Sie unter [Verwalten von Ressourcenkonten in Teams](manage-resource-accounts.md) .
- Wenn Sie einem Ressourcenkonto eine Telefonnummer zuweisen, können Sie jetzt die ﻿kostenlose [virtuelle Benutzerlizenz](teams-add-on-licensing/virtual-user.md)für das Telefon System verwenden. Telefon System ermöglicht Telefonnummern auf Organisationsebene zur Verwendung mit kostengünstigen automatischen Telefonzentralen und Anrufwarteschlangen-Diensten.

  > [!NOTE]
  > Direct Routing-Dienstnummern für Anrufwarteschlangen werden nur für Microsoft Teams-Benutzer und-Agents unterstützt.

  > [!NOTE]
  > Um Anrufe an Personen in Ihrer Organisation umzuleiten, die Online sind, müssen Sie über eine **Telefon System** Lizenz verfügen und für Enterprise-VoIP aktiviert sein oder über Office 365-Anrufpläne verfügen. Weitere Informationen finden Sie unter [Zuweisen von Microsoft Teams-Add-on-Lizenzen](teams-add-on-licensing/assign-teams-add-on-licenses.md). Wenn Sie sie für Enterprise-VoIP aktivieren möchten, können Sie Windows PowerShell verwenden. Führen Sie beispielsweise Folgendes aus:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

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

    > [!NOTE]
    > Anrufwarteschlangen, denen eine direkte Routingnummer zugewiesen ist, unterstützen keine Skype for Business-Clients, lync-Clients oder Skype for Business-IP-Telefone als Agents.

## <a name="step-2--get-or-transfer-toll-or-toll-free-service-phone-numbers"></a>Schritt 2: Abrufen oder übertragen von gebührenpflichtigen oder gebührenfreien Telefonnummern für Dienstleistungen

Bevor Sie Ihre Anrufwarteschlangen erstellen und einrichten können, müssen Sie Ihre vorhandenen gebührenpflichtigen oder gebührenfreien Servicenummern abrufen oder übertragen. Informationen zum Abrufen Ihrer Dienstnummern finden Sie unter [Abrufen von Diensttelefonnummern](getting-service-phone-numbers.md) oder, wenn Sie eine vorhandene Dienstnummer übertragen möchten, unter [Übertragen von Telefonnummern zu Office 365](phone-number-calling-plans/transfer-phone-numbers-to-teams.md). Nachdem Sie die gebührenpflichtigen oder gebührenfreien Service-Telefonnummern erhalten haben, werden Sie in den **Microsoft Teams Admin Center**-  >  **sprach**  >  **Telefonnummern**angezeigt. Gebührenfreie Nummern werden mit einem **Nummerntyp** für **Dienstleistungen (gebührenfrei**) aufgeführt.

> [!NOTE]
> Wenn Sie sich außerhalb der Vereinigten Staaten befinden, können Sie das Microsoft Teams Admin Center nicht verwenden, um Dienstnummern zu erhalten. Wechseln Sie zu [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) , anstatt zu erfahren, wie Sie von außerhalb der Vereinigten Staaten aus Vorgehen.

Wenn Sie mehrere automatische Telefonzentralen einrichten, weisen Sie normalerweise dem Ressourcenkonto der primären automatischen Telefonzentrale eine Telefonnummer zu. Ressourcenkonten, die geschachtelten automatischen Telefonzentralen oder Anrufwarteschlangen zugeordnet sind, benötigen häufig keine Telefonnummern. Diese automatische Telefonzentrale kann Anrufer an Ihre Anrufwarteschlangen oder geschachtelte automatische Telefonzentralen weiterleiten, selbst wenn Sie keine Telefonnummer haben. In diesen Fällen können Sie alle automatischen Telefonzentralen erstellen und Warteschlangen in Ihrem System anrufen, ohne dass Sie die Optionen für die Wähltasten zuweisen, und die Einstellungen später bearbeiten. Es muss eine Anrufwarteschlange oder eine automatische Telefonzentrale vorhanden sein, um Sie als Menüoption zu definieren.

## <a name="step-3--create-a-call-queue"></a>Schritt 3 – Erstellen einer Anrufwarteschlange

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> Für jede Anrufwarteschlange ist ein zugeordnetes [Ressourcenkonto](manage-resource-accounts.md)erforderlich. Sie müssen zuerst das Ressourcenkonto erstellen, dann können Sie es der Anrufwarteschlange zuordnen.

### <a name="use-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams admin Centers

Klicken Sie im **Microsoft Teams Admin Center** **Voice**  >  auf**Warteschlangen**für Sprachanrufe und dann auf **+ Neu hinzufügen**:

### <a name="set-the-display-name-and-resource-account"></a>Einrichten des Anzeige namens und des Ressourcenkontos

![Screenshot einer neuen Anrufwarteschlange mit nummerierten Beschriftungen](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

![Symbol der Zahl 1, verweist auf eine Legende im vorherigen Screenshot- ](media/teamscallout1.png)
 **Namen** geben Sie einen beschreibenden Anzeigenamen für die Anrufwarteschlange ein. Dieser Name ist erforderlich und kann bis zu 64 Zeichen enthalten, einschließlich Leerzeichen.

 Dieser Name wird in der Benachrichtigung für den eingehenden Anruf angezeigt.

* * *

![Symbol der Zahl 2, verweist auf eine Legende im vorherigen Screenshot ](media/teamscallout2.png)
 **Hinzufügen von Konten** wählen Sie ein Ressourcenkonto aus. Alle Anrufwarteschlangen sind für ein Ressourcenkonto erforderlich. Für Ressourcenkonten ist keine Dienst gebührenpflichtige oder gebührenfreie Telefonnummer erforderlich.

Wenn keine Liste aufgeführt ist, rufen Sie Dienstnummern ab, und weisen Sie Sie einem Ressourcenkonto zu, bevor Sie die Anrufwarteschlange erstellen, wie zuvor beschrieben. Informationen zum Abrufen Ihrer Dienstnummern finden Sie unter [Abrufen von Telefonnummern für Dienstleistungen](getting-service-phone-numbers.md). Einzelheiten zum Zuweisen einer Telefonnummer finden Sie unter [Verwalten von Ressourcenkonten in Teams](manage-resource-accounts.md) .

> [!NOTE]
> Wenn Sie eine **Domäne** zuweisen möchten oder müssen, weisen Sie diese dem Ressourcenkonto für die Anrufwarteschlange zu.

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>Festlegen der Begrüßung und der Wartemusik, die wiedergegeben werden soll

![Screenshot der Optionen für Begrüßung und Musik mit nummerierten Beschriftungen](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

![Symbol der Zahl 1, verweist auf eine Legende im vorherigen Screenshot, in ](media/teamscallout1.png)
 **Greeting** der die optionale Ansage für Personen, die die Anruf Warteschlangennummer anrufen, abgespielt wird.

Sie können eine Audiodatei (WAV-, MP3-oder WMA-Formate) hochladen.

![Symbol der Zahl 2, verweist auf eine Legende in der vorherigen Screenshot-Musik in der Warteschleife ](media/teamscallout2.png)
 **Music on hold** können Sie die standardmäßige Musik in der Warteschlange verwenden. Sie können auch eine Audiodatei in WAV-, MP3-oder WMA-Formaten hochladen, um Sie als benutzerdefinierte Musik in Wartestellung zu verwenden.

* * *

### <a name="select-the-call-answering-options"></a>Wählen Sie die Optionen für die Anrufannahme aus.

![Screenshot der Optionen für die Anrufannahme](media/teams-cq-call-answering-options.png)

![Symbol der Zahl 1, verweist auf eine Legende in den vorherigen Screenshot- ](media/teamscallout1.png)
 **Anruf-Agents und-Gruppen** , um einzelne Agents direkt hinzuzufügen, ohne Sie zu einer Gruppe hinzuzufügen, klicken Sie auf **Benutzer hinzufügen**. Legen Sie einzelne Agents in der Reihenfolge ab, in der Sie den Anruf empfangen sollen. Sie können bis zu 20 einzelne Agents hinzufügen (um mehr als 20 hinzuzufügen, um Sie in einer Gruppe zu speichern).

Anrufe werden zuerst an einzelne Agents und dann an die Agents in Gruppen weitergeleitet. 

Sie können bis zu 200-Anruf-Agents auswählen, die zu einer der folgenden Mailinglisten oder-Gruppen gehören:

- Office 365-Gruppe
- Sicherheitsgruppe
- Verteilerliste

Ausgewählte Anruf-Agents müssen eine der folgenden sein:

- Online-Benutzer mit einer Telefon System Lizenz und Enterprise-VoIP aktiviert
- Online Benutzer mit einem Anrufplan
- Lokale Skype for Business Server-Benutzer

  > [!NOTE]
  > Dies gilt auch, wenn Sie Anrufe an Personen in Ihrer Organisation umleiten möchten, die Online sind. Diese Personen müssen über eine **Telefon System** Lizenz und Enterprise-VoIP verfügen *oder* über einen Anrufplan verfügen. Weitere Informationen finden Sie unter [Zuweisen von Lizenzen für Skype for Business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses), [Zuweisen von Microsoft Teams-Lizenzen](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses)oder [der richtige Anrufplan für Sie?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)

   Um einen Agenten für Enterprise-VoIP zu aktivieren, können Sie Windows PowerShell verwenden. Führen Sie beispielsweise Folgendes aus:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- Benutzer mit einer **Telefon System** Lizenz oder einem Anrufplan, die einer Office 365-Gruppe hinzugefügt werden eine e-Mail-aktivierte Verteilerliste oder eine Sicherheitsgruppe. Wenn Sie einen Agenten in einer Verteilerliste oder einer Sicherheitsgruppe als Anruf Warteschlangen-Agent hinzufügen, kann es bis zu drei Stunden dauern, bis der erste Anruf eintrifft. Eine neu erstellte Verteilerliste oder Sicherheitsgruppe kann bis zu 48 Stunden dauern, bis Sie für die Verwendung mit Anrufwarteschlangen verfügbar ist. Neu erstellte Microsoft 365-Gruppen sind fast sofort verfügbar.

- Wenn Ihre Agents die Microsoft Teams-App für Anruf Warteschlangen Anrufe verwenden, müssen Sie sich im TeamsOnly-Modus befinden.

![Symbol der Zahl 2, bezieht sich auf eine Beschriftung im vorherigen Screenshot ](media/teamscallout2.png)
 **Konferenz** Modus der Konferenzmodus reduziert deutlich, wie lange es dauert, bis ein Anrufer mit einem Agenten verbunden ist, nachdem der Agent den Anruf angenommen hat. Wenn Sie über mehr als eine Anrufwarteschlange verfügen, können Sie den Konferenzmodus für einige oder alle Anrufwarteschlangen aktivieren. Das Aktivieren oder Deaktivieren des Konferenzmodus in einer Anrufwarteschlange wirkt sich nicht auf andere Anrufwarteschlangen aus.

Der Konferenzmodus ist standardmäßig deaktiviert, kann aber jederzeit aktiviert werden, wenn die folgenden Voraussetzungen erfüllt sind:

- Agents, die der Anrufwarteschlange hinzugefügt wurden, müssen einen der folgenden Clients verwenden:
  - Die neueste Version des Microsoft Teams-Desktop Clients, der Android-App oder der IOS-App
  - Microsoft Teams Phone Version 1449/1.0.94.2020051601 oder höher
- Die Konten von Agenten Teams müssen auf "nur für Teams" eingestellt sein.

> [!IMPORTANT]
> Wenn die oben aufgeführten Agenten Anforderungen nicht erfüllt sind und der Konferenzmodus in einer Anrufwarteschlange aktiviert ist, werden Agents, die die Anforderungen nicht erfüllen, nicht in die Anruf Weiterleitungsliste aufgenommen. Agenten, die nicht in der Anruf Weiterleitungsliste sind, erhalten keine Anrufe. Wenn Sie über Agents verfügen, die die oben genannten Agenten Anforderungen nicht erfüllen, aktivieren Sie den Konferenzmodus nicht in der Anrufwarteschlange.

Nachdem der Konferenzmodus in einer Anrufwarteschlange aktiviert wurde, profitieren Anrufe von der kürzeren Verbindungszeit, wenn Sie über eine der folgenden Methoden empfangen werden:

- VoIP-Anrufe von einem anderen Microsoft Teams-Desktop Client
- PSTN-Anrufe des Anruf Plans
- Direkte Weiterleitung von PSTN-anrufen

Die meisten Anrufe werden über eine der oben aufgeführten Methoden empfangen. Wenn ein Anruf über eine andere Methode (beispielsweise einen VoIP-Anruf von einem Skype for Business-Client) empfangen wird, wird der Anruf weiterhin zur Anrufwarteschlange hinzugefügt, aber er profitiert nicht von der kürzeren Verbindungszeit.

![Symbol der Zahl 3, verweist auf eine Legende in der vorherigen Screenshot ](media/teamscallout3.png)
 **-Routing Methode** Sie können entweder **Attendant**, **Serial**oder **Round Robin** als Verteilungsmethode auswählen. Standardmäßig sind für alle neuen und vorhandenen Anrufwarteschlangen das Attendant-Routing ausgewählt. Wenn Attendant-Routing verwendet wird, klingelt der erste Anruf in der Warteschlange alle Anruf-Agents gleichzeitig. Der Anruf wird vom ersten Anruf Agenten abgeholt.

- Das **Attendant-Routing** bewirkt, dass der erste Anruf in der Warteschlange alle Anruf-Agents gleichzeitig klingelt. Der Anruf wird vom ersten Anruf Agenten abgeholt.
- **Serielles Routing** eingehende Anrufe Klingeln alle Anruf-Agents eins nach dem anderen vom Anfang der Anruf Agentenliste. Agents können nicht in der Liste der Anruf-Agents bestellt werden. Wenn ein Agent einen Anruf abschließt oder nicht annimmt, klingelt der Anruf beim nächsten Agenten und versucht alle Agenten, bis er abgeholt wird oder ein Timeout annimmt.
- **Round Robin** balanciert das Routing von eingehenden Anrufen aus, damit jeder Anruf-Agent die gleiche Anzahl von Anrufen aus der Warteschlange erhält. Dies kann in einer eingehenden Vertriebsumgebung wünschenswert sein, um die Chancengleichheit zwischen allen Anruf Agenten zu gewährleisten.

![Symbol der Zahl 4, verweist auf eine Legende im vorherigen Screenshot ](media/teamscallout4.png)
 **Anwesenheits** basiertes Routing-Anwesenheits basiertes Routing verwendet den Verfügbarkeitsstatus von Anruf-Agents, um zu ermitteln, ob ein Agent in die Anruf Weiterleitungsliste für die ausgewählte Routingmethode aufgenommen werden soll. Anruf-Agents, deren Verfügbarkeitsstatus auf **verfügbar** festgesetzt ist, sind in der Anruf Weiterleitungsliste enthalten und können Anrufe empfangen. Agents, deren Verfügbarkeitsstatus auf einen beliebigen anderen Status festgesetzt ist, werden aus der Anruf Weiterleitungsliste ausgeschlossen und empfangen keine Anrufe, bis sich der Verfügbarkeitsstatus wieder in **verfügbar**ändert.

Sie können das anwesenheitsbasierte Anrufrouting mit einer der Routingmethoden aktivieren.

Wenn sich ein Agent für das Abrufen von Anrufen entscheidet, wird er nicht in die Anruf Weiterleitungsliste aufgenommen, unabhängig davon, auf welchen Verfügbarkeitsstatus er festgesetzt ist.

> [!IMPORTANT]
> Agents, die den Skype for Business-Client verwenden, sind nicht in der Anruf Weiterleitungsliste enthalten, wenn das anwesenheitsbasierte Routing unabhängig von deren Verfügbarkeitsstatus aktiviert ist. Agenten, die nicht in der Anruf Weiterleitungsliste sind, erhalten keine Anrufe. Wenn Sie über Agenten verfügen, die Skype for Business verwenden, aktivieren Sie das anwesenheitsbasierte Anrufrouting nicht.

### <a name="select-an-agent-opt-out-option"></a>Auswählen einer Option für den Agenten Ausstieg

![Screenshot der Optionen für das ablehnen von Agents mit nummerierten Beschriftungen](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

![Symbol der Zahl 1, bezieht sich auf eine Legende im vorherigen Screenshot ](media/teamscallout1.png)
 -**Agent kann das Abrufen von Anrufen ablehnen** Sie können festlegen, dass Anruf Warteschlangen-Agents das ablehnen von Anrufen aus einer bestimmten Warteschlange zulassen, indem Sie diese Option aktivieren.

Wenn Sie diese Option aktivieren, können alle Agents in dieser Warteschlange die Anrufe von dieser Anrufwarteschlange nach befolgen starten oder beenden. Sie können das die Möglichkeit, sich von Anrufen abzumelden, durch Deaktivieren des Kontrollkästchens jederzeit sperren, wodurch Telefonisten automatisch wieder für diese Anrufwarteschleife angemeldet werden (die Standardeinstellung für alle Telefonisten).

Um auf die Option "ablehnen" zuzugreifen, können Agents:

 1. Öffnen Sie **Optionen** in Skype for Business-Client auf ihrem Desktop.
 2. Klicken Sie in der Registerkarte **Anrufweiterleitung** auf den Link **Online-Einstellungen bearbeiten**.
 3. Klicken Sie auf der Seite Benutzereinstellungen auf **Anrufwarteschlangen**, und deaktivieren Sie dann die Kontrollkästchen, um Warteschlangen abzulehnen.

    > [!NOTE]
    > Agents, die apps oder Endpunkte außer Skype for Business Desktop verwenden, können auf die Option "ablehnen" im Portal "Benutzereinstellungen" zugreifen [https://aka.ms/cqsettings](https://aka.ms/cqsettings) .
    >
    > Wenn sich die Agents in Microsoft Teams-Desktop Clients befinden, können Sie diese mithilfe der Anrufeinstellungen ablehnen. 

![Symbol der Zahl 2, bezieht sich auf einen Callout in der ](media/teamscallout2.png)
 **Benachrichtigungseinstellung** vorheriger Screenshot-Agent

Damit wird festgelegt, wie lange ein Agent über einen Anruf benachrichtigt wird, bevor die seriellen oder Round Robin-Routingmethoden zum nächsten Agenten wechseln.

Die Standardeinstellung ist 30 Sekunden, kann aber für bis zu 3 Minuten festgelegt werden.

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a>Einrichten der Optionen für den Anruf Überlauf und die Timeout Behandlung

![Screenshot der Überlauf Behandlungsoptionen mit nummerierten Beschriftungen](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

![Symbol der Zahl 1, verweist auf eine Legende im vorherigen Screenshot ](media/teamscallout1.png)
 **Maximale Anrufe in der Warteschlange** verwenden Sie diese Einstellung, um die maximale Anzahl von Anrufen festzulegen, die gleichzeitig in der Warteschlange warten können. Der Standardwert ist 50, aber er kann zwischen 0 und 200 liegen. Wenn dieser Grenzwert erreicht ist, wird der Anruf so gehandhabt, wie Sie den Wert für die **Maximale Anzahl von Anrufen** festgelegt haben.

* * *

![Symbol der Zahl 2, verweist auf eine Legende im vorherigen Screenshot, ](media/teamscallout2.png)
 **Wenn die maximale Anzahl von Anrufen erreicht wird** , wenn die Anrufwarteschlange die maximale Größe erreicht (mit der Einstellung Maximale Anzahl von **anrufen in der Warteschlange** festlegen), können Sie auswählen, was mit neuen eingehenden Anrufen geschieht.

- **Verbindung trennen** Der Anruf wird getrennt.
- **Umleitung zu** Wenn Sie diese Option auswählen, wählen Sie eine der folgenden Optionen aus:

  - **Person in Ihrem Unternehmen** Einen Online Benutzer mit einer **Telefon System** Lizenz, der für Enterprise-VoIP aktiviert ist oder einen Anrufplan hat. Sie können es so einrichten, dass der Anrufer an Voicemail gesendet werden kann. Wählen Sie dazu eine **Person in Ihrem Unternehmen** aus, und legen Sie fest, dass Ihre Anrufe direkt an Voicemail weitergeleitet werden.

  Informationen zu den für Voicemail erforderlichen Lizenzen finden Sie unter [Einrichten von Cloud-Voicemail](set-up-phone-system-voicemail.md).

  - **Sprachanwendung** Wählen Sie den Namen eines Ressourcenkontos aus, das entweder einer Anrufwarteschlange oder einer automatischen Telefonzentrale zugeordnet ist, die bereits erstellt wurde.

* * *

![Symbol der Zahl 3, bezieht sich auf eine Legende im vorherigen Screenshot- ](media/teamscallout3.png)
 **Timeout: maximale Wartezeit** Sie können auch entscheiden, wie viel Zeit ein Anruf in der Warteschlange halten kann, bevor er ein Zeitlimit überschritten hat, und muss umgeleitet oder getrennt werden. Die Stelle, an der Sie umgeleitet wird, basiert auf der Festlegung des Timeouts für **einen Anruf** . Sie können eine Dauer von 0 bis 45 Minuten festlegen.

Der Timeoutwert kann in Sekunden in Intervallen von 15 Sekunden festgelegt werden. Dadurch können Sie den Anruffluss mit feinerer Granularität bearbeiten. So können Sie beispielsweise festlegen, dass alle Anrufe, die von einem Agenten nicht innerhalb von 30 Sekunden beantwortet werden, zu einer automatischen Telefonzentrale für Verzeichnis suchen wechseln.

![Symbol der Zahl 4, bezieht sich auf eine Legende im vorherigen Screenshot, wenn der Anruf ](media/teamscallout4.png)
 **ausfällt** , wenn der Anruf den Grenzwert erreicht, den Sie für die **Wartezeit in der Warteschlangen** Einstellung festgelegt haben, können Sie auswählen, was mit dem Anruf geschieht:

- **Verbindung trennen** Der Anruf wird getrennt.
- **Diesen Anruf umleiten an** Wenn Sie diese Option auswählen, haben Sie folgende Möglichkeiten:
  - **Person in Ihrem Unternehmen** Einen Online Benutzer mit einer **Telefon System** Lizenz, der für Enterprise-VoIP aktiviert ist oder Anrufpläne hat. Wenn Sie die Person so einrichten möchten, dass Sie an Voicemail gesendet werden kann, wählen Sie eine **Person in Ihrem Unternehmen** aus, und legen Sie diese Person so fest, dass Ihre Anrufe direkt an Voicemail weitergeleitet werden.

  Informationen zu den für Voicemail erforderlichen Lizenzen finden Sie unter [Einrichten von Cloud-Voicemail](set-up-phone-system-voicemail.md).

  - **Sprach-App** Wählen Sie den Namen eines Ressourcenkontos aus, das entweder einer Anrufwarteschlange oder einer automatischen Telefonzentrale zugeordnet ist, die Sie bereits erstellt haben.

## <a name="change-caller-id-for-outbound-calls"></a>Ändern der Rufnummernanzeige für ausgehende Anrufe

Um die Identität eines Anruf Agenten zu schützen, ändern Sie die Rufnummernanzeige für ausgehende Anrufe an eine Anrufwarteschlange, eine automatische Telefonzentrale oder eine beliebige Dienstnummer mit dem Cmdlet **New-CsCallingLineIdentity** wie im folgenden Beispiel:

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Wenden Sie dann die Richtlinie für den Benutzer mit dem **Grant-CallingLineIdentity-** Cmdlet wie im folgenden Beispiel an: 

``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Weitere Informationen finden Sie unter [wie kann die Anrufer-ID in Ihrer Organisation verwendet werden](/microsoftteams/how-can-caller-id-be-used-in-your-organization).

## <a name="call-queue-cmdlets"></a>Cmdlets für Anrufwarteschleifen

Sie können auch Windows PowerShell verwenden, um automatische Telefonzentralen zu erstellen und einzurichten. Hier sind die Cmdlets, mit denen Sie eine Anrufwarteschlange verwalten.

- [Neu – CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [Satz-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [Get-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a>Weitere Informationen zu Windows PowerShell

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 und Microsoft Teams mit einem zentralen Verwaltungspunkt verwalten. Sie können Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

  - [Einführung in Windows PowerShell und Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Warum Sie Office 365 PowerShell verwenden müssen](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell bietet zahlreiche Vorteile bei der Geschwindigkeit, Einfachheit und Produktivität über das Microsoft Teams Admin Center, wenn Sie Änderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:

  - [Verwalten von Office 365 mit Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Einrichten Ihres Computers für Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Verwandte Themen

[Das Telefonsystem in Office 365 bietet Ihnen Folgendes](here-s-what-you-get-with-phone-system.md)

[Abrufen von Diensttelefonnummern](getting-service-phone-numbers.md)

[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
