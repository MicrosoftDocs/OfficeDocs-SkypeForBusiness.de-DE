---
title: Planen von Microsoft 365 Government - Bereitstellungen GCC - Microsoft-Teams
author: lolajacobsen
ms.author: lehewe
manager: serdars
ms.date: 07/26/2018
ms.topic: article
ms.service: msteams
ms.reviewer: lehewe
description: Anleitung für IT-Spezialisten das Laufwerk Office 365-Bereitstellungen in Entitäten, die Daten können US Organisationsrichtlinien behandeln
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 430b6c6de5468442f7a290b07b28eb59d276e00c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885772"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Planen von Microsoft 365 Government - GCC-Bereitstellungen

Diese Anleitung ist für IT-Spezialisten, die Bereitstellungen von Office 365 in US-Federal, Bundesland, lokalen, tribal oder räumlicher Regierungsbehörden oder anderen Entitäten, die Daten zu behandeln, die behördlichen Vorschriften und Anforderungen, fällt gesteuert werden, in dem die Verwendung von Microsoft 365 Government - eignet sich GCC Sie diese Anforderungen erfüllen.

> [!NOTE]
> Wenn Ihre Organisation bereits Microsoft 365 Government - GCC Berechtigung Anforderungen erfüllt und zum angewendet und in das Programm angenommen wurden, können Sie die Schritte 1 bis 4 überspringen und direkt mit Schritt 5, um mit der Bereitstellung beginnen. 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>Schritt 1. Bestimmen Sie, ob Ihre Organisation Microsoft 365 Government - GCC benötigt und Berechtigung Anforderungen erfüllt. 

Die Microsoft 365 Government - bietet GCC Umgebung Einhaltung US Behörden Anforderungen für die Clouddienste, einschließlich FedRAMP Mittel und Anforderungen für Strafjustiz und federal Tax Informationssysteme (CJI und FTI Datentypen).

Zusätzlich zu genießen die Features und Funktionen von Office 365, Vorteile für Organisationen die folgenden Features, die für Microsoft 365 Government - GCC eindeutig sind:

-   Der Inhalt Ihrer Organisation Kunden von Inhalten in kommerziellen Office 365-Dienste von Microsoft Customer logisch getrennt.
-   Der Inhalt Ihrer Organisation Kunden wird in den USA gespeichert.
-   Zugriff auf Inhalte von Ihrer Organisation Kunden ist auf überwachtes Microsoft-Mitarbeiter beschränkt.
-   Microsoft 365 Government - erfüllt GCC Zertifizierungen und Akkreditierungen, die für uns öffentlicher Sektor-Kunden erforderlich sind.

Sie können weitere Informationen zu Microsoft 365 Government - Angebot für den Kunden am [Office 365 Government plant](https://products.office.com/government/compare-office-365-government-plans), einschließlich [Berechtigung Anforderungen](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)US-Regierung GCC finden.

Die [Beschreibung der Dienste von Office 365 US-Regierung](https://technet.microsoft.com/library/mt774581.aspx) beschreibt die Plattform Vorteile, die meeting-Compliance-Bestimmungen innerhalb der USA zentraler.

> [!Tip]
> Möglicherweise möchten Sie übertragen von Informationen in der Beschreibung in den Tabellen in einer Excel-Arbeitsmappe, und fügen Sie zwei Spalten: **Relevant für meine Organisation Y/N** und **erfüllt die Anforderungen der Organisation Y/N**. Anschließend können Sie diese Liste mit Ihren Kollegen zu bestätigen, dass dieser Dienst Anforderungen Ihrer Organisation erfüllt überprüfen.


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Microsoft 365 Government - GCC für Ihre Organisation geeignet ist.</li><li>Vergewissern Sie sich, dass Ihre Organisation Berechtigung Anforderungen erfüllt.</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Als Nächstes|<ul><li>Verstehen der Funktionen von Microsoft 365 Government - GCC.</li></ul>|

> [!Note]
> Microsoft 365 Government - GCC ist nur in den USA verfügbar. Eine Reihe von [Behörden für Office 365-Pläne](https://products.office.com/en/government/compare-office-365-government-plans)können nicht – US-Regierung Kunden auswählen.

## <a name="step-2-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>Schritt 2. Verstehen Sie, welche Funktionen derzeit nicht verfügbar oder standardmäßig deaktiviert sind. 

Um die Anforderungen des Kunden Cloud Behörden zu unterstützen, es gibt einige Unterschiede zwischen Microsoft 365 Government - GCC und Enterprise-Pläne. In der folgenden Tabelle aufgeführten Features sind nicht verfügbar.

| Funktion                     | Grund            |
|-----------------------------|-------------------|
| Anruf und Meeting-Aufzeichnung  | Aufzeichnung ist abhängig von der Microsoft-Stream, die in der Zukunft in US-Regierung Plänen zur Verfügung gestellt wird. |
| Apps       | Apps (beispielsweise Bots, Registerkarten und Connectors) nicht verfügbar anfänglich, aber wir arbeiten sie zur Verfügung zu stellen, sobald alle ihre Komponenten die FedRAMP Moderate Compliance Leiste erfüllen. |
| E-Mail von einem DDE-Kanal             | Die aktuelle featurearchitektur in US-Regierung Pläne wird nicht unterstützt. |
| Einheitliche Anwesenheit            | Wir sind fertig gestellt Arbeit unseren Unternehmenskunden zuerst für dieses wichtige Features. Es wird in der Zukunft zu behördliche Kunden verfügbar sein. |
| Interop Chat zwischen Teams & SfB Benutzer            | Interop ist abhängigen auf Unified Anwesenheit Service (USV) und kann nicht funktionsfähig, wenn für USV GCC Teams Mandanten aktiviert sind. |

| E-Mail-Benachrichtigungen | Die aktuelle featurearchitektur in den Plänen US-Regierung wird nicht unterstützt. Dieses Feature verfügbar gemacht US-Regierung Plan Kunden in Zukunft laufende "Arbeit" ist. |


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkt|<ul><li>Entscheiden Sie, ob Microsoft 365 Government - Featuregruppe GCC Anforderungen Ihrer Organisation erfüllt.</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Als Nächstes|<ul><li>Verstehen Sie Standardeinstellungen für Sicherheit.</li></ul>|

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>Schritt 3. Grundlegendes zu Microsoft 365 Government - GCC standardsicherheitseinstellungen.

Es wird empfohlen, dass Sie Ihre [Einstellungen Verwaltungs- und Sicherheitsfunktionen](enable-features-office-365.md) sorgfältig überprüfen, bevor Sie sie ändern, und Auswirkungen auf die Einhaltung von Bestimmungen berücksichtigen, bevor Sie Änderungen vorgenommen werden und den Standardeinstellungen für die Sicherheit können Zeit in Anspruch nehmen.

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkt|<ul><li>Entscheiden Sie, ob Sie die Standardeinstellung Microsoft 365 Government - GCC Security Settings, ändern müssen Sie zunächst kennen die Auswirkungen von Änderungen auflösen Sie vornehmen, möglicherweise.</li></ul> |

## <a name="step-4-apply-for-microsoft-365-government---gcc"></a>Schritt 4. Für Microsoft 365 Government - GCC anwenden

Entschlossen, dass dieser Dienst für Ihr Unternehmen geeignet ist, starten Sie den Vorgang [für diesen Dienst hier](https://products.office.com/government/eligibility-validation)anwenden.

## <a name="step-5-plan-for-governance"></a>Schritt 5. Planen der Steuerung

Bestimmen der Anforderungen für die Unternehmensleitung und wie Sie diese erfüllen können. Weitere Informationen finden Sie in [Planen der Steuerung in Teams](plan-teams-governance.md) .

## <a name="step-6-deploy-teams-for-collaboration"></a>Schritt 6. Bereitstellen des Teams für die Zusammenarbeit

Nachdem Sie Onboarded an Microsoft 365 Government - GCC, wurden haben können Sie die standardmäßige Bereitstellungsmethode der Verwendung [der schnelle](https://fasttrack.microsoft.com/fasttrack-faq) und Ihr gewählten Partner mit dem Dienst integrierte folgen.

Wenn Sie bereit sind, stellen Sie so [Aktivieren Sie für die Zusammenarbeit innerhalb Ihrer Organisation über Teams und Kanäle](teams-overview.md)Teams bereit. Achten Sie darauf, dass Sie mit der Annahme und Änderungsmanagement Team oder Teams Champions beteiligen.

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>Schritt 7. Bereitstellen des Teams für Besprechungen und VoIP

Dies ist auch der ideale Zeitpunkt, Teams mit Ihrer breiter beteiligten Gruppe verwenden Sie zum Starten der Planung für die Einführung von Besprechungen und [Cloud-VoIP-Funktionen](cloud-voice-deployment.md).

