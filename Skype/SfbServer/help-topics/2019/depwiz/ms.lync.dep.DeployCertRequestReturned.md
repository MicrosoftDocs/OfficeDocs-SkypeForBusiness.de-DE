---
title: Zertifikatanforderung (Rückgabe)
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
description: 'Die Status der Onlinezertifikatsanforderung Online-Seite zeigt wichtige Informationen, Ergebnisse aus die erfolgreiche Erstellung und der online zertifikatanforderung ausstellen. Auf dieser Seite finden den Fingerabdruck des Zertifikats, der das Zertifikat eindeutig identifiziert. Standardmäßig ist das Kontrollkästchen weisen dieses Zertifikat Skype für zertifikatverwendungen Business Server aktiviert. Wenn Sie auf "Fertig stellen" klicken, wird das Zertifikat automatisch Lync Server 2013 für die Zwecke zugewiesen werden, die Sie während der Erstellungsschritte zum der zertifikatanforderung definiert. Standardmäßig sind die Zwecke, die das Zertifikat zugewiesen werden:'
ms.openlocfilehash: 74ee0fba06add0d069473bc5b6b580c1b1d5810a
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/20/2018
ms.locfileid: "19976597"
---
# <a name="certificate-request-returned"></a>Zertifikatanforderung (Rückgabe)
 
Die **Status der Onlinezertifikatsanforderung Online** -Seite zeigt wichtige Informationen, Ergebnisse aus die erfolgreiche Erstellung und der online zertifikatanforderung ausstellen. Auf dieser Seite finden den Fingerabdruck des Zertifikats, der das Zertifikat eindeutig identifiziert. Standardmäßig ist das Kontrollkästchen **weisen Sie dieses Zertifikat zu Skype für zertifikatverwendungen Business Server** aktiviert. Wenn Sie auf **Fertig stellen**klicken, wird das Zertifikat automatisch Lync Server 2013 für die Zwecke zugewiesen werden, die Sie während der Erstellungsschritte zum der zertifikatanforderung definiert. Standardmäßig sind die Zwecke, die das Zertifikat zugewiesen werden:
  
- Serverstandard für Transport Layer Security MTLS (Mutual) - Verbindungen mit Clients und anderen Servern
    
- Webdienstintern – Client- und serververbindungen am internen webdienststandort für Transport Layer Security/Secure Sockets Layer (TLS/SSL)
    
- Webdienstextern – Client- und serververbindungen am externen webdienststandort für TLS/SSL
    
Klicken Sie auf die **Zertifikatdetails Ansicht** zum Anzeigen des Zertifikats, um zu bestätigen, dass die Eigenschaften des Zertifikats sind wie gewünscht und das Zertifikat ist bereit zur angewendet, und platzieren Sie auf dem Server verwendet werden.
  
Klicken Sie auf **Fertig stellen** , um die online zertifikatanforderung ab abzuschließen. Wenn Sie das Kontrollkästchen **weisen Sie dieses Zertifikat zu Skype für zertifikatverwendungen Business Server**ausgewählt haben, wird das Zertifikat automatisch zugewiesen. Wenn Sie dieses Kontrollkästchen deaktivieren möchten, müssen Sie das Zertifikat in einem separaten Schritt zuweisen. 
  
> [!IMPORTANT]
> Wenn das Stammzertifikat der ausstellenden Zertifizierungsstelle Zertifizierungsstelle (CA) nicht in den Computerspeicher vertrauenswürdige Stammzertifizierungsstelle ist, oder wenn Zertifikate nicht im entsprechenden Store sind, Sie den Status des zusammenfassenden, sehen wie in der folgenden Abbildung dargestellt. Sie haben nicht die Option aus, um das Zertifikat zuzuweisen. Um das Zertifikat Zuordnung abzuschließen, müssen Sie importieren Sie das Stammzertifikat der ausstellenden Zertifizierungsstelle und allen Zertifikaten von Zwischenzertifizierungsstellen, und weisen Sie das Zertifikat, indem Sie auf der Hauptseite des Zertifikat-Assistenten auf **zuweisen** .
  

