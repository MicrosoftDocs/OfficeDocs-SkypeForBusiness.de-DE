---
title: Referenz zur automatischen Telefonzentrale und Anrufwarteschleife und Spracherkennung
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
description: Erfahren Sie mehr über die Optionen für automatische Telefonzentrale und Anrufwarteschleifenwählen und Spracherkennung in Teams.
ms.openlocfilehash: 93a20be62f09ed7b636c593ecac48927d70e237f
ms.sourcegitcommit: 55ba3ed53421da6619724a360d15e80262241079
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2022
ms.locfileid: "67070726"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>Referenz zur automatischen Telefonzentrale und Anrufwarteschleife und Spracherkennung

Die Namens- oder Erweiterungswahl ist eine automatische Telefonzentrale, mit der Anrufer Teams-Benutzer in Ihrer Organisation erreichen können. Mithilfe ihrer Sprach- oder Telefontastatur können Anrufer den vollständigen oder teilweisen Namen oder die Erweiterung der Person, die sie erreichen möchten, sagen oder eingeben. Die automatische Telefonzentrale durchsucht das Firmenverzeichnis, sucht die Person und übernimmt dann den Anrufer.  "Dial by Name" oder "Dial by Extension" sind Optionen, die Sie einrichten, wenn Sie [die Anrufflusseinstellungen in einer automatischen Telefonzentrale konfigurieren](create-a-phone-system-auto-attendant.md?tabs=call-flow).

## <a name="searching-for-users"></a>Suchen nach Benutzern

Teams-Benutzer, die mithilfe der Namensanwahl erreicht werden können, **müssen weder über eine Telefonnummer verfügen noch Ihnen Anrufpläne zugewiesen haben, sie müssen jedoch für Skype for Business Server Benutzer Enterprise-VoIP aktiviert sein**. Bei multinationalen Organisationen findet und überträgt die Namensanwahl Anrufer an Microsoft Teams-Benutzer, die sich in verschiedenen Ländern oder Regionen befinden.

Teams-Benutzer, die mithilfe von "Durchwahl" erreicht werden können, **müssen weder eine Telefonnummer haben noch ihnen Anrufpläne zugewiesen haben, aber sie müssen für Skype for Business Server Benutzer Enterprise-VoIP aktiviert sein**. Außerdem benötigen Sie einen entsprechend konfigurierten Wählplan für Ihre Benutzer. Bei multinationalen Organisationen finden und übertragen Dial by Extension Anrufer an Microsoft Teams-Benutzer, die sich in verschiedenen Ländern oder Regionen befinden.

Angesichts der erforderlichen Voraussetzungen muss die Namens- oder Durchwahl beim Konfigurieren einer automatischen Telefonzentrale explizit aktiviert werden.

### <a name="maximum-directory-size"></a>Maximale Verzeichnisgröße

Es gibt keine Beschränkung für die Anzahl der Active Directory-Benutzer, die "Nach Name wählen" und "Nach Erweiterung wählen" unterstützen können, wenn ein Anrufer nach einer bestimmten Person sucht. Ein Aufrufer kann einen teil- oder vollständigen Namen (Vorname + Nachname und auch Nachname + Vorname) eingeben, benötigt jedoch die vollständige Durchwahlnummer. Die maximale Namenslistengröße, die eine einzelne automatische Telefonzentrale mithilfe der Spracherkennung unterstützen kann, beträgt 80.000 Benutzer.
  
|Eingabetyp|Suchformat|Maximale Anzahl der Benutzer in einer Organisation|
|:-----|:-----|:-----|
|MFV (Eingabe über die Wähltastatur) |Teilweise  <br/> Vorname + Nachname  <br/> Nachname + Vorname |Kein Grenzwert  |
|Sprache (Spracheingabe) |Firstname  <br/> Lastname  <br/> Vorname + Nachname  <br/> Nachname + Vorname  | 80.000 Benutzer |

> [!NOTE]
> Wenn Sie "Namensanwahl" mit Spracherkennung verwenden, das Active Directory Ihrer Organisation jedoch größer als 80.000 Benutzer ist und Sie den Bereich der Namensanwahl mithilfe der Funktion " [Wählbereich](create-a-phone-system-auto-attendant.md?tabs=dial-scope) " nicht eingeschränkt haben, funktioniert "Namenswählen" für Anrufer weiterhin mithilfe einer Telefontastatur, und Spracheingaben sind für alle anderen Szenarien verfügbar. Sie können das Feature "Wählbereich" verwenden, um die erreichbaren Namen einzugrenzen, indem Sie den Bereich der Namensanwahl für eine bestimmte automatische Telefonzentrale ändern.

### <a name="search-considerations"></a>Überlegungen zur Suche

Die Namenswahl durchsucht zuerst das verzeichnis der gesamten Organisation, bevor konfigurierte Ein- oder Ausschlusslisten für den Wählbereich angewendet werden. Wenn die anfängliche Suche im gesamten Verzeichnis mehr als 100 Benutzer zurückgibt, werden die Wählbereichslisten nicht angewendet, die Suche schlägt fehl, und dem Anrufer wird mitgeteilt, dass zu viele Namen gefunden wurden.

## <a name="dial-by-name---keypad-dtmf-entry"></a>Namensanwahl - Eingabe über die Wähltastatur (MFV)

Anrufer können "Namensanwahl" verwenden, um Benutzer zu erreichen, indem sie entweder den vollständigen oder teilweisen Namen der Person angeben, die sie erreichen möchten. Es gibt verschiedene Formate, die verwendet werden können, wenn der Name eingegeben wird.

Beim Durchsuchen des Verzeichnisses Ihrer Organisation können Personen den Schlüssel "0" (Null) verwenden, um ein Leerzeichen zwischen dem Vornamen und dem Nach- oder Nachnamen und dem Vornamen anzugeben. Wenn sie den Namen eingeben, werden sie aufgefordert, ihren Tastatureintrag mit der #-Taste zu beenden. Beispiel: "Nachdem Sie den Namen der Person eingegeben haben, die Sie erreichen möchten, drücken Sie #." Wenn mehrere Namen gefunden werden, erhält der Anrufer eine Liste der Namen, aus denen sie auswählen können.

> [!NOTE]
> Wenn nach der Anwendung von Ein- oder Ausschlusslisten für den Wählbereich mehr als 5 Namen verbleiben, schlägt die Suche fehl, und dem Anrufer wird mitgeteilt, dass zu viele Namen gefunden wurden.
  
Anrufer können bei der Suche nach Namen in Ihrer Organisation über die Wähltastatur eines Telefons die folgenden Suchformate verwenden:
  
|Namensformat|Suchtyp|Beispiel|Suchergebnis|
|:-----|:-----|:-----|:-----|
|Vorname + Nachname |Vollständig  |Amos0Marble# |Amos Marble |
|Nachname + Vorname |Vollständig |Marble0Amos#  |Amos Marble |
|Firstname  |Vollständig   |Amos#   |Drücken Sie „1" für Amos Marble.  <br/> Drücken Sie „2" für Amos Marcus. |
|Lastname |Vollständig |Marble#  |Drücken Sie „1" für Amos Marble.  <br/> Drücken Sie „2" für Mary Marble. |
|Vorname oder Nachname |Teilweise |Mar# |Drücken Sie „1" für Mary Marble.  <br/> Drücken Sie „2" für Mary Jones.  <br/> Drücken Sie „3" für Amos Marcus. |
|Vorname + Nachname |Teilweise |Amos0Mar # |Drücken Sie „1" für Amos Marble.  <br/> Drücken Sie „2" für Amos Marcus. |
|Nachname + Vorname |Teilweise |Mar0Am# |Drücken Sie „1" für Amos Marble.  <br/> Drücken Sie „2" für Amos Marcus. |

Bei der Suche nach Personen über die Wähltastatur eines Telefons können verschiedene Sonderzeichen verwendet werden. Beispielsweise wird die Person aufgefordert, die Rautetaste (#) zu verwenden, während die Nulltaste (0) für ein Leerzeichen zwischen Namen verwendet wird. Wenn die Anrufer die Sterntaste (*) drücken, wird die Liste der übereinstimmenden Namen wiederholt.
  
|Sonderzeichen auf der Wähltastatur eines Telefons|Bedeutung|
|:-----|:-----|
|#   |Endzeichen bei der Eingabe eines Namens |
|0   |Leerschritt zwischen Namen |
|*    |Wiederholt die Liste der übereinstimmenden Namen. |

### <a name="dial-by-name---name-recognition-with-speech"></a>Namensanwahl - Namenserkennung mit Sprache

Personen können mit ihrer Stimme (Spracherkennung) nach anderen Personen in ihrer Organisation suchen. Sie können auch jede Person in Active Directory erreichen, indem sie den vollständigen oder teilweisen Namen der Person sagen, die sie suchen möchten. Mit spracheingaben können Namen in verschiedenen Formaten erkannt werden, einschließlich Vorname, Nachname, Vorname + Nachname oder Nachname + Vorname.
  
Sie können die Spracherkennung für eine automatische Telefonzentrale aktivieren, die Eingabe über die Wähltastatur des Telefons (DTMF) ist jedoch nicht deaktiviert. Die Eingabe über die Wähltastatur des Telefons kann jederzeit verwendet werden, auch wenn die Spracherkennung in der automatischen Telefonzentrale aktiviert ist.
  
Wie bei der Eingabe auf der Wähltastatur des Telefons hört der Anrufer, wenn mehrere Namen gefunden werden, eine Liste der Namen, aus denen er auswählen kann.

> [!NOTE]
> Wenn nach der Anwendung von Ein- oder Ausschlusslisten für den Wählbereich mehr als 5 Namen verbleiben, schlägt die Suche fehl, und dem Anrufer wird mitgeteilt, dass zu viele Namen gefunden wurden.
  
Aufrufer können Namen in den folgenden Formaten sagen:
  
|Name mit Sprache|Suchtyp|Beispiel|Suchergebnis|
|:-----|:-----|:-----|:-----|
|Vorname + Nachname |Vollständig |Amos Marble |Amos Marble |
|Nachname + Vorname |Vollständig  |Marble Amos |Amos Marble |
|Firstname |Vollständig |Amos |Drücken oder sagen Sie „1" für Amos Marble.  <br/> Drücken oder sagen Sie „2" für Amos Jones. |
|Lastname |Vollständig |Marble |Drücken oder sagen Sie „1" für Amos Marble.  <br/> Drücken oder sagen Sie „2" für Ben Marble. |
|Vorname oder Nachname |Teilweise |Mrz |Drücken oder sagen Sie 1 für Mary Marble  <br/> Drücken oder sagen Sie 2 für Mary Jones  <br/> Drücken oder sagen Sie 3 für Amos Marcus |
|Vorname + Nachname |Teilweise |Amos Mar |Drücken oder sagen Sie „1" für Amos Marble.  <br/> Drücken oder sagen Sie 2 für Amos Marcus |

> [!NOTE]
> Es kann bis zu 36 Stunden dauern, bis ein neuer Benutzer aufgrund einer Verzögerung bei der Active Directory-Replikation den Namen im Verzeichnis für "Namenswahl mit Spracherkennung" aufgelistet hat.

### <a name="dial-by-extension"></a>Durchwahl

Benutzer, die Sie für **die Durchwahl** zur Verfügung stellen möchten, benötigen eine Erweiterung, die als Teil eines der folgenden Telefonattribute in Active Directory (und über Azure AD Connect synchronisiert) oder Azure Active Directory definiert ist. (Weitere Informationen finden [Sie unter "Benutzer einzeln hinzufügen" oder "Massenhinzufügen](/microsoft-365/admin/add-users/add-users) ".)

- TelephoneNumber (AD und Azure AD)
- HomePhone (AD)
- Mobile (AD und Azure AD)
- OtherTelephone (AD)

Das erforderliche Format zum Eingeben der Erweiterung in das Feld "Benutzertelefonnummer" kann eines der folgenden Formate sein:

- *+\<phone number>;ext=\<extension>*
- *+\<phone number>X\<extension>*
- *X\<extension>*

- Beispiel 1: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678;ext=5678"
- Beispiel 2: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "+15555555678x5678"
- Beispiel 3: Set-MsolUser -UserPrincipalName usern@domain.com -Phonenumber "x5678"

Sie können die Erweiterung im [Microsoft 365 Admin Center](https://admin.microsoft.com/) oder im [Azure Active Directory Admin Center](https://aad.portal.azure.com) festlegen. Es kann bis zu 12 Stunden dauern, bis Änderungen für automatische Telefonzentralen und Anrufwarteschleifen verfügbar sind.

> [!NOTE]
>  Wenn Sie das Feld "TelephoneNumber" zum Definieren der Erweiterung verwenden, empfiehlt Microsoft, das Format *+\<phone number>";ext=\<extension>*" zu verwenden. Wenn dem Benutzer auch eine Microsoft Teams-Telefonnummer zugewiesen ist, sollten Sie beide Nummern auf die gleiche Weise definieren.


## <a name="language-support"></a>Sprachunterstützung

Sprachunterstützung für Text-zu-Sprache und Spracherkennung ist in diesen [unterstützten Sprachen](create-a-phone-system-auto-attendant-languages.md) verfügbar.

Die folgenden Sprachbefehle sind für die Spracherkennung verfügbar:
  
|Sprachbefehl| Entspricht |
|:-----|:-----|
|Ja | Drücken Sie "1" für "Ja". |
|Nein | Drücken Sie 2 für "Nein". |
|Wiederholen |Wiederholt die Liste der Optionen. Drücken Sie * auf der Tastatur, um die Liste der Optionen zu wiederholen. |
|Anbieter | Drücken Sie 0 für "Operator" |
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
