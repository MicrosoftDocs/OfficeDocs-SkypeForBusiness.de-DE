---
title: Zertifikatanforderung (Rückgabe)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/1/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
description: 'Auf der Seite Status der Onlinezertifikatsanforderung finden Sie wichtige Informationen, die aus der erfolgreichen Erstellung und Ausstellung des Onlinezertifikats resultieren. Die Seite enthält ferner den Zertifikatfingerabdruck, der das Zertifikat eindeutig identifiziert. Standardmäßig ist das Kontrollkästchen "Dieses Zertifikat Skype for Business Server-Zertifikatverwendungen zuweisen" aktiviert. Wenn Sie auf "Fertig stellen" klicken, wird das Zertifikat lync Server 2013 automatisch für die Zwecke zugewiesen, die Sie während der Erstellungsschritte der Zertifikatanforderung definiert haben. Das Zertifikat wird standardmäßig für die folgenden Zwecke zugewiesen:'
ms.openlocfilehash: 41695f37da725816be6858f0de639bca95a09438
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805145"
---
# <a name="certificate-request-returned"></a>Zertifikatanforderung (Rückgabe)
 
Auf der Seite **Status der Onlinezertifikatsanforderung** finden Sie wichtige Informationen, die aus der erfolgreichen Erstellung und Ausstellung des Onlinezertifikats resultieren. Die Seite enthält ferner den Zertifikatfingerabdruck, der das Zertifikat eindeutig identifiziert. Standardmäßig ist das Kontrollkästchen **"Dieses Zertifikat Skype for Business Server-Zertifikatverwendungen** zuweisen" aktiviert. Wenn Sie auf **"Fertig** stellen" klicken, wird das Zertifikat lync Server 2013 automatisch für die Zwecke zugewiesen, die Sie während der Erstellungsschritte der Zertifikatanforderung definiert haben. Das Zertifikat wird standardmäßig für die folgenden Zwecke zugewiesen:
  
- Server default for Mutual Transport Layer Security (MTLS) – Verbindungen mit Clients und anderen Servern
    
- Webdienste intern – Client- und Serververbindungen auf der internen Webdienstwebsite für Transport Layer Security/Secure Sockets Layer (TLS/SSL)
    
- Externe Webdienste – Client- und Serververbindungen auf der externen Webdienstwebsite für TLS/SSL
    
Klicken Sie auf die Schaltfläche **Zertifikatdetails anzeigen**, um das Zertifikat anzuzeigen und zu überprüfen, ob die Eigenschaften des Zertifikats wie gewünscht festgelegt sind und ob es für den Einsatz auf dem Server bereit ist.
  
Klicken Sie auf **Fertig stellen**, um den Anforderungsprozess des Onlinezertifikats abzuschließen. Wenn Sie das Kontrollkästchen "Dieses Zertifikat **Skype for Business Server-Zertifikatverwendungen** zuweisen" aktiviert haben, wird das Zertifikat automatisch zugewiesen. Ist es deaktiviert, müssen Sie das Zertifikat in einem gesonderten Schritt zuweisen. 
  
> [!IMPORTANT]
> Wenn sich das Stammzertifikat der ausstellenden Zertifizierungsstelle nicht im Speicher der vertrauenswürdigen Stammzertifizierungsstelle des Computers befindet oder wenn sich Zwischenzertifizierungsstellenzertifikate nicht im richtigen Speicher befinden, wird der Zusammenfassungsstatus angezeigt, wie in der folgenden Abbildung dargestellt. Dann können Sie das Zertifikat nicht zuweisen. Zum Abschließen des Zertifikatzuweisungsprozesses müssen Sie das Stammzertifikat der ausstellenden Zertifizierungsstelle und etwaige Zertifikate von Zwischenzertifizierungsstellen importieren und anschließend das Zertifikat zuweisen, indem Sie auf der Hauptseite des Zertifikat-Assistenten auf **Zuweisen** klicken.
  

