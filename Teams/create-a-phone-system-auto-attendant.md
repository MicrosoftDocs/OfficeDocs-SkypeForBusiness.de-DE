---
title: Einrichten einer automatischen Cloudtelefonzentrale
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: waseemh
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
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
- Phone System
description: Hier erfahren Sie, wie Sie automatische Cloud-Telefonzentralen für Microsoft Teams einrichten und testen.
ms.openlocfilehash: ba7da55a33aa1fa65b677146e73ce352158a4cdf
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2020
ms.locfileid: "44523799"
---
# <a name="set-up-a-cloud-auto-attendant"></a>Einrichten einer automatischen Cloudtelefonzentrale

Mit automatischen Telefonzentralen können Personen Ihre Organisation anrufen und in einem Menü System navigieren, um mit der richtigen Abteilung, Anrufwarteschlange, Person oder einem Operator zu sprechen. Sie können automatische Telefonzentralen für Ihre Organisation mit dem Microsoft Teams Admin Center oder mit PowerShell erstellen. Wenn Sie eine automatische Telefonzentrale erstellen möchten, wechseln Sie in der linken Navigationsleiste zu **VoIP** , und wählen Sie dann **automatische Telefonzentralen**  >  **Neu hinzufügen**aus.

Wenn Sie mehr über automatische Telefonzentralen erfahren möchten, lesen Sie [Was sind automatische Cloud-Telefonzentralen?](/microsoftteams/what-are-phone-system-auto-attendants)

> [!NOTE]
> Dieser Artikel bezieht sich auf Microsoft Teams und Skype for Business Online.

Telefonnummern werden nicht direkt der automatischen Telefonzentrale, sondern einem [Ressourcenkonto](manage-resource-accounts.md) zugewiesen, das der automatischen Telefonzentrale zugeordnet ist.

Für automatische Telefonzentralen-Implementierungen sind häufig mehrere automatische Telefonzentralen erforderlich. Eine automatische Telefonzentrale der *ersten Ebene* verfügt in der Regel über ein Ressourcenkonto mit einer zugewiesenen Telefonnummer. Eine geschachtelte automatische Telefonzentrale wird als Menü auf zweiter Ebene verwendet, das von der automatischen Telefonzentrale der *ersten Ebene* als Anruf verbunden wird. Eine *geschachtelte* automatische Telefonzentrale muss nicht über eine Telefonnummer verfügen, die dem Ressourcenkonto zugeordnet ist.

## <a name="step-1--get-started"></a>Schritt 1 – erste Schritte

Für eine automatische Telefonzentrale ist ein zugeordnetes Ressourcenkonto erforderlich. Informationen zu Ressourcenkonten und allen erforderlichen Lizenzen finden Sie unter [Verwalten von Ressourcenkonten in Teams](manage-resource-accounts.md) . 
 
<!-- When you create a new auto attendant in Teams after October 10th, 2019, the required auto attendant is automatically created and linked with the new auto attendant. -->
 
> [!TIP]
> Wenn Sie Anrufe an einen Operator oder eine Menüoption umleiten möchten, bei der es sich um einen Online Benutzer mit einer Telefon System Lizenz handelt, müssen Sie diese für Enterprise-VoIP aktivieren. Weitere Informationen finden Sie unter [Zuweisen von Skype for Business-Lizenzen](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) oder [Zuweisen von Microsoft Teams-Add-on-Lizenzen](teams-add-on-licensing/assign-teams-add-on-licenses.md). Sie können auch die Windows PowerShell verwenden. Führen Sie beispielsweise Folgendes aus:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

## <a name="step-2--create-auto-attendants"></a>Schritt 2 – Erstellen von automatischen Telefonzentralen

> [!IMPORTANT]
> Für jede automatische Telefonzentrale ist ein zugeordnetes [Ressourcenkonto](manage-resource-accounts.md)erforderlich. Sie müssen zuerst das Ressourcenkonto erstellen, dann können Sie es der automatischen Telefonzentrale zuordnen.

### <a name="with-the-microsoft-teams-admin-center"></a>Mit dem Microsoft Teams Admin Center

Klicken Sie im **Microsoft Teams Admin Center**auf automatische **Voicemail**  >  -**Telefonzentralen**, und klicken Sie dann auf **+ Hinzufügen**:

#### <a name="general-info-page"></a>Seite "Allgemeine Informationen"

![Screenshot der Seite "meine automatische Telefonzentrale"](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![Symbol der Zahl 1, eine Beschriftung im vorherigen Screenshot- ](media/teamscallout1.png)
 **Namen** geben Sie einen Anzeigenamen für Ihre automatische Telefonzentrale ein. Der Name ist erforderlich und kann maximal 64 Zeichen einschließlich Leerzeichen enthalten. Der hier festgelegte **Name** wird in einer Spalte auf der Registerkarte **automatische Telefonzentrale** angezeigt.

<a name="phonenumber"> </a>

* * *

![Das Symbol der Zahl 2, eine Legende im vorherigen Screenshot ](media/teamscallout2.png)
 <a name="operator"> </a>- 
 **Operator** , ist optional (wird jedoch empfohlen). Sie können die Option " **Operator** " so einstellen, dass Anrufer die Menüs ausbrechen und mit einer bestimmten Person sprechen können.

Die 0-Taste wird standardmäßig dem Operator zugewiesen.

Wenn Sie einen Operator festzulegen, informieren Sie Personen, die über die Option im **Menü "Optionen bearbeiten"** auf der Seite " **Anruffluss** " anrufen. Wenn Sie einen Operator für Ihre automatische Telefonzentrale festlegen, geben Sie den entsprechenden Eingabeaufforderungstext in das Feld **Anrufer hören** ein, oder ändern Sie Ihre Audiodatei, um diese Option einzubeziehen. Beispiel: „Drücken Sie ‚0', um mit der Vermittlung zu sprechen".

Sie haben mehrere Möglichkeiten, den Operator einzurichten:

- **Kein Operator** deaktiviert die Optionen "Operator" und "0 drücken". Dies ist die aktuelle Standardeinstellung.
- Die **Person in der Organisation** weist einer Person eine Telefon System Lizenz zu, die für Enterprise-VoIP oder zugewiesene Anrufpläne in Office 365 aktiviert ist. Sie können es auch so einrichten, dass der Anrufer an die Voicemail weitergeleitet wird. Wenn Sie einen Anrufer an Voicemail senden möchten, wählen Sie **Person in der Organisation** aus, und legen Sie die Einstellungen dieses Kontos fest, um Anrufe direkt an Voicemail zu senden.

     > [!Note]
     > Die **Person in der Organisation** kann ein Online Benutzer oder ein Benutzer sein, der lokal mit Skype for Business Server gehostet wird. Wenn Sie eine **Person in der Organisation** auswählen, können Sie ein Konto mit einem freigegebenen Postfach oder einem Benutzerpostfach auswählen.

- **Sprach-App**  Wählen Sie den Namen des Ressourcenkontos aus, das mit einer automatischen Telefonzentrale oder einer Anrufwarteschlange verknüpft ist, die bereits erstellt wurde. Anrufer, die einen Operator anfordern, werden dorthin umgeleitet.  
<!--   

- **Auto attendant** Select the name of the resource account linked to an auto attendant that has already been created. Callers that request an operator are redirected there.
- **Call queue** Select the name of the resource account linked to a call queue that has already been created. Callers that request an operator are redirected there.

**Phone number (optional)** Enter the service phone number you want to assign to the new resource account this wizard creates and links to the new auto attendant. If you intend this auto attendant to be a nested auto attendant, it doesn't need a phone number. You can add one if for some reason you require several ways to connect to the auto attendant system.

> [!NOTE]
> Auto attendants created after October 10th, 2019 also create a new [resource account](manage-resource-accounts.md) that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available.
-->

* * *

<a name="timezone"> </a>

![Symbol der Zahl 3, einer Legende in der vorherigen Screenshot- ](media/teamscallout3.png) **Zeitzone** Sie müssen die Zeitzone für Ihre automatische Telefonzentrale einstellen. Die Einstellung kann mit der Zeitzone der Hauptadresse, die für Ihre Organisation aufgelistet ist, oder einer anderen Zeitzone identisch sein. Jede automatische Telefonzentrale kann eine andere Zeitzone aufweisen. Die für die automatische Telefonzentrale eingestellten Geschäftszeiten verwenden ebenfalls diese Zeitzone. Stellen Sie sicher, dass Sie die richtige Zeitzone einrichten, um Geschäftsstunden Unterschiede zu vermeiden, da nicht alle Regionen Sommerzeit haben. 

* * *

![Symbol der Zahl 4, ein Callout in der vorherigen Bildschirmfoto ](media/teamscallout4.png)
 <a name="language"> </a> 
 **Sprache** wählen Sie die Sprache aus, die Sie für Ihre automatische Telefonzentrale verwenden möchten. Die automatische Telefonzentrale verwendet diese Sprache für Anrufer, und alle Systemansagen werden in dieser Sprache wiedergegeben.

 * * *

![Symbol der Zahl 5, eine Beschriftung im vorherigen Screenshot Aktivieren der Spracherkennung sprach ](media/teamscallout5.png)
 **Eingaben** ist verfügbar, wenn diese Option aktiviert ist. Anrufer können die Spracheingabe in der von [Ihnen eingerichteten Sprache](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)verwenden. Wenn Sie zulassen möchten, dass Personen nur Ihre Telefontastatur verwenden, um eine Auswahl zu treffen, können Sie die Spracherkennung auf " **aus**" setzen lassen.

* * *  

Wenn Sie mit der Auswahl fertig sind, klicken Sie auf **weiter**.

#### <a name="call-flow"></a>Anruffluss

<a name="greetingsandrouting"> </a>

> [!TIP]
> Sie können festlegen, dass ein benutzerdefinierter Geschäftsstunden Plan mit unterschiedlichen Anruffluss Verhalten während und nach Geschäftszeiten eingerichtet wird. Wenn Sie einen benutzerdefinierten Zeitplan festlegen möchten, legen Sie den optionalen [Anruffluss für After Hours ab](#call-flow-for-after-hours). Standardmäßig verwendet eine automatische Telefonzentrale Geschäftszeiten-Anruf Ströme.

Sie können angepasste Begrüßungen, Eingabeaufforderungen und Menüs einrichten, die von Personen hören, wenn Sie Ihre automatische Telefonzentrale erreichen.

![Screenshot: Abschnitt "Begrüßungsseite für die Anrufbehandlung"](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)

* * *

**Erste Wiedergabe einer Grußnachricht** Eine Begrüßung ist optional und kann auf **keine Begrüßung**, **Wiedergabe einer Audiodatei**oder **eine Grußnachricht**eingestellt werden.

> [!NOTE]
> Eine Begrüßung ist für eine automatische Telefonzentrale der ersten Ebene besonders wertvoll. Eine geschachtelte automatische Telefonzentrale benötigt oft keine Begrüßung.

![Symbol der Zahl 1, einer Legende im vorherigen Screenshot ](media/teamscallout1.png) Wenn Sie **keine Begrüßung**auswählen, hört der Anrufer keine Nachricht oder Begrüßung, bevor der Anruf von einer der Aktionen bearbeitet wird, die Sie später auswählen. 

<!-- You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.-->

![Symbol der Zahl 2, eine Beschriftung im vorherigen Screenshot ](media/teamscallout2.png) Wenn Sie **eine Audiodatei wiedergeben** auswählen, können Sie die Schaltfläche **Datei hochladen** verwenden, um eine aufgezeichnete Grußnachricht hochzuladen, die als Audio gespeichert wurde. WAV,. MP3 oder. WMA-Format. Die Aufzeichnung darf nicht größer als 5 MB sein.

![Symbol der Zahl 3, eine Beschriftung im vorherigen Screenshot ](media/teamscallout3.png) **Geben Sie eine Grußnachricht ein** , wenn Sie diese Option auswählen, geben Sie den Text ein, der vom System gelesen werden soll (bis zu 1000 Zeichen). Geben Sie beispielsweise "Willkommen bei Contoso" ein. Ihr Anruf ist uns sehr wichtig“ Die Ausgabe wird von der Text-zu-Sprache-Software erstellt.

* * *

Im Abschnitt **Anruf weiterleiten** können Sie auswählen, was neben anrufen aus den folgenden Aktionen geschieht. Einstellungen sind die Optionen " **trennen**", " **Anruf umleiten** **" oder "Wiedergabe"**.

Wenn Sie **trennen**auswählen, wird der Anrufer nach der Wiedergabe der Ansage getrennt. 

<a name="redirectcalls"> </a>

![Symbol der Zahl 4: eine Beschriftung im vorherigen Screenshot- ](media/teamscallout4.png) **Umleitungs Anruf** sendet den Anrufer an das gewählte Ziel, ohne eine der Optionen zu wählen. Die möglichen Einstellungen lauten wie folgt:

  - **Person in der Organisation** Für das von Ihnen ausgewählte Konto muss eine Telefon System Lizenz für Enterprise-VoIP aktiviert sein, oder Sie verfügen über einen zugewiesenen Anrufplan in Office 365. Sie können es so einrichten, dass der Anrufer an Voicemail gesendet werden kann: Wählen Sie **Person in der Organisation** aus, und legen Sie fest, dass Anrufe direkt an Voicemail weitergeleitet werden.

    > [!Note]
    > Die **Person in der Organisation** kann ein Online Benutzer oder ein Benutzer sein, der lokal mit Skype for Business Server gehostet wird. Wenn Sie eine **Person in der Organisation** auswählen, können Sie ein Konto mit einem freigegebenen Postfach oder einem Benutzerpostfach auswählen.

  - **Sprach-App** Wählen Sie eine automatische Telefonzentrale oder eine Anrufwarteschlange aus, die bereits eingerichtet wurde. Sie suchen nach der automatischen Telefonzentrale oder Anrufwarteschlange nach dem Namen des Ressourcenkontos, das dem Dienst zugeordnet ist.
  - **Voicemail** Wählen Sie die Office 365-Gruppe aus, die die Benutzer in Ihrer Organisation enthält, die auf Voicemail zugreifen müssen, die von dieser automatischen Telefonzentrale empfangen wurde. Voicemail-Nachrichten werden an die von Ihnen angegebene Office 365-Gruppe gesendet. Um auf Voicemail-Nachrichten zuzugreifen, können Mitglieder der Gruppe Sie öffnen, indem Sie in Outlook zur Gruppe navigieren.

      Schalten Sie die **Transkription** auf **ein** , um die sprach-zu-Text-Transkription von Voicemail-Nachrichten zu aktivieren.

 * * *

![Screenshot: Abschnitt "Aktionen für die Anrufbehandlung"](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)

![Symbol der Zahl 1, einer Legende im vorherigen Screenshot ](media/teamscallout1.png) Wenn Sie **Menü Optionen für "Wiedergabe** " auswählen, können Sie auswählen, ob Sie eine Audiodatei verwenden oder Text eingeben möchten, der als Text-zu-Sprache gerendert wird, um Anrufern Menü Optionen zur Verfügung zu stellen. Wählen Sie diese Option anstelle der Optionen **Umleitung anrufen** oder **trennen** aus.


![Symbol der Zahl 2: eine Legende im vorherigen Screenshot ](media/teamscallout2.png) **Wiedergeben einer Audiodatei** ermöglicht das Einrichten von Eingabeaufforderungen und Optionen für den Anrufer. 
- Wenn Sie **eine Audiodatei wiedergeben** auswählen, können Sie die Schaltfläche **Datei hochladen** verwenden, um eine aufgezeichnete Grußnachricht hochzuladen, die als Audio gespeichert wurde. WAV,. MP3 oder. WMA-Format. Die Aufzeichnung darf nicht größer als 5 MB sein.

- **Eingeben einer Grußnachricht** Wenn Sie diese Option auswählen, geben Sie den Text ein, der vom System gelesen werden soll (bis zu 1000 Zeichen). Geben Sie beispielsweise "Willkommen bei Contoso" ein. Ihr Anruf ist uns sehr wichtig“ Die Ausgabe wird von der Text-zu-Sprache-Software erstellt.

**Menü Optionen einstellen** In diesem Dialogfeld können Telefontasten oder Sprachbefehle hinzugefügt oder entfernt werden. Um eine Menüoption zu löschen, entfernen Sie den Sprachbefehls Eintrag, und legen Sie **Redirect auf** zurück zur **Auswahl**.

> [!TIP]
> Aktualisieren Sie Menü Aufforderungstext, oder nehmen Sie die Audioeingaben erneut auf, wenn Sie Optionen entfernen. Die für Anrufer abgespielte Menüansage wird nicht automatisch aktualisiert.  
>
> Jede Menüoption kann in beliebiger Reihenfolge hinzugefügt und entfernt werden, und die Tastenzuordnungen müssen nicht kontinuierlich sein. So können Sie beispielsweise ein Menü mit den Tasten 0, 1 und 3 erstellen, die den Optionen zugeordnet sind, während die Taste 2 nicht verwendet wird.

> [!NOTE]
> Die Tasten \* (wiederholen) und \# (zurück) werden vom System reserviert und können nicht neu zugewiesen werden. Wenn die Spracherkennung aktiviert ist, entspricht das Drücken von * mit "Wiederholen", und # entspricht den Sprachbefehlen "zurück".

![Symbol der Zahl 3, einer Legende im vorherigen Screenshot ](media/teamscallout3.png) zum Einrichten einer Menüoption klicken Sie auf die Schaltfläche **+ Zuweisen einer Wähl Taste** , und geben Sie Informationen für die folgenden Optionen ein:

![Symbol der Zahl 4: ein Callout in der vorherigen Screenshot- ](media/teamscallout4.png) **Sprachbefehls** Spalte für eine Option kann bis zu 64 Zeichen lang sein und mehrere Wörter wie "Kundendienst" oder "Vorgänge und Gründe" enthalten.   Wenn die Spracherkennung aktiviert ist, wird der Name automatisch erkannt, und der Anrufer ist in der Lage, 3 zu drücken, "drei" zu sagen oder "Kundendienst" zu wählen, um die Option auszuwählen, die Key 3 zugeordnet ist. Dieser Text wird auch von Text in Sprache für die Bestätigungsaufforderung des Diensts gerendert, die möglicherweise so etwas wie "übertragen des Anrufs an den Operator" sein könnte.

![Symbol der Zahl 5, ein Callout im vorherigen Screenshot ](media/teamscallout5.png) die Option " **Umleiten an** " legt fest, wo der Anruf abläuft, wenn die entsprechende Taste gedrückt wird, oder die Option wird mithilfe der Spracherkennung ausgewählt. Der Anruf kann gesendet werden an:

<!-- Is the Operator behavior changing here? Looks like operator is only an available option for dial key 0 -->

- **Operator** Wenn ein Operator bereits eingerichtet ist, wird die Option automatisch der Taste 0 zugeordnet, kann aber auch gelöscht oder einem anderen Schlüssel zugewiesen werden. Der Anrufer, der diese Option auswählt, wird an den festgelegten Operator gesendet. Wenn der Operator nicht auf eine beliebige Taste eingestellt ist, ist der Sprachbefehl "Operator" ebenfalls deaktiviert. 
- Die **Person in der Organisation** kann ein Online Benutzer oder ein Benutzer sein, der lokal mit Skype for Business Server gehostet wird. Der Benutzer muss über eine Telefon System Lizenz verfügen, die für Enterprise-VoIP oder zugewiesene Anrufpläne in Office 365 aktiviert ist. Suchen Sie im Feld nach **Name suchen** nach der betreffenden Person.

- **Sprach-App** Wählen Sie eine automatische Telefonzentrale oder eine Anrufwarteschlange aus, die bereits eingerichtet wurde. Sie suchen nach der automatischen Telefonzentrale oder Anrufwarteschlange nach dem Namen des Ressourcenkontos, das der Anwendung zugeordnet ist.

- **Voicemail** Wählen Sie die Office 365-Gruppe aus, die die Benutzer in Ihrer Organisation enthält, die auf Voicemail zugreifen müssen, die von dieser automatischen Telefonzentrale empfangen wurde. Voicemail-Nachrichten werden an die von Ihnen angegebene Office 365-Gruppe gesendet. Um auf Voicemail-Nachrichten zuzugreifen, können Mitglieder der Gruppe Sie öffnen, indem Sie in Outlook zur Gruppe navigieren.

    Schalten Sie die **Transkription** auf **ein** , um die sprach-zu-Text-Transkription von Voicemail-Nachrichten zu aktivieren.

<!-- - **Auto attendant** Select the name of an existing auto attendant in the **Search by name** field. You will also have to select a resource account associated to the auto attendant. The caller who selects this option is sent to that auto attendant.
- **Call queue** Select the name of an existing call queue in the **Search by name** field. You will also have to select a resource account associated to the call queue. The caller who selects this option is sent to that call queue, where the call is answered by a call agent.
- **External phone number** routes the caller to a designated phone number outside your local system.<!-- does this have prerequisites like direct routing?
- **Group Voicemail** routes the call to a voicemail box that you select.  -->

![Symbol der Zahl 6, einer Legende in der vorherigen Screenshot- ](media/teamscallout6.png) **Verzeichnissuche** in diesem Abschnitt können Sie die **Wählfunktion nach Namen** und **Dial by Extension** die Durchwahl für die automatische Telefonzentrale aktivieren.   Auf der Seite Optionaler Wählbereich können Sie bestimmen, wer in diesen Diensten enthalten ist und was nicht. Die Verzeichnissuche ist standardmäßig auf **keine** eingestellt.

**Wählen nach Name** Wenn Sie diese Option aktivieren, können Anrufer nach Personen in Ihrer Organisation mithilfe **von Dial by Name**suchen. Sie sagen, dass der Name und die Spracherkennung des Benutzers mit einem Benutzer übereinstimmen. Auf der Seite Optionaler Wählbereich können Sie bestimmen, wer in diesen Diensten enthalten ist und was nicht. Jeder Online-Nutzer mit einer Telefon System-Lizenz oder einem lokal gehosteten Benutzer mit Skype for Business Server ist ein berechtigter Nutzer und kann mit dem Dial by-Namen gefunden werden.


**Durchwahl** Wenn Sie diese Option aktivieren, können Anrufer mit den Benutzern in Ihrer Organisation eine Verbindung herstellen, indem Sie die Durchwahl Ihres Telefons eingeben. Auf der Seite Optionaler Wählbereich können Sie auswählen, welche Benutzer als "verfügbar" oder "nicht verfügbar" für " **Dial by Extension** " aufgeführt sind. Jeder Online-Nutzer mit einer Telefon System-Lizenz oder einem lokal gehosteten Benutzer mit Skype for Business Server ist ein berechtigter Nutzer und kann mit Dial by Extension gefunden werden.

> [!IMPORTANT]
> Beachten Sie bitte Folgendes:
>- Benutzer, die Sie für Dial by Extension zur Verfügung stellen möchten, müssen über eine Erweiterung verfügen, die als Teil eines der folgenden Telefon Attribute angegeben ist, die in Active Directory oder Azure Active Directory [Microsoft 365 Admin Center](https://docs.microsoft.com/office365/admin/add-users/add-users?view=o365-worldwide#use-the-new-admin-center-to-add-users)definiert sind.
>    - HomePhone
>    - Mobil-Handy
>    - TelephoneNumber/Telefonnummer
>    - OtherTelephone
>- Das erforderliche Format, um die Erweiterung in das Feld Benutzer Telefonnummer einzugeben, ist entweder `+<phonenumber>;ext=<extension>` oder `x<extension>` .
>- Das Zuweisen einer Erweiterung im Team Admin Center wird derzeit nicht unterstützt. Sie müssen entweder den Befehl " [MsolUser](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0) PowerShell" oder das Microsoft 365 Admin Center verwenden.
>- Es kann bis zu 12 Stunden dauern, bis Änderungen an den Aad-Telefon-und Handy-Attributen verfügbar sind.
>- Bitte definieren Sie keine Erweiterung für die LineUri eines Benutzers. Dies wird derzeit nicht unterstützt.
>- Eine automatische Telefonzentrale kann entweder für die Wahl nach Namen oder für die Durchwahl, aber nicht für beide konfiguriert werden.

> [!NOTE]
> Wenn Sie sowohl die Funktionen " **Dial by Name** " als auch " **Dial by Extension** " verwenden möchten, können Sie die Haupt-automatische Telefonzentrale (für **Dial by Name**aktiviert) erstellen, die Anrufer auffordert, eine Menüoption auszuwählen, wenn Sie die Durchwahl des Benutzers kennen, und diese Option so festlegen, dass der Anruf an eine automatische Telefonzentrale übertragen wird, die für die Durchwahl aktiviert ist

* * *

<!--
**Instructions for callers** lets you choose **Use recorded call instructions** or **Write your call instructions**.  

If you choose **Use recorded call instructions**, you have the option to record and upload new or prerecorded sound files to play as menu instructions. The same app used in recording the auto attendant greeting is used here.

If you choose **Write your call instructions**, enter the script  you want the system to read (up to 1000 characters). For example, you might enter text that begins "Please choose from one of the following menu options ... " and provide a script written to reflect your configuration.
* * *  -->

Wenn Sie Ihre Auswahl getroffen haben, können Sie auf **weiter** klicken, wenn Sie die erweiterten Einstellungen ändern möchten, oder auf **Absenden** klicken, wenn Sie die Standardeinstellungen für Folgendes verwenden möchten:
- Anruffluss für After Hours
- Anruffluss für Feiertage
- Wählbereich
- Ressourcenkonten

Da für Ihre automatische Telefonzentrale ein Ressourcenkonto erforderlich ist, haben Sie die Möglichkeit, zur Seite " **Ressourcenkonto** " zu wechseln und ein bereits konfiguriertes Ressourcenkonto zu verknüpfen oder ein Ressourcenkonto zu erstellen und es der automatischen Telefonzentrale zuzuordnen, wie es unter [Verwalten von Ressourcenkonten in Microsoft Teams](manage-resource-accounts.md)beschrieben ist. Sie können diese automatische Telefonzentrale erst dann verwenden, wenn Sie einem Ressourcenkonto zugeordnet wurde. Klicken Sie dazu unten auf dem Bildschirm auf die Schaltfläche **weiter** , und klicken Sie dann im linken Navigationsbereich auf **Ressourcenkonten** , um direkt zur Seite Ressourcenkonten zu wechseln und die automatische Telefonzentrale einem Ressourcenkonto zuzuordnen.

#### <a name="advanced-settings-optional"></a>Erweiterte Einstellungen (optional)

Es gibt vier zusätzliche Bildschirme, die Sie bei der Auswahl standardmäßig konfigurieren oder belassen können.

##### <a name="call-flow-for-after-hours"></a>Anruffluss für After Hours

Standardmäßig werden die Geschäftszeiten einer automatischen Telefonzentrale von Montag bis Freitag auf 09.00 Uhr eingestellt.  <!--24/7-->, und die Anruffluss Optionen für *After Hours* -Anrufe sind deaktiviert, da alle Stunden als *Geschäftszeiten*gelten. Wenn Sie die Option **benutzerdefinierte Geschäftszeiten einrichten** auswählen, konfiguriert die Seite **Anruffluss für After Hours** die Anruf Behandlungs Regeln, die von der automatischen Telefonzentrale nach Stunden verwendet werden. Die verfügbaren Optionen sind identisch, der Unterschied besteht darin, dass Sie einen Zeitplan für verschiedene Menüs und Verhaltensweisen festlegen können.

Bei einem System von automatischen Telefonzentralen muss möglicherweise nur das Anruf Behandlungs Verhalten für die automatische Telefonzentrale der ersten Ebene nach Stunden eingestellt werden. Geschachtelte automatische Telefonzentralen werden möglicherweise nicht einmal von der automatischen Telefonzentrale der ersten Ebene aufgerufen, aber Alternativ kann das System das After-Hours-Verhalten für jede verwendete automatische Telefonzentrale definieren.

Zunächst werden die Geschäftszeiten so festgelegt, dass Sie um 12:00 Uhr beginnen und um 12:00 Uhr, Sonntag bis Samstag, enden. Alle Stunden, die nicht während der Geschäftszeiten sind, werden *nach Stunden*berücksichtigt.


![Screenshot der Anruffluss Einstellungen für After Hours](media/aa-afterhour.png)
 * * *

![Symbol der Zahl 1, einer Legende im vorherigen Screenshot: ](media/teamscallout1.png) Sie können auf **24/7 auswählen** klicken, um die Geschäftszeiten für diese automatische Telefonzentrale zu übernehmen.

![Symbol der Zahl 2, eine Legende im vorherigen Screenshot ](media/teamscallout2.png) Wählen Sie die Option **auf Standard zurücksetzen** aus, um alle Änderungen im Terminplan rückgängig zu machen und zur Standard Definition der Geschäftszeiten zurückzukehren, wobei Sie Montag bis Freitag 9:00 Uhr bis 5:00 Uhr sind.

![Symbol der Zahl 3: eine Legende im vorherigen Screenshot ](media/teamscallout3.png) Wählen Sie **alle Stunden löschen** aus, um den Terminplan vollständig zu löschen. Wenn Sie diese Option auswählen und die festgelegten Stunden nicht mehr benötigen, sollten Sie diese Option nur verwenden, wenn Sie Ihre Geschäftszeiten vollständig wiederholen möchten.

![Symbol der Zahl 4, einer Legende im vorherigen Screenshot- ](media/teamscallout4.png) ![ Symbol der Zahl 5, einer Legende im vorherigen Screenshot ](media/teamscallout5.png) zum Anpassen der Start-oder Endzeit für einen Wochentag, klicken Sie auf **Start at** oder **Ende** zum Zeitpunkt, zu dem Sie das zurücksetzen möchten, und wählen Sie die neue Uhrzeit in der angezeigten Liste aus.   In der Liste können Sie Geschäftszeiten in 15-Minuten-Intervallen auswählen, und die hier ausgewählten Geschäftszeiten basieren auf der Zeitzone, die Sie auf der Seite **Allgemeine Informationen** festzulegen.

 <!-- The **Apply to all days** option can be used to reset all days of the week to match the settings for that day. This makes setting weekdays and weekends to different hours easier.-->

![Symbol der Zahl 6, eine Legende im vorherigen Screenshot ](media/teamscallout6.png) zum Einrichten einer Unterbrechung (beispielsweise eine Mittagspause), wählen Sie neue Zeit für diesen Wochentag **Hinzufügen** aus, um eine neue Tabellenzeile zu erstellen, und wählen Sie neue Start-und Endzeit aus. Sie können innerhalb der Geschäftszeiten mehrere Pausen festlegen.

Die nach Stunden verfügbaren Optionen für den [Anruffluss](#call-flow) sind die gleichen wie die während der Geschäftszeiten verfügbaren Optionen. Scrollen Sie auf der Seite Informationseintrag nach unten, um die Anruffluss Optionen nach Stunden festzulegen.

* * *

Wenn Sie die gewünschten Optionen ausgewählt haben, klicken Sie auf **weiter**. Sie können auch im linken Navigationsbereich auf **Ressourcenkonten** klicken, um direkt zur Seite Ressourcenkonten zu wechseln und Ihre automatische Telefonzentrale einem Ressourcenkonto zuzuordnen.

##### <a name="call-flow-during-holidays"></a>Anruffluss während der Feiertage

<a name="holidaygreetings"> </a>

Sie können jeder automatische Telefonzentrale bis zu 20 geplante Feiertage hinzufügen. Ihre Organisation hat möglicherweise bereits Feiertage definiert, wie unter [Einrichten von Feiertagen in Microsoft Teams](set-up-holidays-in-teams.md)beschrieben. Wenn dies nicht der Fall ist, sehen Sie den folgenden Bildschirm: 

![Screenshot: keine Feiertage konfiguriert](media/aa-no-holidays.png)

![Symbol der Zahl 1, einer Legende im vorherigen Screenshot, ](media/teamscallout1.png) um einen benutzerdefinierten Anruffluss für einen Feiertag in der automatischen Telefonzentrale festzulegen, klicken Sie auf **+ Hinzufügen** , um den Bildschirm " **neue Feiertags Anruffluss** " anzuzeigen.
> [!TIP]
> Zum Erstellen von Feiertagen können Sie auf dem Bildschirm unter " **organisationsweite Einstellungen**" auf "  >  **Feiertage**" wechseln.  



![Screenshot: Hinzufügen eines Anruf Handlers](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

* * *

![Symbol der Zahl 1, eine Beschriftung im vorherigen Screenshot ](media/teamscallout1.png) Geben Sie einen **Namen** für den neuen Anruffluss ein.

![Symbol der Zahl 2, eine Beschriftung im vorherigen Screenshot ](media/teamscallout2.png) Wenn Sie bereits Feiertage erstellt haben, werden diese im Pulldown-Menü " **Feiertag** " angezeigt, und Sie können Sie auswählen. Möglicherweise wird eine nicht verwendete Option angezeigt, die Sie in Ihren Anforderungen bearbeiten können. Wenn dies nicht der Fall ist, klicken Sie unten in der Pulldown-Liste auf **Hinzufügen** , um einen neuen Feiertag zu erstellen.  Die zum Erstellen eines Feiertags verwendeten Schritte finden Sie unter [Einrichten von Feiertagen in Microsoft Teams](set-up-holidays-in-teams.md) . 

Ein Feiertags-Anruffluss Name kann bis zu 64 Zeichen lang sein und muss für die Organisation eindeutig sein. So können Sie beispielsweise in der gleichen Organisation nicht zwei Urlaubs Anruf Flüsse mit dem Namen "Thanksgiving" haben. Ihre automatische Telefonzentrale kann einen Anruffluss für jeden Feiertag haben, den Sie eingerichtet haben, aber möglicherweise möchten Sie eine gemeinsame Reihe von Verhaltensweisen planen, die nicht mit einer benutzerdefinierten Begrüßung geplant sind.

![Symbol der Zahl 3, eine Legende im vorherigen Screenshot ](media/teamscallout3.png) die für einen Feiertags Anruffluss verfügbaren [Gruß](#call-flow) Optionen entsprechen den Optionen, die während der Geschäftszeiten zur Verfügung stehen. Die **Aktionen** , die nach der Wiedergabe der Ansage ausgeführt werden, sind ebenfalls ähnlich, mit der Ausnahme, dass es sich bei den einzigen verfügbaren Aktionen um die **Trennung** oder **Umleitung**handelt, und bei der Auswahl der Option **zum Umleiten an** ist der Operator nicht eine der verfügbaren Optionen. Sie können kein spezielles Menü für einen Feiertags Fluss einrichten.

> [!NOTE]
> Standardmäßig werden alle während eines Urlaubs Zeitraums empfangenen Anrufe nach der Ansage (sofern vorhanden) auf " **trennen** " festgelegt, sodass Sie eine Umleitung angeben müssen, wenn Sie ein benutzerdefiniertes Verhalten wünschen.

![Screenshot der Anruf Flüsse während der Feiertags Seite](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

Klicken Sie auf speichern, um die Erstellung des Feiertags-Anrufflusses abzuschließen. Nachdem Sie einen Feiertags-Anruffluss erstellt haben, wird er auf dem Bildschirm " **Anruf Flüsse während des Urlaubs** " angezeigt.

Klicken Sie auf **weiter** , um den Wählbereich zu ändern, **zurück** , um Änderungen an den nach Stunden-Anruf strömen vorzunehmen, und über **Mitteln** , wenn Sie fertig sind. Sie können auch im linken Navigationsbereich auf **Ressourcenkonten** klicken, um direkt zur Seite Ressourcenkonten zu wechseln und Ihre automatische Telefonzentrale einem Ressourcenkonto zuzuordnen.

#### <a name="dial-scope"></a>Wählbereich

<a name="dialscope"> </a>

![Screenshot mit der Seite "Wählbereich"](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

Auf dieser Seite können Sie festlegen, wer in Ihrem Verzeichnis aufgeführt und für Dial by Name verfügbar ist, wenn eine Person Ihre Organisation anruft. Dial by Name ist in einem früheren Fenster standardmäßig auf **Off** eingestellt. Alle Benutzer mit einer Erweiterung stehen zur Verfügung **,** wenn die Wähl-Erweiterung zuvor ausgewählt wurde.

![Symbol der Zahl 1: ](media/teamscallout1.png) **Include** die Optionen in diesem Abschnitt sind entweder **alle Online Benutzer** oder Benutzer **definierte Benutzergruppen** .

Wenn Sie **alle Online Benutzer**auswählen, werden alle berechtigten Benutzer in die Verzeichnissuche einbezogen.

**Benutzerdefinierte Benutzergruppen** Mit dieser Option können Sie eine in Ihrer Organisation bereits erstellte Office 365-Gruppe,-Verteilerliste oder-Sicherheitsgruppe suchen und auswählen. Benutzer werden dem Verzeichnis hinzugefügt, wenn Sie sich in der ausgewählten Office 365-Gruppe,-Verteilerliste oder-Sicherheitsgruppe befinden, und Sie sind **Online Benutzer mit einer Telefon System Lizenz** oder lokal mit Skype for Business Server gehostet. Sie können dem Verzeichnis mehrere Microsoft 365-Gruppen,-Verteilerlisten und-Sicherheitsgruppen hinzufügen.

<a name="dialscope"> </a>

Auf dieser Seite können Sie festlegen, welche Benutzer in Ihrer Organisation in Ihrem Verzeichnis aufgeführt und für die Wahl nach Namen verfügbar sein sollen, wenn eine Person, die sich in Ihre Organisation einwählt.

![Symbol der Zahl 2: eine Legende im vorherigen Screenshot ](media/teamscallout2.png) **schließt** die Optionen in diesem Abschnitt aus, mit denen Sie bestimmte Benutzer oder Gruppen von Benutzern aus dem Verzeichnis der Organisation ausschließen können.

Wenn Sie **keine**auswählen, werden alle berechtigten Benutzer in die Verzeichnissuche einbezogen.

**Benutzerdefinierte Benutzergruppe** Sie können nach einer Office 365-Gruppe,-Verteilerliste oder-Sicherheitsgruppe suchen, die in Ihrer Organisation erstellt wurde. Benutzer in dieser Gruppe sind von der Verzeichnissuche ausgeschlossen. Sie können mehrere Microsoft 365-Gruppen,-Verteilerlisten und-Sicherheitsgruppen hinzufügen.


Wenn Sie die Einstellungen bei aktivierter Wahl nach Namen standardmäßig beibehalten, werden alle berechtigten Benutzer in die Verzeichnissuche einbezogen.

> [!NOTE]
> Es kann bis zu 36 Stunden dauern, bis der Name des neuen Benutzers im Verzeichnis aufgeführt ist. Wenn jemand Dial-by-Name mit Spracherkennung verwendet, stehen neue Konten möglicherweise nicht für dieses Feature zur Verfügung.

Nachdem Sie alle erforderlichen Felder eingegeben und die Menüs und Optionen für die Anrufbehandlung eingerichtet haben, klicken Sie auf **weiter** , um mit dem Zuordnen eines Ressourcenkontos fortzufahren.

#### <a name="resource-accounts"></a>Ressourcenkonten

Alle automatischen Telefonzentralen müssen über ein zugeordnetes Ressourcenkonto verfügen.  Für automatische Telefonzentralen auf oberster Ebene wird definitiv mindestens ein Ressourcenkonto benötigt, das über eine zugeordnete Dienstnummer verfügt. Wenn Sie möchten, können Sie einer automatischen Telefonzentrale mit jeweils einer separaten Servicenummer mehrere Ressourcenkonten zuweisen.

Wenn Sie noch kein Ressourcenkonto für Ihre automatische Telefonzentrale konfiguriert haben, wird der folgende Bildschirm angezeigt: 

![Screenshot: optionale Ressourcenkonto Verwaltung](media/aa-ra-optional.png) 

![Symbol der Zahl 1, einer Legende im vorherigen Screenshot Wenn Sie ](media/teamscallout1.png) der automatischen Telefonzentrale mindestens ein vorhandenes und nicht zugewiesenes Ressourcenkonto hinzufügen möchten, klicken Sie auf **Konten hinzufügen** , und wählen Sie Sie aus den bereitgestellten Dialogfeldern aus.

![Screenshot der Zusammenfassungsansicht der neuen Telefonzentrale](media/aa-assigned.png)

![Symbol der Zahl 1, einer Legende im vorherigen Screenshot Wenn Sie ](media/teamscallout1.png) ein zusätzliches Ressourcenkonto hinzufügen möchten, klicken Sie auf **+ Konto hinzufügen**.

![Symbol der Zahl 2, eine Legende im vorherigen Screenshot](media/teamscallout2.png) Das Ressourcenkonto oder die Konten, die dieser automatischen Telefonzentrale zugewiesen sind, werden in einer Liste angezeigt.

## <a name="edit-auto-attendants"></a>Bearbeiten von automatischen Telefonzentralen

Nachdem Sie die neue automatische Telefonzentrale gespeichert haben, wird Sie auf der Seite **automatische Telefonzentralen** angezeigt. Auf dieser Seite können Sie schnell einige der von Ihnen eingerichteten Optionen sehen, einschließlich Name, zugeordnetes Ressourcenkonto, Sprache und zugewiesenen Operator.

![Screenshot der Attendant-Liste](media/aa-list.png)

Wenn Sie die Einstellungen für die automatische Telefonzentrale ändern möchten, wählen Sie die automatische Telefonzentrale aus, und klicken Sie dann im Bereich "Aktion" auf **Bearbeiten**.

<!-- To quickly place a test call to your auto attendant, click the **Test** button in the Action pane. -->

<!-- ## Summary view

You can use the Summary page to review the settings you've created.

![screenshot of the new attendant summary view](media/aa-new-summary.png)

Press the **Create** button to finish setup of your new auto attendant. -->

### <a name="create-an-auto-attendant-with-powershell"></a>Erstellen einer automatischen Telefonzentrale mit PowerShell

Sie können auch PowerShell verwenden, um automatische Telefonzentralen zu erstellen und einzurichten. Hier sind die Cmdlets, die Sie zum Verwalten einer automatischen Telefonzentrale benötigen:

- [Neu – CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [Satz-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [Get-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/get-csautoattendant?view=skype-ps)
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

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 und Microsoft Teams von einem zentralen Punkt aus verwalten, der Ihre tägliche Arbeit vereinfachen kann. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

  - [Einführung in Windows PowerShell und Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Warum Sie Office 365 PowerShell verwenden müssen](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell bietet zahlreiche Vorteile bei der Geschwindigkeit, Einfachheit und Produktivität, wenn nur das Microsoft 365 Admin Center verwendet wird, beispielsweise das vornehmen von Einstellungsänderungen für viele Benutzer gleichzeitig. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:

  - [Verwalten von Office 365 mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>Verwandte Themen

[Das Telefonsystem in Office 365 bietet Ihnen Folgendes](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Abrufen von Diensttelefonnummern](/microsoftteams/getting-service-phone-numbers)

[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[New-CsOrganizationalAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[Was sind automatische Cloudtelefonzentralen?](what-are-phone-system-auto-attendants.md)

[Beispiel für kleine Unternehmen – Einrichten einer automatischen Telefonzentrale](/microsoftteams/tutorial-org-aa)  
