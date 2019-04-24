---
title: Zertifikatanforderung (Rückgabe)
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
ROBOTS: NOINDEX, NOFOLLOW
description: 'Die Status der Onlinezertifikatsanforderung Online-Seite zeigt wichtige Informationen, Ergebnisse aus die erfolgreiche Erstellung und der online zertifikatanforderung ausstellen. Auf dieser Seite finden den Fingerabdruck des Zertifikats, der das Zertifikat eindeutig identifiziert. Standardmäßig ist das Kontrollkästchen weisen dieses Zertifikat Skype für zertifikatverwendungen Business Server aktiviert. Wenn Sie auf "Fertig stellen" klicken, wird das Zertifikat automatisch Skype für Business Server für die Zwecke zugewiesen werden, die Sie während der Erstellungsschritte zum der zertifikatanforderung definiert. Standardmäßig sind die Zwecke, die das Zertifikat zugewiesen werden:'
ms.openlocfilehash: 70868129dc759e19960d2f6d9e3a9a1dc3d2f941
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216368"
---
# <a name="certificate-request-returned"></a>Zertifikatanforderung (Rückgabe)
 
Die **Status der Onlinezertifikatsanforderung Online** -Seite zeigt wichtige Informationen, Ergebnisse aus die erfolgreiche Erstellung und der online zertifikatanforderung ausstellen. Auf dieser Seite finden den Fingerabdruck des Zertifikats, der das Zertifikat eindeutig identifiziert. Standardmäßig ist das Kontrollkästchen **weisen Sie dieses Zertifikat zu Skype für zertifikatverwendungen Business Server** aktiviert. Wenn Sie auf **Fertig stellen**klicken, wird das Zertifikat automatisch Skype für Business Server für die Zwecke zugewiesen werden, die Sie während der Erstellungsschritte zum der zertifikatanforderung definiert. Standardmäßig sind die Zwecke, die das Zertifikat zugewiesen werden:
  
- Serverstandard für Transport Layer Security MTLS (Mutual) - Verbindungen mit Clients und anderen Servern
    
- Webdienstintern – Client- und serververbindungen am internen webdienststandort für Transport Layer Security/Secure Sockets Layer (TLS/SSL)
    
- Webdienstextern – Client- und serververbindungen am externen webdienststandort für TLS/SSL
    
Klicken Sie auf die **Zertifikatdetails Ansicht** zum Anzeigen des Zertifikats, um zu bestätigen, dass die Eigenschaften des Zertifikats sind wie gewünscht und das Zertifikat ist bereit zur angewendet, und platzieren Sie auf dem Server verwendet werden.
  
Klicken Sie auf **Fertig stellen** , um die online zertifikatanforderung ab abzuschließen. Wenn Sie das Kontrollkästchen **weisen Sie dieses Zertifikat zu Skype für zertifikatverwendungen Business Server**ausgewählt haben, wird das Zertifikat automatisch zugewiesen. Wenn Sie dieses Kontrollkästchen deaktivieren möchten, müssen Sie das Zertifikat in einem separaten Schritt zuweisen. 
  
> [!IMPORTANT]
> Wenn das Stammzertifikat der ausstellenden Zertifizierungsstelle Zertifizierungsstelle (CA) nicht in den Computerspeicher vertrauenswürdige Stammzertifizierungsstelle ist, oder wenn Zertifikate nicht im entsprechenden Store sind, Sie den Status des zusammenfassenden, sehen wie in der folgenden Abbildung dargestellt. Sie haben nicht die Option aus, um das Zertifikat zuzuweisen. Um das Zertifikat Zuordnung abzuschließen, müssen Sie importieren Sie das Stammzertifikat der ausstellenden Zertifizierungsstelle und allen Zertifikaten von Zwischenzertifizierungsstellen, und weisen Sie das Zertifikat, indem Sie auf der Hauptseite des Zertifikat-Assistenten auf **zuweisen** .
  

