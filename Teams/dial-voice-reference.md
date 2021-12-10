---
title: Referenz zu automatischer Telefonant- und Anrufwarteschleifen-Wähl- und Spracherkennung
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: Erfahren Sie mehr über die automatische Telefon attendant und die Optionen für Anrufwarteschleifenwählen und Spracherkennung in Teams.
ms.openlocfilehash: 7ea18f5ca1f9fba619fe00f28e93e245a7a8f074
ms.sourcegitcommit: 38a4d2f41270633479afb3412c749365922554e5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2021
ms.locfileid: "61410676"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>Referenz zu automatischer Telefonant- und Anrufwarteschleifen-Wähl- und Spracherkennung

"Nach Name wählen" oder "Durchwahl" ist eine automatische Telefonkonferenzfunktion, mit der Anrufer Teams in Ihrer Organisation erreichen können. Mithilfe der Sprach- oder Telefontastenanrufe können Anrufer den vollständigen oder teilweisen Namen oder die Durchwahl der Person, die sie erreichen möchten, sagen oder eingeben. Die automatische Telefongesellschaft durchsucht das Firmenverzeichnis, sucht die Person und übertiert dann den Anrufer.  Namensanwahl oder Durchwahl durch Durchwahl sind Optionen, die Sie einrichten, wenn Sie die Anrufflusseinstellungen [in einer automatischen Telefonkonferenz konfigurieren.](create-a-phone-system-auto-attendant.md#call-flow)


## <a name="searching-for-users"></a>Suchen nach Benutzern

Teams Benutzer, die über die Namensanwahl erreicht werden können, müssen keine Telefonnummer oder Anrufpläne **haben,** aber sie müssen für Enterprise-VoIP Benutzer Skype for Business Server sein. Bei multinationalen Organisationen werden mit der Namensanwahl Anrufer für Benutzer in Microsoft Teams verschiedenen Ländern oder Regionen suchen und übertragen.

Teams Benutzer, die über die Durchwahl erreichbar sind, müssen keine Telefonnummer oder Anrufpläne **haben,** aber sie müssen für Skype for Business Server-Benutzer Enterprise-VoIP aktiviert sein. Darüber hinaus benötigen Sie einen entsprechend konfigurierten Wählplan für Ihre Benutzer. Bei multinationalen Organisationen finden und übertragen die Durchwahlanrufe Anrufer Microsoft Teams Benutzer in verschiedenen Ländern oder Regionen. 

Angesichts der erforderlichen Voraussetzungen muss "Nach Name wählen" oder "Durchwahl" beim Konfigurieren einer automatischen Telefonant explizit aktiviert sein.

### <a name="maximum-directory-size"></a>Maximale Verzeichnisgröße

Es gibt keine Beschränkung der Anzahl der Active Directory-Benutzer, die die Namensanwahl und die Durchwahl per Durchwahl unterstützen können, wenn ein Anrufer nach einer bestimmten Person sucht. Ein Anrufer kann Namen teilweise oder vollständig eingeben (Vorname + Nachname und auch Nachname + Vorname), benötigt aber die vollständige Durchwahlnummer. Die maximale Größe der Namensliste, die eine einzelne automatische Attendant mithilfe der Spracherkennung unterstützen kann, beträgt 80.000 Benutzer.
  
|Eingabetyp|Suchformat|Maximale Anzahl der Benutzer in einer Organisation|
|:-----|:-----|:-----|
|MFV (Eingabe über die Wähltastatur) |Teilweise  <br/> Vorname + Nachname  <br/> Nachname + Vorname |Kein Grenzwert  |
|Sprache (Spracheingabe) |Vorname  <br/> Nachname  <br/> Vorname + Nachname  <br/> Nachname + Vorname  | 80.000 Benutzer |

> [!NOTE]
> Wenn Sie die Namensanwahl mit Spracherkennung verwenden, active Directory aber mehr als 80.000 Benutzer in Ihrer Organisation [](create-a-phone-system-auto-attendant.md#dial-scope) ist und Sie den Bereich der Namensanwahl nicht mithilfe der Funktion "Wählbereich" eingeschränkt haben, funktioniert die Namensanwahl weiterhin für Ihre Anrufer über die Wähltasten eines Telefons, und Spracheingaben stehen in allen anderen Szenarien zur Verfügung. Sie können das Feature "Wählbereich" verwenden, um die Namen zu ein grenzen, die erreichbar sind, indem Sie den Bereich der Namensanwahl für eine bestimmte automatische Telefon attendant ändern.
 
### <a name="search-considerations"></a>Überlegungen zur Suche 
Namenswählen durchsucht das Verzeichnis der Organisation und filtert die Ergebnisse nach konfigurierten Ein- oder Ausschließen von Wählbereichslisten. Wenn die erste Suche mehr als 100 Benutzer zurückgibt, werden die Listen des Wählbereichs nicht angewendet, die Suche fehlschlägt, und dem Anrufer wird mitgeteilt, dass zu viele Namen gefunden wurden.
 
 
## <a name="dial-by-name---keypad-dtmf-entry"></a>Namensanwahl - Eingabe über die Wähltastatur (MFV)
Anrufer können Benutzer über die Namenswahl erreichen, indem sie entweder den vollständigen oder teilweisen Namen der Person angeben, die sie erreichen möchten. Es gibt verschiedene Formate, die verwendet werden können, wenn der Name eingegeben wird.

Beim Durchsuchen des Verzeichnisses Ihrer Organisation können Benutzer die Taste "0" (Null) verwenden, um ein Leerzeichen zwischen dem Vornamen und dem Nach- oder Nachnamen und dem Vornamen anzugeben. Wenn sie den Namen eingeben, wird sie aufgefordert, die Eingabe über die Tastatur mit der Taste # zu beenden. Beispiel: "Drücken Sie #, nachdem Sie den Namen der Person eingeben, die Sie erreichen möchten." Wenn mehrere Namen gefunden werden, wird der Anrufer eine Liste mit Namen zur Auswahl angezeigt.

> [!NOTE]
> Wenn nach der Anwendung von Ein- oder Ausschließen von Wählbereichslisten mehr als fünf Namen verbleiben, wird die Suche fehlschlagen, und dem Anrufer wird mitgeteilt, dass zu viele Namen gefunden wurden. 
  
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

### <a name="dial-by-name---name-recognition-with-speech"></a>Namensanwahl - Namenserkennung mit Sprache

Personen können mit ihrer Stimme (Spracherkennung) nach anderen Personen in ihrer Organisation suchen. Sie können auch jede Person in Active Directory erreichen, indem sie den vollständigen oder teilweisen Namen der Person sagt, nach der sie suchen möchte. Mithilfe von Spracheingaben können Namen in verschiedenen Formaten erkannt werden, darunter "Vorname", "Nachname", "Vorname + Nachname" oder "Nachname + Vorname".
  
Sie können die Spracherkennung für eine automatische Telefon attendant aktivieren, aber die Eingabe über die Telefontaste (MFV) ist nicht deaktiviert. Telefon Eingabe über die Tastatur kann jederzeit verwendet werden, auch wenn die Spracherkennung in der automatischen Attendant aktiviert ist.
  
Wie bei der Eingabe über die Wähltastatur eines Telefons hört die Anrufer eine Liste mit Namen, aus der Sie auswählen können, wenn mehrere Namen gefunden werden.

> [!NOTE]
> Wenn nach der Anwendung von Ein- oder Ausschließen von Wählbereichslisten mehr als fünf Namen verbleiben, wird die Suche fehlschlagen, und dem Anrufer wird mitgeteilt, dass zu viele Namen gefunden wurden. 
  
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
> Es kann bis zu 36 Stunden dauern, bis ein neuer Benutzer seinen Namen aufgrund von Active Directory-Replikationsverzögerung im Verzeichnis für Namensanwahl mit Spracherkennung aufgeführt hat.
  
## <a name="language-support"></a>Sprachunterstützung

Sprachunterstützung für Text-zu-Sprache und Spracherkennung ist in diesen [unterstützten Sprachen verfügbar.](create-a-phone-system-auto-attendant-languages.md)

Die folgenden Sprachbefehle sind für die Spracherkennung verfügbar: 
  
|Sprachbefehl| Entspricht |
|:-----|:-----|
|Ja | Drücken Sie 1 für Ja. |
|Nein | Drücken Sie 2, um "Nein" zu drücken. |
|Wiederholen |Wiederholt die Liste der Optionen. Drücken Sie * auf der Tastatur, um die Liste der Optionen zu wiederholen. |
|Anbieter | Drücken Sie "0" für "Operator". |
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

[Anfordern von Servicenummern für Skype for Business und Microsoft Teams](./getting-service-phone-numbers.md)

[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
