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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.autoattendants.overview
ms.custom:
- Phone System
description: Erfahren Sie, welche Cloud-automatischen Telefonzentralen sind und wie Sie verwendet werden.
ms.openlocfilehash: ae5d959918240cec63c925eff77653c54294e99c
ms.sourcegitcommit: 2f8b9c7c8d20f2605d09cae4bbaeb10667f2ddea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2019
ms.locfileid: "34330356"
---
# <a name="what-are-cloud-auto-attendants"></a>Was sind automatische Cloudtelefonzentralen?

Das Telefon System in Office 365 stellt automatische Telefonzentralen bereit, mit deren Hilfe externe und interne Anrufer über ein Menü System navigieren können, um Anrufe an Unternehmensbenutzer oder Abteilungen in Ihrer Organisation zu suchen und dort zu platzieren oder zu übertragen.
  
Bei einer automatischen Telefonzentrale handelt es sich um eine Reihe von Sprachansagen oder Audiodateien, die Anrufer hören, anstatt von einem menschlichen Netzbetreiber, wenn Sie eine Organisation anrufen. Wenn Personen eine Nummer anrufen, die einer automatischen Telefonzentrale zugeordnet ist, können Ihre Entscheidungen den Anruf an einen Benutzer umleiten oder jemanden in Ihrer Organisation suchen und dann eine Verbindung mit diesem Benutzer herstellen. Sie können Ihre Auswahl äußern und mit dem Menü System interagieren, indem Sie eine Telefontastatur (DTMF) oder Spracherkennung verwenden.
  
Zum Einrichten einer automatischen Telefonzentrale für das Telefon System in Office 365 wechseln Sie zu [Einrichten einer automatischen Cloud](create-a-phone-system-auto-attendant.md)-Telefonzentrale.
  
Eine automatische Cloud-Telefonzentrale verfügt über die folgenden Features:
  
- Sie kann Unternehmensbegrüßungen oder informative Begrüßungen bereitstellen.
- Sie kann benutzerdefinierte Unternehmensmenüs bereitstellen. Diese Menüs können Sie so anpassen, dass sie aus mehreren Ebenen bestehen.
- Sie bietet eine Verzeichnissuche, mit der Personen, die in das Verzeichnis der Organisation anrufen, nach einem Namen suchen können.
- Damit können Personen, die in Ihrer Organisation anrufen, eine Nachricht erreichen oder eine Nachricht hinterlassen.
- Sie unterstützt mehrere Sprachen für Eingabeaufforderungen, Text-zu-Sprache und Spracherkennung.
- Sie unterstützt die Angabe von Feiertagen und Geschäftszeiten.
- Sie unterstützt die Übertragung von Anrufen an einen Operator, andere Benutzer, Anrufwarteschlangen und automatische Telefonzentralen.

> [!NOTE]
> Dieser Artikel bezieht sich auf Microsoft Teams und Skype for Business Online.

## <a name="getting-started"></a>Erste Schritte

Die folgenden Punkte sind bei Ihrem Einstieg in die Verwendung von automatischen Telefonzentralen wichtig:

- Für eine automatische Telefonzentrale ist ein zugeordnetes Ressourcenkonto erforderlich. Details zu Ressourcenkonten finden Sie unter [Verwalten von Ressourcenkonten in Teams](manage-resource-accounts.md) .
- Wenn Sie eine direkte Routing Nummer zuweisen möchten, müssen Sie die folgenden Lizenzen für Ihre Ressourcenkonten \(Office 365 Enterprise E1, E3 oder E5 mit dem Add-on\)Phone System erwerben und zuweisen.
- Wenn Sie stattdessen eine Microsoft-Dienstnummer zuweisen, müssen Sie dem Ressourcenkonto \(Office 365 Enterprise E1, E3 oder E5 mit dem Telefon System-Add-on und einem Anrufplan die folgenden Lizenzen erwerben und zuweisen\).
- Sie müssen die Ressourcenkonten nur mit einer Telefonnummer lizenzieren, die Ihnen zugewiesen ist. In einer geschachtelten automatischen Telefonzentrale oder Anrufwarteschlange müssen Sie die restlichen automatischen Telefonzentralen oder Anrufwarteschlangen nicht lizenzieren, wenn Ihnen keine Telefonnummern zugeordnet sind. 

> [!NOTE]
> Direct Routing-Dienstnummern für die automatische Telefonzentrale und Anrufwarteschlangen werden nur für Microsoft Teams-Benutzer und-Agents unterstützt.

> [!NOTE]
> Microsoft arbeitet an einem kostenlosen Lizenzierungsmodell für Anwendungen wie automatische Cloud-Telefonzentralen und Anrufwarteschlangen, denn jetzt müssen Sie das Benutzer Lizenzierungsmodell verwenden.
    
   > [!TIP]
   > Wenn Sie Anrufe an einen Operator oder eine Menüoption umleiten möchten, bei der es sich um einen Online Benutzer mit einer **Telefon System** Lizenz handelt, müssen Sie diese für Enterprise-VoIP aktivieren oder Ihnen Anrufpläne zuweisen. Weitere Informationen finden Sie unter [Zuweisen von Microsoft Teams-Lizenzen](assign-teams-licenses.md). Sie können auch die Windows PowerShell verwenden. Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Um gebührenfreie Servicenummern für Ihre automatischen Telefonzentralen zu erhalten und zu verwenden, müssen Sie Kommunikationsguthaben einrichten. Informationen hierzu finden Sie unter [Was sind Kommunikationsguthaben?](what-are-communications-credits.md) und [Einrichten von Kommunikationsguthaben für Ihre Organisation](set-up-communications-credits-for-your-organization.md).

    > [!IMPORTANT]
    > Telefonnummern von Benutzern (Abonnenten) können automatischen Telefonzentralen nicht zugewiesen werden - es können nur gebührenpflichtige oder gebührenfreie Telefonnummern verwendet werden.

- Ein vollständiges System der automatischen Telefonzentrale umfasst in der Regel mehrere automatische Telefonzentralen und erfordert möglicherweise nur eine einzelne zugewiesene Telefonnummer für die automatische Telefonzentrale der obersten Ebene oder des Eintrags. Bei anderen automatischen Telefonzentralen oder Anrufwarteschlangen im gesamten System wird nur eine Telefonnummer benötigt, wenn Sie mehrere Einstiegspunkte in das System eingeben möchten.
- Es ist möglich, einer automatischen Telefonzentrale mehr als eine Telefonnummer zuzuweisen, indem Sie einer automatischen Telefonzentrale mehr als ein Ressourcenkonto zuordnen.
  
## <a name="feature-overview"></a>Funktionsübersicht

### <a name="dial-by-name"></a>Namensanwahl

Dial by Name ist eine Funktion einer automatischen Telefonzentrale, die auch als Verzeichnissuche bezeichnet wird. Damit können die Personen, die Ihre automatische Telefonzentrale anrufen, die Spracherkennung (Spracherkennung) oder Ihre DTMF-Antworten (Telefontastatur) verwenden, um einen vollständigen oder teilweisen Namen einzugeben, um das Firmenverzeichnis zu durchsuchen, die Person zu suchen und dann den Anruf an Sie zu übertragen. Benutzer, die Sie mit dem Namen "Dial by" gefunden und erreicht haben möchten, müssen **nicht über eine Telefonnummer verfügen oder Ihnen Anrufpläne zugeordnet haben, Sie müssen jedoch über eine Telefon System Lizenz verfügen, wenn Sie Online-Benutzer sind oder für lokale Benutzer aktiviert sind**. Durch die Wahl nach Namen können sogar Anrufe an Microsoft Teams-Benutzer, die in verschiedenen Ländern oder Regionen für multinationale Organisationen gehostet werden, gefunden und übertragen werden.

### <a name="maximum-directory-size"></a>Maximale Verzeichnisgröße

Die Active Directory-Größe, für die ein Dial by-Name unterstützt wird, ist unbegrenzt, wenn Sie die Telefontastatur verwenden, um nach der Eingabe von Teil-oder voll Namen zu suchen (Vorname + Nachname und auch Nachname + Vorname). Die maximale Namen Listengröße, die eine einzelne automatische Telefonzentrale mithilfe der Namenserkennung unterstützenkann, ist jedoch 80.000-Benutzer.
  
|Eingabetyp|Suchformat|Maximale Anzahl der Benutzer in einer Organisation|
|:-----|:-----|:-----|
|MFV (Eingabe über die Wähltastatur) |Teilweise  <br/> Vorname + Nachname  <br/> Nachname + Vorname |Keine Beschränkung  |
|Sprache (Spracheingabe) |Vorname  <br/> LastName  <br/> Vorname + Nachname  <br/> Nachname + Vorname  | 80.000-Benutzer |

> [!NOTE]
> Wenn Sie "Dial by Name" mit Spracherkennung verwenden, das Active Directory Ihrer Organisation jedoch größer als 80.000-Benutzer ist und Sie den Umfang der Wählfunktion nicht mit der Funktion "Wählbereich" beschränkt haben, funktioniert das Wählen nach Namen weiterhin für Ihre Anrufer mit einem Telefontasten Feld. und Spracheingaben sind für alle anderen Szenarien verfügbar. Sie können das Feature "Wählbereich" verwenden, um die Namen zu verkleinern, die erreichbar sind, indem Sie den Bereich des Wähl namens für eine bestimmte automatische Telefonzentrale ändern.
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>Namensanwahl - Eingabe über die Wähltastatur (MFV)

Personen, die sich einwählen, können mithilfe von Dial by Name die Benutzer erreichen, indem Sie entweder den vollständigen oder teilweise Namen der Person angeben, die Sie erreichen möchten. Es gibt verschiedene Formate, die verwendet werden können, wenn der Name eingegeben wird.

Wenn Sie das Verzeichnis Ihrer Organisation durchsuchen, können Benutzer die Taste "0" (null) verwenden, um ein Leerzeichen zwischen dem Vornamen und dem Nachnamen und dem letzten Namen anzugeben. Wenn Sie den Namen eingeben, werden Sie aufgefordert, ihren Tastatur Eintrag mit der #-Taste zu kündigen. Wenn Sie beispielsweise den Namen der Person eingeben, die Sie erreichen möchten, drücken Sie #. Wenn mehrere Namen gefunden werden, erhält der Gesprächspartner eine Liste der Namen, aus denen Sie auswählen können.
  
Anrufer können bei der Suche nach Namen in Ihrer Organisation über die Wähltastatur eines Telefons die folgenden Suchformate verwenden:
  
|Namensformat|Suchtyp|Beispiel|Suchergebnis|
|:-----|:-----|:-----|:-----|
|Vorname + Nachname |Vollständig  |Amos0Marble# |Amos Marble |
|Nachname + Vorname |Vollständig |Marble0Amos#  |Amos Marble |
|Vorname  |Vollständig   |Amos#   |Drücken Sie „1" für Amos Marble.  <br/> Drücken Sie „2" für Amos Marcus. |
|LastName |Vollständig |Marble#  |Drücken Sie „1" für Amos Marble.  <br/> Drücken Sie „2" für Mary Marble. |
|Vorname oder Nachname |Teilweise |Mar# |Drücken Sie „1" für Mary Marble.  <br/> Drücken Sie „2" für Mary Jones.  <br/> Drücken Sie „3" für Amos Marcus. |
|Vorname + Nachname |Teilweise |Mar0Amos# |Drücken Sie „1" für Amos Marble.  <br/> Drücken Sie „2" für Amos Marcus. |
|Nachname + Vorname |Teilweise |Mar0Am# |Drücken Sie „1" für Amos Marble.  <br/> Drücken Sie „2" für Amos Marcus. |

Bei der Suche nach Personen über die Wähltastatur eines Telefons können verschiedene Sonderzeichen verwendet werden. Die Person wird beispielsweise aufgefordert, die Pound-Taste (#) zu verwenden, während die NULL-Taste (0) für ein Leerzeichen zwischen den Namen verwendet wird. Wenn die Anrufer die Sterntaste (*) drücken, wird die Liste der übereinstimmenden Namen wiederholt.
  
|Sonderzeichen auf der Wähltastatur eines Telefons|Bedeutung|
|:-----|:-----|
|#   |Endzeichen bei der Eingabe eines Namens |
|0   |Leerschritt zwischen Namen |
|*    |Wiederholt die Liste der übereinstimmenden Namen. |

### <a name="dial-by-name---name-recognition-with-speech"></a>Namensanwahl - Namenserkennung mit Sprache

Personen können mithilfe ihrer Stimme (Spracherkennung) nach anderen Personen in Ihrer Organisation suchen. Sie können auch beliebige Personen im Active Directory des Unternehmens erreichen, indem Sie den Namen der Person sagen, die Sie suchen möchten. Durch die Verwendung von Spracheingaben können Namen in unterschiedlichen Formaten erkannt werden, einschließlich Vorname, Nachname, Vorname + Nachname oder Nachname + Vorname.
  
Wenn Sie die Spracherkennung für eine automatische Telefonzentrale aktivieren, wird die Telefontastatur Eingabe (DTMF) nicht deaktiviert, sodass beide Eingabetypen verwendet werden können. Der Telefontastatur Eintrag kann nicht deaktiviert werden und kann jederzeit verwendet werden, auch wenn die Spracherkennung für die automatische Telefonzentrale aktiviert ist.
  
Wie bei der Eingabe über die Wähltastatur eines Telefons wird den Anrufern, wenn mehrere Namen gefunden werden, eine Liste mit Namen zur Auswahl präsentiert.
  
Die Anrufer können Namen in den folgenden Formaten sagen:
  
|Name mit Sprache|Suchtyp|Beispiel|Suchergebnis|
|:-----|:-----|:-----|:-----|
|Vorname + Nachname |Vollständig |Amos Marble |Amos Marble |
|Nachname + Vorname |Vollständig  |Marble Amos |Amos Marble |
|Vorname |Vollständig |Amos |Drücken oder sagen Sie „1" für Amos Marble.  <br/> Drücken oder sagen Sie „2" für Amos Jones. |
|LastName |Vollständig |Marble |Drücken oder sagen Sie „1" für Amos Marble.  <br/> Drücken oder sagen Sie „2" für Ben Marble. |

> [!NOTE]
> Es kann bis zu 36 Stunden dauern, bis ein neuer Benutzer seinen Namen im Verzeichnis für Dial by Name mit Spracherkennung aufgrund von Active Directory-Replikationsverzögerungen auflistet.
  
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

Die Verwendung des Operators für eine automatische Telefonzentrale ist eine optionale Einstellung, die dem Anrufer die Möglichkeit bietet, mit einem menschlichen Operator zu sprechen.
  
Taste 0 und der Sprachbefehl "Operator" leiten den Anruf standardmäßig an den festgelegten Operator weiter. Dies gilt für alle Sprachen, die für die Spracherkennung unterstützt werden. Sie können auch **Menü Optionen** verwenden, um einen benutzerdefinierten Wert für den Operator zu definieren.
  
Der Operator kann auf Folgendes eingestellt werden:
  
- Ein Microsoft Teams-Benutzer oder ein Skype for Business-Benutzer, für den Enterprise-VoIP aktiviert ist.
  
- Eine andere für Ihre Organisation eingerichtete automatische Telefonzentrale
- Eine beliebige in Ihrer Organisation eingerichtete Anrufwarteschleife. Weitere Informationen zu Anrufwarteschlangen finden Sie unter [Erstellen einer Cloud-Anrufwarteschlange](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

### <a name="business-hours-and-call-handling"></a>Geschäftszeiten und Anrufbehandlung

Die Geschäftszeiten werden für jede automatische Telefonzentrale eingestellt. Wenn die Geschäftszeiten nicht gesetzt sind, gelten alle Tage und alle Stunden des Tages als Geschäftszeiten, da ein 24/7-Terminplan standardmäßig eingestellt ist. Geschäftszeiten können mit Zeit Unterbrechungen während des Tages festgesetzt werden, und alle Stunden, die nicht als Geschäftszeiten festgesetzt sind, gelten als After-Hours-Zeiten. Sie können verschiedene eingehende Anruf Behandlungsoptionen und verschiedene Begrüßungen (optional) einstellen, und beide können für Geschäfts-und After-Hours eingestellt werden.
  
Jede automatische Telefonzentrale verfügt über Anruf Behandlungsoptionen, die festgesetzt werden können:
  
- Sie können festlegen, dass ein Anruf direkt nach der Begrüßung getrennt wird.
- Sie können auch folgende Aktionen ausführen:
  - Leiten Sie den Anruf an einen Microsoft Teams-Benutzer weiter, der über eine **Telefon System** Lizenz verfügt, die für Enterprise-VoIP aktiviert ist oder denen Anrufpläne zugewiesen sind. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Dazu wählen Sie eine **Person in Ihrem Unternehmen** aus, deren Anrufe dann automatisch direkt an die Voicemail weitergeleitet werden.

  
  - Umleiten des Anrufs an eine Anrufwarteschlange Weitere Informationen zu Anrufwarteschlangen finden Sie unter [Erstellen einer Cloud-Anrufwarteschlange](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

  - Leiten Sie den Anruf an eine andere automatische Telefonzentrale weiter, die Sie eingerichtet haben.
- Menüoptionen erstellen und eine Menüansage für die Anrufer wiedergeben. Beispiel: „Drücken Sie ‚1' für den Vertrieb oder ‚2' für den Service. Durch Drücken von ‚0' können Sie jederzeit mit der Vermittlung sprechen."

### <a name="menu-options"></a>Menüoptionen

Automatische Cloud-Telefonzentralen ermöglichen Ihnen das Erstellen von Menüansagen ("drücken Sie 1 für Sales, drücken Sie 2 für Dienste"), und legen Sie Menü Optionen für die Weiterleitung von Anrufen basierend auf den vom Benutzer ausgewählten Einstellungen fest. Durch Einrichten von Menüoptionen für eine automatische Telefonzentrale können Organisationen die Anrufer interaktiv schneller an ihr Ziel führen, ohne dass dazu Vermittlungsmitarbeiter für die Abwicklung der eingehenden Anrufe benötigt werden. Menüansagen können mithilfe von Text-zu-Sprache (vom System generierten Eingabeaufforderungen) oder durch Hochladen einer aufgenommenen Audiodatei erstellt werden. Bei der Spracherkennung werden Sprachbefehle für Freisprechnavigation verwendet, aber die Anrufer können auch mithilfe der Wähltastatur eines Telefons in den Menüs navigieren.
  
Die Tasten 0 bis 9 können **Menü Optionen** in einer automatischen Telefonzentrale mithilfe des Skype for Business admin Centers zugewiesen werden. Unterschiedliche Menü Optionen können für Geschäfts-und After Hours erstellt werden, und in den **Menü Optionen**können Sie die Option "Dial by Name" aktivieren oder deaktivieren. Schlüssel können zugeordnet werden, um die Anrufe zu übertragen an:
  
- Eine Vermittlung, die standardmäßig der Taste „0" zugeordnet ist. Sie kann allerdings wieder einem anderen Schlüssel zugewiesen oder aus dem Menü entfernt werden.
- Eine Anrufwarteschlange
- Eine andere automatische Telefonzentrale. Menüs mit mehreren Ebenen können eingerichtet werden, indem eine **Menü Option** in einer automatischen Telefonzentrale auf eine andere automatische Telefonzentrale mit einer eigenen Gruppe von Menü Optionen verwiesen wird, die als "geschachtelte" automatische Telefonzentrale bezeichnet wird.
- Ein Microsoft Teams-Benutzer, der über eine **Telefon System** Lizenz verfügt, die Enterprise-VoIP aktiviert ist oder denen Anrufpläne zugewiesen sind. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Dazu wählen Sie eine **Person in Ihrem Unternehmen** aus, deren Anrufe dann automatisch direkt an die Voicemail weitergeleitet werden.
  
Wenn die Spracherkennung aktiviert wurde, wird der Name jeder Menüoption zu einem Schlüsselwort für die Spracherkennung. Anrufer können beispielsweise "eins" sagen, um die Menüoption auszuwählen, die Key 1 zugeordnet ist, oder Sie können einfach "Sales" sagen, um dieselbe Menüoption mit dem Namen "Sales" zu wählen.
  
Wenn Sie eine automatische Telefonzentrale und die Menü Optionen einrichten möchten, gehen Sie zu [Einrichten einer automatischen Cloud-Telefonzentrale](create-a-phone-system-auto-attendant.md).
  
### <a name="assigning-phone-numbers-for-an-auto-attendant"></a>Zuweisen von Telefonnummern für eine automatische Telefonzentrale

Sie können der automatischen Telefonzentrale eine Microsoft Calling Plan-Servicenummer oder eine Direct-Routing-Hybrid Nummer zuweisen. Weitere Informationen finden Sie unter [Planen des direkten Routings](direct-routing-plan.md) .

Wenn Sie eine Service-Nummer zuweisen möchten, müssen Sie Ihre bestehenden gebührenpflichtigen oder gebührenfreien Servicenummern abrufen oder übertragen. Sobald Sie die gebührenpflichtigen oder gebührenfreien Service-Telefonnummern erhalten haben, werden Sie im <!-- validate nav path --> **Skype for Business Admin Center** > **** > -**Telefonnummern**, und der angegebene **Nummerntyp** wird als **Service-gebührenfrei**aufgeführt. Informationen zum Abrufen Ihrer Servicenummern finden Sie unter [Abrufen von Service-Telefonnummern für Skype for Business und Microsoft Teams](/microsoftteams/getting-service-phone-numbers) oder, wenn Sie eine vorhandene Servicenummer übertragen möchten, finden Sie unter [übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Wenn Sie sich außerhalb der Vereinigten Staaten befinden, können Sie das Microsoft Teams Admin Center nicht verwenden, um Dienstnummern zu erhalten. Wechseln Sie stattdessen zu [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) , um zu erfahren, wie das geht.
  
## <a name="related-topics"></a>Verwandte Themen

[Das Telefonsystem in Office 365 bietet Ihnen Folgendes](here-s-what-you-get-with-phone-system.md)

[Anfordern von Servicenummern für Skype for Business und Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Beispiel für Kleinunternehmen – Einrichten einer automatischen Telefonzentrale](/microsoftteams/tutorial-org-aa)
