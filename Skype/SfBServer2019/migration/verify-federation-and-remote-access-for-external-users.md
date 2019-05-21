---
title: Überprüfen des Partnerverbunds und des Remotezugriffs für externe Benutzer
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Nachdem Sie die Föderations Route zum Skype for Business Server 2019 Edge-Server gewechselt haben, sollten Sie einige Funktionstests durchführen, um zu überprüfen, ob der Verbund wie erwartet funktioniert. Tests für den Zugriff durch externe Benutzer sollten alle externen Benutzertypen enthalten, die von Ihrer Organisation unterstützt werden, einschließlich der folgenden:'
ms.openlocfilehash: a07cbfc8596cfd49760af1fcee7df90eca362229
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292172"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>Überprüfen des Partnerverbunds und des Remotezugriffs für externe Benutzer

Nachdem Sie die Föderations Route zum Skype for Business Server 2019 Edge-Server gewechselt haben, sollten Sie einige Funktionstests durchführen, um zu überprüfen, ob der Verbund wie erwartet funktioniert. Tests für den Zugriff durch externe Benutzer sollten alle externen Benutzertypen enthalten, die von Ihrer Organisation unterstützt werden, einschließlich der folgenden:
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>Testen der Konnektivität externer Benutzer und des externen Zugriffs

- Benutzer aus mindestens einer Föderationsdomäne, einem internen Benutzer in Skype for Business Server 2019 und einem Benutzer auf der Legacy Installation. Testen Sie Instant Messaging (im), Anwesenheitsinformationen, Audio/Video (A/V) und Desktopfreigabe.
    
- Benutzer jedes öffentlichen Chat Dienstanbieters, die von Ihrer Organisation unterstützt werden (und für die Bereitstellung abgeschlossen wurde), die mit einem Benutzer in Skype for Business Server 2019 und einem Benutzer auf der Legacy Installation kommunizieren. 
    
- Überprüfen Sie, ob anonyme Benutzer an Konferenzen teilnehmen können.
    
- Ein Benutzer, der auf der Legacy Installation mit einem Benutzer in Skype for Business Server 2019 und einem Benutzer auf der Legacy Installation unter Verwendung des Remotebenutzerzugriffs (Protokollierung von lync Server/Skype for Business außerhalb des Intranets, aber ohne VPN) gehostet wird. Testen Sie Chat, Anwesenheit, A/V und Desktopfreigabe.
    
- Ein Benutzer, der auf Skype for Business Server 2019 mit dem Remotebenutzerzugriff (Anmeldung bei Skype for Business Server 2019 von außerhalb des Intranets, aber ohne VPN) mit einem Benutzer in Skype for Business Server 2019 und einem Benutzer auf der Legacy Installation gehostet wird. Testen Sie Chat, Anwesenheit, A/V und Desktopfreigabe.
    

