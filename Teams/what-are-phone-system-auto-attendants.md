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
description: Erfahren Sie mehr über automatische Cloud-Telefonkonferenzen und deren Verwendung, damit Anrufer durch ein Menüsystem wechseln können, um Anrufe an Benutzer oder Abteilungen zu suchen und zu platzieren oder zu übertragen.
ms.openlocfilehash: c8e5b3f608200036b8c9b9ed5338c558464b32d3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100961"
---
# <a name="what-are-cloud-auto-attendants"></a>Was sind automatische Cloud-Attendanten?

Telefonsystem stellt automatische Telefonkonferenzen zur Verfügung, mit denen externe und interne Anrufer durch ein Menüsystem wechseln können, um Anrufe an Benutzer oder Abteilungen in Ihrer Organisation zu suchen und zu platzieren oder zu übertragen.
  
Eine automatische Telefonkonferenz ist meistens ein Knoten in einem System, der einem Anrufer eine Reihe von Sprachaufforderungen oder Audiodateien gibt, die er anstelle eines menschlichen Operators hört. Wenn Personen eine Nummer anrufen, die einer automatischen Telefonwarte zugeordnet ist, können ihre Auswahlmöglichkeiten den Anruf an einen Benutzer umleiten oder jemanden in Ihrer Organisation suchen und dann eine Verbindung mit diesem Benutzer herstellen. Sie können ihre Auswahl ausdrücken und mit dem Menüsystem interagieren, indem sie eine Telefontaste (DTMF) oder spracherkennung verwenden. Die von ihnen getroffenen Optionen können den Anruf auch an eine andere automatische Telefonleitung oder an eine Anrufwarteschlange umleiten.
  
Zum Einrichten einer automatischen Telefon telefonanlage wechseln Sie zu Einrichten einer automatischen [Cloud-Telefonanlage.](create-a-phone-system-auto-attendant.md)
  
Eine automatische Cloud-Attendant verfügt über die folgenden Features:
  
- Sie kann Unternehmensbegrüßungen oder informative Begrüßungen bereitstellen.
- Sie kann benutzerdefinierte Unternehmensmenüs bereitstellen. Diese Menüs können Sie so anpassen, dass sie aus mehreren Ebenen bestehen.
- Sie bietet eine Verzeichnissuche, mit der Personen, die sich ein- und aussuchen, im Verzeichnis der Organisation nach einem Namen suchen können.
- Dadurch kann eine Person, die sich ein anruft, eine Nachricht für eine Person in Ihrer Organisation erreichen oder hinterlassen.
- Es unterstützt mehrere Sprachen für Eingabeaufforderungen, Text-zu-Sprache und Spracherkennung.
- Es unterstützt die Angabe von Feiertagen und Geschäftszeiten.
- Es unterstützt das Übertragen von Anrufen an einen Operator, andere Benutzer, Anrufwarteschlangen und automatische Telefonkonferenzen.
- Es unterstützt freigegebene Voicemail, damit Anrufer eine Nachricht für eine Organisation hinterlassen können.

> [!NOTE]
> Dieser Artikel bezieht sich auf Microsoft Teams und Skype for Business Online.

## <a name="getting-started"></a>Erste Schritte

Die folgenden Punkte sind bei Ihrem Einstieg in die Verwendung von automatischen Telefonzentralen wichtig:

- Eine automatische Attendant muss über ein zugeordnetes Ressourcenkonto verfügen. Details zu Ressourcenkonten finden Sie unter Verwalten von Ressourcenkonten [in Teams.](manage-resource-accounts.md) <!-- You can either use an existing resource account or create a new resource account as you set up your auto attendant. -->
- Wenn Sie einer automatischen Telefonwarte eine Telefonnummer zuweisen, weisen Sie sie streng genommen dem Ressourcenkonto zu, das dieser automatischen Telefonwarte zugeordnet ist. Dies bietet eine Möglichkeit, mehr als eine Telefonnummer auf eine automatische Telefonwarte zugreifen zu lassen. In den meisten Jahren verwendet ein Ressourcenkonto die lizenzfreie virtuelle Benutzerlizenz für Telefonsystem. Diese Lizenz bietet Telefonsystemfunktionen für Telefonnummern auf Organisationsebene und ermöglicht es Ihnen, automatische Telefonwarteschlangen und Anrufwarteschlangen zu erstellen.

> [!NOTE]
> Direkte Routingdienstnummern für automatische Telefonkonferenzen und Anrufwarteschlangen werden nur für Microsoft Teams-Benutzer und Anrufermitarbeiter unterstützt.

   > [!TIP]
   > Um Anrufe an einen Operator oder eine Menüoption  umzuleiten, bei der es sich um einen Onlinebenutzer mit einer Telefonsystemlizenz handelt, müssen Sie deren Konto für Enterprise-VoIP aktivieren oder ihm Anrufpläne zuweisen. Weitere Informationen finden Sie unter Zuweisen von [Microsoft Teams-Add-On-Lizenzen.](teams-add-on-licensing/assign-teams-add-on-licenses.md) Sie können auch die Windows PowerShell verwenden. Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Um gebührenfreie Servicenummern für Ihre automatischen Teilnehmer zu erhalten und zu verwenden, müssen Sie Guthaben für Kommunikationen einrichten. Informationen dazu finden Sie unter Was sind Guthaben für [Kommunikationen?](what-are-communications-credits.md) und [Einrichten von Guthaben für Kommunikationen für Ihre Organisation.](set-up-communications-credits-for-your-organization.md)

    > [!IMPORTANT]
    > Telefonnummern von Benutzern (Abonnenten) können automatischen Telefonzentralen nicht zugewiesen werden - es können nur gebührenpflichtige oder gebührenfreie Telefonnummern verwendet werden.

- Ein vollständiges automatisches Attendant-System ist in der Regel mit mehreren automatischen Attendanten ausgestattet.
- Es ist möglich, auf automatische Telefonanrufe der Einstiegsebene mehr als eine Telefonnummer anzuwenden.
- Automatische Telefonanrufe oder Anrufwarteschlangen im vollständigen System benötigen nur dann eine Telefonnummer, wenn sie ausgehende PSTN-Anrufe führen.
  
## <a name="feature-overview"></a>Übersicht über Features

### <a name="searching-for-users"></a>Suchen nach Benutzern

Dial by Name ist ein Feature einer automatischen Telefonwarte, die auch als Verzeichnissuche bezeichnet wird. Es ermöglicht den Personen, die Ihre automatische Telefon telefonieren, die Spracherkennung oder die Antworten auf der Telefontastentaste (DTMF) zu verwenden, um einen vollständigen oder teilweisen Namen ein eingeben, um das Verzeichnis des Unternehmens zu durchsuchen, die Person zu suchen und dann den Anruf an sie übertragen zu lassen. Benutzer, die Sie mithilfe von Namenswahl finden und erreicht haben möchten, müssen keine Telefonnummer haben oder ihnen Anrufpläne zugewiesen haben, aber sie müssen über eine Telefonsystemlizenz verfügen, wenn sie Onlinebenutzer sind, oder Enterprise-VoIP für **Skype for Business Server-Benutzer** aktiviert sein. Nach Name wählen kann sogar Anrufe an Microsoft Teams-Benutzer finden und übertragen, die in verschiedenen Ländern oder Regionen für multinationale Organisationen gehostet werden. Angesichts der erforderlichen Voraussetzungen aktivieren Sie "Nach Name wählen" explizit in einer automatischen Telefon telefonieren.

Die Durchwahl ist ein Feature einer automatischen Telefonwarte, die ebenfalls Teil der Verzeichnissuche ist. Dies ermöglicht es den Personen, die Ihre automatische Telefon telefonieren, die Spracherkennung oder die Antworten auf der Telefontastentaste (DTMF) zu verwenden, um die Telefonerweiterung des Benutzers ein, den sie erreichen möchten, ein- und dann den Anruf an sie übertragen zu lassen. Benutzer, die Sie mithilfe der Durchwahl finden und erreicht haben möchten, müssen nicht über eine Telefonnummer verfügen oder ihnen Anrufpläne zugewiesen haben, aber sie müssen über eine Telefonsystemlizenz verfügen, wenn sie Onlinebenutzer sind, oder Enterprise-VoIP für  **Skype for Business Server-Benutzer** aktiviert sein. Außerdem benötigen Sie einen entsprechend konfigurierten Wählplan für Ihre Benutzer. Durch die Durchwahl können Sie sogar Anrufe an Microsoft Teams-Benutzer suchen und übertragen, die in verschiedenen Ländern oder Regionen für multinationale Organisationen gehostet werden. Angesichts der erforderlichen Voraussetzungen aktivieren Sie "Wählen nach Erweiterung" explizit in einer automatischen Telefon telefonieren.

#### <a name="maximum-directory-size"></a>Maximale Verzeichnisgröße

Es gibt keinen Grenzwert für die Anzahl von Active Directory-Benutzern, die nach Name wählen und Durchwahl nach Durchwahl unterstützen können, wenn ein Anrufer nach einer bestimmten Person sucht. Ein Anrufer kann teilweise oder vollständige Namen (Vorname + Nachname und auch Nachname + Vorname) eingeben, benötigt jedoch die vollständige Durchwahlnummer. Die maximale Namenslistengröße, die von einer einzelnen automatischen Begleiter mithilfe der Spracherkennung unterstützt werden kann, beträgt 80.000 Benutzer.
  
|Eingabetyp|Suchformat|Maximale Anzahl der Benutzer in einer Organisation|
|:-----|:-----|:-----|
|MFV (Eingabe über die Wähltastatur) |Teilweise  <br/> Vorname + Nachname  <br/> Nachname + Vorname |Kein Grenzwert  |
|Sprache (Spracheingabe) |Vorname  <br/> Nachname  <br/> Vorname + Nachname  <br/> Nachname + Vorname  | 80.000 Benutzer |

> [!NOTE]
> Wenn Sie "Nach Name wählen" mit Spracherkennung verwenden, das Active Directory Ihrer Organisation jedoch größer als 80.000 Benutzer ist und Sie den Umfang der Funktion "Nach Name mit Wählbereich" nicht eingeschränkt haben, funktioniert "Nach Namen wählen" weiterhin für Ihre Anrufer über eine Telefontaste, und Spracheingaben sind für alle anderen Szenarien verfügbar. Sie können das Feature "Wählbereich" verwenden, um die zu erreichenden Namen zu verengungen, indem Sie den Bereich von "Nach Name wählen" für eine bestimmte automatische Telefonwarte ändern.
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>Namensanwahl - Eingabe über die Wähltastatur (MFV)

Personen, die sich einwählen, können mithilfe von "Nach Name wählen" Benutzer erreichen, indem sie entweder den vollständigen oder teilweisen Namen der Person angeben, die sie erreichen möchten. Es gibt verschiedene Formate, die verwendet werden können, wenn der Name eingegeben wird.

Beim Durchsuchen des Unternehmensverzeichnisses können Personen die Taste "0" (Null) verwenden, um ein Leerzeichen zwischen dem Vornamen und dem Nach- oder Nachnamen und dem Vornamen anzugeben. Wenn sie den Namen eingeben, werden sie aufgefordert, ihren Tastatureintrag mit der #-TASTE zu beenden. Beispiel: "Nachdem Sie den Namen der Person eingeben, die Sie erreichen möchten, drücken Sie #". Wenn mehrere Namen gefunden werden, wird der Anrufer eine Liste mit Namen zur Auswahl erhalten.
  
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

Bei der Suche nach Personen über die Wähltastatur eines Telefons können verschiedene Sonderzeichen verwendet werden. Beispielsweise wird die Person aufgefordert, die Pfundtaste (#) zu verwenden, während die Nulltaste (0) für ein Leerzeichen zwischen Namen verwendet wird. Wenn die Anrufer die Sterntaste (*) drücken, wird die Liste der übereinstimmenden Namen wiederholt.
  
|Sonderzeichen auf der Wähltastatur eines Telefons|Bedeutung|
|:-----|:-----|
|#   |Endzeichen bei der Eingabe eines Namens |
|0   |Leerschritt zwischen Namen |
|*    |Wiederholt die Liste der übereinstimmenden Namen. |

#### <a name="dial-by-name---name-recognition-with-speech"></a>Namensanwahl - Namenserkennung mit Sprache

Personen können mit ihrer Stimme (Spracherkennung) nach anderen Personen in ihrer Organisation suchen. Sie können auch jede Person in Active Directory erreichen, indem sie den Namen der Person sagen, die sie suchen möchte. Mithilfe von Spracheingaben können Namen in verschiedenen Formaten erkannt werden, einschließlich Vorname, Nachname, Vorname + Nachname oder Nachname + Vorname.
  
Sie können die Spracherkennung für eine automatische Telefonwarte aktivieren, aber die Eingabe der Telefontastentaste (DTMF) ist nicht deaktiviert. Die Telefontasteneingabe kann jederzeit verwendet werden, auch wenn die Spracherkennung auf der automatischen Telefon telefonieren aktiviert ist.
  
Wenn mehrere Namen gefunden werden, hört die anruferde Person wie bei der Eingabe der Telefontaste eine Liste der Namen, aus der Sie auswählen können.
  
Anrufer können Namen in den folgenden Formaten sagen:
  
|Name mit Sprache|Suchtyp|Beispiel|Suchergebnis|
|:-----|:-----|:-----|:-----|
|Vorname + Nachname |Vollständig |Amos Marble |Amos Marble |
|Nachname + Vorname |Vollständig  |Marble Amos |Amos Marble |
|Vorname |Vollständig |Amos |Drücken oder sagen Sie „1" für Amos Marble.  <br/> Drücken oder sagen Sie „2" für Amos Jones. |
|Nachname |Vollständig |Marble |Drücken oder sagen Sie „1" für Amos Marble.  <br/> Drücken oder sagen Sie „2" für Ben Marble. |

> [!NOTE]
> Es kann bis zu 36 Stunden dauern, bis ein neuer Benutzer seinen Namen im Verzeichnis für Namenswahl mit Spracherkennung aufgrund des Verzögerungsabstands der Active Directory-Replikation aufgelistet hat.
  
### <a name="language-support"></a>Sprachunterstützung

Die folgenden Sprachen stehen für Text-zu-Sprache zur Verfügung, die mit ausgehenden Eingabeaufforderungen verwendet werden:
  
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

Die Spracherkennungseingabe für automatische Teilnehmer ist in den folgenden Sprachen verfügbar:
  
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
|Ja | Drücken Sie 1 für Ja. |
|Nein | Drücken Sie 2 für Nein. |
|Wiederholen |Wiederholt die Liste der Optionen. Drücken Sie * auf der Tastatur, um die Liste der Optionen zu wiederholen. |
|Vermittlung | Drücken Sie 0 für "Operator" |
|Hauptmenü  |Die Anrufer gelangen zum Hauptmenü der automatischen Telefonzentrale. |
|Null | Drücken Sie 0 (standardmäßig mit "Operator").|
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

Eine automatische Telefonkonferenz kann optional so festgelegt werden, dass einem Anrufer eine Auswahl für die Sprachanrufe mit einem menschlichen Operator angezeigt wird.
  
Die Taste 0 und der Sprachbefehl "Operator" leitet den Anruf standardmäßig an den vorgesehenen Operator. Dies gilt für alle Sprachen, die für die Spracherkennung unterstützt werden. Sie können auch Menüoptionen **festlegen verwenden,** um einen benutzerdefinierten Wert für den Operator festlegen.
  
Der Operator kann auf festgelegt werden:
  
- Ein Microsoft Teams-Benutzer oder ein Skype for Business Server-Benutzer, der Enterprise-VoIP aktiviert ist.
- Eine andere für Ihre Organisation eingerichtete automatische Telefonzentrale
- Eine beliebige in Ihrer Organisation eingerichtete Anrufwarteschleife. Weitere Informationen zu Anrufwarteschlangen finden Sie unter [Erstellen einer Cloudanrufwarteschlange.](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

### <a name="business-hours-and-call-handling"></a>Geschäftszeiten und Anrufbehandlung

Geschäftszeiten können für jede automatische Attendant festgelegt werden. Wenn keine Geschäftszeiten festgelegt sind, gelten alle Tage und alle Stunden des Tages als Geschäftszeiten, da standardmäßig ein 24/7-Zeitplan festgelegt ist. Geschäftszeiten können mit Zeitumbrüchen während des Tages festgelegt werden, und alle Stunden, die nicht als Geschäftszeiten festgelegt sind, werden als Nachstunden betrachtet. Sie können unterschiedliche Optionen für die Anrufbehandlung und unterschiedliche Begrüßungen (optional) für Geschäfts- und Nachstunden festlegen.
  
Jede automatische Telefonkonferenz verfügt über mehrere mögliche Anrufbehandlungsoptionen:
  
- Der Anruf kann nach der Abspielung einer Begrüßung getrennt werden.
- Sie können auch folgende Aktionen ausführen:
  - Leiten Sie den Anruf an einen  Microsoft Teams-Benutzer weiter, der über eine Telefonsystemlizenz verfügt, die Enterprise-VoIP aktiviert ist oder denen Anrufpläne zugewiesen sind. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Dazu wählen Sie eine **Person in Ihrem Unternehmen** aus, deren Anrufe dann automatisch direkt an die Voicemail weitergeleitet werden.

  - Leiten Sie den Anruf an eine Anrufwarteschlange um. Weitere Informationen zu Anrufwarteschlangen finden Sie unter [Erstellen einer Cloudanrufwarteschlange.](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

  - Leiten Sie den Anruf an eine andere automatische Telefonleitung um.

Diese Optionen werden dem Anrufer von der automatischen Telefonkonferenz ausgedrückt, wenn menüaufforderungen wieder angezeigt werden. Beispiel: „Drücken Sie ‚1' für den Vertrieb oder ‚2' für den Service. Durch Drücken von ‚0' können Sie jederzeit mit der Vermittlung sprechen."

### <a name="set-menu-options"></a>Menüoptionen festlegen

Mit automatischen Cloud-Telefonkonferenzen können Sie Menüanforderungen erstellen ("Drücken Sie 1 für Vertrieb, 2 für Dienste") und Menüoptionen einrichten, um Anrufe basierend auf der Benutzerauswahl weiterzuvermitteln. Menüoptionen für eine automatische Telefonkonferenz ermöglichen es einer Organisation, eine Reihe von Auswahlmöglichkeiten zur Verfügung zu stellen, die Anrufer schneller an ihr Ziel führen, ohne sich bei der Verarbeitung eingehender Anrufe auf einen menschlichen Operator verlassen zu müssen. Menüanforderungen können entweder mithilfe von Text-zu-Sprache (vom System generierte Eingabeaufforderungen) oder durch Hochladen einer aufgezeichneten Audiodatei erstellt werden. Die Spracherkennung akzeptiert Sprachbefehle für die freihändige Navigation, aber Anrufer können auch die Telefontaste verwenden, um in Menüs zu navigieren.
  
Die Tasten 0 bis 9 können den Wähltasten in einer automatischen Telefonzentrale über das Skype for Business Admin Center zugewiesen werden. Verschiedene Gruppen von Menüoptionen können für Geschäftszeiten und nach Stunden erstellt werden, und Sie können "Nach Name wählen" in den **Menüoptionen aktivieren oder deaktivieren.** Schlüssel können zugeordnet werden, um die Anrufe an zu übertragen:
  
- Eine Vermittlung, die standardmäßig der Taste „0" zugeordnet ist. Sie kann jedoch einem beliebigen anderen Schlüssel erneut zugewiesen oder aus dem Menü entfernt werden.
- Eine Anrufwarteschlange.
- Eine weitere automatische Attendant. Menüs mit mehreren Ebenen können eingerichtet werden, indem eine Menüoption **in** einer automatischen Attendant auf eine andere automatische Attendant mit einer eigenen Gruppe von Menüoptionen verweisen, die als "geschachtelte" automatische Attendant bezeichnet wird.
- Ein Microsoft Teams-Benutzer, der über **eine** Telefonsystemlizenz verfügt, die Enterprise-VoIP aktiviert ist oder denen Anrufpläne zugewiesen sind. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Dazu wählen Sie eine **Person in Ihrem Unternehmen** aus, deren Anrufe dann automatisch direkt an die Voicemail weitergeleitet werden.
  
Der Name jeder Menüoption wird zu einem Schlüsselwort für die Spracherkennung, wenn die Spracherkennung aktiviert wurde. Anrufer können z. B. "One" sagen, um die Menüoption auszuwählen, die der Taste 1 zugeordnet ist, oder sie können "Umsatz" sagen, um dieselbe Menüoption mit dem Namen "Vertrieb" auszuwählen.
  
Zum Einrichten einer automatischen Attendant und der Menüoptionen wechseln Sie zu Einrichten einer automatischen [Cloud-Attendant](create-a-phone-system-auto-attendant.md).
  
### <a name="assigning-phone-numbers-for-an-auto-attendant"></a>Zuweisen von Telefonnummern für eine automatische Telefonwarte

Sie können dem verknüpften Ressourcenkonto Ihrer automatischen Telefonleitung eine Microsoft-Dienstnummer, eine direkte Routingnummer oder eine Hybridnummer zuweisen (oder mehreren Ressourcenkonten, wenn mehr als eine Telefonnummer gewünscht ist). Weitere [Details finden Sie unter Planen](direct-routing-plan.md) des direkten Routings.

Zum Zuweisen einer Dienstnummer müssen Sie Ihre vorhandenen gebührenpflichtigen oder gebührenfreien Servicenummern erhalten oder portieren. Sobald Sie die gebührenpflichtigen oder gebührenfreien Servicetelefonnummern erhalten haben, werden sie in **Skype for Business Admin Center** Voice Phone numbers (Voice phone) von Skype for Business (Skype for Business Admin Center  >  **Voice**  >  **Phone) gezeigt.** **Der Nummertyp** wird als **Dienst – Gebührenfrei aufgeführt.** Informationen zum Abrufen Ihrer Dienstnummern finden Sie unter Abrufen von Servicetelefonnummern für Skype for Business und [Microsoft Teams.](./getting-service-phone-numbers.md) Wenn Sie telefonnummern und vorhandene Servicenummern übertragen möchten, lesen Sie Übertragen von Telefonnummern [nach Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)
  
> [!NOTE]
> Wenn Sie sich außerhalb der Vereinigten Staaten befinden, können Sie das Microsoft Teams Admin Center nicht verwenden, um Servicenummern zu erhalten. Wechseln [Sie stattdessen zu Verwalten von](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) Telefonnummern für Ihre Organisation, um zu sehen, wie das geht.
  
## <a name="related-topics"></a>Verwandte Themen

[Vorteile des Telefonsystems](here-s-what-you-get-with-phone-system.md)

[Anfordern von Servicenummern für Skype for Business und Microsoft Teams](./getting-service-phone-numbers.md)

[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)