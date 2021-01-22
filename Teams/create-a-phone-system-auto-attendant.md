---
title: Einrichten einer automatischen Attendant für Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Erfahren Sie, wie Sie automatische Attendants für Microsoft Teams einrichten und testen.
ms.openlocfilehash: 4809965eaad0f8cd81b59823d3890bd895998906
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49919039"
---
# <a name="set-up-an-auto-attendant"></a>Einrichten einer automatischen Attendant

Mit automatischen Telefonkonferenzen können Personen Ihre Organisation anrufen und in einem Menüsystem navigieren, um mit der richtigen Abteilung, der Anrufwarteschleife, einer Person oder einem Operator zu sprechen. Sie können automatische Attendanten für Ihre Organisation über das Microsoft Teams Admin Center oder mit PowerShell erstellen.

Vergewissern Sie sich, dass Sie die Planung für automatische [](plan-auto-attendant-call-queue.md#getting-started) Telefonisten in [Teams](plan-auto-attendant-call-queue.md) und Anrufwarteschleifen gelesen und die Schritte für die ersten Schritte befolgt haben, bevor Sie die in diesem Artikel erläuterten Schritte ausführen.

Automatische Telefon attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a>

- **Person in der Organisation** – eine Person in Ihrer Organisation, die Sprachanrufe empfangen kann. Dies kann ein Onlinebenutzer oder ein Lokal mit Skype for Business Server gehosteter Benutzer sein.
- **Sprach-App** – eine andere automatische Telefonkonferenz oder eine Anrufwarteschleife. (Wählen Sie das Ressourcenkonto aus, das der automatischen Telefonwarteschlange oder Anrufwarteschleife zugeordnet ist, wenn Sie dieses Ziel auswählen.)
- **Externe Telefonnummer –** beliebige Telefonnummer. (Siehe [technische Details zur externen Übertragung).](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)
- **Voicemail –** das Sprachpostfach, das einer von Ihnen angegebenen Microsoft 365-Gruppe zugeordnet ist.
- **Operator** – der für die automatische Attendant definierte Operator. Das Definieren eines Operators ist optional. Der Operator kann als jedes der anderen Ziele in dieser Liste definiert werden.

Sie werden beim Einrichten einer automatischen Attendant in verschiedenen Phasen aufgefordert, eine dieser Optionen zu wählen.

Zum Einrichten einer automatischen Telefonzentrale erweitern Sie im Teams Admin Center "Sprache", klicken auf **"Automatische** Telefonzentralen" und dann auf **"Hinzufügen".**

## <a name="general-info"></a>Allgemeine Informationen

![Screenshot der Einstellungen der automatischen Telefongesellschaft für Name, Operator, Zeitzone, Sprache und Spracheingaben](media/auto-attendant-general-info-page-new.png)

1. Geben Sie einen Namen für die automatische Attendant in das Feld oben ein.

2. Wenn Sie einen Operator bestimmen möchten, geben Sie das Ziel für Aufrufe an den Operator an. Dies ist optional (aber empfohlen). Sie können die **Operatoroption festlegen,** damit Anrufer aus den Menüs ausbrechen und mit einer bestimmten Person sprechen können.

3. Geben Sie die Zeitzone für diese automatische Attendant an. Die Zeitzone wird verwendet, um die Geschäftszeiten zu berechnen, wenn Sie [einen separaten Anruffluss für die Nachstunden erstellen.](#call-flow-for-after-hours)

4. Geben Sie eine Sprache für diese automatische Attendant an. Dies ist die Sprache, die für vom System generierte Sprachanrufe verwendet wird.

5. Wählen Sie aus, ob Sie Spracheingaben aktivieren möchten. Wenn diese Option aktiviert ist, wird der Name jeder Menüoption zu einem Schlüsselwort für die Spracherkennung. Anrufer können z. B. "Eins" sagen, um die Menüoption auszuwählen, die der Taste "1" zugeordnet ist, oder "Vertrieb", um die Menüoption "Vertrieb" auszuwählen.

6. Klicken Sie auf **Weiter**.

## <a name="call-flow"></a>Anruffluss

![Screenshot der Einstellungen für Begrüßungsnachrichten](media/auto-attendant-call-flow-greeting-message.png)

Wählen Sie aus, ob eine Begrüßung abspielen soll, wenn die automatische Telefonkonferenz einen Anruf beantwortet.

Wenn Sie "Audiodatei **wiedergabe" auswählen,** können Sie die Schaltfläche "Datei hochladen" verwenden, um eine aufgezeichnete Begrüßungsnachricht hochzuladen, die als Audio gespeichert wurde.  WAV, . MP3 oder . WMA-Format. Die Aufzeichnung darf nicht größer als 5 MB sein.

Wenn Sie **eine** Begrüßungsnachricht eingeben, liest das System den Text vor, den Sie eingeben (bis zu 1.000 Zeichen), wenn die automatische Telefonanlage einen Anruf entgegen nimmt.

![Screenshot der Einstellungen für die Anrufrouting](media/auto-attendant-call-flow-route-call-message.png)

Wählen Sie aus, wie sie den Anruf routen möchten.

Wenn Sie **"Trennen"** auswählen, hängt die automatische Telefon attendant den Anruf auf.

Wenn Sie **"Umleitungsanruf"** auswählen, können Sie eines der Anrufroutingziele auswählen.

Wenn Sie **"Wiedergabe"-Menüoptionen auswählen,** können  Sie eine Audiodatei wiedergibt oder eine Begrüßungsnachricht eingeben und dann zwischen Menüoptionen und Verzeichnissuche auswählen. 

### <a name="menu-options"></a>Menüoptionen

![Screenshot der Optionen für die Wähltaoptionen](media/auto-attendant-call-flow-menu-options-complete.png)

Für Wähloptionen können Sie die 0-9-Tasten auf der Wähltasten des Telefons einem der Anrufroutingziele zuweisen. (Die Tasten \* (Wiederholen) und (Zurück) sind vom System reserviert und können nicht erneut \# zugewiesen werden.)

Schlüsselzuordnungen müssen nicht fortlaufend sein. Es ist z. B. möglich, ein Menü zu erstellen, in dem die Tasten 0, 1 und 3 den Optionen zugeordnet sind, während die 2-Taste nicht verwendet wird.

Es wird empfohlen, die Taste 0 dem Operator zuzuordnen, wenn Sie eine konfiguriert haben. Wenn der Operator nicht auf eine Taste festgelegt ist, ist auch der Sprachbefehl "Operator" deaktiviert.

Geben Sie für jede Menüoption Folgendes an:

- **Wähltastatur** – die Taste auf der Wähltastatur des Telefons, um auf diese Option zu zugreifen. Wenn Spracheingaben verfügbar sind, können Anrufer auch diese Nummer sagen, um auf die Option zu zugreifen.

- **Sprachbefehl :** Definiert den Sprachbefehl, den ein Anrufer für den Zugriff auf diese Option ausführen kann, wenn Spracheingaben aktiviert sind. Sie kann mehrere Wörter wie "Kundendienst" oder "Betrieb und Anlage" enthalten. So kann der Anrufer beispielsweise "2" drücken, "zwei" sagen oder "Vertrieb" sagen, um die Option auszuwählen, die der Taste "2" zugeordnet ist. Dieser Text wird auch per Text zu Sprache für die Bestätigungsaufforderung des Diensts gerendert, was beispielsweise so aussehen könnte: "Ihren Anruf an Den Vertrieb durch übertragen".

- **Redirect to** – das Anrufroutingziel, das verwendet wird, wenn Anrufer diese Option auswählen. Wenn Sie an eine automatische Telefon attendant oder Anrufwarteschleife umleiten, wählen Sie das zugeordnete Ressourcenkonto aus.

### <a name="directory-search"></a>Verzeichnissuche

Wenn Sie Bestimmungszielen Wähltasten zuweisen, empfiehlt es sich, **für** die Verzeichnissuche **"Keine" zu wählen.** Wenn ein Anrufer versucht, einen Namen oder eine Durchwahl mit Schlüsseln anwählt, die bestimmten Zielen zugewiesen sind, wird er möglicherweise unerwartet an ein Ziel geroutet, bevor er die Eingabe des Namens oder der Durchwahl abgeschlossen hat. Es wird empfohlen, eine separate automatische Telefon attendant für die Verzeichnissuche zu erstellen und über eine Wähltaste einen Link zu ihrer automatischen Haupttelefonhalterin zu erstellen.

Wenn Sie keine Wähltasten zugewiesen haben, wählen Sie eine Option für die **Verzeichnissuche aus.**

**Namensanwahl** – Wenn Sie diese Option aktivieren, können Anrufer den Namen des Benutzers sagen oder ihn auf der Wähltastatur des Telefons eingeben. Jeder Onlinebenutzer oder jeder Benutzer, der lokal mit Skype for Business Server gehostet wird, ist berechtigter Benutzer und kann mit der Namensanwahl gefunden werden. (Auf der Seite mit dem Wählbereich können Sie festlegen, wer im Verzeichnis enthalten ist [oder nicht.)](#dial-scope)

**Durchwahl :** Wenn Sie diese Option aktivieren, können Anrufer eine Verbindung mit Benutzern in Ihrer Organisation herstellen, indem sie deren Telefonerweiterung wählen. Jeder Onlinebenutzer oder jeder Benutzer, der lokal mit Skype for Business Server gehostet wird, ist berechtigter Benutzer und kann per Durchwahl **gefunden werden.** (Auf der Seite mit dem Wählbereich können Sie festlegen, wer im Verzeichnis enthalten ist [oder nicht.)](#dial-scope)

Benutzer, die sie für die Durchwahlerweiterung zur Verfügung stellen möchten, müssen über eine Durchwahl verfügen, [](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) die als Teil eines der folgenden Telefonattribute angegeben ist, die in Active Directory oder Azure Active Directory definiert sind (weitere Informationen finden Sie unter "Hinzufügen von einzelnen Benutzern oder Massenanrufen".)

- OfficePhone
- HomePhone
- Mobile/MobilePhone
- TelephoneNumber/PhoneNumber
- OtherTelephone

Für die Eingabe der Durchwahl in das Feld für die Telefonnummer des Benutzers ist eine der beiden Formate erforderlich:

- *+\<phone number>;ext=\<extension>*
- *+\<phone number>x\<extension>*
- *x\<extension>*

- Beispiel 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"
- Beispiel 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"
- Beispiel 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"

Sie können die Erweiterung im [Microsoft 365 Admin Center](https://admin.microsoft.com/) oder im Azure Active Directory Admin Center [festlegen.](https://aad.portal.azure.com) Es kann bis zu 12 Stunden dauern, bis Änderungen für automatische Telefonkonferenzen und Anrufwarteschleifen verfügbar sind.

> [!NOTE]
> Wenn Sie sowohl die  Funktion "Nach Name wählen" als auch die Erweiterungsfeatures "Nach Name wählen" verwenden möchten, können Sie in Ihrer automatischen Haupttelefonhalterung eine Wähltaste zuweisen, um eine automatische Telefon attendant zu erreichen, die für die Namensanwahl **aktiviert ist.**  Innerhalb dieser automatischen Telefon attendant können Sie die 1-Taste (der  keine Buchstaben zugeordnet sind) zuweisen, um die automatische Telefon telefonieren mit der Durchwahl zu erreichen.

Nachdem Sie eine Option für die **Verzeichnissuche ausgewählt** haben, klicken Sie auf **"Weiter".**

## <a name="call-flow-for-after-hours"></a>Anruffluss nach Stunden

![Screenshot der Einstellungen für Tag und Uhrzeit nach Stunden](media/auto-attendant-business-hours.png)

Geschäftszeiten können für jede automatische Attendant festgelegt werden. Wenn keine Geschäftszeiten festgelegt sind, werden alle Tage und alle Stunden des Tages als Geschäftszeiten betrachtet, da standardmäßig ein 24/7-Zeitplan festgelegt ist. Geschäftszeiten können mit Tagesferien festgelegt werden, und alle Stunden, die nicht als Geschäftszeiten festgelegt sind, werden als Arbeitsstunden betrachtet. Sie können verschiedene Optionen für die Anrufbehandlung und Begrüßungen für die Nachstunden festlegen.

Je nachdem, wie Sie Ihre automatischen Telefonkonferenzen und Anrufwarteschleifen konfiguriert haben, müssen Sie möglicherweise nur das Anrufrouting nach Stunden für automatische Telefonkonferenzen mit Direkttelefonnummern angeben.

Wenn Sie separate Anrufrouting für Anrufer nach Geschäftszeiten wünschen, geben Sie ihre Geschäftszeiten für jeden Tag an. Klicken **Sie auf "Neue Zeit hinzufügen",** um mehrere Stundensätze für einen bestimmten Tag anzugeben, z. B. eine Mittagspause.

Nachdem Sie Ihre Geschäftszeiten angegeben haben, wählen Sie ihre Anrufroutingoptionen für die folgenden Stunden aus. Die gleichen Optionen stehen wie für die oben angegebene Anrufrouting während der Geschäftszeiten zur Verfügung.

Wenn **Sie fertig** sind, klicken Sie auf "Weiter".

## <a name="call-flows-during-holidays"></a>Anrufflüsse während der Feiertage

![Screenshot der Einstellungen für "Feiertag" und "Feiertagsgruß"](media/auto-attendant-holiday-greeting.png)

Ihre automatische Telefon attendant kann einen Anruffluss für jeden Feiertag haben, [den Sie eingerichtet haben.](set-up-holidays-in-teams.md) Sie können jeder automatische Telefonzentrale bis zu 20 geplante Feiertage hinzufügen.

1. Klicken Sie auf der Seite mit den Einstellungen für den Feiertagsanruf auf **"Hinzufügen".**

2. Geben Sie einen Namen für diese Feiertagseinstellung ein.

3. Wählen Sie **in der** Dropdownliste "Feiertage" den Feiertag aus, den Sie verwenden möchten.

4. Wählen Sie den Typ der zu verwendende Begrüßung aus.

    ![Screenshot der Aktionseinstellungen für einen Feiertagsanruf](media/auto-attendant-holiday-actions.png)

5. Wählen Sie aus, ob Sie den **Anruf** trennen **oder** umleiten möchten.

6. Wenn Sie sich für die Umleitung entscheiden, wählen Sie das Anrufroutingziel für den Anruf aus.

7. Klicken Sie auf **Speichern**.

![Screenshot der Feiertagseinstellungen mit aufgelisteten Feiertagen](media/auto-attendant-holiday-call-settings.png)

Wiederholen Sie den Vorgang bei Bedarf für jeden weiteren Feiertag.

Wenn Sie alle Feiertage hinzugefügt haben, klicken Sie auf **"Weiter".**

## <a name="dial-scope"></a>Wählbereich

![Screenshot der Ein- und Ausschließen-Optionen für den Wählbereich](media/auto-attendant-dial-scope.png)

Der *Wählbereich* definiert, welche Benutzer im Verzeichnis verfügbar sind, wenn ein Anrufer eine Namensanwahl oder eine Durchwahl verwendet. Die Standardeinstellung **"Alle Onlinebenutzer"** umfasst alle Benutzer in Ihrer Organisation, die Onlinebenutzer sind oder lokal mit Skype for Business Server gehostet werden.

Sie können bestimmte Benutzer ein- oder  ausschließen,  indem Sie unter "Ein- oder Ausschließen" die Option "Benutzerdefinierte Benutzergruppe" auswählen und dann eine oder mehrere Microsoft 365-Gruppen, Verteilerlisten oder Sicherheitsgruppen auswählen.  Sie können beispielsweise Leitende Geschäftsleitung in Ihrer Organisation aus dem Wählverzeichnis ausschließen. (Wenn sich ein Benutzer in beiden Listen befindet, wird er aus dem Verzeichnis ausgeschlossen.)

> [!NOTE]
> Es kann bis zu 36 Stunden dauern, bis ein neuer Benutzer seinen Namen im Verzeichnis aufgelistet hat.

Wenn Sie mit dem Festlegen des Wählbereichs fertig sind, klicken Sie auf **"Weiter".**

## <a name="resource-accounts"></a>Ressourcenkonten

Allen automatischen Attendanten muss ein Ressourcenkonto zugeordnet sein.  Automatische Telefonnummern der ersten Ebene benötigen mindestens ein Ressourcenkonto, das über eine zugeordnete Dienstnummer verfügt. Wenn Sie möchten, können Sie einer automatischen Attendant mehrere Ressourcenkonten zuordnen, die jeweils eine separate Dienstnummer haben.

![Screenshot des Ressourcenkontobereichs zum Hinzufügen von Konten](media/auto-attendant-add-resource-account.png)

Um ein Ressourcenkonto hinzuzufügen, klicken **Sie** auf "Konto hinzufügen", und suchen Sie nach dem Konto, das Sie hinzufügen möchten. Klicken Sie **auf**"Hinzufügen" und dann auf **"Hinzufügen".**

![Screenshot der Ressourcenkontoliste mit dem Ressourcenkonto mit zugewiesener Servicenummer](media/auto-attendant-resource-account-assigned.png)

Wenn Sie mit dem Hinzufügen von Dienstkonten fertig sind, klicken Sie auf **"Absenden".** Damit wird die Konfiguration der automatischen Attendant abgeschlossen.

## <a name="external-phone-number-transfers---technical-details"></a>Übertragung von externen Telefonnummern – technische Details

Bitte beachten Sie die [Voraussetzungen,](plan-auto-attendant-call-queue.md#prerequisites) um zu ermöglichen, dass automatische Telefon attendes Anrufe extern übertragen.  Außerdem:

- Für ein Ressourcenkonto [](calling-plans-for-office-365.md) mit einer Anrufplannummer muss die Telefonnummer für externe Übertragungen im E.164-Format eingegeben werden (+[Landescode][Ortswahl][Telefonnummer]).

- Bei einem Ressourcenkonto mit einer Direct-Routing-Nummer ist das Nummernformat für externe Übertragungen von den Einstellungen des Session [Border Controllers (SBC)](direct-routing-connect-the-sbc.md) abhängig.

Die angezeigte ausgehende Telefonnummer wird wie folgt bestimmt:

  - Bei Anrufplannummern wird die ursprüngliche Rufnummer des Anrufers angezeigt.
  - Bei Nummern des direkten Routings basiert die gesendete Zahl wie folgt auf der Einstellung P-Asserted-Identity (WERDEN) auf dem SBC:
    - Wenn dies auf "Deaktiviert" festgelegt ist, wird die Telefonnummer des ursprünglichen Anrufers angezeigt. Dies ist die empfohlene Standardeinstellung.
    - Wenn diese Option auf "Aktiviert" festgelegt ist, wird die Telefonnummer des Ressourcenkontos angezeigt.

Erstellen Sie in einer Skype for Business-Hybridumgebung einen neuen lokalen Benutzer, für den die Anrufumwahl auf die PstN-Nummer festgelegt ist, um einen Anruf einer automatischen Telefonkonferenz in das PSTN zu übertragen. Der Benutzer muss für die Sprachsteuerung Enterprise-VoIP und ihm muss eine Sprachrichtlinie zugewiesen sein. Weitere Informationen finden Sie unter [Anrufübertragung der automatischen Telefonant an das PSTN.](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)

### <a name="create-an-auto-attendant-with-powershell"></a>Erstellen einer automatischen Attendant mit PowerShell

Sie können PowerShell auch zum Erstellen und Einrichten von automatischen Attendanten verwenden. Dies sind die Cmdlets, die Sie zum Verwalten einer automatischen Attendant benötigen:

- [New-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant)  
- [Set-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant)
- [Get-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant)
- [Get-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays)
- [Remove-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant)
- [New-CsAutoAttendantMenu](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu)
- [New-CsOnlineAudioFile](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile)
- [New-CsAutoAttendantCallFlow](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [Export-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [New-CsOnlineTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange)
- [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange)
- [New-CsOnlineSchedule](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule)
- [Get-CsAutoAttendantSupportedTimeZone](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [New-CsAutoAttendantCallHandlingAssociation](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [Get-CsAutoAttendantSupportedLanguage](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [Import-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays)
- [New-CsAutoAttendantCallableEntity](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a>Verwandte Themen

[Das Telefonsystem bietet Ihnen Folgendes](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Abrufen von Diensttelefonnummern](/microsoftteams/getting-service-phone-numbers)

[Verfügbarkeit von Audiokonferenzen und Anrufplänen nach Ländern und Regionen](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[Einführung in Windows PowerShell und Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
