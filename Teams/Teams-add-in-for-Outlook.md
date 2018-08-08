---
title: Verwenden des Microsoft Teams-Besprechungs-Add-Ins in Outlook
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
localization_priority: Priority
description: Microsoft Teams installiert in Outlook ein Add-In, mit dem Benutzer Microsoft Teams-Besprechungen über Outlook planen können.
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 76b1dcb9c7f34780d4e49611d6e97f2ca890b329
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20987128"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>Verwenden des Microsoft Teams-Besprechungs-Add-Ins in Outlook
=======================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Das Microsoft Teams-Besprechungs-Add-In wird für Benutzer, auf deren Windows-PC Microsoft Teams und entweder Office 2013 oder Office 2016 installiert ist, automatisch installiert. Die Benutzer sehen auf dem Menüband „Kalender“ in Outlook das Microsoft Teams-Besprechungs-Add-In. 

![Screenshot des Microsoft Teams-Add-Ins auf dem Outlook-Menüband](media/Teams-add-in-for-Outlook.png)

Wenn Benutzer das Microsoft Teams-Besprechungs-Add-In nicht sehen, weisen Sie sie an, Outlook und Microsoft Teams zu schließen, den Microsoft Teams-Client neu zu starten, sich bei Microsoft Teams anzumelden und den Outlook-Client zu starten (in dieser Reihenfolge).

> [!NOTE]
> Das Microsoft Teams-Besprechungs-Add-In für Outlook ist für Mac-Benutzer zurzeit nicht verfügbar.

## <a name="authentication-requirements"></a>Authentifizierungsanforderungen

Benutzer des Microsoft Teams-Besprechungs-Add-Ins müssen sich mit moderner Authentifizierung bei Microsoft Teams anmelden. Wenn sich Benutzer nicht mit dieser Methode anmelden, können sie zwar den Microsoft Teams-Client verwenden, aber sie können keine Microsoft Teams-Onlinebesprechungen mit dem Outlook-Add-In planen. Dies können Sie mit einer der folgenden Methoden korrigieren:

- Wenn die moderne Authentifizierung für Ihre Organisation nicht konfiguriert ist, sollten Sie sie konfigurieren.
- Wenn die moderne Authentifizierung konfiguriert ist, aber die Benutzer den Vorgang im Dialogfeld abgebrochen haben, weisen Sie die Benutzer an, sich mit mehrstufiger Authentifizierung erneut anzumelden.

Weitere Informationen zum Konfigurieren der Authentifizierung finden Sie unter [Identitätsmodelle und Authentifizierung in Microsoft Teams](identify-models-authentication.md).

## <a name="enable-private-meetings"></a>Aktivieren von privaten Besprechungen

Die Option „Allow scheduling for private meetings“ (Planen von privaten Besprechungen zulassen) muss im [Office 365 Admin Center](https://portal.office.com/adminportal/home) aktiviert sein, damit das Plug-In bereitgestellt wird.

![Screenshot der Einstellungen im Abschnitt „Anrufe und Besprechungen“ im Office 365 Admin Center](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

Der Microsoft Teams-Client ermittelt, ob die Benutzer die 32-Bit- oder 64-Bit-Version benötigen, und installiert dann das richtige Add-In.

> [!NOTE]
> Möglicherweise müssen die Benutzer Outlook nach einer Installation oder einem Upgrade von Microsoft Teams neu starten, um das aktuelle Add-In zu erhalten.

## <a name="other-considerations"></a>Weitere Überlegungen

Die Funktionen des Microsoft Teams-Besprechungs-Add-Ins werden noch weiterentwickelt. Beachten Sie daher Folgendes:
- Einige Funktionen von Onlinebesprechungen, beispielsweise Aufzeichnung, Umfragen und Whiteboards, sind noch nicht verfügbar.
- Besprechungsoptionen sind zurzeit nicht verfügbar.
- Sie können zurzeit nur Personen aus Ihrer Firma einladen, da die Teilnahme externer Benutzer an Besprechungen noch nicht möglich ist.
- Das Add-In ist für geplante Besprechungen mit bestimmten Teilnehmern gedacht, nicht für Besprechungen in einem Kanal. Kanalbesprechungen müssen in Microsoft Teams geplant werden. Zurzeit ist das Microsoft Teams-Besprechungs-Add-In in Outlook nur für Windows-Benutzer verfügbar, aber die Unterstützung für Mac wird noch hinzugefügt.
- Das Add-In funktioniert nicht, wenn sich im Netzwerkpfad zwischen dem PC des Benutzers und den Microsoft Teams-Diensten ein Authentifizierungsproxy befindet.
- Das Add-in wird schrittweise eingeführt werden und möglicherweise nicht für Ihre Organisation noch verfügbar sind.

## <a name="troubleshooting"></a>Problembehandlung

Wenn Sie die Besprechung Teams add-in für Outlook installieren nicht, versuchen Sie diese Schritte zur Problembehandlung.

- Starten Sie den Desktopclient Teams neu.
- Melden Sie sich ab und dann wieder anmelden auf dem Desktopclient Teams.
- Starten Sie den desktop Outlook-Client neu. (Stellen Sie sicher, dass Outlook nicht im Admin-Modus ausgeführt wird.)
- Stellen Sie sicher, dass der Kontoname angemeldeten Benutzer keine Leerzeichen enthalten. (Dies ist ein bekanntes Problem und wird in einem zukünftigen Update behoben werden.)
- Stellen Sie sicher, dass einmaliges Anmelden (SSO) aktiviert ist.

Eine allgemeine Anleitung zum Deaktivieren von Add-Ins finden Sie unter [Anzeigen, Verwalten und Installieren von Add-Ins in Office-Programmen](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).

Weitere Informationen zu [Besprechungen und Anrufen in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

