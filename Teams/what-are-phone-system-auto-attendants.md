---
title: Was sind automatische Cloud-Attendanten?
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
description: Hier erhalten Sie Informationen zu automatischen Cloud-Telefonisten und dazu, wie Sie Anrufer durch ein Menüsystem bewegen können, um Anrufe zu suchen und zu platzieren oder Anrufe an Benutzer oder Abteilungen zu übertragen.
ms.openlocfilehash: 862272ffe0cb42edc092c513823f421ab1c5bd95
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918941"
---
# <a name="what-are-cloud-auto-attendants"></a>Was sind automatische Cloud-Attendanten?

Das Telefonsystem stellt automatische Telefonkonferenzen zur Verfügung, mit denen externe und interne Anrufer durch ein Menüsystem wechseln können, um Anrufe zu suchen und zu platzieren oder Anrufe an Benutzer oder Abteilungen in Ihrer Organisation zu übertragen.
  
Eine automatische Telefonanlage ist meistens ein Knoten in einem System, der anrufer eine Reihe von Sprachanrufen oder Audiodateien gibt, die er anstelle einer menschlichen Netzbetreiber hört. Wenn Personen eine Nummer anrufen, die einer automatischen Telefon attendant zugeordnet ist, können sie den Anruf an einen Benutzer umleiten oder eine Person in Ihrer Organisation suchen und dann eine Verbindung mit diesem Benutzer herstellen. Sie können ihre Auswahl ausdrücken und mit dem Menüsystem interagieren, indem sie eine Telefontaste (MFV) oder die Spracherkennung verwenden. Die von ihnen getroffenen Optionen können den Anruf auch an eine andere automatische Telefonwarteschlange oder an eine Anrufwarteschleife umleiten.
  
Wechseln Sie zum Einrichten einer automatischen Telefonanlage für das Telefonsystem zu "Einrichten [einer automatischen Telefonanlage in der Cloud".](create-a-phone-system-auto-attendant.md)
  
Eine automatische Cloud-Attendant verfügt über die folgenden Features:
  
- Sie kann Unternehmensbegrüßungen oder informative Begrüßungen bereitstellen.
- Sie kann benutzerdefinierte Unternehmensmenüs bereitstellen. Diese Menüs können Sie so anpassen, dass sie aus mehreren Ebenen bestehen.
- Sie bietet eine Verzeichnissuche, mit der Anrufer das Verzeichnis der Organisation nach einem Namen durchsuchen können.
- Dadurch kann eine Person, die anruft, eine Nachricht für eine Person in Ihrer Organisation erreichen oder hinterlassen.
- Es unterstützt mehrere Sprachen für Eingabeaufforderungen, Text-zu-Sprache und Spracherkennung.
- Es unterstützt die Angabe von Feiertagen und Geschäftszeiten.
- Sie unterstützt die Übertragung von Anrufen an einen Netzbetreiber, andere Benutzer, Anrufwarteschleifen und automatische Telefonkonferenzen.
- Sie unterstützt freigegebene Voicemails, damit Anrufer Nachrichten für eine Organisation hinterlassen können.

> [!NOTE]
> Dieser Artikel bezieht sich auf Microsoft Teams und Skype for Business Online.

## <a name="getting-started"></a>Erste Schritte

Die folgenden Punkte sind bei Ihrem Einstieg in die Verwendung von automatischen Telefonzentralen wichtig:

- Eine automatische Attendant muss über ein zugeordnetes Ressourcenkonto verfügen. Details [zu Ressourcenkonten finden](manage-resource-accounts.md) Sie unter "Verwalten von Ressourcenkonten in Teams". <!-- You can either use an existing resource account or create a new resource account as you set up your auto attendant. -->
- Wenn Sie einer automatischen Telefon attendant eine Telefonnummer zuweisen, ordnen Sie diese dem Ressourcenkonto zu, das dieser automatischen Telefon attendant zugeordnet ist. Auf diese Weise können mehrere Telefonnummern auf eine automatische Telefon attendant zugreifen. Meistens wird für ein Ressourcenkonto die kostenlose virtuelle Benutzerlizenz des Telefonsystems verwendet. Diese Lizenz bietet Telefonsystemfunktionen für Telefonnummern auf Organisationsebene und ermöglicht ihnen das Erstellen von automatischen Telefonkonferenzen und Anrufwarteschleifen.

> [!NOTE]
> Direkte Routing-Servicenummern für automatische Telefonisten und Anrufwarteschleifen werden nur für Microsoft Teams-Benutzer und Nur-Telefonisten unterstützt.

   > [!TIP]
   > Um Anrufe an einen Netzbetreiber oder eine Menüoption  umzuleiten, bei dem es sich um einen Onlinebenutzer mit einer Telefonsystemlizenz handelt, müssen Sie sein Konto für Enterprise-VoIP aktivieren oder ihm Anrufpläne zuweisen. Weitere [Informationen finden Sie unter "Zuweisen von Microsoft Teams-Add-On-Lizenzen".](teams-add-on-licensing/assign-teams-add-on-licenses.md) Sie können auch die Windows PowerShell verwenden. Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Um gebührenfreie Servicenummern für Ihre automatischen Telefonnummern zu erhalten und zu verwenden, müssen Sie Guthaben für Kommunikationen einrichten. Informationen dazu finden Sie unter ["Was ist Guthaben für Kommunikationen?",](what-are-communications-credits.md) und richten Sie Guthaben für [Kommunikationen für Ihre Organisation ein.](set-up-communications-credits-for-your-organization.md)

    > [!IMPORTANT]
    > Telefonnummern von Benutzern (Abonnenten) können automatischen Telefonzentralen nicht zugewiesen werden - es können nur gebührenpflichtige oder gebührenfreie Telefonnummern verwendet werden.

- Ein vollständiges automatisches Attendant-System ist in der Regel mit mehreren automatischen Attendanten ausgestattet.
- Es ist möglich, mehrere Telefonnummern auf automatische Telefon telefonieren auf Einstiegsebene anzuwenden.
- Automatische Telefonwarteschleifen ohne Teilnahmeberechtigung oder Anrufwarteschleifen im vollständigen System benötigen nur dann eine Telefonnummer, wenn ausgehende Festnetzanrufe führen.
  
## <a name="feature-overview"></a>Featureübersicht

### <a name="searching-for-users"></a>Suchen nach Benutzern

Die Namensanwahl ist ein Feature einer automatischen Telefon attendant, das auch als Verzeichnissuche bezeichnet wird. So können die Personen, die Ihre automatische Telefongesellschaft anrufen, Sprachanrufe (Spracherkennung) oder Antworten auf der Telefontaste (MFV) verwenden, um einen vollständigen oder teilweisen Namen ein eingeben, um das Verzeichnis des Unternehmens zu durchsuchen, die Person zu suchen und den Anruf dann an diese Person durchzusennen. Benutzer, die Sie mit der Namensanwahl finden und erreichen möchten, müssen keine Telefonnummer oder Anrufpläne zugewiesen haben, aber sie müssen über eine Telefonsystemlizenz verfügen, wenn sie Onlinebenutzer sind oder Enterprise-VoIP für **Skype for Business Server-Benutzer** aktiviert ist. Die Namensanwahl ist sogar in der Lage, Anrufe zu Microsoft Teams-Benutzern zu finden und zu übertragen, die für multinationale Organisationen in verschiedenen Ländern oder Regionen gehostet werden. Angesichts der erforderlichen Voraussetzungen aktivieren Sie die Namensanwahl explizit in einer automatischen Telefon attendant.

Die Durchwahl ist ein Feature einer automatischen Telefon attendant, das auch Teil der Verzeichnissuche ist. So können die Personen, die Ihre automatische Telefon telefonieren, Sprachanrufe (Spracherkennung) oder die Tastensteuerung des Telefons (MFV) verwenden, um die Telefonerweiterung des Benutzers ein, den sie erreichen möchten, ein- und aus dem Anruf an diese zu übertragen. Benutzer, die Sie per Durchwahl finden und erreichen möchten, müssen keine Telefonnummer oder Anrufpläne zugewiesen haben, aber sie müssen über eine Telefonsystemlizenz verfügen, wenn sie Onlinebenutzer sind oder Enterprise-VoIP für  **Skype for Business Server-Benutzer** aktiviert ist. Außerdem benötigen Sie einen entsprechend konfigurierten Wählplan für Ihre Benutzer. Die Durchwahlerweiterung kann sogar Anrufe finden und an Microsoft Teams-Benutzer übertragen, die für multinationale Organisationen in verschiedenen Ländern oder Regionen gehostet werden. Angesichts der erforderlichen Voraussetzungen aktivieren Sie "Durchwahl wählen" explizit in einer automatischen Telefon attendant.

#### <a name="maximum-directory-size"></a>Maximale Verzeichnisgröße

Es gibt kein Limit für die Anzahl der Active Directory-Benutzer, die nach Name wählen, und die Durchwahlerweiterung kann unterstützen, wenn ein Anrufer nach einer bestimmten Person sucht. Ein Anrufer kann Namen teilweise oder vollständig eingeben (Vorname + Nachname und auch Nachname + Vorname), benötigt aber die vollständige Durchwahlnummer. Die maximale Größe der Namensliste, die eine einzelne automatische Attendant mithilfe der Spracherkennung unterstützen kann, beträgt 80.000 Benutzer.
  
|Eingabetyp|Suchformat|Maximale Anzahl der Benutzer in einer Organisation|
|:-----|:-----|:-----|
|MFV (Eingabe über die Wähltastatur) |Teilweise  <br/> Vorname + Nachname  <br/> Nachname + Vorname |Kein Grenzwert  |
|Sprache (Spracheingabe) |Vorname  <br/> Nachname  <br/> Vorname + Nachname  <br/> Nachname + Vorname  | 80.000 Benutzer |

> [!NOTE]
> Wenn Sie die Namensanwahl mit Spracherkennung verwenden, active Directory aber größer als 80.000 Benutzer in Ihrer Organisation ist und Sie den Umfang der Namensanwahl nicht mithilfe der Funktion "Wählbereich" eingeschränkt haben, funktioniert die Namensanwahl weiterhin für Ihre Anrufer über die Wähltasten eines Telefons, und Spracheingaben stehen in allen anderen Szenarien zur Verfügung. Sie können die Funktion "Wählbereich" verwenden, um die namen, die erreichbar sind, durch Ändern des Bereichs von "Nach Name wählen" für eine bestimmte automatische Telefon attendant zu ändern.
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>Namensanwahl - Eingabe über die Wähltastatur (MFV)

Anrufer können Benutzer über die Namenswahl erreichen, indem sie entweder den vollständigen oder teilweisen Namen der Person angeben, die sie erreichen möchten. Es gibt verschiedene Formate, die bei der Eingabe des Namens verwendet werden können.

Beim Durchsuchen des Verzeichnisses Ihrer Organisation können Benutzer die Taste "0" (Null) verwenden, um ein Leerzeichen zwischen dem Vornamen und dem Nach- oder Nachnamen und dem Vornamen anzugeben. Wenn sie den Namen eingeben, wird sie aufgefordert, die Eingabe über die Tastatur mit der #-Taste zu beenden. Beispiel: "Drücken Sie #, nachdem Sie den Namen der Person eingeben, die Sie erreichen möchten." Wenn mehrere Namen gefunden werden, wird dem Anrufer eine Liste mit Namen zur Auswahl angezeigt.
  
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

Bei der Suche nach Personen über die Wähltastatur eines Telefons können verschiedene Sonderzeichen verwendet werden. Beispielsweise wird die Person aufgefordert, die Nummerntaste (#) zu verwenden, während die Nulltaste (0) für ein Leerzeichen zwischen Namen verwendet wird. Wenn die Anrufer die Sterntaste (*) drücken, wird die Liste der übereinstimmenden Namen wiederholt.
  
|Sonderzeichen auf der Wähltastatur eines Telefons|Bedeutung|
|:-----|:-----|
|#   |Endzeichen bei der Eingabe eines Namens |
|0   |Leerschritt zwischen Namen |
|*    |Wiederholt die Liste der übereinstimmenden Namen. |

#### <a name="dial-by-name---name-recognition-with-speech"></a>Namensanwahl - Namenserkennung mit Sprache

Personen können mit ihrer Stimme (Spracherkennung) nach anderen Personen in ihrer Organisation suchen. Sie können auch jede Person in Active Directory erreichen, indem sie den Namen der Person sagen, nach der sie suchen möchte. Mithilfe von Spracheingaben können Namen in verschiedenen Formaten erkannt werden, darunter "Vorname", "Nachname", "Vorname + Nachname" oder "Nachname + Vorname".
  
Sie können die Spracherkennung für eine automatische Telefon attendant aktivieren, aber die Eingabe über die Telefontaste (MFV) ist nicht deaktiviert. Die Eingabe über die Tastatur eines Telefons kann jederzeit verwendet werden, auch wenn die Spracherkennung in der automatischen Telefon attendant aktiviert ist.
  
Wie bei der Eingabe über die Wähltastatur eines Telefons hört die anruferde Person eine Liste mit Namen, aus der Sie auswählen können, wenn mehrere Namen gefunden werden.
  
Anrufer können Namen in den folgenden Formaten sagen:
  
|Name mit Sprache|Suchtyp|Beispiel|Suchergebnis|
|:-----|:-----|:-----|:-----|
|Vorname + Nachname |Vollständig |Amos Marble |Amos Marble |
|Nachname + Vorname |Vollständig  |Marble Amos |Amos Marble |
|Vorname |Vollständig |Amos |Drücken oder sagen Sie „1" für Amos Marble.  <br/> Drücken oder sagen Sie „2" für Amos Jones. |
|Nachname |Vollständig |Marble |Drücken oder sagen Sie „1" für Amos Marble.  <br/> Drücken oder sagen Sie „2" für Ben Marble. |

> [!NOTE]
> Es kann bis zu 36 Stunden dauern, bis ein neuer Benutzer seinen Namen aufgrund eines Zeitabstands bei der Active Directory-Replikation im Verzeichnis für Namensanwahl mit Spracherkennung aufgelistet hat.
  
### <a name="language-support"></a>Sprachunterstützung

Die folgenden Sprachen sind für Text-zu-Sprache verfügbar, der bei ausgehenden Eingabeaufforderungen verwendet wird:
  
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

Spracherkennungseingaben für automatische Attendanten sind in den folgenden Sprachen verfügbar:
  
|A-F|F-Z|
|:-----|:-----|
|Chinesisch (ZH)  |Französisch (FR)  |
|Englisch (AU)  |Deutsch (DE)  |
|Englisch (CA)  |Italienisch (IT)  |
|Englisch (IN)  |Japanisch (JP)  |
|Englisch (Großbritannien)  |Portugiesisch (BR)  |
|Englisch (USA)  |Spanisch (ES)  |
|Französisch (CA)   |Spanisch (MX)  |

Die folgenden Sprachbefehle sind in den 14 Sprachen verfügbar, die für die Spracherkennung unterstützt werden:
  
|Sprachbefehl| Entspricht |
|:-----|:-----|
|Ja | Drücken Sie "1" für "Ja". |
|Nein | Drücken Sie "2" für "Nein". |
|Wiederholen |Wiederholt die Liste der Optionen. Drücken Sie * auf der Tastatur, um die Liste der Optionen zu wiederholen. |
|Vermittlung | Drücken Sie 0 für "Operator". |
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

Eine automatische Telefonkonferenz kann optional festgelegt werden, um einem Anrufer die Auswahl zu geben, mit einem menschlichen Operator zu sprechen.
  
Die Taste 0 und der Sprachbefehl "Operator" leitet den Anruf standardmäßig an den vorgesehenen Operator. Dies gilt für alle Sprachen, die für die Spracherkennung unterstützt werden. Sie können auch Menüoptionen **festlegen,** um einen benutzerdefinierten Wert für den Operator festlegen.
  
Der Operator kann auf:
  
- Ein Microsoft Teams-Benutzer oder ein Skype for Business Server-Benutzer, der Enterprise-VoIP aktiviert ist.
- Eine andere für Ihre Organisation eingerichtete automatische Telefonzentrale
- Eine beliebige in Ihrer Organisation eingerichtete Anrufwarteschleife. Weitere Informationen zu Anrufwarteschleifen finden Sie unter ["Erstellen einer Cloud-Anrufwarteschleife".](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

### <a name="business-hours-and-call-handling"></a>Geschäftszeiten und Anrufbehandlung

Die Geschäftszeiten können für jede automatische Attendant festgelegt werden. Wenn keine Geschäftszeiten festgelegt sind, werden alle Tage und alle Stunden des Tages als Geschäftszeiten betrachtet, da standardmäßig ein 24/7-Zeitplan festgelegt ist. Geschäftszeiten können mit Tagesferien festgelegt werden, und alle Stunden, die nicht als Geschäftszeiten festgelegt sind, werden als Arbeitsstunden betrachtet. Sie können verschiedene Optionen für die Anrufbehandlung sowie unterschiedliche Begrüßungen (optional) für Geschäftszeiten und Nachstunden festlegen.
  
Jede automatische Telefon attendant hat mehrere mögliche Anrufbehandlungsoptionen:
  
- Der Anruf kann nach der Abspielung einer Begrüßung getrennt werden.
- Sie können auch folgende Aktionen ausführen:
  - Leiten Sie den Anruf an einen  Microsoft Teams-Benutzer um, der über eine Telefonsystemlizenz verfügt, Enterprise-VoIP aktiviert ist oder dem Anrufpläne zugewiesen sind. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Dazu wählen Sie eine **Person in Ihrem Unternehmen** aus, deren Anrufe dann automatisch direkt an die Voicemail weitergeleitet werden.

  - Umleiten des Anrufs an eine Anrufwarteschleife Weitere Informationen zu Anrufwarteschleifen finden Sie unter ["Erstellen einer Cloud-Anrufwarteschleife".](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

  - Umleiten des Anrufs an eine andere automatische Telefon attendant

Diese Optionen werden dem Anrufer von der automatischen Telefon attendant bei der Eingabe von Menüanforderungen ausgedrückt. Beispiel: „Drücken Sie ‚1' für den Vertrieb oder ‚2' für den Service. Durch Drücken von ‚0' können Sie jederzeit mit der Vermittlung sprechen."

### <a name="set-menu-options"></a>Menüoptionen festlegen

Mit automatischen Cloud-Telefonkonferenzen können Sie Menüanforderungen erstellen ("Drücken Sie 1 für den Vertrieb, Drücken Sie 2 für Dienste") und Menüoptionen einrichten, um Anrufe basierend auf der Benutzerauswahl weiterzuvermitteln. Menüoptionen für eine automatische Telefongesellschaft ermöglichen es einer Organisation, eine Reihe von Auswahlmöglichkeiten zur Verfügung zu stellen, die Anrufer schneller an ihr Ziel führen, ohne sich für die Verarbeitung eingehender Anrufe auf einen menschlichen Operator verlassen zu müssen. Menüanforderungen können entweder mithilfe von Text-zu-Sprache (vom System generierte Eingabeaufforderungen) oder durch Hochladen einer aufgezeichneten Audiodatei erstellt werden. Die Spracherkennung akzeptiert Sprachbefehle für die Freisprechnavigation, aber auch Anrufer können über die Telefontaste in den Menüs navigieren.
  
Die Tasten 0 bis 9 können den Tasten in einer automatischen Telefonzentrale über das Skype for Business Admin Center zugewiesen werden. Verschiedene Gruppen von Menüoptionen können für die Geschäftszeiten und nach Geschäftszeiten erstellt werden, und Sie können die Namenswahl in den **Menüoptionen aktivieren oder deaktivieren.** Schlüssel können zugeordnet werden, um die Anrufe durch:
  
- Eine Vermittlung, die standardmäßig der Taste „0" zugeordnet ist. Sie kann jedoch jeder anderen Taste erneut zugewiesen oder aus dem Menü entfernt werden.
- Eine Anrufwarteschleife.
- Eine andere automatische Attendant. Menüs mit mehreren Ebenen können eingerichtet werden, indem sie **eine** Menüoption in einer automatischen Attendant auf eine andere automatische Attendant mit einer eigenen Gruppe von Menüoptionen verweisen, die als "geschachtelte" automatische Attendant bezeichnet wird.
- Ein Microsoft Teams-Benutzer, der über eine **Telefonsystemlizenz** verfügt, Enterprise-VoIP aktiviert ist oder dem Anrufpläne zugewiesen sind. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Dazu wählen Sie eine **Person in Ihrem Unternehmen** aus, deren Anrufe dann automatisch direkt an die Voicemail weitergeleitet werden.
  
Der Name jeder Menüoption wird zu einem Schlüsselwort für die Spracherkennung, wenn die Spracherkennung aktiviert wurde. Anrufer können z. B. "Eins" sagen, um die Menüoption auszuwählen, die der Taste "1" zugeordnet ist, oder "Vertrieb", um dieselbe Menüoption namens "Vertrieb" auszuwählen.
  
Wechseln Sie zum Einrichten einer automatischen Attendant und der Menüoptionen zu ["Einrichten einer automatischen Cloud-Attendant".](create-a-phone-system-auto-attendant.md)
  
### <a name="assigning-phone-numbers-for-an-auto-attendant"></a>Zuweisen von Telefonnummern für eine automatische Telefon attendant

Sie können eine Microsoft-Dienstnummer, eine direkte Routingnummer oder eine Hybridnummer dem verknüpften Ressourcenkonto Ihrer automatischen Telefon attendant zuordnen (oder mehreren Ressourcenkonten, wenn mehrere Telefonnummern gewünscht werden). Weitere [Informationen finden Sie unter "Planen des direkten Routings".](direct-routing-plan.md)

Zum Zuweisen einer Servicenummer müssen Sie Ihre vorhandenen gebührenpflichtigen oder gebührenfreien Leistungsnummern erhalten oder portieren. Nachdem Sie die gebührenpflichtigen oder gebührenfreien Servicenummern erhalten haben, werden sie in **den Skype for Business Admin Center** Voice  >    >  **Phone-Nummern.** **Der Nummerntyp** wird als **"Dienst – gebührenfrei" aufgeführt.** Wenn Sie Ihre Servicenummern erhalten möchten, lesen Sie "Erhalten von Servicetelefonnummern für Skype for Business und [Microsoft Teams".](/microsoftteams/getting-service-phone-numbers) Wenn Sie Telefonnummern übertragen möchten und vorhandene Servicenummern vorhanden sind, lesen Sie "Telefonnummern an [Teams übertragen".](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)
  
> [!NOTE]
> Wenn Sie sich außerhalb der USA befinden, können Sie servicenummern nicht über das Microsoft Teams Admin Center erhalten. Wechseln [Sie stattdessen zum Verwalten von Telefonnummern](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) für Ihre Organisation, um zu sehen, wie das geht.
  
## <a name="related-topics"></a>Verwandte Themen

[Das Telefonsystem bietet Ihnen Folgendes](here-s-what-you-get-with-phone-system.md)

[Anfordern von Servicenummern für Skype for Business und Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
