---
title: Neues Direct-Routing
ms.reviewer: CarolynRowe
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: In diesem Artikel werden die neuen Informationen zu Direct-Routing beschrieben. Schauen Sie regelmäßig nach Updates zurück.
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 53a1c2730ebf6db06fb92ac2fc4e0873563c98ce
ms.sourcegitcommit: 9e868a155bcd20dd5dafdedcff091ff77ca7398b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2022
ms.locfileid: "64584329"
---
# <a name="whats-new-for-direct-routing"></a>Neues bei Direct-Routing

In diesem Artikel werden die neuen Informationen zu Direct-Routing beschrieben. Schauen Sie regelmäßig nach Updates zurück.

## <a name="sip-support"></a>SIP-Support

Am 1. Juni 2022 entfernt Microsoft die Unterstützung für sip-all.pstnhub.microsoft.com und sip-all.pstnhub.gov.teams.microsoft.us FQDNs aus der Direct-Routingkonfiguration.

Wenn vor dem 1. Juni keine Maßnahmen ergriffen werden, können die Benutzer keine Anrufe über Direct-Routing ausführen oder empfangen.

So vermeiden Sie Auswirkungen auf den Dienst

- Verwenden Sie die empfohlenen Subnetze (52.112.0.0/14 und 52.120.0.0/14) für beliebige Klassifizierungs- oder ACL-Regeln.
- Beenden Sie die Verwendung des sip-all-FQDNs, wenn Sie Sitzungsrand-Steuerelemente für direktes Routing konfigurieren.

Weitere Informationen finden Sie unter [Planen des direkten Routings](direct-routing-plan.md).

## <a name="tls-certificates"></a>TLS-Zertifikate

Microsoft 365 aktualisiert Teams Dienste für die Verwendung einer anderen Gruppe von Zertifizierungsstelle für Stammzertifikate.

Weitere Informationen und eine vollständige Liste der betroffenen Dienste finden Sie unter [TLS-Zertifikatänderungen an Microsoft 365, einschließlich Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/tls-certificate-changes-to-microsoft-365-services-including/ba-p/3249676).

## <a name="certificate-authorities"></a>Zertifizierungsstelle

Ab dem 1. Februar 2022 vertraut die Direct-Routing-SIP-Schnittstelle nur Zertifikaten, die von Zertifizierungsstelle signiert wurden, die Teil des Microsoft-Programms für vertrauenswürdige Stammzertifikate sind. Gehen Sie wie folgt vor, um Auswirkungen auf den Dienst zu vermeiden:

- Stellen Sie sicher, dass Ihr SBC-Zertifikat von einer Zertifizierungsstelle signiert ist, die Teil des Microsoft-Programms für vertrauenswürdige Stammzertifikate ist.
- Vergewissern Sie sich, dass die EKU-Erweiterung (Extended Key Usage) Ihres Zertifikats "Serverauthentifizierung" enthält.

Weitere Informationen zum Microsoft-Programm für vertrauenswürdige Stammzertifikate finden Sie unter [Programmanforderungen – Microsoft Trusted Root Program](/security/trusted-root/program-requirements).

Eine Liste der vertrauenswürdigen Zertifizierungsstellen finden Sie unter [Zertifikatliste der microsoft-eingeschlossenen Zertifizierungsstelle](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT).

## <a name="replace-headers"></a>Ersetzen von Kopfzeilen

Ab April 2022 lehnet Direct Routing SIP-Anforderungen ab, für die "Replaces headers" definiert sind. Es gibt keine Änderungen an Flüssen, bei denen Microsoft die Replaces-Kopfzeile an den Session Border Controller (SBC) sendet.

Überprüfen Sie Ihre SBC-Konfigurationen, und stellen Sie sicher, dass Sie "Replaces headers" nicht in SIP-Anforderungen verwenden.

## <a name="tls10-and-11"></a>TLS1.0 und 1.1

Um unseren Kunden die erstklassige Verschlüsselung zu ermöglichen, plant Microsoft, die Transport Layer Security (TLS)-Versionen 1.0 und 1.1 zu veraltet. Am 3. April 2022 erzwingen Microsoft die Verwendung von TLS1.2 für die Direct-Routing-SIP-Schnittstelle.

Um Auswirkungen auf den Dienst zu vermeiden, stellen Sie sicher, dass Ihre SBCs für die Unterstützung von TLS1.2 konfiguriert sind und mithilfe einer der folgenden Verschlüsselungssammlungen eine Verbindung herstellen können:

- TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384. B. ECDHE-RSA-AES256-GCM-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256. B. ECDHE-RSA-AES128-GCM-SHA256
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384. B. ECDHE-RSA-AES256-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256. B. ECDHE-RSA-AES128-SHA256

## <a name="related-topics"></a>Verwandte Themen

- [Direct Routing – SIP-Protokoll](direct-routing-protocols-sip.md)
