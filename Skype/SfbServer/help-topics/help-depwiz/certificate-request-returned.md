---
title: Zertifikatanforderung (Rückgabe)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/1/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
description: 'Auf der Status Seite "Online Zertifikatanforderung" werden wichtige Informationen angezeigt, die sich aus der erfolgreichen Erstellung und Ausgabe der Online Zertifikatanforderung ergeben. Diese Seite enthält den Fingerabdruck des Zertifikats, der das Zertifikat eindeutig identifiziert. Standardmäßig ist das Kontrollkästchen Dieses Zertifikat den Skype for Business Server-Zertifikat Verwendungen zuweisen ausgewählt. Wenn Sie auf Fertig stellen klicken, wird das Zertifikat automatisch lync Server 2013 für die Zwecke zugewiesen, die Sie während der Erstellungsschritte der Zertifikatanforderung festgelegt haben. Standardmäßig werden die Zwecke, denen das Zertifikat zugewiesen wird, wie folgt festgelegt:'
ms.openlocfilehash: 885de54ec8deeef1d326e39b5a35e7b08c633973
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687748"
---
# <a name="certificate-request-returned"></a>Zertifikatanforderung (Rückgabe)
 
Auf der Status Seite " **Online Zertifikatanforderung** " werden wichtige Informationen angezeigt, die sich aus der erfolgreichen Erstellung und Ausgabe der Online Zertifikatanforderung ergeben. Diese Seite enthält den Fingerabdruck des Zertifikats, der das Zertifikat eindeutig identifiziert. Standardmäßig ist das Kontrollkästchen **dieses Zertifikat den Skype for Business Server-Zertifikat Verwendungen zuweisen** ausgewählt. Wenn Sie auf **Fertig stellen**klicken, wird das Zertifikat automatisch lync Server 2013 für die Zwecke zugewiesen, die Sie während der Erstellungsschritte der Zertifikatanforderung festgelegt haben. Standardmäßig werden die Zwecke, denen das Zertifikat zugewiesen wird, wie folgt festgelegt:
  
- Server Standard für MTLS (Mutual Transport Layer Security) – Verbindungen zu Clients und anderen Servern
    
- Web Services Internal-Client-und Serververbindungen auf der internen Webdienste-Website für Transport Layer Security/Secure Sockets Layer (TLS/SSL)
    
- Web Services External-Client-und Serververbindungen auf der externen Webdienste-Website für TLS/SSL
    
Klicken Sie auf die Details des Zertifikats **anzeigen** , um das Zertifikat anzuzeigen, um zu bestätigen, dass die Eigenschaften des Zertifikats dem entsprechen, was Sie beabsichtigt haben, und dass das Zertifikat auf dem Server angewendet und verwendet werden kann.
  
Klicken Sie auf **Fertig stellen** , um den Online Zertifikat Anforderungsprozess abzuschließen. Wenn Sie das Kontrollkästchen **dieses Zertifikat den Skype for Business Server-Zertifikat Verwendungen zuweisen**aktiviert haben, wird das Zertifikat automatisch zugewiesen. Wenn Sie dieses Kontrollkästchen deaktiviert haben, müssen Sie das Zertifikat in einem separaten Schritt zuweisen. 
  
> [!IMPORTANT]
> Wenn sich das Stammzertifikat der ausstellenden Zertifizierungsstelle nicht im Speicher der vertrauenswürdigen Stammzertifizierungsstelle des Computers befindet oder wenn sich Zwischenzertifizierungsstellen Zertifikate nicht im richtigen Speicher befinden, wird der Zusammenfassungsstatus angezeigt, wie in der folgenden Abbildung dargestellt. Sie haben nicht die Möglichkeit, das Zertifikat zuzuweisen. Zum Abschließen des Zertifikats Zuordnungsprozesses müssen Sie das Stammzertifikat der ausstellenden Zertifizierungsstelle und alle Zwischenzertifizierungsstellen Zertifikate importieren und dann das Zertifikat zuweisen, indem Sie auf der Seite Hauptzertifikat-Assistent auf **zuweisen** klicken.
  

