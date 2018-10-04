---
title: Einrichten einer automatischen Telefonzentrale für das Telefonsystem
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.date: 9/1/2018
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Informationen Sie zum Einrichten und Testen von Telefonsystem (Cloud, PBX) automatische Telefonzentralen für effiziente Anruf Behandeln von für Ihre Organisation. '
ms.openlocfilehash: 41a4f7d3536e3a92104c98eaee057a47a21aeb9e
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373571"
---
# <a name="set-up-a-phone-system-auto-attendant"></a>Einrichten einer automatischen Telefonzentrale für das Telefonsystem

Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator. You can create an auto attendant for your organization by using the Skype for Business admin center. To create a new auto attendant, go to **Call routing** in the left navigation, and then select **Auto attendants** > **Add new**.

Wenn Sie weitere Informationen zu automatischen Telefonzentralen finden möchten, finden Sie unter [Was Telefonsystem automatischen Telefonzentralen sind?](/microsoftteams/what-are-phone-system-auto-attendants)

## <a name="step-1---getting-started"></a>Schritt 1 - Erste Schritte

- Before you can create and set up your auto attendants, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service numbers, they will show up on the **Skype for Business admin center** > **Voice** > **Phone numbers** page. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md), or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365). **User (subscriber)** numbers can't be assigned to auto attendants. If you are outside the United States, you can't use the Skype for Business admin center to get service numbers; go [here](/microsoftteams/manage-phone-numbers-for-your-organization) instead.

    > [!CAUTION]
    > To get and use toll-free phone numbers, you need to set up Communications Credits. To do this see [What are Communications Credits?](/microsoftteams/what-are-communications-credits) and [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).
  
- Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license. The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for auto attendants. The numbers of auto attendants you can have is dependent on the number **Phone System** and **Audio Conferencing** licenses that are assigned in your organization. To learn more about licensing, go [here](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

    > [!TIP]
    > To redirect calls to an operator or a menu option that is an Online user with a **Phone System** license, you will need to enable them for Enterprise Voice or assign Calling Plans in Office 365 to them. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). You can also use Windows PowerShell. For example, run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
## <a name="step-2---create-a-new-auto-attendant"></a>Schritt 2 - Erstellen einer neuen automatischen Telefonzentrale

![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter**


Klicken Sie im **Skype for Business Admin Center** auf **Anrufweiterleitung** > **Automatische Telefonzentralen** und dann auf **Neu hinzufügen**:

### <a name="edit-general-info-page"></a>Seite „Allgemeine Informationen bearbeiten"

![New auto attendant page 1.](../images/edacec94-9384-4a87-be0a-5c49a151287e.png)

***
![Nummer 1](../images/sfbcallout1.png)<br/>**Name** Enter a descriptive display name for your auto attendant. The name is required and can contain up to 64 characters, including spaces. It will be listed in the **Name** column on the **Auto attendants** tab.
***

![Nummer 2](../images/sfbcallout2.png)<br/>**Phone number** This setting is optional. If you like, select a phone number for your auto attendant. You can pick any available service toll or toll-free phone number that you have for your organization. If there are no phone numbers listed, you will need to get a service toll or toll-free phone number. Go [here](getting-service-phone-numbers.md) to get them. <br/> <br/>

> [!NOTE]
> **User (subscriber)** numbers can't be assigned to auto attendants.

***
![Nummer 3](../images/sfbcallout3.png)<br/>**Zeitzone**: Sie müssen die Zeitzone für Ihre automatische Telefonzentrale festlegen. Die Zeitzone muss jedoch nicht der Zeitzone der für Ihre Organisation angegebenen Hauptadresse entsprechen. Sie können für jede automatische Telefonzentrale eine andere Zeitzone festlegen. Die Geschäftszeiten für die automatische Telefonzentrale werden basierend auf der Zeitzone festgelegt, die Sie hier auswählen.
***
![14](../images/sfbcallout4.png)<br/>**Language** Select the language that you want to use for your auto attendant from any of the available languages listed. The language you set here is the language that the auto attendant will use to interact with people that call in to this auto attendant, and all the system prompts will be played in this language.
***
![Nummer 5](../images/sfbcallout5.png)<br/>**Speech recognition** Speech recognition is available and if this option is selected. People that call in can use voice input in the language you set. You can disable speech recognition by clearing it if you want to only let people use their phone keypad.
***
![Nummer 6](../images/sfbcallout6.png)<br/>**Operator** This is optional and doesn't need to be set for the auto attendant. However, you can set the **Operator** option for people that call in to be able to break out of the menus to speak to a person to help them. <br/> <br/> Die Taste „0" wird automatisch der Vermittlung zugewiesen. <br/> <br/> If you set this up, you will also need to tell people who call in that this is an available option in the **Edit menu options** on the **Business hours call handling** page. If you set an operator on your auto attendant, you will need to enter the corresponding prompt text in the **Callers will hear** box or change your audio file to include this option. For example, "For the Operator, press zero." <br/><br/>  Als Vermittlung können Sie Folgendes festlegen: 
*    **Person in Ihrem Unternehmen** mit einer **Telefonsystem**-Lizenz, die für Enterprise Voice aktiviert oder Anruf-Plänen in Office 365 zugeordnet ist. <br/>

        > [!Note] 
        > **Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013. Lync Server 2010 isn't supported. <br/> 

*    Eine **Anrufwarteschleife**, die Sie eingerichtet haben 
*    You can set it up so the person calling will be sent to voicemail. To do this, select **Person in your company** and set this person's calls to be forwarded directly to voicemail. 

### <a name="select-hours-of-operation-page"></a>Seite „Geschäftszeiten auswählen"

By default, business hours are set to 24 hours a day, 7 days a week, so all hours are considered business hours. All of the hours that aren't included in business hours are considered after business hours. If you select the **Custom** option and set your business hours, then a new page called **After hours call handling** will be added where you can configure the call handling for after business hours for the auto attendant.

![New auto attendant Hours of operation.](../images/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

***
![Nummer 1](../images/sfbcallout1.png)<br/>Wählen Sie die Option **Benutzerdefiniert** aus, um bestimmte Geschäftszeiten im Kalender auszuwählen. Wenn Sie **Benutzerdefiniert** auswählen, werden die Geschäftszeiten standardmäßig auf Montag bis Freitag von 9:00 Uhr bis 17:00 Uhr festgelegt.
***
![Nummer 2](../images/sfbcallout2.png)<br/>To change business hours, highlight the business hours you want to set using the calendar. The calendar allows you to select business hours in 30-minute intervals, and the business hours you select here will be set based on the time zone that you set on the **General info** page. To set up a break (a lunch break, for example), deselect or drag to deselect the time on the calendar. You can set multiple breaks within business hours. 

### <a name="select-business-hours-call-handling-page"></a>Auswählen von Geschäftszeiten aus der Seite für die Anruf-Behandlung

> [!TIP]
> Wenn Sie einen benutzerdefinierten Zeitplan für die Geschäftszeiten verwenden, müssen Sie auch die Anrufbehandlung außerhalb der Geschäftszeiten einrichten. Es wird eine Seite namens **Anrufbehandlung nach Geschäftsschluss** hinzugefügt, auf der Sie diese Optionen konfigurieren können. Dafür stehen die gleichen Optionen zur Verfügung wie für **Anrufbehandlung während der Geschäftszeiten**. 

Begrüßungen, Ansagen und Menüs können, die es Benutzern eingerichtet werden, die während der Geschäftszeiten Anruf in Ihrer Organisation Auto attendant Telefonnummer hören kann.

![Business hours call handling.](../images/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)

***
![Nummer 1](../images/sfbcallout1.png)<br/>**Company greeting** Business hours greeting is optional and can be set to **None**. In this case, the caller will hear no message or greeting before the call is handled by one of the options you select. You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.
*    **Keine:** Wenn Personen die automatische Telefonzentrale unter dieser Telefonnummer anrufen, wird keine Ansage wiedergegeben.
*    **Create a custom greeting** If you choose this option, enter the text you want the system to read (up to 1000 characters). For example, you might enter "Welcome to Contoso. Your call is important to us." in the **Callers will hear** box.
*    **Hochladen einer Audiodatei:** Wenn Sie diese Option wählen, zeichnen Sie die Begrüßung auf und laden Sie anschließend Ihre Audiodatei hoch (im wav-, .mp3- oder .wma-Format).
***
![Nummer 2](../images/sfbcallout2.png)<br/>You can select what happens to calls that arrive during business hours. You can chose from the following options:
* **Verbindung trennen:** Wenn Sie diese Option auswählen, wird die Verbindung der Anrufer nach einer Begrüßung mit Informationen zu den Geschäftszeiten getrennt.
* **Umleiten von Anrufen:** Dies kann verwendet werden, um den Anruf automatisch weiterzuleiten, an:
  * **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365. You can set it up so the person calling in can be sent to voicemail. To do this, select **Person in your company** and set this person to have their calls forwarded directly to voicemail. <br/><br/>   
    > [!Note]
    > **Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013. Lync Server 2010 is not supported. <br/><br/>

  * Eine **Warteschlange:** Die Verwendung einer Warteschlange ermöglicht, dass ein Anruf in eine bestehende Anruf-Warteschlange weitergeleitet werden kann, die Sie einrichten müssen.
  * Another **Auto attendant** You can use an existing auto attendant to create a second level of menu options containing a submenu. These are called nested auto attendants.

* **Menü-Optionen Eingabe-Aufforderung wiedergeben** Diese können auch dazu verwendet werden, damit Sie eine Eingabe-Aufforderung einrichten können, die abgespielt werden soll.
***
![Nummer 3](../images/sfbcallout3.png)<br/>**Menü-Eingabeaufforderung**: Um eine Ansage für das Hauptmenü zu erstellen, können Sie Text-zu-Sprache verwenden oder eine Audiodatei (im WAV-, MP3- oder WMA-Format) hochladen. Sie können die Ansage in das Feld **Anrufer hören** eingeben oder eine Audiodatei aufzeichnen und zum Beispiel Folgendes sagen: „Drücken oder sagen Sie ‚1' für den Vertrieb. Drücken oder sagen Sie ‚2' für den Service. Drücken oder sagen Sie ‚3' für den Kundendienst. Drücken oder sagen Sie ‚0' für die Vermittlung. Um dieses Menü erneut zu hören, drücken Sie die Sterntaste, oder sagen Sie ‚Wiederholen'." **Eine benutzerdefinierte Aufforderung erstellen**: Wenn Sie diese Option ausgewählt haben, müssen Sie den Text eingeben, der vom System vorgelesen werden soll (maximal 1.000 Zeichen). **Eine Audio-Datei hochladen**: Wenn Sie diese Option ausgewählt haben, müssen Sie die Begrüßung aufzeichnen und dann Ihre Audiodatei (im WAV-, MP3- oder WMA-Format) hochladen.
***
![Nummer 4](../images/sfbcallout4.png)<br/>**Dial by name** If you choose this option, this will enable people who call in to search for people in your organization using Directory Search. You can select which people will be listed as available or not available for Dial by Name by setting up those options on the **Dial scope** page. Any online user with a **Phone System** license, or any user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013, can be found with Dial by Name.<br/><br/>  

> [!WARNING]
> Benutzer, die lokal gehostet werden und Lync 2010 verwenden, können mit nach Namen wählen **nicht erreicht werden**.
> ***

![Nummer 5](../images/sfbcallout5.png)<br/>**Edit menu options** Menu options can be added or removed by using key buttons on the keypad. To add a menu option, press the corresponding key on the keypad. The keys in use will change in color and the corresponding row of options will appear below. To delete a menu option, simply click on the corresponding key on the keypad control to deselect this key. The key mapping row will be removed.<br/><br/>  **Tipp:** Sie müssen im Menü Ansagen Text aktualisieren oder erneut zeichnet separat beim Entfernen von Optionen, da dies automatisch für die Aufforderung zur vorhandenen Menü erfolgen wird nicht hinzugefügt.  <br/><br/>  Any menu option can be added and removed in any order, and the key mappings don't have to be continuous. It is possible, for example, to create a menu with keys 0, 1, and 3 mapped to options, while the key 2 isn't used.<br/><br/> 

> [!NOTE]
> The keys * (Repeat) and # (Back) are reserved by the system and can't be reassigned. If speech recognition is enabled, pressing * will correspond with "Repeat" and # will correspond with the "Back" voice commands.


Um Ihre Menüoptionen einzurichten, nachdem Sie die Taste(n) ausgewählt haben, müssen Sie: 
- **Enter the Name of the option** This can be up to 64 characters long, and can contain multiple words like "Customer Service" or "Operations and Grounds." If speech recognition is enabled, the name will automatically be recognized, and the person calling in will be able to either press 3, say "three," or say "Customer Service" to select the option mapped to key 3. 
- The next step is to select where the call is to be sent if the corresponding key is pressed, or the option is selected using speech recognition. The call can be sent to: 
    - **Operator** If operator is already set up, it is automatically mapped to key 0, but it can also be deleted or reassigned to a different key. If operator isn't set to any key, then the voice command "Operator" will be disabled too. 
    - A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned an Calling Plan in Office 365. You can set it up so the person calling in can be sent to voicemail. To do this, select **Person in your company** and set this person to have their calls forwarded directly to voicemail.<br/><br/> 

        > [!Note] 
        > **Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013. Lync Server 2010 is not supported. <br/><br/>

    - Eine **Warteschlange:** Die Verwendung einer Warteschlange ermöglicht, dass ein Anruf in eine bestehende Anruf-Warteschlange weitergeleitet werden kann, die Sie eingerichtet haben. 
    - **Auto Attendant** You can use an existing auto attendant to create a second level of menu options containing a submenu. These are called nested auto attendants.<br/><br/>

        > [!Note]
        > Die **Geschäftszeiten** geschachtelter automatischer Telefonzentralen (oder mit zweiter Ebene) werden ebenfalls eingesetzt, einschließlich der Anrufe, die von anderen Telefonzentralen eingehen, die eingerichtet wurden.         

### <a name="select-holidays-page"></a>Auswahl der Feiertags-Seite 

Sie können jeder automatische Telefonzentrale bis zu 20 geplante Feiertage hinzufügen.

![Einrichten von Feiertagen in der automatischen Telefonzentrale](../images/50a5ce88-7f39-4210-808a-da7ced969854.png)

***
![Nummer 1](../images/sfbcallout1.png)<br/>**Fügen Sie einen Feiertag hinzu** Geben Sie Ihrem neuen Feiertag im Feld **Name des Feiertags** einen Namen.<br/><br/> Holiday names may consist of up to 64 characters and must be unique for the same auto attendant. For example, you cannot have two holidays named "Thanksgiving" in the same auto attendant.  
***
![Nummer 2](../images/sfbcallout2.png)<br/>**Holiday Greeting** The Holiday Greeting is optional and can be set to **None**. In this case, the caller will hear no message or greeting before the call is handled by one of the options you select. You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.
*    **Keine:** Wenn Personen die automatische Telefonzentrale unter dieser Telefonnummer anrufen, wird keine Ansage wiedergegeben.
*    **Create a custom greeting** If you choose this option, enter the text you want the system to read (up to 1000 characters). For example, you might enter "Happy New Year! Our offices are currently closed." in the **Callers will hear** box.
*    **Hochladen einer Audiodatei:** Wenn Sie diese Option wählen, zeichnen Sie die Begrüßung auf und laden anschließend Ihre Audiodatei hoch (im wav-, .mp3- oder .wma-Format).  
***
![Nummer 3](../images/sfbcallout3.png)<br/>**What happens to the calls after the greeting?** You can select what happens to the calls that arrive during this holiday. You can chose from the following options:
* **Verbindung trennen** Die Verbindung des Anrufers wird getrennt, nachdem er die Feiertags-Nachricht gehört hat.
* **Umleiten von Anrufen:** Dies kann verwendet werden, um den Anruf automatisch weiterzuleiten, an:
  * A **Person in your company** with a **Phone System** license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365. You can set it up so the person calling in can be sent to voicemail. To do this, select **Person in your company**, and set this person to have their calls forwarded directly to voicemail. <br/><br/> 

    > [!Note] 
    > **Person in your company** can be an Online user or a user hosted on-premises using Skype for Business Server 2015 or Lync Server 2013. Lync Server 2010 is not supported.<br/><br/>

  * Eine **Anruf-Warteschlange** zur Weiterleitung des Anrufs an eine vorhandene Anruf-Warteschlange, die Sie eingerichtet haben.
  * Another **Auto attendant**, to create a second level of menu options containing a submenu. These are called nested auto attendants. <br/><br/>

    > [!Note]
    > Standardmäßig werden alle während eines Feiertags eingehenden Anrufe festgelegt, deren Verbindung nach der Ansage (falls vorhanden) getrennt wird, somit müssen Sie eine Umleitung angeben, wenn ein anderes Verhalten erwünscht ist.

***
![Nummer 4](../images/sfbcallout4.png)<br/>**When do you want the holiday to start and end?** Enter your holiday start date in dd/mm/yyyy format, and then select a start time, end date, and end time, as prompted in the date range table.<br/><br/>You can specify up to 10 different date ranges for a holiday. For example, you could add date ranges for New Year's Eve holidays for up to 10 years. A holiday can span multiple days.<br/><br/>Um Feiertagen zusätzliche Datumsbereiche hinzuzufügen, (zum Beispiel für das nächste Jahr), klicken Sie auf **Einen weiteren hinzufügen** und geben Sie einen neuen Satz von Start- und Enddatum des Feiertags ein.<br/><br/>Nested holidays are also supported. For example, you could nest multiple holidays within one "holiday break" time frame: 
*    **December 24 through January 3:** "Happy Holidays! Our offices are currently closed. We will reopen on January 4th."
*    **December 25:** "Merry Christmas! Our offices are currently closed. We will reopen on January 4th."
*    **January 1:** "Happy New Year! Our offices are currently closed. We will reopen on January 4th."

Nachdem Sie die automatische Telefonzentrale gespeichert haben, erscheinen Ihre Feiertage auf der Registerkarte **Feiertage**, auf der Sie die Einstellungen zu den Feiertagen bearbeiten, hinzufügen oder ändern können.

### <a name="select-dial-scope-page"></a>Seite „Wählbereich auswählen"

Auf dieser Seite können Sie die Benutzer in Ihrer Organisation aufgelistet in Ihrem Verzeichnis und bereit zur Einwahl nach Name, wenn eine Person, die Aufrufe eingefügt werden Ihrer Organisation einrichten.

![Dial scope for searching with dial by name.](../images/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

***
![Nummer 1](../images/sfbcallout1.png)<br/>Für **Einschließen** gibt es zwei Optionen:
* **All Online users** Using this option allows all of the people in your organization to be included in directory search. All Online users with a **Phone System** license, as well as users hosted on-premises using Skype for Business Server 2015 or Lync Server 2013 who have Calling Plans in Office 365, will be listed. 
* **Custom** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and the people added to this Office 365 Group, distribution list, or security group who are either **Online users with a Phone System license** or hosted on-premises using Skype for Business Server 2015 or Lync Server 2013. You can add multiple Office 365 Groups, distribution lists, and security groups. <br/><br/> 

  > [!Caution]
  > Lokale Benutzer aus der Bereitstellung von Lync Server 2010 wird nicht aufgeführt, wenn jemand das Verzeichnis mit Dial sucht nach Namen. 
***
![Nummer 2](../images/sfbcallout2.png)<br/>Verwenden die Option **ausschließen** , haben Sie zwei Optionen:
* **Keine**: Wenn Sie diese Option verwenden, werden keine Onlinebenutzer von der Verzeichnissuche ausgeschlossen.. 
* **Custom** If you use this option, you can search for an Office 365 Group, distribution list, or security group that has been created in your organization, and all people added to this Office 365 Group, distribution list, or security groups will be excluded from directory search. You can add multiple Office 365 Groups, distribution lists, and security groups. <br/><br/> 

  > [!Caution]
  > Lokale Benutzer aus der Bereitstellung von Lync Server 2010 wird nicht aufgeführt, wenn jemand das Verzeichnis mit Dial sucht nach Namen.          

> [!NOTE]
> Es kann bis zu 36 Stunden für einen neuen Benutzer haben ihre Namen in das Verzeichnis, wenn ein Benutzer Einwahl verwendet nach Namen für die Spracherkennung dauern. 

Nachdem Sie alle erforderlichen Felder eingeben und richten Sie arbeiten mit Menüs und Optionen, klicken Sie auf **Speichern**.

## <a name="editing-and-testing-auto-attendants"></a>Bearbeiten und Testen von automatischen Telefonzentralen

After you have saved your auto attendant, it will be listed on the **Auto attendants** page. This will allow you to quickly see some of the options that you have set up, including the name, phone number, language, and status.

Wenn Sie eine automatische Telefonzentrale ändern möchten, wählen Sie die automatische Telefonzentrale aus, und klicken Sie dann im Bereich Aktion auf **Bearbeiten**.

Sie können einen Testanruf an die automatische Telefonzentrale auch schnell mithilfe der Schaltfläche **Testen** im Aktionsbereich platzieren.

## <a name="want-to-know-more"></a>Möchten Sie mehr wissen?

Sie können auch Windows PowerShell verwenden, um automatische Telefonzentralen zu erstellen und einzurichten.

### <a name="auto-attendant-cmdlets"></a>Cmdlets für automatische Telefonzentralen

Zum Verwalten einer automatischen Telefonzentrale benötigen Sie die folgenden Cmdlets.


|                                                                                                                                                               |                                                                                                                                                               |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                   [New-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796493.aspx)                                    |                                [New-CsOrganizationalAutoAttendantPrompt](https://technet.microsoft.com/library/mt796484.aspx)                                 |
|                                   [Set-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796486.aspx)                                    |                              [New-CsOrganizationalAutoAttendantMenuOption](https://technet.microsoft.com/library/mt796485.aspx)                               |
|                                   [Get-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796482.aspx)                                    |    [Get-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csorganizationalautoattendantholidays?view=skype-ps)    |
|                                  [Remove-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796492.aspx)                                  |                                 [New-CsOrganizationalAutoAttendantMenu](https://technet.microsoft.com/library/mt796488.aspx)                                  |
|                                         [New- CsOnlineAudioFile](https://technet.microsoft.com/library/mt796479.aspx)                                         |                               [New-CsOrganizationalAutoAttendantCallFlow](https://technet.microsoft.com/library/mt796489.aspx)                                |
| [Export-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps) |                                         [New-CsOnlineTimeRange](https://technet.microsoft.com/library/mt796491.aspx)                                          |
|                    [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)                    |                                          [New-CsOnlineSchedule](https://technet.microsoft.com/library/mt796490.aspx)                                          |
|                           [Get-CsOrganizationalAutoAttendantSupportedTimeZone](https://technet.microsoft.com/library/mt796483.aspx)                           |                        [New-CsOrganizationalAutoAttendantCallHandlingAssociation](https://technet.microsoft.com/library/mt796487.aspx)                        |
|                           [Get-CsOrganizationalAutoAttendantSupportedLanguage](https://technet.microsoft.com/library/mt796481.aspx)                           | [Import-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csorganizationalautoattendantholidays?view=skype-ps) |
|                            [New-CsOrganizationalAutoAttendantCallableEntity](https://technet.microsoft.com/library/mt796480.aspx)                             |                                                                                                                                                               |

### <a name="more-about-windows-powershell"></a>Weitere Informationen zu Windows PowerShell

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:

  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:

  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>See Also
[Das bekommen Sie mit Telefonsystem in Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Anfordern von Servicenummern für Skype for Business und Microsoft Teams](getting-service-phone-numbers.md)

[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[Was sind automatische Telefonzentralen für das Telefonsystem?](/MicrosoftTeams/what-are-phone-system-auto-attendants.md)

[Beispiel für Small Business - richten Sie eine automatische Telefonzentrale](tutorial-org-aa.yml)  
