---
title: Übersicht über app validation and app testing by Microsoft
ms.reviewer: ''
description: Verstehen der Qualitätsprüfungen, App-Validierung und Zertifizierungsprogramme für Teams Apps.
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
ms.openlocfilehash: 9accce27ded20f8ce78d4d5b80f6aff474213675
ms.sourcegitcommit: c2a77ef9c1c9e6f00b3a4589bf02b100c37f5801
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2022
ms.locfileid: "64649024"
---
# <a name="checks-and-validation-performed-by-microsoft-on-teams-apps"></a>Prüfungen und Überprüfungen, die von Microsoft in Teams-Apps durchgeführt werden

Microsoft erfordert, dass alle Apps eine obligatorische Überprüfung bestehen, bevor sie für die Endverwendung im Store aufgeführt werden. Sie gilt für alle Apps (mit Ausnahme von benutzerdefinierten Apps), die im Teams App Store veröffentlicht wurden. Darüber hinaus empfiehlt Microsoft App-Entwicklern dringend, an einer optionalen Zertifizierung von Apps teilzunehmen, die auf erweiterte Compliance-, Sicherheits- und Datenschutzkontrollen hinweist.

Alle Apps sind zwingend erforderlich, um die Zertifizierungsrichtlinien für Microsoft-Apps einzuhalten. Das Teams Store-Team führt mehr als 400 Tests durch, um sicherzustellen, dass die Apps verwendbar sind und hohen Datenschutz- und Sicherheitsstandards entsprechen.

Die detaillierten Validierungsrichtlinien, die App-Entwickler einhalten, finden Sie in den [Validierungsrichtlinien für Entwickler](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines).

> [!NOTE]
> Überprüfungen und Überprüfungen durch Microsoft sind für eine benutzerdefinierte App nicht verfügbar, da sie in Ihrer Organisation entwickelt wurde und nur für Mitglieder Ihrer Organisation verfügbar ist.

<!--- TBD: Add the link later. 
To review the certification policies of any app, see [App certification policies]().
Is the link /microsoft-365-app-certification/teams/teams-apps
--->

## <a name="app-validation-and-testing"></a>App-Überprüfung und -Tests

Wir führen über 400 Testfälle für jede App aus, bevor sie auf der Teams Store verfügbar gemacht wird. Die Tests stellen die entsprechende Funktionalität, Benutzererfahrung und Sicherheit sicher und stellen sicher, dass alle Apps den öffentlich aufgeführten CMO-Richtlinien entsprechen. Es folgen einige der Tests, die vom Microsoft App Validation-Team für jede App durchgeführt wurden, bevor sie veröffentlicht wird:

* Stellen Sie sicher, dass Graph von der App angeforderten Berechtigungen wirklich die Berechtigungen sind, die die App-Funktionalität benötigt, und keine zusätzlichen Berechtigungen. Graph Berechtigungen für vorhandene Apps werden regelmäßig überprüft, um sicherzustellen, dass keine zusätzlichen Berechtigungen für eine App erforderlich sind.
* Apps, für die Benutzer sich anmelden/anmelden müssen, müssen über eine Option zum Abmelden/Abmelden verfügen.
* Alle App-Herausgeber durchlaufen einen detaillierten Überprüfungsprozess im Microsoft Partner Center. Die Überprüfung umfasst die E-Mail-Überprüfung, die Geschäftliche Überprüfung und vieles mehr. Weitere Informationen zur App-Veröffentlichung finden Sie unter [Erstellen eines Partner Center-Kontos durch Entwickler](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/create-partner-center-dev-account), [Übermittlungshandbuch für Entwickler](/office/dev/store/add-in-submission-guide) und [Veröffentlichen von Apps durch Entwickler](https://aka.ms/PublishToTeamsStore).
* Nur Apps von verifizierten Herausgebern können Graph Berechtigungen von Endbenutzern anfordern.
* Keine App kann eine ausführbare Datei herunterladen.
* Apps werden so getestet, dass sie keine Werbung enthalten, werbung für andere Apps
* Apps werden so getestet, dass sie ohne anstößige Sprache, Cyberangriffs-Bots, Spam oder Betrugsinhalte geeignet sind.
* Alle Links in einer App sind funktionsfähig und beziehen sich nur auf das App-Angebot.
* Wir testen und bewerten alle veröffentlichten Teams-Apps regelmäßig im Rahmen von App Store-Integritätsprüfungen.
* Datenschutzrichtlinien und Nutzungsbedingungen, die Teams Apps abdecken, werden vom ISV veröffentlicht
* Die Kontaktdaten des ISV finden Sie im Store-Eintrag und auf den entsprechenden [Publisher Nachweisseiten](/microsoft-365-app-certification/teams/teams-apps).

## <a name="publisher-verification"></a>Publisher Überprüfung

Publisher Überprüfung hilft Administratoren und Endbenutzern, die Authentizität von Anwendungsentwicklern zu verstehen, die sich in die Microsoft Identity Platform integrieren. Wenn ein verifizierter Herausgeber vorhanden ist, bedeutet dies, dass der Herausgeber seine Identität mithilfe seines Microsoft Partner Network (MPN)-Kontos überprüft und dieses MPN-Konto der App-Registrierung zugeordnet hat.

Publisher Überprüfung bietet die folgenden Vorteile:

* Erhöhte Transparenz und Risikoreduzierung für Kunden – diese Funktion hilft Kunden zu verstehen, welche Apps, die in ihren Organisationen verwendet werden, von Entwicklern veröffentlicht werden, denen sie vertrauen.
* Verbessertes Branding – Ein `verified` Signal wird auf der Azure Active Directory Zustimmungsaufforderung, Enterprise Apps-Seite und anderen Benutzeroberflächen angezeigt, die von Endbenutzern und Administratoren verwendet werden.
* Reibungslosere Unternehmensakzeptanz – Administratoren können Benutzerzustimmungsrichtlinien konfigurieren, wobei der Herausgeberüberprüfungsstatus als primäre Richtlinienkriterien gilt.

Darüber hinaus empfiehlt Microsoft den App-Entwicklern, an ihrem Complianceprogramm teilzunehmen, bei dem es sich um einen strengen, zweistufigen Ansatz handelt, um App-Qualität, Sicherheit und Compliance sicherzustellen. Teams Store verfügt über Hunderte von Apps, die über die Erfüllung der bereits detaillierten Validierungsrichtlinien hinausgehen und diese Programme einhalten.

## <a name="microsoft-365-app-compliance-program"></a>Microsoft 365 App-Complianceprogramm

Das Microsoft Compliance-Programm zeigt, dass eine App anhand von Steuerelementen überprüft wird, die von führenden Branchenstandardframeworks abgeleitet wurden, und dass starke Sicherheits- und Compliancepraktiken zum Schutz von Kundendaten vorhanden sind. Das Programm hat zwei Phasen:

* Publisher Nachweis.
* Microsoft 365 Zertifizierung.

### <a name="publisher-attestation"></a>Publisher Nachweis

Der App-Entwickler muss eine Selbstbewertung durchführen, die Fragen enthält, die von Kunden oder IT-Administratoren häufig gestellt werden, wenn sie die Sicherheit und Compliance einer App bewerten. Microsoft veröffentlicht diese Informationen dann zur einfacheren und zeitgerechteren Auswertung. Die Informationen umfassen Details zur Datenverarbeitung, Sicherheit, Compliance und Datenschutz, wenn eine App in einer Organisation aktiviert wird.

Weitere Informationen finden Sie im [Veröffentlichungsnachweishandbuch](/microsoft-365-app-certification/docs/enterprise-app-attestation-guide).

### <a name="microsoft-365-certification"></a>Microsoft 365 Zertifizierung

Die App-Zertifizierung wird durch die Überprüfung und Genehmigung einer umfassenden Bewertung durch einen qualifizierten Analysten erreicht, die sich auf die Sicherheits- und Complianceframeworks, Prozesse und Verfahren einer App konzentriert. Die App wird anhand einer Reihe von Sicherheitskontrollen überprüft, die von führenden Branchenstandardframeworks abgeleitet wurden. Das Zertifikat zeigt, dass starke Sicherheits- und Compliancepraktiken vorhanden sind, um Kundendaten zu schützen, wenn die App in einer Organisation aktiviert wird.

<!--- TBD: Parking some content for later review. Check if this content needs to be published.

We also have a few more quality and security checks for apps. We have launched Microsoft Cloud App Security (MCAS) program for the customer who have E5 or EMS license, where we rate risk for your cloud apps based on regulatory certification, industry standards, and best practices. We are also working on an Apps Quality Score system (launching soon) for all apps on Teams platform, and you will be able to check an app’s quality score quickly on Teams Store.

--->
