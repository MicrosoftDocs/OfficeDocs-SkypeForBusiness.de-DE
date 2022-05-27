---
title: Einrichten von Cloudvoicemail
author: CarolynRowe
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
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Erfahren Sie, wie Sie Cloud-Voicemail für Ihre Benutzer einrichten.
ms.openlocfilehash: 6a75856954da509677a1c9ccdb54e34055f171ed
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681406"
---
# <a name="set-up-cloud-voicemail"></a>Einrichten von Cloudvoicemail

Dieser Artikel richtet sich an Microsoft 365 Administratoren, die Cloud-Voicemail für ihre Benutzer einrichten möchten.

Cloud-Voicemail hintergibt Voicemailnachrichten im Exchange Postfach eines Benutzers. Cloud-Voicemail unterstützt keine E-Mail-Systeme von Drittanbietern. Informationen zu Exchange Online Lizenzierungsanforderungen finden Sie [unter Exchange Online Dienstbeschreibung](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description#features-available-to-all-plans). Weitere Informationen zu Administratorrollen finden Sie unter ["Informationen zu Administratorrollen"](/microsoft-365/admin/add-users/about-admin-roles).

## <a name="cloud-voicemail-provisioning"></a>Cloud-Voicemail Bereitstellung

Für Teams Benutzer wird Cloud-Voicemail automatisch eingerichtet und bereitgestellt. *Für Cloud-Voicemail ist keine Microsoft Teams Telefon Lizenz erforderlich.*

Die Bereitstellung für Teams Benutzer ist nicht identisch mit Skype for Business Onlinebenutzern. Für Skype for Business Online-Benutzer wurde Cloud-Voicemail automatisch eingerichtet und bereitgestellt, wenn den Benutzern eine Telefonsystem-Lizenz zugewiesen und vom Bereitstellungssystem aktiviert Enterprise-VoIP wurde.

Für Skype for Business Server lokalen Benutzer wird Cloud-Voicemail automatisch eingerichtet und bereitgestellt. Sie müssen jedoch die Skype for Business Server Umgebung so konfigurieren, dass Anrufe an Cloud-Voicemail weitergeleitet werden. Weitere Informationen finden Sie unter [Plan Cloud-Voicemail Service für lokale Benutzer](/skypeforbusiness/hybrid/plan-cloud-voicemail).

## <a name="cloud-voicemail-storage"></a>Cloud-Voicemail Speicher

Von Cloud-Voicemail generierte Voicemailnachrichten werden entweder in Exchange Online oder in Exchange Server an das Exchange Postfach des Benutzers übermittelt und gespeichert. Es gibt keinen spezifischen oder zusätzlichen Speicher für Voicemail. Die Clients, die auf Voicemail zugreifen (z. B. Microsoft Outlook, Microsoft Teams oder Skype for Business), tun dies über das Exchange Postfach und die bereitgestellten APIs.

Eine Voicemailnachricht enthält eine angefügte Audiodatei mit den Sprachnachrichten und der Voicemailtranskription (sofern aktiviert).

Das Exchange Postfach eines Benutzers speichert alle benutzerdefinierten aufgezeichneten Begrüßungen. Diese Begrüßungen werden von Cloud-Voicemail bei Bedarf während eines eingehenden Anrufs abgerufen.

## <a name="cloud-voicemail-processing"></a>Cloud-Voicemail Verarbeitung

Die Aufzeichnung und Transkription von Cloud-Voicemail beginnt in Microsoft 365 am Ursprung des Anrufs, der an Cloud-Voicemail weitergeleitet wird. Die Nachricht wird dann an das Exchange Postfach des Benutzers übermittelt.

Wenn beispielsweise ein Anruf an einen nicht verfügbaren Direct Routing-Benutzer über einen Session Border Controller (SBC) in Europa eingeht, erfolgt die Voicemailaufzeichnung und -transkription in Europa. Die Nachricht wird dann an das Exchange Postfach des Benutzers übermittelt. Angenommen, ein Teams Benutzer in Nordamerika ruft einen nicht verfügbaren Teams Benutzer in Europa auf. In diesem Fall beginnt der Anruf in Nordamerika, die Verarbeitung erfolgt in Nordamerika und dann wird die Voicemail an das Exchange Postfach des Benutzers in Europa übermittelt.

Die Übermittlung einer Voicemail an ein Exchange Postfach erfolgt wie jede andere E-Mail mithilfe des Simple Mail Transport Protocol (SMTP).

## <a name="manage-cloud-voicemail-for-users"></a>Verwalten von Cloud-Voicemail für Benutzer

Verwenden Sie das Teams PowerShell-Modul wie folgt, um Cloud-Voicemail Features für Ihre Benutzer zu verwalten.

Verwenden Sie zum Verwalten Cloud-Voicemail Features für Benutzergruppen das Cmdlet [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy).
Sie können vorhandene oder neue Voicemailrichtlinien für Features wie Anrufbeantwortungsregeln, Voicemailtranskription, Transkription der Profanitätsmaskierung, Transkriptionsübersetzung und Systemeingabeaufforderungssprache konfigurieren und zuweisen. Weitere Informationen finden Sie unter [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy).

Verwenden Sie zum Verwalten Cloud-Voicemail Einstellungen für einzelne Benutzer das Cmdlet [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings). Cloud-Voicemail Einstellungen, die Sie auf einzelne Benutzer anwenden können, umfassen Anrufbeantwortungsregeln, Eingabeaufforderungssprache, Text-zu-Sprache-Standard und Urlaubsgrüße. Weitere Informationen finden Sie unter [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings).
(Beachten Sie, dass Ihre Endbenutzer diese Einstellungen auch im Teams-Client konfigurieren können, indem sie zu **Einstellungen** ->  **Calls** -> **Configure Voicemail** wechseln.)

Sie können Cloud-Voicemail für einen Benutzer auch deaktivieren, indem Sie das Cmdlet [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) verwenden und den VoicemailEnabled-Parameter auf $false festlegen. Mit dieser Einstellung wird sichergestellt, dass Cloud-Voicemail keine Voicemail mehr für den Benutzer aufzeichnen können.

## <a name="control-routing-of-calls-to-cloud-voicemail"></a>Steuern des Routings von Anrufen an Cloud-Voicemail

Die Standardeinstellung für alle Benutzer, die für Cloud-Voicemail bereitgestellt werden, besteht darin, das Weiterleiten von Anrufen an Cloud-Voicemail zu ermöglichen und Benutzern das Weiterleiten von Anrufen an Cloud-Voicemail zu ermöglichen.

Sie können steuern, ob das Weiterleiten von Anrufen an Cloud-Voicemail für Teams Benutzer zulässig ist, indem Sie das cmdlet Set-CsTeamsCallingPolicy mit dem Parameter AllowVoicemail verwenden. Weitere Informationen finden Sie unter [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

- Wenn Sie AllowVoicemail auf AlwaysDisabled festlegen, werden Anrufe niemals an Voicemail weitergeleitet – unabhängig von den Einstellungen für die Anrufweiterleitung oder nicht beantworteten Einstellungen für einen Benutzer. Voicemail ist in Teams nicht als Anrufweiterleitung oder unbeantwortete Einstellung verfügbar.

- Wenn Sie "AllowVoicemail" auf "AlwaysEnabled" festlegen, werden Anrufe nach dem Klingeln für dreißig Sekunden immer an die Voicemail weitergeleitet – unabhängig von der Einstellung für die Unbeantwortete Anrufweiterleitung für einen Benutzer.

- Wenn Sie AllowVoicemail auf UserOverride festlegen, werden Anrufe basierend auf den Einstellungen für die Anrufweiterleitung und/oder den unbeantworteten Einstellungen für einen Benutzer an die Voicemail weitergeleitet.

## <a name="set-up-cloud-voicemail-to-work-with-on-premises-users"></a>Einrichten Cloud-Voicemail für die Arbeit mit lokalen Benutzern

Sie können Cloud-Voicemail verwenden, um Voicemailfunktionen für Benutzer bereitzustellen, die über Postfächer auf Ihren Exchange-Servern verfügen, oder für Benutzer, die Skype for Business Server verwenden.

In diesem Abschnitt wird beschrieben, wie Sie Cloud-Voicemail für Exchange Server Postfachbenutzer einrichten. Informationen zum Konfigurieren von Cloud-Voicemail für Skype for Business Server Benutzer finden Sie unter [Plan Cloud-Voicemail service for on-premises users](/skypeforbusiness/hybrid/plan-cloud-voicemail).

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Einrichten von Cloud-Voicemail für Exchange Server Postfachbenutzer

Die folgenden Informationen enthalten Informationen zum Konfigurieren von Cloud-Voicemail für die Arbeit mit Teams Benutzern, die ihr Postfach auf Exchange Server haben.

1. Voicemailnachrichten werden über SMTP, das über Exchange Online Protection weitergeleitet wird, an das Exchange Postfach eines Benutzers übermittelt. Um die erfolgreiche Übermittlung dieser Nachrichten zu ermöglichen, stellen Sie sicher, dass Exchange Connectors zwischen Ihren Exchange Servern und Exchange Online Protection ordnungsgemäß konfiguriert sind. Weitere Informationen finden Sie unter [Verwenden von Connectors zum Konfigurieren von E-Mail-Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

2. Um Voicemail-Features wie das Anpassen von Begrüßungen und visuelle Voicemail in Teams Clients zu aktivieren, müssen Sie die Konnektivität zwischen Microsoft 365 und dem Exchange Server Postfach einrichten. Um diese Konnektivität zu aktivieren, müssen Sie das neue Exchange Oauth-Authentifizierungsprotokoll konfigurieren, das unter [Konfigurieren der OAuth-Authentifizierung zwischen Exchange und Exchange Online Organisationen](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help) beschrieben ist, oder den Exchange Hybrid-Assistenten ab Exchange 2013 CU5 oder höher ausführen. Sie müssen auch die Integration und OAuth zwischen Teams und Exchange Server konfigurieren, die unter ["Integration konfigurieren" und "OAuth zwischen Teams und Exchange Server" beschrieben sind](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).

## <a name="enable-protected-voicemail-in-your-organization"></a>Aktivieren geschützter Voicemails in Ihrer Organisation

Wenn jemand eine Voicemailnachricht für einen Benutzer in Ihrer Organisation hinterlässt, wird die Voicemail als E-Mail-Nachrichtenanlage an das Postfach des Benutzers übermittelt.

Mit Microsoft Purview Information Protection können Sie die Voicemailnachrichten verschlüsseln, die sowohl von internen als auch von externen Anrufern hinterlassen werden. Sie können auch verhindern, dass der Benutzer diese Nachrichten weiterleitet. Dieses Feature wird für Benutzer mit Exchange Online Postfächern unterstützt.

Zum Verschlüsseln der Voicemailnachricht können Sie eine Vertraulichkeitsbezeichnung erstellen. Mit der Funktion für die automatische Bezeichnung können Sie sicherstellen, dass die Bezeichnung automatisch auf eingehende Voicemailnachrichten angewendet wird.

Wenn Sie geschützte Voicemail aktivieren, können Benutzer geschützte Voicemailnachrichten anhören, indem sie sich in ihr Voicemailpostfach einrufen oder die Nachricht in Outlook, Outlook im Web oder Outlook für Android oder iOS öffnen. Geschützte Voicemailnachrichten können nicht in Microsoft Teams oder Skype for Business geöffnet werden.

Informationen zum Erstellen einer Vertraulichkeitsbezeichnung für Voicemail finden [Sie unter Verwenden von Vertraulichkeitsbezeichnungen](/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions). Wählen Sie im Abschnitt **"Verschlüsselung** " die Option " **Benutzern das Zuweisen von Berechtigungen gestatten" aus, wenn sie die Bezeichnung anwenden**. Wählen Sie **"In Outlook" aus, erzwingen Sie eine der folgenden Einschränkungen**, und wählen Sie dann die Option **"Nicht weiterleiten**" aus.

Informationen zum Erstellen der Richtlinie für die automatische Bezeichnung zum Anwenden einer Vertraulichkeitsbezeichnung auf Voicemail finden Sie unter [Konfigurieren von Richtlinien für automatische Bezeichnungen](/microsoft-365/compliance/apply-sensitivity-label-automatically#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) und Angeben der folgenden spezifischen Einstellungen:

- **Wählen Sie für "Informationen auswählen", auf die diese Bezeichnung angewendet werden soll**, **die Option "Benutzerdefinierte Richtlinie" aus**.

- **Wählen Sie für "Speicherorte auswählen", auf die Sie die Bezeichnung anwenden möchten**, "**Speicherorte: Exchange für alle Benutzer**" aus.

- Wählen  **Sie für "Allgemeine oder erweiterte Regeln einrichten**" die Option **"Erweiterte Regeln**" aus.

- Exchange Regeln:
  - Bedingungen:
    - **Headerübereinstimmungsmuster**: Content-Class = Voice-CA
    - **Ip-Adresse des Absenders:** 13.107.64.0/18, 52.112.0.0/14, 52.120.0.0/14, 52.238.119.141/32, 52.244.160.207/32

- **Wenn Sie eine Bezeichnung für die automatische Anwendung auswählen möchten**, wählen Sie die Vertraulichkeitsbezeichnung aus, die Sie im obigen Schritt für Voicemail erstellt haben.

- Wenn **Sie weitere Einstellungen für E-Mails** anzeigen möchten, wählen Sie "**Verschlüsselung auf E-Mails anwenden" aus, die von außerhalb Ihrer Organisation empfangen wurden**, und geben Sie den Rights Management Besitzer an.

Die in der Absender-IP-Adresse angegebenen IP V4-Bereiche basieren auf der Liste in ID 12 in [Office 365 URLs und IP-Adressbereichen](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).

Weitere Informationen zur Nachrichtenverschlüsselung finden [Sie unter Definieren von Nachrichtenflussregeln zum Verschlüsseln von E-Mail-Nachrichten](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).

## <a name="help-your-users-learn-about-cloud-voicemail-features"></a>Helfen Sie Ihren Benutzern, mehr über Cloud-Voicemail-Features zu erfahren

Um Ihren Benutzern zu helfen, mehr über die Verwendung und Verwaltung Cloud-Voicemail Features zu erfahren, können Sie die folgenden Artikel empfehlen:

- [Überprüfen Sie Ihre Voicemail in Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [Verwalten Der Anrufeinstellungen in Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)
