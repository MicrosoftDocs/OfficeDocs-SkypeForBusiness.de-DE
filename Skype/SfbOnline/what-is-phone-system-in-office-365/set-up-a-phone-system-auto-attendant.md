---
title: Einrichten einer automatischen Telefonzentrale für das Telefonsystem
author: CarolynRowe
ms.author: crowe
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
ms.openlocfilehash: 79a3292ea15781d448f0931c18a9ed98cd351f01
ms.sourcegitcommit: 60e8365281ec6d780f1b2439bedef0bd71f002d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2019
ms.locfileid: "30046764"
---
# <a name="set-up-a-phone-system-auto-attendant"></a>Einrichten einer automatischen Telefonzentrale für das Telefonsystem

Automatische Telefonzentralen ermöglichen es Personen, die in Ihrer Organisation anrufen, über ein Menüsystem zur richtigen Abteilung, Warteschlange, Person oder dem Telefonisten zu gelangen. Sie können eine automatische Telefonzentrale für Ihre Organisation einrichten, indem Sie das Skype for Business Admin Center verwenden. Zum Erstellen einer neuen automatischen Telefonzentrale, wechseln zur **Anrufrouting** im linken Navigationsbereich, und wählen Sie **automatische Telefonzentralen** > **Hinzufügen**.

Wenn Sie weitere Informationen zu automatischen Telefonzentralen finden möchten, finden Sie unter [Was Telefonsystem automatischen Telefonzentralen sind?](/microsoftteams/what-are-phone-system-auto-attendants)

## <a name="step-1---getting-started"></a>Schritt 1 - Erste Schritte

- Before you can create and set up your auto attendants, you will need to get or transfer your existing toll or toll-free service numbers. Nachdem Sie die gebührenpflichtige oder gebührenfreie Service Zahlen erhalten möchten, sie werden angezeigt, auf die **Skype für Business Administrationscenter** > **VoIP** > Seite**Rufnummern** . Um die Rufnummern Service erhalten möchten, finden Sie unter [Getting Service Rufnummern für Skype für Unternehmen und die Microsoft-Teams](getting-service-phone-numbers.md)oder für Übertragung und vorhandenen Service-Nummer, finden Sie unter [Übertragen von Telefonnummern zu Office 365](/microsoftteams/transfer-phone-numbers-to-office-365). **User (subscriber)** numbers can't be assigned to auto attendants. Wenden Sie sich außerhalb der USA, können Sie mithilfe der Skype für Business Administrationscenter Service Zahlen abrufen; Klicken Sie [hier](/microsoftteams/manage-phone-numbers-for-your-organization) stattdessen.

    > [!CAUTION]
    > Zum Abrufen und gebührenfreien Telefonnummern verwenden, müssen Sie Communications haben einrichten. Hierzu finden Sie [Was sind Communications haben?](/microsoftteams/what-are-communications-credits) und [Communications haben für Ihre Organisation einrichten](/microsoftteams/set-up-communications-credits-for-your-organization).
  
- Ihre Organisation muss eine Lizenz Enterprise E3 plus **Telefonsystem** oder einer E5 Enterprise-Lizenz (mindestens) verfügen. Die Anzahl der **Telefonsystem** Benutzerlizenzen, die zugewiesen sind, wirkt sich auf die Anzahl der Dienst Zahlen, die für automatische Telefonzentralen zu verwendende verfügbar sind. Die Nummern der automatischen Telefonzentralen können Ihnen ist abhängig von die Zahlen **Telefonsystem** und **Audiokonferenzen** -Lizenzen, die in Ihrer Organisation zugewiesen sind. Weitere Informationen zur Lizenzierung finden Sie [hier](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

    > [!TIP]
    > Zum Umleiten von Anrufen an einen Operator oder eine Menüoption, die ein Benutzer Online mit einer Lizenz **Telefonsystem** ist, müssen Sie für Enterprise-VoIP zu aktivieren oder Aufrufen in Office 365-Pläne ihnen zuweisen. Siehe [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Sie können auch die Windows PowerShell verwenden. Führen Sie beispielsweise Folgendes aus:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
## <a name="step-2---create-a-new-auto-attendant"></a>Schritt 2 - Erstellen einer neuen automatischen Telefonzentrale

 **Verwenden das Microsoft-Teams, Administrationscenter**

Klicken Sie in der **Microsoft-Teams, Administrationscenter**auf ![Sfb-Logo-30x30.png](../images/sfb-logo-30x30.png) **Legacy-Portal** >  **Anrufrouting** > **automatische Telefonzentralen**, klicken Sie dann auf **+ Neues hinzufügen**:

### <a name="edit-general-info-page"></a>Seite „Allgemeine Informationen bearbeiten"

![New auto attendant page 1.](../images/edacec94-9384-4a87-be0a-5c49a151287e.png)

***
![Nummer 1](../images/sfbcallout1.png)<br/>**Name** Geben Sie einen aussagekräftigen Anzeigenamen für die automatische Telefonzentrale. Der Name ist erforderlich und kann maximal 64 Zeichen einschließlich Leerzeichen enthalten. Er wird in der Spalte **Name** der Registerkarte **Automatische Telefonzentralen** aufgeführt.
***

![Nummer 2](../images/sfbcallout2.png)<br/>**Telefonnummer** Diese Einstellung ist optional. Wenn Sie möchten, wählen Sie eine Rufnummer für die automatische Telefonzentrale. Sie können auswählen, alle verfügbaren Service gebührenpflichtige oder gebührenfreie Telefonnummer, die Sie für Ihre Organisation müssen. Wenn keine Telefonnummern aufgeführt sind, müssen Sie sich eine gebührenpflichtige oder gebührenfreie Telefonnummer besorgen.  [Hier klicken](getting-service-phone-numbers.md), um diese zu erhalten. <br/> <br/>

> [!NOTE]
> **User (subscriber)** numbers can't be assigned to auto attendants.

***
![Nummer 3](../images/sfbcallout3.png)<br/>**Zeitzone**: Sie müssen die Zeitzone für Ihre automatische Telefonzentrale festlegen. Die Zeitzone muss jedoch nicht der Zeitzone der für Ihre Organisation angegebenen Hauptadresse entsprechen. Sie können für jede automatische Telefonzentrale eine andere Zeitzone festlegen. Die Geschäftszeiten für die automatische Telefonzentrale werden basierend auf der Zeitzone festgelegt, die Sie hier auswählen.
***
![14](../images/sfbcallout4.png)<br/>**Sprache**: Wählen Sie unter den aufgeführten verfügbaren Sprachen die Sprache aus, die Sie für die automatische Telefonzentrale verwenden möchten. Die Sprache, die Sie hier festlegen, wird die Sprache, die die automatische Telefonzentrale zum interagieren mit Personen, die diese automatische Telefonzentrale anrufen, und fordert das System werden in dieser Sprache wiedergegeben werden.
***
![Nummer 5](../images/sfbcallout5.png)<br/>**Spracherkennung** Spracherkennung verfügbar ist und wenn diese Option ausgewählt ist. Personen, die in aufrufen können Spracheingaben in der Sprache, die Sie festlegen. Sie können die Spracherkennung deaktivieren, indem Sie es löschen, wenn Sie nur Personen, die ihre Telefontastatur verwenden können möchten.
***
![Nummer 6](../images/sfbcallout6.png)<br/>**Operator**: Diese Einstellung ist optional und muss für die automatische Telefonzentrale nicht festgelegt werden. Sie können jedoch die Option **Operator** für die Personen festlegen, die im Unterbrechungsmodus außerhalb des Kontextmenüs an eine Person, die sie unterstützen sprechen können aufrufen. <br/> <br/> Die Taste „0" wird automatisch der Vermittlung zugewiesen. <br/> <br/> Wenn Sie dies festlegen, müssen Sie auch Personen mitteilen, die aufgerufen wird, insofern Dies ist eine verfügbare Option in den **Menüoptionen im bearbeiten** auf der Seite **Geschäftszeiten Behandlung aufrufen** . Wenn Sie einen Operator für die automatische Telefonzentrale festlegen, müssen Sie geben den entsprechenden Prompt Text im Feld **Anrufer hören** oder Ändern Ihrer Audiodatei, wenn Sie diese Option. Beispiel: „Drücken Sie ‚0', um mit der Vermittlung zu sprechen". <br/><br/>  Als Vermittlung können Sie Folgendes festlegen: 
*    **Person in Ihrem Unternehmen** mit einer **Telefonsystem**-Lizenz, die für Enterprise Voice aktiviert oder Anruf-Plänen in Office 365 zugeordnet ist. <br/>

     > [!Note] 
     > **Die Person in Ihrem Unternehmen** kann ein Online-Benutzer oder ein vor Ort gehosteter Benutzer sein, der den Skype for Business Server 2015 oder den Lync Server 2013 verwendet. Der Lync Server 2010 wird nicht unterstützt. <br/> 

* Eine **Anrufwarteschleife**, die Sie eingerichtet haben 
* Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Zu diesem Zweck wählen Sie **Person in Ihrem Unternehmen** aus, und legen Sie diese Person Anrufe an die Voicemail weitergeleitet werden. 

### <a name="select-hours-of-operation-page"></a>Seite „Geschäftszeiten auswählen"

Standardmäßig werden Geschäftszeiten auf 24 Stunden am Tag, 7 Tage die Woche festgelegt, damit alle Zeiten als Geschäftszeiten gelten. Alle Zeiten, die nicht innerhalb der Geschäftszeiten liegen, werden als außerhalb der Geschäftszeiten angesehen. Wenn Sie die Option **Benutzerdefiniert** und Geschäftszeiten festlegen, wird eine neue Seite wird aufgerufen, **nachdem Stunden Behandlung aufrufen** , in dem Sie den Anruf behandeln für Geschäftszeiten für die automatische Telefonzentrale konfigurieren können hinzugefügt werden.

![New auto attendant Hours of operation.](../images/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

***
![Nummer 1](../images/sfbcallout1.png)<br/>Wählen Sie die Option **Benutzerdefiniert** aus, um bestimmte Geschäftszeiten im Kalender auszuwählen. Wenn Sie **Benutzerdefiniert** auswählen, werden die Geschäftszeiten standardmäßig auf Montag bis Freitag von 9:00 Uhr bis 17:00 Uhr festgelegt.
***
![Nummer 2](../images/sfbcallout2.png)<br/>Um Geschäftszeiten zu ändern, markieren Sie die Geschäftszeiten, die Sie einstellen möchten, im Kalender. Der Kalender ermöglicht Ihnen die Auswahl von Geschäftszeiten in Abständen von 30 Minuten, und die Geschäftszeiten, die Sie hier auswählen, werden entsprechend der Zeitzone eingestellt, die Sie auf der Seite „ **Allgemeine Daten“** festlegen. Um eine Pause (beispielsweise eine Mittagspause) einzurichten, deaktivieren, oder ziehen Sie zum Deaktivieren die Zeit im Kalender. Sie können innerhalb der Geschäftszeiten mehrere Pausen festlegen. 

### <a name="select-business-hours-call-handling-page"></a>Auswählen von Geschäftszeiten aus der Seite für die Anruf-Behandlung

> [!TIP]
> Wenn Sie einen benutzerdefinierten Zeitplan für die Geschäftszeiten verwenden, müssen Sie auch die Anrufbehandlung außerhalb der Geschäftszeiten einrichten. Es wird eine Seite namens **Anrufbehandlung nach Geschäftsschluss** hinzugefügt, auf der Sie diese Optionen konfigurieren können. Dafür stehen die gleichen Optionen zur Verfügung wie für **Anrufbehandlung während der Geschäftszeiten**. 

Begrüßungen, Ansagen und Menüs können, die es Benutzern eingerichtet werden, die während der Geschäftszeiten Anruf in Ihrer Organisation Auto attendant Telefonnummer hören kann.

![Business hours call handling.](../images/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)

***
![Nummer 1](../images/sfbcallout1.png)<br/>**Begrüßung durch das Unternehmen:** Die Begrüßung während der Geschäftszeiten ist optional und kann auf **keine**festgelegt werden. In diesem Fall hört der Anrufer keine Meldung oder die Ansage, bevor der Anruf durch eine der Optionen verarbeitet wird, die Sie auswählen. Sie können auch eine Audiodatei hochladen (im WAV-, MP3- oder WMA-Format) oder eine benutzerdefinierte Begrüßung der Sprachausgabe verwenden.
* **Keine:** Wenn Personen die automatische Telefonzentrale unter dieser Telefonnummer anrufen, wird keine Ansage wiedergegeben.
*    **Erstellen einer benutzerdefinierten Ansage:** Wenn Sie diese Option auswählen, geben Sie den Text (bis zu 1000 Zeichen) ein, der vom System gelesen werden soll. Beispielsweise können Sie „Willkommen bei Contoso, Ihr Anruf ist uns sehr wichtig“ im Feld **Anrufer hört** eingeben.
* **Hochladen einer Audiodatei:** Wenn Sie diese Option wählen, zeichnen Sie die Begrüßung auf und laden Sie anschließend Ihre Audiodatei hoch (im wav-, .mp3- oder .wma-Format).
***
![Nummer 2](../images/sfbcallout2.png)<br/>Sie können auswählen, was mit Anrufen geschieht, die während der Geschäftszeiten eingehen. Sie können aus den folgenden Optionen wählen:
* **Verbindung trennen:** Wenn Sie diese Option auswählen, wird die Verbindung der Anrufer nach einer Begrüßung mit Informationen zu den Geschäftszeiten getrennt.
* **Umleiten von Anrufen:** Dies kann verwendet werden, um den Anruf automatisch weiterzuleiten, an:
  * **Person in Ihrem Unternehmen** mit einer **Telefonsystem**-Lizenz, die für Enterprise Voice aktiviert oder Anruf-Plänen in Office 365 zugeordnet ist. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Zu diesem Zweck wählen **Person in Ihrem Unternehmen** aus, und legen Sie diese Person ihre Anrufe an die Voicemail weitergeleitet werden. <br/><br/>
    > [!Note]
    > **Die Person in Ihrem Unternehmen** kann ein Online-Benutzer oder ein vor Ort gehosteter Benutzer sein, der den Skype for Business Server 2015 oder den Lync Server 2013 verwendet. Der Lync Server 2010 wird nicht unterstützt. <br/><br/>

  * Eine **Warteschlange:** Die Verwendung einer Warteschlange ermöglicht, dass ein Anruf in eine bestehende Anruf-Warteschlange weitergeleitet werden kann, die Sie einrichten müssen.
  * Weitere **automatische Telefonzentrale** Sie können eine bestehende automatische Telefonzentrale verwenden, um eine zweite Ebene von Menüoptionen zu erstellen, die ein untergeordnetes Teilmenü enthält. Diese werden als geschachtelte automatische Telefonzentralen bezeichnet.

* **Menü-Optionen Eingabe-Aufforderung wiedergeben** Diese können auch dazu verwendet werden, damit Sie eine Eingabe-Aufforderung einrichten können, die abgespielt werden soll.
***
![Nummer 3](../images/sfbcallout3.png)<br/>**Menü-Eingabeaufforderung**: Um eine Ansage für das Hauptmenü zu erstellen, können Sie Text-zu-Sprache verwenden oder eine Audiodatei (im WAV-, MP3- oder WMA-Format) hochladen. Sie können die Ansage in das Feld **Anrufer hören** eingeben oder eine Audiodatei aufzeichnen und zum Beispiel Folgendes sagen: „Drücken oder sagen Sie ‚1' für den Vertrieb. Drücken oder sagen Sie ‚2' für den Service. Drücken oder sagen Sie ‚3' für den Kundendienst. Drücken oder sagen Sie ‚0' für die Vermittlung. Um dieses Menü erneut zu hören, drücken Sie die Sterntaste, oder sagen Sie ‚Wiederholen'." **Eine benutzerdefinierte Aufforderung erstellen**: Wenn Sie diese Option ausgewählt haben, müssen Sie den Text eingeben, der vom System vorgelesen werden soll (maximal 1.000 Zeichen). **Eine Audio-Datei hochladen**: Wenn Sie diese Option ausgewählt haben, müssen Sie die Begrüßung aufzeichnen und dann Ihre Audiodatei (im WAV-, MP3- oder WMA-Format) hochladen.
***
![Nummer 4](../images/sfbcallout4.png)<br/>**Wählen Sie nach Namen** Wenn Sie diese Option auswählen, können diese Personen, die in die Suche nach Personen in Ihrer Organisation mithilfe der Verzeichnissuche aufrufen. Sie können auswählen, welche Personen für die Namensanwahl als verfügbar oder nicht verfügbar aufgelistet werden, indem Sie diese Optionen auf der Seite **Wählbereich** einrichten. Jeder Online-Benutzer mit einer **Telefonsystem**-Lizenz oder ein beliebiger Benutzer der vor Ort gehostet wird und den Skype for Business Server 2015 oder den Lync Server 2013 verwenden, finden Sie unter nach Namen wählen.<br/><br/>  

> [!WARNING]
> Benutzer, die lokal gehostet werden und Lync 2010 verwenden, können mit nach Namen wählen **nicht erreicht werden**.
> ***

![Nummer 5](../images/sfbcallout5.png)<br/>**Edit menu options** Menu options can be added or removed by using key buttons on the keypad. Um eine Menüoption hinzuzufügen, drücken Sie die entsprechende Taste auf der Tastatur. The keys in use will change in color and the corresponding row of options will appear below. Um eine Menüoption zu löschen, klicken Sie einfach auf den entsprechenden Schlüssel für die Tastatur-Steuerelement, um dieser Schlüssel deaktivieren. Die Zeile der Tastenzuordnung wird entfernt.<br/><br/>  **Tipp:** Sie müssen im Menü Ansagen Text aktualisieren oder erneut zeichnet separat beim Entfernen von Optionen, da dies automatisch für die Aufforderung zur vorhandenen Menü erfolgen wird nicht hinzugefügt.  <br/><br/>  Alle Menüoption hinzugefügt und in beliebiger Reihenfolge entfernt werden kann, und die tastenzuordnungen müssen nicht zusammenhängend sein. Es ist beispielsweise möglich, erstellen Sie ein Menü mit Tasten 0, 1 und 3 auf Optionen, zugeordnet werden, während die Taste 2 nicht verwendet wird.<br/><br/> 

> [!NOTE]
> Die Tasten * (Wiederholung) und # (zurück) werden vom System reserviert und können nicht neu zugewiesen werden. Wenn die Spracherkennung aktiviert ist, drücken * wird mit "Wiederholen" entsprechen und # wird mit "Zurück" Sprachbefehle entsprechen.


Um Ihre Menüoptionen einzurichten, nachdem Sie die Taste(n) ausgewählt haben, müssen Sie: 
- **Den Namen der Option eingeben** Dieser kann bis zu 64 Zeichen lang sein und mehrere Wörter enthalten, wie „Kundenservice“ oder „Vorgänge und Gründe“. Wenn die Spracherkennung aktiviert ist, wird der Name automatisch erkannt und der Anrufer kann entweder auf 3 drücken, „drei“ oder „Kundenservice“ sagen, um die der Taste 3 zugeordnete Option auszuwählen. 
- Der nächste Schritt besteht darin, auszuwählen, wohin der Anruf nach Betätigung der entsprechenden Taste oder der Option, die mittels Spracherkennung ausgewählt wird, gesendet wird. Der Anruf kann gesendet werden an: 
    - **Den Vermittler:** Wenn der Vermittler bereits eingerichtet wurde, wird dieser automatisch der Taste 0 zugeordnet, kann aber auch gelöscht oder einer anderen Taste zugeordnet werden. Wenn der Vermittler keiner Taste zugeordnet ist, wird auch der VoIP-Befehl „Vermittler“ deaktiviert. 
    - **Einer Person in Ihrem Unternehmen** mit einer **Telefonsystem** -Lizenz, die für Enterprise Voice aktiviert oder Anruf-Plänen in Office 365 zugeordnet ist. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Zu diesem Zweck wählen **Person in Ihrem Unternehmen** aus, und legen Sie diese Person ihre Anrufe an die Voicemail weitergeleitet werden.<br/><br/> 

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
* **Keine:** Wenn Personen die automatische Telefonzentrale unter dieser Telefonnummer anrufen, wird keine Ansage wiedergegeben.
* **Erstellen einer benutzerdefinierten Ansage:** Wenn Sie diese Option auswählen, geben Sie den Text (bis zu 1000 Zeichen) ein, der vom System gelesen werden soll. Beispielsweise können Sie „Frohes Neues Jahr!“, unsere Büros sind derzeit geschlossen“ im Feld **Anrufer hört** eingeben.
* **Hochladen einer Audiodatei:** Wenn Sie diese Option wählen, zeichnen Sie die Begrüßung auf und laden anschließend Ihre Audiodatei hoch (im wav-, .mp3- oder .wma-Format).  
***
![Nummer 3](../images/sfbcallout3.png)<br/>**Was geschieht mit den Anrufen nach der Begrüßung?** Sie können auswählen, was mit den Anrufen geschieht, die während dieses Feiertags eingehen. Sie können aus den folgenden Optionen wählen:
* **Verbindung trennen** Die Verbindung des Anrufers wird getrennt, nachdem er die Feiertags-Nachricht gehört hat.
* **Umleiten von Anrufen:** Dies kann verwendet werden, um den Anruf automatisch weiterzuleiten, an:
  * Eine **Person in Ihrem Unternehmen** mit einer **Telefonsystem** -Lizenz, die für Enterprise Voice aktiviert oder Anruf-Plänen in Office 365 zugeordnet ist. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Zu diesem Zweck wählen **Person in Ihrem Unternehmen**aus, und legen Sie diese Person ihre Anrufe an die Voicemail weitergeleitet werden. <br/><br/> 

    > [!Note] 
    > **Die Person in Ihrem Unternehmen** kann ein Online-Benutzer oder ein vor Ort gehosteter Benutzer sein, der den Skype for Business Server 2015 oder den Lync Server 2013 verwendet. Der Lync Server 2010 wird nicht unterstützt.<br/><br/>

  * Eine **Anruf-Warteschlange** zur Weiterleitung des Anrufs an eine vorhandene Anruf-Warteschlange, die Sie eingerichtet haben.
  * Eine andere **automatische Telefonzentrale** für die Erstellng einer zweiten Ebene von Menüoptionen, die ein untergeordnetes Teilmenü enthalten. Diese werden als geschachtelte automatische Telefonzentralen bezeichnet. <br/><br/>

    > [!Note]
    > Standardmäßig werden alle während eines Feiertags eingehenden Anrufe festgelegt, deren Verbindung nach der Ansage (falls vorhanden) getrennt wird, somit müssen Sie eine Umleitung angeben, wenn ein anderes Verhalten erwünscht ist.

***
![Nummer 4](../images/sfbcallout4.png)<br/>**Wann möchten Sie, dass der Feiertag beginnt und wann soll er enden?** Geben Sie den Anfangstermin für den Feiertag im Format mm/tt/jjjj an und wählen Sie dann eine Startzeit, ein Enddatum und einen Endzeitpunkt, wenn Sie in der Tabelle Datumsbereich dazu aufgefordert werden.<br/><br/>Sie können bis zu 10 verschiedene Datumsbereiche für einen Feiertag angeben. Sie könnten beispielsweise Datumsbereiche für Silvester-Feiertage für bis zu 10 Jahre hinzufügen. Ein Feiertag kann mehrere Tage umfassen.<br/><br/>Um Feiertagen zusätzliche Datumsbereiche hinzuzufügen, (zum Beispiel für das nächste Jahr), klicken Sie auf **Einen weiteren hinzufügen** und geben Sie einen neuen Satz von Start- und Enddatum des Feiertags ein.<br/><br/>Geschachtelte Feiertage werden ebenfalls unterstützt. Beispielsweise könnten Sie mehrere Feiertage in einen Zeitrahmen „Feiertage“ ein: 
* **24. Dezember bis 03. Januar:** „Fröhliche Feiertage! Unsere Büros sind derzeit geschlossen. Ab dem 4. Januar sind wir wieder für Sie da.“
* **25. Dezember:** „Fröhliche Weihnachten! Unsere Büros sind derzeit geschlossen. Ab dem 4. Januar sind wir wieder für Sie da.“
* **1. Januar:** „Frohes neues Jahr! Unsere Büros sind derzeit geschlossen. Ab dem 4. Januar sind wir wieder für Sie da.“

Nachdem Sie die automatische Telefonzentrale gespeichert haben, erscheinen Ihre Feiertage auf der Registerkarte **Feiertage**, auf der Sie die Einstellungen zu den Feiertagen bearbeiten, hinzufügen oder ändern können.

### <a name="select-dial-scope-page"></a>Seite „Wählbereich auswählen"

Auf dieser Seite können Sie die Benutzer in Ihrer Organisation aufgelistet in Ihrem Verzeichnis und bereit zur Einwahl nach Name, wenn eine Person, die Aufrufe eingefügt werden Ihrer Organisation einrichten.

![Dial scope for searching with dial by name.](../images/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

***
![Nummer 1](../images/sfbcallout1.png)<br/>Für **Einschließen** gibt es zwei Optionen:
* **Alle Onlinebenutzer**: Wenn Sie diese Option verwenden, können alle Benutzer in Ihrer Organisation in eine Verzeichnissuche eingeschlossen werden. Alle Online-Benutzer mit einer **Telefonsystem**-Lizenz und auch lokal gehostete Benutzer, die den Skype for Business Server 2015 oder den Lync Server 2013 verwenden, die Anruf-Pläne in Office 365 haben, werden aufgeführt. 
* **Benutzerdefiniert:** Wenn Sie diese Option verwenden, können Sie nach einer Gruppe von Office 365, Verteilerliste oder Sicherheitsgruppe suchen, die in Ihrer Organisation erstellt wurde und nach Personen, die in Office 365, einerVerteilerliste, oder Sicherheitsgruppe hinzugefügt wurden und entweder **Online-Benutzer mit einer Telefon-Lizenz** oder lokal gehostete, die den Skype for Business Server 2015 oder Lync Server 2013 verwenden. Sie können mehrere Office 365-Gruppen, Verteilerlisten und Sicherheitsgruppen hinzufügen. <br/><br/> 

  > [!Caution]
  > Lokale Benutzer aus der Bereitstellung von Lync Server 2010 wird nicht aufgeführt, wenn jemand das Verzeichnis mit Dial sucht nach Namen. 
***
![Nummer 2](../images/sfbcallout2.png)<br/>Verwenden die Option **ausschließen** , haben Sie zwei Optionen:
* **Keine**: Wenn Sie diese Option verwenden, werden keine Onlinebenutzer von der Verzeichnissuche ausgeschlossen.. 
* **Benutzerdefinierte** Wenn Sie diese Option verwenden, Sie können für eine Gruppe von Office 365, Verteilerliste oder Sicherheitsgruppe an, die in Ihrer Organisation erstellt wurde, suchen und alle Personen an diese Office 365 Gruppe Verteilerliste hinzugefügt oder Sicherheitsgruppen aus Verzeichnissuche ausgeschlossen. Sie können mehrere Office 365-Gruppen, Verteilerlisten und Sicherheitsgruppen hinzufügen. <br/><br/> 

  > [!Caution]
  > Lokale Benutzer aus der Bereitstellung von Lync Server 2010 wird nicht aufgeführt, wenn jemand das Verzeichnis mit Dial sucht nach Namen.

> [!NOTE]
> Es kann bis zu 36 Stunden für einen neuen Benutzer haben ihre Namen in das Verzeichnis, wenn ein Benutzer Einwahl verwendet nach Namen für die Spracherkennung dauern. 

Nachdem Sie alle erforderlichen Felder eingeben und richten Sie arbeiten mit Menüs und Optionen, klicken Sie auf **Speichern**.

## <a name="editing-and-testing-auto-attendants"></a>Bearbeiten und Testen von automatischen Telefonzentralen

Wenn Sie Ihre automatische Telefonzentrale gespeichert haben, wird diese auf der Seite **Automatische Telefonzentralen** aufgeführt. Dadurch können Sie schnell einige Optionen anzuzeigen, die Sie nach oben, festgelegt haben, einschließlich Name, Rufnummer, Sprache und Status.

Wenn Sie eine automatische Telefonzentrale ändern möchten, wählen Sie die automatische Telefonzentrale aus, und klicken Sie dann im Bereich Aktion auf **Bearbeiten**.

Sie können einen Testanruf an die automatische Telefonzentrale auch schnell mithilfe der Schaltfläche **Testen** im Aktionsbereich platzieren.

## <a name="want-to-know-more"></a>Möchten Sie mehr wissen?

Sie können auch Windows PowerShell verwenden, um automatische Telefonzentralen zu erstellen und einzurichten.

### <a name="auto-attendant-cmdlets"></a>Cmdlets für automatische Telefonzentralen

Zum Verwalten einer automatischen Telefonzentrale benötigen Sie die folgenden Cmdlets.

|| |
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

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 und Skype verwalten, für die Business Online verwenden eine zentrale Verwaltung, die Ihrer täglichen Arbeit vereinfachen können, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

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
