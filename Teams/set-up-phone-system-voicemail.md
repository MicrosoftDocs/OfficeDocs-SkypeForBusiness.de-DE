---
title: Einrichten von Cloud-Voicemail
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: wasseemh, phans
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
ms.openlocfilehash: f4547d081cf7b0175da7222bf68fde97cecd21c9
ms.sourcegitcommit: d23185cf6caeeeb055c36609e7c788a2b2e8d07d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2021
ms.locfileid: "60367507"
---
# <a name="set-up-cloud-voicemail"></a>Einrichten von Cloud-Voicemail

Dieser Artikel gilt für Microsoft 365 oder Office 365 Administrator, [](/microsoft-365/admin/add-users/about-admin-roles) wie unter Informationen zu Administratorrollen beschrieben, die das Cloud-Voicemail-Feature für alle Benutzer im Unternehmen einrichten.

> [!NOTE]
> Cloud-Voicemail unterstützt die Ablage von Voicemailnachrichten nur in einem Exchange-Postfach und keine E-Mail-Systeme von Drittanbietern.

> [!NOTE]
> Wenn eine Stellvertretung einen Anruf im Namen einer Stellvertretung beantwortet, sind in der Stellvertretung keine Benachrichtigungen Cloud-Voicemail. Benutzer können Benachrichtigungen über verpasste Anrufe erhalten.

## <a name="cloud-voicemail-for-teams-users"></a>Cloud-Voicemail für Teams Benutzer

Für Teams Benutzer Cloud-Voicemail automatisch eingerichtet und bereitgestellt. Beachten Sie, dass für Telefonsystem keine Lizenz Cloud-Voicemail.

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Einrichten von Cloud-Voicemail für Exchange Server Postfachbenutzer

Die folgenden Informationen enthalten Informationen zum Konfigurieren Cloud-Voicemail, damit sie mit Benutzern zusammenarbeiten, die für Telefonsystem online sind, aber ihr Postfach auf Exchange Server.

1. Voicemailnachrichten werden an das Postfach des benutzers Exchange über SMTP übermittelt, über das Nachrichten Exchange Online Protection. Um eine erfolgreiche Übermittlung dieser Nachrichten zu ermöglichen, stellen Sie sicher, dass Exchange Connectors zwischen Ihren Exchange-Servern und Exchange Online Protection; [Verwenden Von Connectors können Sie E-Mail-Flow.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)

2. Zum Aktivieren von Voicemailfeatures wie dem Anpassen von Begrüßungen und visuellen Voicemails in Skype for Business-Clients ist die Verbindung von Microsoft 365 oder Office 365 zum Exchange-Serverpostfach über Exchange-Webdienste erforderlich. Um diese Verbindung zu aktivieren, müssen Sie das neue Exchange Oauth-Authentifizierungsprotokoll konfigurieren, das unter Konfigurieren der [OAuth-Authentifizierung](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)zwischen Exchange und Exchange Online-Organisationen beschrieben ist, oder den Exchange-Hybrid-Assistenten ab Exchange 2013 CU5 ausführen. Darüber hinaus müssen Sie die Integration und Oauth zwischen Skype for Business Online und Exchange Server konfigurieren, die unter Konfigurieren der Integration und [OAuth zwischen Skype for Business Online](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)und Exchange Server.

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>Einrichten von Cloud-Voicemail für Skype for Business Server Benutzer

Informationen zum Skype for Business von Serverbenutzern Cloud-Voicemail Sie unter Planen Cloud-Voicemail Diensts für [lokale Benutzer.](/skypeforbusiness/hybrid/plan-cloud-voicemail)

## <a name="enabling-protected-voicemail-in-your-organization"></a>Aktivieren geschützter Voicemails in Ihrer Organisation

Wenn jemand eine Voicemailnachricht für einen Benutzer in Ihrer Organisation verlässt, wird die Voicemail als Anlage einer E-Mail-Nachricht an das Postfach des Benutzers zugestellt. Wenn Sie Nachrichtenverschlüsselung mithilfe von Nachrichtenflussregeln anwenden, können Sie verhindern, dass diese Voicemailnachrichten an andere Empfänger weitergeleitet werden. Wenn Sie geschützte Voicemail aktivieren, können Benutzer geschützte Voicemailnachrichten abhören, indem sie sich in ihr Voicemail-Postfach einrufen oder indem sie die Nachricht in Outlook, Outlook im Web oder in Outlook für Android oder iOS öffnen. Geschützte Voicemailnachrichten können nicht in einem Skype for Business oder einer Microsoft Teams.

Weitere Informationen zur Nachrichtenverschlüsselung finden Sie unter [E-Mail-Verschlüsselung.](/microsoft-365/compliance/email-encryption)

> [!NOTE]
> Wir wenden Die Verschlüsselung auf die Voicemail nur an, wenn der Anruf von einem internen Benutzer kommt. Wenn der Anruf von einem externen Benutzer anruft, wird die Voicemail nicht verschlüsselt.

Gehen Sie wie folgt vor, um geschützte Voicemails zu einrichten:

1. Wechseln Sie zu <https://admin.microsoft.com> , und melden Sie sich mit einem Konto mit globalen Administratorberechtigungen an.
2. Wählen **Sie Alle anzeigen** aus, und wechseln Sie dann zu Admin **Center**  >  **Exchange.**
3. Wählen Sie Exchange Admin Center die Option **Nachrichtenflussregeln**  >  **aus.**
4. Wählen **+** **Sie Hinzufügen** aus, und wählen Sie dann Office 365-Nachrichtenverschlüsselung **- und -Rechteschutz auf Nachrichten anwenden aus.**
5. Geben Sie einen Namen für die neue Nachrichtenflussregel ein, und wählen Sie dann unter Diese Regel **anwenden, wenn** die Option Die Nachrichteneigenschaften Schließen Sie den Nachrichtentyp   >   \> **Voicemail ein.** Wählen Sie **OK aus.**
6. Wählen **Sie unter Folgendes tun** die Option Anwenden **Office 365-Nachrichtenverschlüsselung-** und Rechteschutz auf die Nachricht mit aus, und wählen Sie dann eine **aus.** Wählen **Sie unter RMS-Vorlage** die Option **Nicht weiterleiten aus.** Wählen **Sie OK** und dann Speichern **aus.**

    > [!NOTE]
    > Wenn die **RMS-Vorlagenliste** leer ist, müssen Sie die Nachrichtenverschlüsselung einrichten. Weitere Informationen zum Einrichten der Nachrichtenverschlüsselung finden Sie in den folgenden Artikeln:
    >
    > - [Einrichten neuer Nachrichtenverschlüsselungsfunktionen](/microsoft-365/compliance/set-up-new-message-encryption-capabilities)
    > - [Konfigurieren und Verwalten von Vorlagen für Azure Information Protection](/information-protection/deploy-use/configure-policy-templates)
    > - [Option "Nicht weiterleiten" für E-Mails](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

    > [!NOTE]
    > Sie müssen den folgenden Registrierungsschlüssel für Benutzer, Unternehmen und Organisationen festlegen, in denen das Voicemailformular angezeigt werden soll: [HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Outlook\Addins] "AllowVoicemailForm"=dword:00000001

## <a name="help-your-users-learn-teams-voicemail-features"></a>Unterstützen der Benutzer beim Erlernen Teams Voicemail-Funktionen

Wir haben die folgenden Informationen für Ihre Benutzer zum Verwalten ihrer Voicemaileinstellungen sowie weitere Anruffunktionen in Teams:

- [Verwalten Sie Ihre Anrufeinstellungen in Teams.](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f) In diesem Artikel wird erläutert, wie Sie alle Anruffunktionen Teams Endbenutzer verwalten.

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Unterstützen Sie Ihre Benutzer bei der Verwendung der Skype for Business-Voicemail-Funktionen.

Wir bieten Schulungsinformationen und Artikel an, damit Ihre Benutzer erfolgreich mit Skype for Business-Voicemail arbeiten können. Machen Sie Ihre Benutzer auf folgende Artikel aufmerksam:

- [Prüfen von Skype for Business-Voicemail und -Optionen](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): In diesem Artikel wird erläutert, wie Sie Ihre Voicemail in Skype for Business abhören, Ihre Voicemailansage ändern und sich Ihre Voicemail in unterschiedlichen Geschwindigkeiten anhören.

- [Skype for Business 2016-Schulung](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Verwandte Themen

[Einrichten von Skype for Business Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Erfahren Sie, was Ihnen das Telefonsystem bietet](here-s-what-you-get-with-phone-system.md)

[Planen der Migration von Skype for Business Server und Exchange Server](/SkypeForBusiness/hybrid/plan-um-migration)
