---
title: Bereitstellungsprozess für die Gruppenanrufannahme in Skype for Business
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
description: Bereitstellungsprozess und Schritte für die Gruppenanrufannahme in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 0694975515286920344ce2f21ef7ad1f0ab64242
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60775765"
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>Bereitstellungsprozess für die Gruppenanrufannahme in Skype for Business
 
Bereitstellungsprozess und Schritte für die Gruppenanrufannahme in Skype for Business Server Enterprise-VoIP.
  
Mit der Gruppenanrufannahme können Benutzer eingehende Anrufe an ihre Kollegen von ihren eigenen Telefonen aus annehmen. 
  
 Die von der Gruppenanrufannahme verwendeten Komponenten werden automatisch auf dem Front-End-Server oder Standard Edition-Server installiert und aktiviert, wenn Sie Enterprise-VoIP bereitstellen. Sie müssen jedoch die folgenden Schritte ausführen, um die Gruppenanrufannahme zu konfigurieren, bevor sie benutzern zur Verfügung steht.
  
**Bereitstellungsprozess für die Gruppenanrufannahme**

|**Phase**|**Schritte**|**Erforderliche Gruppen und Rollen**|**Bereitstellungsdokumentation**|
|:-----|:-----|:-----|:-----|
|Aktivieren des SEFAUtil-Tools in Ihrer Topologie|Verwenden Sie das Cmdlet New-CsTrustedApplicationPool, um einen neuen vertrauenswürdigen Anwendungspool zu erstellen. Verwenden Sie das Cmdlet New-CsTrustedApplication, um das SEFAUtil-Tool als vertrauenswürdige Anwendung anzugeben. Führen Sie das Cmdlet Enable-CsTopology aus, um die Topologie zu aktivieren. Wenn sie noch nicht vorhanden ist, laden Sie die Skype for Business Server Version des SEFAUtil-Tools von diesem Speicherort herunter, und installieren Sie sie in dem vertrauenswürdigen Anwendungspool, den Sie in Schritt 1 erstellt haben. Stellen Sie sicher, dass SEFAUtil ordnungsgemäß ausgeführt wird, indem Sie es ausführen, um die Anrufweiterleitungseinstellungen eines Benutzers in der Bereitstellung anzuzeigen. |RTCUniversalServerAdmins  <br/> |[Bereitstellen des SEFAUtil-Tools in Skype for Business](deploy-the-sefautil-tool.md) <br/> [New-CsTrustedApplicationPool](/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[New-CsTrustedApplication](/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[Enable-CsTopology](/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [Skype for Business Server 2015 Resource Kit Tools Documentation](../../management-tools/resource-kit-tools.md). (For Skype for Business Server you must use the current version of the tool, but this documentation from Lync Server 2013 still applies.)  <br/> |
|Konfigurieren von Nummernbereichen für die Anrufannahme in der Orbittabelle für das Parken von Anrufen  <br/> |Verwenden Sie das Cmdlet **"New-CSCallParkOrbit",** um Nummernbereiche für die Anrufannahme in der Orbittabelle für das Parken von Anrufen zu erstellen und den Anrufannahmebereichen den Typ **"GroupPickup"** zuzuweisen.  <br/> Für die nahtlose Integration in vorhandene Wählpläne werden Nummernbereiche in der Regel als Block virtueller Erweiterungen konfiguriert. Das Zuweisen von DID-Nummern (Direct Inward Dialing) als Bereichsnummern in der Orbittabelle für das Parken von Anrufen wird nicht unterstützt.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Erstellen oder Ändern eines Nummernbereichs für die Gruppenanrufannahme in Skype for Business](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|Zuweisen einer Anrufannahmenummer zu Benutzern und Aktivieren der Gruppenanrufannahme für die Benutzer  <br/> |Verwenden Sie den Parameter "/enablegrouppickup" im SEFAUtil-Ressourcenkit-Tool, um die Gruppenanrufannahme zu aktivieren und Benutzern eine Anrufannahmenummer zuzuweisen.  <br/> |-  <br/> |[Aktivieren der Gruppenanrufannahme für Benutzer und Zuweisen einer Gruppennummer in Skype for Business](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|Benachrichtigen der Benutzer über ihre zugewiesene Anrufannahmenummer und eine beliebige andere Anzahl von Interesse  <br/> |Nachdem Sie die Gruppenanrufannahme für Benutzer aktiviert haben, verwenden Sie E-Mails oder einen anderen Mechanismus, um Benutzer über ihre Gruppennummer für die Anrufannahme zu informieren. Benachrichtigen Sie die Benutzer über die Nummer der Anrufannahmegruppe für jede Gruppe, die sie möglicherweise überwachen möchten. Da Benutzer Anrufe für andere Benutzer auch dann abrufen können, wenn sie sich nicht in derselben Gruppe befinden, benötigen Benutzer möglicherweise die Nummer der Anrufannahmegruppe für mehrere Gruppen.  <br/> |-  <br/> ||
|Überprüfen der Bereitstellung der Gruppenanrufannahme  <br/> | Testen Sie das Platzieren und Abrufen von Anrufen, um sicherzustellen, dass Ihre Konfiguration wie erwartet funktioniert. Überprüfen Sie mindestens Folgendes: <br/>  Rufen Sie einen Benutzer an, der für die Gruppenanrufannahme aktiviert ist, und lassen Sie den Anruf von einem anderen Benutzer abrufen. Der andere Benutzer kann sich in derselben Gruppe, in einer anderen Gruppe befinden oder die Gruppenanrufannahme nicht aktiviert haben. <br/>  Rufen Sie einen Benutzer an, der für die Gruppenanrufannahme aktiviert ist und den Anruf nicht entgegennimmt. <br/> |-  <br/> ||
