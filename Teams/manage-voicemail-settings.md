---
title: Verwalten Cloud-Voicemail Einstellungen
author: crowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
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
- Phone System
description: Verwalten Von Voicemail-Einstellungen für Ihre Benutzer.
ms.openlocfilehash: 7aa2fdf84f38cb9977b3a4156b28a96b98bbd9d7
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269600"
---
# <a name="manage-cloud-voicemail-settings-for-users"></a>Verwalten Cloud-Voicemail Einstellungen für Benutzer

Mit den Voicemaileinstellungen können Sie Voicemaileinstellungen für einzelne Benutzer konfigurieren.

Bevor Sie Voicemaileinstellungen für Ihre Benutzer konfigurieren, sollten Sie "[Einrichten Cloud-Voicemail](set-up-phone-system-voicemail.md)" lesen. Informationen zum Festlegen von Richtlinien für Benutzergruppen finden [Sie unter Verwalten von Voicemailrichtlinien](manage-voicemail-policies.md).

Die Standardeinstellungen für Cloud-Voicemail lauten:

- Voicemail ist aktiviert.
- Die Eingabeaufforderungssprache wird auf die bevorzugte Sprache des Benutzers festgelegt.
- Die Abwesenheitsbegrüßung ist deaktiviert.
- Die Abwesenheitsbegrüßung ist deaktiviert, wenn automatische Antworten in Outlook festgelegt werden.
- Die Abwesenheitsbegrüßung, wenn der Kalender in Outlook außer Haus angezeigt wird, ist deaktiviert.
- Die Freigabe von Voicemail- und Transkriptionsdaten für den Dienst für Schulungs- und Verbesserungszwecke ist deaktiviert.
- Die Anrufbeantwortungsregel ist auf reguläre Voicemail festgelegt.
- Die Standardmäßige Begrüßungsaufforderung wird nicht überschrieben.
- Die standardmäßige Überschreibung der Abwesenheitsbegrüßungsaufforderung ist nicht festgelegt.
- Das Übertragungsziel ist nicht festgelegt.


Um Cloud-Voicemail Features für Ihre Benutzer zu verwalten, können Sie das Teams Admin Center oder PowerShell verwenden. Beachten Sie, dass Ihre Endbenutzer diese Einstellungen auch im Teams-Client konfigurieren können, indem sie zu **Einstellungen -> Anrufe -> Voicemail konfigurieren wechseln.**

## <a name="use-teams-admin-center"></a>Verwenden des Teams Admin Centers

Im Teams Admin Center:

1.  Navigieren Sie im linken Navigationsbereich zu **"Benutzer > Benutzer verwalten** ", und wählen Sie den Benutzer aus.

2.  Wechseln Sie auf der Seite "Benutzerdetails" zur Registerkarte " **Voicemail** ".

3.  Ändern Sie die Einstellungen.

4.  Klicken Sie auf **Speichern**.


## <a name="use-powershell"></a>Verwenden von PowerShell

Sie können PowerShell auch verwenden, um Voicemaileinstellungen wie folgt zu verwalten:

- Verwenden Sie zum Verwalten Cloud-Voicemail Einstellungen für einzelne Benutzer das Cmdlet [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings). 

- Verwenden Sie zum Anzeigen von Einstellungen das Cmdlet ["Get-CsOnlineVoicemailUserSettings](/powershell/module/skype/get-csonlinevoicemailusersettings) ".

- Sie können Cloud-Voicemail für einen Benutzer deaktivieren, indem Sie das Cmdlet [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) verwenden und den VoicemailEnabled-Parameter auf $false festlegen. 

## <a name="voicemail-settings"></a>Voicemaileinstellungen

- **Voicemail aktiviert** – Diese Einstellung steuert, ob Cloud-Voicemail für den Benutzer aktiviert ist. Wenn die Einstellungen falsch sind, steht Cloud-Voicemail Dienst für den Benutzer nicht zur Verfügung und zeichnet keine Voicemail für den Benutzer auf.

- **Eingabeaufforderungssprache** – Diese Einstellung gibt die Sprache an, die für die Eingabeaufforderungen im Cloud-Voicemail verwendet wird. Weitere Informationen finden [Sie unter Ändern der Standardsprache für Begrüßungen und E-Mails](change-the-default-language-for-greetings-and-emails.md).

- **Begrüßungseinstellungen** – Cloud-Voicemail kann eine bestimmte Begrüßung für den Zeitpunkt, an dem sich der Benutzer im Büro befindet, und für den Zeitpunkt, an dem der Benutzer außer Haus ist, wiedergeben. Beide Begrüßungen können vom Benutzer aufgezeichnet oder eine Text-zu-Sprache-Begrüßung verwendet werden.

  - **Standardbegrüßungsaufforderung überschreiben** – gibt die Text-zu-Sprache-Begrüßung an, die wiedergegeben wird, falls der Benutzer keine Begrüßung aufgezeichnet hat.

  - **Oof Greeting Enabled** – Gibt an, ob die Abwesenheitsbegrüßung im Voicemail-Einzahlungsszenario wiedergegeben wird, unabhängig von den Outlook-Einstellungen.

  - **Oof Greeting Follow Automatic Replies Enabled** – Gibt an, ob die Abwesenheitsbegrüßung im Voicemail-Einzahlungsszenario wiedergegeben werden soll, wenn der Benutzer automatische Antworten in Outlook festlegt.

  - **Oof Greeting Follow Calendar Enabled** – Gibt an, ob die Abwesenheitsbegrüßung im Voicemail-Einzahlungsszenario wiedergegeben werden soll, wenn der Benutzer die Abwesenheit im Kalender festlegt.

  - **Standardüberschreiben der Abwesenheitsansage** – Gibt die Text-zu-Sprache-Begrüßung an, die wiedergegeben wird, wenn der Benutzer außer Haus ist und keine Abwesenheitsbegrüßung aufgezeichnet hat.

- **Anrufbeantwortungsregel** – Diese Einstellung gibt die Anrufbeantwortungsregel an. Die Regel kann sein:
  - Der Dienst lehnt den Anruf ohne Nachricht ab.
  - Es wird nur die entsprechende Begrüßung (normal oder außer Haus) wiedergegeben.
  - Die relevante Begrüßung (normal oder außer Haus) wird wiedergegeben, und der Anrufer wird an den angegebenen Benutzer oder die angegebene Telefonnummer weitergeleitet.
  -  Die entsprechende Begrüßung (normal oder außer Haus) wird wiedergegeben, und der Anrufer kann eine Voicemail verlassen.
  - Die relevante Begrüßung (normal oder außer Haus) wird wiedergegeben, der Anrufer kann eine Voicemail verlassen und darf 0 drücken, um an den angegebenen Benutzer oder die angegebene Telefonnummer weitergeleitet zu werden.

- **Freigeben von Daten für Dienstverbesserungen** – Gibt an, ob Voicemail- und Transkriptionsdaten für den Dienst zur Schulung und Verbesserung der Genauigkeit freigegeben werden. Bei Festlegung auf "false" werden Voicemaildaten unabhängig von der Benutzerauswahl nicht freigegeben.

- **Anrufdurchstellung** – Gibt den Benutzer oder die Telefonnummer an, zu der der Anrufer weitergeleitet wird.


