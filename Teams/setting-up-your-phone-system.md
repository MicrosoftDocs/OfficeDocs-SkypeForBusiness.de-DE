---
title: Einrichten des Telefonsystems in Ihrer Organisation
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-apr2020
- intro-get-started
description: Schrittweise Anleitung zum Einrichten von Teams Telefonsystem für Ihre Organisation in Microsoft 365.
ms.openlocfilehash: 12e202fed6ad63835c364662194be2eabf872b31
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681926"
---
# <a name="set-up-phone-system-in-your-organization"></a>Einrichten des Telefonsystems in Ihrer Organisation

Dieser Artikel enthält eine Roadmap für Inhalte zum Einrichten Telefonsystem – Microsoft-Technologie zur Aktivierung der Anrufsteuerung und der Funktionen von Private Branch Exchange (PBX) in der Microsoft 365 Cloud. Links zu detaillierteren Informationen finden Sie am Ende jedes Schritts.

Bevor Sie diesen Artikel lesen, stellen Sie sicher, dass Sie gelesen haben[, was Telefonsystem ist](what-is-phone-system-in-office-365.md) und [was Sie mit Telefonsystem](here-s-what-you-get-with-phone-system.md) erhalten. In den beiden letzteren Artikeln werden Telefonsystem Anforderungen und Features beschrieben.

In diesem Artikel werden die folgenden Schritte beschrieben:

- [Schritt 1: Kaufen und Zuweisen einer Telefonsystem-Lizenz](#step-1-buy-and-assign-a-phone-system-license)
- [Schritt 2: Auswählen einer PSTN-Konnektivitätsoption](#step-2-choose-a-pstn-connectivity-option)
- [Schritt 3: Abrufen von Telefonnummern für Ihre Benutzer](#step-3-get-phone-numbers-for-your-users)
- [Schritt 4: Abrufen von Telefonnummern für Dienste](#step-4-get-phone-numbers-for-services-call-queues-auto-attendants)
- [Schritt 5: Wenn Sie eine Anrufwarteschleife einrichten möchten](#step-5-if-you-want-to-set-up-a-call-queue)
- [Schritt 6: Wenn Sie eine automatische Telefonzentrale einrichten möchten](#step-6-if-you-want-to-set-up-an-auto-attendant)
- [Schritt 7: Einrichten von Kommunikationsguthaben für gebührenfreie Nummern](#step-7-set-up-communications-credits-for-toll-free-numbers)

## <a name="step-1-buy-and-assign-a-phone-system-license"></a>Schritt 1: Kaufen und Zuweisen einer Telefonsystem-Lizenz

Um einem einzelnen Benutzer eine Telefonsystem Lizenz zuzuweisen, sind die Schritte identisch mit dem Zuweisen einer Microsoft 365 Lizenz. Sie können mehreren Benutzern auch massenhaft Lizenzen zuweisen. Weitere Informationen zu verfügbaren Telefonsystem Lizenzen und zum Erwerben und Zuweisen von Lizenzen finden Sie [unter Teams Add-On-Lizenzen](/microsoftteams//teams-add-on-licensing/microsoft-teams-add-on-licensing) und [Zuweisen Microsoft Teams Add-On-Lizenzen](/microsoftteams/teams-add-on-licensing/assign-teams-add-on-licenses).

## <a name="step-2-choose-a-pstn-connectivity-option"></a>Schritt 2: Auswählen einer PSTN-Konnektivitätsoption

Damit Ihre Benutzer externe Anrufe tätigen und empfangen können, müssen Sie Telefonsystem mit dem Telefonfestnetz (Public Switched Telephone Network, PSTN) verbinden. Microsoft bietet mehrere Optionen für die Verbindung mit dem PSTN, einschließlich:

- Anrufplan. Eine All-in-the-Cloud-Lösung mit Microsoft als Ihrem PSTN-Anbieter.

- Telefonieanbieter. Wenn Ihr vorhandener Netzbetreiber am Microsoft Telefonieanbieter-Programm teilnimmt, kann er PSTN-Anrufe und Session Border Controller (SBCs) für Sie verwalten.

- Direktes Routing. Verwenden Sie Ihren eigenen PSTN-Netzbetreiber, indem Sie Ihre SBCs mit Telefonsystem verbinden.

Weitere Informationen zu allen Konnektivitätsoptionen finden Sie unter [PSTN-Konnektivitätsoptionen](pstn-connectivity.md).

## <a name="step-3-get-phone-numbers-for-your-users"></a>Schritt 3: Abrufen von Telefonnummern für Ihre Benutzer

Bevor Sie in Ihrer Organisation Benutzer für das Tätigen und Empfangen von Anrufen einrichten können, müssen Sie Telefonnummern für diese anfordern.

Informationen zum Verwalten von Telefonnummern für Ihre Benutzer finden Sie in den folgenden Artikeln. Wie Sie Nummern für einen Benutzer verwalten, hängt von der ausgewählten PSTN-Konnektivitätsoption ab.

- [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-landing-page.md) – Bietet eine Übersicht über Telefonnummerntypen mit Links zu bestimmten Artikeln zum Abrufen und Verwalten von Nummern, je nach Ihrer PSTN-Konnektivitätsoption.
Beschreibt die beiden Arten von [Benutzertelefonnummern](manage-phone-numbers-landing-page.md#user-telephone-numbers).

- [Zuweisen, Ändern oder Entfernen einer Telefonnummer für einen Benutzer](assign-change-or-remove-a-phone-number-for-a-user.md) – Beschreibt, wie Sie die erworbenen Telefonnummern zuweisen und verwalten.

- [Wie viele Telefonnummern Sie erhalten können](how-many-phone-numbers-can-you-get.md) – Beschreibt, wie viele Telefonnummern Sie erhalten können, abhängig von den Arten von Telefonnummern und Arten von Lizenzen, die Sie gekauft und zugewiesen haben.

## <a name="step-4-get-phone-numbers-for-services-call-queues-auto-attendants"></a>Schritt 4: Abrufen von Telefonnummern für Dienste (Anrufwarteschleifen, automatische Telefonzentralen)

Zusätzlich zum Abrufen von Telefonnummern für Ihre Benutzer können Sie gebührenpflichtige oder gebührenfreie Telefonnummern für Dienste wie automatische Telefonzentralen und Anrufwarteschleifen erwerben. Eine Dienstnummer kann Hunderte von Anrufen gleichzeitig verarbeiten, während die Telefonnummer eines Benutzers nur wenige Anrufe gleichzeitig verarbeiten kann.

Sie können Servicenummern von Microsoft erhalten, die in Ihrer Lizenzierung enthalten sind. Wenn Sie über PSTN-Konnektivität über Telefonieanbieter oder Direct Routing verfügen, können Sie Servicenummern verwenden, die von Ihrem eigenen Netzbetreiber oder Netzbetreiber bereitgestellt werden.

Weitere Informationen finden Sie unter:

- [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-landing-page.md) – Bietet eine Übersicht über Telefonnummerntypen mit Links zu bestimmten Artikeln zum Abrufen und Verwalten von Nummern, je nach Ihrer PSTN-Konnektivitätsoption.
Beschreibt die von Microsoft verfügbaren [Diensttelefonnummern](manage-phone-numbers-landing-page.md#service-telephone-numbers) , die in Ihrer Lizenzierung enthalten sind. Informationen zu Servicenummern, die von Telefonieanbieter oder Direct Routing bereitgestellt werden, erhalten Sie von Ihrem Anbieter.

- [Wie viele Telefonnummern Sie erhalten können](how-many-phone-numbers-can-you-get.md) – Beschreibt, wie viele Telefonnummern Sie erhalten können, abhängig von den Arten von Telefonnummern und Arten von Lizenzen, die Sie gekauft und zugewiesen haben.

## <a name="step-5-if-you-want-to-set-up-a-call-queue"></a>Schritt 5: Wenn Sie eine Anrufwarteschleife einrichten möchten

Anrufwarteschleifen umfassen Begrüßungen, die verwendet werden, wenn jemand eine Telefonnummer für Ihre Organisation anruft, die Möglichkeit, die Anrufe automatisch in den Haltebereich zu setzen, und die Möglichkeit, nach dem nächsten verfügbaren Anrufagenten zu suchen, um den Anruf zu verarbeiten. Sie können eine einzige Anrufwarteschleife oder mehrere Anrufwarteschleifen für Ihre Organisation erstellen.

Weitere Informationen zu Anrufwarteschleifen finden [Sie unter Erstellen einer Anrufwarteschleife](create-a-phone-system-call-queue.md).

## <a name="step-6-if-you-want-to-set-up-an-auto-attendant"></a>Schritt 6: Wenn Sie eine automatische Telefonzentrale einrichten möchten

Mithilfe automatischer Telefonzentralen können Personen, die sich in Ihre Organisation einwählten, in einem Menüsystem navigieren, um sie zur richtigen Abteilung, Anrufwarteschleife, Person oder Operator zu gelangen.

Informationen zum Einrichten von automatischen Telefonzentralen finden [Sie unter Einrichten einer automatischen Telefonzentrale](create-a-phone-system-auto-attendant.md).

## <a name="step-7-set-up-communications-credits-for-toll-free-numbers"></a>Schritt 7: Einrichten von Kommunikationsguthaben für gebührenfreie Nummern

Wenn Sie gebührenfreie Nummern mit Microsoft Teams verwenden möchten, müssen Sie Guthaben für Kommunikationen einrichten. Gebührenfreie Anrufe werden nach Minuten abgerechnet und erfordern einen positiven Guthabensaldo für Kommunikationen.

Guthaben für Kommunikationen ist eine bequeme Möglichkeit, gebührenfreie Telefonnummern wie folgt hinzuzufügen:

- Mit Servicenummern für VoIP-Apps, z. B. automatische Telefonzentralen oder Anrufwarteschleifen.

- So wählen Sie eine beliebige internationale Telefonnummer aus, wenn Sie über Inlandsanrufplanabonnements verfügen oder über das hinausgehen, was in einem Abonnement für inländische und internationale Anrufe enthalten ist.

- So wählen Sie einen Anruf aus und zahlen pro Minute, nachdem Sie Ihre monatliche Minutenzuteilung ausgeschöpft haben.

Weitere Informationen finden Sie unter [Was sind Guthaben für Kommunikationen?](what-are-communications-credits.md) und [Einrichten von Kommunikationsguthaben für Ihre Organisation](set-up-communications-credits-for-your-organization.md).

## <a name="related-topics"></a>Verwandte Themen

- [Was ist das Telefonsystem?](what-is-phone-system-in-office-365.md)

- [Das Telefonsystem bietet Ihnen Folgendes](here-s-what-you-get-with-phone-system.md)

- [Verwalten von Telefonnummern für Ihre Organisation](manage-phone-numbers-landing-page.md)
