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
ms.openlocfilehash: cf4edb7043c3d9965f2f01710f1ed9e7fa7f96b8
ms.sourcegitcommit: 9ef6e36eeba7db70971f4eb1a45f0ded394b1fe6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2022
ms.locfileid: "62191076"
---
# <a name="set-up-cloud-voicemail"></a>Einrichten von Cloud-Voicemail

Dieser Artikel gilt für Microsoft 365 oder Office 365 Administrator, [](/microsoft-365/admin/add-users/about-admin-roles) wie unter Informationen zu Administratorrollen beschrieben, die das Cloud-Voicemail-Feature für alle Benutzer im Unternehmen einrichten. Cloud-Voicemail erfordert Exchange Postfächer für Benutzer, an denen Voicemailnachrichten gespeichert werden. E-Mail-Systeme von Drittanbietern werden nicht unterstützt. Weitere Exchange Online zur Lizenzierung finden Sie unter [Exchange Online Servicebeschreibung.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description#features-available-to-all-plans)

## <a name="cloud-voicemail-for-teams-users"></a>Cloud-Voicemail für Teams Benutzer

Für Teams Benutzer Cloud-Voicemail automatisch eingerichtet und bereitgestellt. Für Microsoft Teams Telefon ist keine Lizenz Cloud-Voicemail.

## <a name="help-your-users-learn-teams-voicemail-features"></a>Unterstützen der Benutzer beim Erlernen Teams Voicemail-Funktionen

Wir haben die folgenden Informationen für Ihre Benutzer zum Verwenden und Verwalten von Voicemail in Teams:

- [Check your voicemail in Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [Verwalten Sie Ihre Anrufeinstellungen in Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)

## <a name="setting-up-cloud-voicemail-to-work-with-on-premises-users"></a>Einrichten Cloud-Voicemail für die Zusammenarbeit mit lokalen Benutzern

Mithilfe von Cloud-Voicemail können Sie Voicemailfunktionen für Ihre Benutzer bereitstellen, die über Postfächer auf Ihren Exchange-Servern verfügen, oder für Benutzer, die Ihre E-Mail-Skype for Business Server. Dieser Abschnitt enthält Informationen zu diesen Szenarien. 

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Einrichten von Cloud-Voicemail für Exchange Server-Postfachbenutzer

Die folgenden Informationen enthalten Informationen zum Konfigurieren Cloud-Voicemail für die Zusammenarbeit Microsoft Teams Telefon Benutzer, die ihr Postfach auf einem Exchange Server.

1. Voicemailnachrichten werden an das Postfach der Benutzer Exchange über SMTP übermittelt, über die sie Exchange Online Protection. Um eine erfolgreiche Übermittlung dieser Meldungen zu ermöglichen, stellen Sie sicher, dass Exchange Connectors zwischen Ihren Exchange-Servern und Exchange Online Protection; [Verwenden Von Connectors können Sie E-Mail-Flow.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)

2. Zum Aktivieren von Voicemailfeatures wie dem Anpassen von Begrüßungen und visuellen Voicemails in Skype for Business-Clients ist die Konnektivität von Microsoft 365 oder Office 365 zum Exchange-Serverpostfach über Exchange-Webdienste erforderlich. Um diese Verbindung zu aktivieren, müssen Sie das neue Exchange Oauth-Authentifizierungsprotokoll konfigurieren, das unter Konfigurieren der [OAuth-Authentifizierung](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)zwischen Exchange und Exchange Online-Organisationen beschrieben ist, oder den Exchange-Hybrid-Assistenten ab Exchange 2013 CU5 ausführen. Darüber hinaus müssen Sie die Integration und Oauth zwischen Skype for Business Online und Exchange Server konfigurieren, die unter Konfigurieren der Integration und [OAuth](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)zwischen Skype for Business Online und Exchange Server.

### <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>Einrichten von Cloud-Voicemail für Skype for Business Server Benutzer

Informationen zum Skype for Business von Serverbenutzern für Cloud-Voicemail finden Sie unter Cloud-Voicemail des Diensts für [lokale Benutzer.](/skypeforbusiness/hybrid/plan-cloud-voicemail)

## <a name="enabling-protected-voicemail-in-your-organization"></a>Aktivieren geschützter Voicemails in Ihrer Organisation

Wenn jemand eine Voicemailnachricht für einen Benutzer in Ihrer Organisation verlässt, wird die Voicemail als Anlage einer E-Mail-Nachricht an das Postfach des Benutzers zugestellt. Wenn Sie Nachrichtenverschlüsselung mithilfe von Nachrichtenflussregeln anwenden, können Sie verhindern, dass diese Voicemailnachrichten an andere Empfänger weitergeleitet werden. Wenn Sie geschützte Voicemail aktivieren, können Benutzer geschützte Voicemailnachrichten abhören, indem sie sich in ihr Voicemail-Postfach einrufen oder indem sie die Nachricht in Outlook, Outlook im Web oder in Outlook für Android oder iOS öffnen. Geschützte Voicemailnachrichten können nicht in anderen Skype for Business oder in Microsoft Teams.

Weitere Informationen zur Nachrichtenverschlüsselung finden Sie unter [Definieren von Nachrichtenflussregeln zum Verschlüsseln von E-Mail-Nachrichten.](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)
