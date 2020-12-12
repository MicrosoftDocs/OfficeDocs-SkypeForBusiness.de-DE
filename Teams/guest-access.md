---
title: Gastzugriff in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: rafarhi
audience: admin
search.appverid: MET150
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
appliesto:
- Microsoft Teams
description: Gastzugriff in Microsoft Teams ermöglicht Teams in Ihrer Organisation, mit Personen außerhalb Ihrer Organisation zusammenzuarbeiten, indem ihnen Zugriff auf Teams und Kanäle gewährt wird.
ms.openlocfilehash: 09090cc2061c3d138af2b3092e987293255a1134
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662040"
---
# <a name="guest-access-in-microsoft-teams"></a>Gastzugriff in Microsoft Teams

Mit Gastzugriff können Sie Personen, die nicht Ihrer Organisation angehören, Zugriff auf Teams, Dokumente in Kanälen, Ressourcen, Chats und Anwendungen gewähren und gleichzeitig die vollständige Kontrolle über Ihre eigenen Unternehmensdaten behalten.

Ein Gast ist kein Mitarbeiter, Schüler/Student oder Mitglied Ihrer Organisation Er verfügt über kein Geschäfts-, Schul- oder Unikonto bei Ihrer Organisation. Gäste können beispielsweise Partner, Hersteller, Lieferanten oder Berater sein. Jede Person, die nicht Teil Ihrer Organisation ist, kann als Gast in Teams hinzugefügt werden. Dies bedeutet, dass jeder Benutzer mit einem Business-Konto (d. h. ein Azure Active Directory-Konto) oder E-Mail-Heimanwender-Konto (mit Outlook.com, Gmail.com oder einer sonstigen Adresse) als Gast in Microsoft Teams teilnehmen kann – mit vollständigem Zugriff auf Team- und Kanalfunktionen.

Für alle Gäste in Microsoft Teams gelten dieselben Compliance- und Überwachungsmaßnahmen wie überall in Microsoft 365, und die Gäste können in Azure AD verwaltet werden. Der Gastzugriff unterliegt Azure AD- und Microsoft 365- oder Office 365-Dienstbegrenzungen.

Die Gastumgebung hat Beschränkungen, die beabsichtigt sind. Eine vollständige Liste dessen, was ein Gast in Microsoft Teams tun kann und was nicht, finden Sie unter [Vergleich der Funktionen für Teammitglieder und Gäste](guest-experience.md#comparison-of-team-member-and-guest-capabilities).

> [!IMPORTANT]
> Die Gäste folgen den organisationsweiten Teams-Einstellungen für den Koexistenz-Aktualisierungsmodus. Dies kann nicht geändert werden.

Informationen zum Einrichten des Gastzugriffs finden Sie unter [Zusammenarbeit mit Gästen in einem Team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team). 

Wenn Sie den externen Zugriff (Partnerverbund) mit Gastzugriff vergleichen möchten (und entscheiden, welchen Sie verwenden sollten), lesen Sie [Kommunizieren mit Benutzern aus anderen Organisationen in Teams](communicate-with-users-from-other-organizations.md).

## <a name="set-up-guest-access"></a>Einrichten des Gastzugriffs

Der Gastzugriff in Microsoft Teams erfordert das Konfigurieren anderer Einstellungen in Microsoft 365, darunter Einstellungen in Azure AD, Microsoft 365-Gruppen und SharePoint. Wenn Sie mit der Einladung von Gästen zu Microsoft Teams beginnen möchten, lesen Sie einen der folgenden Beiträge:

- Informationen zum Konfigurieren des Gastzugriffs für Microsoft Teams für die allgemeine Nutzung finden Sie unter [Zusammenarbeit mit Gästen in einem Team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).
- Wenn Sie mit einer Partnerorganisation zusammenarbeiten möchten, die Azure Active Directory verwendet, und es Gästen gestatten möchten, sich selbst für den Zugang zu Teams zu registrieren, lesen Sie [Erstellen eines B2B-Extranets mit verwalteten Gästen](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet).

Der Gastzugriff ist eine organisationsweite Einstellung in Microsoft Teams, die standardmäßig deaktiviert ist. Sie können den Gastzugriff auf einzelne Teams mithilfe von [Vertraulichkeitsbezeichnungen](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) steuern.

## <a name="how-a-guest-becomes-a-member-of-a-team"></a>So wird ein Gast Mitglied eines Teams

1. Ein Teambesitzer oder ein Microsoft 365-Administrator [fügt einen Gast zu einem Team hinzu](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).
2. Der Gast empfängt eine Willkommens-E-Mail vom Teambesitzer mit Informationen über das Team und darüber, was ihn als Mitglied nun erwartet.
3. Der Gast akzeptiert die Einladung.
  Gäste, die über ein Firmen-oder Schulkonto in Azure Active Directory verfügen, können die Einladung annehmen und sich direkt authentifizieren. Andere Benutzer erhalten einen einmaligen Zugangscode, um ihre Identität zu überprüfen ([Authentifizierung durch Einmalkennung](https://docs.microsoft.com/azure/active-directory/external-identities/one-time-passcode) erforderlich).
4. Nach dem Akzeptieren der Einladung kann der Gast [an Teams und Kanälen teilnehmen](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499), Kanalnachrichten empfangen und darauf reagieren, [auf Dateien in Kanälen zugreifen](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e), an Besprechungen und Chats teilnehmen, an Dokumenten zusammenarbeiten und mehr. 

In Teams sind Gäste eindeutig zu erkennen. Der Name eines Gasts enthält das Label **(Guest)**, und ein Kanal enthält ein Symbol, um anzugeben, dass Gäste im Team anwesend sind. Weitere Details finden Sie unter [Gastfunktionalität](guest-experience.md).
  
Gäste können das Team jederzeit von Teams aus verlassen. Einzelheiten finden Sie unter [Wie verlasse ich ein Team?](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)

> [!NOTE]
> Wenn ein Gast ein Team verlässt, wird das entsprechende Gastkonto nicht aus dem Verzeichnis Ihrer Organisation entfernt. Dies muss durch einen globalen Microsoft 365-Administrator oder einen Azure AD-Administrator erfolgen.

## <a name="licensing-for-guest-access"></a>Lizenzierung für Gastzugriff

Der Gastzugang ist in allen Abonnements von Microsoft 365 Business Standard, Microsoft 365 Enterprise und Microsoft 365 Education enthalten. Eine zusätzliche Microsoft 365-Lizenz ist nicht erforderlich. Die Anzahl von Gästen, die Sie hinzufügen können, ist in Teams nicht beschränkt. Die Gesamtzahl der Gäste, die Ihrem Mandanten hinzugefügt werden können, kann jedoch durch die kostenpflichtigen Funktionen von Azure AD eingeschränkt sein. Weitere Informationen finden Sie unter [Abrechnungsmodell für Azure AD for External Identities](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).

> [!NOTE]
> Benutzer in Ihrer Organisation, die nur über eigenständige Microsoft 365-Abonnementpläne verfügen, z. B. Exchange Online Plan 2, können nicht als Gäste zu Ihrer Organisation eingeladen werden, da Microsoft Teams diese Benutzer als derselben Organisation angehörig betrachtet. Damit diese Benutzer Microsoft Teams verwenden können, muss ihnen ein Abonnement für Microsoft 365 Business Standard, Office 365 Enterprise oder Office 365 Education zugewiesen werden. 

## <a name="guest-access-reviews"></a>Gast-Zugriffsüberprüfungen

Mit Azure AD können Sie eine Zugriffsüberprüfung für Mitglieder einer Gruppe oder Benutzer, die einer Anwendung zugewiesen sind, erstellen. Das Erstellen regelmäßiger Zugriffsüberprüfungen kann Zeit sparen. Wenn Sie Benutzer, die Zugriff auf eine Anwendung oder ein Team haben oder Mitglied einer Gruppe sind, routinemäßig überprüfen müssen, können Sie die Häufigkeit dieser Überprüfungen definieren. 

Sie können selbst eine Überprüfung des Gastzugriffs durchführen, Gäste bitten, ihre eigene Mitgliedschaft zu überprüfen oder den Besitzer einer Anwendung bzw. einen Entscheidungsträger bitten, die Zugriffsüberprüfung durchzuführen. Verwenden Sie das Azure-Portal, um Überprüfungen des Gastzugriffs durchzuführen. Weitere Informationen finden Sie unter [Verwalten des Gastzugriffs mit Azure AD-Zugriffsüberprüfungen](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews).

## <a name="related-topics"></a>Verwandte Themen

[Zusammenarbeit mit Personen außerhalb Ihrer Organisation](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Sperren von Gästen aus einer bestimmten Microsoft 365-Gruppe oder einem Microsoft Teams-Team](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Erstellen einer sicheren Umgebung für die Gastfreigabe](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

[Kontakt mit dem Support für Geschäftsprodukte aufnehmen – Administratorhilfe](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[Konfigurieren von Microsoft Teams mit drei Schutzebenen](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
