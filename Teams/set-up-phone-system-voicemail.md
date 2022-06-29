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
ms.openlocfilehash: 259072194dc474d88a979ac3afb591e72eb51248
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2022
ms.locfileid: "66494372"
---
# <a name="set-up-cloud-voicemail"></a>Einrichten von Cloudvoicemail

Dieser Artikel richtet sich an Microsoft 365-Administratoren, die Cloud-Voicemail für ihre Benutzer einrichten möchten.

Cloud-Voicemail hinterlegt Voicemailnachrichten im Exchange-Postfach eines Benutzers. Cloud-Voicemail unterstützt keine E-Mail-Systeme von Drittanbietern. Informationen zu Exchange Online Lizenzierungsanforderungen finden Sie [unter Exchange Online Dienstbeschreibung](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description#features-available-to-all-plans). Weitere Informationen zu Administratorrollen finden Sie unter ["Informationen zu Administratorrollen"](/microsoft-365/admin/add-users/about-admin-roles).

## <a name="cloud-voicemail-provisioning"></a>Cloud-Voicemail Bereitstellung

Für Teams-Benutzer wird Cloud-Voicemail automatisch eingerichtet und bereitgestellt. *Für Cloud-Voicemail ist keine Microsoft Teams Telefon Lizenz erforderlich.*

Die Bereitstellung für Teams-Benutzer ist nicht identisch mit Skype for Business Onlinebenutzern. Für Skype for Business Onlinebenutzer wurde Cloud-Voicemail automatisch eingerichtet und bereitgestellt, wenn den Benutzern eine Telefonsystemlizenz zugewiesen und vom Bereitstellungssystem Enterprise-VoIP aktiviert wurde.

Für Skype for Business Server lokalen Benutzer wird Cloud-Voicemail automatisch eingerichtet und bereitgestellt. Sie müssen jedoch die Skype for Business Server Umgebung so konfigurieren, dass Anrufe an Cloud-Voicemail weitergeleitet werden. Weitere Informationen finden Sie unter [Plan Cloud-Voicemail Service für lokale Benutzer](/skypeforbusiness/hybrid/plan-cloud-voicemail).

## <a name="cloud-voicemail-storage"></a>Cloud-Voicemail Speicher

Von Cloud-Voicemail generierte Voicemailnachrichten werden entweder in Exchange Online oder in Exchange Server an das Exchange-Postfach des Benutzers übermittelt und gespeichert. Es gibt keinen spezifischen oder zusätzlichen Speicher für Voicemail. Die Clients, die auf Voicemail zugreifen (z. B. Microsoft Outlook, Microsoft Teams oder Skype for Business), tun dies über das Exchange-Postfach und die bereitgestellten APIs.

Eine Voicemailnachricht enthält eine angefügte Audiodatei mit den Sprachnachrichten und der Voicemailtranskription (sofern aktiviert).

Das Exchange-Postfach eines Benutzers speichert alle benutzerdefinierten aufgezeichneten Begrüßungen. Diese Begrüßungen werden von Cloud-Voicemail bei Bedarf während eines eingehenden Anrufs abgerufen.

## <a name="cloud-voicemail-processing"></a>Cloud-Voicemail Verarbeitung

Die Aufzeichnung und Transkription von Cloud-Voicemail beginnt in Microsoft 365 am Ursprung des Anrufs, der an Cloud-Voicemail weitergeleitet wird. Die Nachricht wird dann an das Exchange-Postfach des Benutzers übermittelt.

Wenn beispielsweise ein Anruf an einen nicht verfügbaren Direct Routing-Benutzer über einen Session Border Controller (SBC) in Europa eingeht, erfolgt die Voicemailaufzeichnung und -transkription in Europa. Die Nachricht wird dann an das Exchange-Postfach des Benutzers übermittelt. Angenommen, ein Teams-Benutzer in Nordamerika ruft einen nicht verfügbaren Teams-Benutzer in Europa auf. In diesem Fall beginnt der Anruf in Nordamerika, die Verarbeitung erfolgt in Nordamerika und dann wird die Voicemail an das Exchange-Postfach des Benutzers in Europa übermittelt.

Die Übermittlung einer Voicemail an ein Exchange-Postfach erfolgt wie jede andere E-Mail mithilfe des Simple Mail Transport Protocol (SMTP).

## <a name="manage-cloud-voicemail-for-users"></a>Verwalten von Cloud-Voicemail für Benutzer

Sie können Cloud-Voicemail für Benutzer verwalten, indem Sie Voicemailrichtlinien angeben und Voicemaileinstellungen konfigurieren.  

- **Mit Voicemailrichtlinien** können Sie Features für Benutzergruppen verwalten. Sie können vorhandene oder neue Voicemailrichtlinien für Features wie Anrufbeantwortungsregeln, Voicemailtranskription, Transkription der Profanitätsmaskierung, Transkriptionsübersetzung und Systemeingabeaufforderungssprache konfigurieren und zuweisen. Informationen zum Verwalten von Voicemailrichtlinien finden [Sie unter Verwalten von Voicemailrichtlinien](manage-voicemail-policies.md).

- **Mit den Voicemaileinstellungen** können Sie Einstellungen für einzelne Benutzer konfigurieren. Sie können Einstellungen wie Anrufbeantwortungsregeln, Eingabeaufforderungssprache, Text-zu-Sprache-Standard und Urlaubsgrüße konfigurieren. Informationen zum Konfigurieren von Einstellungen für einzelne Benutzer finden [Sie unter Verwalten von Voicemaileinstellungen](manage-voicemail-settings.md). Beachten Sie, dass Ihre Endbenutzer diese Einstellungen auch im Teams-Client konfigurieren können, indem sie zu **Einstellungen -> Anrufe -> Voicemail konfigurieren** wechseln.

## <a name="control-routing-of-calls-to-cloud-voicemail"></a>Steuern des Routings von Anrufen an Cloud-Voicemail

Die Standardeinstellung für alle Benutzer, die für Cloud-Voicemail bereitgestellt werden, besteht darin, das Weiterleiten von Anrufen an Cloud-Voicemail zu ermöglichen und Benutzern das Weiterleiten von Anrufen an Cloud-Voicemail zu ermöglichen.

Sie können steuern, ob das Routing von Anrufen an Cloud-Voicemail für Teams-Benutzer zulässig ist, indem Sie das Teams Admin Center oder PowerShell verwenden. 

- Um das Teams Admin Center zu verwenden, wechseln Sie zu **VoIP-Anrufrichtlinien** ->  – > hinzufügen oder vorhandene Richtlinie bearbeiten – > **Voicemail für das Routing eingehender Anrufe verfügbar ist**.  

- Verwenden Sie in PowerShell das cmdlet Set-CsTeamsCallingPolicy mit dem Parameter AllowVoicemail. Weitere Informationen finden Sie unter [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

  - Wenn Sie AllowVoicemail auf AlwaysDisabled festlegen, werden Anrufe niemals an Voicemail weitergeleitet – unabhängig von den Einstellungen für die Anrufweiterleitung oder nicht beantworteten Einstellungen für einen Benutzer. Voicemail ist in Teams nicht als Anrufweiterleitung oder unbeantwortete Einstellung verfügbar.

  - Wenn Sie "AllowVoicemail" auf "AlwaysEnabled" festlegen, werden Anrufe nach dem Klingeln für dreißig Sekunden immer an die Voicemail weitergeleitet – unabhängig von der Einstellung für die Unbeantwortete Anrufweiterleitung für einen Benutzer.

  - Wenn Sie AllowVoicemail auf UserOverride festlegen, werden Anrufe basierend auf den Einstellungen für die Anrufweiterleitung und/oder den unbeantworteten Einstellungen für einen Benutzer an die Voicemail weitergeleitet.

## <a name="set-up-cloud-voicemail-to-work-with-on-premises-users"></a>Einrichten Cloud-Voicemail für die Arbeit mit lokalen Benutzern

Sie können Cloud-Voicemail verwenden, um Voicemailfunktionen für Benutzer bereitzustellen, die über Postfächer auf Ihren Exchange-Servern verfügen, oder für Benutzer, die Skype for Business Server verwenden.

In diesem Abschnitt wird beschrieben, wie Sie Cloud-Voicemail für Exchange Server Postfachbenutzer einrichten. Informationen zum Konfigurieren von Cloud-Voicemail für Skype for Business Server Benutzer finden Sie unter [Plan Cloud-Voicemail service for on-premises users](/skypeforbusiness/hybrid/plan-cloud-voicemail).

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Einrichten von Cloud-Voicemail für Exchange Server Postfachbenutzer

Die folgenden Informationen enthalten Informationen zum Konfigurieren von Cloud-Voicemail für die Zusammenarbeit mit Teams-Benutzern, die ihr Postfach auf Exchange Server haben.

1. Voicemailnachrichten werden über SMTP, das über Exchange Online Protection weitergeleitet wird, an das Exchange-Postfach eines Benutzers übermittelt. Um die erfolgreiche Übermittlung dieser Nachrichten zu ermöglichen, stellen Sie sicher, dass Exchange-Connectors zwischen Ihren Exchange-Servern und Exchange Online Protection ordnungsgemäß konfiguriert sind. Weitere Informationen finden Sie unter [Verwenden von Connectors zum Konfigurieren des Nachrichtenflusses](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

2. Um Voicemail-Features wie das Anpassen von Begrüßungen und visuelle Voicemail in Teams-Clients zu aktivieren, müssen Sie die Konnektivität zwischen Microsoft 365 und dem Exchange Server Postfach einrichten. Um diese Konnektivität zu aktivieren, müssen Sie das neue Exchange Oauth-Authentifizierungsprotokoll konfigurieren, das unter [Konfigurieren der OAuth-Authentifizierung zwischen Exchange und Exchange Online Organisationen](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help) beschrieben ist, oder den Exchange-Hybrid-Assistenten ab Exchange 2013 CU5 ausführen. Außerdem müssen Sie die Integration und OAuth zwischen Teams und Exchange Server konfigurieren, die unter [Konfigurieren der Integration und OAuth zwischen Teams und Exchange Server](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises) beschrieben sind.

## <a name="enable-protected-voicemail-in-your-organization"></a>Aktivieren geschützter Voicemails in Ihrer Organisation

Wenn jemand eine Voicemailnachricht für einen Benutzer in Ihrer Organisation hinterlässt, wird die Voicemail als E-Mail-Nachrichtenanlage an das Postfach des Benutzers übermittelt.

Mit Microsoft Purview Information Protection können Sie die Voicemailnachrichten verschlüsseln, die sowohl von internen als auch von externen Anrufern hinterlassen werden. Sie können auch verhindern, dass der Benutzer diese Nachrichten weiterleitet. Dieses Feature wird für Benutzer mit Exchange Online Postfächern unterstützt.

Zum Verschlüsseln der Voicemailnachricht können Sie eine Vertraulichkeitsbezeichnung erstellen. Mit der Funktion für die automatische Bezeichnung können Sie sicherstellen, dass die Bezeichnung automatisch auf eingehende Voicemailnachrichten angewendet wird.

Wenn Sie geschützte Voicemail aktivieren, können Benutzer geschützte Voicemailnachrichten abhören, indem sie sich in ihr Voicemailpostfach einrufen oder die Nachricht in Outlook, Outlook im Web oder Outlook für Android oder iOS öffnen. Geschützte Voicemailnachrichten können in Microsoft Teams oder Skype for Business nicht geöffnet werden.

Informationen zum Erstellen einer Vertraulichkeitsbezeichnung für Voicemail finden [Sie unter Verwenden von Vertraulichkeitsbezeichnungen](/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions). Wählen Sie im Abschnitt **"Verschlüsselung** " die Option " **Benutzern das Zuweisen von Berechtigungen gestatten" aus, wenn sie die Bezeichnung anwenden**. Wählen Sie **in Outlook aus, erzwingen Sie eine der folgenden Einschränkungen**, und wählen Sie dann die Option **"Nicht weiterleiten** " aus.

Informationen zum Erstellen der Richtlinie für die automatische Bezeichnung zum Anwenden einer Vertraulichkeitsbezeichnung auf Voicemail finden Sie unter [Konfigurieren von Richtlinien für automatische Bezeichnungen](/microsoft-365/compliance/apply-sensitivity-label-automatically#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) und Angeben der folgenden spezifischen Einstellungen:

- **Wählen Sie für "Informationen auswählen", auf die diese Bezeichnung angewendet werden soll**, **die Option "Benutzerdefinierte Richtlinie" aus**.

- Wählen **Sie für "Speicherorte auswählen", auf die Sie die Bezeichnung anwenden möchten**, **"Speicherorte: Exchange für alle Benutzer**" aus.

- Wählen  **Sie für "Allgemeine oder erweiterte Regeln einrichten**" die Option **"Erweiterte Regeln**" aus.

- Exchange-Regeln:
  - Bedingungen:
    - **Headerübereinstimmungsmuster**: Content-Class = Voice-CA
    - **Ip-Adresse des Absenders:** 13.107.64.0/18, 52.112.0.0/14, 52.120.0.0/14, 52.238.119.141/32, 52.244.160.207/32

- **Wenn Sie eine Bezeichnung für die automatische Anwendung auswählen möchten**, wählen Sie die Vertraulichkeitsbezeichnung aus, die Sie im obigen Schritt für Voicemail erstellt haben.

- Wenn **Sie zusätzliche Einstellungen für E-Mails** erhalten möchten, wählen Sie " **Verschlüsselung auf E-Mails anwenden" aus, die von außerhalb Ihrer Organisation empfangen werden**, und geben Sie den Besitzer der Rechteverwaltung an.

Die in der Absender-IP-Adresse angegebenen IP V4-Bereiche basieren auf der Liste in ID 12 in [Office 365 URLs und IP-Adressbereichen](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).

Weitere Informationen zur Nachrichtenverschlüsselung finden [Sie unter Definieren von Nachrichtenflussregeln zum Verschlüsseln von E-Mail-Nachrichten](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).

## <a name="help-your-users-learn-about-cloud-voicemail-features"></a>Helfen Sie Ihren Benutzern, mehr über Cloud-Voicemail-Features zu erfahren

Um Ihren Benutzern zu helfen, mehr über die Verwendung und Verwaltung Cloud-Voicemail Features zu erfahren, können Sie die folgenden Artikel empfehlen:

- [Überprüfen Ihrer Voicemail in Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [Verwalten Ihrer Anrufeinstellungen in Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)
