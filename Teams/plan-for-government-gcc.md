---
title: Microsoft 365 Government – GCC-Bereitstellungen
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Leitfaden für IT-Profis zur Laufwerkierung von Microsoft 365-Bereitstellungen in Entitäten, die Daten verarbeiten, die us-Behörden-Bestimmungen unterliegen
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
ms.openlocfilehash: a55c7440b7d3183e93391ecc0e4f8781ba7b690f
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013299"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Planen für Microsoft 365 Government – GCC-Bereitstellungen

Dieser Leitfaden ist für IT-Profis, die Bereitstellungen von Microsoft 365 in Bundes-, Bundesstaats-, Landes-, lokalen, juristischen oder neuen Behörden oder anderen Unternehmen treiben, die mit Daten umgehen, die staatlichen Vorschriften und Anforderungen unterliegen, wobei die Verwendung von Microsoft 365 Government - GCC diesen Anforderungen entspricht. Neuer 26. März 2020: Verpassen Sie nicht unseren herunterladbaren [Schnellstartleitfaden für GCC.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)

> [!IMPORTANT]
> Microsoft Teams hat aufgrund der Virusvirus-Pandemic (COVID-19) einen enormen Anstieg bei Onlineanrufen und Audio-/Videokonferenzen zu erleben.<br/>
> 
>Als Reaktion auf die bisher beispiellose Zunahme der Anrufe und um Kontinuität und Verfügbarkeit sicherzustellen, lässt Microsoft Microsoft Teams GCC-Audio-/Videoserver in unseren kommerziellen Rechenzentren sowie in unseren Regierungsdatencentern Verarbeitungskapazität nutzen.<br/>
> 
>Diese Audio-/Videoserver befinden sich auf den Microsoft Azure FedRAMP High-Grenzwertservern in den USA und speichern keine Kundeninhalte. Diese Server verarbeiten jedoch Audio- und Videodaten für Anrufe und Konferenzen und werden während dieses Zwischenzeitraums von unseren kommerziellen Mitarbeitern verwendet.<br/>
> 
>Qualifiziertes, überprüftes Personal überwacht diese Server auf potenziellen Zugriff auf Kundendaten, indem interaktive Anmeldungen bei diesen Servern überprüft werden. Qualifizierte Mitarbeiter erfüllen GCC-Anforderungen für den Zugriff auf Kundeninhalte. Details zu den Prüfungsanforderungen finden Sie in der [Beschreibung des GCC-Diensts.](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)<br/>
> 
>Vielen Dank für Ihre Unterstützung, da wir Maßnahmen ergreifen, um sicherzustellen, dass unsere Dienste in diesen außergewöhnliche Zeiten verfügbar und zuverlässig bleiben.<br/>


> [!NOTE]
> Wenn Ihre Organisation die Berechtigungsanforderungen für Microsoft 365 Government - GCC bereits erfüllt und für das Programm angewendet und für das Programm akzeptiert wurde, können Sie die Schritte 1 und 2 überspringen und direkt mit Schritt 3 fortgehen. 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>Schritt 1: Bestimmen Sie, ob Ihre Organisation Microsoft 365 Government - GCC benötigt und die Berechtigungsanforderungen erfüllt. 

Die Microsoft 365 Government - GCC-Umgebung bietet Compliance mit den US-Behördenanforderungen für Clouddienste, einschließlich FedRAMP Moderate, und Anforderungen für kriminelle handlungen und steuerbefreite Informationssysteme (CJI- und FTI-Datentypen).

Organisationen profitieren nicht nur von den Features und Funktionen von Microsoft 365, sondern auch von den folgenden Features, die Microsoft 365 Government - GCC einzigartig sind:

-   Die Kundeninhalte Ihrer Organisation sind logisch von Kundeninhalten in kommerziellen Microsoft 365-Diensten von Microsoft getrennt.
-   Die Kundeninhalte Ihrer Organisation werden in den USA gespeichert.
-   Der Zugriff auf die Kundeninhalte Ihrer Organisation ist auf angezeigte Microsoft-Mitarbeiter beschränkt.
-   Microsoft 365 Government – GCC entspricht den Zertifizierungen und Zertifizierungen, die für Kunden des öffentlichen US-Amerikanischen Gesundheitswesens erforderlich sind.

Weitere Informationen zum Microsoft 365 Government - GCC-Angebot für US Government-Kunden finden Sie unter [Microsoft 365](https://products.office.com/government/compare-office-365-government-plans)Government-Pläne, einschließlich [Berechtigungsanforderungen.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)

In [der Beschreibung des Microsoft 365 US Government-Diensts](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) werden die Vorteile der Plattform beschrieben, die sich auf erfüllende Complianceanforderungen in den USA zentriert befinden.

> [!Tip]
> Möglicherweise möchten Sie die Tabellen mit Informationen in der Dienstbeschreibung in eine Excel-Arbeitsmappe übertragen und zwei Spalten hinzufügen: Relevant für meine Organisation **Y/N** und Entspricht den Anforderungen meiner Organisation **Y/N**. Anschließend können Sie diese Liste mit Ihren Kollegen überprüfen, um zu bestätigen, dass dieser Dienst den Anforderungen Ihrer Organisation entspricht.

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Ein Symbol, das Entscheidungspunkte darstellt.](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Microsoft 365 Government - GCC für Ihre Organisation geeignet ist.</li><li>Vergewissern Sie sich, dass Ihre Organisation die Berechtigungsanforderungen erfüllt.</li></ul> |

> [!Note]
> Microsoft 365 Government – GCC steht nur in den USA zur Verfügung. Kunden außerhalb der US-Regierung können aus einer Reihe von [Microsoft 365 Government-Plänen auswählen.](https://products.office.com/en/government/compare-office-365-government-plans)


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>Schritt 2: Bewerben für Microsoft 365 Government - GCC

Nachdem Sie sich entschieden haben, dass dieser Dienst für Ihre Organisation am richtigen ist, beginnen Sie hier den Prozess für [die Bewerbung für diesen Dienst.](https://products.office.com/government/eligibility-validation)

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>Schritt 3: Hier finden Sie Informationen zu den standardmäßigen Sicherheitseinstellungen von Microsoft 365 Government – GCC.

Wir empfehlen, sich vor derEn [](enable-features-office-365.md) Änderung Die Administrator- und Sicherheitseinstellungen sorgfältig zu überprüfen und vor Änderungen Auswirkungen auf die Compliance zu berücksichtigen, bevor Sie Änderungen an den standardmäßigen Sicherheitseinstellungen vornehmen.

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Ein Symbol, das einen Entscheidungspunkt darstellt.](media/audio_conferencing_image7.png) <br/>Entscheidungspunkt|<ul><li>Entscheiden Sie, ob Sie eine der Standardsicherheitseinstellungen von Microsoft 365 Government - GCC ändern möchten, um zuerst die Auswirkungen von Änderungen zu verstehen, die Sie möglicherweise vornehmen.</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>Schritt 4: Verstehen Sie, welche Funktionen derzeit standardmäßig nicht verfügbar oder deaktiviert sind.

Um den Anforderungen unserer Cloud-Kunden für Behörden gerecht zu werden, gibt es einige Unterschiede zwischen den Plänen Microsoft 365 Government – GCC und Enterprise. In der folgenden Tabelle finden Sie Informationen zu den verfügbaren Features.

[Beschreibung des Microsoft Teams-Diensts](/office365/servicedescriptions/teams-service-description)

> [!Note]
> Sobald andere Workloads vollständig in der GCC-Cloud verfügbar sind, stehen sie in Teams zur Verfügung, sobald alle weiteren Integrationsarbeiten abgeschlossen sind.


|&nbsp;|&nbsp;|
|-----------|------------|
| ![Ein Symbol, das einen Entscheidungspunkt darstellt.](media/audio_conferencing_image7.png) <br/>Entscheidungspunkt|<ul><li>Entscheiden Sie, ob der Teams-Featuresatz den Anforderungen Ihrer Organisation entspricht.</li></ul> |

## <a name="step-5-plan-for-governance"></a>Schritt 5: Planen der Governance

Ermitteln Sie Ihre Anforderungen an Governance und wie Sie sie erfüllen können. Weitere Informationen [finden Sie unter Planen der Governance in Teams.](plan-teams-governance.md)

|&nbsp;|&nbsp;|
|-----------|------------|
| ![Ein Symbol, das einen Entscheidungspunkt darstellt.](media/audio_conferencing_image7.png) <br/>Entscheidungspunkt|<ul><li>Ermitteln und dokumentieren Sie Ihre Governanceanforderungen, und folgen Sie den Richtlinien unter [Planen der Governance in Teams.](plan-teams-governance.md)</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>Schritt 6: Bereitstellen von Teams für die Zusammenarbeit

Nachdem Sie Microsoft 365 Government – GCC installiert haben, folgen Sie den empfohlenen Bereitstellungspfaden, die unter Rollout [von Microsoft Teams beschrieben sind.](./deploy-overview.md) Arbeiten Sie unbedingt mit Ihrem Adoption and Change Management-Team und den Teams-Champions zusammen.

Sie können auch mit [FastTrack](https://www.microsoft.com/fasttrack) oder dem ausgewählten Partner zusammenarbeiten, um den Dienst zu integrieren.

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>Schritt 7: Bereitstellen von Teams für Besprechungen und Sprachanrufe

Dies ist auch ein guter Zeitpunkt, um Teams mit Ihrer breiteren Gruppe der Projektbeteiligten zu verwenden, um mit der Planung für das Roll out von Besprechungen und [Cloud-Sprachfeatures zu beginnen.](./cloud-voice-landing-page.md)