---
title: Was sind automatische Cloudtelefonzentralen?
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.date: 4/2/2019
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.autoattendants.overview
ms.custom:
- Phone System
description: Enthält Informationen zu Cloud-Telefonzentralen und deren Verwendung.
ms.openlocfilehash: 99310e44fbab43e16d0816acdb8a85815863b286
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32211693"
---
# <a name="what-are-cloud-auto-attendants"></a>Was sind automatische Cloudtelefonzentralen?

Telefonsystem in Office 365 bietet automatische Telefonzentralen, die verwendet werden kann, um zu externen lassen und interne Anrufer über ein Menüsystem platzieren, und durchstellen von Anrufen an Unternehmen Benutzer oder Abteilungen in Ihrer Organisation verschieben.
  
Eine automatische Telefonzentrale ist eine Reihe von Ansagen oder audio-Dateien, die anstelle einer human Operator Anrufer hören, wenn sie eine Organisation anrufen. Beim Aufruf von Personen einer Zahl, die eine automatische Telefonzentrale zugeordnet können ihre Optionen leiten den Anruf an einen Benutzer oder Suchen nach einer Person in Ihrer Organisation und dem betreffenden Benutzer verbinden. Sie können ihre Auswahl express und interagieren mit dem Menüsystem mithilfe eines Telefontastatur (MFV) oder die Spracherkennung.
  
Um eine automatische Telefonzentrale für das Telefonsystem in Office 365 einzurichten, gehen Sie zu [einer Cloud-Telefonzentrale einrichten](create-a-phone-system-auto-attendant.md).
  
Eine Cloud-Telefonzentrale bietet Folgendes:
  
- Sie kann Unternehmensbegrüßungen oder informative Begrüßungen bereitstellen.
- Sie kann benutzerdefinierte Unternehmensmenüs bereitstellen. Diese Menüs können Sie so anpassen, dass sie aus mehreren Ebenen bestehen.
- Es bietet Verzeichnissuche finden, die die Personen, die ermöglicht in aufrufen, um im Verzeichnis der Organisation für einen Namen zu suchen.
- Sie können einer Person, die Anrufe in erreichen, oder lassen Sie eine Nachricht für eine Person in Ihrer Organisation.
- Es unterstützt mehrere Sprachen für ansagen, Text-Sprach- und die Spracherkennung.
- Angeben von Feiertagen und Geschäftszeiten unterstützt.
- Übertragen der Anruf an einen Operator, der andere Benutzer, Anruf Warteschlangen und automatischen Telefonzentralen unterstützt.

> [!NOTE]
> Dieser Artikel bezieht sich auf Microsoft-Teams und Skype für Business Online.

## <a name="getting-started"></a>Erste Schritte

Die folgenden Punkte sind bei Ihrem Einstieg in die Verwendung von automatischen Telefonzentralen wichtig:

- Eine automatische Telefonzentrale ist erforderlich, um ein Ressourcenkonto zugeordneten verfügen. Details auf Ressourcenkonten finden Sie unter [Manage Ressourcenkonten in Teams](manage-resource-accounts.md) .
- Wenn Sie eine direkte Routing Number zuweisen möchten, müssen Sie erwerben und weisen Sie die folgenden Lizenzen der Ressourcenkonten \(Office 365 Enterprise E1, E3 oder E5, mit dem Telefonsystem Add-on\).
- Wenn Sie stattdessen eine Microsoft-Dienst Zahl zuordnen möchten, müssen Sie erwerben und weisen Sie Ihr Ressourcenkonto folgenden Lizenzen \(Office 365 Enterprise E1, E3 oder E5, mit dem Telefonsystem Add-on und Aufrufen planen\).
- Sie müssen nur die Ressourcenkonten mit einer Telefonnummer, die ihnen zugewiesenen lizenzieren. In einer geschachtelten automatische Telefonzentrale oder ein Anruf die Warteschlange müssen Sie nicht den Rest der automatischen Telefonzentralen lizenzieren, oder rufen Sie Warteschlangen aus, wenn keine ihnen zugeordnete Telefonnummern vorhanden sind. 

> [!NOTE]
> Direkte Routing Service Zahlen für die automatische Telefonzentrale und Anruf Warteschlangen werden gegenwärtig nur für Microsoft-Teams, Benutzer und Agents unterstützt.

> [!NOTE]
> Microsoft arbeitet eine entsprechende Lizenzierungsmodell für Anwendungen wie Cloud automatische Telefonzentrale und den Anruf-Warteschlangen für an jetzt Sie das Benutzerlizenzierung Objektmodell verwenden müssen.
    
   > [!TIP]
   > Zum Umleiten von Anrufen an einen Operator oder eine Menüoption, die ein Benutzer Online mit einer Lizenz **Telefonsystem** ist, müssen Sie für Enterprise-VoIP zu aktivieren oder zu diesen zuweisen plant aufrufen. Finden Sie unter [Microsoft-Teams, Zuweisen von Lizenzen](assign-teams-licenses.md). Sie können auch die Windows PowerShell verwenden. Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Zum Abrufen und gebührenfreie Service Zahlen für die automatische Telefonzentralen verwenden, müssen Sie Communications haben einrichten. Hierzu finden Sie unter [Was sind Communications haben?](what-are-communications-credits.md) und [Communications haben für Ihre Organisation einrichten](set-up-communications-credits-for-your-organization.md).

    > [!IMPORTANT]
    > Telefonnummern von Benutzern (Abonnenten) können automatischen Telefonzentralen nicht zugewiesen werden - es können nur gebührenpflichtige oder gebührenfreie Telefonnummern verwendet werden.

- Eine vollständige Auto attendant System wird gewöhnlich sind mehrere automatische Telefonzentralen und erfordern nur eine einzelne zugewiesene Telefonnummer für den Eintrag oder der obersten Ebene der automatischen Telefonzentrale. Andere Telefonzentralen oder Anruf Warteschlangen in der gesamten Systems werden nur eine Telefonnummer ein erforderlich, wenn Sie mehrere Einstiegspunkte in das System bereitstellen möchten.
- Es ist möglich, eine automatische Telefonzentrale durch mehrere Ressourcenkonto an eine automatische Telefonzentrale zuordnen mehr als eine Telefonnummer zuweisen.
  
## <a name="feature-overview"></a>Übersicht über die Features

### <a name="dial-by-name"></a>Namensanwahl

Dial namentlich ist ein Feature von einer automatischen Telefonzentrale, die auch als Verzeichnissuche bezeichnet. Sie können die Personen, die die automatische Telefonzentrale Verwendung von VoIP (Spracherkennung) oder die Telefonnummer Tastatur (MFV) Antworten, geben einen vollständigen oder teilweisen Namen Unternehmensverzeichnis durchsuchen, suchen Sie die Person anrufen, und veranlassen Sie der Anruf weitergeleitet werden. Benutzer, die Sie verwenden möchten, befindet sich und mit Dial namentlich erreicht haben **ist nicht erforderlich, haben Sie eine Rufnummer ein oder ihnen zugewiesen haben aufrufen plant, aber sie müssen eine Lizenz Telefonsystem aufweisen, wenn sie die online-Benutzer sind oder EV für Verbindungspfad Benutzer aktiviert**. Dial namentlich werden auch ermitteln und durchstellen von Anrufen an Microsoft-Teams, Benutzer, die in verschiedenen Ländern oder Regionen für multinationale Unternehmen gehostet werden.

### <a name="maximum-directory-size"></a>Maximale Verzeichnisgröße

Es gibt keine Beschränkung für die Active Directory-Größe für die Einwahl namentlich unterstützt wird, wenn die Telefontastatur suchen zur Eingabe von teilweiser oder vollständiger Names (Vorname Nachname, und auch LastName + FirstName). Es ist jedoch die maximale Listengröße, dass eine einzelne automatische Telefonzentrale unterstützen kann Speech Recognition Namen mit 80.000 Benutzern.
  
|Eingabetyp|Suchformat|Maximale Anzahl der Benutzer in einer Organisation|
|:-----|:-----|:-----|
|MFV (Eingabe über die Wähltastatur) |Teilweise  <br/> Vorname + Nachname  <br/> Nachname + Vorname |Keine Begrenzung  |
|Sprache (Spracheingabe) |Vorname  <br/> Nachname  <br/> Vorname + Nachname  <br/> Nachname + Vorname  | 80.000 Benutzern |

> [!NOTE]
> Bei Verwendung der Einwahl namentlich mit Speech Recognition, aber Ihre Organisation Active Directory ist größer als 80.000 Benutzern und Sie noch nicht den Bereich der Einwahl über den Namen mithilfe von DFÜ-bereichsfeature begrenzt, Dial namentlich funktioniert auch weiterhin für die über die Tastatur eine Rufnummer für Anrufer , und Spracheingaben werden für alle anderen Szenarien zur Verfügung gestellt. DFÜ-bereichsfeature können Sie die Namen einzuschränken, die durch eine Änderung der Zugriffsnummer für eine bestimmte automatische Telefonzentrale namentlich erreichbar sind.
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>Namensanwahl - Eingabe über die Wähltastatur (MFV)

Personen einwählen, können Dial namentlich erreichen von Benutzern durch Angeben von entweder den vollständigen oder teilweisen Namen der Person, die sie erreichen möchten. Es gibt verschiedene Formate, die verwendet werden können, wenn der Name eingegeben wurde.

Bei der Suche Verzeichnis Ihrer Organisation können Personen die "0" (null), verwenden ein Leerzeichen zwischen dem vor- und dem letzten anzugeben oder last Name und first. Wenn sie den Namen eingeben, werden sie aufgefordert, ihre Tastatur-Eintrag mit dem #-Schlüssel zu beenden. Beispiel: "nach Eingabe des Namens der Person ein, den, die Sie erreichen möchten, drücken Sie #." Wenn es sind mehrere Namen, die der anrufenden Person gefunden, werden erhält eine Liste mit Namen aus.
  
Anrufer können bei der Suche nach Namen in Ihrer Organisation über die Wähltastatur eines Telefons die folgenden Suchformate verwenden:
  
|Namensformat|Suchtyp|Beispiel|Suchergebnis|
|:-----|:-----|:-----|:-----|
|Vorname + Nachname |Vollständig  |Amos0Marble# |Amos Marble |
|Nachname + Vorname |Vollständig |Marble0Amos#  |Amos Marble |
|Vorname  |Vollständig   |Amos#   |Drücken Sie „1" für Amos Marble.  <br/> Drücken Sie „2" für Amos Marcus. |
|Nachname |Vollständig |Marble#  |Drücken Sie „1" für Amos Marble.  <br/> Drücken Sie „2" für Mary Marble. |
|Vorname oder Nachname |Teilweise |Mar# |Drücken Sie „1" für Mary Marble.  <br/> Drücken Sie „2" für Mary Jones.  <br/> Drücken Sie „3" für Amos Marcus. |
|Vorname + Nachname |Teilweise |Mar0Amos# |Drücken Sie „1" für Amos Marble.  <br/> Drücken Sie „2" für Amos Marcus. |
|Nachname + Vorname |Teilweise |Mar0Am# |Drücken Sie „1" für Amos Marble.  <br/> Drücken Sie „2" für Amos Marcus. |

Bei der Suche nach Personen über die Wähltastatur eines Telefons können verschiedene Sonderzeichen verwendet werden. Beispielsweise die Person gebeten, verwenden Sie die Rautetaste (#), während für ein Leerzeichen zwischen Null (0)-Taste verwendet wird. Wenn die Anrufer die Sterntaste (*) drücken, wird die Liste der übereinstimmenden Namen wiederholt.
  
|Sonderzeichen auf der Wähltastatur eines Telefons|Bedeutung|
|:-----|:-----|
|#   |Endzeichen bei der Eingabe eines Namens |
|0   |Leerschritt zwischen Namen |
|*    |Wiederholt die Liste der übereinstimmenden Namen. |

### <a name="dial-by-name---name-recognition-with-speech"></a>Namensanwahl - Namenserkennung mit Sprache

Personen können andere Personen in ihrer Organisation über ihre VoIP (Spracherkennung) suchen. Sie können auch erreichen alle in Active Directory des Unternehmens sagen Sie den Namen der Person, die sie suchen möchten. Mithilfe von Spracheingaben erkennen Namen in verschiedenen Formaten, einschließlich FirstName, LastName, FirstName LastName, oder LastName + FirstName.
  
Wenn Sie die Spracherkennung für eine automatische Telefonzentrale aktivieren, werden nicht Telefon Tastatur Eintrag (MFV) deaktiviert werden, damit beide Arten von Eingabe verwendet werden können. Telefon Tastatur Eintrag kann nicht deaktiviert werden und kann jederzeit verwendet werden, selbst wenn die Spracherkennung für die automatische Telefonzentrale aktiviert ist.
  
Wie bei der Eingabe über die Wähltastatur eines Telefons wird den Anrufern, wenn mehrere Namen gefunden werden, eine Liste mit Namen zur Auswahl präsentiert.
  
Die Anrufer können Namen in den folgenden Formaten sagen:
  
|Nennen Sie mit der Sprache|Suchtyp|Beispiel|Suchergebnis|
|:-----|:-----|:-----|:-----|
|Vorname + Nachname |Vollständig |Amos Marble |Amos Marble |
|Nachname + Vorname |Vollständig  |Marble Amos |Amos Marble |
|Vorname |Vollständig |Amos |Drücken oder sagen Sie „1" für Amos Marble.  <br/> Drücken oder sagen Sie „2" für Amos Jones. |
|Nachname |Vollständig |Marble |Drücken oder sagen Sie „1" für Amos Marble.  <br/> Drücken oder sagen Sie „2" für Ben Marble. |

> [!NOTE]
> Es kann bis zu 36 Stunden für einen neuen Benutzer ihre Namen in das Verzeichnis mit Namen für die Spracherkennung aufgrund von Active Directory-Replikation Zeitabstand für Einwahl aufgeführt haben dauern.
  
### <a name="language-support"></a>Sprachunterstützung

Für Text-zu-Sprache sind die folgenden Sprachen verfügbar:
  
||||
|:-----|:-----|:-----|
|Arabisch (EG)  |Englisch (NZ)  |Koreanisch (KO)  |
|Chinesisch (HK)  |Englisch (Großbritannien) |Norwegisch (NO)  |
|Chinesisch (TW) |Englisch (USA) |Polnisch (PL)  |
|Chinesisch (ZH) |Finnisch (FI) |Portugiesisch (BR) |
|Dänisch (DA)  |Französisch (CA)  |Portugiesisch (PT) |
|Niederländisch (NL)   |Französisch (FR)  |Russisch (RU) |
|Englisch (AU)  |Deutsch (DE) |Spanisch (ES)  |
|Englisch (CA)  |Italienisch (IT) |Spanisch (MX)|
|Englisch (IN)  |Japanisch (JP) |Schwedisch (SV)|

Spracherkennung für automatische Telefonzentralen ist in den folgenden Sprachen verfügbar:
  
|||
|:-----|:-----|
|Chinesisch (ZH)  |Französisch (FR)  |
|Englisch (AU)  |Deutsch (DE)  |
|Englisch (CA)  |Italienisch (IT)  |
|Englisch (IN)  |Japanisch (JP)  |
|Englisch (Großbritannien)  |Portugiesisch (BR)  |
|Englisch (USA)  |Spanisch (ES)  |
|Französisch (CA)   |Spanisch (MX)  |

Die folgenden Sprachbefehle sind in den vierzehn (14) für Spracherkennung unterstützten Sprachen verfügbar:
  
|Sprachbefehl| Entspricht |
|:-----|:-----|
|Ja |Ja - entspricht dem Drücken von „1" für „Ja". |
|Nein |Nein - entspricht dem Drücken von „2" für „Nein". |
|Wiederholen |Wiederholt die Liste der Optionen - entspricht dem Drücken von „*" zum Wiederholen der Liste der Optionen. |
|Vermittlung |Zurück zur Vermittlung - entspricht dem Drücken von „0" für „Vermittlung". |
|Hauptmenü  |Die Anrufer gelangen zum Hauptmenü der automatischen Telefonzentrale. |
|Null |Entspricht dem Drücken von „0" (standardmäßig identisch mit „Vermittlung").|
|Eins |Entspricht dem Drücken von „1". |
|Zwei |Entspricht dem Drücken von „2". |
|Drei|Entspricht dem Drücken von „3".|
|Vier |Entspricht dem Drücken von „4". |
|Fünf |Entspricht dem Drücken von „5". |
|Sechs  |Entspricht dem Drücken von „6". |
|Sieben |Entspricht dem Drücken von „7".|
|Acht |Entspricht dem Drücken von „8".|
|Neun  |Entspricht dem Drücken von „9".|

### <a name="using-the-operator-option"></a>Verwenden der Vermittlungsoption

Verwenden Sie den Operator für eine automatische Telefonzentrale ist eine optionale Einstellung, die den Anrufer mit der Option für einen human Operator sprechen bereitstellt.
  
0-Taste und den VoIP-Befehl "Operator" leiten Sie den Anruf an dem angegebenen Operator standardmäßig. Dies ist die Groß-/Kleinschreibung für alle Sprachen für die Spracherkennung unterstützt. Sie können auch **Menüoptionen** verwenden, um einen benutzerdefinierten Wert für den Operator festzulegen.
  
Der Operator kann festgelegt werden:
  
- Ein Microsoft-Teams, Benutzer oder eine Skype für Unternehmen auf lokale Benutzer, die Enterprise-VoIP aktiviert ist.
  
- Eine andere für Ihre Organisation eingerichtete automatische Telefonzentrale
- Eine beliebige in Ihrer Organisation eingerichtete Anrufwarteschleife. Weitere Informationen zum Anruf Warteschlangen finden Sie unter [Erstellen einer Cloud-Anruf-Warteschlange](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

### <a name="business-hours-and-call-handling"></a>Geschäftszeiten und Anrufbehandlung

Geschäftszeiten werden für jede automatische Telefonzentrale festgelegt. Wenn Geschäftszeiten festgelegt sind, werden alle Tage und alle Stunden am Tag Geschäftszeiten berücksichtigt, da standardmäßig ein Zeitplan 24/7 festgelegt ist. Geschäftszeiten kann mit Breaks rechtzeitig während der Tag und alle der Stunden, die nicht festgelegt werden, wie Geschäftszeiten Geschäftszeiten gelten festgelegt werden. Sie können unterschiedliche eingehende Anrufbehandlung Optionen und anderen Ansage (die optionale sind), und beide für Geschäftszeiten und Geschäftszeiten festgelegt sein.
  
Jede automatische Telefonzentrale hat Anrufbehandlung Optionen, die festgelegt werden können:
  
- Sie können festlegen, dass ein Anruf direkt nach der Begrüßung getrennt wird.
- Sie können auch folgende Aktionen ausführen:
  - Umleiten des Anrufs an einen Microsoft-Teams, Benutzer, der über eine Lizenz **Telefonsystem** verfügt, die Enterprise-VoIP aktiviert ist, oder sie zugewiesen wurde plant aufrufen. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Dazu wählen Sie eine **Person in Ihrem Unternehmen** aus, deren Anrufe dann automatisch direkt an die Voicemail weitergeleitet werden.

  
  - Umleiten des Anrufs an eine Warteschleife Anruf. Weitere Informationen zum Anruf Warteschlangen finden Sie unter [Erstellen einer Cloud-Anruf-Warteschlange](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

  - Leiten Sie den Anruf an eine andere automatische Telefonzentrale, die Sie eingerichtet haben.
- Menüoptionen erstellen und eine Menüansage für die Anrufer wiedergeben. Beispiel: „Drücken Sie ‚1' für den Vertrieb oder ‚2' für den Service. Durch Drücken von ‚0' können Sie jederzeit mit der Vermittlung sprechen."

### <a name="menu-options"></a>Menüoptionen

Cloud-Telefonzentralen können Sie Menüansagen ("drücken Sie 1 für den Vertrieb, 2 für Dienste drücken") erstellen und Einrichten von Menüoptionen für das Anrufrouting basierend auf der Auswahl des Benutzers. Durch Einrichten von Menüoptionen für eine automatische Telefonzentrale können Organisationen die Anrufer interaktiv schneller an ihr Ziel führen, ohne dass dazu Vermittlungsmitarbeiter für die Abwicklung der eingehenden Anrufe benötigt werden. Menüansagen können erstellt werden, mithilfe der Sprachausgabe (vom System generierte Ansagen) oder durch Hochladen einer Audiodatei, die aufgezeichnet wurden. Bei der Spracherkennung werden Sprachbefehle für Freisprechnavigation verwendet, aber die Anrufer können auch mithilfe der Wähltastatur eines Telefons in den Menüs navigieren.
  
Tasten 0 bis 9 können in eine automatische Telefonzentrale mit der Skype für Business Administrationscenter **Menüoptionen** zugewiesen werden. Verschiedene Sätze von Menüoptionen können erstellt werden, für die Geschäftszeiten und außerhalb der Geschäftszeiten, und Sie aktivieren oder deaktivieren Sie namentlich in den **Optionen im Menü**wählen können. Schlüssel können zum Weiterleiten der Anrufe für zugeordnet werden:
  
- Eine Vermittlung, die standardmäßig der Taste „0" zugeordnet ist. Jedoch möglich erneut zugewiesen an eine beliebige Taste, oder aus dem Menü entfernt.
- Eine Warteschlange Anruf.
- Eine andere automatische Telefonzentrale. Menüs mit mehreren Ebenen können eingerichtet werden, zeigen Sie eine **Menüoption** in eine automatische Telefonzentrale an eine andere automatische Telefonzentrale mit einem eigenen Satz von Menüoptionen, die eine "geschachtelte" Automatische Telefonzentrale bezeichnet wird.
- Ein Microsoft-Teams, Benutzer mit einem **Telefonsystem** lizenzieren, die Enterprise-VoIP aktiviert oder hat aufrufen plant zugeordnet ist, diese. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Dazu wählen Sie eine **Person in Ihrem Unternehmen** aus, deren Anrufe dann automatisch direkt an die Voicemail weitergeleitet werden.
  
Der Name des jede Menüoption wird ein Spracherkennung Schlüsselwort, wenn die Spracherkennung aktiviert wurde. Beispielsweise können Anrufer sagen Sie "1", um die Menüoption, Schlüssel 1 zugeordnet sind, wählen oder sie können einfach sagen "Sales", um die gleichen Menüoption mit dem Namen "Sales".
  
Um eine automatische Telefonzentrale und die Menüoptionen im einzurichten, gehen Sie [Richten Sie eine Cloud-Telefonzentrale](create-a-phone-system-auto-attendant.md).
  
### <a name="assigning-phone-numbers-for-an-auto-attendant"></a>Zuweisen von Rufnummern für eine automatische Telefonzentrale

Sie können eine Microsoft Plan Service-Nummer oder eine direkte Hybrid Bankleitzahl an die automatische Telefonzentrale aufrufen zuweisen. Einzelheiten finden Sie unter [Planen der direkten Routing](direct-routing-plan.md) .

Zuweisen, indem Sie eine Zahl Dienst benötigen zum Abrufen oder übertragen Ihre vorhandenen gebührenpflichtige oder gebührenfreie Service Zahlen. Nachdem Sie die gebührenpflichtige oder gebührenfreie Service Telefonnummern erhalten möchten, sie werden angezeigt, der <!-- validate nav path --> **Skype für Business Administrationscenter** > **VoIP** > **Telefonnummern**und die **Typ-Nummer** aufgeführt wird als **Dienst - gebührenfreie**aufgeführt werden. Um die Rufnummern Service erhalten möchten, finden Sie unter [Getting Service Rufnummern für Skype für Unternehmen und die Microsoft-Teams](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers) oder für Übertragung und vorhandenen Service-Nummer, finden Sie unter [Übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Wenn Sie sich außerhalb der USA sind, können das Microsoft-Teams, Administrationscenter Sie um Service Zahlen zu erhalten. Wechseln Sie [Telefonnummern für Ihre Organisation verwalten](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) stattdessen wie es angezeigt.
  
## <a name="related-topics"></a>Verwandte Themen

[Das Telefonsystem in Office 365 bietet Ihnen Folgendes](here-s-what-you-get-with-phone-system.md)

[Anfordern von Servicenummern für Skype for Business und Microsoft Teams](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)

[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Beispiel für Kleinunternehmen – Einrichten einer automatischen Telefonzentrale](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)
