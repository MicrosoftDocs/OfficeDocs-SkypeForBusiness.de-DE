---
title: Bereitstellen der VIS-Serverrolle in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6401e67-59fe-4419-a0ab-ffac88e67632
description: 'Zusammenfassung: Bereitstellen der Rolle "Video-Interoperabilität-Server (VIS)" in Skype for Business Server.'
ms.openlocfilehash: 0683a413b3442cf09d2703d3593851c2808146a077df23969c339d526b9ebda8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54330529"
---
# <a name="deploy-the-vis-server-role-in-skype-for-business-server"></a>Bereitstellen der VIS-Serverrolle in Skype for Business Server
 
**Zusammenfassung:** Stellen Sie die Rolle des Video-Interoperabilität-Servers (VIS) in Skype for Business Server bereit.
  
Um den VIS-Dienst auf dem Server einzurichten, der gerade im Topologie-Generator erstellt wurde, starten Sie den Skype for Business Server Bereitstellungs-Assistenten, drücken **Sie "Installieren" oder "Aktualisieren" Skype for Business Server Systems,** und führen Sie die folgenden Schritte im Assistenten aus:
  
1.  Wählen Sie **"Lokale Konfiguration installieren" Store** aus.
    
2. Wählen Sie **"Setup" aus, oder entfernen Sie Skype for Business Server Komponenten.**
    
3. Wählen Sie **"Zertifikate anfordern", "Installieren" oder "Zuweisen" aus.**
    
4. Wählen Sie **Startdienste** aus.
    
Die Software für diesen Dienst ist jetzt installiert und wird ausgeführt. Sie können das MmC-Tool "Dienste" öffnen, um festzustellen, ob der **Skype for Business Server Video-Interoperabilität-Serverdienst** zusammen mit anderen Skype for Business Server-Diensten ausgeführt wird. Als Nächstes müssen Sie den VIS-Server oder -Pool konfigurieren.
## <a name="see-also"></a>Siehe auch

[Konfigurieren des Video-Interoperabilitätsservers in Skype for Business Server](configure-the-vis.md)
