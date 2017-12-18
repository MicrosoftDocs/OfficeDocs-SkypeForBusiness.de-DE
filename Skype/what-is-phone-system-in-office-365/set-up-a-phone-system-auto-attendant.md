---
title: "Einrichten einer automatischen Telefonzentrale für Telefonsystem"
ms.author: tonysmit
author: tonysmit
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c

description: "Learn how to set up and test Phone System (Cloud PBX) auto attendents for efficient call handling for your organization. "
---

# Einrichten einer automatischen Telefonzentrale für Telefonsystem

> [!IMPORTANT]
> Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den [Haftungsausschluss](6fc2687c-0abf-43b8-aa54-7c3b2a84b67c.md#MT_Footer).  
  
Automatische Telefonzentralen sind sehr nützlich und ermöglichen Personen, die Ihre Organisation anrufen, die Navigation in einem Menüsystem. Dort können sie die richtige Abteilung, die Anrufwarteschleife, eine Person oder die Vermittlung erreichen. Sie können im Skype for Business Admin Center eine automatische Telefonzentrale für Ihre Organisation erstellen. Um eine neue automatische Telefonzentrale zu erstellen, navigieren Sie auf der linken Seite zu **Anrufweiterleitung** und wählen dann **Automatische Telefonzentralen** > **Neu hinzufügen** aus.
  
Wenn Sie weitere Informationen zur automatischen Telefonzentralen möchten, finden Sie unter [Was sind Telefonsystem Telefonzentralen?](what-are-phone-system-auto-attendants.md).
  
## Schritt 1 - Erste Schritte

- Bevor Sie Ihre automatischen Telefonzentralen erstellen und einrichten können, müssen Sie sich gebührenpflichtige oder gebührenfreie Servicenummern besorgen oder entsprechende vorhandene Nummern übertragen. Wenn Sie die gebührenpflichtigen oder gebührenfreien Servicenummern haben, werden diese auf der Registerkarte **Skype for Business Admin Center** > **VoIP** > **Telefonnummern** angezeigt, und als **Nummerntyp** ist **Service - gebührenfrei** angegeben. Wie Sie Ihre Servicenummern erhalten, erfahren Sie unter[Abrufen von Skype for Business-Leistungsnummern](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md). Wenn Sie eine vorhandene Servicenummer übertragen möchten, lesen Sie [Übertragen von Telefonnummern zu Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md). Nummern von **Benutzern (Abonnenten)** können nicht zu automatischen Telefonzentralen zugewiesen werden. Wenn Sie sich außerhalb der USA befinden, können Sie Servicenummern nicht über das Skype for Business Admin Center beziehen. Lesen Sie stattdessen[Verwalten von Telefonnummern für Ihre Organisation](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) nach, wie Sie außerhalb der USA vorgehen müssen.
    
    > [!CAUTION]
    > Zum Abrufen und gebührenfreie Telefonnummern verwenden, müssen Sie Kommunikation Gutschriften einrichten. Hierzu finden Sie [Was ist Guthaben für Kommunikationen?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md) und[Einrichten von Guthaben für Kommunikationen für Ihre Organisation](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md). 
  
- Ihre Organisation muss eine Lizenz für Enterprise E3 plus **Telefonsystem** oder eine Lizenz für Enterprise E5 (mindestens) verfügen. Die Anzahl der **Telefonsystem** Benutzerlizenzen, die zugewiesen werden Nachteile, dass die Anzahl der Dienst, die Zahlen stehen für Telefonzentralen verwendet werden soll. Die Nummern der automatischen Telefonzentralen, die Sie haben, können, hängt von der Zahlen **Telefonsystem** und **Audio Konferenzen** Lizenzen, die in Ihrer Organisation zugewiesen werden. Weitere Informationen zur Lizenzierung, wechseln Sie[Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!TIP]
    > Um umzuleiten Anrufe an einen Operator oder eine Menüoption, die eine Online-Benutzer mit einer Lizenz **Telefonsystem** ist, müssen Sie für Enterprise-VoIP zu aktivieren oder zu zuweisen in Office 365-Pläne aufrufen. Finden Sie unter[Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Sie können auch Windows PowerShell verwenden. Führen Sie zum Beispiel:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
## Schritt 2 - Erstellen einer neuen automatischen Telefonzentrale

Klicken Sie im **Skype for Business Admin Center** auf **Anrufweiterleitung** > **Automatische Telefonzentralen** und dann auf **Neu hinzufügen**:
  
### Seite „Allgemeine Informationen bearbeiten"

Geben Sie auf der allgemeinen Infoseite „Bearbeiten" Folgendes ein bzw. treffen Sie die gewünschte Auswahl:
  
![New auto attendant page 1.](../images/edacec94-9384-4a87-be0a-5c49a151287e.png)
  
|||
|:-----|:-----|
|**1** <br/> |**Name**: Geben Sie einen aussagekräftigen Anzeigenamen für Ihre automatische Telefonzentrale ein. Der Name ist erforderlich und kann maximal 64 Zeichen einschließlich Leerzeichen enthalten. Er wird in der Spalte **Name** der Registerkarte **Automatische Telefonzentralen** aufgeführt. <br/> |
|**2** <br/> |**Rufnummer** Diese Einstellung ist optional. Wenn Sie möchten, wählen Sie eine Rufnummer ein, für der automatischen Telefonzentrale. Sie können auswählen, alle verfügbaren Service weder eine gebührenpflichtige oder gebührenfreie Rufnummer, die Sie für Ihre Organisation aufweisen. Wenn keine Telefonnummern aufgeführt sind, müssen Sie zum Abrufen eines Service weder eine gebührenpflichtige oder Telefon gebührenfreie Nummer. Wechseln Sie[Abrufen von Skype for Business-Leistungsnummern](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) werden können. <br/> > [!NOTE]> Nummern von **Benutzern (Abonnenten)** können nicht zu automatischen Telefonzentralen zugewiesen werden.          |
|**3** <br/> |**Zeitzone**: Sie müssen die Zeitzone für Ihre automatische Telefonzentrale festlegen. Die Zeitzone muss jedoch nicht der Zeitzone der für Ihre Organisation angegebenen Hauptadresse entsprechen. Sie können für jede automatische Telefonzentrale eine andere Zeitzone festlegen. Die Geschäftszeiten für die automatische Telefonzentrale werden basierend auf der Zeitzone festgelegt, die Sie hier auswählen.  <br/> |
|**4** <br/> |**Sprache**: Wählen Sie unter den aufgeführten verfügbaren Sprachen die Sprache aus, die Sie für die automatische Telefonzentrale verwenden möchten. Die hier festgelegte Sprache wird von der automatischen Telefonzentrale für Interaktionen mit Anrufern verwendet, und in dieser Sprache werden auch alle Systemansagen wiedergegeben.  <br/> |
|**5** <br/> |**Spracherkennung**: Spracherkennung ist verfügbar, und wenn diese Option aktiviert ist, können Anrufer Spracheingabe in der von Ihnen festgelegten Sprache verwenden. Wenn die Anrufer nur die Wähltastatur ihres Telefons verwenden sollen, können Sie die Spracherkennung deaktivieren, indem Sie die Option deaktivieren.  <br/> |
|**6** <br/> |**Operator**: Diese Einstellung ist optional und muss für die automatische Telefonzentrale nicht festgelegt werden. Sie können die Option **Operator** jedoch festlegen, damit Anrufer die Menüs verlassen können, um mit einer Person zu sprechen und um Hilfe zu bitten. <br/>  Die Taste „0" wird automatisch der Vermittlung zugewiesen. <br/>  Wenn Sie diese Funktion einrichten, müssen Sie die Anrufer unter **Menüoptionen bearbeiten** auf der Seite **Anrufbehandlung während der Geschäftszeiten** darauf hinweisen, dass diese Option verfügbar ist. Wenn Sie für Ihre automatische Telefonzentrale eine Vermittlung festlegen, müssen Sie den entsprechenden Ansagetext in das Feld **Anrufer hören** eingeben oder Ihre Audiodatei ändern, um diese Option aufzunehmen. Beispiel: „Drücken Sie ‚0', um mit der Vermittlung zu sprechen". <br/>  Als Vermittlung können Sie Folgendes festlegen: <br/>  Eine **Person in Ihrem Unternehmen** mit einer **Telefonsystem** Lizenz, die für Enterprise-VoIP aktiviert ist, oder in Office 365-Pläne aufrufen zugewiesen. <br/> > [!NOTE]> **Person in Ihrem Unternehmen** kann es sich um eine Online-Benutzer oder ein Benutzer gehostet lokal verwenden von Skype für Business Server 2015 und Lync Server 2013. Lync Server 2010 wird nicht unterstützt.           Eine **Anrufwarteschleife**, die Sie eingerichtet haben  <br/>  Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Dazu wählen Sie eine **Person in Ihrem Unternehmen** aus und legen die Anrufe dieser Person so fest, dass sie direkt an die Voicemail weitergeleitet werden. <br/> |
   
### Seite „Geschäftszeiten auswählen"

Standardmäßig sind die Geschäftszeiten auf 24 Stunden und sieben Tage in der Woche festgelegt. Das heißt, alle Zeiten gelten als Geschäftszeiten. Alle Zeiten, die nicht in den Geschäftszeiten enthalten sind, gelten als außerhalb der Geschäftszeiten liegend. Wenn Sie die Option **Benutzerdefiniert** auswählen und Ihre Geschäftszeiten festlegen, wird eine neue Seite namens **Anrufbehandlung nach Geschäftsschluss** hinzugefügt, und Sie müssen die Anrufbehandlung nach Geschäftsschluss für die automatische Telefonzentrale festlegen.
  
![New auto attendant Hours of operation.](../images/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)
  
|||
|:-----|:-----|
|**1** <br/> |Wählen Sie die Option **Benutzerdefiniert** aus, um bestimmte Geschäftszeiten im Kalender auszuwählen. Wenn Sie **Benutzerdefiniert** auswählen, werden die Geschäftszeiten standardmäßig auf Montag bis Freitag von 9:00 Uhr bis 17:00 Uhr festgelegt. <br/> |
|**2** <br/> |Um die Geschäftszeiten zu ändern, wählen Sie mithilfe des Kalenders die Geschäftszeiten aus, die Sie festlegen möchten. Im Kalender können Sie die Geschäftszeiten in 30-Minuten-Intervallen auswählen, und die hier ausgewählten Geschäftszeiten werden basierend auf der Zeitzone festgelegt, die Sie auf der Seite **Allgemeine Informationen** festgelegt haben. Um eine Pause (z. B. eine Mittagspause) einzurichten, heben Sie die Auswahl der entsprechenden Zeit im Kalender auf, oder ziehen Sie, um die Auswahl der Zeit aufzuheben. Sie können auch mehrere Pausen innerhalb der Geschäftszeiten festlegen. <br/> |
   
### Behandeln von Seite Select Geschäftszeiten-Anruf

> [!TIP]
> Wenn Sie einen benutzerdefinierten Zeitplan für die Geschäftszeiten verwenden, müssen Sie auch die Anrufbehandlung außerhalb der Geschäftszeiten einrichten. Es wird eine Seite namens **Anrufbehandlung nach Geschäftsschluss** hinzugefügt, auf der Sie diese Optionen konfigurieren können. Dafür stehen die gleichen Optionen zur Verfügung wie für **Anrufbehandlung während der Geschäftszeiten**. 
  
Sie können Grüßen, Menüs und Anweisungen für Personen einrichten, die in Ihrer Organisation automatische Telefonzentrale Rufnummer anrufen üblichen Geschäftszeiten hören werden.
  
![Business hours call handling.](../images/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
  
|||
|:-----|:-----|
|**1**|**Unternehmensbegrüßung**: Die Begrüßung während der Geschäftszeiten ist optional und kann auf **Keine** festgelegt werden. In diesem Fall hören die Anrufer keine Nachricht oder Begrüßung, bevor der Anruf durch eine der von Ihnen ausgewählten Optionen behandelt wird. Sie können auch eine Audiodatei (im WAV-, MP3- oder WMA-Format) hochladen oder mit Text-zu-Sprache eine benutzerdefinierte Begrüßung erstellen. **Keine** Keine Begrüßung wird wiedergegeben, wenn Personen die automatische Telefonzentrale Rufnummer anrufen. **Erstellen eines benutzerdefinierten Grußzeile** Wenn Sie diese Option auswählen, geben Sie den Text (bis zu 1000 Zeichen) gelesen werden soll. Beispielsweise könnten Sie eingeben "Willkommen bei Contoso. Ihr Anruf ist uns wichtig."im Feld **Anrufer zu hören**. **Hochladen einer Audiodatei** Wenn Sie diese Option wählen, zeichnen Sie die Ansage auf, und Laden Sie die Audiodatei (im Format WAV, MP3 oder WMA).|
|**2**| Sie können auswählen, was passiert, Anrufe, die während der üblichen Geschäftszeiten eintreffen. Sie können aus den folgenden Optionen auswählen: **Trennen**: Wenn Sie diese Option auswählen, hören die Anrufer die Begrüßung für die Geschäftszeiten und werden dann getrennt. **Anruf umleiten**: Diese Option können Sie verwenden, um den Anruf automatisch an folgende Ziele zu senden: **Person, die in Ihrem Unternehmen** mit einer **Telefonsystem** Lizenz, die für Enterprise-VoIP aktiviert ist, oder in Office 365-Pläne aufrufen zugewiesen. Sie können es einrichten, sodass die Person, die Aufrufen an die Voicemail gesendet werden kann. Dazu wählen Sie **die Person in Ihrem Unternehmen** aus, und legen Sie diese Person ihre Anrufe direkt an die Voicemail weitergeleitet haben.> [!NOTE]> **Person in Ihrem Unternehmen** kann es sich um eine Online-Benutzer oder ein Benutzer gehostet lokal verwenden von Skype für Business Server 2015 und Lync Server 2013. Lync Server 2010 wird nicht unterstützt.          **Anrufwarteschleife**: Mithilfe einer Anrufwarteschleife können Sie den Anruf an eine vorhandene Anrufwarteschleife durchstellen, die Sie eingerichtet haben.  Eine andere **automatische Telefonzentrale** Sie können eine vorhandene automatische Telefonzentrale verwenden, um eine zweite Ebene mit Menüoptionen zu erstellen, die ein Untermenü enthält. Diese Telefonzentrale wird als „geschachtelte" automatische Telefonzentrale bezeichnet. **Optionsanzeige Wiedergabemenü**: Hier können Sie eine Ansage einrichten, die wiedergegeben werden soll. |
|**3**|**Menü-Eingabeaufforderung**: Um eine Ansage für das Hauptmenü zu erstellen, können Sie Text-zu-Sprache verwenden oder eine Audiodatei (im WAV-, MP3- oder WMA-Format) hochladen. Sie können die Ansage in das Feld **Anrufer hören** eingeben oder eine Audiodatei aufzeichnen und zum Beispiel Folgendes sagen: „Drücken oder sagen Sie ‚1' für den Vertrieb. Drücken oder sagen Sie ‚2' für den Service. Drücken oder sagen Sie ‚3' für den Kundendienst. Drücken oder sagen Sie ‚0' für die Vermittlung. Um dieses Menü erneut zu hören, drücken Sie die Sterntaste, oder sagen Sie ‚Wiederholen'." **Eine benutzerdefinierte Aufforderung erstellen**: Wenn Sie diese Option ausgewählt haben, müssen Sie den Text eingeben, der vom System vorgelesen werden soll (maximal 1.000 Zeichen). **Eine Audio-Datei hochladen**: Wenn Sie diese Option ausgewählt haben, müssen Sie die Begrüßung aufzeichnen und dann Ihre Audiodatei (im WAV-, MP3- oder WMA-Format) hochladen. |
|**4**|**Wählen Sie anhand des Namens** Wenn Sie diese Option auswählen, wird diese Personen aktivieren, die so suchen Sie nach Personen in Ihrer Organisation mithilfe der Suchfunktion Directory einwählen. Sie können auswählen, welche Personen als verfügbar oder nicht verfügbar für Einwahlnummern namentlich aufgeführt werden, indem Sie diese Optionen auf der Seite **Einwählen Umfang** einrichten. Jeder online-Benutzer mit einer Lizenz **Telefonsystem** oder ein beliebiger Benutzer gehostet lokal verwenden von Skype für Business Server 2015 und Lync Server 2013 finden Sie über DFÜ anhand des Namens.> [!CAUTION]> Benutzer gehostet lokale Einwahlnummern namentlich mit Lync 2010 **nicht erreicht werden kann**.          |
|**5**|**Menüoptionen bearbeiten**: Sie können Menüoptionen mithilfe von Tasten der Wähltastatur hinzufügen oder entfernen. Um eine Menüoption hinzuzufügen, drücken Sie die entsprechende Taste der Wähltastatur. Die Farbe der verwendeten Tasten ändert sich, und die entsprechende Zeile mit Optionen wird darunter angezeigt. Um eine Menüoption zu löschen, klicken Sie einfach auf die entsprechende Taste des Wähltastatur-Steuerelements, um die Auswahl dieser Taste aufzuheben. Die Zeile für die Tastenzuordnung wird daraufhin entfernt.> [!TIP]> Wenn Sie Optionen hinzufügen oder entfernen, müssen Sie separat den Text der Menüansagen aktualisieren oder die Audiodatei erneut aufzeichnen, da dies für die vorhandene Menüansage nicht automatisch geschieht.           Sie können beliebige Menüoptionen in beliebiger Reihenfolge hinzufügen und entfernen. Außerdem müssen die Tastaturzuordnungen nicht fortlaufend sein. Sie können beispielsweise ein Menü mit den Tasten „0", „1" und „3" zu Optionen zuordnen und die Taste „2" nicht verwenden.> [!NOTE]> Die Tasten „*" (Wiederholen) und „#" (Zurück) sind für das System reserviert und können nicht neu zugewiesen werden. Wenn die Spracherkennung aktiviert ist, entspricht das Drücken von „*" dem Sprachbefehl „Wiederholen", und „#" entspricht „Zurück".           |
|| Um nach der Auswahl der Tasten die Menüoptionen einzurichten, müssen Sie so vorgehen: **Geben Sie den Namen der Option ein.** Der Name kann aus maximal 64 Zeichen bestehen und kann mehrere Wörter wie „Kundendienst" oder „Betrieb und Anlagen" enthalten. Wenn die Spracherkennung aktiviert ist, wird der Name automatisch erkannt, und die Anrufer können „3" drücken, „drei" sagen oder „Kundendienst" sagen, um die Option auszuwählen, die der Taste „3" zugeordnet ist. Im nächsten Schritt wählen Sie aus, wohin der Anruf gesendet werden soll, wenn die entsprechende Taste gedrückt wird oder die Option mithilfe der Spracherkennung ausgewählt wird. Der Anruf kann an folgende Ziele gesendet werden: **Vermittlung**: Wenn die Vermittlung bereits eingerichtet ist, wird sie automatisch der Taste „0" zugeordnet. Sie kann jedoch auch gelöscht oder einer anderen Taste zugewiesen werden. Wenn die Vermittlung keiner Taste zugeordnet ist, ist auch der Sprachbefehl „Vermittlung" deaktiviert.  Eine **Person in Ihrem Unternehmen** mit einer **Telefonsystem** Lizenz, die für Enterprise-VoIP aktiviert ist, oder eine aufrufen planen in Office 365 zugewiesen. Sie können es einrichten, sodass die Person, die Aufrufen an die Voicemail gesendet werden kann. Dazu wählen Sie **die Person in Ihrem Unternehmen** aus, und legen Sie diese Person ihre Anrufe direkt an die Voicemail weitergeleitet haben.> [!NOTE]> **Person in Ihrem Unternehmen** kann es sich um eine Online-Benutzer oder ein Benutzer gehostet lokal verwenden von Skype für Business Server 2015 und Lync Server 2013. Lync Server 2010 wird nicht unterstützt.          **Anrufwarteschleife**: Mithilfe einer Anrufwarteschleifenoption können Sie den Anruf an eine vorhandene Anrufwarteschleife durchstellen, die Sie eingerichtet haben. **Automatische Telefonzentrale**: Sie können eine vorhandene automatische Telefonzentrale verwenden, um eine zweite Ebene mit Menüoptionen zu erstellen, die ein Untermenü enthält. Diese Telefonzentrale wird als „geschachtelte automatische Telefonzentrale" bezeichnet. > [!NOTE]>  Die **Geschäftszeiten** von geschachtelten automatischen Telefonzentralen (oder automatischen Telefonzentralen der zweiten Ebene) werden auch für die Anrufe verwendet, die von einer anderen eingerichteten automatischen Telefonzentrale gesendet werden.          |
   
### Wählen Sie Feiertage Seite (Vorschau nur für Kunden verfügbar)

Sie können jede automatische Telefonzentrale bis zu 20 geplanten Feiertage hinzufügen.
  
![Setting up Holidays in auto attendant](../images/50a5ce88-7f39-4210-808a-da7ced969854.png)
  
|||
|:-----|:-----|
|**1**|**Fügen Sie einen Feiertag hinzu.** Geben Sie einen Namen für Ihre neue "Feiertag" im Feld **Name des Feiertags**.Namen Feiertage können bis zu 64 Zeichen bestehen und für die gleichen automatische Telefonzentrale eindeutig sein. Angenommen, Sie zwei Feiertage mit dem Namen "Erntedankfest" in der gleichen automatische Telefonzentrale nicht möglich.|
|**2**|**Feiertag Grußzeile** Der Feiertag Grußzeile ist optional und kann auf **keine** festgelegt werden. In diesem Fall wird der Anrufer hören keine Nachricht oder Begrüßung vor der Anruf durch eine der Optionen behandelt wird, die Sie auswählen. Sie können auch Hochladen einer Audiodatei (in den Formaten WAV, MP3- oder WMA), oder erstellen einen benutzerdefinierten Gruß Sprachausgabe verwenden. **Keine** Keine Begrüßung wird wiedergegeben, wenn Personen die automatische Telefonzentrale Rufnummer anrufen. **Erstellen eines benutzerdefinierten Grußzeile** Wenn Sie diese Option auswählen, geben Sie den Text (bis zu 1000 Zeichen) gelesen werden soll. Sie können beispielsweise "Herzlichen Glückwunsch zum Neujahr! eingeben Unserer Büros sind derzeit in das Feld **Anrufer zu hören** geschlossen.". **Hochladen einer Audiodatei** Wenn Sie diese Option wählen, zeichnen Sie die Weihnachtskarte auf, und Laden Sie die Audiodatei (im Format WAV, MP3 oder WMA).|
|**3**|**Was Anrufe geschieht, nachdem die Begrüßung?** Sie können auswählen, was passiert, um Anrufe, die während dieses Feiertag eintreffen. Sie können aus den folgenden Optionen auswählen: **Trennen** Die Person, die Einwahl wird nach der Weihnachtskarte hören getrennt. **Anruf umleiten**: Diese Option können Sie verwenden, um den Anruf automatisch an folgende Ziele zu senden:  Eine **Person in Ihrem Unternehmen** mit einer **Telefonsystem** Lizenz, die für Enterprise-VoIP aktiviert ist, oder in Office 365-Pläne aufrufen zugewiesen. Sie können es einrichten, sodass die Person, die Aufrufen an die Voicemail gesendet werden kann. Hierzu wählen Sie **die Person in Ihrem Unternehmen** aus, und legen Sie diese Person ihre Anrufe direkt an die Voicemail weitergeleitet haben.> [!NOTE]> **Person in Ihrem Unternehmen** kann es sich um eine Online-Benutzer oder ein Benutzer gehostet lokal verwenden von Skype für Business Server 2015 und Lync Server 2013. Lync Server 2010 wird nicht unterstützt.           Eine **Warteschlange aufrufen,** um den Anruf an eine vorhandene anrufen Warteschlange weiterleiten, die Sie eingerichtet haben Eine andere **automatische Telefonzentrale**, um eine zweite Ebene der Menüoptionen, enthält ein Untermenü zu erstellen. Diese werden geschachtelte Telefonzentralen bezeichnet. > [!NOTE]>  Standardmäßig werden alle während eines Zeitraums Feiertag eingehenden Anrufe festgelegt, nach der Ansage (falls vorhanden), trennen, damit Sie eine Umleitung angeben müssen, wenn ein anderes Verhalten gewünscht wird.          |
|**4**|**Wenn Sie das "Feiertag" zum Starten und beenden möchten?** Geben Sie den Anfangstermin "Feiertag" im Format mm/tt/jjjj, und wählen Sie dann eine Startzeit, Enddatum und Endzeit, wie in den Bereich Datumstabelle dazu aufgefordert werden.Sie können bis zu 10 verschiedenen Datumsbereiche für einen Feiertag angeben. Beispielsweise könnten Sie Datumsbereiche für Silvester Feiertage für bis zu 10 Jahre hinzufügen. Ein Feiertag kann mehrere Tage umfassen.Weitere hinzufügen "Feiertag" Datum Bereiche (zum Beispiel für das nächste Jahr), klicken Sie auf **ein anderes hinzufügen**, und geben Sie einen neuen Satz von Anfangs- und Endtermine für die Weihnachtsfeiertage.Geschachtelte Feiertage werden ebenfalls unterstützt. Beispielsweise könnten Sie mehrere Feiertage in einem "" Feiertag "Seitenumbruch" zeitlichen Rahmen schachteln: **· Dezember 24 bis Januar 3:** "schöne Feiertage! Unserer Niederlassung sind derzeit geschlossen. Wir werden auf 4. Januar erneut geöffnet werden." **· Dezember 25:** "Fröhliche Weihnachten! Unserer Niederlassung sind derzeit geschlossen. Wir werden auf 4. Januar erneut geöffnet werden." **· Januar 1:** "Herzlichen Glückwunsch zum Neujahr! Unserer Niederlassung sind derzeit geschlossen. Wir werden auf 4. Januar erneut geöffnet werden."|
   
Nachdem Sie Ihre automatische Telefonzentrale gespeichert haben, werden Ihre Feiertage auf der Registerkarte **Feiertage**, wo Sie bearbeiten, hinzufügen oder Ändern von Einstellungen für "Feiertag" angezeigt.
  
### Seite „Wählbereich auswählen"

Auf dieser Seite können Sie einrichten, welche Benutzer in Ihrer Organisation im Verzeichnis aufgeführt werden und für die Namensanwahl verfügbar sein sollen, wenn jemand bei der Organisation anruft.
  
![Dial scope for searching with dial by name.](../images/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)
  
|||
|:-----|:-----|
|**1** <br/> | Für **Einschließen** gibt es zwei Optionen: <br/> **Alle Online-Benutzer** Mit dieser Option kann alle Personen in Ihrer Organisation, in dem Verzeichnis durchsuchen aufgenommen werden sollen. Alle Online-Benutzer mit einer Lizenz **Telefonsystem** als auch Benutzer gehostet lokal verwenden von Skype für Business Server 2015 und Lync Server 2013, Pläne aufrufen, die in Office 365 haben werden aufgelistet. <br/> **Benutzerdefinierte** Wenn Sie diese Option verwenden, können Sie nach einer Gruppe von Office 365, Verteilerliste oder Sicherheitsgruppe, die in Ihrer Organisation erstellt wurde suchen und Personen hinzugefügt in Office 365-Gruppe, Verteilerliste oder Sicherheitsgruppe, die entweder **sind Online-Benutzer mit einer Telefon-Lizenz** oder gehostete lokal verwenden Skype für Business Server 2015 oder Lync Server 2013 in Suchfunktion für das enthalten sein sollen. Sie können mehrere Office 365-Gruppen, Verteilerlisten und Sicherheitsgruppen hinzufügen. <br/> > [!CAUTION]>  Lokale Bereitstellungen von Lync Server 2010 Benutzer wird nicht aufgeführt, wenn ein Benutzer mit eingehenden Verbindungen Verzeichnis durchsucht anhand des Namens.          |
|**2** <br/> | Für **Ausschließen** gibt es zwei Optionen: <br/> **Keine**: Wenn Sie diese Option verwenden, werden keine Onlinebenutzer von der Verzeichnissuche ausgeschlossen..  <br/> **Benutzerdefinierte** Wenn Sie diese Option verwenden, können Sie nach einer Office 365-Gruppe suchen, Liste oder Sicherheit Verteilergruppe, die in Ihrer Organisation und alle Personen erstellt wurde hinzugefügt in Office 365 Gruppe Verzeichnis durchsuchen Verteilergruppen Liste oder Sicherheit ausgeschlossen werden müssen. Sie können mehrere Office 365-Gruppen, Verteilerlisten und Sicherheitsgruppen hinzufügen. <br/> > [!CAUTION]>  Lokale Bereitstellungen von Skype für Business 2015 oder Lync Server 2013 und 2010 Benutzer wird nicht aufgeführt, wenn ein Benutzer mit eingehenden Verbindungen Verzeichnis durchsucht anhand des Namens.          |
   
> [!NOTE]
> Es kann bis zu 36 Stunden dauern, bis der Name eines neuen Benutzer im Verzeichnis aufgelistet wird, wenn jemand die Namensanwahl mit Spracherkennung verwendet. 
  
Wenn Sie alle erforderlichen Felder ausgefüllt und die Einstellungen in den Menüs und Optionen für die Anrufbehandlung vorgenommen haben, klicken Sie auf **Speichern**.
  
## Bearbeiten und Testen einer automatischen Telefonzentrale

Wenn Sie Ihre automatische Telefonzentrale gespeichert haben, wird diese auf der Seite **Automatische Telefonzentralen** aufgeführt. Auf diese Weise sehen Sie schnell einige der Optionen, die Sie eingerichtet haben, unter anderem den Namen, die Telefonnummer, die Sprache und den Status.
  
Wenn Sie Änderungen an einer automatischen Telefonzentrale vornehmen möchten, klicken Sie auf die automatische Telefonzentrale, um sie zu markieren, und klicken Sie dann im Seitenbereich auf **Bearbeiten**.
  
Sie können auch schnell einen Testanruf an die automatische Telefonzentrale tätigen, indem Sie im Seitenbereich die Schaltfläche **Test** verwenden.
  
## Möchten Sie mehr wissen?

Sie können auch Windows PowerShell verwenden, um automatische Telefonzentralen zu erstellen und einzurichten.
  
### Cmdlets für automatische Telefonzentralen

Zum Verwalten einer automatischen Telefonzentrale benötigen Sie die folgenden Cmdlets.
  
||||
|:-----|:-----|:-----|
|[New-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796493.aspx) <br/> |[Get-CsOrganizationalAutoAttendantSupportedTimeZone]( https://technet.microsoft.com/en-us/library/mt796483.aspx) <br/> |[New-CsOrganizationalAutoAttendantMenu](https://technet.microsoft.com/en-us/library/mt796488.aspx ) <br/> |
|[Set-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796486.aspx) <br/> |[Get-CsOrganizationalAutoAttendantSupportedLanguage](https://technet.microsoft.com/en-us/library/mt796481.aspx) <br/> |[New-CsOrganizationalAutoAttendantCallFlow](https://technet.microsoft.com/en-us/library/mt796489.aspx) <br/> |
|[Get-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796482.aspx ) <br/> |[New-CsOrganizationalAutoAttendantCallableEntity](https://technet.microsoft.com/en-us/library/mt796480.aspx) <br/> |[New-CsOnlineTimeRange](https://technet.microsoft.com/en-us/library/mt796491.aspx ) <br/> |
|[Remove-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796492.aspx) <br/> |[New-CsOrganizationalAutoAttendantPrompt](https://technet.microsoft.com/en-us/library/mt796484.aspx ) <br/> |[New-CsOnlineSchedule](https://technet.microsoft.com/en-us/library/mt796490.aspx) <br/> |
|[New- CsOnlineAudioFile](https://technet.microsoft.com/en-us/library/mt796479.aspx) <br/> |[New-CsOrganizationalAutoAttendantMenuOption](https://technet.microsoft.com/en-us/library/mt796485.aspx ) <br/> |[New-CsOrganizationalAutoAttendantCallHandlingAssociation](https://technet.microsoft.com/en-us/library/mt796487.aspx ) <br/> |
|[Export-CsOrganizationalAutoAttendantHolidays (nur Vorschau für Kunden)](https://docs.microsoft.com/en-us/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps) <br/> |[Get-CsOrganizationalAutoAttendantHolidays (nur Vorschau für Kunden)](https://docs.microsoft.com/en-us/powershell/module/skype/get-csorganizationalautoattendantholidays?view=skype-ps) <br/> |[Import-CsOrganizationalAutoAttendantHolidays (nur Vorschau für Kunden)](https://docs.microsoft.com/en-us/powershell/module/skype/import-csorganizationalautoattendantholidays?view=skype-ps) <br/> |
|[Neu-CsOnlineDateTimeRange (nur Vorschau für Kunden)](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps) <br/> |||
   
### Weitere Informationen zu Windows PowerShell

- In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sechs Gründe für die Verwendung von Windows PowerShell zum Verwalten von Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell zum Ausführen häufiger Skype for Business Online-Verwaltungsaufgaben](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Haftungsausschluss für maschinelle Übersetzungen**: Dieser Artikel wurde mithilfe eines Computersystems und ohne jegliche Bearbeitung durch Personen übersetzt. Microsoft bietet solche maschinellen Übersetzungen als Hilfestellung für Benutzer ohne Englischkenntnisse an, damit Sie von den Informationen zu Produkten, Diensten und Technologien von Microsoft profitieren können. Da es sich bei diesem Artikel um eine maschinelle Übersetzung handelt, enthält er möglicherweise Fehler in Bezug auf (Fach-)Terminologie, Syntax und/oder Grammatik. 
  

