---
title: Richten Sie eine automatische Telefonzentrale Telefonsystem
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: "Informationen Sie zum Einrichten und Testen von Telefonsystem (Cloud, PBX) automatische Telefonzentralen für effiziente Anruf Behandeln von für Ihre Organisation. "
ms.openlocfilehash: 294a91ec723d8234e2dbfec8da79441080263c30
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-a-phone-system-auto-attendant"></a>Richten Sie eine automatische Telefonzentrale Telefonsystem

Automatische Telefonzentralen können Personen, die in Ihrer Organisation anrufen, und navigieren Sie ein Menüsystem diese an die richtige Abteilung erhalten möchten, rufen Sie Warteschlange, Person, oder der Operator. Sie können eine automatische Telefonzentrale für Ihre Organisation mithilfe der Skype für Business-Verwaltungskonsole erstellen. Zum Erstellen einer neuen automatischen Telefonzentrale, wechseln zur **Anrufrouting** im linken Navigationsbereich, und wählen Sie **automatische Telefonzentralen** > **Hinzufügen**.
  
Wenn Sie weitere Informationen zu automatischen Telefonzentralen finden möchten, finden Sie unter [Was Telefonsystem automatischen Telefonzentralen sind?](what-are-phone-system-auto-attendants.md)
  
## <a name="step-1---getting-started"></a>Schritt 1 - Erste Schritte

- Bevor Sie erstellen und von der automatischen Telefonzentralen einrichten können, müssen Sie zum Abrufen oder übertragen Ihre vorhandenen gebührenpflichtige oder gebührenfreie Service Zahlen. Nachdem Sie die gebührenpflichtige oder gebührenfreie Service Zahlen erhalten möchten, sie werden angezeigt, auf die **Skype für Business Administrationscenter** > **VoIP** > Seite**Rufnummern** . Um die Rufnummern Service erhalten möchten, finden Sie unter [Getting Service Rufnummern für Skype für Unternehmen und die Microsoft-Teams](getting-service-phone-numbers.md)oder für Übertragung und vorhandenen Service-Nummer, finden Sie unter [Übertragen von Telefonnummern zu Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md). Benutzeranzahl **(Abonnent)** kann nicht zum automatischen Telefonzentralen zugewiesen werden. Wenden Sie sich außerhalb der USA, können Sie mithilfe der Skype für Business Administrationscenter Service Zahlen abrufen; Klicken Sie [hier](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) stattdessen.
    
    > [!CAUTION]
    > Zum Abrufen und gebührenfreien Telefonnummern verwenden, müssen Sie Communications haben einrichten. Hierzu finden Sie [Was sind Communications haben?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md) und [Communications haben für Ihre Organisation einrichten](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md). 
  
- Ihre Organisation muss eine Lizenz Enterprise E3 plus **Telefonsystem** oder einer E5 Enterprise-Lizenz (mindestens) verfügen. Die Anzahl der **Telefonsystem** Benutzerlizenzen, die zugewiesen sind, wirkt sich auf die Anzahl der Dienst Zahlen, die für automatische Telefonzentralen zu verwendende verfügbar sind. Die Nummern der automatischen Telefonzentralen können Ihnen ist abhängig von die Zahlen **Telefonsystem** und **Audiokonferenzen** -Lizenzen, die in Ihrer Organisation zugewiesen sind. Weitere Informationen zu Lizenzierung, klicken Sie [hier](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!TIP]
    > Zum Umleiten von Anrufen an einen Operator oder eine Menüoption, die ein Benutzer Online mit einer Lizenz **Telefonsystem** ist, müssen Sie für Enterprise-VoIP zu aktivieren oder Aufrufen in Office 365-Pläne ihnen zuweisen. Finden Sie unter [Skype für Geschäfts- und Microsoft-Teams, Lizenzen zuweisen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Sie können auch Windows PowerShell verwenden. Führen Sie beispielsweise Folgendes aus:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true` 
  
## <a name="step-2---create-a-new-auto-attendant"></a>Schritt 2 - Erstellen einer neuen automatischen Telefonzentrale

Klicken Sie im **Skype for Business Admin Center** auf **Anrufweiterleitung** > **Automatische Telefonzentralen** und dann auf **Neu hinzufügen**:
  
### <a name="edit-general-info-page"></a>Seite „Allgemeine Informationen bearbeiten"
  
![New auto attendant page 1.](../images/edacec94-9384-4a87-be0a-5c49a151287e.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/>**Name** Geben Sie einen aussagekräftigen Anzeigenamen für die automatische Telefonzentrale. Der Name ist erforderlich und kann bis zu 64 Zeichen enthalten, einschließlich Leerzeichen. Sie werden in der Spalte **Name** auf der Registerkarte **automatische Telefonzentralen** eingetragen sein.
***

![Nummer 2](../images/sfbcallout2.png)<br/>**Telefonnummer** Diese Einstellung ist optional. Wenn Sie möchten, wählen Sie eine Rufnummer für die automatische Telefonzentrale. Sie können auswählen, alle verfügbaren Service gebührenpflichtige oder gebührenfreie Telefonnummer, die Sie für Ihre Organisation müssen. Wenn keine aufgeführten Telefonnummern vorhanden sind, müssen Sie zum Abrufen eines Diensts gebührenpflichtige oder gebührenfreie Telefonnummer Anzahl. [Hier](getting-service-phone-numbers.md) werden können. <br/> <br/>

    > [!Note]
    > **User (subscriber)** numbers can't be assigned to auto attendants.
***
![Nummer 3](../images/sfbcallout3.png)<br/>**Zeitzone**: Sie müssen die Zeitzone für Ihre automatische Telefonzentrale festlegen. Die Zeitzone muss jedoch nicht der Zeitzone der für Ihre Organisation angegebenen Hauptadresse entsprechen. Sie können für jede automatische Telefonzentrale eine andere Zeitzone festlegen. Die Geschäftszeiten für die automatische Telefonzentrale werden basierend auf der Zeitzone festgelegt, die Sie hier auswählen.
***
![14](../images/sfbcallout4.png)<br/>**Sprache** Wählen Sie die Sprache, die Sie für die automatische Telefonzentrale von einem beliebigen verfügbaren Sprachen aufgeführt verwenden möchten. Die Sprache, die Sie hier festlegen, wird die Sprache, die die automatische Telefonzentrale zum interagieren mit Personen, die diese automatische Telefonzentrale anrufen, und fordert das System werden in dieser Sprache wiedergegeben werden.
***
![Zahl 5](../images/sfbcallout5.png)<br/>**Spracherkennung** Spracherkennung verfügbar ist und wenn diese Option ausgewählt ist. Personen, die in aufrufen können Spracheingaben in der Sprache, die Sie festlegen. Sie können die Spracherkennung deaktivieren, indem Sie es löschen, wenn Sie nur Personen, die ihre Telefontastatur verwenden können möchten.
***
![Zahl 6](../images/sfbcallout6.png)<br/>**Operator** Dies ist optional und muss nicht für die automatische Telefonzentrale festgelegt werden. Sie können jedoch die Option **Operator** für die Personen festlegen, die im Unterbrechungsmodus außerhalb des Kontextmenüs an eine Person, die sie unterstützen sprechen können aufrufen. <br/> <br/> Die Taste „0" wird automatisch der Vermittlung zugewiesen. <br/> <br/> Wenn Sie dies festlegen, müssen Sie auch Personen mitteilen, die aufgerufen wird, insofern Dies ist eine verfügbare Option in den **Menüoptionen im bearbeiten** auf der Seite **Geschäftszeiten Behandlung aufrufen** . Wenn Sie einen Operator für die automatische Telefonzentrale festlegen, müssen Sie geben den entsprechenden Prompt Text im Feld **Anrufer hören** oder Ändern Ihrer Audiodatei, wenn Sie diese Option. Beispielsweise "für den Operator drücken 0 (null)." <br/><br/>  Als Vermittlung können Sie Folgendes festlegen: 
*    **Person in Ihrem Unternehmen** mit einer **Telefonsystem** -Lizenz, die für Enterprise Voice aktiviert oder Aufrufen in Office 365-Pläne zugeordnet ist. <br/>

        > [!Note] 
        > **Person in Ihrem Unternehmen** kann es sich um ein Online-Benutzer oder ein Benutzer gehostet: lokal mit Skype für Business Server 2015 oder Lync Server 2013. Lync Server 2010 wird nicht unterstützt. <br/> 

*    Eine **Warteschlange aufrufen** , die Sie eingerichtet haben. 
*    Sie können es einrichten, damit die Person Aufrufen an die Voicemail gesendet werden. Zu diesem Zweck wählen Sie **Person in Ihrem Unternehmen** aus, und legen Sie diese Person Anrufe an die Voicemail weitergeleitet werden. 
   
### <a name="select-hours-of-operation-page"></a>Seite „Geschäftszeiten auswählen"

Standardmäßig werden Geschäftszeiten auf 24 Stunden am Tag, 7 Tage die Woche festgelegt, damit alle Stunden Geschäftszeiten gelten. Der Stunden, die Bestandteil von Geschäftszeiten werden nicht alle gelten Geschäftszeiten. Wenn Sie die Option **Benutzerdefiniert** und Geschäftszeiten festlegen, wird eine neue Seite wird aufgerufen, **nachdem Stunden Behandlung aufrufen** , in dem Sie den Anruf behandeln für Geschäftszeiten für die automatische Telefonzentrale konfigurieren können hinzugefügt werden.
  
![New auto attendant Hours of operation.](../images/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

***
![Nummer 1](../images/sfbcallout1.png)<br/>Wählen Sie die Option **Benutzerdefiniert** aus, um bestimmte Geschäftszeiten im Kalender auszuwählen. Wenn Sie **Benutzerdefiniert** auswählen, werden die Geschäftszeiten standardmäßig auf Montag bis Freitag von 9:00 Uhr bis 17:00 Uhr festgelegt. 
***
![Nummer 2](../images/sfbcallout2.png)<br/>Um Geschäftszeiten zu ändern, markieren Sie die Geschäftszeiten an, den, die Sie mit dem Kalender festlegen möchten. Im Kalender ermöglicht Ihnen die Auswahl von Geschäftszeiten in Abständen von 30 Minuten, und der Geschäftszeiten hier gewählte festgelegt basierend auf der Zeitzone, die Sie auf der Seite " **Allgemein"** festlegen. Um einen Umbruch (beispielsweise einer Mittagspause) einzurichten, deaktivieren, oder deaktivieren die Zeit im Kalender ziehen. Sie können mehrere Umbrüche innerhalb von Geschäftszeiten festlegen. 
   
### <a name="select-business-hours-call-handling-page"></a>Auswählen von Geschäftszeiten Anruf Behandeln von Seite

> [!TIP]
> Wenn Sie einen benutzerdefinierten Zeitplan für die Geschäftszeiten verwenden, müssen Sie auch die Anrufbehandlung außerhalb der Geschäftszeiten einrichten. Es wird eine Seite namens **Anrufbehandlung nach Geschäftsschluss** hinzugefügt, auf der Sie diese Optionen konfigurieren können. Dafür stehen die gleichen Optionen zur Verfügung wie für **Anrufbehandlung während der Geschäftszeiten**. 
  
Begrüßungen, Ansagen und Menüs können, die es Benutzern eingerichtet werden, die während der Geschäftszeiten Anruf in Ihrer Organisation Auto attendant Telefonnummer hören kann.
  
![Business hours call handling.](../images/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/>**Unternehmen Begrüßung** Begrüßung während der Geschäftszeit ist optional und kann auf **keine**festgelegt werden. In diesem Fall hören der Anrufer keine Meldung oder die Ansage, bevor der Anruf durch eine der Optionen verarbeitet wird, die Sie auswählen. Sie können auch Hochladen einer Audiodatei (im WAV-, MP3- oder WMA-Format) oder erstellen eine benutzerdefinierte Begrüßung Sprachausgabe verwenden.
*    **None** Keine Ansage wird wiedergegeben werden, wenn Personen die automatische Telefonzentrale Telefonnummer anrufen.
*    **Erstellen eines benutzerdefinierten Ansage** Wenn Sie diese Option auswählen, geben Sie den Text (bis zu 1000 Zeichen) gelesen werden soll. Beispielsweise können Sie eingeben, "Willkommen bei Contoso. Der Anruf ist wichtig für uns." im Feld **Anrufer hören** .
*    **Hochladen einer Audiodatei** Wenn Sie diese Option wählen, tragen Sie die Begrüßung und anschließendes hochladen Sie der Audiodatei (im WAV-, MP3 oder WMA-Format).
***
![Nummer 2](../images/sfbcallout2.png)<br/>Sie können auswählen, was geschieht, Anrufe, die während der Geschäftszeit eingehen. Sie können aus den folgenden Optionen wählen:
*    **Verbindung trennen** Wenn Sie diese Option auswählen, werden die Person einwählen, getrennt nach einer Begrüßung während der Geschäftszeit hören.
*    **Umleiten von Anrufen** Dies kann verwendet werden, um den Anruf an automatisch zu senden:
     *    **Person in Ihrem Unternehmen** mit einer **Telefonsystem** -Lizenz, die für Enterprise Voice aktiviert oder Aufrufen in Office 365-Pläne zugeordnet ist. Sie können es einrichten, damit die Person, die Aufrufen an die Voicemail gesendet werden kann. Zu diesem Zweck wählen **Person in Ihrem Unternehmen** aus, und legen Sie diese Person ihre Anrufe an die Voicemail weitergeleitet werden. <br/><br/>   
        > [!Note]
        > **Person in Ihrem Unternehmen** kann es sich um ein Online-Benutzer oder ein Benutzer gehostet: lokal mit Skype für Business Server 2015 oder Lync Server 2013. Lync Server 2010 wird nicht unterstützt. <br/><br/>

     *    Eine **Warteschlange rufen Sie** mithilfe einer Warteschlange aufrufen können den Anruf an eine vorhandene aufrufen Warteschlange übertragen werden, die Sie eingerichtet haben.
     *    Erstellen Sie eine zweite Ebene im Menü Optionen, die ein Untermenü enthält-Telefonzentrale eine andere **automatische Telefonzentrale** Sie eine vorhandene verwenden können. Diese werden geschachtelte Telefonzentralen bezeichnet.
*    **Menü Optionen Aufforderung wiedergeben** Dies können auch dazu verwendet werden, bei denen Sie eine Aufforderung einrichten, die abgespielt werden soll.
***
![Nummer 3](../images/sfbcallout3.png)<br/>**Menü-Eingabeaufforderung**: Um eine Ansage für das Hauptmenü zu erstellen, können Sie Text-zu-Sprache verwenden oder eine Audiodatei (im WAV-, MP3- oder WMA-Format) hochladen. Sie können die Ansage in das Feld **Anrufer hören** eingeben oder eine Audiodatei aufzeichnen und zum Beispiel Folgendes sagen: „Drücken oder sagen Sie ‚1' für den Vertrieb. Drücken oder sagen Sie ‚2' für den Service. Drücken oder sagen Sie ‚3' für den Kundendienst. Drücken oder sagen Sie ‚0' für die Vermittlung. Um dieses Menü erneut zu hören, drücken Sie die Sterntaste, oder sagen Sie ‚Wiederholen'." **Eine benutzerdefinierte Aufforderung erstellen**: Wenn Sie diese Option ausgewählt haben, müssen Sie den Text eingeben, der vom System vorgelesen werden soll (maximal 1.000 Zeichen). **Eine Audio-Datei hochladen**: Wenn Sie diese Option ausgewählt haben, müssen Sie die Begrüßung aufzeichnen und dann Ihre Audiodatei (im WAV-, MP3- oder WMA-Format) hochladen.
***
![Nummer 4](../images/sfbcallout4.png)<br/>**Wählen Sie nach Namen** Wenn Sie diese Option auswählen, können diese Personen, die in die Suche nach Personen in Ihrer Organisation mithilfe der Verzeichnissuche aufrufen. Sie können auswählen, welche Personen als nicht verfügbar für Einwahl namentlich aufgeführt werden durch diese Optionen auf der Seite **Wählen Sie eine Bereich** einrichten. Jeder Benutzer online mit einer Lizenz **Telefonsystem** oder ein beliebiger Benutzer gehostet: lokal mit Skype für Business Server 2015 oder Lync Server 2013 finden Sie über DFÜ nach Namen.<br/><br/>  **Vorsicht:** Benutzer gehostet lokale Zugriffsnummer nach Namen mit Lync 2010 **nicht erreicht werden kann** .
***

![Zahl 5](../images/sfbcallout5.png)<br/>**Menüoptionen im bearbeiten** Menüoptionen können hinzugefügt oder mithilfe von wichtigen Schaltflächen auf der Tastatur entfernt werden. Wenn eine Menüoption hinzufügen möchten, drücken Sie auf der Tastatur den entsprechenden Schlüssel. Verwendet die Schlüssel in Farbe geändert werden, und die entsprechende Zeile der Optionen unter angezeigt. Um eine Menüoption zu löschen, klicken Sie einfach auf den entsprechenden Schlüssel für die Tastatur-Steuerelement, um dieser Schlüssel deaktivieren. Die Zeile tastenzuordnung werden entfernt.<br/><br/>  **Tipp:** Sie müssen im Menü Ansagen Text aktualisieren oder erneut zeichnet separat beim Entfernen von Optionen, da dies automatisch für die Aufforderung zur vorhandenen Menü erfolgen wird nicht hinzugefügt.  <br/><br/>  Alle Menüoption hinzugefügt und in beliebiger Reihenfolge entfernt werden kann, und die tastenzuordnungen müssen nicht zusammenhängend sein. Es ist beispielsweise möglich, erstellen Sie ein Menü mit Tasten 0, 1 und 3 auf Optionen, zugeordnet werden, während die Taste 2 nicht verwendet wird.<br/><br/> 

    > [!Note] 
    > The keys * (Repeat) and # (Back) are reserved by the system and can't be reassigned. If speech recognition is enabled, pressing * will correspond with "Repeat" and # will correspond with the "Back" voice commands. <br/><br/>

Um Ihre Menüoptionen im eingerichtet werden, nachdem Sie den Schlüssel ausgewählt haben, müssen Sie: 
- **Geben Sie den Namen der option** Dies kann bis zu 64 Zeichen lang sein und kann enthalten mehrere Wörter wie "Customer Service" oder "Vorgänge und Gründe." Wenn die Spracherkennung aktiviert ist, der Name automatisch erkannt wird und Person einwählen, sehen, drücken Sie entweder 3 können, sagen Sie "3" oder sagen Sie "Customer Service" aktivieren Sie die Option Schlüssel 3 zugeordnet. 
- Der nächste Schritt besteht aus, in dem der Anruf ist gesendet werden, wenn die entsprechende Taste gedrückt wird, oder die Option mithilfe der Spracherkennung aktiviert ist. Der Anruf kann an gesendet werden: 
    - **Operator** Wenn Operator bereits festgelegt ist, wird es automatisch Schlüssel 0 zugeordnet, jedoch können auch gelöscht oder einem anderen Schlüssel zugewiesen. Wenn Operator auf eine beliebige Taste, nicht festgelegt ist, wird zu der VoIP-Befehl "Operator" deaktiviert. 
    - Eine **Person in Ihrem Unternehmen** mit einer **Telefonsystem** -Lizenz, die für Enterprise Voice aktiviert oder ein Aufruf von planen in Office 365 zugeordnet ist. Sie können es einrichten, damit die Person, die Aufrufen an die Voicemail gesendet werden kann. Zu diesem Zweck wählen **Person in Ihrem Unternehmen** aus, und legen Sie diese Person ihre Anrufe an die Voicemail weitergeleitet werden.<br/><br/> 
    
        > [!Note] 
        > **Person in Ihrem Unternehmen** kann es sich um ein Online-Benutzer oder ein Benutzer gehostet: lokal mit Skype für Business Server 2015 oder Lync Server 2013. Lync Server 2010 wird nicht unterstützt. <br/><br/>

    - **Aufrufen der Warteschlange** Eine Anruf Queue-Option ermöglicht den Anruf an eine vorhandene Anruf Warteschlange übertragen werden, die Sie eingerichtet haben. 
    - **Automatische Telefonzentrale** Eine vorhandene automatische Telefonzentrale können Sie eine zweite Ebene im Menü Optionen, die mit einem Untermenü erstellen. Diese werden geschachtelte Telefonzentralen bezeichnet.<br/><br/>
    
        > [!Note]
        > Die **Geschäftszeiten** geschachtelte (oder der zweiten Ebene) automatische Telefonzentralen wird für die Anrufe von anderen Telefonzentralen, die bereits eingerichteten gesendete einschließlich auch verwendet werden.         
   
### <a name="select-holidays-page"></a>Wählen Sie Feiertage Seite 

Sie können jede automatische Telefonzentrale bis zu 20 geplanten Feiertage hinzufügen.
  
![Einrichten von Feiertagen in die automatische Telefonzentrale](../images/50a5ce88-7f39-4210-808a-da7ced969854.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/>**Fügen Sie einen Feiertag hinzu** Geben Sie einen Namen für die neue Feiertag im Feld **Name des Feiertags** ein.<br/><br/> Namen Feiertage können bis zu 64 Zeichen lang sein und müssen für die gleichen Telefonzentrale eindeutig sein. Angenommen, Sie zwei Feiertagen, die mit dem Namen "Danksagung für geleistete" in der gleichen Telefonzentrale nicht möglich.  
***
![Nummer 2](../images/sfbcallout2.png)<br/>**Feiertag Begrüßung** Die Feiertag Begrüßung ist optional und kann auf **keine**festgelegt werden. In diesem Fall hören der Anrufer keine Meldung oder die Ansage, bevor der Anruf durch eine der Optionen verarbeitet wird, die Sie auswählen. Sie können auch Hochladen einer Audiodatei (im WAV-, MP3- oder WMA-Format) oder erstellen eine benutzerdefinierte Begrüßung Sprachausgabe verwenden.
*    **None** Keine Ansage wird wiedergegeben werden, wenn Personen die automatische Telefonzentrale Telefonnummer anrufen.
*    **Erstellen eines benutzerdefinierten Ansage** Wenn Sie diese Option auswählen, geben Sie den Text (bis zu 1000 Zeichen) gelesen werden soll. Beispielsweise können Sie "Happy neues Jahr! eingeben. Unsere Büros sind derzeit geschlossen." im Feld **Anrufer hören** .
*    **Hochladen einer Audiodatei** Wenn Sie diese Option wählen, Aufzeichnen der Grußformel Feiertag und anschließendes Hochladen der Audiodatei (im WAV-, MP3 oder WMA-Format).  
***
![Nummer 3](../images/sfbcallout3.png)<br/>**Was geschieht, nachdem die Begrüßung auf Anrufe?** Sie können auswählen, was geschieht, an die Anrufe, die während dieses Feiertag eingehen. Sie können aus den folgenden Optionen wählen:
*    **Verbindung trennen** Die Person einwählen, werden nach dem hören der Ansage Feiertag getrennt.
*    **Umleiten von Anrufen** Dies kann verwendet werden, um den Anruf an automatisch zu senden:
     *    Eine **Person in Ihrem Unternehmen** mit einer **Telefonsystem** -Lizenz, die für Enterprise Voice aktiviert oder Aufrufen in Office 365-Pläne zugeordnet ist. Sie können es einrichten, damit die Person, die Aufrufen an die Voicemail gesendet werden kann. Zu diesem Zweck wählen **Person in Ihrem Unternehmen**aus, und legen Sie diese Person ihre Anrufe an die Voicemail weitergeleitet werden. <br/><br/> 
     
         > [!Note] 
         > **Person in Ihrem Unternehmen** kann es sich um ein Online-Benutzer oder ein Benutzer gehostet: lokal mit Skype für Business Server 2015 oder Lync Server 2013. Lync Server 2010 wird nicht unterstützt.<br/><br/>

     *    Eine **Warteschlange aufrufen** Weiterleitung des Anrufs an eine vorhandene Warteschlange aufrufen, die Sie eingerichtet haben.
     *    Eine andere **automatische Telefonzentrale**, erstellen Sie eine zweite Ebene im Menü Optionen, die ein Untermenü enthält. Diese werden geschachtelte Telefonzentralen bezeichnet. <br/><br/>
     
         > [!Note]
         > Standardmäßig werden alle während eines Zeitraums Feiertag eingehenden Anrufe festgelegt, trennen Sie nach der Ansage (falls vorhanden), müssen Sie eine Umleitung angeben, wenn ein anderes Verhalten ist erwünscht.

***
![Nummer 4](../images/sfbcallout4.png)<br/>**Wenn möchten Sie den Feiertag So starten und beenden?** Geben Sie den Anfangstermin Feiertag im Format mm/tt/jjjj, und wählen Sie dann eine Startzeit, Enddatum und Endzeit, wie in der Tabelle Datum Bereich dazu aufgefordert werden.<br/><br/>Sie können bis zu 10 verschiedene Datumsbereiche für einen Feiertag angeben. Sie könnten beispielsweise Datumsbereiche für Silvester Feiertage für bis zu 10 Jahre hinzufügen. Ein Feiertag kann mehrere Tage umfassen.<br/><br/>Zusätzliche hinzufügen Feiertag Datum Bereiche (zum Beispiel für das nächste Jahr), klicken Sie auf **einen anderen hinzufügen**, und geben Sie einen neuen Satz von Start- und Enddatum des Feiertags.<br/><br/>Geschachtelte Feiertage werden ebenfalls unterstützt. Beispielsweise könnten Sie mehrere Feiertage Zeitrahmen von einem "Feiertag Break-schachteln: 
*    **Dezember 24 bis Januar 3:** "Happy Feiertage! Unsere Büros sind derzeit geschlossen. Es wird auf 4. Januar öffnen Sie es erneut."
*    **Dezember 25:** "Fröhliche Weihnachten! Unsere Büros sind derzeit geschlossen. Es wird auf 4. Januar öffnen Sie es erneut."
*    **1. Januar:** "Happy neues Jahr! Unsere Büros sind derzeit geschlossen. Es wird auf 4. Januar öffnen Sie es erneut."
   
Nachdem Sie die automatische Telefonzentrale gespeichert haben, werden auf der Registerkarte **Feiertage** , in dem Sie bearbeiten, hinzufügen oder Ändern von Feiertag Einstellungen können Feiertage angezeigt.
  
### <a name="select-dial-scope-page"></a>Seite „Wählbereich auswählen"

Auf dieser Seite können Sie die Benutzer in Ihrer Organisation aufgelistet in Ihrem Verzeichnis und bereit zur Einwahl nach Name, wenn eine Person, die Aufrufe eingefügt werden Ihrer Organisation einrichten.
  
![Dial scope for searching with dial by name.](../images/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/>Für **Einschließen** gibt es zwei Optionen:
*    **Alle Online-Benutzern** Mit dieser Option kann alle Personen in Ihrer Organisation, die in Verzeichnissuche eingeschlossen werden. Alle Online-Benutzer mit einer Lizenz **Telefonsystem** als auch Benutzer gehostet: lokal mit Skype für Business Server 2015 oder Lync Server 2013, die Pläne Aufrufen in Office 365, haben aufgeführt. 
*    **Benutzerdefinierte** Wenn Sie diese Option verwenden, Sie können für eine Gruppe von Office 365, Verteilerliste oder Sicherheitsgruppe an, die in Ihrer Organisation erstellt wurde, suchen, und Personen hinzugefügt in Office 365, Verteilerliste, oder Sicherheitsgruppe, die entweder **sind Online-Benutzer mit einem Telefon-Lizenz** oder gehostete lokalen Skype für die Business Server 2015 oder Lync Server 2013. Sie können mehrere Office 365-Gruppen, Verteilerlisten und Sicherheitsgruppen hinzufügen. <br/><br/> 

    > [!Caution]
    > Lokale Benutzer aus der Bereitstellung von Lync Server 2010 wird nicht aufgeführt, wenn jemand das Verzeichnis mit Dial sucht nach Namen. 
***
![Nummer 2](../images/sfbcallout2.png)<br/>Verwenden die Option **ausschließen** , haben Sie zwei Optionen:
*    **Keine**: Wenn Sie diese Option verwenden, werden keine Onlinebenutzer von der Verzeichnissuche ausgeschlossen.. 
*    **Benutzerdefinierte** Wenn Sie diese Option verwenden, Sie können für eine Gruppe von Office 365, Verteilerliste oder Sicherheitsgruppe an, die in Ihrer Organisation erstellt wurde, suchen und alle Personen an diese Office 365 Gruppe Verteilerliste hinzugefügt oder Sicherheitsgruppen aus Verzeichnissuche ausgeschlossen. Sie können mehrere Office 365-Gruppen, Verteilerlisten und Sicherheitsgruppen hinzufügen. <br/><br/> 

    > [!Caution]
    > Lokale Benutzer aus der Bereitstellung von Lync Server 2010 wird nicht aufgeführt, wenn jemand das Verzeichnis mit Dial sucht nach Namen.          
   
> [!NOTE]
> Es kann bis zu 36 Stunden für einen neuen Benutzer haben ihre Namen in das Verzeichnis, wenn ein Benutzer Einwahl verwendet nach Namen für die Spracherkennung dauern. 
  
Nachdem Sie alle erforderlichen Felder eingeben und richten Sie arbeiten mit Menüs und Optionen, klicken Sie auf **Speichern**.
  
## <a name="editing-and-testing-auto-attendants"></a>Bearbeiten und Testen von automatischen Telefonzentralen

Nachdem Sie die automatische Telefonzentrale gespeichert haben, wird sie auf der Seite **automatische Telefonzentralen** eingetragen sein. Dadurch können Sie schnell einige Optionen anzuzeigen, die Sie nach oben, festgelegt haben, einschließlich Name, Rufnummer, Sprache und Status.
  
Wenn Sie eine automatische Telefonzentrale ändern möchten, wählen Sie die automatische Telefonzentrale aus, und klicken Sie dann im Bereich Aktion auf **Bearbeiten**.
  
Sie können einen Testanruf an die automatische Telefonzentrale auch schnell mithilfe der Schaltfläche **Testen** im Aktionsbereich platzieren.
  
## <a name="want-to-know-more"></a>Möchten Sie mehr wissen?

Sie können auch Windows PowerShell verwenden, um automatische Telefonzentralen zu erstellen und einzurichten.
  
### <a name="auto-attendant-cmdlets"></a>Cmdlets für automatische Telefonzentralen

Zum Verwalten einer automatischen Telefonzentrale benötigen Sie die folgenden Cmdlets.
  
||| 
|---|---|
[Neue CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796493.aspx)                                                                      | [Neue CsOrganizationalAutoAttendantPrompt](https://technet.microsoft.com/en-us/library/mt796484.aspx)                                                              |
| [Set-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796486.aspx)                                                                      | [Neue CsOrganizationalAutoAttendantMenuOption](https://technet.microsoft.com/en-us/library/mt796485.aspx)                                                           |
| [Get-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796482.aspx)                                                                      | [Get-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/en-us/powershell/module/skype/get-csorganizationalautoattendantholidays?view=skype-ps)       |
| [Remove-CsOrganizationalAutoAttendant](https://technet.microsoft.com/en-us/library/mt796492.aspx)                                                                   | [Neue CsOrganizationalAutoAttendantMenu](https://technet.microsoft.com/en-us/library/mt796488.aspx)                                                                  |
| [New- CsOnlineAudioFile](https://technet.microsoft.com/en-us/library/mt796479.aspx)                                                                                 | [Neue CsOrganizationalAutoAttendantCallFlow](https://technet.microsoft.com/en-us/library/mt796489.aspx)                                                              |
| [Export-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/en-us/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps) | [Neue CsOnlineTimeRange](https://technet.microsoft.com/en-us/library/mt796491.aspx)                                                                                  |
| [Neue CsOnlineDateTimeRange](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)                                       | [Neue CsOnlineSchedule](https://technet.microsoft.com/en-us/library/mt796490.aspx)                                                                                   |
| [Get-CsOrganizationalAutoAttendantSupportedTimeZone](https://technet.microsoft.com/en-us/library/mt796483.aspx)                                                     | [Neue CsOrganizationalAutoAttendantCallHandlingAssociation](https://technet.microsoft.com/en-us/library/mt796487.aspx)                                               |
| [Get-CsOrganizationalAutoAttendantSupportedLanguage](https://technet.microsoft.com/en-us/library/mt796481.aspx)                                                     | [Import-CsOrganizationalAutoAttendantHolidays](https://docs.microsoft.com/en-us/powershell/module/skype/import-csorganizationalautoattendantholidays?view=skype-ps) |
| [Neue CsOrganizationalAutoAttendantCallableEntity](https://technet.microsoft.com/en-us/library/mt796480.aspx)                                                      |  |   |
   
### <a name="more-about-windows-powershell"></a>Weitere Informationen zu Windows PowerShell

- In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Warum müssen Sie mithilfe von Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Verwandte Themen
[Hier ist das Ergebnis in das Telefonsystem in Office 365](here-s-what-you-get-with-phone-system.md)

[Abrufen von Telefonnummern Service für Skype für Unternehmen und die Microsoft-Teams](getting-service-phone-numbers.md)

[Verfügbarkeit von Ländern und Regionen für Audiokonferenzen und plant aufrufen](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    

