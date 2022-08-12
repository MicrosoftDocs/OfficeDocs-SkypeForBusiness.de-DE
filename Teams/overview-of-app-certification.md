---
title: Übersicht über die App-Zertifizierung durch Microsoft
description: Erfahren Sie mehr über das Microsoft 365-App-Compliance-Programm für Sicherheit, Compliance und Datenschutz von Drittanbieter-Apps.
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
ms.openlocfilehash: 9918c1ce81464f2fbe9a0c16bc0373e54858d79b
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299084"
---
# <a name="microsoft-365-app-compliance-program-for-security-compliance-and-privacy-of-third-party-apps"></a>Microsoft 365 App-Compliance-Programm für Sicherheit, Compliance und Datenschutz von Drittanbieter-Apps

Im Rahmen des Microsoft-Compliance-Programms wird eine App anhand von Kontrollelementen überprüft und überwacht, die von führenden Branchenstandard-Frameworks abgeleitet sind. Das Programm zeigt, dass starke Sicherheits- und Compliancepraktiken zum Schutz von Kundendaten angewandt. Das Programm umfasst die folgenden Phasen:

* Herausgeberüberprüfung
* Publisher Nachweis.
* Microsoft 365 Zertifizierung.

## <a name="publisher-verification"></a>Herausgeberüberprüfung

Bevor ein App-Entwickler seine App an Microsoft übermitteln kann, muss sich der Entwickler einer Überprüfung unterziehen. Ein Entwickler überprüft seine Identität mithilfe seines MPN-Kontos (Microsoft Partner Network) und ordnet dieses MPN-Konto der App-Registrierung zu. Dank Herausgeberüberprüfung können Administratoren und Endbenutzer die Authentizität von Anwendungsentwicklern nachvollziehen. Die Publisher-Überprüfung bietet die folgenden Vorteile:

* Erhöhte Transparenz und Risikoreduzierung für Kunden – diese Funktion hilft Kunden zu verstehen, welche Apps, die in ihren Organisationen verwendet werden, von Entwicklern veröffentlicht werden, denen sie vertrauen.
* Verbessertes Branding – Ein `verified` Signal wird auf der Azure Active Directory-Zustimmungsaufforderung, auf der Seite "Unternehmens-Apps" und anderen Benutzeroberflächen angezeigt, die von Endbenutzern und Administratoren verwendet werden.
* Reibungslosere Unternehmensakzeptanz – Administratoren können Benutzerzustimmungsrichtlinien konfigurieren, wobei der Herausgeberüberprüfungsstatus als primäre Richtlinienkriterien gilt.

## <a name="publisher-attestation"></a>Herausgebernachweis

Publisher Nachweis ist die nächste Stufe im App-Complianceprogramm. Apps mit Herausgebernachweis bieten Administratoren Vertrauen in Sicherheits- und Compliance-Maßnahmen im Hinblick auf eine App. Außerdem wird dadurch die Zeit zum Überprüfen dieser Informationen für eine App verkürzt. Der Nachweis spiegelt die Sicherheits-, Datenverarbeitungs- und Compliancepraktiken einer App gegenüber mehr als 80 von [Microsoft Cloud App Security](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/cloud-app-security) identifizierten Risikofaktoren wider. Das Verfahren für den Herausgebernachweis kann gestartet werden, bevor die Herausgeberüberprüfung abgeschlossen ist.

App-Entwickler werden aufgefordert, eine Selbstbewertung durchzuführen, die Häufig gestellte Fragen von Kunden und IT-Administratoren enthält, um die Sicherheit und Compliance einer App zu bewerten. Microsoft veröffentlicht diese Informationen dann zur einfacheren und zeitgerechteren Auswertung. Weitere Informationen finden Sie im [Nachweishandbuch](/microsoft-365-app-certification/docs/enterprise-app-attestation-guide).

Administratoren können auf drei verschiedene Arten schnell nach veröffentlichten bestätigten Apps suchen.

* Wenn Sie weitere Informationen zu einer App sammeln, sehen Sie sich die Details einer bestimmten App über ihren Link unter [Sicherheit und Compliance von Microsoft Teams-Apps](/microsoft-365-app-certification/teams/teams-apps) an. Alternativ können Sie den `Publisher attestation`Link im [Teams Admin Center](https://admin.teams.microsoft.com/) auswählen.

  :::image type="content" source="media/attested-app-tac3.png" alt-text="Wählen Sie im Teams Admin Center den Link zum Herausgebernachweis aus, um Details zum Nachweis einer App anzuzeigen.":::

* Wenn Sie Teams Admin Center die Details einer App auf der Seite **[App verwalten](https://admin.teams.microsoft.com/policies/manage-apps)** überprüfen, sehen Sie sich das Symbol „Herausgebernachweis“ auf dem Banner auf der Detailseite der App an.

  :::image type="content" source="media/attested-app-tac1.png" alt-text="In Teams Admin Center wird Publisher Symbol &quot;Bestätigt&quot; in allen bestätigten Apps angezeigt.":::

* Im Microsoft Teams Admin Center weist ein blaues Häkchen vor dem App-Namen beim [Erteilen von Berechtigungen für die App](app-permissions-admin-center.md) darauf hin, dass es sich entweder um eine vom Herausgeber attestierte App oder um eine Microsoft 365-zertifizierte App handelt.

   :::image type="content" source="media/attested-app-tac2.png" alt-text="Im Microsoft Teams Admin Center weist das blaue Häkchen im Dialogfeld zum Erteilen von Berechtigungen darauf hin, dass für eine App ein Herausgebernachweis vorliegt.":::

Auf der Seite mit den Nachweisdetails für eine nachgewiesene oder zertifizierte App sind die folgenden Details aufgeführt.

:::image type="content" source="media/attested-app-doc-details.png" alt-text="Ausführliche Informationen zu Apps mit Herausgebernachweis.":::

## <a name="microsoft-365-certification"></a>Microsoft 365 Zertifizierung

Die App-Zertifizierung erfolgt durch:

* Überprüfung durch einen qualifizierten Analysten.
* Genehmigung einer umfassenden Bewertung mit Schwerpunkt auf den Frameworks, Prozessen und Verfahren einer App für Sicherheit und Compliance.

Wir überprüfen die App anhand einer Reihe von Sicherheitskontrollen, die von führenden Branchenstandard-Frameworks abgeleitet sind.

Das Zertifikat zeigt die starken Sicherheits- und Compliancepraktiken, die vorhanden sind, um Kundendaten zu schützen, wenn die App in einer Organisation verwendet wird. Weitere Informationen dazu, wie Administratoren und Endbenutzer von der Zertifizierung profitieren, finden Sie unter [Übersicht über das Microsoft 365 App-Complianceprogramm](/microsoft-365-app-certification/docs/enterprise-app-certification-guide).

Administratoren können folgendermaßen schnell nach Microsoft 365-zertifizierten Apps suchen.

* Wenn Sie weitere Informationen zu einer App im Web sammeln, sehen Sie sich das Schildsymbol in der [ Microsoft-Dokumentation zur App an](/microsoft-365-app-certification/teams/teams-apps).

  :::image type="content" source="media/attested-app-doc-details.png" alt-text="Sehen Sie sich die Microsoft 365 Zertifizierungsinformationen im ausführlichen Hilfeartikel zur Sicherheit und Compliance einer App an":::

* Wenn Sie eine Anwendung im [Teams Admin Center](https://admin.teams.microsoft.com/policies/manage-apps) überprüfen, sortieren Sie die Liste der Apps mithilfe der Spalte „Zertifizierung“. Sehen Sie sich das Symbol an, und klicken Sie optional auf den Link, um auf die oben erwähnte App-spezifische Seite zuzugreifen.

  :::image type="content" source="media/m365cert-apps-list1.png" alt-text="Sehen Sie sich den Microsoft 365-Zertifizierungsstatus einer App im Teams Admin Center an." lightbox="media/m365cert-apps-list2.png":::

* Für die Betrachtung der Details einer App sehen Sie sich das Microsoft 365-zertifizierte Symbol im App-Banner an.

  :::image type="content" source="media/m365cert-app-details-banner.png" alt-text="Sehen Sie sich bezüglich der Verwaltung einer bestimmten App im Teams Admin Center die Microsoft 365-Zertifizierungsinformationen im App-Banner an":::

* Im Microsoft Teams Admin Center weist ein blaues Häkchen vor dem App-Namen beim [Erteilen von Berechtigungen für die App](app-permissions-admin-center.md) darauf hin, dass es sich entweder um eine vom Herausgeber attestierte App oder um eine Microsoft 365-zertifizierte App handelt.

   :::image type="content" source="media/attested-app-tac2.png" alt-text="Im Teams Admin Center können Administratoren im Dialogfeld zum Erteilen von Berechtigungen das blaue Kontrollhäkchen aktivieren, um sicherzustellen, dass die App Microsoft 365-zertifiziert ist":::

## <a name="view-security-compliance-and-privacy-information"></a>Anzeigen von Sicherheits-, Compliance- und Datenschutzinformationen

Informationen zu Sicherheit, Datenschutz, Compliance und Verhalten einer bestätigten oder zertifizierten App finden Sie in der [Microsoft-Dokumentation](/microsoft-365-app-certification/teams/teams-apps) und im [Teams Admin Center](https://admin.teams.microsoft.com/policies/manage-apps).

### <a name="microsoft-documentation"></a>Microsoft-Dokumentation

Details zu Sicherheit, Datenschutz, Compliance uvm. für jede App finden Sie in den App-spezifischen Hilfeartikeln, die mit den [Microsoft Teams Apps „Sicherheit“ und „Compliance“](/microsoft-365-app-certification/teams/teams-apps) verknüpft sind.

:::image type="content" source="media/attested-app-doc-details.png" alt-text="Detaillierte Informationen, die für Apps bereitgestellt werden, die das Microsoft Compliance-Programm durchlaufen.":::

### <a name="teams-admin-center"></a>Teams Admin Center

Beim Auswerten einer App können Sie unabhängige Cloud Access Security Brokers (CASB) verwenden, z. B. Microsoft Cloud App Security (MCAS), um Informationen zu Sicherheit und Verhalten einer App zu finden. Das Teams Admin Center enthält Informationen zur Sicherheit und Compliance von MCAS für Microsoft 365 zertifizierte Apps. Lesen Sie diese Informationen auf der Seite mit den App-Details, um zu überprüfen, ob die App Ihren Sicherheitsanforderungen entspricht.

> [!NOTE]
> Dieses Feature steht allen Administratoren zur Verfügung, unabhängig davon, ob Ihre Organisation über eine Lizenz verfügt, die MCAS unterstützt.

So greifen Sie auf MCAS Informationen für eine App zu:

1. Wählen Sie im Teams Admin Center **Teams-Apps** > **[Apps verwalten](https://admin.teams.microsoft.com/policies/manage-apps)** aus.

1. Wählen Sie **"Zertifizierung**" aus, um Apps zu sortieren und alle Microsoft 365 zertifizierten Apps an den Anfang der Tabelle zu verschieben.

1. Wählen Sie eine Microsoft 365 Zertifizierte App aus.

1. Wählen Sie die Registerkarte **"Sicherheit und Compliance** " aus.

   :::image type="content" source="media/mcas.png" alt-text="Screenshot der Registerkarte Teams Admin Center für Sicherheit und Compliance.":::

   Um weitere Details zu den unterstützten Funktionen für die App zu erhalten, wählen Sie die Dropdownliste für jede Kategorie aus.

## <a name="view-privacy-policy-and-terms-of-use-of-an-app"></a>Anzeigen von Datenschutzrichtlinien und Nutzungsbedingungen einer App

Im Microsoft Teams Admin Center enthält jede App-Seite einen Link zu der Datenschutzerklärung und den Nutzungsbedingungen der App.

:::image type="content" source="media/tac-app-tou-privacy-info1.png" alt-text="Über das Teams Admin Center können Administratoren auf den Link zu den Datenschutzrichtlinien und Nutzungsbedingungen für jede App zugreifen." lightbox="media/tac-app-tou-privacy-info2.png":::

## <a name="related-articles"></a>Verwandte Artikel

* [Anzeigen von App-Berechtigungen und Erteilen der Administratorzustimmung](app-permissions-admin-center.md).
