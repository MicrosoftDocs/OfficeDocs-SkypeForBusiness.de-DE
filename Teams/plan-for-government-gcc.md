---
title: Office 365 Government-gcc-Bereitstellungen
author: lolajacobsen
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Leitfaden für IT-Experten zum Steuern von Office 365-Bereitstellungen in Entitäten, die Daten verarbeiten, die von der US-amerikanischen Regierung geregelt werden
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
ms.openlocfilehash: b93762c92d9681074124ba8ddb3fd066bdf8a60a
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665227"
---
# <a name="plan-for-office-365-government---gcc-deployments"></a>Plan für Office 365 Government-gcc-Bereitstellungen

Diese Anleitung richtet sich an IT-Experten, die Bereitstellungen von Office 365 in den US-Bundes-, bundesstaatlichen, lokalen, Stammes-oder Gebietskörperschaften oder anderen Entitäten steuern, die Daten verarbeiten, die behördlichen Vorschriften und Anforderungen unterliegen, wobei die Verwendung von Office 365 Government-gcc geeignet ist, diese Anforderungen zu erfüllen. Neuer März 26, 2020: verpassen Sie nicht unseren downloadbaren [schnell Start Leit Faden für gcc](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).

> [!IMPORTANT]
> Microsoft Teams erlebt aufgrund der Coronavirus (COVID-19)-Pandemie eine enorme Spitze bei Online-anrufen und Audio/Videokonferenzen.<br/>
> 
>Als Antwort auf die noch nie dagewesene Zunahme von Anrufen und die Gewährleistung von Kontinuität und Verfügbarkeit ermöglicht Microsoft Microsoft Teams gcc-Audio/Video-Server die Nutzung der Verarbeitungskapazität in unseren kommerziellen Rechenzentren sowie in unseren Regierungs Rechenzentren.<br/>
> 
>Diese Audio/Video-Server befinden sich auf den Microsoft Azure FedRAMP-Grenz Servern in den Vereinigten Staaten und speichern keine Kunden Inhalte. Diese Server verarbeiten jedoch Audio-und Videodaten für Anrufe und Konferenzen und sind während dieser Zwischenzeit unter unseren kaufmännischen Mitarbeitern tätig.<br/>
> 
>Qualifizierte, geprüfte Mitarbeiter überwachen diese Server auf potenziellen Zugriff auf Kundendaten, indem Sie alle interaktiven log-ons auf diesen Servern überprüfen. Qualifiziertes Personal erfüllt die Anforderungen von gcc für den Zugriff auf Kunden Inhalte. Details zu den Prüfungsanforderungen finden Sie in der [gcc-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).<br/>
> 
>Vielen Dank für Ihre Unterstützung, während wir Schritte Unternehmen, um sicherzustellen, dass unsere Dienste in diesen außergewöhnlichen Zeiten verfügbar und zuverlässig sind.<br/>


> [!NOTE]
> Wenn Ihre Organisation bereits die Berechtigungsanforderungen von Office 365 Government-gcc erfüllt und in das Programm übernommen und akzeptiert wurde, können Sie die Schritte 1 und 2 überspringen und direkt zu Schritt 3 wechseln. 

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---gcc-and-meets-eligibility-requirements"></a>Schritt 1: Ermitteln Sie, ob Ihre Organisation Office 365 Government-gcc benötigt und die Anspruchsvoraussetzungen erfüllt. 

Die Office 365 Government-gcc-Umgebung bietet die Einhaltung der US-Government-Anforderungen für Cloud-Dienste, einschließlich FedRAMP moderate, und Anforderungen für Strafjustiz-und föderale Steuerinformationssystem (CJI-und FTI-Datentypen).

Neben den Features und Funktionen von Office 365 profitieren Organisationen von den folgenden Features, die für Office 365 Government-gcc einzigartig sind:

-   Der Kunden Inhalt Ihrer Organisation wird logisch von Kundeninhalten in den kommerziellen Office 365-Diensten von Microsoft getrennt.
-   Der Kunden Inhalt Ihrer Organisation wird in den Vereinigten Staaten gespeichert.
-   Der Zugriff auf die Kunden Inhalte Ihrer Organisation ist auf geschirmte Microsoft-Mitarbeiter beschränkt.
-   Office 365 Government-gcc entspricht Zertifizierungen und Akkreditierungen, die für Kunden im öffentlichen Dienst in den USA erforderlich sind.

Weitere Informationen zum Office 365 Government-gcc-Angebot für US-Government-Kunden finden Sie unter [Office 365 Government-Pläne](https://products.office.com/government/compare-office-365-government-plans), einschließlich der [Anspruchsvoraussetzungen](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).

Die [Office 365 US Government Service Description](https://technet.microsoft.com/library/mt774581.aspx) beschreibt die Vorteile der Plattform, die sich auf die Erfüllung der Compliance-Anforderungen in den USA konzentrieren.

> [!Tip]
> Möglicherweise möchten Sie die Tabellen mit Informationen in der Dienstbeschreibung in eine Excel-Arbeitsmappe übertragen und zwei Spalten hinzufügen, die **für meine Organisation y/n relevant** sind und **den Anforderungen meiner Organisation y/n entsprechen**. Sie können diese Liste dann mit ihren Kollegen überprüfen, um zu bestätigen, dass dieser Dienst den Anforderungen Ihrer Organisation entspricht.

|    |     |
|-----------|------------|
| ![Ein Symbol mit Entscheidungspunkten](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Office 365 Government-gcc für Ihre Organisation geeignet ist.</li><li>Vergewissern Sie sich, dass Ihre Organisation die Berechtigungsanforderungen erfüllt.</li></ul> |

> [!Note]
> Office 365 Government-gcc steht nur in den Vereinigten Staaten zur Verfügung. Kunden außerhalb der US-Regierung können aus einer Reihe von [Office 365 Government-Plänen](https://products.office.com/en/government/compare-office-365-government-plans)wählen.


## <a name="step-2-apply-for-office-365-government---gcc"></a>Schritt 2: Bewerben für Office 365 Government-gcc

Nachdem Sie entschieden haben, dass dieser Dienst für Ihre Organisation richtig ist, starten Sie den Prozess der [Bewerbung für diesen Dienst hier](https://products.office.com/government/eligibility-validation).

## <a name="step-3-understand-office-365-government---gcc-default-security-settings"></a>Schritt 3: Grundlegendes zu Office 365 Government-gcc-Standardsicherheitseinstellungen.

Wir empfehlen, dass Sie sich Zeit nehmen, um Ihre [Administrator-und Sicherheitseinstellungen](enable-features-office-365.md) sorgfältig zu überprüfen, bevor Sie Sie ändern, und die Auswirkungen auf die Kompatibilität berücksichtigen, bevor Sie Änderungen an den Standardsicherheitseinstellungen vornehmen.

|    |     |
|-----------|------------|
| ![Symbol, das einen Entscheidungspunkt darstellt](media/audio_conferencing_image7.png) <br/>Entscheidungspunkt|<ul><li>Entscheiden Sie, ob Sie die standardmäßigen Sicherheitseinstellungen von Office 365 Government-gcc ändern möchten, um die Auswirkungen von Änderungen, die Sie möglicherweise vornehmen, zunächst zu verstehen.</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>Schritt 4: Sie wissen, welche Funktionen zurzeit nicht verfügbar oder standardmäßig deaktiviert sind.

Um den Anforderungen unserer Government Cloud-Kunden gerecht zu werden, gibt es einige Unterschiede zwischen Office 365 Government-gcc-und Enterprise-Plänen. Informationen zu den verfügbaren Features finden Sie in der folgenden Tabelle.

[Microsoft Teams-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

> [!Note]
> Sobald andere Arbeitslasten in der gcc-Cloud vollständig verfügbar sind, werden Sie in Teams verfügbar, wenn alle zusätzlichen Integrationsarbeiten abgeschlossen sind.


|    |     |
|-----------|------------|
| ![Symbol, das einen Entscheidungspunkt darstellt](media/audio_conferencing_image7.png) <br/>Entscheidungspunkt|<ul><li>Entscheiden Sie, ob der Featuresatz für Teams die Anforderungen Ihrer Organisation erfüllt.</li></ul> |

## <a name="step-5-plan-for-governance"></a>Schritt 5: Plan für Governance

Ermitteln Sie Ihre Anforderungen für Governance und wie Sie Sie erfüllen können. Weitere Informationen finden Sie unter [Planen von Governance in Teams](plan-teams-governance.md) .

|    |     |
|-----------|------------|
| ![Symbol, das einen Entscheidungspunkt darstellt](media/audio_conferencing_image7.png) <br/>Entscheidungspunkt|<ul><li>Ermitteln und dokumentieren Sie Ihre Governance-Anforderungen, und befolgen Sie die Richtlinien in [Plan for Governance in Teams](plan-teams-governance.md).</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>Schritt 6: Bereitstellen von Teams für die Zusammenarbeit

Nachdem Sie die Office 365 Government – gcc installiert haben, befolgen Sie den empfohlenen Bereitstellungspfad, der in [Anleitung zum Rollout von Microsoft Teams](How-to-roll-out-teams.md)beschrieben wird. Stellen Sie sicher, dass Sie sich mit Ihrem Adoptions-, Change Management-und Team-Champion beschäftigen.

Sie können auch mit der [Zusammenarbeit](https://www.microsoft.com/fasttrack) oder dem ausgewählten Partner an Bord des Diensts arbeiten.

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>Schritt 7: Bereitstellen von Teams für Besprechungen und Sprachanrufe

Dies ist auch eine gute Zeit, um Teams für Ihre breitere Interessengruppe zu verwenden, um mit der Planung für das Rollout von Besprechungen und [Cloud-Sprachfeatures](cloud-voice-deployment.md)zu beginnen.

