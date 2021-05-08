---
title: Was sind automatische Cloud-Attendants?
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: makolomi
ms.date: 4/2/2019
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
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
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
description: Erfahren Sie mehr über automatische Cloud-Telefonkonferenzen und wie Sie diese verwenden, damit Anrufer durch ein Menüsystem wechseln können, um Anrufe zu suchen und zu platzieren oder Anrufe an Benutzer oder Abteilungen zu übertragen.
ms.openlocfilehash: c8e5b3f608200036b8c9b9ed5338c558464b32d3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100961"
---
# <a name="what-are-cloud-auto-attendants"></a>Was sind automatische Cloud-Attendants?

Telefonsystem stellt automatische Telefonkonferenzen zur Verfügung, mit denen externe und interne Anrufer durch ein Menüsystem wechseln können, um Anrufe zu suchen und zu platzieren oder Anrufe an Benutzer oder Abteilungen in Ihrer Organisation zu übertragen.
  
Eine automatische Telefonanlage ist meistens ein Knoten in einem System, der Anrufern eine Reihe von Sprachanrufen oder Audiodateien gibt, die sie hören, statt einer menschlichen Operator. Wenn Personen eine Nummer anrufen, die einer automatischen Telefon attendant zugeordnet ist, können sie den Anruf an einen Benutzer umleiten oder jemanden in Ihrer Organisation suchen und dann eine Verbindung mit diesem Benutzer herstellen. Sie können ihre Auswahl ausdrücken und mit dem Menüsystem interagieren, indem sie eine Telefontaste (MFV) oder spracherkennung verwenden. Die von ihnen getroffenen Optionen können den Anruf auch an eine andere automatische Telefonkonferenz oder an eine Anrufwarteschleife umleiten.
  
Wechseln Sie zum Einrichten einer automatischen Telefonsystem zu [Einrichten einer automatischen Cloud-Attendant.](create-a-phone-system-auto-attendant.md)
  
Eine automatische Cloud-Attendant verfügt über die folgenden Features:
  
- Sie kann Unternehmensbegrüßungen oder informative Begrüßungen bereitstellen.
- Sie kann benutzerdefinierte Unternehmensmenüs bereitstellen. Diese Menüs können Sie so anpassen, dass sie aus mehreren Ebenen bestehen.
- Sie bietet eine Verzeichnissuche, mit der Anrufer das Verzeichnis der Organisation nach einem Namen durchsuchen können.
- Damit kann eine Person, die anruft, eine Nachricht für eine Person in Ihrer Organisation erreichen oder hinterlassen.
- Es unterstützt mehrere Sprachen für Eingabeaufforderungen, Text-zu-Sprache und Spracherkennung.
- Sie unterstützt die Angabe von Feiertagen und Geschäftszeiten.
- Sie unterstützt die Übertragung von Anrufen an eine Netzbetreiber, andere Benutzer, Anrufwarteschleifen und automatische Telefonkonferenzen.
- Sie unterstützt freigegebene Voicemails für Anrufer, um Nachrichten für eine Organisation zu hinterlassen.

> [!NOTE]
> Dieser Artikel bezieht sich auf Microsoft Teams und Skype for Business Online.

## <a name="getting-started"></a>Erste Schritte

Die folgenden Punkte sind bei Ihrem Einstieg in die Verwendung von automatischen Telefonzentralen wichtig:

- Eine automatische Attendant muss über ein zugeordnetes Ressourcenkonto verfügen. Einzelheiten [zu Ressourcenkonten finden Sie Teams](manage-resource-accounts.md) unter Verwalten von Ressourcenkonten in einem Ressourcenkonto. <!-- You can either use an existing resource account or create a new resource account as you set up your auto attendant. -->
- Wenn Sie einer automatischen Telefon attendant eine Telefonnummer zuweisen, ordnen Sie diese ausschließlich dem Ressourcenkonto zu, das dieser automatischen Telefon attendant zugeordnet ist. Auf diese Weise können mehrere Telefonnummern auf eine automatische Telefon attendant zugreifen. In den meisten Jahren wird für ein Ressourcenkonto die kostenfreie Und-Telefonsystem virtueller Benutzer verwendet. Diese Lizenz bietet Telefonsystem Funktionen für Telefonnummern auf Organisationsebene und ermöglicht Ihnen das Erstellen von automatischen Telefonkonferenzen und Anrufwarteschleifen.

> [!NOTE]
> Direktes Routing von Servicenummern für automatische Telefonleitung und Anrufwarteschleifen wird nur für Microsoft Teams und Anruf-Agents unterstützt.

   > [!TIP]
   > Um Anrufe an eine Netzbetreiber oder Menüoption weiterzuleiten, bei dem es sich um einen Onlinebenutzer mit **einer Telefonsystem-Lizenz** handelt, müssen Sie sein Konto für Enterprise-VoIP aktivieren oder ihm Anrufpläne zuweisen. Weitere [Informationen finden Microsoft Teams Zuweisen von Add-On-Lizenzen.](teams-add-on-licensing/assign-teams-add-on-licenses.md) Sie können auch die Windows PowerShell verwenden. Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Um gebührenfreie Servicenummern für Ihre automatischen Attendants zu erhalten und zu verwenden, müssen Sie Guthaben für Kommunikationen einrichten. Informationen dazu finden Sie unter [Was ist Guthaben für Kommunikationen?](what-are-communications-credits.md) und [Einrichten von Guthaben für Kommunikationen für Ihre Organisation.](set-up-communications-credits-for-your-organization.md)

    > [!IMPORTANT]
    > Telefonnummern von Benutzern (Abonnenten) können automatischen Telefonzentralen nicht zugewiesen werden - es können nur gebührenpflichtige oder gebührenfreie Telefonnummern verwendet werden.

- Ein vollständiges automatisches Attendant-System ist in der Regel mit mehreren automatischen Attendants ausgestattet.
- Es ist möglich, mehrere Telefonnummern auf automatische Telefon telefonieren auf Einstiegsebene anzuwenden.
- Automatische Telefonkonferenzen oder Anrufwarteschleifen im vollständigen System benötigen nur dann eine Telefonnummer, wenn sie ausgehende PSTN-Anrufe führen.
  
## <a name="feature-overview"></a>Übersicht über Features

### <a name="searching-for-users"></a>Suchen nach Benutzern

Namensanwahl ist ein Feature einer automatischen Telefon attendant, das auch als Verzeichnissuche bezeichnet wird. So können Personen, die Ihre automatische Telefongesellschaft anrufen, Sprachanrufe (Spracherkennung) oder DTMF-Antworten (Phone Keypad) verwenden, um einen vollständigen oder teilweisen Namen zum Durchsuchen des Firmenverzeichnisses ein ein, suchen die Person und lassen den Anruf an diese Person durch. Benutzer, die Sie mit der Namensanwahl erreicht haben möchten, müssen keine Telefonnummer oder Anrufpläne haben, aber sie müssen über eine **Telefonsystem-Lizenz verfügen,** wenn sie Onlinebenutzer sind, oder Enterprise-VoIP für Skype for Business Server-Benutzer aktiviert sein. Namensanwahl ist sogar in der Lage, Anrufe zu finden und an Microsoft Teams-Benutzer zu übertragen, die in verschiedenen Ländern oder Regionen für multinationale Organisationen gehostet werden. Angesichts der erforderlichen Voraussetzungen aktivieren Sie die Namensanwahl explizit in einer automatischen Telefon attendant.

Die Durchwahl ist ein Feature einer automatischen Telefon attendant, das ebenfalls Teil der Verzeichnissuche ist. So können Personen, die Ihre automatische Telefonkonferenz anrufen, Sprachanrufe (Spracherkennung) oder DTMF-Antworten (Phone Keypad) verwenden, um die Telefonerweiterung des Benutzers ein- bzw. aus, den sie erreichen möchten, und den Anruf dann an sie durch übertragen lassen. Benutzer, die Sie per Durchwahl erreicht haben möchten, müssen keine Telefonnummer oder Anrufpläne haben, aber sie müssen über eine **Telefonsystem-Lizenz verfügen,** wenn sie Onlinebenutzer sind oder Enterprise-VoIP für Skype for Business Server-Benutzer aktiviert sind. Darüber hinaus benötigen Sie einen entsprechend konfigurierten Wählplan für Ihre Benutzer. Durch die Durchwahl können Sie sogar Anrufe an Benutzer Microsoft Teams suchen und übertragen, die in verschiedenen Ländern oder Regionen für multinationale Organisationen gehostet werden. Angesichts der erforderlichen Voraussetzungen aktivieren Sie die Option "Durchwahl wählen" explizit in einer automatischen Telefon attendant.

#### <a name="maximum-directory-size"></a>Maximale Verzeichnisgröße

Es gibt keine Beschränkung der Anzahl der Active Directory-Benutzer, die die Namensanwahl und die Durchwahl per Durchwahl unterstützen können, wenn ein Anrufer nach einer bestimmten Person sucht. Ein Anrufer kann Namen teilweise oder vollständig eingeben (Vorname + Nachname und auch Nachname + Vorname), benötigt aber die vollständige Durchwahlnummer. Die maximale Größe der Namensliste, die eine einzelne automatische Attendant mithilfe der Spracherkennung unterstützen kann, beträgt 80.000 Benutzer.
  
|Eingabetyp|Suchformat|Maximale Anzahl der Benutzer in einer Organisation|
|:-----|:-----|:-----|
|MFV (Eingabe über die Wähltastatur) |Teilweise  <br/> Vorname + Nachname  <br/> Nachname + Vorname |Kein Grenzwert  |
|Sprache (Spracheingabe) |Vorname  <br/> Nachname  <br/> Vorname + Nachname  <br/> Nachname + Vorname  | 80.000 Benutzer |

> [!NOTE]
> Wenn Sie die Namensanwahl mit Spracherkennung verwenden, active Directory aber mehr als 80.000 Benutzer in Ihrer Organisation ist und Sie den Bereich der Namensanwahl nicht mithilfe der Funktion "Wählbereich" eingeschränkt haben, funktioniert die Namensanwahl weiterhin für Ihre Anrufer über die Wähltasten eines Telefons, und Spracheingaben stehen in allen anderen Szenarien zur Verfügung. Sie können das Feature "Wählbereich" verwenden, um die Namen zu ein grenzen, die erreichbar sind, indem Sie den Bereich der Namensanwahl für eine bestimmte automatische Telefon attendant ändern.
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>Namensanwahl - Eingabe über die Wähltastatur (MFV)

Anrufer können Benutzer mithilfe von Namenswählen erreichen, indem sie den vollständigen oder teilweisen Namen der Person angeben, die sie erreichen möchten. Es gibt verschiedene Formate, die verwendet werden können, wenn der Name eingegeben wird.

Beim Durchsuchen des Verzeichnisses Ihrer Organisation können Benutzer die Taste "0" (Null) verwenden, um ein Leerzeichen zwischen dem Vornamen und dem Nach- oder Nachnamen und dem Vornamen anzugeben. Wenn sie den Namen eingeben, wird sie aufgefordert, die Eingabe über die Zehnertaste mit der Taste # zu beenden. Beispiel: "Drücken Sie #, nachdem Sie den Namen der Person eingeben, die Sie erreichen möchten." Wenn mehrere Namen gefunden werden, wird der Anrufer eine Liste mit Namen zur Auswahl angezeigt.
  
Anrufer können bei der Suche nach Namen in Ihrer Organisation über die Wähltastatur eines Telefons die folgenden Suchformate verwenden:
  
|Namensformat|Suchtyp|Beispiel|Suchergebnis|
|:-----|:-----|:-----|:-----|
|Vorname + Nachname |Vollständig  |Amos0Marble# |Amos Marble |
|Nachname + Vorname |Vollständig |Marble0Amos#  |Amos Marble |
|Vorname  |Vollständig   |Amos#   |Drücken Sie „1" für Amos Marble.  <br/> Drücken Sie „2" für Amos Marcus. |
|Nachname |Vollständig |Marble#  |Drücken Sie „1" für Amos Marble.  <br/> Drücken Sie „2" für Mary Marble. |
|Vorname oder Nachname |Teilweise |Mar# |Drücken Sie „1" für Mary Marble.  <br/> Drücken Sie „2" für Mary Jones.  <br/> Drücken Sie „3" für Amos Marcus. |
|Vorname + Nachname |Teilweise |Amos0Mar # |Drücken Sie „1" für Amos Marble.  <br/> Drücken Sie „2" für Amos Marcus. |
|Nachname + Vorname |Teilweise |Mar0Am# |Drücken Sie „1" für Amos Marble.  <br/> Drücken Sie „2" für Amos Marcus. |

Bei der Suche nach Personen über die Wähltastatur eines Telefons können verschiedene Sonderzeichen verwendet werden. Die Person wird z. B. aufgefordert, die Nummerntaste (#) zu verwenden, während die Nulltaste (0) für ein Leerzeichen zwischen Namen verwendet wird. Wenn die Anrufer die Sterntaste (*) drücken, wird die Liste der übereinstimmenden Namen wiederholt.
  
|Sonderzeichen auf der Wähltastatur eines Telefons|Bedeutung|
|:-----|:-----|
|#   |Endzeichen bei der Eingabe eines Namens |
|0   |Leerschritt zwischen Namen |
|*    |Wiederholt die Liste der übereinstimmenden Namen. |

#### <a name="dial-by-name---name-recognition-with-speech"></a>Namensanwahl - Namenserkennung mit Sprache

Personen können mit ihrer Stimme (Spracherkennung) nach anderen Personen in ihrer Organisation suchen. Sie können auch jede Person in Active Directory erreichen, indem sie den Namen der Person sagt, nach der sie suchen möchte. Mithilfe von Spracheingaben können Namen in verschiedenen Formaten erkannt werden, darunter "Vorname", "Nachname", "Vorname + Nachname" oder "Nachname + Vorname".
  
Sie können die Spracherkennung für eine automatische Telefon attendant aktivieren, aber die Eingabe über die Telefontaste (MFV) ist nicht deaktiviert. Telefon Eingabe über die Tastatur kann jederzeit verwendet werden, auch wenn die Spracherkennung in der automatischen Attendant aktiviert ist.
  
Wie bei der Eingabe über die Wähltastatur eines Telefons hört die Anrufer eine Liste mit Namen, aus der Sie auswählen können, wenn mehrere Namen gefunden werden.
  
Anrufer können Namen in den folgenden Formaten sagen:
  
|Name mit Sprache|Suchtyp|Beispiel|Suchergebnis|
|:-----|:-----|:-----|:-----|
|Vorname + Nachname |Vollständig |Amos Marble |Amos Marble |
|Nachname + Vorname |Vollständig  |Marble Amos |Amos Marble |
|Vorname |Vollständig |Amos |Drücken oder sagen Sie „1" für Amos Marble.  <br/> Drücken oder sagen Sie „2" für Amos Jones. |
|Nachname |Vollständig |Marble |Drücken oder sagen Sie „1" für Amos Marble.  <br/> Drücken oder sagen Sie „2" für Ben Marble. |

> [!NOTE]
> Es kann bis zu 36 Stunden dauern, bis ein neuer Benutzer seinen Namen aufgrund von Active Directory-Replikationsverzögerung im Verzeichnis für Namensanwahl mit Spracherkennung aufgeführt hat.
  
### <a name="language-support"></a>Sprachunterstützung

Die folgenden Sprachen stehen für Text-zu-Sprache zur Verfügung, die bei ausgehenden Eingabeaufforderungen verwendet werden:
  
|A-E|E-J|K-Z|
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

Spracherkennungseingaben für automatische Attendants sind in den folgenden Sprachen verfügbar:
  
|A-F|F-Z|
|:-----|:-----|
|Chinesisch (ZH)  |Französisch (FR)  |
|Englisch (AU)  |Deutsch (DE)  |
|Englisch (CA)  |Italienisch (IT)  |
|Englisch (IN)  |Japanisch (JP)  |
|Englisch (Großbritannien)  |Portugiesisch (BR)  |
|Englisch (USA)  |Spanisch (ES)  |
|Französisch (CA)   |Spanisch (MX)  |

Die folgenden Sprachbefehle sind in den 14 sprachen verfügbar, die für die Spracherkennung unterstützt werden:
  
|Sprachbefehl| Entspricht |
|:-----|:-----|
|Ja | Drücken Sie 1 für Ja. |
|Nein | Drücken Sie 2, um "Nein" zu drücken. |
|Wiederholen |Wiederholt die Liste der Optionen. Drücken Sie * auf der Tastatur, um die Liste der Optionen zu wiederholen. |
|Vermittlung | Drücken Sie "0" für "Operator". |
|Hauptmenü  |Die Anrufer gelangen zum Hauptmenü der automatischen Telefonzentrale. |
|Null | Drücken Sie 0 (standardmäßig identisch mit "Operator").|
|Eins | Drücken Sie 1. |
|Zwei | Drücken Sie 2. |
|Drei| Drücken Sie 3.|
|Vier | Drücken Sie 4. |
|Fünf | Drücken Sie 5. |
|Sechs  | Drücken Sie 6. |
|Sieben | Drücken Sie 7.|
|Acht |Drücken Sie 8.|
|Neun  |Drücken Sie 9.|

### <a name="the-operator-option"></a>Die Operatoroption

Eine automatische Telefonkonferenz kann optional festgelegt werden, um einem Anrufer die Auswahl zu geben, mit einer menschlichen Telefongesellschaft zu sprechen.
  
Die Taste 0 und der Sprachbefehl "Operator" leitet den Anruf standardmäßig an den vorgesehenen Operator. Dies gilt für alle Sprachen, die für die Spracherkennung unterstützt werden. Sie können auch **Menüoptionen festlegen verwenden,** um einen benutzerdefinierten Wert für den Operator festlegen.
  
Der Operator kann auf:
  
- Ein Microsoft Teams oder ein Skype for Business Server Benutzer, der Enterprise-VoIP aktiviert ist.
- Eine andere für Ihre Organisation eingerichtete automatische Telefonzentrale
- Eine beliebige in Ihrer Organisation eingerichtete Anrufwarteschleife. Weitere Informationen zu Anrufwarteschleifen finden Sie unter [Erstellen einer Cloud-Anrufwarteschleife.](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

### <a name="business-hours-and-call-handling"></a>Geschäftszeiten und Anrufbehandlung

Die Geschäftszeiten können für jede automatische Attendant festgelegt werden. Wenn keine Geschäftszeiten festgelegt sind, werden alle Tage und alle Stunden des Tages als Geschäftszeiten betrachtet, da standardmäßig ein Rund-um-die-Uhr-Zeitplan festgelegt ist. Geschäftszeiten können mit Tagesumbrüchen festgelegt werden, und alle Stunden, die nicht als Geschäftszeiten festgelegt sind, werden als Nachstunden betrachtet. Sie können verschiedene Optionen für die Anrufbehandlung sowie unterschiedliche Ansungen (optional) für die Geschäftszeiten und die Geschäftszeiten festlegen.
  
Jede automatische Telefon attendant hat mehrere mögliche Anrufbehandlungsoptionen:
  
- Der Anruf kann nach der Abspielung einer Begrüßung unterbrochen werden.
- Sie können auch folgende Aktionen ausführen:
  - Leiten Sie den Anruf an einen Microsoft Teams-Benutzer um, der über eine **Telefonsystem-Lizenz** verfügt, Enterprise-VoIP aktiviert ist oder dem Anrufpläne zugewiesen sind. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Dazu wählen Sie eine **Person in Ihrem Unternehmen** aus, deren Anrufe dann automatisch direkt an die Voicemail weitergeleitet werden.

  - Leiten Sie den Anruf an eine Anrufwarteschleife um. Weitere Informationen zu Anrufwarteschleifen finden Sie unter [Erstellen einer Cloud-Anrufwarteschleife.](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

  - Leiten Sie den Anruf an eine andere automatische Telefon attendant um.

Diese Optionen werden dem Anrufer von der automatischen Telefonant ausgedrückt, wenn sie Menüanforderungen wieder gibt. Beispiel: „Drücken Sie ‚1' für den Vertrieb oder ‚2' für den Service. Durch Drücken von ‚0' können Sie jederzeit mit der Vermittlung sprechen."

### <a name="set-menu-options"></a>Menüoptionen festlegen

Automatische Cloud-Telefon attendants allow you to create menu prompts ("Press 1 for Sales, Press 2 for Services") and set menu options to route calls based on user selections. Mit Den Menüoptionen für eine automatische Telefon attendant kann eine Organisation eine Reihe von Auswahlmöglichkeiten bereitstellen, die Anrufer schneller an ihr Ziel führen, ohne sich für die Verarbeitung eingehender Anrufe auf eine personale Hilfsorganisation verlassen zu müssen. Menüanforderungen können entweder mithilfe von Text-zu-Sprache (vom System generierte Eingabeaufforderungen) oder durch Hochladen einer aufgezeichneten Audiodatei erstellt werden. Die Spracherkennung akzeptiert Sprachbefehle für die Freisprechnavigation, aber die Anrufer können auch über die Telefontaste in den Menüs navigieren.
  
Die Tasten 0 bis 9 können tasten in einer automatischen Telefonzentrale mithilfe des Skype for Business admin center zugewiesen werden. Verschiedene Gruppen von Menüoptionen können für die Geschäftszeiten und nach Geschäftszeiten erstellt werden, und Sie können namenswählen in den **Menüoptionen aktivieren oder deaktivieren.** Tasten können zugeordnet werden, um die Anrufe an:
  
- Eine Vermittlung, die standardmäßig der Taste „0" zugeordnet ist. Sie kann jedoch jeder anderen Taste erneut zugewiesen oder aus dem Menü entfernt werden.
- Eine Anrufwarteschleife.
- Eine andere automatische Attendant. Menüs mit mehreren Ebenen können eingerichtet werden, indem sie **eine** Menüoption in einer automatischen Attendant auf eine andere automatische Attendant mit einer eigenen Gruppe von Menüoptionen verweisen, die als "geschachtelte" automatische Attendant bezeichnet wird.
- Ein Microsoft Teams Benutzer, der über eine **Telefonsystem** verfügt, Enterprise-VoIP aktiviert ist oder dem Anrufpläne zugewiesen sind. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Dazu wählen Sie eine **Person in Ihrem Unternehmen** aus, deren Anrufe dann automatisch direkt an die Voicemail weitergeleitet werden.
  
Der Name jeder Menüoption wird zu einem Schlüsselwort für die Spracherkennung, wenn die Spracherkennung aktiviert ist. So können Anrufer beispielsweise "Eins" sagen, um die Menüoption auszuwählen, die der Taste "1" zugeordnet ist, oder "Vertrieb", um die Menüoption "Vertrieb" auszuwählen.
  
Zum Einrichten einer automatischen Attendant und der Menüoptionen wechseln Sie zu Einrichten [einer automatischen Cloud-Attendant.](create-a-phone-system-auto-attendant.md)
  
### <a name="assigning-phone-numbers-for-an-auto-attendant"></a>Zuweisen von Telefonnummern für eine automatische Telefon attendant

Sie können eine Microsoft-Dienstnummer, eine direkte Routingnummer oder eine Hybridnummer dem verknüpften Ressourcenkonto Ihrer automatischen Telefonleitung (oder mehreren Ressourcenkonten, wenn mehrere Telefonnummern gewünscht werden) zuordnen. Weitere [Informationen finden Sie unter Planen des direkten Routings.](direct-routing-plan.md)

Zum Zuweisen einer Leistungsnummer müssen Sie Ihre vorhandenen gebührenpflichtigen oder gebührenfreien Leistungsnummern erhalten oder portieren. Sobald Sie die gebührenpflichtigen oder gebührenfreien Servicenummern erhalten haben, werden diese in Skype for Business **Admin Center**  >  **Voice**  >  **Telefon Telefonnummern .** **Der Nummerntyp** ist als **Dienst – gebührenfrei aufgeführt.** Wie Sie Ihre Leistungsnummern erhalten, erfahren Sie unter Abrufen von Servicetelefonnummern für Skype for Business und [Microsoft Teams](./getting-service-phone-numbers.md) oder, wenn Sie Telefonnummern und vorhandene Servicenummern übertragen möchten, unter Übertragen von Telefonnummern an [Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)
  
> [!NOTE]
> Wenn Sie sich außerhalb der Vereinigten Staaten befinden, können Sie servicenummern nicht über Microsoft Teams Admin Center erhalten. Wechseln [Sie stattdessen zu Verwalten von Telefonnummern](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) für Ihre Organisation, um zu sehen, wie das geht.
  
## <a name="related-topics"></a>Verwandte Themen

[Vorteile des Telefonsystems](here-s-what-you-get-with-phone-system.md)

[Anfordern von Servicenummern für Skype for Business und Microsoft Teams](./getting-service-phone-numbers.md)

[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)