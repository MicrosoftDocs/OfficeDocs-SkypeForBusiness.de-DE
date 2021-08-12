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
description: Nach dem Übergang der Partnerverbundroute zum Skype for Business Server 2019-Edgeserver sollten Sie einige Funktionale Tests durchführen, um sicherzustellen, dass der Partnerverbund wie erwartet funktioniert. Tests für den Zugriff durch externe Benutzer sollten jeden externen Benutzertyp umfassen, den Ihre Organisation unterstützt, einschließlich eines oder aller der folgenden Typen.
ms.openlocfilehash: 80a7e5042fb9473e3bbd07438c1f0a57026b1bc5454784973870a695946c0cd7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303329"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>Überprüfen des Partnerverbunds und des Remotezugriffs für externe Benutzer

Nach dem Übergang der Partnerverbundroute zum Skype for Business Server 2019-Edgeserver sollten Sie einige Funktionale Tests durchführen, um sicherzustellen, dass der Partnerverbund wie erwartet funktioniert. Tests für den Zugriff durch externe Benutzer sollten jeden externen Benutzertyp umfassen, den Ihre Organisation unterstützt, einschließlich eines oder aller der folgenden Typen.
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>Testen der Konnektivität externer Benutzer und des externen Zugriffs

- Benutzer aus mindestens einer Verbunddomäne, einem internen Benutzer auf Skype for Business Server 2019 und einem Benutzer bei der Legacyinstallation. Testen Sie Chat, Anwesenheit, Audio/Video (A/V) und Desktopfreigabe.
    
- Benutzer jedes öffentlichen Chatdienstanbieters, den Ihre Organisation unterstützt (und für den die Bereitstellung abgeschlossen wurde), kommunizieren mit einem Benutzer am Skype for Business Server 2019 und einem Benutzer bei der Legacyinstallation. 
    
- Stellen Sie sicher, dass anonyme Benutzer in der Lage sind, an Konferenzen teilzunehmen.
    
- Ein Benutzer, der auf der Legacyinstallation mithilfe des Remotebenutzerzugriffs (Protokollierung von i nto Lync Server/Skype for Business von außerhalb des Intranets, aber ohne VPN) mit einem Benutzer auf Skype for Business Server 2019 und einem Benutzer bei der Legacyinstallation gehostet wird. Testen Sie Sofortnachrichten, Anwesenheit, A/V und Desktopfreigabe.
    
- Ein Benutzer, der auf Skype for Business Server 2019 mithilfe des Remotebenutzerzugriffs (Anmeldung bei Skype for Business Server 2019 von außerhalb des Intranets, aber ohne VPN) mit einem Benutzer auf Skype for Business Server 2019 und einem Benutzer bei der Legacyinstallation gehostet wird. Testen Sie Sofortnachrichten, Anwesenheit, A/V und Desktopfreigabe.
    

