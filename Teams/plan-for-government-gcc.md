---
title: Microsoft 365 Behörden – GCC Bereitstellungen
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Leitfaden für IT-Profis, um Microsoft 365 Bereitstellungen in Entitäten vordrangen, die Daten verarbeiten, die US-Behörden-Vorschriften unterliegen
ms.localizationpriority: medium
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
ms.openlocfilehash: a3013b89ab384ca3f66c04bee06ccbbaf57445ff
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727604"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Planen von Microsoft 365 Government – GCC-Bereitstellungen

Dieser Leitfaden ist für IT-Profis, die Bereitstellungen von Microsoft 365 in US-Bundesstaaten, Bundesstaaten, lokalen, lokalen, juristischen oder neuen Behörden oder anderen Unternehmen treiben, die Daten verarbeiten, die staatlichen Vorschriften und Anforderungen unterliegen, wobei die Verwendung von Microsoft 365 Government - GCC diesen Anforderungen entspricht. Neuer 26. März 2020: Verpassen Sie nicht unseren herunterladbaren [Schnellstartleitfaden für GCC.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)

> [!IMPORTANT]
> Microsoft Teams der Virusvirus -Pandemic (COVID-19) zu einer enormen Menge an Onlineanrufen und Audio-/Videokonferenzen bei.<br/>
> 
>Als Reaktion auf die bisher beispiellose Zunahme der Anrufe und um Kontinuität und Verfügbarkeit sicherzustellen, lässt Microsoft zu, dass Microsoft Teams GCC-Audio-/Videoserver die Verarbeitungskapazität in unseren kommerziellen Rechenzentren sowie in unseren Rechenzentren der Regierung nutzen.<br/>
> 
>Diese Audio-/Videoserver befinden sich innerhalb Microsoft Azure FedRAMP High-Grenzwertservers in den USA und speichern keine Kundeninhalte. Diese Server verarbeiten jedoch Audio- und Videodaten für Anrufe und Konferenzen und werden während dieses Zwischenzeitraums von unseren kommerziellen Mitarbeitern verwendet.<br/>
> 
>Qualifiziertes, überprüftes Personal überwacht diese Server auf potenziellen Zugriff auf Kundendaten, indem interaktive Anmeldungen bei diesen Servern überprüft werden. Qualifizierte Mitarbeiter erfüllen GCC Anforderungen für den Zugriff auf Kundeninhalte. Details zu den Prüfungsanforderungen finden Sie in der [GCC DesDiensts.](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)<br/>
> 
>Vielen Dank für Ihre Unterstützung, da wir Maßnahmen ergreifen, um sicherzustellen, dass unsere Dienste in diesen außergewöhnliche Zeiten verfügbar und zuverlässig bleiben.<br/>


> [!NOTE]
> Wenn Ihre Organisation die Berechtigungsanforderungen für Microsoft 365 Government – GCC bereits erfüllt und für das Programm angewendet und für das Programm akzeptiert wurde, können Sie die Schritte 1 und 2 überspringen und direkt mit Schritt 3 fortgehen. 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>Schritt 1: Bestimmen Sie, ob Ihre Organisation Microsoft 365 Government - GCC und die Berechtigungsanforderungen erfüllt. 

Die Microsoft 365 Government - GCC-Umgebung bietet Compliance mit den anforderungen der US-Regierung für Clouddienste, einschließlich FedRAMP Moderate, und Anforderungen für kriminelle Steuerinformationssysteme (CJI- und FTI-Datentypen).

Organisationen profitieren nicht nur von den Features und Funktionen von Microsoft 365, sondern auch von den folgenden Features, die für Microsoft 365 Government -GCC:

-   Die Kundeninhalte Ihrer Organisation sind logisch von Kundeninhalten in kommerziellen Diensten Microsoft 365 Microsoft getrennt.
-   Die Kundeninhalte Ihrer Organisation werden in den USA gespeichert.
-   Der Zugriff auf die Kundeninhalte Ihrer Organisation ist auf angezeigte Microsoft-Mitarbeiter beschränkt.
-   Microsoft 365 Government – GCC Zertifizierungen und Zertifikate entsprechen, die für Kunden im öffentlichen US-Unternehmen erforderlich sind.

Weitere Informationen zum Angebot "Microsoft 365 Government - GCC für US Government"-Kunden finden Sie unter [Microsoft 365 Government-Pläne](https://products.office.com/government/compare-office-365-government-plans), einschließlich [Anspruchsvoraussetzungen.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)

In [Microsoft 365 Beschreibung des US Government-Diensts](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) werden die Vorteile der Plattform beschrieben, die sich auf erfüllende Complianceanforderungen in den Vereinigten Staaten zentriert befinden.

> [!Tip]
> Möglicherweise möchten Sie die Informationstabellen in der Dienstbeschreibung in eine Excel-Arbeitsmappe übertragen und zwei Spalten hinzufügen: Relevant für meine Organisation **Y/N** und Entspricht den Anforderungen meiner Organisation **Y/N**. Anschließend können Sie diese Liste mit Ihren Kollegen überprüfen, um zu bestätigen, dass dieser Dienst den Anforderungen Ihrer Organisation entspricht.

|    |     |
|-----------|------------|
| ![Symbol mit Entscheidungspunkten](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, Microsoft 365 Government - GCC für Ihre Organisation geeignet ist.</li><li>Vergewissern Sie sich, dass Ihre Organisation die Berechtigungsanforderungen erfüllt.</li></ul> |

> [!Note]
> Microsoft 365 Government – GCC ist nur in den USA verfügbar. Kunden außerhalb der US-Regierung können unter einer Reihe von [Government Microsoft 365 wählen.](https://products.office.com/en/government/compare-office-365-government-plans)


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>Schritt 2: Apply for Microsoft 365 Government - GCC

Nachdem Sie sich entschieden haben, dass dieser Dienst für Ihre Organisation am richtigen ist, beginnen Sie hier den Prozess für [die Bewerbung für diesen Dienst.](https://products.office.com/government/eligibility-validation)

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>Schritt 3: Hier finden Microsoft 365 zu GCC " Government – GCC Standardsicherheitseinstellungen".

Wir empfehlen, sich vor derEn [](enable-features-office-365.md) Änderung Die Administrator- und Sicherheitseinstellungen sorgfältig zu überprüfen und vor Änderungen Auswirkungen auf die Compliance zu berücksichtigen, bevor Sie Änderungen an den standardmäßigen Sicherheitseinstellungen vornehmen.

|    |     |
|-----------|------------|
| ![Ein Symbol, das einen Entscheidungspunkt zeigt.](media/audio_conferencing_image7.png) <br/>Entscheidungspunkt|<ul><li>Entscheiden Sie, ob Sie eine der standardsicherheitseinstellungen von Microsoft 365 Government - GCC ändern und zuerst die Auswirkungen von Änderungen verstehen, die Sie möglicherweise vornehmen.</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>Schritt 4: Verstehen Sie, welche Funktionen derzeit standardmäßig nicht verfügbar oder deaktiviert sind.

Um den Anforderungen unserer Government Cloud-Kunden gerecht zu werden, gibt es einige Unterschiede zwischen Microsoft 365 Government – GCC und Enterprise Plänen. In der folgenden Tabelle finden Sie Informationen zu den verfügbaren Features.

[Microsoft Teams der Dienstbeschreibung](/office365/servicedescriptions/teams-service-description)

> [!Note]
> Sobald andere Workloads in der GCC-Cloud vollständig verfügbar sind, stehen sie in Teams zur Verfügung, sobald alle weiteren Integrationsarbeiten abgeschlossen sind.


|    |     |
|-----------|------------|
| ![Ein Symbol, das einen Entscheidungspunkt zeigt.](media/audio_conferencing_image7.png) <br/>Entscheidungspunkt|<ul><li>Entscheiden Sie, Teams Featuresatz den Anforderungen Ihrer Organisation entspricht.</li></ul> |

## <a name="step-5-plan-for-governance"></a>Schritt 5: Planen der Governance

Ermitteln Sie Ihre Anforderungen an Governance und wie Sie sie erfüllen können. Weitere Informationen [finden Sie unter Teams](plan-teams-governance.md) governance im Projekt.

|    |     |
|-----------|------------|
| ![Ein Symbol, das einen Entscheidungspunkt zeigt.](media/audio_conferencing_image7.png) <br/>Entscheidungspunkt|<ul><li>Ermitteln und dokumentieren Sie Ihre Governanceanforderungen, und folgen Sie den Richtlinien unter Planen der [Governance in Teams.](plan-teams-governance.md)</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>Schritt 6: Bereitstellen Teams für die Zusammenarbeit

Nachdem Sie bei Microsoft 365 Government – GCC onboarded wurden, folgen Sie den empfohlenen Bereitstellungspfaden, die [unter](./deploy-overview.md)So wird's Microsoft Teams. Achten Sie darauf, dass Sie mit Ihrem Übernahme- und Änderungsverwaltungsteam zusammenarbeiten und Teams werden.

Sie können auch mit [dem](https://www.microsoft.com/fasttrack) FastTrack oder dem ausgewählten Partner zusammenarbeiten, um den Dienst zu integrieren.

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>Schritt 7: Bereitstellen Teams für Besprechungen und Sprachanrufe

Dies ist auch ein guter Zeitpunkt, um Teams breitere Projektbeteiligtengruppe zu nutzen, um mit der Planung für das Roll out von Besprechungen und [Cloud-Sprachfeatures zu beginnen.](./cloud-voice-landing-page.md)