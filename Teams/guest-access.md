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
ms.openlocfilehash: cab51fd9cf0a81c849a0baf379150ccb2e08d818
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030281"
---
# <a name="guest-access-in-microsoft-teams"></a>Gastzugriff in Microsoft Teams

Mit Gastzugriff können Sie den Zugriff auf Teams, Dokumente in Kanälen, Ressourcen, Chats und Anwendungen für Personen außerhalb Ihrer Organisation unter Beibehaltung der Kontrolle über Ihre Unternehmensdaten bereitstellen.

Ein Gast ist kein Mitarbeiter, Schüler/Student oder Mitglied Ihrer Organisation Er verfügt über kein Geschäfts-, Schul- oder Unikonto bei Ihrer Organisation. Gäste können beispielsweise Partner, Hersteller, Lieferanten oder Berater sein. Jede Person, die nicht Teil Ihrer Organisation ist, kann als Gast in Teams hinzugefügt werden. Das bedeutet, dass jeder Benutzer mit einem Unternehmenskonto (also einem Azure Active Directory-Konto) oder einem Consumer-e-Mail-Konto (mit Outlook.com, gmail.com oder anderen) als Gast in Teams teilnehmen kann, mit Zugriff auf Teams und Kanal Erlebnisse.

Als Team-Administrator steuern Sie, [welche Funktionen Gäste in Teams verwenden können (und können)](manage-guests.md). Gäste in Teams unterliegen dem gleichen Compliance-und Überwachungs Schutz wie die restlichen Microsoft 365 und können in Azure AD verwaltet werden. Gastzugriff unterliegt Azure AD- und Microsoft 365- oder Office 365-Dienstbegrenzungen.

Die Gastumgebung hat Beschränkungen, die beabsichtigt sind. Eine vollständige Liste dessen, was ein Gast in Teams tun kann und was nicht, finden Sie unter [Vergleich der Teammitglieder und Gast Funktionen](guest-experience.md#comparison-of-team-member-and-guest-capabilities).

> [!IMPORTANT]
> Gastbenutzer folgen den organisationsweiten Einstellungen in Teams für den Upgrade-Modus. Dies kann nicht geändert werden.

Wenn Sie den externen Zugriff (Partnerverbund) mit Gastzugriff vergleichen möchten (und entscheiden, welchen Sie verwenden sollten), lesen Sie [Kommunizieren mit Benutzern aus anderen Organisationen in Teams](communicate-with-users-from-other-organizations.md).

## <a name="set-up-guest-access"></a>Einrichten des Gastzugriffs

Für Gastzugriff in Teams müssen andere Einstellungen in Microsoft 365, einschließlich Einstellungen in Azure AD, Microsoft 365-Gruppen und SharePoint, konfiguriert werden. Wenn Sie mit der Einladung von Gästen zu Teams beginnen möchten, lesen Sie eine der folgenden Themen:

- Informationen zum Konfigurieren des Gastzugriffs für Teams zur allgemeinen Verwendung finden Sie unter [Zusammenarbeit mit Gästen in einem Team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).
- Informationen zur Zusammenarbeit mit einer Partnerorganisation, die Azure Active Directory verwendet und es Gästen ermöglicht, sich selbst für Team Zugriff zu registrieren, finden Sie unter [Erstellen eines B2B-Extranets mit verwalteten Gästen](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet).

Gastzugriff in Teams ist eine organisationsweite Einstellung, die standardmäßig deaktiviert ist. Mithilfe von [Vertraulichkeits Beschriftungen](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)können Sie den Gastzugriff auf einzelne Teams steuern.

## <a name="how-a-guest-becomes-a-member-of-a-team"></a>So wird ein Gast Mitglied eines Teams

1. Ein Teambesitzer oder ein Microsoft 365-Administrator [Fügt einen Gast zu einem Team hinzu](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).
2. Der Gast empfängt eine Willkommens-E-Mail vom Teambesitzer mit Informationen über das Team und darüber, was ihn als Mitglied nun erwartet.
3. Der Gast akzeptiert die Einladung.
  Gastbenutzer, die über ein Firmen-oder Schulkonto in Azure Active Directory verfügen, können die Einladung annehmen und sich direkt authentifizieren. Anderen Benutzern wird ein einmaliger Passcode gesendet, um deren Identität zu überprüfen ([eine einmalige Kennungs Authentifizierung](https://docs.microsoft.com/azure/active-directory/external-identities/one-time-passcode) erforderlich).
4. Nach dem Akzeptieren der Einladung kann der Gast [an Teams und Kanälen teilnehmen](https://support.office.com/article/df38ae23-8f85-46d3-b071-cb11b9de5499), Kanalnachrichten empfangen und darauf reagieren, [auf Dateien in Kanälen zugreifen](https://support.office.com/article/access-files-in-channels-c593c78a-27c4-4661-a598-682baa30ca7e), an Besprechungen und Chats teilnehmen, an Dokumenten zusammenarbeiten und mehr. 

In Teams sind Gäste eindeutig zu erkennen. Der Name eines Gastbenutzers enthält die Bezeichnung **(Gast)** , und in einem Kanal wird durch ein Symbol auf eine Gastteilnahme im Team hingewiesen. Weitere Details finden Sie unter [Gastfunktionalität](guest-experience.md).
  
Gäste können das Team jederzeit von Teams aus verlassen. Einzelheiten finden Sie unter [Wie verlasse ich ein Team?](https://support.office.com/article/leave-a-team-e481005d-3ec6-4694-b300-375472ba4076)

> [!NOTE]
> Wenn Sie das Team verlassen, wird das Gastkonto nicht aus dem Verzeichnis Ihrer Organisation entfernt. Dies muss von einem globalen Microsoft 365-Administrator oder einem Azure AD-Administrator ausgeführt werden.

## <a name="licensing-for-guest-access"></a>Lizenzierung für Gastzugriff

Der Gastzugriff ist in allen Microsoft 365 Business Standard-, Microsoft 365 Enterprise-und Microsoft 365 Education-Abonnements enthalten. Es ist keine zusätzliche Microsoft 365-Lizenz erforderlich. Die Anzahl von Gästen, die Sie hinzufügen können, ist in Teams nicht beschränkt. Die Gesamtzahl der Gäste, die Ihrem Mandanten hinzugefügt werden können, kann jedoch durch die kostenpflichtigen Funktionen von Azure AD eingeschränkt sein. Weitere Informationen finden Sie unter [Abrechnungsmodell für Azure AD-externe Identitäten](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).

> [!NOTE]
> Benutzer in Ihrer Organisation, die nur über eigenständige Microsoft 365-Abonnement Pläne verfügen, wie etwa Exchange Online Plan 2, können nicht als Gäste in Ihrer Organisation eingeladen werden, da diese Benutzer von Teams zur gleichen Organisation gehören. Damit diese Benutzer Teams verwenden können, muss ihnen ein Abonnement für Microsoft 365 Business Standard, Office 365 Enterprise oder Office 365 Education zugewiesen werden. 

## <a name="guest-access-reviews"></a>Bewertungen für Gastzugriff

Mit Azure AD können Sie eine Zugriffsüberprüfung für Mitglieder einer Gruppe oder Benutzer, die einer Anwendung zugewiesen sind, erstellen. Das Erstellen regelmäßiger Zugriffsüberprüfungen kann Zeit sparen. Wenn Sie Benutzer, die Zugriff auf eine Anwendung, ein Team oder Mitglieder einer Gruppe haben, regelmäßig überprüfen müssen, können Sie die Häufigkeit dieser Bewertungen definieren. 

Sie können selbst eine Überprüfung des Gastzugriffs durchführen, Gäste bitten, ihre eigene Mitgliedschaft zu überprüfen oder den Besitzer einer Anwendung bzw. einen Entscheidungsträger bitten, die Zugriffsüberprüfung durchzuführen. Verwenden Sie das Azure-Portal, um Bewertungen von Gastzugriffen durchzuführen. Weitere Informationen finden Sie unter [Verwalten des Gastzugriffs mit Azure AD-Zugriffsüberprüfungen](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews).

## <a name="related-topics"></a>Verwandte Themen

[Zusammenarbeiten mit Personen außerhalb Ihrer Organisation](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)

[Sperren von Gastbenutzern aus einer bestimmten Microsoft 365-Gruppe oder einem Microsoft Teams-Team](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Erstellen einer sicheren Gast Freigabe Umgebung](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

[Kontakt mit dem Support für Geschäftsprodukte aufnehmen – Administratorhilfe](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[Konfigurieren von Teams mit drei Schutzebenen](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
