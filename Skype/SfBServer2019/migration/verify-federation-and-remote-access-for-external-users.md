---
title: Überprüfen des Partnerverbunds und des Remotezugriffs für externe Benutzer
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Nachdem Sie die partnerverbundroute zum Skype for Business Server 2019 Edgeserver gewechselt haben, sollten Sie einige Funktionstests durchführen, um zu überprüfen, ob der Verbund wie erwartet ausgeführt wird. Tests für den Zugriff durch externe Benutzer sollten alle Typen von externen Benutzern enthalten, die von Ihrer Organisation unterstützt werden, einschließlich einer oder aller der folgenden.
ms.openlocfilehash: b2567f4e46bd39d2748e3a4a3ba6cc5d6c197b11
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751667"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>Überprüfen des Partnerverbunds und des Remotezugriffs für externe Benutzer

Nachdem Sie die partnerverbundroute zum Skype for Business Server 2019 Edgeserver gewechselt haben, sollten Sie einige Funktionstests durchführen, um zu überprüfen, ob der Verbund wie erwartet ausgeführt wird. Tests für den Zugriff durch externe Benutzer sollten alle Typen von externen Benutzern enthalten, die von Ihrer Organisation unterstützt werden, einschließlich einer oder aller der folgenden.
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>Testen der Konnektivität externer Benutzer und des externen Zugriffs

- Benutzer aus mindestens einer Verbunddomäne, einem internen Benutzer auf Skype for Business Server 2019 und einem Benutzer auf der Legacy Installation. Testen von Chatnachrichten, Anwesenheit, Audio/Video (A/V) und Desktopfreigabe.
    
- Benutzer aller öffentlichen Sofortnachrichten-Dienstanbieter, die von Ihrer Organisation unterstützt werden (und für die die Bereitstellung abgeschlossen ist), die mit einem Benutzer auf Skype for Business Server 2019 und einem Benutzer auf der Legacy Installation kommunizieren. 
    
- Stellen Sie sicher, dass anonyme Benutzer in der Lage sind, an Konferenzen teilzunehmen.
    
- Ein auf der Legacy Installation gehosteter Benutzer verwendet den Remotebenutzerzugriff (Protokollierung i num lync Server/Skype for Business von außerhalb des Intranets, aber ohne VPN) mit einem Benutzer unter Skype for Business Server 2019 und einem Benutzer auf der Legacy Installation. Testen Sie Sofortnachrichten, Anwesenheit, A/V und Desktopfreigabe.
    
- Ein Benutzer, der auf Skype for Business Server 2019 mit Remotebenutzerzugriff (Anmeldung bei Skype for Business Server 2019 von außerhalb des Intranets, aber ohne VPN) mit einem Benutzer unter Skype for Business Server 2019 und einem Benutzer auf der Legacy Installation gehostet wird. Testen Sie Sofortnachrichten, Anwesenheit, A/V und Desktopfreigabe.
    

