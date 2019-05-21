---
title: Bereitstellungsprozess für die Gruppenanruf Abholung in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
description: Bereitstellungsprozess und Schritte für die Gruppenanruf Abholung in Skype for Business Server Enterprise-VoIP
ms.openlocfilehash: f493c3c83f3fa703dd5f62989f4f2e444e83ed5d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289924"
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>Bereitstellungsprozess für die Gruppenanruf Abholung in Skype for Business
 
Bereitstellungsprozess und Schritte für die Gruppenanruf Abholung in Skype for Business Server Enterprise-VoIP
  
Mit der Gruppenanruf Abholung können Benutzer eingehende Anrufe an Ihre Kollegen über ihre eigenen Telefone annehmen. 
  
 Die Komponenten, die von der Gruppenanruf Abholung verwendet werden, werden beim Bereitstellen von Enterprise-VoIP automatisch auf dem Front-End-Server oder Standard Edition-Server installiert und aktiviert. Sie müssen jedoch die folgenden Schritte ausführen, um die Gruppenanruf Abholung zu konfigurieren, bevor Sie für die Benutzer verfügbar ist.
  
**Bereitstellungsprozess für die Gruppenanrufannahme**

|**Phase**|**Schritte**|**Erforderliche Gruppen und Rollen**|**Bereitstellungsdokumentation**|
|:-----|:-----|:-----|:-----|
|Aktivieren des SEFAUtil-Tools in Ihrer Topologie|Verwenden Sie das Cmdlet New-CsTrustedApplicationPool zum Erstellen eines neuen vertrauenswürdigen Anwendungspools. Verwenden Sie das Cmdlet New-CsTrustedApplication, um das SEFAUtil-Tool als vertrauenswürdige Anwendung anzugeben. Führen Sie das Cmdlet Enable-CsTopology aus, um die Topologie zu aktivieren. Wenn Sie noch nicht darüber verfügen, laden Sie die Skype for Business Server-Version des SEFAUtil-Tools von diesem Speicherort herunter, und installieren Sie Sie in dem vertrauenswürdigen Anwendungspool, den Sie in Schritt 1 erstellt haben. Überprüfen Sie, ob SEFAUtil ordnungsgemäß ausgeführt wird. Führen Sie dazu das Tool aus, um die Anrufweiterleitungseinstellungen eines Benutzers in der Bereitstellung anzuzeigen. |RTCUniversalServerAdmins  <br/> |[Bereitstellen des SEFAUtil-Tools in Skype for Business](deploy-the-sefautil-tool.md) <br/> [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[Enable-CsTopology](https://docs.microsoft.com/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [Dokumentation zu den Skype for Business Server 2015 Resource Kit-Tools](../../management-tools/resource-kit-tools.md). (Für Skype for Business Server müssen Sie die aktuelle Version des Tools verwenden, doch diese Dokumentation von lync Server 2013 gilt weiterhin.)  <br/> |
|Konfigurieren von Nummernbereichen für die Anrufannahme in der Orbittabelle für das Parken von Anrufen  <br/> |Verwenden Sie das Cmdlet **New-CSCallParkOrbit**, um Nummernbereiche für die Anrufannahme in der Orbittabelle für das Parken von Anrufen zu erstellen und den Nummernbereiche für die Anrufannahme den Typ **„GroupPickup“** zuzuweisen.  <br/> Um eine nahtlose Integration in vorhandene Wählpläne zu ermöglichen, sind Nummernbereiche in der Regel als Block virtueller Durchwahlnummern konfiguriert. Das Zuweisen von DID (Direct Inward Dialing)-Nummern als Orbitnummern in der Orbittabelle für das Parken von Anrufen wird nicht unterstützt.<br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Erstellen oder Ändern eines Gruppenanruf-Pickup-Nummernbereichs in Skype for Business](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|Zuweisen einer Anruf-Abholnummer zu Benutzern und Aktivieren der Gruppenanruf Abholung für die Benutzer  <br/> |Verwenden Sie den/enablegrouppickup-Parameter im SEFAUtil Resource Kit-Tool, um die Gruppenanruf Abholung zu aktivieren und Benutzern eine Anruf-Abholnummer zuzuweisen.  <br/> |-  <br/> |[Aktivieren der Gruppenanruf Abholung für Benutzer und Zuweisen einer Gruppennummer in Skype for Business](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|Informieren der Benutzer über die ihnen zugewiesene Nummer für die Anrufannahme und weitere relevante Nummern  <br/> |Nachdem Sie die Gruppenanrufannahme für Benutzer aktiviert haben, können Sie die Benutzer per E-Mail oder anderweitig über die Nummer für die Gruppenanrufannahme informieren. Teilen Sie den Benutzern die Gruppenanrufannahme-Nummer für alle Gruppen mit, die ggf. von ihnen überwacht werden. Da Benutzer auch Anrufe für andere Benutzer entgegennehmen können, wenn sie nicht derselben Gruppe angehören, benötigen sie möglicherweise die Gruppenanrufannahme-Nummer für mehrere Gruppen.  <br/> |-  <br/> ||
|Überprüfen der Bereitstellung Ihrer Gruppenanruf Abholung  <br/> | Testen Sie Anrufe und das Abrufen von Anrufen, um sicherzustellen, dass Ihre Konfiguration erwartungsgemäß funktioniert. Folgendes muss mindestens überprüft werden: <br/>  Rufen Sie einen für die Gruppenanrufannahme aktivierten Benutzer an, und lassen Sie einen anderen Benutzer den Anruf annehmen. Der andere Benutzer kann sich entweder in derselben oder in einer anderen Gruppe befinden, oder die Gruppenanrufannahme ist für diesen Benutzer nicht aktiviert. <br/>  Rufen Sie einen für die Gruppenanrufannahme aktivierten Benutzer an, und nehmen Sie den Anruf nicht an. <br/> |-  <br/> ||
   

