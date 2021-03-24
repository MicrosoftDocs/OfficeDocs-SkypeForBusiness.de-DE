---
title: Referenz zur automatischen Telefonkonferenz und Anrufwarteschlange
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
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
description: Erfahren Sie mehr über die Optionen für automatische Telefonkonferenz und Anrufwarteschlange in Teams.
ms.openlocfilehash: f62a04735d386637489d52956e6a064a2eba1e4e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098441"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>Referenz zur automatischen Telefonkonferenz und Anrufwarteschlange

Dial by Name ist ein Feature einer automatischen Telefonwarte, die auch als Verzeichnissuche bezeichnet wird. Es ermöglicht den Personen, die Ihre automatische Telefon telefonieren, die Spracherkennung oder die Antworten auf der Telefontastentaste (DTMF) zu verwenden, um einen vollständigen oder teilweisen Namen ein eingeben, um das Verzeichnis des Unternehmens zu durchsuchen, die Person zu suchen und dann den Anruf an sie übertragen zu lassen. Wenn Sie die Anrufflusseinstellungen in einer automatischen Telefonkonferenz konfigurieren, richten Sie die Wähleinstellungen nach [Name ein.](create-a-phone-system-auto-attendant.md#call-flow)

## <a name="searching-for-users"></a>Suchen nach Benutzern

Benutzer, die Sie mithilfe von Namenswahl finden und erreichen möchten, müssen nicht über eine Telefonnummer verfügen oder ihnen Anrufpläne zugewiesen haben, aber sie müssen Enterprise-VoIP für **Skype for Business Server-Benutzer** aktiviert sein. Nach Name wählen kann sogar Anrufe an Microsoft Teams-Benutzer finden und übertragen, die in verschiedenen Ländern oder Regionen für multinationale Organisationen gehostet werden. Angesichts der erforderlichen Voraussetzungen aktivieren Sie "Nach Name wählen" explizit in einer automatischen Telefon telefonieren.

Die Durchwahl ist ein Feature einer automatischen Telefonwarte, die ebenfalls Teil der Verzeichnissuche ist. Dies ermöglicht es den Personen, die Ihre automatische Telefon telefonieren, die Spracherkennung oder die Antworten auf der Telefontastentaste (DTMF) zu verwenden, um die Telefonerweiterung des Benutzers ein, den sie erreichen möchten, ein- und dann den Anruf an sie übertragen zu lassen. Benutzer, die Sie mithilfe der Durchwahl finden und erreicht haben möchten, müssen keine Telefonnummer haben oder ihnen Anrufpläne zugewiesen haben, aber sie müssen Enterprise-VoIP für  **Skype for Business Server-Benutzer** aktiviert sein. Außerdem benötigen Sie einen entsprechend konfigurierten Wählplan für Ihre Benutzer. Durch die Durchwahl können Sie sogar Anrufe an Microsoft Teams-Benutzer suchen und übertragen, die in verschiedenen Ländern oder Regionen für multinationale Organisationen gehostet werden. Angesichts der erforderlichen Voraussetzungen aktivieren Sie "Wählen nach Erweiterung" explizit in einer automatischen Telefon telefonieren.

### <a name="maximum-directory-size"></a>Maximale Verzeichnisgröße

Es gibt keinen Grenzwert für die Anzahl von Active Directory-Benutzern, die nach Name wählen und Durchwahl nach Durchwahl unterstützen können, wenn ein Anrufer nach einer bestimmten Person sucht. Ein Anrufer kann teilweise oder vollständige Namen (Vorname + Nachname und auch Nachname + Vorname) eingeben, benötigt jedoch die vollständige Durchwahlnummer. Die maximale Namenslistengröße, die von einer einzelnen automatischen Begleiter mithilfe der Spracherkennung unterstützt werden kann, beträgt 80.000 Benutzer.
  
|Eingabetyp|Suchformat|Maximale Anzahl der Benutzer in einer Organisation|
|:-----|:-----|:-----|
|MFV (Eingabe über die Wähltastatur) |Teilweise  <br/> Vorname + Nachname  <br/> Nachname + Vorname |Kein Grenzwert  |
|Sprache (Spracheingabe) |Vorname  <br/> Nachname  <br/> Vorname + Nachname  <br/> Nachname + Vorname  | 80.000 Benutzer |

> [!NOTE]
> Wenn Sie "Nach Name wählen" mit Spracherkennung verwenden, das Active Directory Ihrer Organisation jedoch größer als 80.000 Benutzer ist und Sie den Umfang der Funktion "Nach Name mit Wählbereich" nicht eingeschränkt haben, funktioniert "Nach Namen wählen" weiterhin für Ihre Anrufer über eine Telefontaste, und Spracheingaben sind für alle anderen Szenarien verfügbar. Sie können das Feature "Wählbereich" verwenden, um die zu erreichenden Namen zu verengungen, indem Sie den Bereich von "Nach Name wählen" für eine bestimmte automatische Telefonwarte ändern.
  
## <a name="dial-by-name---keypad-dtmf-entry"></a>Namensanwahl - Eingabe über die Wähltastatur (MFV)
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

### <a name="dial-by-name---name-recognition-with-speech"></a>Namensanwahl - Namenserkennung mit Sprache

Personen können mit ihrer Stimme (Spracherkennung) nach anderen Personen in ihrer Organisation suchen. Sie können auch jede Person in Active Directory erreichen, indem sie den vollständigen oder teilweisen Namen der Person sagen, die sie suchen möchte. Mithilfe von Spracheingaben können Namen in verschiedenen Formaten erkannt werden, einschließlich Vorname, Nachname, Vorname + Nachname oder Nachname + Vorname.
  
Sie können die Spracherkennung für eine automatische Telefonwarte aktivieren, aber die Eingabe der Telefontastentaste (DTMF) ist nicht deaktiviert. Die Telefontasteneingabe kann jederzeit verwendet werden, auch wenn die Spracherkennung auf der automatischen Telefon telefonieren aktiviert ist.
  
Wenn mehrere Namen gefunden werden, hört die anruferde Person wie bei der Eingabe der Telefontaste eine Liste der Namen, aus der Sie auswählen können.
  
Anrufer können Namen in den folgenden Formaten sagen:
  
|Name mit Sprache|Suchtyp|Beispiel|Suchergebnis|
|:-----|:-----|:-----|:-----|
|Vorname + Nachname |Vollständig |Amos Marble |Amos Marble |
|Nachname + Vorname |Vollständig  |Marble Amos |Amos Marble |
|Vorname |Vollständig |Amos |Drücken oder sagen Sie „1" für Amos Marble.  <br/> Drücken oder sagen Sie „2" für Amos Jones. |
|Nachname |Vollständig |Marble |Drücken oder sagen Sie „1" für Amos Marble.  <br/> Drücken oder sagen Sie „2" für Ben Marble. |
|Vorname oder Nachname |Teilweise |Mar |Drücken oder sagen Sie 1 für Mary Marble  <br/> Drücken oder sagen Sie 2 für Mary Jones  <br/> Drücken oder sagen Sie 3 für Amos Marcus |
|Vorname + Nachname |Teilweise |Amos Mar |Drücken oder sagen Sie „1" für Amos Marble.  <br/> Drücken oder sagen Sie 2 für Amos Marcus |


> [!NOTE]
> Es kann bis zu 36 Stunden dauern, bis ein neuer Benutzer seinen Namen im Verzeichnis für Namenswahl mit Spracherkennung aufgrund des Verzögerungsabstands der Active Directory-Replikation aufgelistet hat.
  
## <a name="language-support"></a>Sprachunterstützung

Die folgenden Sprachen stehen für Text-zu-Sprache zur Verfügung, die mit ausgehenden Eingabeaufforderungen verwendet werden:
  
|-|-|-|
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
  
|-|-|
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

## <a name="related-topics"></a>Verwandte Themen

[Vorteile des Telefonsystems](here-s-what-you-get-with-phone-system.md)

[Anfordern von Servicenummern für Skype for Business und Microsoft Teams](./getting-service-phone-numbers.md)

[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)