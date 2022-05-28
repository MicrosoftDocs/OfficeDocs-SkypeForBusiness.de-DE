---
title: Mandantenverwaltungssteuerelement für die Spracherkennung (Sprachprofil) in Teams-Räume
author: dstrome
ms.author: dstrome
ms.reviewer: parisataheri
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie mehr über die Mandantenverwaltungssteuerung für die Spracherkennung (Sprachprofil) in Teams Besprechungsräumen.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3d5caa402be0ea282d70bfe17cc9d2d728e6ec2c
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2022
ms.locfileid: "65760927"
---
# <a name="manage-voice-recognition-technology-controls-for-an-intelligent-speaker"></a>Verwalten von Steuerelementen für die Spracherkennungstechnologie für einen intelligenten Lautsprecher

Ein intelligenter Lautsprecher verwendet Sprachprofilinformationen, um zu erkennen, wer was in der Livetranskription gesagt hat. Wenn ein Microsoft Teams-Räume für Windows Besprechungsraum mit einem intelligenten Lautsprecher ausgestattet ist, kann die Livetranskription während der Besprechung verwendet werden. In diesem Artikel wird erläutert, wie Sie als Mandantenadministrator die Sprachprofilerstellung steuern, die für die Spracherkennung zum Generieren von Livetranskription verwendet wird. Sie können steuern, in welchem Umfang die Organisation Spracherkennung und die folgenden Features verwendet:

- Bearbeiten Sie den Namen des Sprechers in Transkriptionen.
- Ändern Sie den Sprecher einer einzelnen Äußerung in der Transkription, oder ändern Sie den Sprecher in allen Äußerungen im Transkript (jedoch nicht in zukünftigen Transkriptionen).
- Ändern Sie die Sprecheridentifikation für die Personen, die in der Besprechung aufgeführt sind.
- Entfernen Sie die Identifizierung einer oder mehrerer Äußerungen, die als dieser Sprecher identifiziert wurden, in jedem Transkript.

## <a name="review-intelligent-speaker-requirements"></a>Überprüfen der Anforderungen für intelligente Lautsprecher

Ein intelligenter Lautsprecher enthält ein spezielles Sieben-Mikrofon-Array. Das System verwendet Sprachprofilinformationen, um Stimmen von bis zu 10 Personen in Besprechungsräumen zu identifizieren.

Die folgenden Elemente sind Anforderungen an intelligente Lautsprecher:

- Im Besprechungsraum sollten maximal 10 Personen persönlich anwesend sein.
- Der Besprechungsraum verfügt über einen Uploadlink von mindestens 7 MBit/s.

Epos, Sennheiser und yealink intelligente Lautsprecher werden unterstützt.

> [!NOTE]
> Intelligent Speaker ist in allen Ländern und Regionen verfügbar. Eine Liste der Gebietsschemas, die derzeit für biometrische Registrierung und Transkription in Besprechungen unterstützt werden, finden Sie unter ["Unterstützte Gebietsschemas](#supported-locales) ".

## <a name="set-up-an-intelligent-speaker"></a>Einrichten eines intelligenten Lautsprechers

Ein intelligenter Lautsprecher verbindet sich direkt über USB mit der Teams-Räume Konsole.

> [!NOTE]
> Ein intelligenter Yealink-Lautsprecher **muss** mit einer Yealink-Konsole verwendet werden.

> [!NOTE]
> Wir unterstützen keinen intelligenten Lautsprecher, der mit Logitech Surface Pro Microsoft Teams-Räume verbunden ist. Es gibt ein bekanntes Problem, dass Teams-Räume den intelligenten Lautsprecher nicht über das Dock erkennen können.

Ein intelligenter Lautsprecher sollte mindestens 8 Zoll (20 cm) von Wänden und großen Objekten wie Laptops entfernt platziert werden. Wenn das USB-Kabel des intelligenten Lautsprechers nicht lang genug für Ihre Einrichtung ist, verwenden Sie Kabelverweiter.

1. Melden Sie sich als Administrator bei der Konsole an.
2. Legen Sie die Teams Geräteeinstellungen so fest, dass sie dem Mikrofon und Lautsprecher des intelligenten Lautsprechers entsprechen.
   Sie können dies auch über das TAC-Portal statt über die Raumkonsole tun.

   Das Diagramm zeigt, wie der intelligente Lautsprecher mit dem Gerät verbunden ist, wenn das Gerät ein Datenfeld enthält.

   ![Das Setup des intelligenten Lautsprechers mit Lautsprecher, Leistung und Datenfeld. Eine Zeile wird an den USB-Anschluss der Konsole und die andere an die Stromversorgung angeschlossen.](../media/intelligent-speakers1.png)

   Das Diagramm zeigt, wie der intelligente Lautsprecher mit dem Gerät verbunden ist, wenn das Gerät kein Datenfeld enthält.

   ![Das Setup des intelligenten Lautsprechers mit dem Lautsprecher, der direkt mit der Konsole verbunden ist.](../media/intelligent-speakers2.png)

> [!Note]
> EPOS- und Yealink-Geräte sollten das Präfix "EPOS" oder "Yealink" aufweisen und "UAC2_RENDER" im Lautsprechernamen und "UAC2_TEAMS" im Mikrofonnamen enthalten. Wenn Sie diese Mikrofon- und Lautsprechernamen nicht im Dropdownmenü finden, starten Sie das Intelligent Speaker-Gerät neu.

## <a name="enable-an-intelligent-speaker-user-recognition"></a>Aktivieren einer Benutzererkennung für intelligente Lautsprecher

Sprachprofildaten können in jeder Besprechung mit einem intelligenten Lautsprecher verwendet werden. Informationen zu den Besprechungseinstellungen finden Sie [unter Teams Besprechungsrichtlinien](../meetings-policies-recording-and-transcription.md#allow-transcription) und den [PowerShell-Besprechungs-Cmdlets](/powershell/module/skype/set-csteamsmeetingpolicy).

Die VoIP-Profildaten des Benutzers werden erstellt, wenn die Richtlinie so festgelegt ist, dass sie unterscheidet oder während der Besprechung ein eingeladener Teilnehmer, der keine Besprechung ist, eingeht. Die VoIP-Profildaten werden am Ende der Besprechung geschlossen.

Im Folgenden sind die erforderlichen Richtlinien zum Festlegen eines intelligenten Lautsprechers und einer Benutzererkennung angegeben.

|Richtlinie|Beschreibung|Werte und Verhalten|
|-|-|-|
|enrollUserOverride|Hiermit legen Sie die Sprachprofilerfassung oder -registrierung in Teams Einstellungen für einen Mandanten fest. |**Deaktiviert**<br><ul><li> Benutzer, die sich noch nie registriert haben, können sich nicht anzeigen, registrieren oder erneut registrieren.<li>Der Einstiegspunkt zum Registrierungsfluss wird ausgeblendet.<li>Wenn Benutzer einen Link zur Registrierungsseite auswählen, wird eine Meldung angezeigt, die besagt, dass dieses Feature für ihre Organisation nicht aktiviert ist.  <li>Benutzer, die sich registriert haben, können ihr VoIP-Profil in den Teams-Einstellungen anzeigen und entfernen. Nachdem sie ihr VoIP-Profil entfernt haben, können sie den Registrierungsfluss nicht mehr anzeigen, darauf zugreifen oder abschließen.</li></ul><br>**Aktiviert**<br><ul><li> Benutzer können den Registrierungsfluss anzeigen, darauf zugreifen und abschließen.<li>Der Einstiegspunkt wird auf Teams Einstellungsseite unter der Registerkarte "**Erkennung**" angezeigt.</li></ul>|
|roomAttributeUserOverride|Steuern der sprachbasierten Benutzeridentifikation in Besprechungsräumen. Diese Einstellung ist für Teams-Räume Konten erforderlich.| **Aus**<br><ul><li>Das Teams-Räume Gerät sendet keine bandbreitensparende Audiodatenströme aus dem Raum. <li>Benutzer von Besprechungsräumen werden weder zugeordnet noch unterschieden, und ihre Sprachsignaturen werden weder abgerufen noch verwendet.<li>Besprechungsraumbenutzer sind unbekannt.</li></ul> <br>**Attribut**<br><ul><li>Chatroombenutzer werden basierend auf ihrem Registrierungsstatus zugeordnet.<li>Benutzer, die registriert sind, werden in der Transkription mit ihrem Namen angezeigt.  <li>Benutzer, die nicht registriert sind, werden als Sprecher \<n>angezeigt.<li>Das Teams-Räume Gerät sendet sieben Audiostreams aus dem Raum.</ul> <br>**Unterscheiden**<br> <ul><li>Die Benutzer von Räumen werden als Lautsprecher 1, Lautsprecher 2, .... Sprecher \<n> in der Transkription.</li><li>Unabhängig vom Registrierungsstatus des Benutzers wird sein Name in der Transkription nicht angezeigt.</li><li>Das Teams-Räume Gerät sendet sieben Audiostreams aus dem Raum.</li></ul>
|AllowTranscription|Erforderlich für Benutzer- und Teams-Räume-Konten.|**Wahr** und **Falsch**|
||||

Legen Sie im Teams Admin Center die **Transkriptionsrichtlinie** fest. Einstellungen sind standardmäßig **deaktiviert**.

![das Admin Center mit hervorgehobenen Besprechungsrichtlinien und ausgewählter Option "Transkription zulassen".](../media/allow-transcription1.png)
  
> [!NOTE]
> Nachdem eine Richtlinie zugewiesen wurde, kann es bis zu 48 Stunden dauern, bis sie wirksam wird. Damit die Richtlinie früher wirksam wird, müssen Konten abgemeldet und wieder angemeldet werden.

## <a name="frequently-asked-questions-faq"></a>Häufig gestellte Fragen (FAQ)

**Wo werden die VoIP-Profildaten gespeichert?**

VoIP-Profildaten werden in Office 365 Cloud mit Benutzerinhalten gespeichert.

**Was ist die Aufbewahrungszeitachse und -richtlinie?**

Die allgemeine Aufbewahrungsrichtlinie wird in der [Übersicht über die Datenaufbewahrung](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview) angegeben. Darüber hinaus werden die VoIP-Profildaten eines Benutzers nach 1 Jahr gelöscht, wenn der Benutzer innerhalb dieses 1-Jahres-Zeitraums nicht zu Besprechungen mit einem intelligenten Sprecher eingeladen wird. Daten werden in Besprechungen für vorhandene Mitarbeiter nicht verwendet. Wenn ein Mitarbeiter das Unternehmen verlassen hat, werden VoIP-Profildaten als Benutzerinhalte betrachtet und gemäß Office 365 in der [Datenaufbewahrungsübersicht beschriebenen Datenaufbewahrungsrichtlinie](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview) behandelt.

**Werden Sprachprofildaten Microsoft-Dienste verwendet?**

Nein, VoIP-Profildaten werden nur für den Zweck verwendet, für den der Benutzer seine Zustimmung erteilt hat. Microsoft verwendet die Sprachprofildaten nur in Teams Spracherkennungsszenarien.

Beispielsweise verwendet Microsoft die Daten in den folgenden Situationen nicht:

**Werden meine VoIP-Profildaten verwendet, wenn ich an einer Besprechung in einer anderen Organisation teilniere?**

Nicht nur in Besprechungen, die von einem Benutzer in Ihrer Organisation organisiert wurden.

**Wie kann ich mein Sprachprofil exportieren?**

Ihr IT-Administrator kann Ihre Audiodaten jederzeit exportieren.

## <a name="supported-locales"></a>Unterstützte Gebietsschemas

Die folgenden Registrierungs- und In-Meeting-Transkriptionsgebietsschemas werden in allen Ländern und Regionen unterstützt.

### <a name="enrollment-locales"></a>Gebietsschemas für die Registrierung

Endbenutzer können ihre Stimmen für die Erkennung in den folgenden Gebietsschemas registrieren:

|**Sprache**|**Land/Region**|**Kultur-ID**|
|:-----|:-----|:-----|
|Englisch  <br/> |Australien <br/> |en-AU  <br/> |
|Englisch  <br/> |Kanada  <br/> |en-CA <br/> |
|Englisch  <br/> |Indien  <br/> |en-IN  <br/> |
|Englisch  <br/> |Neuseeland  <br/> |en-NZ  <br/> |
|Englisch  <br/> |Vereinigtes Königreich  <br/> |en-GB  <br/> |
|Englisch  <br/> |Vereinigte Staaten  <br/> |en-US  <br/> |


### <a name="in-meeting-transcription-locales"></a>Transkriptionsgebietsschemas in Besprechungen

Nachdem sich ein Endbenutzer registriert hat, kann seine Stimme während Besprechungen erkannt und in der Transkription identifiziert werden, wenn die Besprechung auf eines der folgenden Gebietsschemas festgelegt ist:

|**Sprache**|**Land/Region**|**Kultur-ID**|
|:-----|:-----|:-----|
|Chinesisch (vereinfacht)  <br/> |China  <br/> |zh-CN  <br/> |
|Englisch  <br/> |Australien <br/> |en-AU  <br/> |
|Englisch  <br/> |Kanada  <br/> |en-CA <br/> |
|Englisch  <br/> |Indien  <br/> |en-IN  <br/> |
|Englisch  <br/> |Neuseeland  <br/> |en-NZ  <br/> |
|Englisch  <br/> |Vereinigtes Königreich  <br/> |en-GB  <br/> |
|Englisch  <br/> |Vereinigte Staaten  <br/> |en-US  <br/> |
|Französisch  <br/> |Kanada  <br/> |fr-CA  <br/> |
|Französisch  <br/> |Frankreich  <br/> |fr-FR  <br/> |
|Deutsch  <br/> |Deutschland  <br/> |de-DE  <br/> |
|Italienisch  <br/> |Italien  <br/> | it-IT <br/> |
|Japanisch  <br/> |Japan  <br/> |ja-JP  <br/> |
|Koreanisch  <br/> |Korea  <br/> |ko-KR  <br/> |
|Portugiesisch  <br/> |Brasilien  <br/> |pt-BR  <br/> |
|Spanisch  <br/> |Mexiko  <br/> |es-MX  <br/> |
|Spanisch  <br/> |Spanien  <br/> |es-ES  <br/> |

## <a name="related-topics"></a>Verwandte Themen

[Supportartikel: Verwenden intelligenter Lautsprecher zum Identifizieren von Teilnehmern im Raum ](https://support.microsoft.com/office/use-teams-intelligent-speakers-to-identify-in-room-participants-in-meeting-transcription-a075d6c0-30b3-44b9-b218-556a87fadc00)
