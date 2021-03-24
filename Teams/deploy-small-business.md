---
title: Einrichten von Microsoft Teams in Ihrem Kleinunternehmen
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Richten Sie Teams in Ihrem Kleinunternehmen ein, damit Ihre Benutzer per Chat und Dateifreigabe zusammenarbeiten, kleine und große Besprechungen einrichten und daran teilnehmen sowie per Video und Sprache kommunizieren können.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2fd7865823cffdfd2f2b2932a78744786c59cfd0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101231"
---
# <a name="set-up-microsoft-teams-in-your-small-business"></a>Einrichten von Microsoft Teams in Ihrem Kleinunternehmen

Es gibt viele Möglichkeiten zum Anpassen von Teams. In den folgenden Abschnitten wird gezeigt, wie Sie die einzelnen Teams-Workloads einrichten: **Chats, Teams und Kanäle**; **Besprechungen und Konferenzen**; und **Cloud Voice**. Die Reihenfolge, in der Sie die einzelnen Arbeitslasten einrichten, liegt bei Ihnen. Zwar empfehlen wir ihnen, zuerst die Chats, Teams und Kanäle für die Arbeitsauslastung eingerichtet zu haben, sie können aber mit Besprechungen und Konferenzen oder sogar mit Cloud Voice beginnen. Sie haben die Wahl.

> [!NOTE]
> Wenn dies noch nicht geschehen ist, wird dringend empfohlen, die Bereitstellung von Teams mit einem Pilotprojekt zu beginnen. Ein Pilotprojekt ermöglicht es Ihnen und einigen Early Adoptern, sich vor der Planung und dem möglichen Rollout mit Teams und dessen Funktionen vertraut zu machen. Weitere Informationen zum Starten Ihres Pilotprojekts finden Sie unter [Erste Schritte mit Microsoft Teams](get-started-with-teams-quick-start.md).

Stellen Sie vor dem allgemeinen Rollout von Teams sicher, dass Ihre Organisation bereit ist, indem Sie die Punkte unter [Stellen Sie sicher, dass Sie bereit sind](get-started-with-teams-quick-start.md#make-sure-youre-ready) überprüfen.

Springen Sie zu dem Abschnitt, der Sie interessiert:

- [Workloads](#workloads)
  - [Chat, Teams und Kanäle](#chat-teams-and-channels)
  - [Besprechungen und Konferenzen](#meetings-and-conferencing)
  - [Business Voice](#business-voice)
- [Bereitstellen von Clients](#deploy-clients)
- [Schulung](#training)

## <a name="workloads"></a>Workloads
### <a name="chat-teams-and-channels"></a>Chat, Teams und Kanäle

Chats, Teams und Kanäle sind die Säulen von Teams. Der **Chat** ermöglicht es einem oder mehreren Benutzern, sich zu unterhalten, Dateien zu teilen und sich privat zu treffen. Mit **Teams**, das für alle Personen in Ihrer Organisation oder nur für die Teammitglieder sichtbar sein kann, können die richtigen Personen unabhängig von der Aufgabe oder dem Anlass zusammenarbeiten, ganz gleich, ob es um ein langes Projekt oder die Planung einer Geburtstagsfeier geht. **Kanäle** innerhalb von Teams können Themen, Projekte, Abteilungen oder alles andere segmentieren, was für Ihr Team sinnvoll ist. Details zu Chats, Teams und Kanälen finden Sie unter [Übersicht über Teams und Kanäle](teams-channels-overview.md).

> [!TIP]
> Schauen Sie sich an, wie Sie Teamrollen, Zugriff und Messagingrichtlinien verwalten können, indem Sie das Modul [Verwalten von Microsoft Teams](/learn/modules/m365-teams-collab-manage-teams/) in Microsoft Learn abschließen.

Wenn Sie über das Roll out von Teams und Kanälen nachdenken, müssen Sie entscheiden, wer diese erstellen darf, ob Gäste von außerhalb Ihrer Organisation darauf zugreifen können und so weiter. Der Artikel [Chat, Teams, Kanäle und Apps in Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md) enthält viele Informationen zur Planung von Chats, Teams und Kanälen. Allerdings sollten Sie über einige wichtige Dinge in diesem Artikel nachdenken. Wählen Sie eine Entscheidung aus, wenn Sie weitere Informationen dazu wünschen.

| Entscheidung | Beschreibung |
|--|--|
| [Wer sollte Teams-Administrator sein?](deploy-chat-teams-channels-microsoft-teams-landing-page.md#teams-administrators) | Administratorrollen können verwendet werden, um Personen, die Teams verwalten möchten, bestimmte Berechtigungen zu erteilen. Kleine Unternehmen benötigen diese zusätzlichen Rollen möglicherweise nicht, da dieselbe Person möglicherweise für alle Aspekte von Teams verantwortlich ist. Sie können Mitglieder später jederzeit hinzufügen oder entfernen.<br><br>[Verwenden von Teams-Administratorrollen zum Verwalten von Microsoft Teams](using-admin-roles.md) |
| [Wer sollte Team-Besitzer und -mitglieder sein?](deploy-chat-teams-channels-microsoft-teams-landing-page.md#teams-owners-and-members) | Teambesitzer steuern, wer auf ein Team und dessen Kanäle zugreifen kann. Sie können entscheiden, ob ein Team oder Kanal öffentlich (für die Organisation) oder privat ist, und Richtlinien einrichten, z. B. ob ein Kanal moderiert werden soll. Mitglieder können auf das Team und dessen Kanäle zugreifen (sofern kein Kanal auf "Privat" festgelegt ist und sie kein Mitglied dieses Kanals sind) und können als Moderatoren festgelegt werden.<br><br>[Zuweisen von Teambesitzern und -mitgliedern in Microsoft Teams](assign-roles-permissions.md) |
| [Sollte der Gastzugriff aktiviert sein?](deploy-chat-teams-channels-microsoft-teams-landing-page.md#guest-access) |Mithilfe eines Gastzugriffs können Personen in Ihrer Organisation Personen außerhalb Ihrer Organisation dazu einladen, auf Ihr Teams und Ihre Kanäle zuzugreifen. Der Gastzugriff wird häufig verwendet, um mit Personen außerhalb Ihrer Organisation zusammenzuarbeiten, die keine formelle Beziehung mit Ihrer Organisation haben. So könnten Sie beispielsweise einen Projektplaner vorübergehend zur Arbeit an einem Projekt einladen.<br>Der Gastzugriff ist anders als der externe Zugriff. Beim Gastzugriff werden bestimmte Personen zur Interaktion mit Personen in Ihrer Organisation eingeladen.  <br>Der Gastzugriff ist standardmäßig **Aus**. <br><br>[Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams](set-up-guests.md)  |

Sie müssen nichts weiter tun, damit Ihre Benutzer mit der Nutzung von Chats, Teams und Kanälen beginnen können. Es gibt jedoch zahlreiche Optionen zum Steuern, wie Teams verwendet wird. Sie können jetzt Änderungen vornehmen oder warten, bis Sie sehen können, wie die Mitarbeiter Teams verwenden. Für weitere Informationen sollten Sie auch die folgenden Artikel lesen:

- [Verwalten von Messaging-Richtlinien in Teams](messaging-policies-in-teams.md)
- [Teams-Einstellungen](enable-features-office-365.md#teams-settings)

### <a name="meetings-and-conferencing"></a>Besprechungen und Konferenzen

Besprechungen und Konferenzen ermöglichen es Personen in Ihrer Organisation, sich untereinander und mit Personen außerhalb Ihrer Organisation zu treffen. Jede Person mit einem Teams- oder Skype for Business-Client kann an **Besprechungen** teilnehmen, zu denen sie eingeladen wurde. Mithilfe des Mikrofons, der Kamera und des Bildschirms ihres Geräts können die Teilnehmer an der Unterhaltung teilnehmen, ohne ein Telefon zu benötigen. Teilnehmer können chatten, Sprachanrufe tätigen und Video und Apps mit anderen Teilnehmern über einen PC oder ein mobiles Gerät teilen.

**Audiokonferenzen** ermöglicht es Teilnehmern, über ein normales Telefon an Besprechungen teilzunehmen, indem sie eine Konferenztelefonnummer anrufen und eine Besprechungs-ID eingeben. Audiokonferenzen sind nützlich, wenn ein Teilnehmer nicht über eine gute Internetverbindung verfügt, die Besprechung nur per Sprache stattfindet oder er wegen einem anderen Umstand nicht über den Teams-Client teilnehmen kann.

> [!TIP]
> Machen Sie sich mit Besprechungen und Ereignissen vertraut, indem Sie das Modul [Besprechungen, Konferenzen und Ereignisse mit Microsoft Teams verwalten](/learn/modules/m365-teams-collab-manage-meetings) in Microsoft Learn abschließen.

Besprechungen sind in Teams standardmäßig aktiviert, Sie können jedoch die Besprechungserfahrung für Organisatoren und Teilnehmer steuern. Sie können auch Richtlinien dafür festlegen, was Personen vor und während Besprechungen tun oder nicht tun dürfen. Für weitere Informationen sollten Sie auch die folgenden Artikel lesen:

- [Schnellstart für Administratoren – Besprechungen und Liveereignisse in Microsoft Teams](quick-start-meetings-live-events.md)
- [Einrichten von Audiokonferenzen für kleine und mittelständische Unternehmen](audio-conferencing-smb.md)

### <a name="business-voice"></a>Business Voice

[Microsoft 365 Business Voice](business-voice/whats-business-voice.md) ist eine großartige Lösung für Unternehmen mit weniger als 300 Benutzern, die ihnen alle Funktionen einer Office-Telefonanlage bietet. Business Voice umfasst Voicemail, Anrufer-ID, Menüs für das Telefonsystem, gebührenfreie Nummern und mehr, ohne eine komplexe und kostenaufwendige lokale Telefonanlage verwalten zu müssen.

Business Voice basiert auf Microsoft 365 Phone System und vereinfacht das Hinzufügen von VoIP zu Ihrer Organisation durch die Bündelung von Telefonsystemfunktionen und -add-Ons sowie durch einen einfach zu bedienenden Assistenten, der Ihnen beim Einrichten Ihrer Telefonanlage hilft. Wenn Sich Ihre Organisation in einem [Land oder einer Region befindet, das/die Business Voice](business-voice/country-region-availability.md)unterstützt, können Sie Ihre Telefonnummern zu Microsoft 365 übertragen und uns die Verwaltung Ihres Telefonsystems für Sie gestatten.

Mit Microsoft 365 als Telefonanlage können Sie jedes Gerät in ein Smartphone verwandeln, indem Sie den Teams-Client darauf installieren. Wenn Sie aber lieber über ein herkömmliches Tischtelefon oder Konferenztelefon verfügen möchten, stehen viele für Teams zertifizierte Geräte zur Auswahl. In beiden Richtungen werden Anrufe immer an ihren eigenen Ort weiter geroutet, und Anrufe, die Sie tätigen, verfügen stets über Ihre Telefonnummer im Büro.

Wenn Sie An der Nutzung von Business Voice interessiert sind, lesen Sie [Was muss ich kaufen, um Microsoft 365 Business Voice verwenden zu können?](business-voice/what-to-buy.md).

## <a name="deploy-clients"></a>Bereitstellen von Clients

Wenn Sie bereit sind, Teams für Ihre Benutzer zu verwenden, können sie den Teams-Client auf ihrem Windows-, Mac- oder Linux-PC oder aber auf ihrem Android- oder iOS-Gerät installieren. Benutzer können den Teams-Client direkt von <https://teams.microsoft.com/downloads> herunterladen.

Stellen Sie sicher, dass jeder, der Teams verwenden wird, über eine Teams-Lizenz verfügt. Weitere Informationen zum Zuweisen einer Teams-Lizenz finden Sie unter [Verwalten des Benutzerzugriffs auf Teams](user-access.md#using-the-microsoft-365-admin-center).

> [!TIP]
> Erhalten Sie Empfehlungen zur Planung der Bereitstellung Ihrer Teams-Clientbereitstellung, indem Sie das Modul [Bereitstellen von Microsoft Teams-Clients](/learn/modules/m365-teams-collab-deploy-clients/) Microsoft Learn abschließen.

Wenn Ihre Organisation Microsoft Endpoint Configuration Manager, Gruppenrichtlinien oder einen Verteilungsmechanismus eines Drittanbieters verwendet, finden Sie Informationen zum Bereitstellen von Software auf den Computern ihrer Benutzer unter [Installieren von Microsoft Teams mithilfe von Microsoft Endpoint Configuration Manager](msi-deployment.md).

Detaillierte Informationen zum Bereitstellen von Teams-Clients finden Sie unter [Erhalten von Clients für Microsoft Teams](get-clients.md).

## <a name="training"></a>Schulung

Informationen dazu, wie Sie Ihre Benutzer in der Nutzung von Teams schulen, finden Sie unter [Microsoft Teams-Schulung](training-microsoft-teams-landing-page.md).