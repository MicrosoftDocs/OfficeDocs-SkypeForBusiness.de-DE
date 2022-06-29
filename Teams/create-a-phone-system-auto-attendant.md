---
title: Einrichten einer automatischen Telefonzentrale für Microsoft Teams
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
ms.custom:
- Phone System
description: Erfahren Sie, wie Sie automatische Telefonzentralen in Microsoft Teams einrichten und verwalten.
ms.openlocfilehash: 37326ec03c22c91de5f4c4edb94aaad67f52bde5
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2022
ms.locfileid: "66240944"
---
# <a name="set-up-an-auto-attendant"></a>Einrichten einer automatischen Telefonzentrale

Mit automatischen Telefonzentralen können Personen Ihre Organisation anrufen und in einem Menüsystem navigieren, um mit der richtigen Abteilung, Anrufwarteschleife, Person oder einem Operator zu sprechen. Sie können automatische Telefonzentralen für Ihre Organisation mit dem Microsoft Teams Admin Center oder mit PowerShell erstellen.

Achten Sie darauf, dass Sie " [Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md) " gelesen haben und die [ersten Schritte](plan-auto-attendant-call-queue.md#getting-started) ausgeführt haben, bevor Sie die Verfahren in diesem Artikel befolgen.

Automatische Telefonzentralen können Anrufe basierend auf der Eingabe der Anrufer an eines der folgenden Ziele weiterleiten:

- **Operator** – der für die automatische Telefonzentrale definierte Operator. Das Definieren eines Operators ist optional. Der Operator kann als eines der anderen Ziele in dieser Liste definiert werden.
- **Person in der Organisation** – eine Person in Ihrer Organisation, die Sprachanrufe empfangen kann. Diese Person kann ein Onlinebenutzer oder ein Lokal gehosteter Benutzer sein, der mit Skype for Business Server gehostet wird.
- **VoIP-App** – eine andere automatische Telefonzentrale oder anrufwarteschleife. (Wählen Sie das Ressourcenkonto aus, das der automatischen Telefonzentrale oder Anrufwarteschleife zugeordnet ist, wenn Sie dieses Ziel auswählen.)
- **Voicemail** – das VoIP-Postfach, das einer von Ihnen angegebenen Microsoft 365-Gruppe zugeordnet ist. Sie können auswählen, ob Voicemailtranskriptionen und die Option "Bitte hinterlasse eine Nachricht nach dem Ton" angezeigt werden sollen. Systemaufforderung.
  - Aktivieren Sie im M365 Admin Center für die von Ihnen angegebene Microsoft 365-Gruppe "Personen außerhalb der Organisation das E-Mail-Senden von E-Mails an dieses Team gestatten".
- **Externe Telefonnummer** – beliebige Telefonnummer. Sehen Sie [sich die technischen Details zur externen Übertragung an](create-a-phone-system-auto-attendant.md?tabs=additional-resources).
- **Ankündigung (Audiodatei)** – Wiedergeben einer Audiodatei. Eine aufgezeichnete Ankündigungsnachricht, die Sie hochladen, die als Audio in gespeichert ist. WAV, .MP3 oder . WMA-Format. Die Aufzeichnung darf nicht größer als 5 MB sein. Das System gibt die Ankündigung wieder und kehrt dann zum Menü der automatischen Telefonzentrale zurück.
- **Ankündigung (typisiert)** – Geben Sie eine Nachricht ein. Text, den das System lesen soll. Sie können bis zu 1000 Zeichen eingeben. Das System gibt die Ankündigung wieder und kehrt dann zum Menü der automatischen Telefonzentrale zurück.

Die Schritte zum Hinzufügen einer automatischen Telefonzentrale sind:

1. Richten Sie allgemeine Informationen ein.
1. Richten Sie einen einfachen Anruffluss ein.
1. Richten Sie einen Anruffluss nach Feierabend ein.
1. Richten Sie Anrufflüsse für Feiertage ein.
1. Einrichten des Wählbereichs.
1. Richten Sie Ressourcenkonten ein.

Die im Artikel beschriebenen Schritte erstellen automatische Telefonzentralen mithilfe des Teams Admin Centers. Anweisungen zum **Erstellen von automatischen Telefonzentralen mithilfe von PowerShell** finden [Sie unter Erstellen automatischer Telefonzentralen mit PowerShell-Cmdlets](create-a-phone-system-auto-attendant-via-cmdlets.md).

## <a name="follow-these-steps-to-set-up-your-auto-attendant"></a>Führen Sie die folgenden Schritte aus, um Ihre automatische Telefonzentrale einzurichten.

# <a name="step-1---general-info"></a>[Schritt 1 – Allgemeine Informationen](#tab/general-info)

## <a name="step-1---set-the-auto-attendants-general-information"></a>Schritt 1: Festlegen der allgemeinen Informationen der automatischen Telefonzentrale

Um eine automatische Telefonzentrale einzurichten, erweitern Sie im [Teams Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2066851) **die Option "VoIP**", wählen Sie " **Automatische Telefonzentralen**" und dann " **Hinzufügen"** aus.

1. Geben Sie im Feld oben einen Namen für die automatische Telefonzentrale ein.

2. Geben Sie zum Festlegen eines Operators das Ziel für Aufrufe an den Operator an. Diese Bezeichnung ist optional, wird jedoch empfohlen. Legen **Sie die** Operatoroption fest, damit Anrufer aus den Menüs ausbrechen und mit einer bestimmten Person sprechen können.

3. Geben Sie die Zeitzone für diese automatische Telefonzentrale an. Die Zeitzone wird für die Berechnung der Geschäftszeiten verwendet, wenn Sie [einen separaten Anruffluss für Nachstunden erstellen](?tabs=after-hours).

4. Geben Sie eine [unterstützte Sprache](create-a-phone-system-auto-attendant-languages.md) für diese automatische Telefonzentrale an. Dies ist die Sprache, die für vom System generierte Sprachansagen verwendet wird.

5. Wählen Sie aus, ob Sie Spracheingaben aktivieren möchten. Wenn diese Option aktiviert ist, wird der Name jeder Menüoption zu einem Schlüsselwort für die Spracherkennung. Anrufer können z. B. "Eins" sagen, um die Menüoption auszuwählen, die Schlüssel 1 zugeordnet ist, oder sie können "Vertrieb" sagen, um die Menüoption mit dem Namen "Vertrieb" auszuwählen.

   > [!NOTE]
   > Wenn Sie in Schritt 4 eine Sprache auswählen, die keine Spracheingaben unterstützt, wird diese Option deaktiviert.

Nachdem Sie die allgemeinen Informationen ihrer automatischen Telefonzentrale festgelegt haben, wählen Sie **"Weiter**" aus.


# <a name="step-2---basic-call-flow"></a>[Schritt 2 : Einfacher Anruffluss](#tab/call-flow)

## <a name="step-2---set-up-the-basic-call-flow"></a>Schritt 2 : Einrichten des grundlegenden Anrufflusses

### <a name="set-a-greeting"></a>Festlegen einer Begrüßung

- Wenn Sie **"Audiodatei wiedergeben** " auswählen, können Sie die Schaltfläche " **Datei hochladen** " verwenden, um eine aufgezeichnete Begrüßungsnachricht hochzuladen, die als Audiodatei gespeichert ist. WAV, .MP3 oder . WMA-Format. Die Aufzeichnung darf nicht größer als 5 MB sein.

- Wenn Sie " **Begrüßungsnachricht eingeben** " auswählen, liest das System den eingegebenen Text (bis zu 1000 Zeichen), wenn die automatische Telefonzentrale einen Anruf annimmt.

### <a name="route-the-call"></a>Weiterleiten des Anrufs

- Wenn Sie **"Trennen**" auswählen, legt die automatische Telefonzentrale den Anruf auf.
- Wenn Sie **"Anruf umleiten**" auswählen, können Sie eines der Ziele für die Anrufweiterleitung auswählen.
- Wenn Sie **die Menüoptionen "Wiedergeben**" auswählen, können Sie eine **Audiodatei wiedergeben** oder **eine Begrüßungsnachricht eingeben** und dann zwischen Menüoptionen und Verzeichnissuche wählen.

#### <a name="play-menu-options"></a>Menüoptionen "Wiedergeben"

Weisen Sie für Wähloptionen die 0-9-Tasten auf der Wähltastatur des Telefons einem der Anrufweiterleitungsziele zu. Die Tasten \* (Sternchen) und \# (Pfund) werden vom System reserviert und können nicht neu zugewiesen werden. Wenn Sie eine dieser Tasten drücken, wird das aktuelle Menü wiederholt.

> [!NOTE]
> Die Taste "#" sichert nur die letzte automatische Telefonzentrale. Sobald die Grenze zu einer neuen automatischen Telefonzentrale überschritten wurde, können Sie mit der #-Taste nicht mehr zur vorherigen Telefonzentrale gelangen.

Schlüsselzuordnungen müssen nicht fortlaufend sein. Es ist möglich, ein Menü mit den Tasten 0, 1 und 3 zu den Optionen zu erstellen, während die Taste 2 nicht verwendet wird.

Es wird empfohlen, den Nullschlüssel dem Operator zuzuordnen, wenn Sie einen konfiguriert haben. Wenn der Operator nicht auf eine Taste festgelegt ist, ist auch der Sprachbefehl "Operator" deaktiviert.

Geben Sie für jede Menüoption die folgenden Einstellungen an:

- **Wähltaste** – die Taste auf der Telefontastatur, um auf diese Option zuzugreifen. Wenn Spracheingaben verfügbar sind, können Anrufer auch diese Nummer sagen, um auf die Option zuzugreifen.

- **Sprachbefehl** – Definiert den Sprachbefehl, den ein Anrufer für den Zugriff auf diese Option erteilen kann, wenn Spracheingaben aktiviert sind. Sie kann mehrere Wörter wie "Kundendienst" oder "Vorgänge und Gründe" enthalten. Beispielsweise kann der Aufrufer 2 drücken, "zwei" sagen oder "Vertrieb" sagen, um die Option auszuwählen, die den beiden Tasten zugeordnet ist. Dieser Text wird auch durch Text-zu-Sprache für die Bestätigungsaufforderung des Diensts gerendert. Dies kann etwa "Durchstellung Ihres Anrufs an den Vertrieb" lauten.

- **Umleiten an** – das Anrufweiterleitungsziel, das verwendet wird, wenn Anrufer diese Option auswählen. Wenn Sie zu einer automatischen Telefonzentrale oder Anrufwarteschleife umleiten, wählen Sie das zugehörige Ressourcenkonto aus.

##### <a name="directory-search"></a>Verzeichnissuche

Wenn Sie Zielorten Wählschlüssel zuweisen, empfiehlt es sich, für die **Verzeichnissuche** **"Keine**" auszuwählen. Wenn ein Anrufer versucht, einen Namen oder eine Erweiterung mithilfe von Schlüsseln zu wählen, die bestimmten Zielen zugewiesen sind, wird er möglicherweise unerwartet an ein Ziel weitergeleitet, bevor er die Eingabe des Namens oder der Erweiterung abgeschlossen hat. Es wird empfohlen, dass Sie eine separate automatische Telefonzentrale für die Verzeichnissuche erstellen und ihre automatische Haupttelefonzentrale mit einer Wähltaste verknüpfen.

Wenn Sie keine Wählschlüssel zugewiesen haben, wählen Sie eine Option für die **Verzeichnissuche** aus.

**Namensanwahl** – Wenn Sie diese Option aktivieren, können Anrufer den Namen des Benutzers sagen oder auf der Wähltastatur des Telefons eingeben. Jeder Onlinebenutzer oder jeder Benutzer, der lokal mit Skype for Business Server gehostet wird, ist ein berechtigter Benutzer und kann mit "Dial by name" gefunden werden.

**Dial by extension** – Wenn Sie diese Option aktivieren, können Anrufer eine Verbindung mit Benutzern in Ihrer Organisation herstellen, indem sie ihre Telefonerweiterung wählen. Jeder Onlinebenutzer oder jeder Benutzer, der lokal mithilfe von Skype for Business Server gehostet wird, ist ein berechtigter Benutzer und kann **mit der Erweiterung "Dial"** gefunden werden. (Sie können festlegen, wer im Verzeichnis auf der Seite " [Wählbereich](?tabs=dial-scope) " enthalten ist und wer nicht.)

> [!NOTE]
> Wenn Sie sowohl die Funktionen **"Dial by name** " als auch **"Dial by extension** " verwenden möchten, können Sie ihrer automatischen Hauptzentrale eine Wähltaste zuweisen, um eine automatische Telefonzentrale zu erreichen, die für **"Dial by name**" aktiviert ist. Innerhalb dieser automatischen Telefonzentrale können Sie die 1 Taste (der keine Buchstaben zugeordnet sind) zuweisen, um die automatische Telefonzentrale " **Dial by extension** " zu erreichen.

Weitere Informationen finden Sie in der [Wähl- und Sprachreferenz](dial-voice-reference.md).

Nachdem Sie Ihre grundlegenden Anrufflussoptionen festgelegt haben, wählen Sie **"Weiter**" aus.

# <a name="step-3---after-hours-call-flow"></a>[Schritt 3 : Anruffluss nach Feierabend](#tab/after-hours)

## <a name="step-3---set-up-call-flow-for-after-hours-optional"></a>Schritt 3: Einrichten des Anrufflusses für Nachstunden (optional)

Geschäftszeiten können für jede automatische Telefonzentrale festgelegt werden.

- Wenn geschäftszeiten nicht festgelegt sind, werden alle Tage und alle Stunden am Tag als Geschäftszeiten betrachtet, da standardmäßig ein 24/7-Zeitplan festgelegt ist.
- Geschäftszeiten können mit Zeitumbrüchen während des Tages festgelegt werden, und alle Stunden, die nicht als Geschäftszeiten festgelegt sind, werden als Nachstunden betrachtet.
- Sie können unterschiedliche Optionen für die Behandlung eingehender Anrufe und Begrüßungen für Nachstunden festlegen.

Je nachdem, wie Sie Ihre automatischen Telefonzentralen und Anrufwarteschleifen konfiguriert haben, müssen Sie möglicherweise nur die Anrufweiterleitung nach Feierabend für automatische Telefonzentralen mit direkten Telefonnummern angeben.

Wenn Sie ein separates Anrufrouting für Anrufer nach Feierabend wünschen, geben Sie Ihre Geschäftszeiten für jeden Tag an.

1. Passen Sie neben dem Wochentag in der Tabelle die **Uhrzeiten "Anfang an** " und " **Ende" an** .
1. Wählen Sie bei Bedarf **"Neue Zeit hinzufügen"** aus, um mehrere Stundensätze für einen bestimmten Tag anzugeben, z. B. um eine Mittagspause anzugeben.
1. Wählen Sie Ihre Anrufweiterleitungsoptionen für nach Feierabend aus. Die gleichen allgemeinen Anrufflussoptionen stehen auch nach Feierabend zur Verfügung.

Nachdem Sie den Anruffluss nach Feierabend hinzugefügt haben, wählen Sie **"Weiter**" aus.

# <a name="step-4---holiday-call-flow"></a>[Schritt 4 – Anruffluss für Feiertage](#tab/holidays)

## <a name="step-4---set-up-call-flows-for-holidays-optional"></a>Schritt 4 – Einrichten von Anrufflüssen für Feiertage (optional)

Ihre automatische Telefonzentrale kann für jeden [von Ihnen eingerichteten Feiertag](set-up-holidays-in-teams.md) einen Anruffluss haben. Sie können jeder automatische Telefonzentrale bis zu 20 geplante Feiertage hinzufügen.

1. Wählen Sie auf der Seite "Anrufeinstellungen für Feiertage" die Option **"Hinzufügen"** aus.

1. Geben Sie einen Namen für diese Feiertagseinstellung ein.

1. Wählen Sie in der Dropdownliste " **Feiertag** " den Feiertag aus, den Sie verwenden möchten.

1. Wählen Sie die Art der Begrüßung aus, die Sie verwenden möchten.

1. Wählen Sie aus, ob Sie den Anruf **trennen** oder **umleiten** möchten.

    1. Wenn Sie sich für die Umleitung entschieden haben, wählen Sie das Anrufweiterleitungsziel für den Anruf aus.
    1. Wenn Sie Menüoptionen wiedergeben möchten, konfigurieren Sie die **Menüoptionen "Wiedergeben"**.

1. Klicken Sie auf **Speichern**.

Wiederholen Sie den Vorgang nach Bedarf für jeden zusätzlichen Feiertag.

Nachdem Sie alle Ihre Urlaubszeiten hinzugefügt haben, wählen Sie **"Weiter**" aus.

# <a name="step-5---dial-scope"></a>[Schritt 5 – Wählbereich](#tab/dial-scope)

## <a name="step-5---set-up-dial-scope-optional"></a>Schritt 5 – Einrichten des Wählbereichs (optional)

Der *Wählbereich* definiert, welche Benutzer im Verzeichnis verfügbar sind, wenn ein Anrufer eine Namens- oder Durchwahlnummer verwendet. Der Standardwert von **"Alle Onlinebenutzer**" umfasst alle Benutzer in Ihrer Organisation, die Onlinebenutzer sind oder lokal mithilfe von Skype for Business Server gehostet werden.

Sie können bestimmte Benutzer ein- oder ausschließen, indem Sie unter **"Ein-** oder **Ausschließen**" die **Option "Benutzerdefinierte Benutzergruppe**" auswählen und eine oder mehrere Microsoft 365-Gruppen, Verteilerlisten oder Sicherheitsgruppen auswählen. Beispielsweise können Sie Führungskräfte in Ihrer Organisation aus dem Wählverzeichnis ausschließen.

Wenn sich ein Benutzer in beiden Listen befindet, wird er aus dem Verzeichnis ausgeschlossen.

> [!NOTE]
> Es kann bis zu 36 Stunden dauern, bis ein neuer Benutzer den Namen im Verzeichnis aufgeführt hat.

Nachdem Sie Ihre Optionen für den **Wählbereich** ausgewählt haben, wählen Sie **"Weiter**" aus.

# <a name="step-6---resource-accounts"></a>[Schritt 6 : Ressourcenkonten](#tab/resource-accounts)

## <a name="step-6---set-up-resource-accounts-optional"></a>Schritt 6 : Einrichten von Ressourcenkonten (optional)

Allen automatischen Telefonzentralen muss ein Ressourcenkonto zugeordnet sein.  Automatische Telefonzentralen der ersten Ebene benötigen mindestens ein Ressourcenkonto mit einer zugeordneten Dienstnummer. Wenn Sie möchten, können Sie einer automatischen Telefonzentrale mehrere Ressourcenkonten zuweisen, die jeweils eine separate Dienstnummer haben.

Um ein Ressourcenkonto hinzuzufügen, wählen Sie **"Konto hinzufügen"** aus, und suchen Sie nach dem Konto, das Sie hinzufügen möchten. Wählen Sie **"Hinzufügen"** und dann " **Hinzufügen"** aus.

Nachdem Sie Ressourcenkonten hinzugefügt haben, wählen Sie **"Weiter**" aus.

Weitere Informationen finden [Sie unter Verwalten von Teams-Ressourcenkonten](manage-resource-accounts.md) .

# <a name="additional-resources"></a>[Weitere Ressourcen](#tab/additional-resources)

## <a name="resources-for-more-complex-scenarios"></a>Ressourcen für komplexere Szenarien

### <a name="external-phone-number-transfers---technical-details"></a>Externe Telefonnummernübertragungen – technische Details

Lesen Sie die [Voraussetzungen](plan-auto-attendant-call-queue.md#prerequisites) , damit automatische Telefonzentralen Anrufe extern übertragen können.  Außerdem:

- Für ein Ressourcenkonto mit einer [Anrufplanlizenz](calling-plans-for-office-365.md) oder [einer Telefonieanbieternummer](operator-connect-plan.md) muss die externe Übertragungstelefonnummer im E.164-Format (+[Ländervorwahl][Vorwahl][Telefonnummer]) eingegeben werden.

- Bei einem Ressourcenkonto mit einer Microsoft Teams Telefon Lizenz- und Direct Routing-Online-VoIP-Routingrichtlinie hängt das Externe Übertragungstelefonnummernformat von den [SBC-Einstellungen (Session Border Controller)](direct-routing-connect-the-sbc.md) ab.

Die ausgehende Telefonnummer, die angezeigt wird, wird wie folgt bestimmt:

- Für Anrufplan- und Telefonieanbieternummern wird die Telefonnummer des ursprünglichen Anrufers angezeigt.
- Bei Direct Routing-Nummern basiert die gesendete Nummer wie folgt auf der P-Asserted-Identity (PAI)-Einstellung auf dem SBC:
  - Wenn diese Option auf "Deaktiviert" festgelegt ist, wird die Telefonnummer des ursprünglichen Anrufers angezeigt. Dies ist die standard- und empfohlene Einstellung.
  - Wenn diese Option auf "Aktiviert" festgelegt ist, wird die Telefonnummer des Ressourcenkontos angezeigt.

Erstellen Sie in einer Skype for Business Hybridumgebung zum Übertragen eines automatischen Telefonzentralenanrufs an das PSTN einen neuen lokalen Benutzer, bei dem die Anrufweiterleitung auf die PSTN-Nummer festgelegt ist. Der Benutzer muss für Enterprise-VoIP aktiviert sein und eine VoIP-Richtlinie zugewiesen haben. Weitere Informationen finden Sie unter [Automatische Telefonzentralenanrufübertragung an das PSTN](/SkypeForBusiness/plan/exchange-unified-messaging-online-migration-support#auto-attendant-call-transfer-to-pstn).

### <a name="auto-attendant-diagnostic-tool"></a>Diagnosetool für automatische Telefonzentrale

Als Administrator können Sie mit dem folgenden Diagnosetool überprüfen, ob eine automatische Telefonzentrale Anrufe empfangen kann:

1. Wählen Sie unten **Tests ausführen** aus, um das Diagnosetool im Microsoft 365 Admin füllen.

   > [!div class="nextstepaction"]
   > [Ausführen von Tests: Automatische Teams-Telefonzentrale](https://aka.ms/TeamsAADiag)

2. Geben Sie im Diagnosebereich "Ausführen" das Ressourcenkonto in das Feld **"Benutzername" oder "E-Mail** " ein, und wählen Sie dann **"Tests ausführen**" aus.

3. Die Tests identifizieren Mandanten-, Richtlinien- oder Ressourcenkontokonfigurationen, die verhindern, dass die automatische Telefonzentrale Anrufe entgegennehmen kann, und geben Schritte zur Behebung der erkannten Probleme an.

---

### <a name="related-topics"></a>Verwandte Themen

[Hier erfahren Sie, was Sie mit Teams Phone erhalten](./here-s-what-you-get-with-phone-system.md)

[Servicetelefonnummern erhalten](./getting-service-phone-numbers.md)

[Verfügbarkeit von Audiokonferenzen und Anrufplänen nach Ländern und Regionen](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Einführung in Windows PowerShell und Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
