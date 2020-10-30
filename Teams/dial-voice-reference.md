---
title: Automatische Telefonzentrale und Anruf Warteschlangen Wähl-und sprach Erkennungs Referenz
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
description: Informieren Sie sich über die Optionen für die automatische Telefonzentrale und die Wähl-und Spracherkennung in Teams.
ms.openlocfilehash: bf520fa4dffe258da523c8815449f1e71279d7f2
ms.sourcegitcommit: bc471f18e40e37456edc9696e11b175581847617
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2020
ms.locfileid: "48800568"
---
# <a name="auto-attendant-and-call-queue-dialing-and-voice-recognition-reference"></a>Automatische Telefonzentrale und Anruf Warteschlangen Wähl-und sprach Erkennungs Referenz

Dial by Name ist eine Funktion einer automatischen Telefonzentrale, die auch als Verzeichnissuche bezeichnet wird. Damit können die Personen, die Ihre automatische Telefonzentrale anrufen, die Spracherkennung (Spracherkennung) oder Ihre DTMF-Antworten (Telefontastatur) verwenden, um einen vollständigen oder teilweisen Namen einzugeben, um das Firmenverzeichnis zu durchsuchen, die Person zu suchen und dann den Anruf an Sie zu übertragen. Sie richten Dial by Name ein, wenn Sie [die Einstellungen für den Anruffluss in einer automatischen Telefonzentrale konfigurieren](create-a-phone-system-auto-attendant.md#call-flow).

## <a name="searching-for-users"></a>Suchen nach Benutzern

Benutzer, die Sie über den Namen "Dial by" gefunden und erreicht haben möchten, müssen **nicht über eine Telefonnummer verfügen oder Ihnen Anrufpläne zugeordnet haben, Sie müssen aber über eine Telefon System Lizenz verfügen, wenn Sie Online-Benutzer sind oder Enterprise-VoIP für Skype for Business Server-Benutzer aktiviert sind** . Durch die Wahl nach Namen können sogar Anrufe an Microsoft Teams-Benutzer, die in verschiedenen Ländern oder Regionen für multinationale Organisationen gehostet werden, gefunden und übertragen werden. Wenn Sie die erforderlichen Voraussetzungen erfüllt haben, aktivieren Sie in einer automatischen Telefonzentrale explizit Dial by Name.

Dial by Extension ist eine Funktion einer automatischen Telefonzentrale, die ebenfalls Teil der Verzeichnissuche ist. Sie ermöglicht es den Personen, die Ihre automatische Telefonzentrale anrufen, die Spracherkennung (Spracherkennung) oder Ihre DTMF-Antworten (Telefontastatur) zu verwenden, um die Durchwahl des Benutzers einzugeben, den Sie erreichen möchten, und dann den Anruf an Sie übertragen zu lassen. Benutzer, die Sie mit Dial by Extension erreichen möchten, müssen  **nicht über eine Telefonnummer verfügen oder Ihnen Anrufpläne zugeordnet haben, Sie müssen aber über eine Telefon System Lizenz verfügen, wenn Sie Online-Benutzer sind oder Enterprise-VoIP für Skype for Business Server-Benutzer aktiviert sind** . Außerdem benötigen Sie einen entsprechend konfigurierten Wählplan für Ihre Benutzer. Dial by Extension kann sogar Anrufe an Microsoft Teams-Nutzer finden und übertragen, die in verschiedenen Ländern oder Regionen für multinationale Organisationen gehostet werden. Wenn Sie die erforderlichen Voraussetzungen erfüllen, aktivieren Sie in einer automatischen Telefonzentrale explizit die Durchwahlnummer.

### <a name="maximum-directory-size"></a>Maximale Verzeichnisgröße

Die Anzahl der Active Directory-Benutzer, die nach Namen wählen, und die Durchwahl können unterstützen, wenn ein Anrufer nach einer bestimmten Person sucht. Ein Anrufer kann Teil-oder vollständige Namen (Vorname + Nachname und auch Nachname + Vorname) eingeben, benötigt aber die vollständige Durchwahlnummer. Die maximale Namen Listengröße, die eine einzelne automatische Telefonzentrale mithilfe der Spracherkennung unterstützenkann, ist 80.000-Benutzer.
  
|Eingabetyp|Suchformat|Maximale Anzahl der Benutzer in einer Organisation|
|:-----|:-----|:-----|
|MFV (Eingabe über die Wähltastatur) |Teilweise  <br/> Vorname + Nachname  <br/> Nachname + Vorname |Keine Beschränkung  |
|Sprache (Spracheingabe) |Vorname  <br/> LastName  <br/> Vorname + Nachname  <br/> Nachname + Vorname  | 80.000-Benutzer |

> [!NOTE]
> Wenn Sie mit der Spracherkennung Dial by Name verwenden, das Active Directory Ihrer Organisation jedoch größer als 80.000-Benutzer ist und Sie den Umfang der Wählfunktion nicht mit der Funktion "Wählbereich" beschränkt haben, funktioniert das Wählen nach Namen weiterhin für Ihre Anrufer über eine Telefontastatur, und Spracheingaben sind für alle anderen Szenarien verfügbar. Sie können das Feature "Wählbereich" verwenden, um die Namen zu verkleinern, die erreichbar sind, indem Sie den Bereich des Wähl namens für eine bestimmte automatische Telefonzentrale ändern.
  
## <a name="dial-by-name---keypad-dtmf-entry"></a>Namensanwahl - Eingabe über die Wähltastatur (MFV)
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
|Vorname + Nachname |Teilweise |Amos0Mar # |Drücken Sie „1" für Amos Marble.  <br/> Drücken Sie „2" für Amos Marcus. |
|Nachname + Vorname |Teilweise |Mar0Am# |Drücken Sie „1" für Amos Marble.  <br/> Drücken Sie „2" für Amos Marcus. |

Bei der Suche nach Personen über die Wähltastatur eines Telefons können verschiedene Sonderzeichen verwendet werden. Die Person wird beispielsweise aufgefordert, die Pound-Taste (#) zu verwenden, während die NULL-Taste (0) für ein Leerzeichen zwischen den Namen verwendet wird. Wenn die Anrufer die Sterntaste (*) drücken, wird die Liste der übereinstimmenden Namen wiederholt.
  
|Sonderzeichen auf der Wähltastatur eines Telefons|Bedeutung|
|:-----|:-----|
|#   |Endzeichen bei der Eingabe eines Namens |
|0   |Leerschritt zwischen Namen |
|*    |Wiederholt die Liste der übereinstimmenden Namen. |

### <a name="dial-by-name---name-recognition-with-speech"></a>Namensanwahl - Namenserkennung mit Sprache

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
  
## <a name="language-support"></a>Sprachunterstützung

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

## <a name="related-topics"></a>Verwandte Themen

[Das Telefonsystem bietet Ihnen Folgendes](here-s-what-you-get-with-phone-system.md)

[Anfordern von Servicenummern für Skype for Business und Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Beispiel für Kleinunternehmen – Einrichten einer automatischen Telefonzentrale](/microsoftteams/tutorial-org-aa)
