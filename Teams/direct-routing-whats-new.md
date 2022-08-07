---
title: Neuerungen beim Direct Routing
ms.reviewer: CarolynRowe
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: In diesem Artikel werden die Neuerungen im Direct Routing beschrieben. Suchen Sie häufig nach Updates.
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
ms.openlocfilehash: 8db0f0c4d29f786166098587aafc3ec1db256e38
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271460"
---
# <a name="whats-new-for-direct-routing"></a>Neuerungen bei Direct Routing

In diesem Artikel werden die Neuerungen im Direct Routing beschrieben. Suchen Sie häufig nach Updates.

## <a name="sip-support"></a>SIP-Unterstützung

Am 1. Juni 2022 entfernt Microsoft die Unterstützung für sip-all.pstnhub.microsoft.com und sip-all.pstnhub.gov.teams.microsoft.us FQDNs aus der Direct Routing-Konfiguration.

Wenn vor dem 1. Juni keine Aktionen ausgeführt werden, können Benutzer keine Anrufe über Direct Routing tätigen oder empfangen.

So verhindern Sie Auswirkungen auf den Dienst:

- Verwenden Sie die empfohlenen Subnetze (52.112.0.0/14 und 52.120.0.0/14) für alle Klassifizierungs- oder ACL-Regeln.
- Beenden Sie die Verwendung des sip-all-FQDN beim Konfigurieren von Session Border Controls für Direct Routing.

Weitere Informationen finden Sie unter [Planen von Direct Routing](direct-routing-plan.md).

## <a name="tls-certificates"></a>TLS-Zertifikate

Microsoft 365 aktualisiert Teams und andere Dienste, um einen anderen Satz von Stammzertifizierungsstellen (CAs) zu verwenden.

Weitere Informationen und eine vollständige Liste der betroffenen Dienste finden Sie unter [TLS-Zertifikatänderungen an Microsoft 365-Diensten, einschließlich Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/tls-certificate-changes-to-microsoft-365-services-including/ba-p/3249676).

## <a name="certificate-authorities"></a>Zertifizierungsstellen

Ab dem 1. Februar 2022 vertraut die DIRECT Routing-SIP-Schnittstelle nur Zertifikaten, die von Zertifizierungsstellen signiert wurden und Teil des vertrauenswürdigen Stammzertifikatprogramms von Microsoft sind. Führen Sie die folgenden Schritte aus, um Auswirkungen auf den Dienst zu vermeiden:

- Stellen Sie sicher, dass Ihr SBC-Zertifikat von einer Zertifizierungsstelle signiert ist, die Teil des vertrauenswürdigen Microsoft-Stammzertifikatprogramms ist.
- Stellen Sie sicher, dass die Erweiterung für die erweiterte Schlüsselnutzung (Extended Key Usage, EKU) Ihres Zertifikats "Serverauthentifizierung" enthält.

Weitere Informationen zum vertrauenswürdigen Stammzertifikatprogramm von Microsoft finden Sie unter ["Programmanforderungen – Microsoft Trusted Root Program"](/security/trusted-root/program-requirements).

Eine Liste der vertrauenswürdigen Zertifizierungsstellen finden Sie unter [Microsoft Included CA Certificate List](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT).

## <a name="replace-headers"></a>Kopfzeilen ersetzen

Ab April 2022 lehnt Direct Routing SIP-Anforderungen ab, für die Replaces-Header definiert sind. Es gibt keine Änderungen an Flüssen, bei denen Microsoft den Replaces-Header an den Session Border Controller(SBC) sendet.

Überprüfen Sie Ihre SBC-Konfigurationen, und stellen Sie sicher, dass Sie keine Replaces-Header in SIP-Anforderungen verwenden.

## <a name="tls10-and-11"></a>TLS1.0 und 1.1

Um unseren Kunden die erstklassige Verschlüsselung bereitzustellen, plant Microsoft, die TLS-Versionen 1.0 und 1.1 für Transport Layer Security (TLS) zu veralteten Versionen zu verwenden. Am 3. April 2022 erzwingt Microsoft die TLS1.2-Verwendung für die Direct Routing-SIP-Schnittstelle.

Um Auswirkungen auf den Dienst zu vermeiden, stellen Sie sicher, dass Ihre SBCs für die Unterstützung von TLS1.2 konfiguriert sind und eine Verbindung mithilfe einer der folgenden Verschlüsselungssammlungen herstellen können:

- TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 d. h. ECDHE-RSA-AES256-GCM-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 d. h. ECDHE-RSA-AES128-GCM-SHA256
- TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 d. h. ECDHE-RSA-AES256-SHA384
- TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 d. h. ECDHE-RSA-AES128-SHA256

## <a name="related-topics"></a>Verwandte Themen

- [Direct Routing – SIP-Protokoll](direct-routing-protocols-sip.md)
