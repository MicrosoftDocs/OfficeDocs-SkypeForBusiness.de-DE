---
title: Übersicht über app validation and app testing by Microsoft
ms.reviewer: ''
description: Grundlegendes zu den Qualitätsprüfungen und der App-Validierung für Teams Apps.
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 04/05/2022
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a916d6bdd57c2956c076461d7f36df64d5c503d9
ms.sourcegitcommit: 745d707ec63685ce7f973785e7056628472b9c45
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2022
ms.locfileid: "64910901"
---
# <a name="validation-performed-by-microsoft-for-all-teams-apps"></a>Von Microsoft durchgeführte Überprüfung für alle Teams-Apps

Microsoft erfordert, dass alle Apps eine obligatorische Überprüfung bestehen, bevor sie für die Endverwendung im Store aufgeführt werden. Sie gilt für alle Apps (mit Ausnahme von benutzerdefinierten Apps), die im Teams App Store veröffentlicht wurden. Darüber hinaus empfiehlt Microsoft App-Entwicklern dringend, an einer optionalen Zertifizierung von Apps teilzunehmen, die auf erweiterte Compliance-, Sicherheits- und Datenschutzkontrollen hinweist.

Alle Apps sind zwingend erforderlich, um die Zertifizierungsrichtlinien für Microsoft-Apps einzuhalten. Das Teams Store-Team führt mehr als 400 Tests durch, um sicherzustellen, dass die Apps verwendbar sind und hohen Datenschutz- und Sicherheitsstandards entsprechen.

Die detaillierten Validierungsrichtlinien, die App-Entwickler einhalten, finden Sie in den [Validierungsrichtlinien für Entwickler](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines). Der Leitfaden basiert auf den [Zertifizierungsrichtlinien für Teams Apps](/legal/marketplace/certification-policies#1140-teams).

> [!NOTE]
> Überprüfungen und Überprüfungen durch Microsoft sind für eine benutzerdefinierte App nicht verfügbar, da sie in Ihrer Organisation entwickelt wurde und nur für Mitglieder Ihrer Organisation verfügbar ist.

## <a name="app-validation-and-testing"></a>App-Überprüfung und -Tests

Wir führen über 400 Testfälle für jede App aus, bevor sie im Teams Store verfügbar gemacht wird. Die Tests stellen die entsprechende Funktionalität, Benutzererfahrung und Sicherheit sicher und stellen sicher, dass alle Apps den öffentlich aufgeführten CMO-Richtlinien entsprechen. Es folgen einige der Tests, die vom Microsoft App Validation-Team für jede App durchgeführt wurden, bevor sie veröffentlicht wird:

* Stellen Sie sicher, dass die von der App angeforderten Graph-Berechtigungen wirklich diejenigen sind, die die App-Funktionalität benötigt, und keine zusätzlichen Berechtigungen. Graph-Berechtigungen für vorhandene Apps werden regelmäßig überprüft, um sicherzustellen, dass keine zusätzlichen Berechtigungen für eine App erforderlich sind.
* Apps, für die sich Benutzer anmelden müssen, verfügen über eine Abmeldeoption.
* Alle App-Herausgeber durchlaufen einen detaillierten Überprüfungsprozess im Microsoft Partner Center. Die Überprüfung umfasst die E-Mail-Überprüfung, die Geschäftliche Überprüfung und vieles mehr. Weitere Informationen zur App-Veröffentlichung finden Sie unter [Erstellen eines Partner Center-Kontos durch Entwickler](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/create-partner-center-dev-account), [Übermittlungshandbuch für Entwickler](/office/dev/store/add-in-submission-guide) und [Veröffentlichen von Apps durch Entwickler](https://aka.ms/PublishToTeamsStore).
* Nur Apps von bestätigten Herausgebern können Graph-Berechtigungen von Endbenutzern anfordern.
* Keine App kann eine ausführbare Datei herunterladen.
* Apps werden so getestet, dass sie keine Werbung enthalten, werbung für andere Apps
* Apps werden so getestet, dass sie ohne anstößige Sprache, Cyberangriffs-Bots, Spam oder Betrugsinhalte geeignet sind.
* Alle Links in einer App sind funktionsfähig und beziehen sich nur auf das App-Angebot.
* Wir testen und bewerten alle veröffentlichten Teams-Apps regelmäßig im Rahmen von App Store-Integritätsprüfungen.
* Datenschutzrichtlinien und Nutzungsbedingungen, die Teams Apps abdecken, werden vom ISV veröffentlicht
* Die Kontaktdaten des ISV finden Sie im Store-Eintrag und auf den jeweiligen [Publisher-Nachweisseiten](/microsoft-365-app-certification/teams/teams-apps).

Darüber hinaus empfiehlt Microsoft den App-Entwicklern, an ihrem Complianceprogramm teilzunehmen, bei dem es sich um einen strengen, zweistufigen Ansatz handelt, um App-Qualität, Sicherheit und Compliance sicherzustellen. Teams Store verfügt über Hunderte von Apps, die über die Erfüllung der bereits detaillierten Validierungsrichtlinien hinausgehen und diese Programme einhalten.

## <a name="see-also"></a>Siehe auch

* [Übersicht für Administratoren des Microsoft 365 App-Compliance-Programms](overview-of-app-certification.md)
