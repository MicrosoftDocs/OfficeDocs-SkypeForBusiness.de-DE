---
title: Sicherheitshandbuch für Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 08/21/2020
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: Anleitung zur sicheren Verwendung von Microsoft Teams auf einem gemeinsam genutzten Computer am Arbeitsplatz.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 45497c824cfc20644a59e35f7812b17058f61c2c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117053"
---
# <a name="use-microsoft-teams-securely-on-shared-computers"></a>Sicheres Verwenden von Microsoft Teams auf gemeinsam genutzten Computern

Wenn möglich, wird Unternehmen *empfohlen*, einen Zero Trust-Ansatz für Clientgeräte einzusetzen, indem sie Geräteverwaltungsfunktionen, die Durchsetzung von Gerätezustandsprüfungen und Richtlinien, Verschlüsselung auf Geräteebene und andere Sicherheitsfunktionen nutzen.

:::image type="content" source="media/tp_ZeroTrustPrinciples.PNG" alt-text="Zero Trust-Abbildung zur Verdeutlichung der Zero Trust-Grundsätze – explizite Überprüfungen, niedrigste Berechtigungen und Annehmen von Sicherheitsverletzungen – in blauen Kreisen.":::

Administratoren können sehr sichere Bedingungen schaffen, indem sie auf Überprüfungen, niedrigste Berechtigungen und Annehmen von Sicherheitsverletzungen *bestehen*. Diese Standards führen zu Aktionen, die das Risiko sowohl für Benutzer als auch für Daten minimieren.

> [!TIP]
> Zur tiefer gehenden Untersuchung der Zero Trust-Grundsätze schauen Sie sich [diese Videos](/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537) an.

## <a name="tips-for-using-microsoft-teams-securely-from-a-shared-computer"></a>Tipps für eine sichere Verwendung von Microsoft Teams auf einem gemeinsam genutzten Computer

Auch wenn dies vielleicht nicht in allen Szenarien möglich oder praktikabel ist, sollten Sicherheitsadministratoren trotzdem unbedingt so gut wie möglich den Anleitungen für die Verwendung von Teams auf einem gemeinsam genutzten Computer oder einem nicht verwalteten Gerät folgen.

Es sollten Pläne entwickelt werden, die den Richtlinien möglichst genau entsprechen.

1. Nutzen Sie die Sicherheitsfunktionen der Betriebssystemplattform.
    1. Stellen Sie sicher, dass das Betriebssystem so konfiguriert ist, dass Updates vom Betriebssystemanbieter automatisch installiert werden (für Microsoft-Systeme wird dies über [**Windows Update**](https://support.microsoft.com/help/12373/windows-update-faq) erreicht). 
    1. Stellen Sie sicher, dass alle Geräteverschlüsselungsfunktionen wie z. B. [**bitlocker**](/windows/security/information-protection/bitlocker/bitlocker-overview) aktiviert sind und der für den Zugriff auf das Gerät verwendete Schlüssel gesichert ist.  Beachten Sie, dass die meisten modernen [**Windows 10-Geräte Bitlocker unterstützen**](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10). 
    1. Verwenden Sie Antivirusfunktionen wie diejenigen, die von [**Windows Defender**](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) auf Ihren Geräten bereitgestellt werden.
    1. Die Verwendung von [getrennten Benutzerkonten](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account) für jeden Benutzer des Systems wird dringend empfohlen.
    1. Vergeben oder verwenden Sie *keine* Administratorrechte für nicht administrative Funktionen (wie z. B. das Surfen im Web, das Ausführen von Teams usw.).

Wenn die oben genannten Richtlinien nicht eingehalten werden können, empfehlen wir die Anwendung zusätzlicher bewährter Methoden für Browsersicherheit:

1. Nutzen Sie Browsersicherheitsfunktionen.
    1. Verwenden Sie private Browsersitzungen, um Daten und Verlauf, die auf der Festplatte verbleiben, zu minimieren. Verwenden Sie z. B. [InPrivate-Browsen in Microsoft Edge](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate), [Inkognitobrowsing in Google Chrome](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en) bzw. die entsprechende Funktionen Ihres Browsers für private Browsersitzungen. 
    1. Es wird empfohlen, das Systemverhalten so zu ändern, dass *standardmäßig* private Browsersitzungen verwendet werden. 

2. Navigieren Sie zur [Web-App für Teams](https://teams.microsoft.com) (manchmal auch als *Webclient* bezeichnet), und verwenden Sie diese und nicht den herunterladbaren Teams-Client.

3. Wenn Sie mit der Verwendung des gemeinsam genutzten Computers fertig sind, müssen Sie folgende Schritte ausführen: 
    1. [Melden Sie sich bei Microsoft Teams ab](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487).
    1. Schließen Sie alle Registerkarten und Fenster des Browsers.
    1. Melden Sie sich vom Gerät ab.

Die oben aufgeführten Punkte sind keine umfassende Liste der bewährten Methoden oder Sicherheitskontrollen für alle Situationen, und in Ihrer Umgebung können möglicherweise zusätzliche Maßnahmen ergriffen werden (Sicherheitsadministratoren können sich beispielsweise für die Verwendung von sicheren Links und sicheren Anhängen für Teams entscheiden, wenn Sie [Office 365 ATP Plan 1 oder 2](/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2) verwenden). Diese Schritte sind jedoch ein Ausgangspunkt für die Erstellung von Anleitungen für die Verwendung von Teams auf gemeinsam genutzten Geräten.

## <a name="more-information"></a>Weitere Informationen

[Bitlocker in Configuration Manager](/mem/configmgr/protect/deploy-use/bitlocker/deploy-management-agent)

[BitLocker für Windows 10 in Intune](/mem/intune/protect/encrypt-devices)

[Sicherheitsmaßnahmen für den Endpunkt in Intune](/mem/intune/protect/endpoint-security)

[Aktivieren](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app) von Microsoft Defender Antivirus in Windows-Sicherheit und [Ausführen von Scans](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)

[Artikel zum Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus)

[Teams-Webclient/Teams-Web-App](./get-clients.md#web-client)

[Sicherheit und Microsoft Teams](./teams-security-guide.md)