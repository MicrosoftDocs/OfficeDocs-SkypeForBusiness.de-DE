---
title: Microsoft 365 Government – GCC-Bereitstellungen
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Leitfaden für IT-Profis zum Ansinnen von Microsoft 365-Bereitstellungen in Entitäten, die Daten behandeln, die den Vorschriften der US-Regierung unterliegen
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ecc733c181e268dd6092f169e91d2f9acb4ee47
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117833"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Plan für Microsoft 365 Government – GCC-Bereitstellungen

Diese Anleitung gilt für IT-Profis, die Bereitstellungen von Microsoft 365 in US-Bundesstaaten, Bundesstaaten, lokalen, stammesischen oder gebietsbezogenen Behörden oder anderen Entitäten, die Daten behandeln, die staatlichen Vorschriften und Anforderungen unterliegen, wo die Verwendung von Microsoft 365 Government - GCC geeignet ist, um diese Anforderungen zu erfüllen. Neu am 26. März 2020: Verpassen Sie nicht unseren herunterladbaren [Schnellstartleitfaden für GCC.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)

> [!IMPORTANT]
> Microsoft Teams erlebt aufgrund der Coronavirus-Pandemie (COVID-19) einen enormen Anstieg bei Onlineanrufen und Audio-/Videokonferenzen.<br/>
> 
>Als Reaktion auf die beispiellose Zunahme von Anrufen und um Kontinuität und Verfügbarkeit sicherzustellen, lässt Microsoft Microsoft Microsoft Teams GCC-Audio-/Videoserver die Verarbeitungskapazität in unseren kommerziellen Rechenzentren sowie in unseren Behördendatencentern nutzen.<br/>
> 
>Diese Audio-/Videoserver befinden sich auf den Microsoft Azure FedRAMP High-Anerkennungsgrenzservern in den USA und speichern keine Kundeninhalte. Diese Server verarbeiten jedoch Audio und Video für Anrufe und Konferenzen und arbeiten während dieser Zwischenperiode unter unseren kommerziellen Mitarbeitern.<br/>
> 
>Qualifizierte, überprüfte Mitarbeiter überwachen diese Server auf potenziellen Zugriff auf Kundendaten, indem sie alle interaktiven Anmeldungen für diese Server überprüfen. Qualifizierte Mitarbeiter erfüllen die GCC-Anforderungen für den Zugriff auf Kundeninhalte. Details zu den Anforderungen für die Überprüfung finden Sie in der [Beschreibung des GCC-Diensts.](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)<br/>
> 
>Vielen Dank für Ihre Unterstützung, während wir schritte, um sicherzustellen, dass unsere Dienste in diesen außergewöhnlichen Zeiten verfügbar und zuverlässig bleiben.<br/>


> [!NOTE]
> Wenn Ihre Organisation die Berechtigungsanforderungen für Microsoft 365 Government - GCC bereits erfüllt und für das Programm beantragt und akzeptiert wurde, können Sie die Schritte 1 und 2 überspringen und direkt zu Schritt 3 wechseln. 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>Schritt 1: Ermitteln Sie, ob Ihre Organisation Microsoft 365 Government – GCC benötigt und die Voraussetzungen für die Teilnahmeberechtigung erfüllt. 

Die Microsoft 365 Government - GCC-Umgebung bietet die Einhaltung der Us-Government-Anforderungen für Clouddienste, einschließlich FedRAMP Moderate, sowie Anforderungen für Strafjustiz und Steuerinformationssysteme des Bundes (CJI- und FTI-Datentypen).

Organisationen profitieren nicht nur von den Features und Funktionen von Microsoft 365, sondern profitieren auch von den folgenden Features, die für Microsoft 365 Government – GCC einzigartig sind:

-   Die Kundeninhalte Ihrer Organisation sind logisch vom Kundeninhalt in den kommerziellen Microsoft 365-Diensten von Microsoft getrennt.
-   Die Kundeninhalte Ihrer Organisation werden in den USA gespeichert.
-   Der Zugriff auf die Kundeninhalte Ihrer Organisation ist auf angezeigte Microsoft-Mitarbeiter beschränkt.
-   Microsoft 365 Government – GCC erfüllt Zertifizierungen und Zertifizierungen, die für Kunden des öffentlichen Us-Amerikanischen Öffentlichen Diensts erforderlich sind.

Weitere Informationen zum Microsoft 365 Government - GCC-Angebot für Us-Government-Kunden finden Sie unter [Microsoft 365](https://products.office.com/government/compare-office-365-government-plans)Government-Pläne, einschließlich Der Anforderungen an die [Berechtigung.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)

In [der Beschreibung des Microsoft 365 US-Government-Diensts](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) werden die Vorteile der Plattform beschrieben, die sich auf die Erfüllung von Complianceanforderungen in den USA zentriert befinden.

> [!Tip]
> Möglicherweise möchten Sie die Tabellen mit Informationen in der Dienstbeschreibung in eine Excel-Arbeitsmappe übertragen und zwei Spalten hinzufügen: Relevant für meine Organisation **Y/N** und Erfüllt die Anforderungen meiner Organisation **Y/N**. Anschließend können Sie diese Liste zusammen mit Ihren Kollegen überprüfen, um zu bestätigen, dass dieser Dienst den Anforderungen Ihrer Organisation entspricht.

|    |     |
|-----------|------------|
| ![Ein Symbol mit Entscheidungspunkten](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Microsoft 365 Government – GCC für Ihre Organisation geeignet ist.</li><li>Vergewissern Sie sich, dass Ihre Organisation die Berechtigungsanforderungen erfüllt.</li></ul> |

> [!Note]
> Microsoft 365 Government – GCC ist nur in den USA verfügbar. Kunden von Behörden außerhalb der USA können aus einer Reihe von [Microsoft 365 Government-Plänen auswählen.](https://products.office.com/en/government/compare-office-365-government-plans)


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>Schritt 2: Für Microsoft 365 Government bewerben – GCC

Nachdem Sie entschieden haben, dass dieser Dienst für Ihre Organisation richtig ist, starten Sie hier den Prozess der Bewerbung [für diesen Dienst.](https://products.office.com/government/eligibility-validation)

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>Schritt 3: Microsoft 365 Government – GCC-Standardsicherheitseinstellungen.

Wir empfehlen, sich Zeit zu [](enable-features-office-365.md) nehmen, ihre Administrator- und Sicherheitseinstellungen sorgfältig zu überprüfen, bevor Sie sie ändern, und die Auswirkungen auf die Compliance zu berücksichtigen, bevor Sie Änderungen an den Standardsicherheitseinstellungen vornehmen.

|    |     |
|-----------|------------|
| ![Symbol, das einen Entscheidungspunkt darstellt](media/audio_conferencing_image7.png) <br/>Entscheidungspunkt|<ul><li>Entscheiden Sie, ob Sie eine der standardmäßigen Microsoft 365 Government - GCC-Sicherheitseinstellungen ändern, um zunächst die Auswirkungen aller Änderungen zu verstehen, die Sie möglicherweise vornehmen.</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>Schritt 4: Verstehen Sie, welche Funktionen derzeit standardmäßig nicht verfügbar oder deaktiviert sind.

Um den Anforderungen unserer Cloudkunden in der Regierung gerecht zu werden, gibt es einige Unterschiede zwischen Microsoft 365 Government - GCC- und Enterprise-Plänen. In der folgenden Tabelle finden Sie Informationen zu den verfügbaren Features.

[Beschreibung des Microsoft Teams-Diensts](/office365/servicedescriptions/teams-service-description)

> [!Note]
> Sobald andere Workloads in der GCC-Cloud vollständig verfügbar sind, werden sie in Teams verfügbar sein, wenn alle zusätzlichen Integrationsarbeiten abgeschlossen sind.


|    |     |
|-----------|------------|
| ![Symbol, das einen Entscheidungspunkt darstellt](media/audio_conferencing_image7.png) <br/>Entscheidungspunkt|<ul><li>Entscheiden Sie, ob der Featuresatz "Teams" den Anforderungen Ihrer Organisation entspricht.</li></ul> |

## <a name="step-5-plan-for-governance"></a>Schritt 5: Planen der Governance

Bestimmen Sie Ihre Anforderungen an governance und wie Sie diese erfüllen können. Weitere Informationen finden Sie [unter Planen der Governance in Teams.](plan-teams-governance.md)

|    |     |
|-----------|------------|
| ![Symbol, das einen Entscheidungspunkt darstellt](media/audio_conferencing_image7.png) <br/>Entscheidungspunkt|<ul><li>Ermitteln und dokumentieren Sie Ihre Governanceanforderungen nach den Richtlinien in [Plan for Governance in Teams.](plan-teams-governance.md)</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>Schritt 6: Bereitstellen von Teams für die Zusammenarbeit

Folgen Sie nach dem Onboarding bei Microsoft 365 Government – GCC dem empfohlenen Bereitstellungspfad unter So [wird's:](./deploy-overview.md)Rollout von Microsoft Teams beschrieben. Achten Sie darauf, sich mit Ihrem Adoptions- und Änderungsverwaltungsteam und den Teams-Champions zu beschäftigen.

Sie können auch mit [FastTrack](https://www.microsoft.com/fasttrack) oder Ihrem ausgewählten Partner zusammenarbeiten, um den Dienst zu integrieren.

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>Schritt 7: Bereitstellen von Teams für Besprechungen und Sprachnachrichten

Dies ist auch ein guter Zeitpunkt, um Teams mit Ihrer breiteren Stakeholdergruppe zu verwenden, um mit der Planung für das Roll out von Besprechungen und [Cloud-Sprachfeatures zu beginnen.](./cloud-voice-landing-page.md)