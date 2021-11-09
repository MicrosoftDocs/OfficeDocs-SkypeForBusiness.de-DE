---
title: Zertifikatanforderung (Rückgabe)
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 4/1/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
description: 'Auf der Seite Status der Onlinezertifikatsanforderung finden Sie wichtige Informationen, die aus der erfolgreichen Erstellung und Ausstellung des Onlinezertifikats resultieren. Die Seite enthält ferner den Zertifikatfingerabdruck, der das Zertifikat eindeutig identifiziert. Standardmäßig ist das Kontrollkästchen Dieses Zertifikat Skype for Business Server Zertifikatverwendungen zuweisen aktiviert. Wenn Sie auf Fertig stellen klicken, wird das Zertifikat lync Server 2013 automatisch für die Zwecke zugewiesen, die Sie während der Erstellungsschritte der Zertifikatanforderung definiert haben. Das Zertifikat wird standardmäßig für die folgenden Zwecke zugewiesen:'
ms.openlocfilehash: 64c12960e574b9e43059989713974631db2a427e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60831099"
---
# <a name="certificate-request-returned"></a>Zertifikatanforderung (Rückgabe)
 
Auf der Seite **Status der Onlinezertifikatsanforderung** finden Sie wichtige Informationen, die aus der erfolgreichen Erstellung und Ausstellung des Onlinezertifikats resultieren. Die Seite enthält ferner den Zertifikatfingerabdruck, der das Zertifikat eindeutig identifiziert. Standardmäßig ist das Kontrollkästchen **Dieses Zertifikat Skype for Business Server Zertifikatverwendungen zuweisen** aktiviert. Wenn Sie auf **Fertig stellen** klicken, wird das Zertifikat lync Server 2013 automatisch für die Zwecke zugewiesen, die Sie während der Erstellungsschritte der Zertifikatanforderung definiert haben. Das Zertifikat wird standardmäßig für die folgenden Zwecke zugewiesen:
  
- Serverstandard für Mutual Transport Layer Security (MTLS) – Verbindungen mit Clients und anderen Servern
    
- Webdienste intern – Client- und Serververbindungen auf der internen Webdienstwebsite für Transport Layer Security/Secure Sockets Layer (TLS/SSL)
    
- Webdienste extern – Client- und Serververbindungen auf der externen Webdienstwebsite für TLS/SSL
    
Klicken Sie auf die Schaltfläche **Zertifikatdetails anzeigen**, um das Zertifikat anzuzeigen und zu überprüfen, ob die Eigenschaften des Zertifikats wie gewünscht festgelegt sind und ob es für den Einsatz auf dem Server bereit ist.
  
Klicken Sie auf **Fertig stellen**, um den Anforderungsprozess des Onlinezertifikats abzuschließen. Wenn Sie das Kontrollkästchen **"Zertifikat Skype for Business Server Zertifikatverwendungen zuweisen"** aktiviert haben, wird das Zertifikat automatisch zugewiesen. Ist es deaktiviert, müssen Sie das Zertifikat in einem gesonderten Schritt zuweisen. 
  
> [!IMPORTANT]
> Wenn sich das Stammzertifikat der ausstellenden Zertifizierungsstelle nicht im Speicher der vertrauenswürdigen Stammzertifizierungsstelle des Computers befindet oder sich Zwischenzertifizierungsstellenzertifikate nicht im richtigen Speicher befinden, wird der Zusammenfassungsstatus angezeigt, wie in der folgenden Abbildung dargestellt. Dann können Sie das Zertifikat nicht zuweisen. Zum Abschließen des Zertifikatzuweisungsprozesses müssen Sie das Stammzertifikat der ausstellenden Zertifizierungsstelle und etwaige Zertifikate von Zwischenzertifizierungsstellen importieren und anschließend das Zertifikat zuweisen, indem Sie auf der Hauptseite des Zertifikat-Assistenten auf **Zuweisen** klicken.
  

