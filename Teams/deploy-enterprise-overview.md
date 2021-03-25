---
title: Microsoft Teams Enterprise-Bereitstellung – Übersicht
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Erfahren Sie, wie Sie Unternehmensfeatures von Microsoft Teams bereitstellen.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd3e60fafecd3cf025187935a9dc28b492c39d1b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121413"
---
# <a name="teams-enterprise-deployment-overview"></a>Teams Enterprise-Bereitstellung – Übersicht

Wenn Sie ein mittleres oder großes Unternehmen sind, müssen Sie sich überlegen, wie Sie den Dienst für die Benutzer bereitstellen, wie Sie den Microsoft Teams-Client für sie bereitstellen, wie sich Ihr Netzwerkentwurf auf die Qualität der Echtzeitkommunikation auswirken könnte und so weiter. In den folgenden Abschnitten finden Sie Artikel, die Ihnen bei der Planung von Teams in Ihrer Organisation helfen.

> [!NOTE]
> Wenn dies noch nicht geschehen ist, wird dringend empfohlen, die Bereitstellung von Teams mit einem Pilotprojekt zu beginnen. Ein Pilotprojekt ermöglicht es Ihnen und einigen Early Adoptern, sich vor der Planung und dem möglichen Rollout mit Teams und dessen Funktionen vertraut zu machen. Weitere Informationen zum Starten Ihres Pilotprojekts finden Sie unter [Erste Schritte mit Microsoft Teams](get-started-with-teams-quick-start.md).

Nachdem Sie die nachstehenden Abschnitte gelesen haben und bereit sind, mit der Bereitstellung von Teams in Ihrer Organisation zu beginnen, lesen Sie [Einrichten von Microsoft Teams in Ihrem Unternehmen](deploy-enterprise-setup.md).

## <a name="architecture"></a>Architektur

Teams ist eng in Microsoft 365 integriert und nutzt zahlreiche Funktionen für Chat, Dateifreigabe, Besprechungen, Telefonie, Videostreaming und vieles mehr. Bevor Sie Teams in den Einsatz nehmen, sehen Sie sich die Poster [IT-Architektur- und Telefonielösungen von Microsoft Teams](teams-architecture-solutions-posters.md) an, um sich mit der Art und Weise vertraut zu machen, wie Teams mit dem Rest von Microsoft 365 zusammenarbeiten kann, um ihren Benutzern ein umfassendes Teamerlebnis zu bieten.

## <a name="workloads"></a>Workloads

Teams verfügt über drei Workloads, die unabhängig voneinander bereitgestellt werden können: **Chat, Teams und Kanäle**; **Besprechungen und Konferenzen**; und **Telefonanlage und PSTN-Konnektivität (Public Switched Telephone Network) für**. Für jeden Workload gibt es einen eigenen Abschnitt in der Dokumentation, der es einfacher macht, Informationen zu diesem Workload zu finden. Hierzu gehören Informationen zur Bereitstellungsplanung.

Informationen zur Bereitstellungsplanung für den Workload, den Sie bereitstellen möchten, finden Sie in den folgenden Artikeln:

- [Chat, Teams und Kanäle](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
- [Besprechungen und Konferenzen](deploy-meetings-microsoft-teams-landing-page.md)
- [Telefonsystem und PSTN-Konnektivität](cloud-voice-landing-page.md)

## <a name="network-planner"></a>Netzwerkplaner

Die Netzwerkplanung für Teams ist äußerst wichtig, wenn Sie eine große Anzahl von Benutzern, komplexe Netzwerke oder beides haben. Teams unterstützt Sprachanrufe und Videokonferenzen, die beide auf Echtzeitkommunikation angewiesen sind, um den Benutzern die bestmögliche Benutzererfahrung zu bieten. Netzwerke müssen:

- Über ausreichende Bandbreitenkapazität verfügen, um die Anzahl gleichzeitiger Sprachanrufe, Videokonferenzen, Besprechungen, Bildschirmfreigaben und so weiter zu nutzen.
- Netzwerkhardware verwenden, die Kommunikationsprotokolle in Echtzeit unterstützt.
- Die erforderlichen Netzwerkports zwischen Geräten in Ihren Netzwerken, Microsoft 365-Diensten und externen Benutzern zulassen.

Lesen Sie die folgenden Artikel, um die Anforderungen an das Teams-Netzwerk besser zu verstehen:

- [Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams](prepare-network.md)
- [Proxyserver für Skype for Business Online und Microsoft Teams](proxy-servers-for-skype-for-business-online.md)

Um Sie bei der Planung zu unterstützen, enthält Teams den Netzwerkplaner. Der Netzwerkplaner stellt Fragen zur Anzahl und den Typen von Benutzern, über die Sie verfügen, über wie viele Websites Ihre Organisation verfügt, zur Bandbreitenkapazität Ihrer Netzwerklinks und mehr. Anhand dieser Informationen erstellt der Netzwerkplaner einen Bericht, der die Bandbreitenanforderungen für die einzelnen Aktivitäten zusammen mit den Empfehlungen zeigt.

 > [!div class="nextstepaction"]
> [Zum Netzwerkplaner wechseln](https://admin.teams.microsoft.com/networkplanner/organization)

(Sie müssen ein [globaler Microsoft 365-Administrator](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) sein, um den Netzwerkplaner öffnen zu können.)

Details zur Funktionsweise des Netzwerkplaners finden Sie unter [Verwenden des Netzwerkplaners für Microsoft Teams](network-planner.md).

Ein Beispiel dazu, wie der Netzwerkplaner Ihr Netzwerk planen kann, finden Sie unter [Verwenden des Netzwerkplaners – Beispielszenario](tutorial-network-planner-example.yml).

## <a name="teams-advisor"></a>Advisor für Teams

Der Advisor für Teams ist eine Lösung innerhalb von Teams, in der Teams, Kanäle, Dateifreigaben und Planner zusammenkommen, um ein Bereitstellungsprojekt für Ihre Organisation zu erstellen. Der Teamberater erstellt einen Projektplan speziell für den von Ihnen ausgewählten Workload (z. B. Chat, Teams und Kanäle), der die empfohlenen Aufgaben umfasst, die Sie während der Bereitstellung ausführen sollten. Jede Aufgabe enthält Anweisungen, Vorschläge und Links zu relevanten Artikeln, die Sie durch den Vorgang führen. Sie können einer oder mehrere Personen Aufgaben auf einfache Weise zuweisen und für jede Aufgabe ein Start- und Enddatum angeben.

> [!TIP]
> Erfahren Sie, wie Sie den Advisor für Teams verwenden können, um Sie bei der Planung Ihrer Teams-Bereitstellung zu unterstützen, indem Sie das Modul [Rollout mithilfe des Advisors für Teams](/learn/modules/m365-teams-rollout-using-advisor/) in Microsoft Learn abschließen.

> [!div class="nextstepaction"]
> [Zum Advisor für Teams wechseln](https://admin.teams.microsoft.com/teams-deployment)

(Sie müssen ein [globaler Microsoft 365-Administrator](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) sein, um den Advisor für Teams öffnen zu können.)

Details zur Funktionsweise des Advisor für Teams finden Sie unter [Verwenden von Advisor für Teams als Hilfe beim Rollout von Microsoft Teams](use-advisor-teams-roll-out.md).

## <a name="lifecycle-and-governance-planning"></a>Lebenszyklus- und Governanceplanung

Bei der Planung der Bereitstellung von Teams müssen Sie den Lebenszyklus von Teams, Kanälen, Dateien und so weiter in Ihrer Organisation berücksichtigen. Darüber hinaus sollten Sie sich überlegen, welche Arten von Informationen hierin gespeichert werden. Teams können für ein bestimmtes Projekt, für eine Abteilung oder als zentrale Ressource für die gesamte Organisation erstellt werden. Für jede dieser Anwendungen gibt es unterschiedliche Anforderungen, die zu Fragen wie den folgenden führen:

- Wie lange bleiben die Teams aktiv?
- Wer sollte die Teams und deren Kanäle besitzen und verwalten?
- Sollten bestimmte Compliance-Anforderungen für einige Teams gelten, für andere aber nicht?
- Sollte es eine Benennungsrichtlinie geben, damit die Benutzer das richtige Team identifizieren können?

Die Erstellung von Richtlinien und Leitfäden als Teil Ihrer anfänglichen Bereitstellung wird dazu beitragen, dass Ihre Benutzer die benötigten Informationen finden können. Ebenso wichtig ist jedoch, dass geeignete Richtlinien dazu beitragen, Ihre Organisation vor dem Verlust von Informationen zu schützen, Ihnen dabei zu helfen, die gesetzlichen Vorschriften zu erfüllen, und Ihnen dabei zu helfen, Informationen zu Archivzwecken bei Bedarf zu speichern.

Weitere Informationen zum Lebenszyklusmanagement und zur Governance in Teams finden Sie in den folgenden Themen:

- [Planen der Lebenszyklusverwaltung in Microsoft Teams](plan-teams-lifecycle.md)
- [Planen der Governance in Teams](plan-teams-governance.md).

## <a name="adoption"></a>Einführung

Um sicherzustellen, dass Ihr Unternehmen und Ihre Benutzer den größtmöglichen Nutzen aus Teams ziehen, benötigen Sie ein Einführungsprogramm. Ein effektives Einführungsprogramm kann Early Adopters mobilisieren, die Folgendes können:

- Formulieren der Vorteile von Teams für ihre Kollegen und für Geschäfts- oder Gruppenleiter.
- Für Begeisterung bei anderen sorgen, die sehen, wie Teams die Zusammenarbeit verbessert und die Verbindung zueinander erleichtert.
- Bei der Bewertung vorhandener Geschäftsprozesse helfen, und Empfehlungen machen, wie Teams in diese integriert werden können.
- Melden Sie dem Bereitstellungsteam sowohl die Erfolge als auch die Schwierigkeiten, um den Einführungsprozess zu verbessern.

Details zum Einrichten eines Einführungsprogramms finden Sie unter [Einführung von Microsoft Teams](adopt-microsoft-teams-landing-page.md).