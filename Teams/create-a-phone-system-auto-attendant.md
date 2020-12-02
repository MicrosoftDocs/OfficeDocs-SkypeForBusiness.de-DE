---
title: Einrichten einer automatischen Telefonzentrale für Microsoft Teams
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
description: Hier erfahren Sie, wie Sie automatische Telefonzentralen für Microsoft Teams einrichten und testen.
ms.openlocfilehash: 203a05e19ffce4154c123cbb700ca59e0b75a63a
ms.sourcegitcommit: 660d0d65892408d0bb4ac1a870c88b11a7c6841e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "49530518"
---
# <a name="set-up-an-auto-attendant"></a>Einrichten einer automatischen Telefonzentrale

Mit automatischen Telefonzentralen können Personen Ihre Organisation anrufen und in einem Menü System navigieren, um mit der richtigen Abteilung, Anrufwarteschlange, Person oder einem Operator zu sprechen. Sie können automatische Telefonzentralen für Ihre Organisation mit dem Microsoft Teams Admin Center oder mit PowerShell erstellen.

Stellen Sie sicher, dass Sie den [Plan für automatische Team-Telefonzentralen und-Warteschlangen](plan-auto-attendant-call-queue.md) gelesen haben, und folgen Sie den [Schritten unter erste](plan-auto-attendant-call-queue.md#getting-started) Schritte, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen.

Automatische Telefonzentralen können Anrufe, basierend auf der Eingabe von Anrufern, an eines der folgenden Ziele weiterleiten: <a name="call-routing-options" ></a>

- **Person in der Organisation** – eine Person in Ihrer Organisation, die Sprachanrufe empfangen kann. Hierbei kann es sich um einen Online Benutzer oder einen lokal gehosteten Benutzer mit Skype for Business Server handeln.
- **Sprach-App** – eine andere automatische Telefonzentrale oder eine Anrufwarteschlange. (Wählen Sie das Ressourcenkonto aus, das der automatischen Telefonzentrale oder der Anrufwarteschlange zugeordnet ist, wenn Sie dieses Ziel auswählen.)
- **Externe Telefonnummer** – eine beliebige Telefonnummer. (Siehe [technische Informationen zur externen Übertragung](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)).
- **Voicemail** – das Voicemail-Postfach, das einer von Ihnen angegebenen Microsoft 365-Gruppe zugeordnet ist.
- **Operator** – der für die automatische Telefonzentrale definierte Operator. Das Definieren eines Operators ist optional. Der Operator kann als eines der anderen Ziele in dieser Liste definiert werden.

Sie werden aufgefordert, eine dieser Optionen in verschiedenen Phasen zu wählen, während Sie eine automatische Telefonzentrale einrichten.

Zum Einrichten einer automatischen Telefonzentrale erweitern Sie im Team Admin Center die **Sprache**, klicken Sie auf **automatische Telefonzentralen**, und klicken Sie dann auf **Hinzufügen**.

## <a name="general-info"></a>Allgemeine Informationen

![Screenshot der Einstellungen für die automatische Telefonzentrale für Name, Operator, Zeitzone, Sprache und Spracheingaben](media/auto-attendant-general-info-page-new.png)

1. Geben Sie einen Namen für die automatische Telefonzentrale in das Feld oben ein.

2. Wenn Sie einen Operator festlegen möchten, geben Sie das Ziel für Anrufe an den Operator an. Dies ist optional (wird aber empfohlen). Sie können die Option " **Operator** " so einstellen, dass Anrufer die Menüs ausbrechen und mit einer bestimmten Person sprechen können.

3. Geben Sie die Zeitzone für diese automatische Telefonzentrale an. Die Zeitzone wird zum Berechnen von Geschäftszeiten verwendet, wenn Sie [einen separaten Anruffluss für After Hours erstellen](#call-flow-for-after-hours).

4. Geben Sie eine Sprache für diese automatische Telefonzentrale an. Hierbei handelt es sich um die Sprache, die für vom System generierte Sprachansagen verwendet wird.

5. Wählen Sie aus, ob die Spracheingabe aktiviert werden soll. Wenn diese Option aktiviert ist, wird der Name jeder Menüoption zu einem Schlüsselwort für die Spracherkennung. Anrufer können beispielsweise "eins" sagen, um die Menüoption auszuwählen, die Key 1 zugeordnet ist, oder Sie können "Sales" sagen, um die Menüoption "Sales" zu wählen.

6. Klicken Sie auf **Weiter**.

## <a name="call-flow"></a>Anruffluss

![Screenshot der Einstellungen für Grußnachrichten](media/auto-attendant-call-flow-greeting-message.png)

Wählen Sie aus, ob Sie eine Ansage wiedergeben möchten, wenn die automatische Telefonzentrale einen Anruf annimmt.

Wenn Sie **eine Audiodatei wiedergeben** auswählen, können Sie die Schaltfläche **Datei hochladen** verwenden, um eine aufgezeichnete Grußnachricht hochzuladen, die als Audio gespeichert wurde. WAV,. MP3 oder. WMA-Format. Die Aufzeichnung darf nicht größer als 5 MB sein.

Wenn Sie **eine Begrüßungsnachricht eingeben** auswählen, liest das System den Text, den Sie eingeben (bis zu 1000 Zeichen), wenn die automatische Telefonzentrale einen Anruf annimmt.

![Screenshot der Anrufweiterleitungseinstellungen](media/auto-attendant-call-flow-route-call-message.png)

Wählen Sie aus, wie Sie den Anruf weiterleiten möchten.

Wenn Sie **trennen** auswählen, wird der Anruf von der automatischen Telefonzentrale aufgegeben.

Wenn Sie **Anruf umleiten** wählen, können Sie eines der Anruf Weiterleitungs Ziele auswählen.

Wenn Sie **Menü Optionen wiedergeben** auswählen, können Sie eine **Audiodatei abspielen** oder **eine Begrüßungsnachricht eingeben** und dann zwischen den Menü Optionen und der Verzeichnissuche wählen.

### <a name="menu-options"></a>Menü Optionen

![Screenshot der Optionen für Wähltasten](media/auto-attendant-call-flow-menu-options-complete.png)

Für Wähloptionen können Sie die 0-9-Schlüssel auf der Telefontastatur einem der Anruf Weiterleitungs Ziele zuweisen. (Die Tasten \* (Wiederholen) und \# (zurück) werden vom System reserviert und können nicht neu zugewiesen werden.)

Tastenzuordnungen müssen nicht kontinuierlich sein. So können Sie beispielsweise ein Menü mit den Tasten 0, 1 und 3 erstellen, die den Optionen zugeordnet sind, während die Taste 2 nicht verwendet wird.

Wir empfehlen, die 0-Taste dem Operator zuzuordnen, wenn Sie einen konfiguriert haben. Wenn der Operator nicht auf eine beliebige Taste eingestellt ist, ist der Sprachbefehl "Operator" ebenfalls deaktiviert.

Geben Sie für jede Menüoption Folgendes an:

- **Wähl Taste** – die Taste auf der Telefontastatur, um auf diese Option zuzugreifen. Wenn Spracheingaben verfügbar sind, können Anrufer diese Nummer auch sagen, um auf die Option zuzugreifen.

- **Sprachbefehl** – definiert den Sprachbefehl, den ein Anrufer für den Zugriff auf diese Option geben kann, wenn Spracheingaben aktiviert sind. Sie kann mehrere Wörter wie "Kundendienst" oder "Vorgänge und Gründe" enthalten. Der Anrufer kann beispielsweise 2 drücken, "zwei" sagen oder "Umsatz" sagen, um die Option auszuwählen, die der Taste 2 zugeordnet ist. Dieser Text wird auch von Text zu Sprache für die Bestätigungsaufforderung des Diensts gerendert, die möglicherweise so etwas wie "übertragen Ihres Anrufs an Verkäufe" sein könnte.

- **Umleitung zu** – das Anrufrouting Ziel, das verwendet wird, wenn Anrufer diese Option auswählen. Wenn Sie eine Umleitung an eine automatische Telefonzentrale oder eine Anrufwarteschlange durchführen, wählen Sie das zugehörige Ressourcenkonto aus.

### <a name="directory-search"></a>Verzeichnissuche

Wenn Sie Wähltasten zu Zielen zuweisen, empfehlen wir, dass Sie **keine** für die **Verzeichnissuche** auswählen. Wenn ein Anrufer versucht, mithilfe von Schlüsseln, die bestimmten Zielen zugewiesen sind, einen Namen oder eine Durchwahlnummer zu wählen, werden Sie möglicherweise unerwartet an ein Ziel weitergeleitet, bevor Sie den Namen oder die Erweiterung eingeben. Wir empfehlen, dass Sie eine separate automatische Telefonzentrale für die Verzeichnissuche erstellen und Ihre primäre automatische Telefonzentrale über eine Wähl Taste darauf verweisen.

Wenn Sie keine Wähltasten zugewiesen haben, wählen Sie eine Option für die **Verzeichnissuche** aus.

**Nach Namen wählen** : Wenn Sie diese Option aktivieren, können Anrufer den Namen des Benutzers sagen oder ihn auf der Telefontastatur eingeben. Jeder Online-Nutzer mit einer Telefon System-Lizenz oder einem lokal gehosteten Benutzer mit Skype for Business Server ist ein berechtigter Nutzer und kann mit dem Dial by-Namen gefunden werden. (Sie können auf der Seite [Wählbereich](#dial-scope) einstellen, wer im Verzeichnis enthalten ist und was nicht.)

**Durchwahl: Wenn** Sie diese Option aktivieren, können Anrufer mit den Benutzern in Ihrer Organisation eine Verbindung herstellen, indem Sie die Durchwahl Ihres Telefons wählen. Jeder Online-Nutzer mit einer Telefon System-Lizenz oder einem lokal gehosteten Benutzer mit Skype for Business Server ist ein berechtigter Nutzer und kann mit **Dial by Extension** gefunden werden. (Sie können auf der Seite [Wählbereich](#dial-scope) einstellen, wer im Verzeichnis enthalten ist und was nicht.)

Benutzer, die Sie für Dial by Extension zur Verfügung stellen möchten, müssen über eine Erweiterung verfügen, die als Teil eines der folgenden in Active Directory oder Azure Active Directory definierten Telefon Attribute angegeben ist (Weitere Informationen finden Sie unter [einzeln oder in Massen Hinzufügen von Benutzern](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) .)

- OfficePhone
- HomePhone
- Mobil-Handy
- TelephoneNumber/Telefonnummer
- OtherTelephone

Das erforderliche Format, um die Erweiterung in das Feld Benutzer Telefonnummer einzugeben, ist entweder *+ \<phone number> ; Ext \<extension> =* oder *+ \<phone number> ; \<extension> x*.
Beispiel: Set-MsolUser-userPrincipalName Usern@Domain.com-Telefonnummer "+ 15555555678; ext = 5678".

Sie können die Erweiterung im [Microsoft 365 Admin Center](https://admin.microsoft.com/) oder im [Azure Active Directory Admin Center](https://aad.portal.azure.com)einrichten. Es kann bis zu 12 Stunden dauern, bis Änderungen für automatische Telefonzentralen und Anrufwarteschlangen verfügbar sind.

> [!NOTE]
> Wenn Sie sowohl die Funktionen " **Dial by Name** " als auch "Dial **by Extension** " verwenden möchten, können Sie eine Wähltaste für Ihre primäre automatische Telefonzentrale zuweisen, um eine automatische Telefonzentrale zu erreichen, die für **Dial by Name** aktiviert ist. Innerhalb dieser automatischen Telefonzentrale können Sie die 1-Taste (der keine Buchstaben zugeordnet sind) zuweisen, um **die automatische Telefon** Zentrale für die Durchwahl zu erreichen.

Nachdem Sie eine **Verzeichnis Such** Option ausgewählt haben, klicken Sie auf **weiter**.

## <a name="call-flow-for-after-hours"></a>Anruffluss für After Hours

![Screenshot der Tages-und Uhrzeiteinstellungen für After Hours](media/auto-attendant-business-hours.png)

Die Geschäftszeiten können für jede automatische Telefonzentrale eingestellt werden. Wenn die Geschäftszeiten nicht gesetzt sind, gelten alle Tage und alle Stunden des Tages als Geschäftszeiten, da ein 24/7-Terminplan standardmäßig eingestellt ist. Geschäftszeiten können mit Zeit Unterbrechungen während des Tages festgesetzt werden, und alle Stunden, die nicht als Geschäftszeiten festgesetzt sind, gelten als After-Hours-Zeiten. Sie können unterschiedliche Optionen für eingehende Anrufe und Grußformeln für After-Hours-Einstellungen einstellen.

Je nachdem, wie Sie Ihre automatischen Telefonzentralen und Anrufwarteschlangen konfiguriert haben, müssen Sie möglicherweise nur nach Stunden-Anrufweiterleitung für automatische Telefonzentralen mit direkten Telefonnummern angeben.

Wenn Sie für Anrufer nach Stunden ein separates Anrufrouting wünschen, geben Sie Ihre Geschäftszeiten für jeden Tag an. Klicken Sie auf **neue Zeit hinzufügen** , um mehrere Stundensätze für einen bestimmten Tag anzugeben, beispielsweise um eine Mittagspause anzugeben.

Nachdem Sie Ihre Geschäftszeiten angegeben haben, wählen Sie Ihre Anrufweiterleitungsoptionen für After Hours aus. Die gleichen Optionen stehen zur Verfügung wie für das oben angegebene Geschäftszeiten-Anrufrouting.

Klicken Sie auf **weiter** , wenn Sie fertig sind.

## <a name="call-flows-during-holidays"></a>Anruf Ströme während der Feiertage

![Screenshot der Einstellungen für Feiertags-und Feiertags Begrüßung](media/auto-attendant-holiday-greeting.png)

Ihre automatische Telefonzentrale kann einen Anruffluss für jeden Feiertag haben, den [Sie eingerichtet](set-up-holidays-in-teams.md)haben. Sie können jeder automatische Telefonzentrale bis zu 20 geplante Feiertage hinzufügen.

1. Klicken Sie auf der Seite Feiertags Anrufeinstellungen auf **Hinzufügen**.

2. Geben Sie einen Namen für diese Feiertagseinstellung ein.

3. Wählen Sie in der Dropdownliste **Feiertag** den Feiertag aus, den Sie verwenden möchten.

4. Wählen Sie die Art der Begrüßung aus, die Sie verwenden möchten.

    ![Screenshot der Aktionseinstellungen für Feiertags Anrufe](media/auto-attendant-holiday-actions.png)

5. Wählen Sie aus, ob Sie den Anruf **trennen** oder **umleiten** möchten.

6. Wenn Sie die Umleitung gewählt haben, wählen Sie das Anrufrouting Ziel für den Anruf aus.

7. Klicken Sie auf **Speichern**.

![Screenshot der Feiertags Einstellungen mit aufgelisteten Feiertagen](media/auto-attendant-holiday-call-settings.png)

Wiederholen Sie den Vorgang nach Bedarf für jeden weiteren Feiertag.

Wenn Sie alle Ihre Feiertage hinzugefügt haben, klicken Sie auf **weiter**.

## <a name="dial-scope"></a>Wählbereich

![Screenshot der Optionen "Wählbereich einbeziehen und ausschließen"](media/auto-attendant-dial-scope.png)

Der *Wählbereich* definiert, welche Benutzer im Verzeichnis verfügbar sind, wenn ein Anrufer Dial-by-Name oder Dial-by-Extension verwendet. Der Standardwert **aller Online Benutzer** umfasst alle Benutzer in Ihrer Organisation, die Online Benutzer mit einer Telefon System Lizenz sind oder lokal mit Skype for Business Server gehostet werden.

Sie können bestimmte Benutzer einbeziehen oder ausschließen, indem Sie unter **einbeziehen** oder **ausschließen** eine **benutzerdefinierte Benutzergruppe** auswählen und eine oder mehrere Microsoft 365-Gruppen,-Verteilerlisten oder-Sicherheitsgruppen auswählen. So können Sie beispielsweise Führungskräfte in Ihrer Organisation aus dem Wähl Verzeichnis ausschließen. (Wenn sich ein Benutzer in beiden Listen befindet, wird er aus dem Verzeichnis ausgeschlossen.)

> [!NOTE]
> Es kann bis zu 36 Stunden dauern, bis der Name des neuen Benutzers im Verzeichnis aufgeführt ist.

Wenn Sie mit dem Festlegen des Wähl Bereichs fertig sind, klicken Sie auf **weiter**.

## <a name="resource-accounts"></a>Ressourcenkonten

Alle automatischen Telefonzentralen müssen über ein zugeordnetes Ressourcenkonto verfügen.  Die automatische Telefonzentrale der ersten Ebene benötigt mindestens ein Ressourcenkonto, das über eine zugeordnete Dienstnummer verfügt. Wenn Sie möchten, können Sie einer automatischen Telefonzentrale mit jeweils einer separaten Servicenummer mehrere Ressourcenkonten zuweisen.

![Screenshot des Panels "Konto hinzufügen" des Ressourcenkontos](media/auto-attendant-add-resource-account.png)

Wenn Sie ein Ressourcenkonto hinzufügen möchten, klicken Sie auf **Konto hinzufügen** , und suchen Sie nach dem Konto, das Sie hinzufügen möchten. Klicken Sie auf **Hinzufügen**, und klicken Sie dann auf **Hinzufügen**.

![Screenshot der Ressourcenkonto Liste mit dem Ressourcenkonto mit zugewiesener Dienstnummer](media/auto-attendant-resource-account-assigned.png)

Wenn Sie alle Dienstkonten hinzugefügt haben, klicken Sie auf **Absenden**. Damit ist die Konfiguration der automatischen Telefonzentrale abgeschlossen.

## <a name="external-phone-number-transfers---technical-details"></a>Externe Rufnummern Übertragungen – technische Details

Beziehen Sie sich bitte auf die [Voraussetzungen](plan-auto-attendant-call-queue.md#prerequisites) , damit automatische Telefonzentralen Anrufe extern übertragen können.  Außerdem:

- Bei einem Ressourcenkonto mit einer [Anruf Plan](calling-plans-for-office-365.md) Nummer muss die externe Telefonnummer im E. 164-Format (+ [Landesvorwahl] [Ortsvorwahl] [Telefonnummer]) eingegeben werden.

- Bei einem Ressourcenkonto mit einer direkten Routing Nummer ist das Format für die externe Übertragung von Telefonnummern abhängig von den Einstellungen für den [Session Border Controller (SBC)](direct-routing-connect-the-sbc.md) .

Die angezeigte ausgehende Telefonnummer wird wie folgt bestimmt:

  - Bei Anruf Plan Nummern wird die Telefonnummer des ursprünglichen Anrufers angezeigt.
  - Für direkte Routing Nummern basiert die gesendete Nummer auf der Einstellung P-Asserted-Identity (Pai) für den SBC wie folgt:
    - Wenn diese Option deaktiviert ist, wird die Telefonnummer des ursprünglichen Anrufers angezeigt. Dies ist die Standardeinstellung und die empfohlene Einstellung.
    - Bei aktivierter Option wird die Telefonnummer des Ressourcenkontos angezeigt.

Wenn Sie in einer Skype for Business-Hybridumgebung einen Anruf der automatischen Telefonzentrale an das PSTN übertragen möchten, erstellen Sie einen neuen lokalen Benutzer, wobei die Anrufweiterleitung auf die PSTN-Nummer festgesetzt ist. Der Benutzer muss für Enterprise-VoIP aktiviert sein und eine VoIP-Richtlinie zugewiesen haben. Weitere Informationen finden Sie unter [automatische Telefonzentrale-Anrufübertragung an PSTN](https://docs.microsoft.com/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).

### <a name="create-an-auto-attendant-with-powershell"></a>Erstellen einer automatischen Telefonzentrale mit PowerShell

Sie können auch PowerShell verwenden, um automatische Telefonzentralen zu erstellen und einzurichten. Hier sind die Cmdlets, die Sie zum Verwalten einer automatischen Telefonzentrale benötigen:

- [Neu – CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant)  
- [Satz-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant)
- [Get-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant)
- [Get-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays)
- [Remove-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant)
- [Neu – CsAutoAttendantMenu](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu)
- [Neu – CsOnlineAudioFile](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile)
- [Neu – CsAutoAttendantCallFlow](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow)
- [Export-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays)
- [New-CsOnlineTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange)
- [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange)
- [New-CsOnlineSchedule](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule)
- [Get-CsAutoAttendantSupportedTimeZone](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone)
- [Neu – CsAutoAttendantCallHandlingAssociation](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation)
- [Get-CsAutoAttendantSupportedLanguage](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)
- [Importieren-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays)
- [Neu – CsAutoAttendantCallableEntity](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity)

## <a name="related-topics"></a>Verwandte Themen

[Das Telefonsystem bietet Ihnen Folgendes](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Abrufen von Diensttelefonnummern](/microsoftteams/getting-service-phone-numbers)

[Verfügbarkeit von Audiokonferenzen und Anrufplänen nach Ländern und Regionen](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[Beispiel für kleine Unternehmen – Einrichten einer automatischen Telefonzentrale](/microsoftteams/tutorial-org-aa)

[Einführung in Windows PowerShell und Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
