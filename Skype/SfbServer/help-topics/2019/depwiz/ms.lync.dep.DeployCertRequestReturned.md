---
title: Zertifikatanforderung (Rückgabe)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
ROBOTS: NOINDEX, NOFOLLOW
description: 'Auf der Status Seite "Online Zertifikatanforderung" werden wichtige Informationen angezeigt, die sich aus der erfolgreichen Erstellung und Ausgabe der Online Zertifikatanforderung ergeben. Diese Seite enthält den Fingerabdruck des Zertifikats, der das Zertifikat eindeutig identifiziert. Standardmäßig ist das Kontrollkästchen Dieses Zertifikat den Skype for Business Server-Zertifikat Verwendungen zuweisen ausgewählt. Wenn Sie auf Fertig stellen klicken, wird das Zertifikat automatisch dem Skype for Business-Server für die Zwecke zugewiesen, die Sie während der Erstellungsschritte der Zertifikatanforderung festgelegt haben. Standardmäßig werden die Zwecke, denen das Zertifikat zugewiesen wird, wie folgt festgelegt:'
ms.openlocfilehash: 02d114ff55360f3e88a866485759510ce5f107c4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278021"
---
# <a name="certificate-request-returned"></a>Zertifikatanforderung (Rückgabe)
 
Auf der Status Seite " **Online Zertifikatanforderung** " werden wichtige Informationen angezeigt, die sich aus der erfolgreichen Erstellung und Ausgabe der Online Zertifikatanforderung ergeben. Diese Seite enthält den Fingerabdruck des Zertifikats, der das Zertifikat eindeutig identifiziert. Standardmäßig ist das Kontrollkästchen **dieses Zertifikat den Skype for Business Server-Zertifikat Verwendungen zuweisen** ausgewählt. Wenn Sie auf **Fertig stellen**klicken, wird das Zertifikat automatisch dem Skype for Business-Server für die Zwecke zugewiesen, die Sie während der Erstellungsschritte der Zertifikatanforderung festgelegt haben. Standardmäßig werden die Zwecke, denen das Zertifikat zugewiesen wird, wie folgt festgelegt:
  
- Server Standard für MTLS (Mutual Transport Layer Security) – Verbindungen zu Clients und anderen Servern
    
- Web Services Internal-Client-und Serververbindungen auf der internen Webdienste-Website für Transport Layer Security/Secure Sockets Layer (TLS/SSL)
    
- Web Services External-Client-und Serververbindungen auf der externen Webdienste-Website für TLS/SSL
    
Klicken Sie auf die Details des Zertifikats **anzeigen** , um das Zertifikat anzuzeigen, um zu bestätigen, dass die Eigenschaften des Zertifikats dem entsprechen, was Sie beabsichtigt haben, und dass das Zertifikat auf dem Server angewendet und verwendet werden kann.
  
Klicken Sie auf **Fertig stellen** , um den Online Zertifikat Anforderungsprozess abzuschließen. Wenn Sie das Kontrollkästchen **dieses Zertifikat den Skype for Business Server-Zertifikat Verwendungen zuweisen**aktiviert haben, wird das Zertifikat automatisch zugewiesen. Wenn Sie dieses Kontrollkästchen deaktiviert haben, müssen Sie das Zertifikat in einem separaten Schritt zuweisen. 
  
> [!IMPORTANT]
> Wenn sich das Stammzertifikat der ausstellenden Zertifizierungsstelle nicht im Speicher der vertrauenswürdigen Stammzertifizierungsstelle des Computers befindet oder wenn sich Zwischenzertifizierungsstellen Zertifikate nicht im richtigen Speicher befinden, wird der Zusammenfassungsstatus angezeigt, wie in der folgenden Abbildung dargestellt. Sie haben nicht die Möglichkeit, das Zertifikat zuzuweisen. Zum Abschließen des Zertifikats Zuordnungsprozesses müssen Sie das Stammzertifikat der ausstellenden Zertifizierungsstelle und alle Zwischenzertifizierungsstellen Zertifikate importieren und dann das Zertifikat zuweisen, indem Sie auf der Seite Hauptzertifikat-Assistent auf **zuweisen** klicken.
  

