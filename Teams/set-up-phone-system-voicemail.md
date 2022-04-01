---
title: Einrichten von Cloud-Voicemail
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
ms.openlocfilehash: dd98275ac768990337a47f1f4ba6dacbdb385087
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592720"
---
# <a name="set-up-cloud-voicemail"></a>Einrichten von Cloud-Voicemail

Dieser Artikel ist für Microsoft 365 vorgesehen, die ein Cloud-Voicemail für ihre Benutzer einrichten möchten.

Cloud-Voicemail ablagert Voicemailnachrichten im Postfach Exchange Benutzers. Cloud-Voicemail unterstützt keine E-Mail-Systeme von Drittanbietern. Weitere Exchange Online finden Sie unter [Exchange Online der Dienstbeschreibung](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description#features-available-to-all-plans). Weitere Informationen zu Administratorrollen finden Sie unter Informationen [zu Administratorrollen](/microsoft-365/admin/add-users/about-admin-roles).

## <a name="cloud-voicemail-provisioning"></a>Cloud-Voicemail-Bereitstellung

Für Teams Benutzer wird Cloud-Voicemail automatisch eingerichtet und bereitgestellt. *Für Microsoft Teams Telefon ist keine Lizenz Cloud-Voicemail.*

Die Bereitstellung Teams Benutzer ist nicht dasselbe wie für Skype for Business Online-Benutzer. Für Skype for Business Online-Benutzer wurde Cloud-Voicemail automatisch eingerichtet und bereitgestellt, wenn den Benutzern eine Telefonsystem-Lizenz zugewiesen wurde und Enterprise-VoIP Bereitstellungssystem aktiviert wurde.

Für Skype for Business Server lokalen Benutzer wird Cloud-Voicemail automatisch eingerichtet und bereitgestellt. Sie müssen jedoch die Umgebung für Skype for Business Server konfigurieren, um Anrufe an Cloud-Voicemail. Weitere Informationen finden Sie unter [Cloud-Voicemail dienst für lokale Benutzer.](/skypeforbusiness/hybrid/plan-cloud-voicemail)

## <a name="cloud-voicemail-storage"></a>Cloud-Voicemail von Speicher

Voicemailnachrichten, die von Cloud-Voicemail generiert werden, werden an das Exchange-Postfach des Benutzers übermittelt und dort gespeichert, entweder in einem Exchange Online oder in Exchange Server. Es gibt keinen spezifischen oder zusätzlichen Speicher für Voicemail. Die Clients, die auf Voicemail zugreifen (z. B. Microsoft Outlook, Microsoft Teams oder Skype for Business), verwenden dazu das Exchange-Postfach und die bereitgestellten APIs.

Eine Voicemailnachricht enthält eine angefügte Audiodatei mit den Sprachnachrichten und der Voicemail-Transkription (sofern aktiviert).

Das Exchange Postfach eines Benutzers speichert alle benutzerdefinierten aufgezeichneten Begrüßungen. Diese Begrüßungen werden nach Bedarf Cloud-Voicemail während eines eingehenden Anrufs abgerufen.

## <a name="cloud-voicemail-processing"></a>Cloud-Voicemail wird verarbeitet

Die Aufzeichnung und Transkription der Cloud-Voicemail beginnt in Microsoft 365, wenn der Anruf an die andere Cloud-Voicemail. Die Nachricht wird dann an das Postfach des Exchange zugestellt.

Wenn beispielsweise ein Anruf bei einem nicht verfügbaren Direct Routing-Benutzer über einen Session Border Controller (SBC) in Europa einkommt, erfolgt die Voicemailaufzeichnung und -transkription in Europa. Die Nachricht wird dann an das Postfach des Exchange zugestellt. Ein weiteres Beispiel: Angenommen, ein Teams in Nordamerika anruft einen nicht verfügbaren Teams in Europa. In diesem Fall beginnt der Anruf in Nordamerika, die Verarbeitung erfolgt in Nordamerika, und die Voicemail wird dann an das Postfach des Benutzers Exchange in Europa übermittelt.

Die Zustellung einer Voicemail an ein Exchange-Postfach erfolgt wie jede andere E-Mail mithilfe von SMTP (Simple Mail Transport Protocol).

## <a name="manage-cloud-voicemail-for-users"></a>Verwalten Cloud-Voicemail für Benutzer

Zum Verwalten Cloud-Voicemail Features für Ihre Benutzer verwenden Sie das Teams PowerShell-Modul wie folgt.

Zum Verwalten Cloud-Voicemail Features für Benutzergruppen verwenden Sie das [Cmdlet New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy).
Sie können vorhandene oder neue Voicemailrichtlinien für Features wie Anrufbeantwortungsregeln, Voicemail-Transkription, Transkription von obszöner Transkription, Transkriptionübersetzung und Systemanrufsprache konfigurieren und zuweisen. Weitere Informationen finden Sie unter [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy).

Zum Verwalten Cloud-Voicemail Einstellungen für einzelne Benutzer verwenden Sie das [Cmdlet Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings). Cloud-Voicemail Einstellungen, die Sie auf einzelne Benutzer anwenden können, umfassen Anrufbeantwortungsregeln, Eingabeaufforderungssprache, Standardtext zu Sprache und Urlaubsgrüße. Weitere Informationen finden Sie unter [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings).
(Beachten Sie, dass Die Endbenutzer diese Einstellungen auch im Teams-Client konfigurieren können, indem sie zu **Einstellungen** ->  **CallsConfigure** ->  **Voicemail" gehen**.)

Sie können auch Cloud-Voicemail für einen Benutzer deaktivieren, indem Sie das [Cmdlet Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) verwenden und den Parameter VoicemailEnabled auf $false. Diese Einstellung stellt sicher, Cloud-Voicemail keine Voicemail mehr für den Benutzer aufzeichnen kann.

## <a name="control-routing-of-calls-to-cloud-voicemail"></a>Steuern des Routings von Anrufen an Cloud-Voicemail

Die Standardeinstellung für alle benutzer, die für Cloud-Voicemail bereitgestellt werden, ist das Weiterleiten von Anrufen an Cloud-Voicemail und das Weiterleiten von Anrufen an Cloud-Voicemail.

Mit dem cmdlet Set-CsTeamsCallingPolicy AllowVoicemail können Sie steuern, ob Cloud-Voicemail Weiterleitung von Anrufen an Teams Benutzer zulässig ist. Weitere Informationen finden Sie  [unterSet-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

- Wenn Sie AllowVoicemail auf AlwaysDisabled festlegen, werden Anrufe nie an die Voicemail weitergeleitet – unabhängig von den Einstellungen für die Weiterleitung oder die Einstellungen für nicht beantwortete Anrufe eines Benutzers. Voicemail ist in der Standardeinstellung für Anruf weiterleiten oder nicht Teams.

- Wenn Sie AllowVoicemail auf AlwaysEnabled festlegen, werden Anrufe immer nach 30 Sekunden unbeantwortet an die Voicemail weitergeleitet– unabhängig von der Einstellung für nicht beantwortete Anrufanrufe für einen Benutzer.

- Wenn Sie AllowVoicemail auf UserOverride festlegen, werden Anrufe basierend auf der Anrufumschaltung und/oder nicht beantworteten Einstellungen für einen Benutzer an die Voicemail weitergeleitet.

## <a name="set-up-cloud-voicemail-to-work-with-on-premises-users"></a>Einrichten Cloud-Voicemail für die Zusammenarbeit mit lokalen Benutzern

Mithilfe von Cloud-Voicemail können Sie Voicemailfunktionen für Benutzer bereitstellen, die über Postfächer auf Ihren Exchange-Servern verfügen, oder für Benutzer, die Ihre Skype for Business Server.

In diesem Abschnitt wird beschrieben, wie Sie Cloud-Voicemail Postfachbenutzer Exchange Server einrichten. Informationen zum Konfigurieren von Cloud-Voicemail für Skype for Business Server Benutzer finden Sie unter Cloud-Voicemail eines Diensts für [lokale Benutzer](/skypeforbusiness/hybrid/plan-cloud-voicemail).

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Einrichten von Cloud-Voicemail für Exchange Server Postfachbenutzer

Die folgenden Informationen enthalten Informationen zum Konfigurieren Cloud-Voicemail für benutzer Teams, die ihr Postfach auf einem Exchange Server.

1. Voicemailnachrichten werden an das Postfach eines Benutzers Exchange über SMTP übermittelt, das über die Exchange Online Protection. Um eine erfolgreiche Übermittlung dieser Meldungen zu ermöglichen, stellen Sie sicher, dass Exchange Connectors zwischen Ihren Exchange-Servern und Exchange Online Protection. Weitere Informationen finden Sie unter [Verwenden von Connectors zum Konfigurieren von E-Mail Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

2. Um Voicemailfeatures wie das Anpassen von Begrüßungen und visuellen Voicemails in Teams-Clients zu aktivieren, müssen Sie die Verbindung zwischen Microsoft 365 und dem Postfach Exchange Server einrichten. Um diese Verbindung zu aktivieren, müssen Sie das neue Exchange Oauth-Authentifizierungsprotokoll konfigurieren, das unter Konfigurieren der [OAuth-Authentifizierung zwischen Exchange und Exchange Online-Organisationen](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help) beschrieben ist, oder den Exchange-Hybrid-Assistenten von Exchange 2013 CU5 oder höher ausführen. Sie müssen auch die Integration und Oauth zwischen Teams und Exchange Server die unter Konfigurieren der [Integration und OAuth](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises) zwischen Teams und Exchange Server.

## <a name="enable-protected-voicemail-in-your-organization"></a>Aktivieren von geschützten Voicemails in Ihrer Organisation

Wenn jemand eine Voicemailnachricht für einen Benutzer in Ihrer Organisation verlässt, wird die Voicemail als Anlage einer E-Mail-Nachricht an das Postfach des Benutzers zugestellt. 

Mithilfe Microsoft Information Protection können Sie die Voicemailnachrichten verschlüsseln, die sowohl von internen als auch von externen Anrufern gesendet wurden. Sie können auch verhindern, dass benutzer diese Nachrichten weiterleiten. Dieses Feature wird für Benutzer mit Exchange Online unterstützt.

Zum Verschlüsseln der Voicemailnachricht können Sie eine Vertraulichkeitsbezeichnung erstellen. Mit der automatischen Beschriftungsfunktion können Sie sicherstellen, dass die Bezeichnung automatisch auf eingehende Voicemailnachrichten angewendet wird. 

Wenn Sie geschützte Voicemail aktivieren, können Benutzer geschützte Voicemailnachrichten abhören, indem sie sich in ihr Voicemail-Postfach einrufen oder indem sie die Nachricht in Outlook, Outlook im Web oder Outlook für Android oder iOS öffnen. Geschützte Voicemailnachrichten können nicht in anderen Microsoft Teams oder auf Skype for Business.

Informationen zum Erstellen einer Vertraulichkeitsbezeichnung für Voicemail finden Sie unter [Verwenden von Vertraulichkeitsbezeichnungen](/microsoft-365/compliance/encryption-sensitivity-labels?view=o365-worldwide#let-users-assign-permissions). Wählen Sie **im Abschnitt Verschlüsselung** die Option **Benutzern das Zuweisen von Berechtigungen gestatten, wenn sie die Bezeichnung anwenden aus**. Wählen **Sie in Outlook eine der folgenden Einschränkungen** durch, und wählen Sie dann die Option Nicht **weiterleiten** aus.

Informationen zum Erstellen der Automatischen Kennzeichnungsrichtlinie, um eine Vertraulichkeitsbezeichnung auf Voicemail anzuwenden, finden Sie unter Konfigurieren von Richtlinien für die automatische [Beschriftung und Festlegen](/microsoft-365/compliance/apply-sensitivity-label-automatically?view=o365-worldwide#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) der folgenden spezifischen Einstellungen:

-   Wählen **Sie für Informationen auswählen, auf die diese Bezeichnung angewendet werden soll** die Option **Benutzerdefinierte Richtlinie aus**.

-   Wählen **Sie unter Speicherorte auswählen, an denen Sie die Bezeichnung** anwenden möchten die Option **Orte: Exchange für alle Benutzer aus**.

-   Wählen  **Sie unter Allgemeine oder erweiterte Regeln einrichten** die Option **Erweiterte Regeln aus**.

- Exchange Regeln:
    - Bedingungen:<br>
        - **Header entspricht dem Muster:**<br>
              Content-Class = Voice-CA
       -  **Absender-IP-Adresse:**<br>
               13.107.64.0/18, 52.112.0.0/14, 52.120.0.0/14, 52.238.119.141/32, 52.244.160.207/32

- Wählen **Sie für Bezeichnung auswählen, die automatisch angewendet werden soll** im vorstehenden Schritt die Vertraulichkeitsbezeichnung aus, die Sie für Voicemail erstellt haben.

- Wenn **Sie zusätzliche Einstellungen für E-Mails vornehmen** möchten, wählen Sie Verschlüsselung auf E-Mails anwenden **aus, die** von außerhalb Ihrer Organisation empfangen wurden, und geben Sie den Besitzer der Rechteverwaltung an.

Die ip V4 ranges specified in Sender IP address is based on the list in ID 12 in [Office 365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#skype-for-business-online-and-microsoft-teams).

Weitere Informationen zur Nachrichtenverschlüsselung finden Sie unter [Definieren von Nachrichtenflussregeln zum Verschlüsseln von E-Mail-Nachrichten](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).

## <a name="help-your-users-learn-about-cloud-voicemail-features"></a>Unterstützen der Benutzer beim Erlernen der Cloud-Voicemail Features

Wenn Sie Ihren Benutzern dabei helfen möchten, mehr über die Verwendung und Verwaltung Cloud-Voicemail Features zu erfahren, können Sie die folgenden Artikel empfehlen:

- [Überprüfen Sie Ihre Voicemail in Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [Verwalten Sie Ihre Anrufeinstellungen in Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)
