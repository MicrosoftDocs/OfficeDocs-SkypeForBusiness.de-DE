---
title: Verwalten der kostenlosen Office 365 G1-Testversion für US-Regierungsbehörden
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: Admin
ms.reviewer: aarimm
ms.service: msteams
search.appverid: MET150
ms.localizationpriority: high
description: 'US-Regierungsbehörden: Wenn Sie Microsoft Teams noch nicht verwenden, es aber eilig benötigen, stellen Sie Ihren Benutzern, die als Reaktion auf den Ausbruch von COVID-19 (Coronavirus) remote oder von zu Hause aus arbeiten müssen (WFH), die Office 365 G1-Testversion bereit.'
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: c1208636547258524816ca77e57ddc3b83646144
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618471"
---
# <a name="manage-the-office-365-g1-trial-for-us-government"></a>Verwalten der Office 365 G1-Testversion für US-Regierungsbehörden 

Ab dem 1. Juli 2020 steht die Office 365 E1-Testversion nicht länger zur Verfügung. Wenn Sie Benutzer für Microsoft Teams lizenzieren müssen, lesen Sie die [Microsoft Teams-Dienstbeschreibung](/office365/servicedescriptions/teams-service-description), um eine Liste der kostenpflichtigen Abonnements mit Teams zu finden. 

Verwenden Sie die Anleitung in diesem Artikel, um Ihre bestehenden Office 365 G1-Testversionen zu verwalten, einschließlich der [Aktualisierung auf ein kostenpflichtiges Abonnement](#upgrade-users-from-the-office-365-g1-trial-license). Um mehr zu erfahren, lesen Sie [Microsoft 365 Government-Pläne](https://www.microsoft.com/microsoft-365/government/compare-office-365-government-plans) und [in der gcc-Cloud verfügbare Microsoft Teams-Funktionen](plan-for-government-gcc.md).

Versäumen Sie nicht die Vielzahl unserer Anleitungen für die [Unterstützung von Remotemitarbeitern mit Teams](support-remote-work-with-teams.md).

## <a name="manage-the-g1-trial"></a>Verwalten der G1-Testversion

Sobald Sie die Office 365 G1-Testversion aktiviert haben, schalten Sie die Lizenz für alle Anwendungen frei, die sie benötigen. Weitere Informationen hierzu finden Sie unter [Verwalten des Benutzerzugriffs auf Microsoft Teams](user-access.md).

Sobald Sie die G1-Testversion für die Benutzer, die sie benötigen, freigeschaltet haben, können Sie diese Benutzer genauso wie Benutzer verwalten, die eine kostenpflichtige Lizenz verwenden. Weitere Informationen finden Sie unter [Verwalten von Microsoft Teams-Einstellungen in Ihrer Organisation](enable-features-office-365.md).

### <a name="upgrade-users-from-the-office-365-g1-trial-license"></a>Upgraden von Benutzern mit Office 365 G1-Testlizenz

So führen Sie ein Upgrade von Benutzern mit G1-Testlizenz auf ein bezahltes Abonnement aus

1.  Kaufen Sie ein Abonnement, das Microsoft Teams enthält.

2.  Entfernen Sie das Office 365 G1-Testabonnement des Benutzers.

3.  Weisen Sie die neu erworbene Lizenz zu.

Weitere Informationen finden Sie unter [Teams für US-Regierungsbehörden](expand-teams-across-your-org/teams-for-government-landing-page.md).

> [!NOTE]
> Wenn die G1-Testlizenz abläuft und kein unmittelbares Upgrade auf ein Abonnement mit Teams für einen Benutzer erfolgt, werden die Benutzerdaten nicht entfernt. Der Benutzer bleibt weiterhin in Azure Active Directory und alle Daten innerhalb von Teams werden beibehalten. Sobald dem Benutzer eine neue Lizenz zugewiesen wird, um die Teams-Funktionen wieder zu aktivieren, sind alle Inhalte immer noch vorhanden.
> 
### <a name="remove-an-office-365-g1-trial-license"></a>Entfernen einer Office 365 G1-Testlizenz

  - Wenn Sie diese Lizenz über PowerShell entfernen möchten, ziehen Sie [Entfernen von Lizenzen von Benutzerkonten mit Office 365 PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell) zurate.

  - Wenn Sie diese Lizenz über das Verwaltungsportal entfernen möchten, lesen Sie [Löschen eines Benutzers aus Ihrer Organisation](/microsoft-365/admin/add-users/delete-a-user).

## <a name="related-topics"></a>Verwandte Themen

[Verwalten des Benutzerzugriffs auf Teams](user-access.md)

[Verwalten von Teams-Einstellungen in Ihrer Organisation](enable-features-office-365.md)
