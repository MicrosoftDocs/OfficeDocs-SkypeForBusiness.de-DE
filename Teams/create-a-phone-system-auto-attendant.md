---
title: Einrichten einer automatischen Telefonzentrale des Telefonsystems
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
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
description: Informationen Sie zum Einrichten und Testen von Telefonsystem (Cloud, PBX) automatische Telefonzentralen für effiziente Anruf Behandeln von für Ihre Organisation.
ms.openlocfilehash: 83a59090e447a5bfbda4cf72481b9d6b1ce21a0e
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "30542319"
---
# <a name="set-up-a-phone-system-auto-attendant"></a>Einrichten einer automatischen Telefonzentrale des Telefonsystems

Automatische Telefonzentralen ermöglichen es Personen, die in Ihrer Organisation anrufen, über ein Menüsystem zur richtigen Abteilung, Warteschlange, Person oder dem Telefonisten zu gelangen. Sie können für Ihre Organisation eine automatische Telefonzentrale erstellen, mit dem Microsoft-Teams, Administrationscenter. Zum Erstellen einer neuen automatischen Telefonzentrale, wechseln im linken Navigationsbereich zu **VoIP** , und wählen Sie **automatische Telefonzentralen** > **Hinzufügen**.

Wenn Sie weitere Informationen zu automatischen Telefonzentralen finden möchten, finden Sie unter [Was Telefonsystem automatischen Telefonzentralen sind?](/microsoftteams/what-are-phone-system-auto-attendants)

> [!NOTE]
> Dieser Artikel bezieht sich auf Microsoft-Teams und Skype für Business Online.

## <a name="step-1---getting-started"></a>Schritt 1 - Erste Schritte

- Bevor Sie erstellen und der automatischen Telefonzentralen, einrichten Wenn die automatische Telefonzentrale eine Rufnummer verfügen können (und viele zweiter Ebene fordert oder automatische Telefonzentralen wird nicht geschachtelt erfordern eine Rufnummer ein) müssen Sie zum Abrufen oder übertragen Ihre vorhandenen gebührenpflichtige oder gebührenfreie Service Zahlen . Nachdem Sie die gebührenpflichtige oder gebührenfreie Service Zahlen erhalten möchten, sie werden angezeigt, auf der **Microsoft-Teams, Administrationscenter** > **VoIP** > Seite**Rufnummern** . Um die Rufnummern Service erhalten möchten, finden Sie unter [Getting Service Rufnummern](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md)oder Übertragung und vorhandenen Service-Nummer, finden Sie unter [Übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md). **User (subscriber)** numbers can't be assigned to auto attendants. Wenden Sie sich außerhalb der USA, können das Microsoft-Teams, Administrationscenter Sie Service Zahlen erhalten; Klicken Sie [hier](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

    > [!CAUTION]
    > Zum Abrufen und gebührenfreien Telefonnummern verwenden, müssen Sie Communications haben einrichten. Hierzu finden Sie [Was sind Communications haben?](what-are-communications-credits.md) und [Communications haben für Ihre Organisation einrichten](set-up-communications-credits-for-your-organization.md).
  
- Ihre Organisation muss eine Lizenz Enterprise E3 plus **Telefonsystem** oder einer E5 Enterprise-Lizenz (mindestens) verfügen. Die Anzahl der **Telefonsystem** Benutzerlizenzen, die zugewiesen sind, wirkt sich auf die Anzahl der Dienst Zahlen, die für automatische Telefonzentralen zu verwendende verfügbar sind. Die Nummern der automatischen Telefonzentralen können Ihnen ist abhängig von die Zahlen **Telefonsystem** und **Audiokonferenzen** -Lizenzen, die in Ihrer Organisation zugewiesen sind. Weitere Informationen zur Lizenzierung finden Sie [hier](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

    > [!TIP]
    > Zum Umleiten von Anrufen an einen Operator oder eine Menüoption, die ein Benutzer Online mit einer Lizenz **Telefonsystem** ist, müssen Sie für Enterprise-VoIP zu aktivieren oder Aufrufen in Office 365-Pläne ihnen zuweisen. Siehe [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Sie können auch die Windows PowerShell verwenden. Führen Sie beispielsweise Folgendes aus:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

## <a name="step-2---create-a-new-auto-attendant"></a>Schritt 2 - Erstellen einer neuen automatischen Telefonzentrale

> [!IMPORTANT]
> Jeder Anruf Warteschlange ist erforderlich, um einer zugeordneten [Ressource-Konto](manage-resource-accounts.md)haben. Sie müssen das Ressourcenkonto erstellen und dann können Sie es an die automatische Telefonzentrale zuordnen.

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden das Microsoft-Teams, Administrationscenter

In der **Microsoft-Teams, Administrationscenter**, klicken Sie auf **VoIP** > **automatische Telefonzentralen**, klicken Sie dann auf **+ neu**:

#### <a name="general-info-page"></a>Seite "Allgemein"

![New auto attendant page 1.](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![Nummer 1](media/sfbcallout1.png)

**Name** Geben Sie einen aussagekräftigen Anzeigenamen für die automatische Telefonzentrale. Der Name ist erforderlich und kann maximal 64 Zeichen einschließlich Leerzeichen enthalten. Er wird in der Spalte **Name** der Registerkarte **Automatische Telefonzentralen** aufgeführt.

* * *

![Nummer 2](media/sfbcallout2.png)

**Ressource-Konto** Klicken Sie auf diese Schaltfläche, um eine oder mehrere Ressourcenkonten für Ihre neue automatische Telefonzentrale die Verbindung auswählen. Alle automatischen Telefonzentralen sind erforderlich, um über ein Ressourcenkonto zugeordneten verfügen. Ein Ressourcenkonto kann eine Telefonnummer ein, das Konto zugeordnet ist, aber möglicherweise nicht. Eine automatische Telefonzentrale auf oberster Ebene würde fast immer würde ein Ressourcenkonto mit einer zugewiesene Telefonnummer, eine sekundären Telefonzentrale (als Ebene 2 Menü die erste Ebene Telefonzentrale für die Verbindung mit verwendet) möglicherweise auf einfache Weise müssen jedoch nicht zugewiesene eine Telefonnummer seine Ressource-Konto

* * *

![Nummer 3](media/sfbcallout3.png)

**Zeitzone**: Sie müssen die Zeitzone für Ihre automatische Telefonzentrale festlegen. Die Zeitzone muss jedoch nicht der Zeitzone der für Ihre Organisation angegebenen Hauptadresse entsprechen. Sie können für jede automatische Telefonzentrale eine andere Zeitzone festlegen. Die Geschäftszeiten für die automatische Telefonzentrale werden basierend auf der Zeitzone festgelegt, die Sie hier auswählen.

* * *

![Nummer 4](media/sfbcallout4.png)

**Sprache**: Wählen Sie unter den aufgeführten verfügbaren Sprachen die Sprache aus, die Sie für die automatische Telefonzentrale verwenden möchten. Die Sprache, die Sie hier festlegen, wird die Sprache, die die automatische Telefonzentrale zum interagieren mit Personen, die diese automatische Telefonzentrale anrufen, und fordert das System werden in dieser Sprache wiedergegeben werden.

* * *

![Nummer 5](media/sfbcallout5.png)

**Operator**: Diese Einstellung ist optional und muss für die automatische Telefonzentrale nicht festgelegt werden. Sie können jedoch die Option **Operator** für die Personen festlegen, die im Unterbrechungsmodus außerhalb des Kontextmenüs an eine Person, die sie unterstützen sprechen können aufrufen.

Die Taste „0" wird automatisch der Vermittlung zugewiesen.

Wenn Sie dies festlegen, müssen Sie auch Personen mitteilen, die aufgerufen wird, insofern Dies ist eine verfügbare Option in den **Menüoptionen im bearbeiten** auf der Seite **Geschäftszeiten Behandlung aufrufen** . Wenn Sie einen Operator für die automatische Telefonzentrale festlegen, müssen Sie geben den entsprechenden Prompt Text im Feld **Anrufer hören** oder Ändern Ihrer Audiodatei, wenn Sie diese Option. Beispiel: „Drücken Sie ‚0', um mit der Vermittlung zu sprechen".

Als Vermittlung können Sie Folgendes festlegen:

- **Person in Ihrem Unternehmen** mit einer **Telefonsystem**-Lizenz, die für Enterprise Voice aktiviert oder Anruf-Plänen in Office 365 zugeordnet ist.

     > [!Note]
     > **Die Person in Ihrem Unternehmen** kann ein Online-Benutzer oder ein vor Ort gehosteter Benutzer sein, der den Skype for Business Server 2015 oder den Lync Server 2013 verwendet. Der Lync Server 2010 wird nicht unterstützt.

- Eine **Warteschlange aufrufen** , die Sie eingerichtet haben.
- Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Zu diesem Zweck wählen Sie **Person in Ihrem Unternehmen** aus, und legen Sie diese Person Anrufe an die Voicemail weitergeleitet werden.

* * *

![Nummer 6](media/sfbcallout6.png)

**Spracheingaben aktivieren** Die Spracherkennung ist verfügbar, wenn diese Option ausgewählt ist. Personen, die in aufrufen können Spracheingaben in der [Sprache, die Sie festlegen](set-auto-attendant-languages-for-audio-conferencing-in-teams.md). Sie können die Spracherkennung deaktivieren, indem Sie es aus, wenn Sie nur Personen, die ihre Telefontastatur verwenden können möchten.

* * *

Wenn Sie mit Ihrer Auswahl fertig sind, klicken Sie auf **Weiter**.

#### <a name="business-hours-page"></a>Seite Geschäftszeiten

Geschäftszeiten werden standardmäßig auf 9 Uhr bis 17 Uhr, Montag bis Freitag festgelegt.  Alle Zeiten, die nicht innerhalb der Geschäftszeiten liegen, werden als außerhalb der Geschäftszeiten angesehen. Klicken Sie auf **24/7 Wählen** , um alle Stunden Geschäftszeiten stellen. Wenn Sie die Option **Wählen 24/7** auswählen, wird die Seite **nach dem Aufruf von Stunden Einstellungen** so konfigurieren Sie den Anruf behandeln für Geschäftszeiten für die automatische Telefonzentrale verwendet werden.

![New auto attendant Hours of operation.](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![Nummer 1](media/sfbcallout1.png)

Geschäftszeiten werden standardmäßig auf Montag Freitag, 09:00 h - 5:00 Uhr festgelegt. Wählen Sie **Deaktivieren aller Stunden, die** Option alle Stunden Stundenangaben des Zeitplans aufheben. Wenn Sie **auf Standard zurücksetzen**auswählen, werden auf Montag Freitag, 09:00 h - 5:00 Uhr Geschäftszeiten zurückgesetzt.

* * *

![Nummer 2](media/sfbcallout2.png)

Um Geschäftszeiten zu ändern, markieren Sie die Geschäftszeiten, die Sie einstellen möchten, im Kalender. Der Kalender ermöglicht Ihnen die Auswahl von Geschäftszeiten in Abständen von 30 Minuten, und die Geschäftszeiten, die Sie hier auswählen, werden entsprechend der Zeitzone eingestellt, die Sie auf der Seite „ **Allgemeine Daten“** festlegen. Um eine Pause (beispielsweise eine Mittagspause) einzurichten, deaktivieren, oder ziehen Sie zum Deaktivieren die Zeit im Kalender. Sie können innerhalb der Geschäftszeiten mehrere Pausen festlegen.

* * *

Wenn Sie mit Ihrer Auswahl fertig sind, klicken Sie auf **Weiter**.

#### <a name="business-hours-call-settings"></a>Geschäftszeiten Einstellungen für die

> [!TIP]
> Wenn Sie einen Zeitplan für die benutzerdefinierte Geschäftszeiten verwenden, müssen Sie auch Anruf über die Seite **nach dem Aufruf von Stunden behandeln** , an die gleichen Optionen wie **Geschäftszeiten Einstellungen für die**Geschäftszeiten für zuzuteilen einrichten.

Begrüßungen, Ansagen und Menüs können, die es Benutzern eingerichtet werden, die während der Geschäftszeiten Anruf in Ihrer Organisation Auto attendant Telefonnummer hören kann.

![Geschäftszeiten Anrufbehandlung. ](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
 ![Geschäftszeiten Anrufbehandlung fortgesetzt.](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)

* * *

![Nummer 1](media/sfbcallout1.png)

**Begrüßung** Eine Begrüßung während der Geschäftszeit ist optional und kann auf **kein Ansage**festgelegt werden. In diesem Fall hören der Anrufer keine Meldung oder die Ansage, bevor der Anruf durch eine der Aktionen, die Sie auswählen, verarbeitet wird. Sie können auch eine Audiodatei hochladen (im WAV-, MP3- oder WMA-Format) oder eine benutzerdefinierte Begrüßung der Sprachausgabe verwenden.

- **Keine Begrüßung** Keine Ansage wird wiedergegeben werden, wenn Personen die automatische Telefonzentrale Telefonnummer anrufen.
- **Hochladen einer Audiodatei:** Wenn Sie diese Option wählen, zeichnen Sie die Begrüßung auf und laden Sie anschließend Ihre Audiodatei hoch (im wav-, .mp3- oder .wma-Format).
- **Geben Sie eine Nachricht ein Ansage** Wenn Sie diese Option auswählen, geben Sie den Text (bis zu 1000 Zeichen) gelesen werden soll. Beispielsweise können Sie „Willkommen bei Contoso, Ihr Anruf ist uns sehr wichtig“ im Feld **Anrufer hört** eingeben.

* * *

![Nummer 2](media/sfbcallout2.png)

Sie können auswählen, was mit Anrufen geschieht, die während der Geschäftszeiten eingehen. Sie können wählen Sie aus der folgenden Aktionen aus:

- **Verbindung trennen:** Wenn Sie diese Option auswählen, wird die Verbindung der Anrufer nach einer Begrüßung mit Informationen zu den Geschäftszeiten getrennt.
- **Umleiten von Anrufen:** Dies kann verwendet werden, um den Anruf automatisch weiterzuleiten, an:
  - **Person im Unternehmen** mit einer **Telefonsystem** -Lizenz, die für Enterprise Voice aktiviert oder Aufrufen in Office 365-Pläne zugeordnet ist. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Zu diesem Zweck wählen **Person im Unternehmen** aus, und legen Sie diese Person ihre Anrufe an die Voicemail weitergeleitet werden.

    > [!Note]
    > **Person im Unternehmen** kann es sich um ein Online-Benutzer oder ein Benutzer gehostet: lokal mit Skype für Business Server 2015 oder Lync Server 2013. Der Lync Server 2010 wird nicht unterstützt.

   - Eine andere **automatische Telefonzentrale**

   Eine vorhandene automatische Telefonzentrale können Sie eine zweite Ebene im Menü Optionen, die mit einem Untermenü erstellen. Diese werden als geschachtelte automatische Telefonzentralen bezeichnet. Um den Anruf an eine automatische Telefonzentrale geschachtelte senden möchten, wählen Sie **Person im Unternehmen** aus, und weisen Sie ein Ressourcenkonto entweder diejenige, die bereits verfügt über eine zugehörige automatische Telefonzentrale oder eine, die Sie zuordnen möchten, um eine automatische Telefonzentrale, sobald Sie fertig sind diese automatische Telefonzentrale erstellen.

- **Wiedergeben von Menüoptionen** kann auch verwendet werden, bei denen Sie eine Aufforderung einrichten, die abgespielt werden soll.

* * *

![Nummer 3](media/sfbcallout3.png)

**Menü Aufforderung** Um hauptmenüansage zu erstellen, können Sie verwenden der Sprachausgabe oder Hochladen einer Audiodatei (WAV-, MP3 oder WMA). Geben Sie die Aufforderung im Feld **Ihre Menünavigation für Anrufer festlegen** oder Aufzeichnen einer Audiodatei und sag, zum Beispiel: "für den Vertrieb, sagen drücken oder 1 angenommen. Drücken Sie für Dienste die oder Angenommen Sie 2. Drücken Sie für die Unterstützung von Kunden oder sagen Sie 3. Für den Operator drücken oder 0 sagen. Um dieses Menü erneut zu hören, drücken Sie die Sterntaste, oder sprechen Sie wiederholen Sie." **Geben Sie eine Nachricht ein Ansage** Wenn Sie dies gewählt haben, sollten Sie den Text eingeben (bis zu 1000 Zeichen) gelesen werden soll. **Hochladen einer Audiodatei** Wenn Sie dies gewählt haben, müssen Sie die Ansage aufzeichnen und anschließendes Hochladen der Audiodatei (im WAV-, MP3- oder WMA-Format).

* * *

![Nummer 4](media/sfbcallout4.png)

**Menü Optionen setup** Mithilfe der wichtigsten Schaltflächen auf der Tastatur Menüoptionen können hinzugefügt oder entfernt werden. Drücken Sie zum Hinzufügen einer Menüoption **+ weisen Dial-Taste**. Nachfolgend wird eine entsprechende Zeile der Optionen angezeigt. Um eine Menüoption zu löschen, klicken Sie links neben dem entsprechenden Schlüssel für das Steuerelement, Tastatur auf und klicken Sie auf das Löschsymbol oben. Die Zeile der Tastenzuordnung wird entfernt.

> [!TIP]
> Sie müssen im Menü Ansagen Text aktualisieren oder erneut zeichnet separat beim Entfernen von Optionen, da dies automatisch für die Aufforderung zur vorhandenen Menü erfolgen wird nicht hinzugefügt.  
>
>Alle Menüoption hinzugefügt und in beliebiger Reihenfolge entfernt werden kann, und die tastenzuordnungen müssen nicht zusammenhängend sein. Es ist beispielsweise möglich, erstellen Sie ein Menü mit Tasten 0, 1 und 3 auf Optionen, zugeordnet werden, während die Taste 2 nicht verwendet wird.

> [!NOTE]
> Die Schlüssel \* (Wiederholung) und \# (zurück) werden vom System reserviert und nicht neu zugewiesen werden. Wenn die Spracherkennung aktiviert ist, drücken * wird mit "Wiederholen" entsprechen und # wird mit "Zurück" Sprachbefehle entsprechen.

Zum Einrichten Ihrer Menüoptionen nach dem Auswählen der Einwahl Keys benötigen Sie:

- Geben Sie den **Sprachbefehl** der Option. Dies kann bis zu 64 Zeichen lang sein und kann enthalten mehrere Wörter wie "Customer Service" oder "Vorgänge und Gründe." Wenn die Spracherkennung aktiviert ist, wird der Name automatisch erkannt und der Anrufer kann entweder auf 3 drücken, „drei“ oder „Kundenservice“ sagen, um die der Taste 3 zugeordnete Option auszuwählen.
- Wählen Sie aus, in dem der Anruf ist gesendet werden, wenn die entsprechende Taste gedrückt wird, oder die Option mithilfe der Spracherkennung aktiviert ist. Der Anruf kann gesendet werden an:

  - **Den Vermittler:** Wenn der Vermittler bereits eingerichtet wurde, wird dieser automatisch der Taste 0 zugeordnet, kann aber auch gelöscht oder einer anderen Taste zugeordnet werden. Wenn der Vermittler keiner Taste zugeordnet ist, wird auch der VoIP-Befehl „Vermittler“ deaktiviert.
  - **Einer Person in Ihrem Unternehmen** mit einer **Telefonsystem** -Lizenz, die für Enterprise Voice aktiviert oder Anruf-Plänen in Office 365 zugeordnet ist. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Zu diesem Zweck wählen **Person in Ihrem Unternehmen** aus, und legen Sie diese Person ihre Anrufe an die Voicemail weitergeleitet werden.

    > [!Note]
    > **Die Person in Ihrem Unternehmen** kann ein Online-Benutzer oder ein vor Ort gehosteter Benutzer sein, der den Skype for Business Server 2015 oder den Lync Server 2013 verwendet. Der Lync Server 2010 wird nicht unterstützt.
    - Eine andere **automatische Telefonzentrale**

       Eine vorhandene automatische Telefonzentrale können Sie eine zweite Ebene im Menü Optionen, die mit einem Untermenü erstellen. Diese werden als geschachtelte automatische Telefonzentralen bezeichnet. Um den Anruf an eine automatische Telefonzentrale geschachtelte senden möchten, wählen Sie **Person im Unternehmen** aus, und weisen Sie ein Ressourcenkonto entweder diejenige, die bereits verfügt über eine zugehörige automatische Telefonzentrale oder eine, die Sie zuordnen möchten, um eine automatische Telefonzentrale, sobald Sie fertig sind diese automatische Telefonzentrale erstellen.

        > [!Note]
        > Die **Geschäftszeiten** geschachtelter automatischer Telefonzentralen (oder mit zweiter Ebene) werden ebenfalls eingesetzt, einschließlich der Anrufe, die von anderen Telefonzentralen eingehen, die eingerichtet wurden.

<!--    - **call queue** Using a call queue option allows the call to be transferred to an existing call queue that you have set up. -->

* * *

![Nummer 5](media/sfbcallout5.png)

**Wählen Sie nach Namen** Wenn Sie diese Option auswählen, können diese Personen, die in die Suche nach Personen in Ihrer Organisation mithilfe der Verzeichnissuche aufrufen. Sie können auswählen, welche Personen für die Namensanwahl als verfügbar oder nicht verfügbar aufgelistet werden, indem Sie diese Optionen auf der Seite **Wählbereich** einrichten. Jeder Online-Benutzer mit einer **Telefonsystem**-Lizenz oder ein beliebiger Benutzer der vor Ort gehostet wird und den Skype for Business Server 2015 oder den Lync Server 2013 verwenden, finden Sie unter nach Namen wählen.

> [!WARNING]
> Benutzer, die lokal gehostet werden und Lync 2010 verwenden, können mit nach Namen wählen **nicht erreicht werden**.

* * *

Wenn Sie mit Ihrer Auswahl fertig sind, klicken Sie auf **Weiter**.

#### <a name="holiday-call-settings"></a>Einstellungen für Urlaub

Sie können jeder automatische Telefonzentrale bis zu 20 geplante Feiertage hinzufügen.

> [!TIP]
> Navigieren Sie die dem Bildschirm unter **Org geltende Einstellungen** > **Feiertage** zum Erstellen von Feiertagen, oder Sie können diese als Teil der Erstellung einer neuen anrufbearbeiter erstellen.

![Einrichten von Feiertagen in der automatischen Telefonzentrale](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![Nummer 1](media/sfbcallout1.png)

Wenn Sie bereits andere automatische Telefonzentralen erstellt haben, können Sie eine Option finden Sie unter können verwenden oder in der gewünschten Informationen in dieser Liste bearbeitet. Wenn dies nicht der Fall ist, Sie müssen einen neuen Anruf-Ereignishandler erstellen.

Um einen neuen Anruf Ereignishandler hinzuzufügen, klicken Sie auf **+ New-Handler aufrufen**.

* * *

![Einrichten von Feiertagen in Fortsetzung automatische Telefonzentrale](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![Nummer 1](media/sfbcallout1.png)

Klicken Sie im neuen Geben Sie einen Namen für die neue anrufbearbeiter im oberen Bereich des Bildschirms.

![Nummer 2](media/sfbcallout2.png)

Wenn der Name der bereits in der Liste der **Feiertage** Pulldownmenü vorhanden ist, können Sie es. Wenn der Name des Feiertags Menschen, mit denen nicht bereits vorhanden ist, wählen Sie in der Dropdownliste aus und weisen einen Namen und ein Datum für den neuen Feiertag in der neuen im nun angezeigten Bildschirm **erstellen neue Feiertag** aus. Klicken Sie auf **Speichern** , wenn Sie bereit sind.

Feiertags-Namen können bis zu 64 Zeichen lang sein und müssen für die gleiche Telefonzentrale eindeutig sein. Beispielsweise können Sie in derselben automatischen Telefonzentrale keine zwei Feiertage mit dem Namen „Thanksgiving“ haben.

![Nummer 3](media/sfbcallout3.png)

**Begrüßung** Die Ansage ist optional und kann auf **kein Ansage**festgelegt werden. In diesem Fall hört der Anrufer keine Meldung oder die Ansage, bevor der Anruf durch eine der Optionen verarbeitet wird, die Sie auswählen. Sie können auch eine Audiodatei hochladen (im WAV-, MP3- oder WMA-Format) oder eine benutzerdefinierte Begrüßung der Sprachausgabe verwenden.

- **Keine Begrüßung** Keine Ansage wird wiedergegeben werden, wenn Personen die automatische Telefonzentrale Telefonnummer anrufen.
- **Hochladen einer Audiodatei** Wenn Sie diese Option wählen, Aufzeichnen der Grußformel Feiertag und anschließendes Hochladen der Audiodatei (im WAV-, MP3 oder WMA-Format)
- **Geben Sie eine Nachricht ein Ansage** Wenn Sie diese Option auswählen, geben Sie den Text (bis zu 1000 Zeichen) gelesen werden soll. Beispielsweise können Sie „Frohes Neues Jahr!“, unsere Büros sind derzeit geschlossen“ im Feld **Typ eine Ansage Nachricht** .

![Nummer 4](media/sfbcallout4.png)

**Aktionen** Sie können auswählen, was geschieht, an die Anrufe, die während dieses Feiertag eingehen. Sie können aus den folgenden Optionen wählen:

- **Verbindung trennen** Die Verbindung des Anrufers wird getrennt, nachdem er die Feiertags-Nachricht gehört hat.
- **Umleiten von Anrufen:** Dies kann verwendet werden, um den Anruf automatisch weiterzuleiten, an:
  - Eine **Person in Ihrem Unternehmen** mit einer **Telefonsystem** -Lizenz, die für Enterprise Voice aktiviert oder Anruf-Plänen in Office 365 zugeordnet ist. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Zu diesem Zweck wählen **Person in Ihrem Unternehmen**aus, und legen Sie diese Person ihre Anrufe an die Voicemail weitergeleitet werden.

    > [!Note]
    > **Die Person in Ihrem Unternehmen** kann ein Online-Benutzer oder ein vor Ort gehosteter Benutzer sein, der den Skype for Business Server 2015 oder den Lync Server 2013 verwendet. Der Lync Server 2010 wird nicht unterstützt.

  - Eine **Warteschlange anrufen** auf den Anruf an eine vorhandene Anruf Warteschlange übertragen, die Sie eingerichtet haben.
  - Eine andere **automatische Telefonzentrale**, erstellen Sie eine zweite Ebene im Menü Optionen, die einem Untermenü enthält. Diese werden als geschachtelte automatische Telefonzentralen bezeichnet.

    > [!Note]
    > Standardmäßig werden alle während eines Feiertags eingehenden Anrufe festgelegt, deren Verbindung nach der Ansage (falls vorhanden) getrennt wird, somit müssen Sie eine Umleitung angeben, wenn ein anderes Verhalten erwünscht ist.

#### <a name="select-dial-scope-page"></a>Seite „Wählbereich auswählen"

Auf dieser Seite können Sie die Benutzer in Ihrer Organisation aufgelistet in Ihrem Verzeichnis und bereit zur Einwahl nach Name, wenn eine Person, die Aufrufe eingefügt werden Ihrer Organisation einrichten.

![Dial scope for searching with dial by name.](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

![Nummer 1](media/sfbcallout1.png) verwenden die Option **einschließen** , haben Sie zwei Optionen:

- **Alle Onlinebenutzer**: Wenn Sie diese Option verwenden, können alle Benutzer in Ihrer Organisation in eine Verzeichnissuche eingeschlossen werden. Alle Online-Benutzer mit einer **Telefonsystem**-Lizenz und auch lokal gehostete Benutzer, die den Skype for Business Server 2015 oder den Lync Server 2013 verwenden, die Anruf-Pläne in Office 365 haben, werden aufgeführt.
- **Benutzerdefinierte Gruppe** Wenn Sie diese Option verwenden, Sie können für eine Gruppe von Office 365, Verteilerliste oder Sicherheitsgruppe an, die in Ihrer Organisation erstellt wurde, suchen, und Personen hinzugefügt in Office 365, Verteilerliste, oder Sicherheitsgruppe, die entweder **sind Online-Benutzer mit einem Telefon-Lizenz** oder gehostete lokalen Skype für die Business Server 2015 oder Lync Server 2013. Sie können mehrere Office 365-Gruppen, Verteilerlisten und Sicherheitsgruppen hinzufügen.

  > [!Caution]
  > Lokale Benutzer aus der Bereitstellung von Lync Server 2010 wird nicht aufgeführt, wenn jemand das Verzeichnis mit Dial sucht nach Namen.

* * *

![Nummer 2](media/sfbcallout2.png)

Verwenden die Option **ausschließen** , haben Sie zwei Optionen:

- **Keine**: Wenn Sie diese Option verwenden, werden keine Onlinebenutzer von der Verzeichnissuche ausgeschlossen..
- **Benutzerdefinierte Gruppe** Wenn Sie diese Option verwenden, Sie können für eine Gruppe von Office 365, Verteilerliste oder Sicherheitsgruppe an, die in Ihrer Organisation erstellt wurde, suchen und alle Personen an diese Office 365 Gruppe Verteilerliste hinzugefügt oder Sicherheitsgruppen aus Verzeichnissuche ausgeschlossen. Sie können mehrere Office 365-Gruppen, Verteilerlisten und Sicherheitsgruppen hinzufügen.

  > [!Caution]
  > Lokale Benutzer aus der Bereitstellung von Lync Server 2010 wird nicht aufgeführt, wenn jemand das Verzeichnis mit Dial sucht nach Namen.

> [!NOTE]
> Es kann bis zu 36 Stunden für einen neuen Benutzer haben ihre Namen in das Verzeichnis, wenn ein Benutzer Einwahl verwendet nach Namen für die Spracherkennung dauern.

Nachdem Sie alle erforderlichen Felder eingeben und richten Sie arbeiten mit Menüs und Optionen, klicken Sie auf **Absenden**.

## <a name="editing-and-testing-auto-attendants"></a>Bearbeiten und Testen von automatischen Telefonzentralen

Wenn Sie Ihre automatische Telefonzentrale gespeichert haben, wird diese auf der Seite **Automatische Telefonzentralen** aufgeführt. Dadurch können Sie schnell einige Optionen anzuzeigen, die Sie nach oben, festgelegt haben, einschließlich Name, Rufnummer, Sprache und Status.

Wenn Sie eine automatische Telefonzentrale ändern möchten, wählen Sie die automatische Telefonzentrale aus, und klicken Sie dann im Bereich Aktion auf **Bearbeiten**.

Sie können einen Testanruf an die automatische Telefonzentrale auch schnell mithilfe der Schaltfläche **Testen** im Aktionsbereich platzieren.

## <a name="want-to-know-more"></a>Möchten Sie mehr wissen?

Sie können auch Windows PowerShell verwenden, um automatische Telefonzentralen zu erstellen und einzurichten.

### <a name="auto-attendant-cmdlets"></a>Cmdlets für automatische Telefonzentralen

Zum Verwalten einer automatischen Telefonzentrale benötigen Sie die folgenden Cmdlets.

|||
|---  |---  |
| [New-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796493.aspx) | [New-CsOrganizationalAutoAttendantPrompt](https://technet.microsoft.com/library/mt796484.aspx) |
| [Set-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796486.aspx) | [New-CsOrganizationalAutoAttendantMenuOption](https://technet.microsoft.com/library/mt796485.aspx) |
| [Get-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796482.aspx) | [Get-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csorganizationalautoattendantholidays?view=skype-ps) |
| [Remove-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796492.aspx) | [New-CsOrganizationalAutoAttendantMenu](https://technet.microsoft.com/library/mt796488.aspx) |
| [New- CsOnlineAudioFile](https://technet.microsoft.com/library/mt796479.aspx) | [New-CsOrganizationalAutoAttendantCallFlow](https://technet.microsoft.com/library/mt796489.aspx) |
| [Export-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps) | [New-CsOnlineTimeRange](https://technet.microsoft.com/library/mt796491.aspx) |
| [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps) | [New-CsOnlineSchedule](https://technet.microsoft.com/library/mt796490.aspx) |
| [Get-CsOrganizationalAutoAttendantSupportedTimeZone](https://technet.microsoft.com/library/mt796483.aspx) | [New-CsOrganizationalAutoAttendantCallHandlingAssociation](https://technet.microsoft.com/library/mt796487.aspx) |
| [Get-CsOrganizationalAutoAttendantSupportedLanguage](https://technet.microsoft.com/library/mt796481.aspx) | [Import-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csorganizationalautoattendantholidays?view=skype-ps) |
| [New-CsOrganizationalAutoAttendantCallableEntity](https://technet.microsoft.com/library/mt796480.aspx) | |

### <a name="more-about-windows-powershell"></a>Weitere Informationen zu Windows PowerShell

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 und eine zentrale Verwaltung Ihrer täglichen Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen, die mit Microsoft-Teams verwalten. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

  - [Einführung in Windows PowerShell und Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Warum Sie Office 365 PowerShell verwenden müssen](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:

  - [Verwalten von Office 365 mit Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Verwandte Themen

[Das Telefonsystem in Office 365 bietet Ihnen Folgendes](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Anfordern von Servicenummern](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[New-CsOrganizationalAutoAttendant](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[Was sind automatische Telefonzentralen des Telefonsystems?](what-are-phone-system-auto-attendants.md)

[Beispiel für Small Business - richten Sie eine automatische Telefonzentrale](/skypeforbusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml)  