---
title: Bereitstellungsprozess für die Gruppe aufrufen Pickup-in Skype für Unternehmen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
description: Bereitstellungsprozess und Schritte für die Gruppe aufrufen Pickup-in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 92dbb6ef4a96ed4972794a61814abcd31586ffb3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223062"
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>Bereitstellungsprozess für die Gruppe aufrufen Pickup-in Skype für Unternehmen
 
Bereitstellungsprozess und Schritte für die Gruppe aufrufen Pickup-in Skype für Business Server Enterprise-VoIP.
  
Gruppe aufrufen Pickup-ermöglicht Benutzern, eingehende Anrufe an ihre Kollegen aus ihrer eigenen Telefone zu beantworten. 
  
 Die Komponenten, die die Gruppe aufrufen Pickup-verwendet sind automatisch installiert und bei der Bereitstellung von Enterprise-VoIP auf dem Front-End-Server oder Standard Edition-Server aktiviert. Allerdings müssen Sie die folgenden Schritte verwenden, Gruppe aufrufen Pickup-konfigurieren, bevor es für Benutzer verfügbar ist.
  
**Bereitstellungsprozess für die Gruppenanrufannahme**

|**Phase**|**Schritte**|**Erforderliche Gruppen und Rollen**|**Bereitstellungsdokumentation**|
|:-----|:-----|:-----|:-----|
|Aktivieren Sie das Tool SEFAUtil in Ihrer Topologie|Verwenden Sie das Cmdlet "New-CsTrustedApplicationPool", um einen neuen vertrauenswürdigen Anwendungspool zu erstellen. Verwenden Sie das Cmdlet "New-CsTrustedApplication", um das Tool SEFAUtil als vertrauenswürdige Anwendung anzugeben. Führen Sie das Cmdlet Enable-CsTopology, um die Topologie zu aktivieren. Wenn Sie bereits besitzen, herunterladen Sie der Skype für Business Server-Version des Tools SEFAUtil aus diesem Speicherort und installieren Sie es auf den vertrauenswürdigen Anwendungspool, den Sie in Schritt 1 erstellt haben. Überprüfen Sie, ob SEFAUtil ordnungsgemäß ausgeführt wird. Führen Sie dazu das Tool aus, um die Anrufweiterleitungseinstellungen eines Benutzers in der Bereitstellung anzuzeigen. |RTCUniversalServerAdmins  <br/> |[Das Tool SEFAUtil in Skype für Unternehmen bereitstellen](deploy-the-sefautil-tool.md) <br/> [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[Enable-CsTopology](https://docs.microsoft.com/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [Skype für Business Server 2015 Resource Kit Tools-Dokumentation](../../management-tools/resource-kit-tools.md). (Für Skype für Business Server müssen Sie die aktuelle Version des Tools verwenden, aber weiterhin gilt dieser Dokumentation von Lync Server 2013).  <br/> |
|Konfigurieren von Nummernbereichen für die Anrufannahme in der Orbittabelle für das Parken von Anrufen  <br/> |Verwenden Sie das Cmdlet **New-CSCallParkOrbit**, um Nummernbereiche für die Anrufannahme in der Orbittabelle für das Parken von Anrufen zu erstellen und den Nummernbereiche für die Anrufannahme den Typ **„GroupPickup“** zuzuweisen.  <br/> Um eine nahtlose Integration in vorhandene Wählpläne zu ermöglichen, sind Nummernbereiche in der Regel als Block virtueller Durchwahlnummern konfiguriert. Das Zuweisen von DID (Direct Inward Dialing)-Nummern als Orbitnummern in der Orbittabelle für das Parken von Anrufen wird nicht unterstützt.<br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Erstellen oder Ändern eines Gruppe anrufen Pickup-Nummernbereichs in Skype für Unternehmen](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|Weisen Sie eine pickup Wählen einer Nummer Benutzern zu, und aktivieren Sie Gruppe aufrufen Pickup-für die Benutzer  <br/> |Verwenden Sie den Parameter /enablegrouppickup in SEFAUtil Resource Kit-Tool, aktivieren Gruppe aufrufen Pickup-und Zuweisen einer pickup Wählen einer Nummer für Benutzer.  <br/> |-  <br/> |[Aktivieren Sie Gruppe aufrufen Pickup-für Benutzer, und weisen Sie eine Gruppe Zahl in Skype für Unternehmen](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|Informieren der Benutzer über die ihnen zugewiesene Nummer für die Anrufannahme und weitere relevante Nummern  <br/> |Nachdem Sie die Gruppenanrufannahme für Benutzer aktiviert haben, können Sie die Benutzer per E-Mail oder anderweitig über die Nummer für die Gruppenanrufannahme informieren. Teilen Sie den Benutzern die Gruppenanrufannahme-Nummer für alle Gruppen mit, die ggf. von ihnen überwacht werden. Da Benutzer auch Anrufe für andere Benutzer entgegennehmen können, wenn sie nicht derselben Gruppe angehören, benötigen sie möglicherweise die Gruppenanrufannahme-Nummer für mehrere Gruppen.  <br/> |-  <br/> ||
|Überprüfen der Gruppe anrufen Pickup-bereitstellungs  <br/> | Testen Sie Anrufe und das Abrufen von Anrufen, um sicherzustellen, dass Ihre Konfiguration erwartungsgemäß funktioniert. Folgendes muss mindestens überprüft werden: <br/>  Rufen Sie einen für die Gruppenanrufannahme aktivierten Benutzer an, und lassen Sie einen anderen Benutzer den Anruf annehmen. Der andere Benutzer kann sich entweder in derselben oder in einer anderen Gruppe befinden, oder die Gruppenanrufannahme ist für diesen Benutzer nicht aktiviert. <br/>  Rufen Sie einen für die Gruppenanrufannahme aktivierten Benutzer an, und nehmen Sie den Anruf nicht an. <br/> |-  <br/> ||
   

