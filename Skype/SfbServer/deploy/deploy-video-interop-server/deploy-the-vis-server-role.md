---
title: Bereitstellen der VIS-Serverrolle in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: b6401e67-59fe-4419-a0ab-ffac88e67632
description: 'Zusammenfassung: Bereitstellen der Rolle des Video-Interoperabilität-Servers (VIS) in Skype for Business Server.'
ms.openlocfilehash: 35d3be9a9469136ad9cfaea1f2f6ef99bf665ed1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751204"
---
# <a name="deploy-the-vis-server-role-in-skype-for-business-server"></a>Bereitstellen der VIS-Serverrolle in Skype for Business Server
 
**Zusammenfassung:** Stellen Sie die Rolle "Video-Interoperabilität-Server (VIS) in Skype for Business Server bereit.
  
Um den VIS-Dienst auf dem Server einzurichten, der gerade im Topologie-Generator erstellt wurde, starten Sie den Skype for Business Server Bereitstellungs-Assistenten, drücken **Sie "Installieren" oder "Skype for Business Server System aktualisieren",** und führen Sie die folgenden Schritte im Assistenten aus:
  
1.  Wählen Sie **"Lokale Konfiguration installieren" Store** aus.
    
2. Wählen Sie **setup or Remove Skype for Business Server Components**.
    
3. Wählen Sie **"Zertifikate anfordern", "Installieren" oder "Zuweisen" aus.**
    
4. Wählen Sie **Startdienste** aus.
    
Die Software für diesen Dienst ist jetzt installiert und wird ausgeführt. Sie können das MmC-Tool "Dienste" öffnen, um festzustellen, ob der **Skype for Business Server Video-Interoperabilität-Serverdienst** zusammen mit anderen Skype for Business Server-Diensten ausgeführt wird. Als Nächstes müssen Sie den VIS-Server oder -Pool konfigurieren.
## <a name="see-also"></a>Weitere Informationen

[Konfigurieren des Video-Interoperabilitätsservers in Skype for Business Server](configure-the-vis.md)
