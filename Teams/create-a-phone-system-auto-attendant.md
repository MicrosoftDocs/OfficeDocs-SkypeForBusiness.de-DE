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
description: Erfahren Sie, wie Sie automatische Attendanten für Microsoft Teams einrichten und testen.
ms.openlocfilehash: 8aabdcdd8e5f58604e8b8d09524b6d096f62f7be
ms.sourcegitcommit: d62e6cefceebe481eb207c59872f1aa67f0fc528
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2021
ms.locfileid: "50460885"
---
# <a name="set-up-an-auto-attendant"></a>Einrichten einer automatischen Attendant

Mithilfe von automatischen Telefonkonferenzen können Personen Ihre Organisation anrufen und in einem Menüsystem navigieren, um mit der richtigen Abteilung, Anrufwarteschlange, Person oder einem Operator zu sprechen. Sie können automatische Attendants für Ihre Organisation mit dem Microsoft Teams Admin Center oder mit PowerShell erstellen.

Achten Sie darauf, dass Sie automatische Telefonkonferenzen und [](plan-auto-attendant-call-queue.md#getting-started) Anrufwarteschlangen für Planen für [Teams](plan-auto-attendant-call-queue.md) gelesen haben, und folgen Sie den Schritten für die ersten Schritte, bevor Sie die in diesem Artikel beschriebenen Verfahren ausführen.

Automatische Telefon attendants can direct calls, based on callers' input, to one of the following destinations: <a name="call-routing-options" ></a>

- **Operator** – der für die automatische Attendant definierte Operator. Das Definieren eines Operators ist optional. Der Operator kann als eines der anderen Ziele in dieser Liste definiert werden.
- **Person in der Organisation** – eine Person in Ihrer Organisation, die Sprachanrufe empfangen kann. Dies kann ein Onlinebenutzer oder ein Benutzer sein, der lokal mit Skype for Business Server gehostet wird.
- **Sprach-App** – eine andere automatische Telefonkonferenz oder Anrufwarteschlange. (Wählen Sie das Ressourcenkonto aus, das der automatischen Telefonkonferenz oder Anrufwarteschlange zugeordnet ist, wenn Sie dieses Ziel auswählen.)
- **Voicemail** – das Sprachpostfach, das einer von Ihnen angegebenen Microsoft 365-Gruppe zugeordnet ist.
- **Externe Telefonnummer –** beliebige Telefonnummer. (Siehe [technische Details zur externen Übertragung](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).
- **Ankündigung** – Wiedergabe einer Audiodatei. Eine aufgezeichnete Ankündigungsnachricht, die Sie hochladen und die als Audio in gespeichert wird. WAV, . MP3 oder . WMA-Format. Die Aufzeichnung darf nicht größer als 5 MB sein. Das System gibt die Ankündigung wieder und kehrt dann zum Menü der automatischen Attendant zurück.
- **Ankündigung** – Geben Sie eine Nachricht ein. Text, den das System lesen soll. Sie können bis zu 1.000 Zeichen eingeben. Das System gibt die Ankündigung wieder und kehrt dann zum Menü der automatischen Attendant zurück.

Beim Einrichten einer automatischen Attendant werden Sie aufgefordert, eine dieser Optionen in verschiedenen Phasen zu wählen.

Zum Einrichten einer automatischen Telefonzentrale erweitern Sie im Teams Admin Center **Voice,** wählen **Sie Automatische Telefonzentralen** und dann **Hinzufügen aus.**

## <a name="general-info"></a>Allgemeine Informationen

![Screenshot der Einstellungen der automatischen Telefonwarte für Name, Operator, Zeitzone, Sprache und Spracheingaben](media/auto-attendant-general-info-page-new.png)

1. Geben Sie oben im Feld einen Namen für die automatische Attendant ein.

2. Wenn Sie einen Operator festlegen möchten, geben Sie das Ziel für Anrufe an den Operator an. Dies ist optional (aber empfohlen). Sie können die Option **Operator** so festlegen, dass Anrufer aus den Menüs ausbrechen und mit einer bestimmten Person sprechen können.

3. Geben Sie die Zeitzone für diese automatische Attendant an. Die Zeitzone wird zum Berechnen von Geschäftszeiten verwendet, wenn Sie einen separaten Anruffluss für [nach Stunden erstellen.](#call-flow-for-after-hours)

4. Geben Sie [eine unterstützte Sprache](create-a-phone-system-auto-attendant-languages.md) für diese automatische Attendant an. Dies ist die Sprache, die für systemgenerierte Sprachanforderungen verwendet wird.

5. Wählen Sie aus, ob Sie Spracheingaben aktivieren möchten. Wenn diese Option aktiviert ist, wird der Name jeder Menüoption zu einem Schlüsselwort für die Spracherkennung. Anrufer können z. B. "One" sagen, um die Menüoption auszuwählen, die Der Taste 1 zugeordnet ist, oder sie können "Umsatz" sagen, um die Menüoption mit dem Namen "Vertrieb" auszuwählen.

> [!NOTE]
> Wenn Sie in Schritt 4 eine Sprache auswählen, die Spracheingaben nicht unterstützt, wird diese Option deaktiviert.

6. Wählen Sie **Weiter aus.**

## <a name="call-flow"></a>Anruffluss

![Screenshot der Einstellungen für Grußnachrichten](media/auto-attendant-call-flow-greeting-message.png)

Wählen Sie aus, ob sie eine Begrüßung wieder geben möchten, wenn die automatische Telefonkonferenz einen Anruf beantwortet.

Wenn Sie **Audiodateien wiederverspielen auswählen,** können Sie die Schaltfläche **Datei** hochladen verwenden, um eine aufgezeichnete Begrüßungsnachricht hochzuladen, die als Audio in gespeichert ist. WAV, . MP3 oder . WMA-Format. Die Aufzeichnung darf nicht größer als 5 MB sein.

Wenn Sie Grußnachricht **eingeben** auswählen, liest das System den Text vor, den Sie eingeben (bis zu 1.000 Zeichen), wenn die automatische Telefonkonferenz einen Anruf entgegen nimmt.

![Screenshot der Anrufroutingeinstellungen](media/auto-attendant-call-flow-route-call-message.png)

Wählen Sie aus, wie sie den Anruf weiterrouten möchten.

Wenn Sie Trennen **auswählen,** hängt die automatische Telefonkonferenz den Anruf auf.

Wenn Sie Anruf **umleiten auswählen,** können Sie eines der Anrufroutingziele auswählen.

Wenn Sie Menüoptionen für "Wiedergabe" **auswählen,** können Sie eine Audiodatei wiedererwählen oder **eine** Grußnachricht eingeben und dann zwischen Menüoptionen und Verzeichnissuche auswählen. 

### <a name="menu-options"></a>Menüoptionen

![Screenshot der Wähltastenoptionen](media/auto-attendant-call-flow-menu-options-complete.png)

Bei Wähloptionen können Sie einem der Anrufrouteziele die 0 bis 9 Tasten auf der Telefontaste zuweisen. (Die Tasten \* (Wiederholen) und (Zurück) werden vom System reserviert und können nicht \# erneut zugewiesen werden.)

Schlüsselzuordnungen müssen nicht fortlaufend sein. Es ist z. B. möglich, ein Menü mit den Tasten 0, 1 und 3 zu erstellen, während die beiden Tasten nicht verwendet werden.

Es wird empfohlen, die Nulltaste dem Operator zuzuordnen, wenn Sie eine konfiguriert haben. Wenn der Operator nicht auf eine Taste festgelegt ist, ist auch der Sprachbefehl "Operator" deaktiviert.

Geben Sie für jede Menüoption die folgenden Einstellungen an:

- **WÄHLTA0** – die Taste auf der Telefontaste, um auf diese Option zu zugreifen. Wenn Spracheingaben verfügbar sind, können Anrufer diese Nummer auch sagen, um auf die Option zu zugreifen.

- **Sprachbefehl** : Definiert den Sprachbefehl, den ein Anrufer für den Zugriff auf diese Option geben kann, wenn Spracheingaben aktiviert sind. Sie kann mehrere Wörter wie "Kundendienst" oder "Vorgänge und Gründe" enthalten. Beispielsweise kann der Anrufer 2 drücken, "zwei" sagen oder "Umsatz" sagen, um die Option auszuwählen, die der beiden Taste zugeordnet ist. Dieser Text wird auch per Text in Sprache für die Bestätigungsaufforderung des Diensts gerendert, was etwa "Übertragen Ihres Anrufs in den Vertrieb" sein kann.

- **Umleiten zu** – das Anrufroutingziel, das verwendet wird, wenn Anrufer diese Option auswählen. Wenn Sie an eine automatische Telefonleitung oder Anrufwarteschlange umleiten, wählen Sie das zugeordnete Ressourcenkonto aus.

### <a name="directory-search"></a>Verzeichnissuche

Wenn Sie Zielzielen Wähltasten zuweisen, empfiehlt es sich, Für Verzeichnissuche **keine** **zu wählen.** Wenn ein Anrufer versucht, einen Namen oder eine Erweiterung mithilfe von Schlüsseln zu wählen, die bestimmten Zielen zugewiesen sind, wird er möglicherweise unerwartet an ein Ziel geroutet, bevor er die Eingabe des Namens oder der Erweiterung abgeschlossen hat. Es wird empfohlen, eine separate automatische Telefonwarte für die Verzeichnissuche zu erstellen und über eine Wähltaste einen Link zur automatischen Haupttelefonwarte zu erstellen.

Wenn Sie keine Wähltasten zugewiesen haben, wählen Sie eine Option für die **Verzeichnissuche aus.**

**Nach Namen wählen** – Wenn Sie diese Option aktivieren, können Anrufer den Namen des Benutzers sagen oder ihn auf der Telefontaste eingeben. Jeder Onlinebenutzer oder jeder Benutzer, der lokal mit Skype for Business Server gehostet wird, ist ein berechtigter Benutzer und kann mit Dial by name gefunden werden. (Sie können festlegen, wer im Verzeichnis auf der Seite Wählbereich enthalten ist [und nicht.)](#dial-scope)

**Durchwahl:** Wenn Sie diese Option aktivieren, können Anrufer eine Verbindung mit Benutzern in Ihrer Organisation herstellen, indem sie die Telefonerweiterung wählen. Jeder Onlinebenutzer oder jeder Benutzer, der lokal mit Skype for Business Server gehostet wird, ist ein berechtigter Benutzer und kann über die Erweiterung **Dial by gefunden werden.** (Sie können festlegen, wer im Verzeichnis auf der Seite Wählbereich enthalten ist [und nicht.)](#dial-scope)

Für Benutzer, die Sie für die Durchwahl verfügbar machen möchten, muss eine Erweiterung als Teil eines [](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) der folgenden Telefonattribute angegeben sein, die in Active Directory oder Azure Active Directory definiert sind (weitere Informationen finden Sie unter Hinzufügen von Benutzern einzeln oder in Massen).)

- OfficePhone
- HomePhone
- Mobile/MobilePhone
- TelephoneNumber/PhoneNumber
- OtherTelephone

Das erforderliche Format für die Eingabe der Erweiterung in das Feld "Benutzertelefonnummer" ist entweder:

- *+\<phone number>;ext=\<extension>*
- *+\<phone number>x\<extension>*
- *x\<extension>*

- Beispiel 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+1555555678;ext=5678"
- Beispiel 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"
- Beispiel 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"

Sie können die Erweiterung im [Microsoft 365 Admin Center](https://admin.microsoft.com/) oder im Azure Active Directory Admin Center [festlegen.](https://aad.portal.azure.com) Es kann bis zu 12 Stunden dauern, bis Änderungen für automatische Telefonanten und Anrufwarteschlangen verfügbar sind.

> [!NOTE]
> Wenn Sie sowohl die  Features "Nach Name wählen" als auch "Nach Name wählen" verwenden möchten, können Sie ihrer automatischen Haupttelefonwarte eine Wähltaste zuweisen, um zu einer automatischen Telefonwarte zu gelangen, die für "Nach Name" aktiviert **ist.**  Innerhalb dieser automatischen Telefon attendant können Sie die 1-Taste (die keine Buchstaben zugeordnet ist) zuweisen, um die automatische Telefonwarte "DurchWahl **nach"** zu erreichen.

Nachdem Sie eine Option für die **Verzeichnissuche ausgewählt haben,** wählen Sie **Weiter aus.**

## <a name="call-flow-for-after-hours"></a>Anruffluss nach Stunden

![Screenshot der Tages- und Uhrzeiteinstellungen nach Stunden](media/auto-attendant-business-hours.png)

Geschäftszeiten können für jede automatische Attendant festgelegt werden. Wenn keine Geschäftszeiten festgelegt sind, gelten alle Tage und alle Stunden des Tages als Geschäftszeiten, da standardmäßig ein 24/7-Zeitplan festgelegt ist. Geschäftszeiten können mit Zeitumbrüchen während des Tages festgelegt werden, und alle Stunden, die nicht als Geschäftszeiten festgelegt sind, werden als Nachstunden betrachtet. Sie können unterschiedliche Optionen für die Anrufbehandlung und Begrüßungen für die Nachstunden festlegen.

Je nachdem, wie Sie Ihre automatischen Telefonwarteschlangen und Anrufwarteschlangen konfiguriert haben, müssen Sie möglicherweise nur das Anrufrouting nach stundenlangen Zeiten für automatische Telefonanten mit direkten Telefonnummern angeben.

Wenn Sie ein separates Anrufrouting für Anrufer nach stundenlangen Gesprächen wünschen, geben Sie Ihre Geschäftszeiten für jeden Tag an. Wählen **Sie Neue Uhrzeit hinzufügen aus,** um mehrere Stundensätze für einen bestimmten Tag anzugeben, z. B. um eine Mittagspause anzugeben.

Nachdem Sie Ihre Geschäftszeiten angegeben haben, wählen Sie ihre Anrufroutingoptionen für nach stundenlang aus. Die gleichen Optionen sind wie für das oben angegebene Anrufrouting während der Geschäftszeiten verfügbar.

Wählen **Sie Weiter** aus, wenn Sie fertig sind.

## <a name="call-flows-during-holidays"></a>Anrufflüsse während der Feiertage

![Screenshot der Feiertags- und Feiertagsgrußeinstellungen](media/auto-attendant-holiday-greeting.png)

Ihre automatische Telefonkonferenz kann für jeden Feiertag, den Sie eingerichtet haben, [einen Anruffluss haben.](set-up-holidays-in-teams.md) Sie können jeder automatische Telefonzentrale bis zu 20 geplante Feiertage hinzufügen.

1. Wählen Sie auf der Seite Feiertagsanrufeinstellungen die Option **Hinzufügen aus.**

2. Geben Sie einen Namen für diese Feiertagseinstellung ein.

3. Wählen Sie **in der** Dropdownliste Feiertag den Feiertag aus, den Sie verwenden möchten.

4. Wählen Sie den Typ der Begrüßung aus, den Sie verwenden möchten.

    ![Screenshot der Aktionseinstellungen für Feiertagsanrufe](media/auto-attendant-holiday-actions.png)

5. Wählen Sie aus, ob **Sie** den Anruf trennen **oder umleiten** möchten.

6. Wenn Sie sich für die Umleitung entschieden haben, wählen Sie das Anrufroutingziel für den Anruf aus.

7. Klicken Sie auf **Speichern**.

![Screenshot der Feiertagseinstellungen mit aufgelisteten Feiertagen](media/auto-attendant-holiday-call-settings.png)

Wiederholen Sie den Vorgang bei Bedarf für jeden weiteren Feiertag.

Wenn Sie alle Ihre Feiertage hinzugefügt haben, wählen Sie **Weiter aus.**

## <a name="dial-scope"></a>Wählbereich

![Screenshot des Wählbereichs : Optionen zum Ein- und Ausschließen](media/auto-attendant-dial-scope.png)

Der *Wählbereich* definiert, welche Benutzer im Verzeichnis verfügbar sind, wenn ein Anrufer eine Nach-Name-Wähl- oder Durchwahl verwendet. Die Standardeinstellung **Aller Onlinebenutzer umfasst** alle Benutzer in Ihrer Organisation, die Onlinebenutzer sind oder lokal mit Skype for Business Server gehostet werden.

Sie können bestimmte Benutzer ein- oder  ausschließen,  indem Sie unter Ein- oder Ausschließen benutzerdefinierte Benutzergruppe auswählen und eine oder mehrere Microsoft 365-Gruppen, Verteilerlisten oder Sicherheitsgruppen auswählen.  So können Sie beispielsweise Führungskräfte in Ihrer Organisation aus dem Wählverzeichnis ausschließen. (Wenn sich ein Benutzer in beiden Listen befindet, wird er aus dem Verzeichnis ausgeschlossen.)

> [!NOTE]
> Es kann bis zu 36 Stunden dauern, bis ein neuer Benutzer seinen Namen im Verzeichnis aufgelistet hat.

Wenn Sie mit dem Festlegen des Wählbereichs fertig sind, wählen Sie **Weiter aus.**

## <a name="resource-accounts"></a>Ressourcenkonten

Alle automatischen Attendanten müssen über ein zugeordnetes Ressourcenkonto verfügen.  Automatische Teilnehmer der ersten Ebene benötigen mindestens ein Ressourcenkonto mit einer zugeordneten Dienstnummer. Wenn Sie möchten, können Sie einer automatischen Attendant mehrere Ressourcenkonten zuweisen, die jeweils eine separate Dienstnummer haben.

![Screenshot des Ressourcenkonto-Add-Accounts-Panels](media/auto-attendant-add-resource-account.png)

Wenn Sie ein Ressourcenkonto hinzufügen möchten, wählen Sie **Konto hinzufügen aus,** und suchen Sie nach dem Konto, das Sie hinzufügen möchten. Wählen **Sie Hinzufügen** und dann Hinzufügen **aus.**

![Screenshot der Ressourcenkontoliste mit Ressourcenkonto mit zugewiesener Dienstnummer](media/auto-attendant-resource-account-assigned.png)

Wenn Sie das Hinzufügen von Dienstkonten abgeschlossen haben, wählen Sie **Absenden aus,** um die Konfiguration der automatischen Attendant-Funktion zu abschließen.

## <a name="external-phone-number-transfers---technical-details"></a>Übertragung externer Telefonnummern – technische Details

Lesen Sie die [Voraussetzungen,](plan-auto-attendant-call-queue.md#prerequisites) damit automatische Telefonanten Anrufe extern übertragen können.  Außerdem:

- Bei einem Ressourcenkonto [](calling-plans-for-office-365.md)mit einer Anrufplanlizenz muss die Telefonnummer für externe Überweisungen im E.164-Format (+[Ländercode][Vorwahl][Telefonnummer]) eingegeben werden.

- Bei einem Ressourcenkonto mit einer Telefonsystemlizenz und einer Direct Routing Online Voice Routing-Richtlinie ist das Telefonnummernformat für externe Übertragungen von den Einstellungen des [Session Border Controllers (SBC)](direct-routing-connect-the-sbc.md) abhängig.

Die angezeigte ausgehende Telefonnummer wird wie folgt bestimmt:

  - Bei Anrufplannummern wird die Telefonnummer des ursprünglichen Anrufers angezeigt.
  - Bei Direct Routing-Nummern basiert die gesendete Nummer wie folgt auf der Einstellung P-Asserted-Identity (PA) auf dem SBC:
    - Wenn sie auf Deaktiviert festgelegt ist, wird die Telefonnummer des ursprünglichen Anrufers angezeigt. Dies ist die Standardeinstellung und empfohlene Einstellung.
    - Wenn auf Aktiviert festgelegt ist, wird die Telefonnummer des Ressourcenkontos angezeigt.

Um in einer Skype for Business-Hybridumgebung einen automatischen Telefonanruf in das PSTN zu übertragen, erstellen Sie einen neuen lokalen Benutzer mit anrufverteilter Weiterleitung, die auf die PSTN-Nummer festgelegt ist. Der Benutzer muss für die Enterprise-VoIP aktiviert sein und eine Sprachrichtlinie zugewiesen haben. Weitere Informationen finden Sie unter [Automatische Telefonanrufübertragung in PSTN.](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn)

### <a name="create-an-auto-attendant-with-powershell"></a>Erstellen einer automatischen Attendant mit PowerShell

Sie können PowerShell auch zum Erstellen und Einrichten automatischer Attendanten verwenden. Hier sind die Cmdlets, die Sie zum Verwalten einer automatischen Attendant benötigen:

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

[Vorteile des Telefonsystems](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Servicetelefonnummern erhalten](/microsoftteams/getting-service-phone-numbers)

[Verfügbarkeit von Audiokonferenzen und Anrufplänen nach Ländern und Regionen](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[Einführung in Windows PowerShell und Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
