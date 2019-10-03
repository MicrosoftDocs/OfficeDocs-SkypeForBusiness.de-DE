---
title: Einrichten einer automatischen Cloudtelefonzentrale
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: waseemh
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
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
description: Hier erfahren Sie, wie Sie automatische Cloud-Telefonzentralen für Microsoft Teams einrichten und testen.
ms.openlocfilehash: 0cac6b1bb7d19e91e4042bcb0673f6c677e77d2e
ms.sourcegitcommit: 2d31209aae9e0171693389db97b0b5c974864673
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2019
ms.locfileid: "37375709"
---
# <a name="set-up-a-cloud-auto-attendant"></a>Einrichten einer automatischen Cloudtelefonzentrale

Automatische Telefonzentralen ermöglichen es Personen, die in Ihrer Organisation anrufen, über ein Menüsystem zur richtigen Abteilung, Warteschlange, Person oder dem Telefonisten zu gelangen. Sie können eine automatische Telefonzentrale für Ihre Organisation erstellen, indem Sie das Microsoft Teams Admin Center verwenden. Wenn Sie eine neue automatische Telefonzentrale erstellen möchten, wechseln Sie in der linken Navigationsleiste zu **VoIP** , und wählen Sie dann **automatische Telefonzentralen** > **Neu hinzufügen**aus.

Wenn Sie mehr über automatische Telefonzentralen erfahren möchten, lesen Sie [Was sind automatische Cloud-Telefonzentralen?](/microsoftteams/what-are-phone-system-auto-attendants)

> [!NOTE]
> Dieser Artikel bezieht sich auf Microsoft Teams und Skype for Business Online.

## <a name="step-1--get-started"></a>Schritt 1 – erste Schritte

- Für eine automatische Telefonzentrale ist ein zugeordnetes Ressourcenkonto erforderlich. Informationen zu Ressourcenkonten und allen erforderlichen Lizenzen finden Sie unter [Verwalten von Ressourcenkonten in Teams](manage-resource-accounts.md) .

> [!TIP]
> Wenn Sie Anrufe an einen Operator oder eine Menüoption umleiten möchten, bei der es sich um einen Online Benutzer mit einer **Telefon System** Lizenz handelt, müssen Sie diese für Enterprise-VoIP aktivieren. Weitere Informationen finden Sie unter [Zuweisen von Skype for Business-Lizenzen](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) oder [Zuweisen von Microsoft Teams-Lizenzen](assign-teams-licenses.md). Sie können auch die Windows PowerShell verwenden. Führen Sie beispielsweise Folgendes aus:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

## <a name="step-2--create-a-new-auto-attendant"></a>Schritt 2: Erstellen einer neuen automatischen Telefonzentrale

> [!IMPORTANT]
> Für jede automatische Telefonzentrale ist ein zugeordnetes [Ressourcenkonto](manage-resource-accounts.md)erforderlich. Sie müssen zuerst das Ressourcenkonto erstellen, dann können Sie es der automatischen Telefonzentrale zuordnen.

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams admin Centers

Klicken Sie im **Microsoft Teams Admin Center**auf **Automatische Voicemail** > -**Telefonzentralen**, und klicken Sie dann auf **+ neu**:

#### <a name="general-info-page"></a>Seite "Allgemeine Informationen"

![Screenshot der Seite "meine automatische Telefonzentrale"](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![Symbol der Zahl 1, das auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout1.png)

**Name** Geben Sie einen aussagekräftigen Anzeige Namen für Ihre automatische Telefonzentrale ein. Der Name ist erforderlich und kann maximal 64 Zeichen einschließlich Leerzeichen enthalten. Sie wird in der Spalte **Name** auf der Registerkarte **automatische Telefonzentralen** angezeigt.

* * *

![Symbol der Zahl 2, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout2.png)

<a name="phonenumber"> </a>

**Ressourcenkonto** Klicken Sie auf diese Schaltfläche, um ein oder mehrere Ressourcenkonten auszuwählen, um eine Verbindung mit der neuen automatischen Telefonzentrale herzustellen. Für alle automatischen Telefonzentralen ist ein zugeordnetes Ressourcenkonto erforderlich. Ein Ressourcenkonto kann eine Telefonnummer haben, die mit dem Konto verknüpft ist, aber eine Telefonnummer ist nicht erforderlich. Eine automatische Telefonzentrale der obersten Ebene weist normalerweise ein Ressourcenkonto mit einer zugewiesenen Telefonnummer auf, aber eine geschachtelte automatische Telefonzentrale (wird als Menü der Ebene 2 verwendet, mit dem die automatische Telefonzentrale eine Verbindung herstellt) hat möglicherweise keine Telefonnummer, die dem Ressourcenkonto zugeordnet ist.

* * *

![Symbol der Zahl 3, die auf eine Legende im vorherigen Screenshot](media/sfbcallout3.png)
 <a name="timezone"> </a> verweist

**Zeitzone** Sie müssen die Zeitzone für Ihre automatische Telefonzentrale festlegen, Sie muss aber nicht der Zeitzone der Hauptadresse entsprechen, die für Ihre Organisation aufgeführt ist. Jede automatische Telefonzentrale kann eine andere Zeitzone aufweisen, und die für die automatische Telefonzentrale festgelegten Geschäftszeiten werden basierend auf der hier ausgewählten Zeitzone festgesetzt.

* * *

![Symbol der Zahl 4, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout4.png)

<a name="language"> </a>

**Sprache**: Wählen Sie unter den aufgeführten verfügbaren Sprachen die Sprache aus, die Sie für die automatische Telefonzentrale verwenden möchten. Bei der hier festgelegten Sprache handelt es sich um die Sprache, die von der automatischen Telefonzentrale für die Interaktion mit Personen verwendet wird, die diese automatische Telefonzentrale anrufen, und alle Systemansagen werden in dieser Sprache wiedergegeben.

* * *

![Symbol der Zahl 5, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout5.png)

<a name="operator"> </a>

**Operator** Dies ist optional, aber Sie können die Option " **Operator** " so einstellen, dass Anrufer die Menüs ausbrechen und mit einer Person sprechen können.

Die 0-Taste wird standardmäßig dem Operator zugewiesen.

Wenn Sie einen Operator einrichten, müssen Sie auch Personen, die über die Option in den **Menü Optionen "Bearbeiten"** anrufen, auf der Seite " **Geschäftszeiten-Anrufbehandlung** " informieren. Wenn Sie einen Operator für Ihre automatische Telefonzentrale festlegen, müssen Sie den entsprechenden Eingabeaufforderungstext im Feld **Anrufer werden hören** eingeben oder Ihre Audiodatei so ändern, dass diese Option einbezogen wird. Beispiel: „Drücken Sie ‚0', um mit der Vermittlung zu sprechen".

Sie haben mehrere Möglichkeiten, den Operator einzurichten:

- **Person in Ihrem Unternehmen** mit einer **Telefonsystem**-Lizenz, die für Enterprise Voice aktiviert oder Anruf-Plänen in Office 365 zugeordnet ist.

     > [!Note]
     > **Die Person in Ihrem Unternehmen** kann ein Online-Benutzer oder ein vor Ort gehosteter Benutzer sein, der den Skype for Business Server 2015 oder den Lync Server 2013 verwendet.

- **Sprachanwendung** Wählen Sie den Namen eines Ressourcenkontos aus, das entweder einer Anrufwarteschlange oder einer automatischen Telefonzentrale zugeordnet ist, die bereits erstellt wurde.
- Sie können es so einrichten, dass die Person, die anruft, an Voicemail gesendet wird. Wählen Sie dazu **Person in Ihrem Unternehmen** aus, und legen Sie fest, dass die Anrufe dieser Person direkt an Voicemail weitergeleitet werden.

* * *

![Symbol der Zahl 6, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout6.png)

**Aktivieren von Spracheingaben** Wenn diese Option ausgewählt ist, steht die Spracherkennung zur Verfügung. Personen, die sich einwählen, können die Spracheingabe in der von [Ihnen festgelegten Sprache](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)verwenden. Wenn Sie nur Personen Ihre Telefontastatur verwenden lassen möchten, können Sie die Spracherkennung deaktivieren, indem Sie Sie auf aus setzen.

* * *

Wenn Sie die gewünschten Optionen ausgewählt haben, klicken Sie auf **weiter**.

#### <a name="business-hours-page"></a>Seite "Geschäftszeiten"

Standardmäßig werden die Geschäftszeiten von Montag bis Freitag auf 9:00 Uhr bis 5:00 Uhr eingestellt. Alle Stunden, die nicht in Geschäftszeiten enthalten sind, werden nach Geschäftszeiten berücksichtigt. Sie können auf **24/7 auswählen** klicken, um die Geschäftszeiten für alle Stunden zu übernehmen. Wenn Sie die Option **Select 24/7** auswählen, wird die Seite **After Hours-Anrufeinstellungen** verwendet, um die Regeln für die Anrufbehandlung für die automatische Telefonzentrale für After Business Hours zu konfigurieren.

![Screenshot der Seite "Geschäftszeiten"](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![Symbol der Zahl 1, das auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout1.png)

Standardmäßig sind die Geschäftszeiten auf Montag bis Freitag, 9:00 Uhr-5:00 Uhr, eingestellt. Wählen Sie die Option **alle Stunden löschen** aus, um die Auswahl aller Stunden im Terminplan aufzuheben. Wenn Sie **auf Standard zurücksetzen**klicken, werden die Geschäftszeiten auf Montag bis Freitag 9:00 Uhr-5:00 Uhr zurückgesetzt.

* * *

![Symbol der Zahl 2, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout2.png)

Um die Geschäftszeiten zu ändern, markieren Sie die Geschäftszeiten, die Sie im Kalender festlegen möchten. Im Kalender können Sie Geschäftszeiten in Intervallen von 30 Minuten auswählen, und die hier ausgewählten Geschäftszeiten basieren auf der Zeitzone, die Sie auf der Seite **Allgemeine Informationen** festzulegen. Um eine Pause (beispielsweise eine Mittagspause) einzurichten, deaktivieren, oder ziehen Sie zum Deaktivieren die Zeit im Kalender. Sie können innerhalb der Geschäftszeiten mehrere Pausen festlegen.

* * *

Wenn Sie die gewünschten Optionen ausgewählt haben, klicken Sie auf **weiter**.

#### <a name="business-hours-call-settings"></a>Anrufeinstellungen für Geschäftszeiten

> [!TIP]
> Wenn Sie einen benutzerdefinierten Terminplan für Geschäftszeiten verwenden, müssen Sie auch die Anrufübergabe nach Geschäftszeiten über die Seite **After Hours-Anrufbehandlung** einrichten, auf der Sie die gleichen Optionen wie die **Anrufeinstellungen für Geschäftszeiten**erhalten.

Sie können Begrüßungen, Ansagen und Menüs einrichten, die Personen hören, wenn Sie die Telefonnummer anrufen, die mit der automatischen Telefonzentrale Ihrer Organisation während der Geschäftszeiten verknüpft ist.

![Screenshot des Abschnitts "Begrüßungs](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![Bildschirm der Geschäftszeiten-Anrufbehandlung" im Abschnitt "Geschäftszeiten-Anrufbehandlung"](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)

* * *

![Symbol der Zahl 1, das auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout1.png)

<a name="greetingsandrouting"> </a>

**Gruß** Eine Begrüßung in Geschäftszeiten ist optional und kann auf **keine Ansage**eingestellt werden. In diesem Fall hört der Anrufer keine Nachricht oder Begrüßung, bevor der Anruf von einer der von Ihnen ausgewählten Aktionen bearbeitet wird. Sie können auch eine Audiodatei hochladen (im WAV-, MP3- oder WMA-Format) oder eine benutzerdefinierte Begrüßung der Sprachausgabe verwenden.
- **Hochladen einer Audiodatei:** Wenn Sie diese Option wählen, zeichnen Sie die Begrüßung auf und laden Sie anschließend Ihre Audiodatei hoch (im wav-, .mp3- oder .wma-Format).
- **Eingeben einer Grußnachricht** Wenn Sie diese Option auswählen, geben Sie den Text ein, der vom System gelesen werden soll (bis zu 1000 Zeichen). Beispielsweise können Sie „Willkommen bei Contoso, Ihr Anruf ist uns sehr wichtig“ im Feld **Anrufer hört** eingeben.

* * *

![Symbol der Zahl 2, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout2.png)

Sie können auswählen, was mit Anrufen geschieht, die während der Geschäftszeiten eingehen. Sie können aus den folgenden Aktionen auswählen:

<a name="redirectcalls"> </a>

- **Verbindung trennen:** Wenn Sie diese Option auswählen, wird die Verbindung der Anrufer nach einer Begrüßung mit Informationen zu den Geschäftszeiten getrennt.
- **Umleiten von Anrufen:** Dies kann verwendet werden, um den Anruf automatisch weiterzuleiten, an:
  - **Person in einem Unternehmen** mit einer **Telefon System** Lizenz, die für Enterprise-VoIP oder zugewiesene Anrufpläne in Office 365 aktiviert ist. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Wählen Sie dazu **Person in Company aus** , und legen Sie diese Person so fest, dass Ihre Anrufe direkt an Voicemail weitergeleitet werden.

    > [!Note]
    > Die **Person im Unternehmen** kann ein Online Benutzer oder ein Benutzer sein, der lokal mit Skype for Business Server 2015 oder lync Server 2013 gehostet wird.

   - Eine andere **automatische Telefonzentrale**

   Sie können eine vorhandene automatische Telefonzentrale verwenden, um eine zweite Ebene von Menü Optionen zu erstellen, die ein Untermenü enthält. Diese werden als geschachtelte automatische Telefonzentralen bezeichnet. Wenn Sie den Anruf an eine geschachtelte automatische Telefonzentrale senden möchten, wählen Sie **Person in Company aus** , und weisen Sie ein Ressourcenkonto zu, das entweder bereits über eine zugeordnete automatische Telefonzentrale verfügt oder das Sie einer automatischen Telefonzentrale zuordnen, sobald Sie mit dem Erstellen der automatischen Telefonzentrale fertig sind.

- Die Optionen für das **Wiedergabemenü** können auch verwendet werden, um eine Ansage einzurichten, die wiedergegeben werden soll.

* * *

![Symbol der Zahl 3, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout3.png)

**Menü Aufforderung** Zum Erstellen der Eingabeaufforderung im Hauptmenü können Sie entweder Text-zu-Sprache verwenden oder eine Audiodatei (WAV, MP3 oder WMA) hochladen. Sie können die Eingabeaufforderung im Feld **Menünavigation für Anrufer einrichten** eingeben oder eine Audiodatei aufzeichnen und beispielsweise Folgendes sagen: "für Verkäufe sagen oder drücken oder sagen Sie" 1 ". Wenn Sie Dienste nutzen, drücken oder sagen Sie "2". Drücken oder sagen Sie für den Kundendienst 3. Drücken oder sagen Sie für den Operator 0. Wenn Sie dieses Menü wieder hören möchten, drücken Sie die Sterntaste oder sagen Sie wiederholen. " **Eingeben einer Grußnachricht** Wenn Sie diese Option ausgewählt haben, sollten Sie den Text eingeben, der vom System gelesen werden soll (bis zu 1000 Zeichen). **Hochladen einer Audiodatei** Wenn Sie diese Option ausgewählt haben, müssen Sie die Begrüßung aufzeichnen und dann Ihre Audiodatei (im WAV-, MP3-oder WMA-Format) hochladen.

* * *

![Symbol der Zahl 4, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout4.png)

**Setup für Menü Optionen** Menü Optionen mit Tasten Schaltflächen auf der Tastatur können hinzugefügt oder entfernt werden. Drücken Sie **+ Zuweisen einer Wähl Taste**, um eine Menüoption hinzuzufügen. Unten wird eine entsprechende Zeile mit Optionen angezeigt. Um eine Menüoption zu löschen, klicken Sie einfach links neben der entsprechenden Taste auf der Tastatursteuerung, und klicken Sie oben auf das Symbol Löschen. Die Zeile der Tastenzuordnung wird entfernt.

> [!TIP]
> Sie müssen den Text der Menü Eingabeaufforderung aktualisieren oder das Audiosignal beim Hinzufügen zu entfernen-Optionen separat erneut aufzeichnen, da es für die vorhandene Menüansage nicht automatisch ausgeführt wird.  
>
>Jede Menüoption kann in beliebiger Reihenfolge hinzugefügt und entfernt werden, und die Tastenzuordnungen müssen nicht kontinuierlich sein. So können Sie beispielsweise ein Menü mit den Tasten 0, 1 und 3 erstellen, die den Optionen zugeordnet sind, während die Taste 2 nicht verwendet wird.

> [!NOTE]
> Die Tasten \* (wiederholen) \# und (zurück) werden vom System reserviert und können nicht neu zugewiesen werden. Wenn die Spracherkennung aktiviert ist, entspricht das Drücken von * mit "Wiederholen", und # entspricht den Sprachbefehlen "zurück".

Wenn Sie Ihre Menü Optionen einrichten möchten, müssen Sie, nachdem Sie die Wähltasten (en) ausgewählt haben, Folgendes tun:

- Geben Sie den **Sprachbefehl** der Option ein. Dies kann bis zu 64 Zeichen lang sein und mehrere Wörter wie "Kundendienst" oder "Vorgänge und Gründe" enthalten. Wenn die Spracherkennung aktiviert ist, wird der Name automatisch erkannt und der Anrufer kann entweder auf 3 drücken, „drei“ oder „Kundenservice“ sagen, um die der Taste 3 zugeordnete Option auszuwählen.
- Wählen Sie aus, wo der Anruf gesendet werden soll, wenn die entsprechende Taste gedrückt wird oder die Option mithilfe der Spracherkennung ausgewählt wird. Der Anruf kann gesendet werden an:

  - **Den Vermittler:** Wenn der Vermittler bereits eingerichtet wurde, wird dieser automatisch der Taste 0 zugeordnet, kann aber auch gelöscht oder einer anderen Taste zugeordnet werden. Wenn der Vermittler keiner Taste zugeordnet ist, wird auch der VoIP-Befehl „Vermittler“ deaktiviert.
  - **Einer Person in Ihrem Unternehmen** mit einer **Telefonsystem** -Lizenz, die für Enterprise Voice aktiviert oder Anruf-Plänen in Office 365 zugeordnet ist. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Wählen Sie dazu **Person in Ihrem Unternehmen** aus, und legen Sie diese Person so fest, dass Ihre Anrufe direkt an Voicemail weitergeleitet werden.

    > [!Note]
    > **Die Person in Ihrem Unternehmen** kann ein Online Benutzer oder ein Benutzer sein, der lokal mit Skype for Business Server oder lync Server 2013 gehostet wird.

  - Eine andere **automatische Telefonzentrale**

       Sie können eine vorhandene automatische Telefonzentrale verwenden, um eine zweite Ebene von Menü Optionen zu erstellen, die ein Untermenü enthält. Diese werden als geschachtelte automatische Telefonzentralen bezeichnet. Wenn Sie den Anruf an eine geschachtelte automatische Telefonzentrale senden möchten, wählen Sie **Person in Company aus** , und weisen Sie ein Ressourcenkonto zu, das entweder bereits über eine zugeordnete automatische Telefonzentrale verfügt oder das Sie einer automatischen Telefonzentrale zuordnen, sobald Sie mit dem Erstellen der automatischen Telefonzentrale fertig sind.

        > [!Note]
        > The **Business Hours** of nested (or second-level) auto attendants will also be used, including for the calls sent from other auto attendants that have been set up.

    - **Sprachanwendung** Wählen Sie den Namen eines Ressourcenkontos aus, das entweder einer Anrufwarteschlange oder einer automatischen Telefonzentrale zugeordnet ist, die bereits erstellt wurde.

* * *

![Symbol der Zahl 5, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout5.png)

**Wählen nach Name** Wenn Sie diese Option auswählen, können Personen, die in Ihrer Organisation anrufen, mithilfe der Verzeichnissuche nach Personen suchen. Sie können auswählen, welche Personen für die Namensanwahl als verfügbar oder nicht verfügbar aufgelistet werden, indem Sie diese Optionen auf der Seite **Wählbereich** einrichten. Jeder Online-Benutzer mit einer **Telefon System** Lizenz oder einem lokal gehosteten Benutzer mit Skype for Business Server oder lync Server 2013 kann mit Dial by Name gefunden werden.

* * *

Wenn Sie Ihre Auswahl getroffen haben, klicken Sie auf **weiter**.

#### <a name="holiday-call-settings"></a>Einstellungen für Feiertags Anrufe

<a name="holidaygreetings"> </a>

Sie können jeder automatische Telefonzentrale bis zu 20 geplante Feiertage hinzufügen.

> [!TIP]
> Sie können den Bildschirm bei den **organisationsweiten Einstellungen** > **für Feiertage öffnen, um Feiertage** zu erstellen, oder Sie können Sie im Rahmen des Erstellens eines neuen Anruf Handlers erstellen.

![Screenshot der Seite "Feiertags Anrufeinstellungen"](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![Symbol der Zahl 1, das auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout1.png)

Wenn Sie bereits andere automatische Telefonzentralen erstellt haben, wird möglicherweise eine Option angezeigt, die Sie verwenden oder bearbeiten können, in der Liste, die Sie benötigen. Wenn dies nicht der Fall ist, müssen Sie einen neuen Anruf Handler erstellen.

Wenn Sie einen neuen Anruf Handler hinzufügen möchten, klicken Sie auf **+ Neuer Anruf Handler**.

* * *

![Screenshot mit dem Hinzufügen eines neuen Anruf Handlers](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![Symbol der Zahl 1, das auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout1.png)

Geben Sie im Fenster neu einen Namen für den neuen Anruf Handler am oberen Rand des Bildschirms ein.

![Symbol der Zahl 2, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout2.png)

Wenn der Name Ihres Feiertags bereits in der Dropdown-Liste " **Feiertag** " vorhanden ist, können Sie ihn verwenden. Wenn der gewünschte Feiertagsname noch nicht vorhanden ist, wählen Sie in der Pulldown-Liste **neue Feiertage erstellen** aus, und weisen Sie dem neuen Bildschirm, der angezeigt wird, einen Namen und ein Datum für den neuen Feiertag zu. Klicken Sie auf **Speichern** , wenn Sie fertig sind.

Feiertags-Namen können bis zu 64 Zeichen lang sein und müssen für die gleiche Telefonzentrale eindeutig sein. Beispielsweise können Sie in derselben automatischen Telefonzentrale keine zwei Feiertage mit dem Namen „Thanksgiving“ haben.

![Symbol der Zahl 3, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout3.png)

**Gruß** Die Begrüßung ist optional und kann auf **keine Grußformel**eingestellt werden. In diesem Fall hört der Anrufer keine Meldung oder die Ansage, bevor der Anruf durch eine der Optionen verarbeitet wird, die Sie auswählen. Sie können auch eine Audiodatei hochladen (im WAV-, MP3- oder WMA-Format) oder eine benutzerdefinierte Begrüßung der Sprachausgabe verwenden.

- **Keine Begrüßung** Wenn Personen die Telefonnummer der automatischen Telefonzentrale anrufen, wird keine Begrüßung wiedergegeben.
- **Hochladen einer Audiodatei** Wenn Sie diese Option auswählen, notieren Sie den Feiertags Gruß, und laden Sie dann Ihre Audiodatei (im WAV-, MP3-oder WMA-Format) hoch.
- **Eingeben einer Grußnachricht** Wenn Sie diese Option auswählen, geben Sie den Text ein, der vom System gelesen werden soll (bis zu 1000 Zeichen). Beispielsweise können Sie „Frohes Neues Jahr!“, unsere Büros sind derzeit geschlossen“ Geben Sie im Feld **Grußnachrichten ein** .

![Symbol der Zahl 4, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout4.png)

**Aktionen** Sie können auswählen, was mit den anrufen passiert, die in diesem Feiertag ankommen. Sie können aus den folgenden Optionen wählen:

- **Verbindung trennen** Die Verbindung des Anrufers wird getrennt, nachdem er die Feiertags-Nachricht gehört hat.
- **Umleiten von Anrufen:** Dies kann verwendet werden, um den Anruf automatisch weiterzuleiten, an:
  - Eine **Person in Ihrem Unternehmen** mit einer **Telefonsystem** -Lizenz, die für Enterprise Voice aktiviert oder Anruf-Plänen in Office 365 zugeordnet ist. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Wählen Sie dazu **Person in Ihrem Unternehmen**aus, und legen Sie diese Person so fest, dass Ihre Anrufe direkt an Voicemail weitergeleitet werden.

    > [!Note]
    > **Die Person in Ihrem Unternehmen** kann ein Online-Benutzer oder ein vor Ort gehosteter Benutzer sein, der den Skype for Business Server 2015 oder den Lync Server 2013 verwendet.

   - **Sprachanwendung** Wählen Sie den Namen eines Ressourcenkontos aus, das entweder einer Anrufwarteschlange oder einer automatischen Telefonzentrale zugeordnet ist, die bereits erstellt wurde.

    > [!Note]
    > Standardmäßig werden alle während eines Feiertags eingehenden Anrufe festgelegt, deren Verbindung nach der Ansage (falls vorhanden) getrennt wird, somit müssen Sie eine Umleitung angeben, wenn ein anderes Verhalten erwünscht ist.

<a name="dialscope"></a>
#### <a name="select-dial-scope-page"></a>Seite „Wählbereich auswählen"

Auf dieser Seite können Sie festlegen, welche Benutzer in Ihrer Organisation in Ihrem Verzeichnis aufgeführt und für die Wahl nach Namen verfügbar sein sollen, wenn eine Person, die sich in Ihre Organisation einwählt.

![Screenshot mit der Seite "Wählbereich"](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

![Symbol der Zahl 1, die auf eine Legende im vorherigen Screenshot](media/sfbcallout1.png) mit der Option " **einbeziehen** " verweist, haben Sie zwei Möglichkeiten:

- **Alle Onlinebenutzer**: Wenn Sie diese Option verwenden, können alle Benutzer in Ihrer Organisation in eine Verzeichnissuche eingeschlossen werden. Alle Online Benutzer mit einer **Telefon System** Lizenz sowie Benutzer, die lokal mit Skype for Business Server oder lync Server 2013 mit Anrufplänen in Office 365 gehostet werden, werden aufgelistet.
- **Benutzerdefinierte Benutzergruppe** Wenn Sie diese Option verwenden, können Sie nach einer Office 365-Gruppe,-Verteilerliste oder-Sicherheitsgruppe suchen, die in Ihrer Organisation erstellt wurde, und den Personen, die zu dieser Office 365-Gruppe,-Verteilerliste oder-Sicherheitsgruppe hinzugefügt wurden, die entweder **Online-Benutzer mit einem Telefon System Lizenz** oder lokal gehostet mit Skype for Business Server 2015 oder lync Server 2013. Sie können mehrere Office 365-Gruppen, Verteilerlisten und Sicherheitsgruppen hinzufügen.

* * *

![Symbol der Zahl 2, die auf eine Legende im vorherigen Screenshot verweist](media/sfbcallout2.png)

Mit der Option **ausschließen** haben Sie zwei Möglichkeiten:

- **Keine**: Wenn Sie diese Option verwenden, werden keine Onlinebenutzer von der Verzeichnissuche ausgeschlossen..
- **Benutzerdefinierte Benutzergruppe** Wenn Sie diese Option verwenden, können Sie nach einer Office 365-Gruppe,-Verteilerliste oder-Sicherheitsgruppe suchen, die in Ihrer Organisation erstellt wurde, und alle Personen, die dieser Office 365-Gruppe,-Verteilerliste oder-Sicherheitsgruppen hinzugefügt wurden, werden von der Verzeichnissuche ausgeschlossen. Sie können mehrere Office 365-Gruppen, Verteilerlisten und Sicherheitsgruppen hinzufügen.

> [!NOTE]
> Es kann bis zu 36 Stunden dauern, bis ein neuer Benutzer seinen Namen im Verzeichnis aufgeführt hat, wenn jemand die Wählfunktion mit der Spracherkennung verwendet.

Nachdem Sie alle erforderlichen Felder eingegeben und die Menüs und Optionen für die Anrufbehandlung eingerichtet haben, klicken Sie auf **Absenden**.

## <a name="editing-and-testing-auto-attendants"></a>Bearbeiten und Testen von automatischen Telefonzentralen

Wenn Sie Ihre automatische Telefonzentrale gespeichert haben, wird diese auf der Seite **Automatische Telefonzentralen** aufgeführt. Auf diese Weise können Sie einige der von Ihnen eingerichteten Optionen, einschließlich Name, Telefonnummer, Sprache und Status, schnell sehen.

Wenn Sie Änderungen an einer automatischen Telefonzentrale vornehmen möchten, wählen Sie die automatische Telefonzentrale aus, und klicken Sie dann im Bereich "Aktion" auf **Bearbeiten**.

Sie können auch schnell einen Testanruf an Ihre automatische Telefonzentrale über die Schaltfläche **Testen** im Bereich "Aktion" platzieren.

## <a name="auto-attendant-cmdlets"></a>Cmdlets für automatische Telefonzentralen

Sie können auch Windows PowerShell verwenden, um automatische Telefonzentralen zu erstellen und einzurichten. Hier sind die Cmdlets, die Sie zum Verwalten einer automatischen Telefonzentrale benötigen:

- [Neu – CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [Satz-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [Get-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)
- [Get-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [Remove-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [Neu – CsAutoAttendantMenu](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [Neu – CsOnlineAudioFile](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [Neu – CsAutoAttendantCallFlow](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [Export-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [New-CsOnlineTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [New-CsOnlineSchedule](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [Get-CsAutoAttendantSupportedTimeZone](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [Neu – CsAutoAttendantCallHandlingAssociation](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [Get-CsAutoAttendantSupportedLanguage](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [Importieren-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [Neu – CsAutoAttendantCallableEntity](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)

### <a name="more-about-windows-powershell"></a>Weitere Informationen zu Windows PowerShell

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 und Microsoft Teams mit einem zentralen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

  - [Einführung in Windows PowerShell und Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Warum Sie Office 365 PowerShell verwenden müssen](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell bietet zahlreiche Vorteile in Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Einstellungsänderungen vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:

  - [Verwalten von Office 365 mit Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Verwandte Themen

[Das Telefonsystem in Office 365 bietet Ihnen Folgendes](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Abrufen von Diensttelefonnummern](/microsoftteams/getting-service-phone-numbers)

[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[New-CsOrganizationalAutoAttendant](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[Was sind automatische Cloudtelefonzentralen?](what-are-phone-system-auto-attendants.md)

[Beispiel für Kleinunternehmen – Einrichten einer automatischen Telefonzentrale](/microsoftteams/tutorial-org-aa)  
