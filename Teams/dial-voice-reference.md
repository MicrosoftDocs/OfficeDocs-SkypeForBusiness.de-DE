---
title: Referenz zu automatischer Telefonant- und Anrufwarteschleifenwahl und Spracherkennung
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
description: Erfahren Sie mehr über die automatische Telefonant- und Anrufwarteschleifenwähl- und Spracherkennungsoptionen in Teams.
ms.openlocfilehash: 1cb8da2d2e6625de5a1471d1051c1ca51f11bbae
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918961"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>Referenz zu automatischer Telefonant- und Anrufwarteschleife

Die Namensanwahl ist ein Feature einer automatischen Telefon attendant, das auch als Verzeichnissuche bezeichnet wird. So können die Personen, die Ihre automatische Telefongesellschaft anrufen, Sprachanrufe (Spracherkennung) oder Antworten auf der Telefontaste (MFV) verwenden, um einen vollständigen oder teilweisen Namen ein eingeben, um das Verzeichnis des Unternehmens zu durchsuchen, die Person zu suchen und den Anruf dann an diese Person durchzusennen. Sie richten die Anrufdurchwahl nach Namen ein, [wenn Sie die Anrufflusseinstellungen in einer automatischen Telefon attendant konfigurieren.](create-a-phone-system-auto-attendant.md#call-flow)

## <a name="searching-for-users"></a>Suchen nach Benutzern

Benutzer, die Sie mit der Namensanwahl finden und erreichen möchten, müssen keine Telefonnummer haben oder Ihnen Anrufpläne zugewiesen sein, aber sie müssen Enterprise-VoIP für **Skype for Business Server-Benutzer** aktiviert sein. Die Namensanwahl kann sogar Anrufe an Microsoft Teams-Benutzer, die in verschiedenen Ländern oder Regionen für multinationale Organisationen gehostet werden, suchen und an diese übertragen. Angesichts der erforderlichen Voraussetzungen aktivieren Sie die Namensanwahl explizit in einer automatischen Telefon attendant.

Die Durchwahl ist ein Feature einer automatischen Telefon attendant, das auch Teil der Verzeichnissuche ist. Sie ermöglicht es den Personen, die Ihre automatische Telefon attendant anrufen, Sprachanrufe (Spracherkennung) oder die Tastensteuerung des Telefons (MFV) zu verwenden, um die Telefonerweiterung des Benutzers ein, den sie zu erreichen versuchen, und den Anruf dann an sie durchzusennen. Benutzer, die Sie mit der Durchwahl erreicht haben möchten, müssen keine Telefonnummer haben oder Ihnen keine Anrufpläne zugewiesen sein, aber sie müssen Enterprise-VoIP für  **Skype for Business Server-Benutzer** aktiviert sein. Außerdem benötigen Sie einen entsprechend konfigurierten Wählplan für Ihre Benutzer. Die Durchwahlerweiterung kann sogar Anrufe finden und an Microsoft Teams-Benutzer übertragen, die für multinationale Organisationen in verschiedenen Ländern oder Regionen gehostet werden. Angesichts der erforderlichen Voraussetzungen aktivieren Sie "Durchwahl wählen" explizit in einer automatischen Telefon attendant.

### <a name="maximum-directory-size"></a>Maximale Verzeichnisgröße

Es gibt kein Limit für die Anzahl der Active Directory-Benutzer, die nach Name wählen, und die Durchwahlerweiterung kann unterstützen, wenn ein Anrufer nach einer bestimmten Person sucht. Ein Anrufer kann Namen teilweise oder vollständig eingeben (Vorname + Nachname und auch Nachname + Vorname), benötigt aber die vollständige Durchwahlnummer. Die maximale Größe der Namensliste, die eine einzelne automatische Attendant mithilfe der Spracherkennung unterstützen kann, beträgt 80.000 Benutzer.
  
|Eingabetyp|Suchformat|Maximale Anzahl der Benutzer in einer Organisation|
|:-----|:-----|:-----|
|MFV (Eingabe über die Wähltastatur) |Teilweise  <br/> Vorname + Nachname  <br/> Nachname + Vorname |Kein Grenzwert  |
|Sprache (Spracheingabe) |Vorname  <br/> Nachname  <br/> Vorname + Nachname  <br/> Nachname + Vorname  | 80.000 Benutzer |

> [!NOTE]
> Wenn Sie die Namensanwahl mit Spracherkennung verwenden, active Directory aber größer als 80.000 Benutzer in Ihrer Organisation ist und Sie den Umfang der Namensanwahl nicht mithilfe der Funktion "Wählbereich" eingeschränkt haben, funktioniert die Namensanwahl weiterhin für Ihre Anrufer über die Wähltasten eines Telefons, und Spracheingaben stehen in allen anderen Szenarien zur Verfügung. Sie können die Funktion "Wählbereich" verwenden, um die namen, die erreichbar sind, durch Ändern des Bereichs von "Nach Name wählen" für eine bestimmte automatische Telefon attendant zu ändern.
  
## <a name="dial-by-name---keypad-dtmf-entry"></a>Namensanwahl - Eingabe über die Wähltastatur (MFV)
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

### <a name="dial-by-name---name-recognition-with-speech"></a>Namensanwahl - Namenserkennung mit Sprache

Personen können mit ihrer Stimme (Spracherkennung) nach anderen Personen in ihrer Organisation suchen. Sie können auch jede Person in Active Directory erreichen, indem sie den vollständigen oder teilweisen Namen der Person sagen, nach der sie suchen möchte. Mithilfe von Spracheingaben können Namen in verschiedenen Formaten erkannt werden, darunter "Vorname", "Nachname", "Vorname + Nachname" oder "Nachname + Vorname".
  
Sie können die Spracherkennung für eine automatische Telefon attendant aktivieren, aber die Eingabe über die Telefontaste (MFV) ist nicht deaktiviert. Die Eingabe über die Tastatur eines Telefons kann jederzeit verwendet werden, auch wenn die Spracherkennung in der automatischen Telefon attendant aktiviert ist.
  
Wie bei der Eingabe über die Wähltastatur eines Telefons hört die anruferde Person eine Liste mit Namen, aus der Sie auswählen können, wenn mehrere Namen gefunden werden.
  
Anrufer können Namen in den folgenden Formaten sagen:
  
|Name mit Sprache|Suchtyp|Beispiel|Suchergebnis|
|:-----|:-----|:-----|:-----|
|Vorname + Nachname |Vollständig |Amos Marble |Amos Marble |
|Nachname + Vorname |Vollständig  |Marble Amos |Amos Marble |
|Vorname |Vollständig |Amos |Drücken oder sagen Sie „1" für Amos Marble.  <br/> Drücken oder sagen Sie „2" für Amos Jones. |
|Nachname |Vollständig |Marble |Drücken oder sagen Sie „1" für Amos Marble.  <br/> Drücken oder sagen Sie „2" für Ben Marble. |
|Vorname oder Nachname |Teilweise |März |Drücken oder sagen Sie "1" für Mary Marble.  <br/> Drücken oder sagen Sie "2" für Mary Jones.  <br/> Drücken oder sagen Sie "3" für Amos Abt. |
|Vorname + Nachname |Teilweise |Amos Mar |Drücken oder sagen Sie „1" für Amos Marble.  <br/> Drücken oder sagen Sie "2" für Amos Abt. |


> [!NOTE]
> Es kann bis zu 36 Stunden dauern, bis ein neuer Benutzer seinen Namen aufgrund eines Zeitabstands bei der Active Directory-Replikation im Verzeichnis für Namensanwahl mit Spracherkennung aufgelistet hat.
  
## <a name="language-support"></a>Sprachunterstützung

Die folgenden Sprachen sind für Text-zu-Sprache verfügbar, der bei ausgehenden Eingabeaufforderungen verwendet wird:
  
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

Spracherkennungseingaben für automatische Attendanten sind in den folgenden Sprachen verfügbar:
  
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

## <a name="related-topics"></a>Verwandte Themen

[Das Telefonsystem bietet Ihnen Folgendes](here-s-what-you-get-with-phone-system.md)

[Anfordern von Servicenummern für Skype for Business und Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
