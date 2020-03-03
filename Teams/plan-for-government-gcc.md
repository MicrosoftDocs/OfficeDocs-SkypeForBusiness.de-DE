---
title: Planen von Microsoft 365 Government – GCC-Bereitstellungen – Microsoft Teams
author: lolajacobsen
ms.author: lolaj
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
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 51afc464b5f6d0fa698250d1255315535e383bf8
ms.sourcegitcommit: ed0ecb3b1250a23d3b91a5a33256aee1c3119db1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2020
ms.locfileid: "42374322"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Plan für Microsoft 365 Government-gcc-Bereitstellungen

Diese Anleitung richtet sich an IT-Experten, die Bereitstellungen von Office 365 in US-Bundes-, bundesstaatlichen, lokalen, Stammes-oder Gebietskörperschaften oder anderen Entitäten führen, die Daten verarbeiten, die behördlichen Vorschriften und Anforderungen unterliegen, wobei die Verwendung von Microsoft 365 Government-gcc ist geeignet, diese Anforderungen zu erfüllen.

> [!NOTE]
> Wenn Ihre Organisation bereits die Berechtigungsanforderungen von Microsoft 365 Government-gcc erfüllt und in das Programm übernommen und akzeptiert wurde, können Sie die Schritte 1 und 2 überspringen und direkt zu Schritt 3 wechseln. 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>Schritt 1: Ermitteln Sie, ob Ihre Organisation Microsoft 365 Government-gcc benötigt und die Anspruchsvoraussetzungen erfüllt. 

Die Microsoft 365 Government-gcc-Umgebung bietet die Einhaltung der Anforderungen der US-Regierung für Cloud-Dienste, einschließlich FedRAMP moderat, und Anforderungen für die Strafjustiz und die föderalen Steuer Informationssysteme (CJI-und FTI-Datentypen).

Neben den Features und Funktionen von Office 365 profitieren Organisationen von den folgenden Features, die für Microsoft 365 Government-gcc einzigartig sind:

-   Der Kunden Inhalt Ihrer Organisation wird logisch von Kundeninhalten in den kommerziellen Office 365-Diensten von Microsoft getrennt.
-   Der Kunden Inhalt Ihrer Organisation wird in den Vereinigten Staaten gespeichert.
-   Der Zugriff auf die Kunden Inhalte Ihrer Organisation ist auf geschirmte Microsoft-Mitarbeiter beschränkt.
-   Microsoft 365 Government-gcc erfüllt Zertifizierungen und Akkreditierungen, die für Kunden im öffentlichen Dienst in den USA erforderlich sind.

Weitere Informationen zum Microsoft 365 Government-gcc-Angebot für US-Government-Kunden finden Sie unter [Office 365 Government-Pläne](https://products.office.com/government/compare-office-365-government-plans), einschließlich der [Anspruchsvoraussetzungen](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).

Die [Office 365 US Government Service Description](https://technet.microsoft.com/library/mt774581.aspx) beschreibt die Vorteile der Plattform, die sich auf die Erfüllung der Compliance-Anforderungen in den USA konzentrieren.

> [!Tip]
> Möglicherweise möchten Sie die Tabellen mit Informationen in der Dienstbeschreibung in eine Excel-Arbeitsmappe übertragen und zwei Spalten hinzufügen, die **für meine Organisation y/n relevant** sind und **den Anforderungen meiner Organisation y/n entsprechen**. Sie können diese Liste dann mit ihren Kollegen überprüfen, um zu bestätigen, dass dieser Dienst den Anforderungen Ihrer Organisation entspricht.

|    |     |
|-----------|------------|
| ![Ein Symbol mit Entscheidungspunkten](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte|<ul><li>Entscheiden Sie, ob Microsoft 365 Government-gcc für Ihre Organisation geeignet ist.</li><li>Vergewissern Sie sich, dass Ihre Organisation die Berechtigungsanforderungen erfüllt.</li></ul> |

> [!Note]
> Microsoft 365 Government-gcc steht nur in den Vereinigten Staaten zur Verfügung. Kunden außerhalb der US-Regierung können aus einer Reihe von [Office 365 Government-Plänen](https://products.office.com/en/government/compare-office-365-government-plans)wählen.


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>Schritt 2: Bewerben für Microsoft 365 Government-gcc

Nachdem Sie entschieden haben, dass dieser Dienst für Ihre Organisation richtig ist, starten Sie den Prozess der [Bewerbung für diesen Dienst hier](https://products.office.com/government/eligibility-validation).

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>Schritt 3: Grundlegendes zu Microsoft 365 Government-gcc-Standardsicherheitseinstellungen.

Wir empfehlen, dass Sie sich Zeit nehmen, um Ihre [Administrator-und Sicherheitseinstellungen](enable-features-office-365.md) sorgfältig zu überprüfen, bevor Sie Sie ändern, und die Auswirkungen auf die Kompatibilität berücksichtigen, bevor Sie Änderungen an den Standardsicherheitseinstellungen vornehmen.

|    |     |
|-----------|------------|
| ![Ein Symbol, das einen Entscheidungspunkt darstellt](media/audio_conferencing_image7.png) <br/>Entscheidungspunkt|<ul><li>Entscheiden Sie, ob Sie die standardmäßigen Sicherheitseinstellungen für Microsoft 365 Government-gcc ändern möchten, um die Auswirkungen von Änderungen, die Sie möglicherweise vornehmen, zunächst zu verstehen.</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>Schritt 4: Sie wissen, welche Funktionen zurzeit nicht verfügbar oder standardmäßig deaktiviert sind. 

Um den Anforderungen unserer Government Cloud-Kunden gerecht zu werden, gibt es einige Unterschiede zwischen den Microsoft 365 Government-gcc-und Enterprise-Plänen. Informationen zu den verfügbaren Features finden Sie in der folgenden Tabelle.

|                             | Feature                     | GCC            |
|-----------------------------|-----------------------------|----------------|
| Basis | Anmeldung | Verfügbar |
| | Anwesenheit | Verfügbar |
| | Einheitliche Anwesenheitsinformationen (Skype for Business und Teams Unified) | Verfügbar |
| Aktivität | Feed | Verfügbar |
|  | Meine Aktivitäten | Verfügbar |
| Chat | Unterhaltung | Verfügbar |
| | Dateien | Verfügbar |
| | Organigramm | Verfügbar |
| | Aktivität | Verfügbar |
| | Interop (1:1 Teams – Skype for Business-Chat) | Verfügbar |
| Teams | Kanal Nachricht | Verfügbar |
| | Kanaldateien | Verfügbar |
| | OneNote-Registerkarte | Auf dem Government-Rückstand |
| | Senden eines Kanals per e-Mail | Nicht verfügbar |
| | Mitglied hinzufügen | Verfügbar |
| | Gastzugriff | Verfügbar |
| Besprechungen | Besprechung planen | Verfügbar |
| | Teilnehmen an einer Besprechung | Verfügbar |
| | VoIP-Besprechung | Verfügbar |
| | Desktopfreigabe | Verfügbar |
| | Geben und übernehmen der Steuerung in der Freigabe | Verfügbar |
| | Verbinden von einem Konferenzraum | Verfügbar |
| | Anonyme Verknüpfung | Verfügbar |
| | Cloud-Aufzeichnung | Verfügbar |
| | Besprechungsnotizen | Verfügbar |
| | Liveereignisse | Verfügbar |
| | Verbund Besprechungen | Verfügbar |
| | Surface Hub-Unterstützung | Verfügbar |
| Anrufe | Kontakte | Verfügbar |
| | Verlauf | Verfügbar |
| | Voicemail | Verfügbar |
| | VoIP-Anruf | Verfügbar |
| | Skype for Business – Teams anrufen | Verfügbar |
| | Anrufpläne | Verfügbar |
| | Audiokonferenzen (dadurch, dass Besprechungsteilnehmer über PSTN beitreten können) | Verfügbar |
| | Microsoft Phone-System Direktes Routing | Verfügbar |
| | Lobby für PSTN-Anrufer | Verfügbar |
| | Anrufwarteschlange | Verfügbar |
| | Unterstützung von Boss und Stellvertretung | Verfügbar |
| | Beratende und sichere Übertragung | Verfügbar |
| | Durchbruch nicht stören | Verfügbar |
| | Markanter Ring | Verfügbar |
| | 1:1-Gruppen-Anruf Eskalation mit Teams, Skype for Business und PSTN-Teilnehmern | Verfügbar |
| | Weiterleiten an Gruppe | Verfügbar |
| | Übertragung an PSTN-Anruf | Verfügbar |
| | Anrufpläne für Notrufe | Verfügbar |
| | Unterstützung für vorhandene zertifizierte SIP-Telefone | Verfügbar |
| | USB-HID | Verfügbar |
| | eDiscovery für Anrufe und Besprechungen | Verfügbar |
| | Automatische Telefonzentrale der Organisation | Verfügbar |
| | Support für Skype-Nutzer – Teams anrufen | Verfügbar |
| Dateien | Jüngsten | Verfügbar |
| | Microsoft Teams | Verfügbar |
| Speichern | App Store | Verfügbar |
| Suche | Meldungen | Verfügbar |
| | Kontakte | Verfügbar |
| | Dateien | Verfügbar |
| | Schrägstrich Befehle | Verfügbar |
| Compliance | Kompatibilitäts Inhaltssuche | Verfügbar |
| | Aufbewahrungs | Verfügbar |
| | Überwachungsprotokoll Suche | Verfügbar |
| | Rechtliche Aufbewahrung | Verfügbar |
| | eDiscovery | Verfügbar |

> [!Note]
> Sobald andere Arbeitslasten in der gcc-Cloud vollständig verfügbar sind, werden Sie in Teams verfügbar, wenn alle zusätzlichen Integrationsarbeiten abgeschlossen sind.


|    |     |
|-----------|------------|
| ![Ein Symbol, das einen Entscheidungspunkt darstellt](media/audio_conferencing_image7.png) <br/>Entscheidungspunkt|<ul><li>Entscheiden Sie, ob der Featuresatz für Teams die Anforderungen Ihrer Organisation erfüllt.</li></ul> |

## <a name="step-5-plan-for-governance"></a>Schritt 5: Plan für Governance

Ermitteln Sie Ihre Anforderungen für Governance und wie Sie Sie erfüllen können. Weitere Informationen finden Sie unter [Planen von Governance in Teams](plan-teams-governance.md) .

|    |     |
|-----------|------------|
| ![Ein Symbol, das einen Entscheidungspunkt darstellt](media/audio_conferencing_image7.png) <br/>Entscheidungspunkt|<ul><li>Ermitteln und dokumentieren Sie Ihre Governance-Anforderungen, und befolgen Sie die Richtlinien in [Plan for Governance in Teams](plan-teams-governance.md).</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>Schritt 6: Bereitstellen von Teams für die Zusammenarbeit

Nachdem Sie die Microsoft 365 Government – gcc installiert haben, befolgen Sie den empfohlenen Bereitstellungspfad, der in [Anleitung zum Rollout von Microsoft Teams](How-to-roll-out-teams.md)beschrieben wird. Stellen Sie sicher, dass Sie sich mit Ihrem Adoptions-, Change Management-und Team-Champion beschäftigen.

Sie können auch mit der [Zusammenarbeit](https://www.microsoft.com/fasttrack) oder dem ausgewählten Partner an Bord des Diensts arbeiten.

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>Schritt 7: Bereitstellen von Teams für Besprechungen und Sprachanrufe

Dies ist auch eine gute Zeit, um Teams für Ihre breitere Interessengruppe zu verwenden, um mit der Planung für das Rollout von Besprechungen und [Cloud-Sprachfeatures](cloud-voice-deployment.md)zu beginnen.

