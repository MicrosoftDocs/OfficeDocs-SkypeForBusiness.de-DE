---
title: Verwalten von Tags in Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: acolonna, salu
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie die Verwendung von Tags in Microsoft Teams in Ihrer Organisation verwalten können.
ms.openlocfilehash: 9d9ba4584572ad1e1707c250ee92c49e9aaec7fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831235"
---
# <a name="manage-tags-in-microsoft-teams"></a>Verwalten von Tags in Microsoft Teams

> [!NOTE]
> Eines der in diesem Artikel erläuterten Features, das **Tagging** nach Schicht, wurde noch nicht veröffentlicht. Es wurde angekündigt und wird in Kürze folgen. Wenn Sie ein Administrator sind, können Sie herausfinden, wann dieses Feature im Nachrichtencenter (im [Microsoft 365 Admin Center) veröffentlicht wird.](https://portal.office.com/adminportal/home) Weitere Informationen zu bevorstehenden Features von Teams finden Sie in der [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).

## <a name="overview"></a>Übersicht

Tags in Microsoft Teams ermöglichen Benutzern eine schnelle und einfache Verbindung mit einer Teilmenge von Personen in einem Team. Sie können benutzerdefinierte Tags erstellen und zuweisen, um Personen anhand von Attributen wie Rolle, Projekt, Qualifikation oder Ort zu kategorisieren. Oder Kategorien können Personen anhand ihrer Zeitplan- und Schichtinformationen in der App ["Schichten"](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts) (in Kürze verfügbar) automatisch zugewiesen werden. Nachdem ein Tag einem oder mehreren Teammitgliedern hinzugefügt wurde, kann sie in @mentions von jedem im Team in einem Kanalbeitrag verwendet werden oder eine Unterhaltung nur mit den Personen beginnen, denen diese Markierung zugewiesen ist.

Wie bereits erwähnt, gibt es in Teams zwei Arten von Tags.

- **Benutzerdefinierte Tags:** Teambesitzer und Teammitglieder (wenn das Feature für sie aktiviert ist) können Personen Tags manuell erstellen und zuweisen. So erreichen beispielsweise die Markierungen "Designer" oder "Radierg 2016" diese Personengruppen in einem Team, ohne deren Namen eingeben zu müssen.
- **Tagging nach Schicht** (in Kürze verfügbar): Mit diesem Feature werden Personen automatisch Tags zugewiesen, die ihrem Zeitplan und dem Gruppennamen der Schicht in der App "Schichten" [](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) in Teams entsprechen. Beispielsweise erreicht das Tag "EngineerOnCall" alle Entwickler, die in Schichten geplant sind, um zu dem Zeitpunkt zu arbeiten, zu dem das Tag in einem Chat oder Kanalbeitrag verwendet wird. Mit dem Tagging nach Schicht macht Teams den Rat nicht mehr, den Namen der Mitarbeiter in der Schicht zu kennen, wenn Benutzer Informationen schnell informieren müssen. Das Tagging nach Schicht kann auch von großen Personalverwaltungssystemen wie JDA, Kroneos und AMiON unterstützt werden, indem diese mit Schichten in Teams integriert werden. Weitere Informationen zum Einrichten dieses Features finden Sie unter ["Einrichten von Tags nach Schicht".](#set-up-tagging-by-shift-coming-soon)

> [!NOTE]
> Tags werden in privaten Kanälen noch nicht unterstützt. Tags sind in Organisationen der US Government Community Cloud (GCC), GCC High oder Department of Defense (DoD) noch nicht verfügbar. 

## <a name="how-tags-work"></a>Funktionsweise von Tags

Eine Markierung kann einer Person in einem bestimmten Team manuell hinzugefügt oder automatisch zugewiesen werden. Sie kann dann in der @mentions in  einem Chat oder in einem Beitrag in einem beliebigen Standardkanal des Teams verwendet werden. Nachfolgend finden Sie einige Beispiele für die Verwendung von Tags in Teams:

- Ein Manager eines Ladens veröffentlicht eine Ankündigung in einem Kanal, um alle Cashiers zu benachrichtigen.
- Ein Krankenhausadministrator sendet eine Nachricht an alle Radiergärte in einem Kanal.
- Ein Marketingmanager beginnt einen Gruppenchat mit allen Designern.
- Eine Krankenschwester sendet eine Nachricht an alle Anrufer. (in Kürze verfügbar)
- Ein Systemtechniker veröffentlicht eine Ankündigung in einem Kanal, um alle Schichtfeldtechniker zu benachrichtigen. (in Kürze verfügbar)

Wenn ein Tag in @mentioned Kanal unterhaltung angezeigt wird, werden die dem Tag zugeordneten Teammitglieder wie alle anderen Mitglieder @mention.

## <a name="manage-custom-tags-for-your-organization"></a>Verwalten von benutzerdefinierten Tags für Ihre Organisation

Als Administrator können Sie im Microsoft Teams Admin Center steuern, wie Tags organisationsweit verwendet werden. Derzeit können Sie PowerShell nicht zum Verwalten von Tags verwenden.

![Screenshot der Einstellungen für das Tagging im Microsoft Teams Admin Center](media/manage-tags-admin-settings.png)

Ein Team kann bis zu 100 Tags enthalten, bis zu 100 Teammitglieder können einem Tag zugewiesen werden, und einem einzelnen Benutzer können bis zu 25 Tags zugewiesen werden. 

### <a name="set-who-can-add-custom-tags"></a>Festlegen, wer benutzerdefinierte Tags hinzufügen kann

Teambesitzer können standardmäßig benutzerdefinierte Tags hinzufügen. Sie können diese Einstellung ändern, damit Teambesitzer und Teammitglieder Kategorien erstellen, bearbeiten, löschen und verwalten können, oder Sie können Tags für Ihre Organisation deaktivieren.

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Organisationsweite Einstellungen** > **Teams-Einstellungen**.
2. Wählen **Sie unter "Kategorien"** neben **"Tags werden verwaltet von"** eine der folgenden Optionen aus:

    - **Teambesitzer und -mitglieder:** Zulassen, dass Teambesitzer und Mitglieder Kategorien verwalten.
    - **Teambesitzer:** Zulassen, dass Teambesitzer Kategorien verwalten.
    - **Deaktiviert**: Deaktivieren von Tags.

### <a name="configure-custom-tags-settings"></a>Konfigurieren von benutzerdefinierten Kategorieneinstellungen

Sie können die folgenden Kategorieneinstellungen konfigurieren, um zu steuern, wie benutzerdefinierte Tags in der gesamten Organisation verwendet werden.

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Organisationsweite Einstellungen** > **Teams-Einstellungen**.
2. Legen Sie unter **Tagging** je nach den Anforderungen Ihrer Organisation Folgendes fest.

    - Lassen Sie Teambesitzer außer Kraft setzen, wer Tags verwalten **kann:** Wenn Sie diese Einstellung aktivieren, können  Teambesitzer festlegen, ob Teammitglieder innerhalb eines Teams Tags erstellen und verwalten können, und der Wert der Tags wird durch festlegen als Standardwert für jedes Team festgelegt. Wenn Sie diese Einstellung deaktivieren, können die **Tags** nicht pro Team geändert werden.
    - **Vorgeschlagene Standardtags**: Hiermit können Sie eine Reihe von Standardtags hinzufügen. Sie können bis zu 25 Tags hinzufügen, und jedes Tag kann maximal 25 Zeichen enthalten. Teambesitzer und -mitglieder können diese Vorschläge verwenden, weitere hinzufügen oder einen neuen Satz von Tags erstellen (wenn das Feature für sie aktiviert ist).
    - **Erstellen von benutzerdefinierten Tags:** Aktivieren Sie diese Einstellung, damit andere Personen als die von Ihnen vorgeschlagenen Standardtags Tags hinzufügen können. Wenn dies deaktiviert ist, können Benutzer nur die vorgeschlagenen Standardtags verwenden. Wenn Sie dies deaktivieren, stellen Sie sicher, dass Sie mindestens einen Standardtags hinzufügen.

## <a name="manage-custom-tags-settings-for-a-team"></a>Verwalten von benutzerdefinierten Kategorieneinstellungen für ein Team

Wenn Sie im  Microsoft Teams Admin Center die Einstellung "Teambesitzer außer Kraft setzen dürfen, die Kategorien verwalten können" aktiviert haben, können Teambesitzer festlegen, ob Mitglieder Tags auf Teamebene hinzufügen können. Wechseln Sie dazu auf der Registerkarte **Einstellungen** für ein Team zu **Tags**, und wählen Sie dann aus, wer Tags hinzufügen kann.

![Screenshot der Tag-Einstellung auf Teamebene](media/manage-tags-team-settings.png)

## <a name="use-tags"></a>Verwenden von Tags

Hier erfahren Sie, wie Sie benutzerdefinierte Tags hinzufügen und Tags nach Schicht einrichten (wenn Sie die App "Schichten" in Teams verwenden). Wenn Sie mehr erfahren möchten, lesen Sie [Verwenden von Tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).

### <a name="create-and-assign-custom-tags"></a>Erstellen und Zuweisen von benutzerdefinierten Tags

Wenn Sie benutzerdefinierte Tags erstellen und zuweisen möchten, wählen Sie auf der linken Seite der App die Option **"Teams"** aus, und suchen Sie dann Ihr Team in der Liste. Wählen **Sie 2 2 Weitere Optionen aus,** und wählen Sie dann **"Kategorien verwalten" aus.** Hier können Sie Tags erstellen und sie Personen in Ihrem Team zuweisen.

![Screenshot zum Anwenden von Tags im Teams-Client  ](media/manage-tags-teams.png)

Wenn Sie eine  Markierung löschen möchten, wählen Sie 

### <a name="set-up-tagging-by-shift-coming-soon"></a>Einrichten von Tags nach Schicht (in Kürze folgen)

1. Wechseln Sie in Teams zur [App "Schichten".](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop)
2. Erstellen Sie [Schichtgruppen,](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea#bkmk_organizeshiftsbygroup) und benennen Sie sie nach einem Attribut wie einer Rolle. Beispiel: EngineerOnCall. Der Name der Schichtgruppe ist der Name der Markierung.
3. [Füllen Sie einen Zeitplan aus,](https://support.microsoft.com/office/fill-out-a-schedule-in-shifts-2d58df9b-1c6c-4c84-b0c3-835de7ad13ea) indem Sie den Mitgliedern Ihrer Teams Schichten zuweisen. Wenn Sie fertig sind, wählen Sie in der oberen rechten Ecke der App "Schichten" die Option **"Für Team freigeben" aus.**
4. Warten Sie 15 Minuten, bis die geplanten Schichten den Taggingdienst auffüllen.
5. Verwenden Sie die Markierung überall dort, wo Sie Tags in Teams verwenden.

Das Tagging nach Schicht ermöglicht es Ihren Benutzern, die Personen in Echtzeit zu erreichen, die sich im Schichtbetrieb in der Schicht auf dem Computer begnen. Benachrichtigungen werden nur an Personen gesendet, die schichtdienstverteilt sind, wenn ein Tag zum Starten eines Chats oder in einem Kanalbeitrag verwendet wird.

## <a name="related-topics"></a>Verwandte Themen

[Verwenden von Tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[Verwalten der Schichten-App für Ihre Organisation in Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Hilfedokumentation zu Schichten](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
