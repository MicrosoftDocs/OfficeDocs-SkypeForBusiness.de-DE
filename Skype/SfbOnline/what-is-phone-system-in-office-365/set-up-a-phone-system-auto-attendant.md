---
title: Einrichten einer automatischen Telefonzentrale für das Telefonsystem
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: 'Erfahren Sie wie Sie ein Telefonsystem (Cloud PBX) mit automatischer Telefonzentrale für die effiziente Anruf-Verwaltung in Ihrem Unternehmen einrichten und testen. '
ms.openlocfilehash: fb35e36e7d59a3d47584fd15e592f68dd3ac4ae5
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780463"
---
# <a name="set-up-a-phone-system-auto-attendant"></a>Einrichten einer automatischen Telefonzentrale für das Telefonsystem

Automatische Telefonzentralen sind sehr nützlich und ermöglichen Personen, die Ihr Unternehmen anrufen, die Navigation in einem Menüsystem. Dort können sie die richtige Abteilung, die Anrufwarteschleife, eine Person oder die Vermittlung erreichen. Im Skype for Business Admin Center können Sie eine automatische Telefonzentrale für Ihre Organisation erstellen. Um eine neue automatische Telefonzentrale zu erstellen, navigieren Sie auf der linken Seite auf die **Anrufweiterleitung** und wählen dann **Automatische Telefonzentralen** > **Neu hinzufügen** aus.
  
Wenn Sie weitere Informationen zu automatischen Telefonzentralen erhalten möchten, finden Sie diese unter [Was sind automatische Telefonzentralen für Telefonsysteme?](/microsoftteams/what-are-phone-system-auto-attendants)
  
## <a name="step-1---getting-started"></a>Schritt 1 - Erste Schritte

- Bevor Sie Ihre automatischen Telefonzentralen erstellen und einrichten können, müssen Sie zum Abrufen oder Übertragen Ihre vorhandenen gebührenpflichtigen oder gebührenfreien Service-Nummern erhalten oder übertragen. Nachdem Sie die gebührenpflichtigen oder gebührenfreien Service-Nummern erhalten haben, werden diese auf der Seite **Skype for Business Admin Center** > **VoIP** > **Rufnummern** angezeigt. Um Ihre Service-Rufnummern zu erhalten, finden Sie eine Anleitung unter [Service-Rufnummern für Skype for Business und Microsoft-Teams anfordern](getting-service-phone-numbers.md). Wenn Sie jedoch vorhandene Service-Nummern auf Office 365 übertragen möchen, finden Sie weitere Einzelheiten unter [Übertragen von Telefonnummern auf Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**Benutzer- (Abonnenten-)** Nummern können automatischen Telefonzentralen nicht zugeordnet werden. Außerhalb der USA, wo Sie den Skype for Business Admin Center für die Vergabe von Service-Nummer nicht nutzen können, klicken Sie stattdessen bitte [hier](/microsoftteams/manage-phone-numbers-for-your-organization).
    
    > [!CAUTION]
    > Um gebührenfreie Servicenummern zu erhalten müssen Sie Guthaben für Kommunikationen einrichten. Hierzu finden Sie eine Anleitung unter [Was sind Guthaben für Kommunikationen?](/microsoftteams/what-are-communications-credits) und [Einrichten von Guthaben für Kommunikationen in Ihrer Organisation](/microsoftteams/set-up-communications-credits-for-your-organization). 
  
- Ihre Organisation benötigt (mindestens) eine Enterprise E3 plus **Telefonsystem**-Lizenz oder eine E5 Enterprise-Lizenz. Die Anzahl der zugewiesenen Benutzerlizenzen für das **Telefonsystem** hat einen Einfluss die Anzahl der Servicenummern, die zur Verwendung für Anrufwarteschleifen verfügbar sind. Die Nummern der automatischen Telefonzentralen, die Ihnen zur Verfügung stehen, hängen von den Nummern des **Telefonsystems** und den Lizenzen für **Audiokonferenzen**, die in Ihrer Organisation zugewiesen sind. Weitere Informationen zur Lizenzierung finden Sie [hier](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!TIP]
    > Zum Umleiten von Anrufen an einen Vermittler oder eine Menüoption, die ein Online-Benutzer mit einer **Telefonsystem**-Lizenz ist, müssen Sie diese für Enterprise-VoIP aktivieren oder ihnen in Office 365 Anruf-Pläne zuweisen. Siehe [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Sie können auch die Windows PowerShell verwenden. Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` 
  
## <a name="step-2---create-a-new-auto-attendant"></a>Schritt 2 - Erstellen einer neuen automatischen Telefonzentrale

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Nutzung des Skype for Business Admin Centers**


Klicken Sie im **Skype for Business Admin Center** auf **Anrufweiterleitung** > **Automatische Telefonzentralen** und dann auf **Neu hinzufügen**:
  
### <a name="edit-general-info-page"></a>Seite „Allgemeine Informationen bearbeiten"
  
![Neue automatische Telefonzentrale, Seite 1.](../images/edacec94-9384-4a87-be0a-5c49a151287e.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/>**Name**: Geben Sie einen aussagekräftigen Anzeigenamen für Ihre automatische Telefonzentrale ein. Der Name ist erforderlich und kann maximal 64 Zeichen einschließlich Leerzeichen enthalten. Er wird in der Spalte **Name** der Registerkarte **Automatische Telefonzentralen** aufgeführt.
***

![Nummer 2](../images/sfbcallout2.png)<br/>**Telefonnummer** Diese Einstellung ist optional. Wenn Sie möchten, wählen Sie eine Rufnummer für die automatische Telefonzentrale. Sie können alle verfügbaren gebührenpflichtigen oder gebührenfreien Service-Rufnummern auswählen, die Sie in Ihrer Organisation haben. Wenn keine Telefonnummern aufgeführt sind, müssen Sie sich eine gebührenpflichtige oder gebührenfreie Telefonnummer besorgen.  [Hier klicken](getting-service-phone-numbers.md), um diese zu erhalten. <br/> <br/>

> [!NOTE]
> **Benutzer- (Abonnenten-)** Nummern können automatischen Telefonzentralen nicht zugeordnet werden.
    
***
![Nummer 3](../images/sfbcallout3.png)<br/>**Zeitzone**: Sie müssen die Zeitzone für Ihre automatische Telefonzentrale festlegen. Die Zeitzone muss jedoch nicht der Zeitzone der für Ihre Organisation angegebenen Hauptadresse entsprechen. Sie können für jede automatische Telefonzentrale eine andere Zeitzone festlegen. Die Geschäftszeiten für die automatische Telefonzentrale werden basierend auf der Zeitzone festgelegt, die Sie hier auswählen.
***
![14](../images/sfbcallout4.png)<br/>**Sprache**: Wählen Sie unter den aufgeführten verfügbaren Sprachen die Sprache aus, die Sie für die automatische Telefonzentrale verwenden möchten. Die hier festgelegte Sprache wird von der automatischen Telefonzentrale für Interaktionen mit Anrufern verwendet, und in dieser Sprache werden auch alle Systemansagen wiedergegeben.
***
![Nummer 5](../images/sfbcallout5.png)<br/>**Spracherkennung**: Spracherkennung ist verfügbar, und wenn diese Option aktiviert ist, können Anrufer Spracheingaben in der von Ihnen festgelegten Sprache verwenden. Wenn die Anrufer nur die Wähltastatur ihres Telefons verwenden sollen, können Sie die Spracherkennung mit der Option deaktivieren.
***
![Nummer 6](../images/sfbcallout6.png)<br/>**Vermittler**: Diese Einstellung ist optional und muss für die automatische Telefonzentrale nicht festgelegt werden. Sie können die Option **Vermittler** jedoch festlegen, damit Anrufer die Menüs verlassen können, um mit einer Person zu sprechen und um Hilfe zu bitten. <br/> <br/> Die Taste „0" wird automatisch der Vermittlung zugewiesen. <br/> <br/> Wenn Sie diese Funktion einrichten, müssen Sie die Anrufer darauf hinweisen, dass diese Option unter **Menüoptionen bearbeiten** auf der Seite **Anrufbehandlung während der Geschäftszeiten** verfügbar ist. Wenn Sie für Ihre automatische Telefonzentrale eine Vermittlung festlegen, müssen Sie den entsprechenden Ansagetext in das Feld **Anrufer hören** eingeben oder Ihre Audiodatei ändern, um diese Option aufzunehmen. Beispiel: „Drücken Sie ‚0', um mit der Vermittlung zu sprechen". <br/><br/>  Als Vermittlung können Sie Folgendes festlegen: 
*    **Person in Ihrem Unternehmen** mit einer **Telefonsystem**-Lizenz, die für Enterprise Voice aktiviert oder Anruf-Plänen in Office 365 zugeordnet ist. <br/>

        > [!Note] 
        > **Die Person in Ihrem Unternehmen** kann ein Online-Benutzer oder ein vor Ort gehosteter Benutzer sein, der den Skype for Business Server 2015 oder den Lync Server 2013 verwendet. Der Lync Server 2010 wird nicht unterstützt. <br/> 

*    Eine **Anrufwarteschleife**, die Sie eingerichtet haben. 
*    Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Dazu wählen Sie eine **Person in Ihrem Unternehmen** aus und legen die Anrufe dieser Person so fest, dass sie direkt an die Voicemail weitergeleitet werden. 
   
### <a name="select-hours-of-operation-page"></a>Auswahl der Zeiten für die Vermittler-Seite

Standardmäßig werden Geschäftszeiten auf 24 Stunden am Tag, 7 Tage die Woche festgelegt, damit alle Zeiten als Geschäftszeiten gelten. Alle Zeiten, die nicht innerhalb der Geschäftszeiten liegen, werden als außerhalb der Geschäftszeiten angesehen. Wenn Sie die Option **Benutzerdefiniert** auswählen und Ihre Geschäftszeiten festlegen, wird eine neue Seite **Anruf-Behandlung außerhalb der Geschäftszeiten** aufgerufen, die hinzugefügt wird und in der Sie die Anrufbehandlung außerhalb der Geschäftszeiten für die automatische Telefonzentrale konfigurieren können.
  
![Neue Geschäftszeiten für die automatische Telefonzentrale.](../images/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

***
![Nummer 1](../images/sfbcallout1.png)<br/>Wählen Sie die Option **Benutzerdefiniert** aus, um bestimmte Geschäftszeiten im Kalender auszuwählen. Wenn Sie **Benutzerdefiniert** auswählen, werden die Geschäftszeiten standardmäßig auf Montag bis Freitag von 9:00 Uhr bis 17:00 Uhr festgelegt.
***
![Nummer 2](../images/sfbcallout2.png)<br/>Um Geschäftszeiten zu ändern, markieren Sie die Geschäftszeiten, die Sie einstellen möchten, im Kalender. Der Kalender ermöglicht Ihnen die Auswahl von Geschäftszeiten in Abständen von 30 Minuten, und die Geschäftszeiten, die Sie hier auswählen, werden entsprechend der Zeitzone eingestellt, die Sie auf der Seite „ **Allgemeine Daten“** festlegen. Um eine Pause (beispielsweise eine Mittagspause) einzurichten, deaktivieren, oder ziehen Sie zum Deaktivieren die Zeit im Kalender. Sie können innerhalb der Geschäftszeiten mehrere Pausen festlegen. 
   
### <a name="select-business-hours-call-handling-page"></a>Auswählen von Geschäftszeiten aus der Seite für die Anruf-Behandlung

> [!TIP]
> Wenn Sie einen benutzerdefinierten Zeitplan für die Geschäftszeiten verwenden, müssen Sie auch die Anrufbehandlung außerhalb der Geschäftszeiten einrichten. Es wird eine Seite namens **Anrufbehandlung nach Geschäftsschluss** hinzugefügt, auf der Sie diese Optionen konfigurieren können. Dafür stehen die gleichen Optionen zur Verfügung wie für **Anrufbehandlung während der Geschäftszeiten**. 
  
Sie können Begrüßungen, Anweisungen und Menüs einrichten, die Anrufer hören, die die Nummer der automatischen Telefonzentrale Ihrer Organisation während der Geschäftszeiten anrufen.
  
![Anruf-Behandlung während der Geschäftszeiten.](../images/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/>**Begrüßung durch das Unternehmen:** Die Begrüßung während der Geschäftszeiten ist optional und kann auf **keine**festgelegt werden. In diesem Fall hört der Anrufer keine Meldung oder die Ansage, bevor der Anruf durch eine der Optionen verarbeitet wird, die Sie auswählen. Sie können auch eine Audiodatei hochladen (im WAV-, MP3- oder WMA-Format) oder eine benutzerdefinierte Begrüßung der Sprachausgabe verwenden.
*    **Keine:** Wenn Personen die automatische Telefonzentrale unter dieser Telefonnummer anrufen, wird keine Ansage wiedergegeben.
*    **Erstellen einer benutzerdefinierten Ansage:** Wenn Sie diese Option auswählen, geben Sie den Text (bis zu 1000 Zeichen) ein, der vom System gelesen werden soll. Beispielsweise können Sie „Willkommen bei Contoso, Ihr Anruf ist uns sehr wichtig“ im Feld **Anrufer hört** eingeben.
*    **Hochladen einer Audiodatei:** Wenn Sie diese Option wählen, zeichnen Sie die Begrüßung auf und laden Sie anschließend Ihre Audiodatei hoch (im wav-, .mp3- oder .wma-Format).
***
![Nummer 2](../images/sfbcallout2.png)<br/>Sie können auswählen, was mit Anrufen geschieht, die während der Geschäftszeiten eingehen. Sie können aus den folgenden Optionen wählen:
*    **Verbindung trennen:** Wenn Sie diese Option auswählen, wird die Verbindung der Anrufer nach einer Begrüßung mit Informationen zu den Geschäftszeiten getrennt.
*    **Umleiten von Anrufen:** Dies kann verwendet werden, um den Anruf automatisch weiterzuleiten, an:
     *    **Person in Ihrem Unternehmen** mit einer **Telefonsystem**-Lizenz, die für Enterprise Voice aktiviert oder Anruf-Plänen in Office 365 zugeordnet ist. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Dazu wählen Sie eine **Person in Ihrem Unternehmen** aus, deren Anrufe dann direkt an die Voicemail weitergeleitet werden. <br/><br/>   
        > [!Note]
        > **Die Person in Ihrem Unternehmen** kann ein Online-Benutzer oder ein vor Ort gehosteter Benutzer sein, der den Skype for Business Server 2015 oder den Lync Server 2013 verwendet. Der Lync Server 2010 wird nicht unterstützt. <br/><br/>

     *    Eine **Warteschlange:** Die Verwendung einer Warteschlange ermöglicht, dass ein Anruf in eine bestehende Anruf-Warteschlange weitergeleitet werden kann, die Sie einrichten müssen.
     *    Weitere **automatische Telefonzentrale** Sie können eine bestehende automatische Telefonzentrale verwenden, um eine zweite Ebene von Menüoptionen zu erstellen, die ein untergeordnetes Teilmenü enthält. Diese werden als geschachtelte automatische Telefonzentralen bezeichnet.
*    **Menü-Optionen Eingabe-Aufforderung wiedergeben** Diese können auch dazu verwendet werden, damit Sie eine Eingabe-Aufforderung einrichten können, die abgespielt werden soll.
***
![Nummer 3](../images/sfbcallout3.png)<br/>**Menü-Eingabeaufforderung**: Um eine Ansage für das Hauptmenü zu erstellen, können Sie Text-zu-Sprache verwenden oder eine Audiodatei (im WAV-, MP3- oder WMA-Format) hochladen. Sie können die Ansage in das Feld **Anrufer hören** eingeben oder eine Audiodatei aufzeichnen und zum Beispiel Folgendes sagen: „Drücken oder sagen Sie ‚1' für den Vertrieb. Drücken oder sagen Sie ‚2' für den Service. Drücken oder sagen Sie ‚3' für den Kundendienst. Drücken oder sagen Sie ‚0' für die Vermittlung. Um dieses Menü erneut zu hören, drücken Sie die Sterntaste, oder sagen Sie ‚Wiederholen'." **Eine benutzerdefinierte Aufforderung erstellen**: Wenn Sie diese Option ausgewählt haben, müssen Sie den Text eingeben, der vom System vorgelesen werden soll (maximal 1.000 Zeichen). **Eine Audio-Datei hochladen**: Wenn Sie diese Option ausgewählt haben, müssen Sie die Begrüßung aufzeichnen und dann Ihre Audiodatei (im WAV-, MP3- oder WMA-Format) hochladen.
***
![Nummer 4](../images/sfbcallout4.png)<br/>**Nach Namen wählen**: Wenn Sie diese Option auswählen, können Anrufer mit der Verzeichnissuche nach Personen in Ihrer Organisation suchen. Sie können auswählen, welche Personen für die Namensanwahl als verfügbar oder nicht verfügbar aufgelistet werden, indem Sie diese Optionen auf der Seite **Wählbereich** einrichten. Jeder Online-Benutzer mit einer **Telefonsystem**-Lizenz oder ein beliebiger Benutzer der vor Ort gehostet wird und den Skype for Business Server 2015 oder den Lync Server 2013 verwenden, finden Sie unter nach Namen wählen.<br/><br/>  

> [!WARNING]
> Benutzer, die lokal gehostet werden und Lync 2010 verwenden, können mit nach Namen wählen **nicht erreicht werden**.
***

![Nummer 5](../images/sfbcallout5.png)<br/>**Menüoptionen Bearbeiten:** Die Menüoptionen können über die Tastatur hinzugefügt oder entfernt werden. Um eine Menüoption hinzuzufügen, drücken Sie die entsprechende Taste auf der Tastatur. The verwendeten Tasten ändern ihre Farbe und die entsprechende Optionszeile erscheint darunter. Um eine Menü-Option zu löschen, klicken Sie einfach auf die entsprechende Taste auf der Tastatursteuerung, um diese zu deaktivieren. Die Zeile der Tastenzuordnung wird entfernt.<br/><br/>  **Tipp:** Sie müssen den Text der Eingabe-Aufforderungen aktualisieren oder die Audio-Datei erneut separat aufzeichnen, wenn Sie Optionen hinzufügen oder entfernen, da dies bei der vorhandenen Menü-Anweisung nicht automatisch erfolgt.  <br/><br/>  Jede Menüoption kann in beliebiger Reihenfolge hinzugefügt und entfernt werden und die Tastenzuordnungen müssen nicht fortlaufend sein. Es ist beispielsweise möglich, ein Menü mit Tasten 0, 1 und 3 zu erstellen, die Optionen zugeordnet sind, während die Taste 2 nicht verwendet wird.<br/><br/> 

> [!NOTE]
> Die Tasten * (Wiederholung) und # (zurück) werden vom System reserviert und können nicht neu zugewiesen werden. Wenn die Spracherkennung aktiviert wurde, entspricht * „Wiederholen“ und # entspricht den „Zurück“-Voice-Befehlen.


Um Ihre Menüoptionen einzurichten, nachdem Sie die Taste(n) ausgewählt haben, müssen Sie: 
- **Den Namen der Option eingeben** Dieser kann bis zu 64 Zeichen lang sein und mehrere Wörter enthalten, wie „Kundenservice“ oder „Vorgänge und Gründe“. Wenn die Spracherkennung aktiviert ist, wird der Name automatisch erkannt und der Anrufer kann entweder auf 3 drücken, „drei“ oder „Kundenservice“ sagen, um die der Taste 3 zugeordnete Option auszuwählen. 
- Der nächste Schritt besteht darin, auszuwählen, wohin der Anruf nach Betätigung der entsprechenden Taste oder der Option, die mittels Spracherkennung ausgewählt wird, gesendet wird. Der Anruf kann gesendet werden an: 
    - **Den Vermittler:** Wenn der Vermittler bereits eingerichtet wurde, wird dieser automatisch der Taste 0 zugeordnet, kann aber auch gelöscht oder einer anderen Taste zugeordnet werden. Wenn der Vermittler keiner Taste zugeordnet ist, wird auch der VoIP-Befehl „Vermittler“ deaktiviert. 
    - **Einer Person in Ihrem Unternehmen** mit einer **Telefonsystem** -Lizenz, die für Enterprise Voice aktiviert oder Anruf-Plänen in Office 365 zugeordnet ist. Sie können es so einrichten, dass Anrufer an die Voicemail gesendet werden. Dazu wählen Sie eine **Person in Ihrem Unternehmen** aus, deren Anrufe dann direkt an die Voicemail weitergeleitet werden.<br/><br/> 
    
        > [!Note] 
        > **Die Person in Ihrem Unternehmen** kann ein Online-Benutzer oder ein vor Ort gehosteter Benutzer sein, der den Skype for Business Server 2015 oder den Lync Server 2013 verwendet. Der Lync Server 2010 wird nicht unterstützt. <br/><br/>

    - Eine **Warteschlange:** Die Verwendung einer Warteschlange ermöglicht, dass ein Anruf in eine bestehende Anruf-Warteschlange weitergeleitet werden kann, die Sie eingerichtet haben. 
    - **Automatische Telefonzentrale** Sie können eine bestehende automatische Telefonzentrale verwenden, um eine zweite Ebene von Menüoptionen zu erstellen, die ein untergeordnetes Teilmenü enthält. Diese werden als geschachtelte automatische Telefonzentralen bezeichnet.<br/><br/>
    
        > [!Note]
        > Die **Geschäftszeiten** geschachtelter automatischer Telefonzentralen (oder mit zweiter Ebene) werden ebenfalls eingesetzt, einschließlich der Anrufe, die von anderen Telefonzentralen eingehen, die eingerichtet wurden.         
   
### <a name="select-holidays-page"></a>Auswahl der Feiertags-Seite 

Sie können jeder automatische Telefonzentrale bis zu 20 geplante Feiertage hinzufügen.
  
![Einrichten von Feiertagen in der automatischen Telefonzentrale](../images/50a5ce88-7f39-4210-808a-da7ced969854.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/>**Fügen Sie einen Feiertag hinzu** Geben Sie Ihrem neuen Feiertag im Feld **Name des Feiertags** einen Namen.<br/><br/> Feiertags-Namen können bis zu 64 Zeichen lang sein und müssen für die gleiche Telefonzentrale eindeutig sein. Beispielsweise können Sie in derselben automatischen Telefonzentrale keine zwei Feiertage mit dem Namen „Thanksgiving“ haben.  
***
![Nummer 2](../images/sfbcallout2.png)<br/>**Feiertags-Begrüßung** Die Feiertags-Begrüßung ist optional und kann auf **keine**festgelegt werden. In diesem Fall hört der Anrufer keine Meldung oder die Ansage, bevor der Anruf durch eine der Optionen verarbeitet wird, die Sie auswählen. Sie können auch eine Audiodatei hochladen (im WAV-, MP3- oder WMA-Format) oder eine benutzerdefinierte Begrüßung der Sprachausgabe verwenden.
*    **Keine:** Wenn Personen die automatische Telefonzentrale unter dieser Telefonnummer anrufen, wird keine Ansage wiedergegeben.
*    **Erstellen einer benutzerdefinierten Ansage:** Wenn Sie diese Option auswählen, geben Sie den Text (bis zu 1000 Zeichen) ein, der vom System gelesen werden soll. Beispielsweise können Sie „Frohes Neues Jahr!“, unsere Büros sind derzeit geschlossen“ im Feld **Anrufer hört** eingeben.
*    **Hochladen einer Audiodatei:** Wenn Sie diese Option wählen, zeichnen Sie die Begrüßung auf und laden anschließend Ihre Audiodatei hoch (im wav-, .mp3- oder .wma-Format).  
***
![Nummer 3](../images/sfbcallout3.png)<br/>**Was geschieht mit den Anrufen nach der Begrüßung?** Sie können auswählen, was mit den Anrufen geschieht, die während dieses Feiertags eingehen. Sie können aus den folgenden Optionen wählen:
*    **Verbindung trennen** Die Verbindung des Anrufers wird getrennt, nachdem er die Feiertags-Nachricht gehört hat.
*    **Umleiten von Anrufen:** Dies kann verwendet werden, um den Anruf automatisch weiterzuleiten, an:
     *    Eine **Person in Ihrem Unternehmen** mit einer **Telefonsystem** -Lizenz, die für Enterprise Voice aktiviert oder Anruf-Plänen in Office 365 zugeordnet ist. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Dazu wählen Sie eine **Person in Ihrem Unternehmen** aus, deren Anrufe dann direkt an die Voicemail weitergeleitet werden. <br/><br/> 
     
         > [!Note] 
         > **Die Person in Ihrem Unternehmen** kann ein Online-Benutzer oder ein vor Ort gehosteter Benutzer sein, der den Skype for Business Server 2015 oder den Lync Server 2013 verwendet. Der Lync Server 2010 wird nicht unterstützt.<br/><br/>

     *    Eine **Anruf-Warteschlange** zur Weiterleitung des Anrufs an eine vorhandene Anruf-Warteschlange, die Sie eingerichtet haben.
     *    Eine andere **automatische Telefonzentrale** für die Erstellng einer zweiten Ebene von Menüoptionen, die ein untergeordnetes Teilmenü enthalten. Diese werden als geschachtelte automatische Telefonzentralen bezeichnet. <br/><br/>
     
         > [!Note]
         > Standardmäßig werden alle während eines Feiertags eingehenden Anrufe festgelegt, deren Verbindung nach der Ansage (falls vorhanden) getrennt wird, somit müssen Sie eine Umleitung angeben, wenn ein anderes Verhalten erwünscht ist.

***
![Nummer 4](../images/sfbcallout4.png)<br/>**Wann möchten Sie, dass der Feiertag beginnt und wann soll er enden?** Geben Sie den Anfangstermin für den Feiertag im Format mm/tt/jjjj an und wählen Sie dann eine Startzeit, ein Enddatum und einen Endzeitpunkt, wenn Sie in der Tabelle Datumsbereich dazu aufgefordert werden.<br/><br/>Sie können bis zu 10 verschiedene Datumsbereiche für einen Feiertag angeben. Sie könnten beispielsweise Datumsbereiche für Silvester-Feiertage für bis zu 10 Jahre hinzufügen. Ein Feiertag kann mehrere Tage umfassen.<br/><br/>Um Feiertagen zusätzliche Datumsbereiche hinzuzufügen, (zum Beispiel für das nächste Jahr), klicken Sie auf **Einen weiteren hinzufügen** und geben Sie einen neuen Satz von Start- und Enddatum des Feiertags ein.<br/><br/>Geschachtelte Feiertage werden ebenfalls unterstützt. Beispielsweise könnten Sie mehrere Feiertage in einen Zeitrahmen „Feiertage“ ein: 
*    **24. Dezember bis 03. Januar:** „Fröhliche Feiertage! Unsere Büros sind derzeit geschlossen. Ab dem 4. Januar sind wir wieder für Sie da.“
*    **25. Dezember:** „Fröhliche Weihnachten! Unsere Büros sind derzeit geschlossen. Ab dem 4. Januar sind wir wieder für Sie da.“
*    **1. Januar:** „Frohes neues Jahr! Unsere Büros sind derzeit geschlossen. Ab dem 4. Januar sind wir wieder für Sie da.“
   
Nachdem Sie die automatische Telefonzentrale gespeichert haben, erscheinen Ihre Feiertage auf der Registerkarte **Feiertage**, auf der Sie die Einstellungen zu den Feiertagen bearbeiten, hinzufügen oder ändern können.
  
### <a name="select-dial-scope-page"></a>Seite „Wählbereich auswählen"

Auf dieser Seite können Sie einrichten, welche Benutzer in Ihrer Organisation im Verzeichnis aufgeführt werden und für die Namensanwahl verfügbar sein sollen, wenn jemand bei der Organisation anruft.
  
![Wahlumfang für die Suche mit Namensanwahl.](../images/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/>Für **Einschließen** gibt es zwei Optionen:
*    **Alle Onlinebenutzer**: Wenn Sie diese Option verwenden, können alle Benutzer in Ihrer Organisation in eine Verzeichnissuche eingeschlossen werden. Alle Online-Benutzer mit einer **Telefonsystem**-Lizenz und auch lokal gehostete Benutzer, die den Skype for Business Server 2015 oder den Lync Server 2013 verwenden, die Anruf-Pläne in Office 365 haben, werden aufgeführt. 
*    **Benutzerdefiniert:** Wenn Sie diese Option verwenden, können Sie nach einer Gruppe von Office 365, Verteilerliste oder Sicherheitsgruppe suchen, die in Ihrer Organisation erstellt wurde und nach Personen, die in Office 365, einerVerteilerliste, oder Sicherheitsgruppe hinzugefügt wurden und entweder **Online-Benutzer mit einer Telefon-Lizenz** oder lokal gehostete, die den Skype for Business Server 2015 oder Lync Server 2013 verwenden. Sie können mehrere Office 365-Gruppen, Verteilerlisten und Sicherheitsgruppen hinzufügen. <br/><br/> 

    > [!Caution]
    > Lokale Benutzer aus der Bereitstellung des Lync Server 2010 werden nicht aufgeführt, wenn jemand das Verzeichnis mit Namensanwahl durchsucht. 
***
![Nummer 2](../images/sfbcallout2.png)<br/>Bei Verwendung der Option **Ausschließen** haben Sie zwei Optionen:
*    **Keine**: Wenn Sie diese Option verwenden, werden keine Onlinebenutzer von der Verzeichnissuche ausgeschlossen. 
*    **Benutzerdefiniert**: Wenn Sie diese Option verwenden, können Sie nach einer Office 365-Gruppe, Verteilerliste oder Sicherheitsgruppe suchen, die in Ihrer Organisation erstellt wurde. Alle Personen, die dieser Office 365-Gruppe, Verteilerliste oder Sicherheitsgruppe hinzugefügt wurden, werden von der Verzeichnissuche ausgeschlossen. Sie können mehrere Office 365-Gruppen, Verteilerlisten und Sicherheitsgruppen hinzufügen. <br/><br/> 

    > [!Caution]
    > Lokale Benutzer aus der Bereitstellung des Lync Server 2010 werden nicht aufgeführt, wenn jemand das Verzeichnis mit Namensanwahl durchsucht.          
   
> [!NOTE]
> Es kann bis zu 36 Stunden dauern, bis der Name eines neuen Benutzer im Verzeichnis aufgelistet wird, wenn jemand die Namensanwahl mit Spracherkennung verwendet. 
  
Wenn Sie alle erforderlichen Felder ausgefüllt und die Einstellungen in den Menüs und Optionen für die Anrufbehandlung vorgenommen haben, klicken Sie auf **Speichern**.
  
## <a name="editing-and-testing-auto-attendants"></a>Bearbeiten und Testen einer automatischen Telefonzentrale

Wenn Sie Ihre automatische Telefonzentrale gespeichert haben, wird diese auf der Seite **Automatische Telefonzentralen** aufgeführt. Auf diese Weise sehen Sie schnell einige der Optionen, die Sie eingerichtet haben, unter anderem den Namen, die Telefonnummer, die Sprache und den Zustand.
  
Wenn Sie eine automatische Telefonzentrale ändern möchten, wählen Sie die automatische Telefonzentrale aus, und klicken Sie dann im Bereich Aktion auf **Bearbeiten**.
  
Sie können auch einen kurzen Testanruf an die automatische Telefonzentrale tätigen, indem Sie im Aktions-Bereich die Schaltfläche **Test** verwenden.
  
## <a name="want-to-know-more"></a>Möchten Sie mehr wissen?

Sie können auch Windows PowerShell verwenden, um automatische Telefonzentralen zu erstellen und einzurichten.
  
### <a name="auto-attendant-cmdlets"></a>Cmdlets für automatische Telefonzentralen

Zum Verwalten einer automatischen Telefonzentrale benötigen Sie die folgenden Cmdlets.
  
||| 
|---|---|
[New-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796493.aspx)                                                                      | [New-CsOrganizationalAutoAttendantPrompt](https://technet.microsoft.com/library/mt796484.aspx)                                                              |
| [Set-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796486.aspx)                                                                      | [New-CsOrganizationalAutoAttendantMenuOption](https://technet.microsoft.com/library/mt796485.aspx)                                                           |
| [Get-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796482.aspx)                                                                      | [Get-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csorganizationalautoattendantholidays?view=skype-ps)       |
| [Remove-CsOrganizationalAutoAttendant](https://technet.microsoft.com/library/mt796492.aspx)                                                                   | [New-CsOrganizationalAutoAttendantMenu](https://technet.microsoft.com/library/mt796488.aspx)                                                                  |
| [New- CsOnlineAudioFile](https://technet.microsoft.com/library/mt796479.aspx)                                                                                 | [New-CsOrganizationalAutoAttendantCallFlow](https://technet.microsoft.com/library/mt796489.aspx)                                                              |
| [Export-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps) | [New-CsOnlineTimeRange](https://technet.microsoft.com/library/mt796491.aspx)                                                                                  |
| [New-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)                                       | [New-CsOnlineSchedule](https://technet.microsoft.com/library/mt796490.aspx)                                                                                   |
| [Get-CsOrganizationalAutoAttendantSupportedTimeZone](https://technet.microsoft.com/library/mt796483.aspx)                                                     | [New-CsOrganizationalAutoAttendantCallHandlingAssociation](https://technet.microsoft.com/library/mt796487.aspx)                                               |
| [Get-CsOrganizationalAutoAttendantSupportedLanguage](https://technet.microsoft.com/library/mt796481.aspx)                                                     | [Import-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csorganizationalautoattendantholidays?view=skype-ps) |
| [New-CsOrganizationalAutoAttendantCallableEntity](https://technet.microsoft.com/library/mt796480.aspx)                                                      |  |   |
   
### <a name="more-about-windows-powershell"></a>Weitere Informationen zu Windows PowerShell

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Dinge zu tun haben. Siehe folgende Themen, um Windows PowerShell zu verwenden:
    
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
    
  
 
