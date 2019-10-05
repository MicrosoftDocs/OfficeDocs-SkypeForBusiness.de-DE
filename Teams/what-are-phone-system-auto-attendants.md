---
title: Was sind automatische Cloud-Telefonzentralen?
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
ms.openlocfilehash: 43b5b023660c22a719b84079416df8ac3a7cff98
ms.sourcegitcommit: d349922409f49b52048597a56b81501163749a69
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/05/2019
ms.locfileid: "37401859"
---
# <a name="what-are-cloud-auto-attendants"></a>Was sind automatische Cloud-Telefonzentralen?

Das Telefon System in Office 365 stellt automatische Telefonzentralen bereit, mit deren Hilfe externe und interne Anrufer über ein Menü System navigieren können, um Anrufe an Benutzer oder Abteilungen in Ihrer Organisation zu suchen und dort zu platzieren oder zu übertragen.
  
Eine automatische Telefonzentrale ist in der Regel ein Knoten in einem System und gibt dem Anrufer eine Reihe von Sprachansagen oder Audiodateien, die Sie hören, anstatt eines menschlichen Netzbetreibers. Wenn Personen eine Nummer anrufen, die einer automatischen Telefonzentrale zugeordnet ist, können Ihre Entscheidungen den Anruf an einen Benutzer umleiten oder jemanden in Ihrer Organisation suchen und dann eine Verbindung mit diesem Benutzer herstellen. Sie können Ihre Auswahl äußern und mit dem Menü System interagieren, indem Sie eine Telefontastatur (DTMF) oder Spracherkennung verwenden. Die von Ihnen vorgenommenen Optionen können auch den Anruf an eine andere automatische Telefonzentrale oder an eine Anrufwarteschlange umleiten.
  
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

- Für eine automatische Telefonzentrale ist ein zugeordnetes Ressourcenkonto erforderlich. Details zu Ressourcenkonten finden Sie unter [Verwalten von Ressourcenkonten in Teams](manage-resource-accounts.md) . <!-- You can either use an existing resource account or create a new resource account as you set up your auto attendant. -->
- Wenn Sie einer automatischen Telefonzentrale eine Telefonnummer zuweisen, weisen Sie Sie streng genommen dem Ressourcenkonto zu, das der automatischen Telefonzentrale zugeordnet ist. Auf diese Weise können mehr als eine Telefonnummer auf eine automatische Telefonzentrale zugreifen. In den meisten Fällen wird für ein Ressourcenkonto die virtuelle Benutzerlizenz für das ﻿kostenlose Telefon System verwendet. Diese Lizenz bietet Telefon System Funktionen für Telefonnummern auf Organisationsebene und ermöglicht Ihnen das Erstellen von automatischen Telefonzentralen und Anrufwarteschlangen.

> [!NOTE]
> Direct Routing-Dienstnummern für die automatische Telefonzentrale und die Anrufwarteschlangen werden nur für Microsoft Teams-Benutzer und Anruf-Agents unterstützt.

   > [!TIP]
   > Wenn Sie Anrufe an einen Operator oder eine Menüoption umleiten möchten, bei der es sich um einen Online Benutzer mit einer **Telefon System** Lizenz handelt, müssen Sie sein Konto für Enterprise-VoIP aktivieren oder ihm Anrufpläne zuweisen. Nähers hierzu erfahren Sie unter [Zuweisen von Microsoft Teams-Lizenzen](assign-teams-licenses.md). Sie können auch die Windows PowerShell verwenden. Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Um gebührenfreie Servicenummern für Ihre automatischen Telefonzentralen zu erhalten und zu verwenden, müssen Sie Kommunikationsguthaben einrichten. Informationen hierzu finden Sie unter [Was sind Kommunikationsguthaben?](what-are-communications-credits.md) und [Einrichten von Kommunikationsguthaben für Ihre Organisation](set-up-communications-credits-for-your-organization.md).

    > [!IMPORTANT]
    > Telefonnummern von Benutzern (Abonnenten) können automatischen Telefonzentralen nicht zugewiesen werden - es können nur gebührenpflichtige oder gebührenfreie Telefonnummern verwendet werden.

- Ein vollständiges System der automatischen Telefonzentrale umfasst in der Regel mehrere automatische Telefonzentralen und erfordert möglicherweise nur eine einzelne zugewiesene Telefonnummer für die automatische Telefonzentrale der obersten Ebene oder des Eintrags. Bei anderen automatischen Telefonzentralen oder Anrufwarteschlangen im gesamten System wird nur eine Telefonnummer benötigt, wenn Sie mehrere Einstiegspunkte in das System eingeben möchten.
- Es ist möglich, einer automatischen Telefonzentrale mehr als eine Telefonnummer zuzuweisen, indem Sie einer automatischen Telefonzentrale mehr als ein Ressourcenkonto zuordnen.
  
## <a name="feature-overview"></a>Funktionsübersicht

### <a name="searching-for-users"></a>Suchen nach Benutzern

Dial by Name ist eine Funktion einer automatischen Telefonzentrale, die auch als Verzeichnissuche bezeichnet wird. Damit können die Personen, die Ihre automatische Telefonzentrale anrufen, die Spracherkennung (Spracherkennung) oder Ihre DTMF-Antworten (Telefontastatur) verwenden, um einen vollständigen oder teilweisen Namen einzugeben, um das Firmenverzeichnis zu durchsuchen, die Person zu suchen und dann den Anruf an Sie zu übertragen. Benutzer, die Sie über den Namen "Dial by" gefunden und erreicht haben möchten, müssen **nicht über eine Telefonnummer verfügen oder Ihnen Anrufpläne zugeordnet haben, Sie müssen jedoch über eine Telefon System Lizenz verfügen, wenn Sie Online-Benutzer sind oder Enterprise-VoIP für Skype for Business Server aktiviert sind. Benutzer**aus. Durch die Wahl nach Namen können sogar Anrufe an Microsoft Teams-Benutzer, die in verschiedenen Ländern oder Regionen für multinationale Organisationen gehostet werden, gefunden und übertragen werden. Wenn Sie die erforderlichen Voraussetzungen erfüllt haben, aktivieren Sie in einer automatischen Telefonzentrale explizit Dial by Name.

Dial by Extension ist eine Funktion einer automatischen Telefonzentrale, die ebenfalls Teil der Verzeichnissuche ist. Sie ermöglicht es den Personen, die Ihre automatische Telefonzentrale anrufen, die Spracherkennung (Spracherkennung) oder Ihre DTMF-Antworten (Telefontastatur) zu verwenden, um die Durchwahl des Benutzers einzugeben, den Sie erreichen möchten, und dann den Anruf an Sie übertragen zu lassen. Benutzer, die Sie mit Dial by Extension gefunden und erreicht haben möchten, müssen **nicht über eine Telefonnummer verfügen oder Ihnen Anrufpläne zugeordnet haben, Sie müssen aber über eine Telefon System Lizenz verfügen, wenn Sie Online-Benutzer sind oder Enterprise-VoIP für Skype for Business aktiviert ist. Server Benutzer**. Außerdem benötigen Sie einen entsprechend konfigurierten Wählplan für Ihre Benutzer. Dial by Extension kann sogar Anrufe an Microsoft Teams-Nutzer finden und übertragen, die in verschiedenen Ländern oder Regionen für multinationale Organisationen gehostet werden. Wenn Sie die erforderlichen Voraussetzungen erfüllen, aktivieren Sie in einer automatischen Telefonzentrale explizit die Durchwahlnummer.

#### <a name="maximum-directory-size"></a>Maximale Verzeichnisgröße

Die Anzahl der Active Directory-Benutzer, die nach Namen wählen, und die Durchwahl können unterstützen, wenn ein Anrufer nach einer bestimmten Person sucht. Ein Anrufer kann Teil-oder vollständige Namen (Vorname + Nachname und auch Nachname + Vorname) eingeben, benötigt aber die vollständige Durchwahlnummer. Die maximale Namen Listengröße, die eine einzelne automatische Telefonzentrale mithilfe der Spracherkennung unterstützenkann, ist 80.000-Benutzer.
  
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

#### <a name="dial-by-name---name-recognition-with-speech"></a>Namensanwahl - Namenserkennung mit Sprache

Personen können mit ihrer Stimme (Spracherkennung) nach anderen Personen in Ihrer Organisation suchen. Sie können auch beliebige Personen in Active Directory erreichen, indem Sie den Namen der Person sagen, die Sie suchen möchten. Durch die Verwendung von Spracheingaben können Namen in unterschiedlichen Formaten erkannt werden, einschließlich Vorname, Nachname, Vorname + Nachname oder Nachname + Vorname.
  
Sie können die Spracherkennung für eine automatische Telefonzentrale aktivieren, aber die Telefontastatur Eingabe (DTMF) ist nicht deaktiviert. Die Telefontastatur Eingabe kann jederzeit verwendet werden, auch wenn die Spracherkennung für die automatische Telefonzentrale aktiviert ist.
  
Wenn mehrere Namen gefunden werden, wird wie bei der Telefontastatur Eingabe eine Liste der Namen angezeigt, aus denen Sie auswählen können.
  
Anrufer können Namen in den folgenden Formaten sagen:
  
|Name mit Sprache|Suchtyp|Beispiel|Suchergebnis|
|:-----|:-----|:-----|:-----|
|Vorname + Nachname |Vollständig |Amos Marble |Amos Marble |
|Nachname + Vorname |Vollständig  |Marble Amos |Amos Marble |
|Vorname |Vollständig |Amos |Drücken oder sagen Sie „1" für Amos Marble.  <br/> Drücken oder sagen Sie „2" für Amos Jones. |
|LastName |Vollständig |Marble |Drücken oder sagen Sie „1" für Amos Marble.  <br/> Drücken oder sagen Sie „2" für Ben Marble. |

> [!NOTE]
> Es kann bis zu 36 Stunden dauern, bis ein neuer Benutzer seinen Namen im Verzeichnis für Dial by Name mit Spracherkennung aufgrund von Active Directory-Replikationsverzögerungen auflistet.
  
### <a name="language-support"></a>Sprachunterstützung

Die folgenden Sprachen sind für Text-zu-Sprache mit ausgehenden Eingabeaufforderungen verfügbar:
  
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

Die sprach Erkennungs Eingabe für automatische Telefonzentralen steht in den folgenden Sprachen zur Verfügung:
  
|||
|:-----|:-----|
|Chinesisch (ZH)  |Französisch (FR)  |
|Englisch (AU)  |Deutsch (DE)  |
|Englisch (CA)  |Italienisch (IT)  |
|Englisch (IN)  |Japanisch (JP)  |
|Englisch (Großbritannien)  |Portugiesisch (BR)  |
|Englisch (USA)  |Spanisch (ES)  |
|Französisch (CA)   |Spanisch (MX)  |

Die folgenden Sprachbefehle stehen in den 14 für die Spracherkennung unterstützten Sprachen zur Verfügung:
  
|Sprachbefehl| Entspricht |
|:-----|:-----|
|Ja | Drücken Sie 1 für Yes. |
|Nein | Drücken Sie 2 für Nein. |
|Wiederholen |Wiederholt die Liste der Optionen. Drücken Sie * auf der Tastatur, um die Liste der Optionen zu wiederholen. |
|Vermittlung | Drücken Sie 0 für "Operator" |
|Hauptmenü  |Die Anrufer gelangen zum Hauptmenü der automatischen Telefonzentrale. |
|Null | Drücken Sie 0 (standardmäßig wie "Operator").|
|Eins | Drücken Sie 1. |
|Zwei | Drücken Sie 2. |
|Drei| Drücken Sie 3.|
|Vier | Drücken Sie 4. |
|Fünf | Drücken Sie 5. |
|Sechs  | Drücken Sie 6. |
|Sieben | Drücken Sie 7.|
|Acht |Drücken Sie 8.|
|Neun  |Drücken Sie 9.|

### <a name="the-operator-option"></a>Die Option "Operator"

Eine automatische Telefonzentrale kann optional so eingestellt werden, dass ein Anrufer eine Auswahl erhält, um mit einem menschlichen Operator zu sprechen.
  
Taste 0 und der Sprachbefehl "Operator" leiten den Anruf standardmäßig an den festgelegten Operator weiter. Dies gilt für alle Sprachen, die für die Spracherkennung unterstützt werden. Sie können auch **Menü Optionen einstellen** verwenden, um einen benutzerdefinierten Wert für den Operator zu definieren.
  
Der Operator kann auf Folgendes eingestellt werden:
  
- Ein Microsoft Teams-Benutzer oder ein Skype for Business Server-Benutzer, für den Enterprise-VoIP aktiviert ist.
- Eine andere für Ihre Organisation eingerichtete automatische Telefonzentrale
- Eine beliebige in Ihrer Organisation eingerichtete Anrufwarteschleife. Weitere Informationen zu Anrufwarteschlangen finden Sie unter [Erstellen einer Cloud-Anrufwarteschlange](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

### <a name="business-hours-and-call-handling"></a>Geschäftszeiten und Anrufbehandlung

Die Geschäftszeiten können für jede automatische Telefonzentrale eingestellt werden. Wenn die Geschäftszeiten nicht gesetzt sind, gelten alle Tage und alle Stunden des Tages als Geschäftszeiten, da ein 24/7-Terminplan standardmäßig eingestellt ist. Geschäftszeiten können mit Zeit Unterbrechungen während des Tages festgesetzt werden, und alle Stunden, die nicht als Geschäftszeiten festgesetzt sind, gelten als After-Hours-Zeiten. Sie können verschiedene eingehende Anruf Behandlungsoptionen und verschiedene Begrüßungen (die optional sind) für Geschäfts-und After-Hours-Zeiten einstellen.
  
Jede automatische Telefonzentrale verfügt über mehrere mögliche Anruf Behandlungsoptionen:
  
- Der Anruf kann nach der Wiedergabe einer Ansage getrennt werden.
- Sie können auch folgende Aktionen ausführen:
  - Leiten Sie den Anruf an einen Microsoft Teams-Benutzer weiter, der über eine **Telefon System** Lizenz verfügt, die für Enterprise-VoIP aktiviert ist oder denen Anrufpläne zugewiesen sind. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Dazu wählen Sie eine **Person in Ihrem Unternehmen** aus, deren Anrufe dann automatisch direkt an die Voicemail weitergeleitet werden.

  - Umleiten des Anrufs an eine Anrufwarteschlange Weitere Informationen zu Anrufwarteschlangen finden Sie unter [Erstellen einer Cloud-Anrufwarteschlange](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

  - Leiten Sie den Anruf an eine andere automatische Telefonzentrale weiter.

Diese Optionen werden dem Anrufer von der automatischen Telefonzentrale beim Abspielen von Menüansagen angezeigt. Beispiel: „Drücken Sie ‚1' für den Vertrieb oder ‚2' für den Service. Durch Drücken von ‚0' können Sie jederzeit mit der Vermittlung sprechen."

### <a name="set-menu-options"></a>Menü Optionen einstellen

Automatische Cloud-Telefonzentralen ermöglichen Ihnen das Erstellen von Menüansagen ("drücken Sie 1 für Sales, drücken Sie 2 für Dienste"), und richten Sie Menü Optionen zum Weiterleiten von Anrufen basierend auf der Benutzerauswahl ein. Mit den Menü Optionen für eine automatische Telefonzentrale können Organisationen eine Reihe von Optionen zur Verfügung stellen, mit denen Anrufer schneller an Ihr Ziel weitergeleitet werden können, ohne dass Sie sich auf einen menschlichen Netzbetreiber verlassen können, der eingehende Anrufe übernimmt. Menüansagen können entweder mithilfe von Text-zu-Sprache (vom System generierte Eingabeaufforderungen) oder durch Hochladen einer aufgezeichneten Audiodatei erstellt werden. Spracherkennung akzeptiert Sprachbefehle für die Freisprech Navigation, aber auch Anrufer können über die Tastatur des Telefons in Menüs navigieren.
  
Die Tasten 0 bis 9 können Wähltasten in einer automatischen Telefonzentrale mithilfe des Skype for Business admin Centers zugewiesen werden. Unterschiedliche Menü Optionen können für Geschäfts-und After Hours erstellt werden, und in den **Menü Optionen**können Sie die Option "Dial by Name" aktivieren oder deaktivieren. Schlüssel können zugeordnet werden, um die Anrufe zu übertragen an:
  
- Eine Vermittlung, die standardmäßig der Taste „0" zugeordnet ist. Sie kann jedoch einem anderen Schlüssel zugewiesen oder aus dem Menü entfernt werden.
- Eine Anrufwarteschlange
- Eine andere automatische Telefonzentrale. Menüs mit mehreren Ebenen können eingerichtet werden, indem eine **Menü Option** in einer automatischen Telefonzentrale auf eine andere automatische Telefonzentrale mit einer eigenen Gruppe von Menü Optionen verwiesen wird, die als "geschachtelte" automatische Telefonzentrale bezeichnet wird.
- Ein Microsoft Teams-Benutzer, der über eine **Telefon System** Lizenz verfügt, die Enterprise-VoIP aktiviert ist oder denen Anrufpläne zugewiesen sind. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Dazu wählen Sie eine **Person in Ihrem Unternehmen** aus, deren Anrufe dann automatisch direkt an die Voicemail weitergeleitet werden.
  
Wenn die Spracherkennung aktiviert wurde, wird der Name jeder Menüoption zu einem Schlüsselwort für die Spracherkennung. Anrufer können beispielsweise "eins" sagen, um die Menüoption auszuwählen, die Key 1 zugeordnet ist, oder Sie können "Sales" sagen, um dieselbe Menüoption mit dem Namen "Sales" zu wählen.
  
Wenn Sie eine automatische Telefonzentrale und die Menü Optionen einrichten möchten, gehen Sie zu [Einrichten einer automatischen Cloud-Telefonzentrale](create-a-phone-system-auto-attendant.md).
  
### <a name="assigning-phone-numbers-for-an-auto-attendant"></a>Zuweisen von Telefonnummern für eine automatische Telefonzentrale

Sie können dem verknüpften Ressourcenkonto der automatischen Telefonzentrale eine Microsoft-Dienstnummer, eine direkte Routingnummer oder eine Hybrid Nummer zuweisen (oder mehrere Ressourcenkonten, wenn mehr als eine Telefonnummer erwünscht ist). Weitere Informationen finden Sie unter [Planen des direkten Routings](direct-routing-plan.md) .

Wenn Sie eine Dienstnummer zuweisen möchten, müssen Sie Ihre vorhandenen gebührenpflichtigen oder gebührenfreien Servicenummern abrufen oder portieren. Sobald Sie die gebührenpflichtigen oder gebührenfreien Telefonnummern für Dienstleistungen erhalten haben, werden Sie in **Skype for Business Admin Center** > -**sprach** > **Telefonnummern**angezeigt. Der **Nummerntyp** ist als **Service-gebührenfrei**aufgeführt. Informationen zum Abrufen Ihrer Servicenummern finden Sie unter [Abrufen von Service-Telefonnummern für Skype for Business und Microsoft Teams](/microsoftteams/getting-service-phone-numbers) oder, wenn Sie eine vorhandene Servicenummer übertragen möchten, finden Sie unter [übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Wenn Sie sich außerhalb der Vereinigten Staaten befinden, können Sie das Microsoft Teams Admin Center nicht verwenden, um Dienstnummern zu erhalten. Wechseln Sie stattdessen zu [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) , um zu erfahren, wie das geht.
  
## <a name="related-topics"></a>Verwandte Themen

[Das Telefonsystem in Office 365 bietet Ihnen Folgendes](here-s-what-you-get-with-phone-system.md)

[Anfordern von Servicenummern für Skype for Business und Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Beispiel für Kleinunternehmen – Einrichten einer automatischen Telefonzentrale](/microsoftteams/tutorial-org-aa)
