---
title: Verwenden des Microsoft Teams-Besprechungs-Add-Ins in Outlook
author: ChuckEdmonson
ms.author: chucked
manager: serdars
audience: Admin
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams installiert in Outlook ein Add-In, mit dem Benutzer Microsoft Teams-Besprechungen über Outlook planen können.
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 801c4f43e9aafa7fe8331d85b601afd584505164
ms.sourcegitcommit: e5cb24ad166268392e692d3d1b92125646e5d66e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2019
ms.locfileid: "34417443"
---
<a name="use-the-teams-meeting-add-in-in-outlook"></a>Verwenden des Microsoft Teams-Besprechungs-Add-Ins in Outlook
=======================================

Das Microsoft Teams-Besprechungs-Add-In wird für Benutzer, auf deren Windows-PC Microsoft Teams und entweder Office 2013 oder Office 2016 installiert ist, automatisch installiert. Die Benutzer sehen auf dem Menüband „Kalender“ in Outlook das Microsoft Teams-Besprechungs-Add-In. 

![Screenshot des Microsoft Teams-Add-Ins auf dem Outlook-Menüband](media/Teams-add-in-for-Outlook.png)

> [!NOTE]
> Benutzer von Windows 7 müssen das [Update für Universal C Runtime in Windows](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows) installieren, damit das Add-In für die Teams-Besprechung funktioniert.

Wenn Benutzer das Microsoft Teams-Besprechungs-Add-In nicht sehen, weisen Sie sie an, Outlook und Microsoft Teams zu schließen, den Microsoft Teams-Client neu zu starten, sich bei Microsoft Teams anzumelden und den Outlook-Client zu starten (in dieser Reihenfolge).

> [!NOTE]
> Die Schaltfläche "Teams-Besprechung" in Outlook für Mac wird im Menüband von Outlook für Mac angezeigt, wenn in Outlook Produktions-Build 16,20 und höher ausgeführt wird.

## <a name="authentication-requirements"></a>Authentifizierungsanforderungen

Benutzer des Microsoft Teams-Besprechungs-Add-Ins müssen sich mit moderner Authentifizierung bei Microsoft Teams anmelden. Wenn sich Benutzer nicht mit dieser Methode anmelden, können sie zwar den Microsoft Teams-Client verwenden, aber sie können keine Microsoft Teams-Onlinebesprechungen mit dem Outlook-Add-In planen. Dies können Sie mit einer der folgenden Methoden korrigieren:

- Wenn die moderne Authentifizierung für Ihre Organisation nicht konfiguriert ist, sollten Sie sie konfigurieren.
- Wenn die moderne Authentifizierung konfiguriert ist, aber die Benutzer den Vorgang im Dialogfeld abgebrochen haben, weisen Sie die Benutzer an, sich mit mehrstufiger Authentifizierung erneut anzumelden.

Weitere Informationen zum Konfigurieren der Authentifizierung finden Sie unter [Identitätsmodelle und Authentifizierung in Microsoft Teams](identify-models-authentication.md).

## <a name="enable-private-meetings"></a>Aktivieren von privaten Besprechungen

Die Option " **Terminplanung für private Besprechungen zulassen** " muss im Microsoft Teams Admin Center aktiviert sein, damit das Plug-in bereitgestellt wird. Wechseln Sie im Admin Center zu **Besprechungen** > **Besprechungsrichtlinien**, und legen Sie im Abschnitt **Allgemein** **Zeitplanung für private Besprechungen zulassen** auf „Aktiviert“ fest.)

![Screenshot der Einstellungen im Microsoft Teams Admin Center.](media/teams-add-in-for-outlook-image1.png)

Der Microsoft Teams-Client ermittelt, ob die Benutzer die 32-Bit- oder 64-Bit-Version benötigen, und installiert dann das richtige Add-In.

> [!NOTE]
> Möglicherweise müssen die Benutzer Outlook nach einer Installation oder einem Upgrade von Microsoft Teams neu starten, um das aktuelle Add-In zu erhalten.

## <a name="other-considerations"></a>Andere Überlegungen

Die Funktionen des Microsoft Teams-Besprechungs-Add-Ins werden noch weiterentwickelt. Beachten Sie daher Folgendes:
- Polling steht noch nicht zur Verfügung.
- Das Whiteboard beginnt mit dem Rollout.
- Besprechungsoptionen sind zurzeit nicht verfügbar.
- Sie können zurzeit nur Personen aus Ihrer Firma einladen, da die Teilnahme externer Benutzer an Besprechungen noch nicht möglich ist.
- Das Add-In ist für geplante Besprechungen mit bestimmten Teilnehmern gedacht, nicht für Besprechungen in einem Kanal. Kanalbesprechungen müssen in Microsoft Teams geplant werden. Zurzeit ist das Microsoft Teams-Besprechungs-Add-In in Outlook nur für Windows-Benutzer verfügbar, aber die Unterstützung für Mac wird noch hinzugefügt.
- Das Add-In funktioniert nicht, wenn sich im Netzwerkpfad zwischen dem PC des Benutzers und den Microsoft Teams-Diensten ein Authentifizierungsproxy befindet.
- Das Add-In wird schrittweise bereitgestellt und steht möglicherweise noch nicht für Ihre Organisation zur Verfügung.

## <a name="troubleshooting"></a>Problembehandlung

Wenn Sie das Add-In für Teams-Besprechungen für Outlook nicht installieren können, versuchen Sie diese Schritte zur Problembehandlung.

- Stellen Sie sicher, dass alle verfügbaren Updates für den Outlook-Desktopclient angewendet wurden. 
- Starten Sie den Teams-Desktopclient neu.
- Melden Sie sich ab, und melden Sie sich dann wieder beim Teams-Desktopclient an.
- Starten Sie den Outlook-Desktopclient neu. (Stellen Sie sicher, dass Outlook nicht im Admin-Modus ausgeführt wird.)
- Stellen Sie sicher, dass der Name des angemeldeten Benutzerkontos keine Leerzeichen enthält. (Dies ist ein bekanntes Problem, das in einem zukünftigen Update behoben wird.)
- Stellen Sie sicher, dass Single Sign-On (SSO) aktiviert ist.

Eine allgemeine Anleitung zum Deaktivieren von Add-Ins finden Sie unter [Anzeigen, Verwalten und Installieren von Add-Ins in Office-Programmen](https://support.office.com/article/View-manage-and-install-add-ins-in-Office-programs-16278816-1948-4028-91E5-76DCA5380F8D).

Weitere Informationen zu [Besprechungen und Anrufen in Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

