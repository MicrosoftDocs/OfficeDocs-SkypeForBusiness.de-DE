---
title: Bereitstellungsprozess für die Gruppenanrufannahme in Skype for Business
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 082daeac-e667-4e2d-b78d-8e0901f9f0e9
description: Bereitstellungsprozess und Schritte für die Gruppenanrufannahme in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 44f161b72661bb6bdaf52c88448df23546439be1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105791"
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>Bereitstellungsprozess für die Gruppenanrufannahme in Skype for Business
 
Bereitstellungsprozess und Schritte für die Gruppenanrufannahme in Skype for Business Server Enterprise-VoIP.
  
Mit der Gruppenanrufannahme können Benutzer eingehende Anrufe an kollegen von ihren eigenen Telefonen entgegennahmen. 
  
 Die von der Gruppenanrufannahme verwendeten Komponenten werden automatisch auf dem Front-End- oder Standard Edition-Server installiert und aktiviert, wenn Sie Enterprise-VoIP. Sie müssen jedoch die folgenden Schritte ausführen, um die Gruppenanrufannahme zu konfigurieren, bevor sie benutzern zur Verfügung steht.
  
**Bereitstellungsprozess für die Gruppenanrufannahme**

|**Phase**|**Schritte**|**Erforderliche Gruppen und Rollen**|**Bereitstellungsdokumentation**|
|:-----|:-----|:-----|:-----|
|Aktivieren des SEFAUtil-Tools in Ihrer Topologie|Verwenden Sie New-CsTrustedApplicationPool cmdlet, um einen neuen vertrauenswürdigen Anwendungspool zu erstellen. Verwenden Sie New-CsTrustedApplication cmdlet, um das SEFAUtil-Tool als vertrauenswürdige Anwendung anzugeben. Führen Sie Enable-CsTopology cmdlet aus, um die Topologie zu aktivieren. Wenn sie noch nicht vorhanden ist, laden Sie die Skype for Business Server-Version des SEFAUtil-Tools von diesem Speicherort herunter, und installieren Sie sie im vertrauenswürdigen Anwendungspool, den Sie in Schritt 1 erstellt haben. Stellen Sie sicher, dass SEFAUtil ordnungsgemäß ausgeführt wird, indem Sie es ausführen, um die Anruf weiterleitungseinstellungen eines Benutzers in der Bereitstellung anzeigen zu können. |RTCUniversalServerAdmins  <br/> |[Bereitstellen des SEFAUtil-Tools in Skype for Business](deploy-the-sefautil-tool.md) <br/> [New-CsTrustedApplicationPool](/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[New-CsTrustedApplication](/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[Enable-CsTopology](/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [Dokumentation zu Skype for Business Server 2015 Resource Kit Tools](../../management-tools/resource-kit-tools.md). (Für Skype for Business Server müssen Sie die aktuelle Version des Tools verwenden, diese Dokumentation aus Lync Server 2013 gilt jedoch weiterhin.)  <br/> |
|Konfigurieren von Anrufannahmenummerbereichen in der Orbittabelle zum Parken von Anrufen  <br/> |Verwenden Sie **das Cmdlet New-CSCallParkOrbit,** um Anrufannahmenummerbereiche in der Orbittabelle zum Parken von Anrufen zu erstellen, und weisen Sie den Anrufannahmebereichen den Typ **GroupPickup zu.**  <br/> Für eine nahtlose Integration in vorhandene Wählpläne werden Nummernbereiche in der Regel als Block virtueller Durchwahlen konfiguriert. Das Zuweisen von Direktwahlnummern (Direct Inward Dialing, DID) als Bereichsnummern in der Orbittabelle zum Parken von Anrufen wird nicht unterstützt.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Erstellen oder Ändern eines Gruppenanrufannahmenummerbereichs in Skype for Business](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|Zuweisen einer Anrufannahmenummer zu Benutzern und Aktivieren der Gruppenanrufannahme für die Benutzer  <br/> |Verwenden Sie den Parameter /enablegrouppickup im SEFAUtil-Ressourcenkit-Tool, um die Gruppenanrufannahme zu aktivieren und benutzern eine Anrufannahmenummer zuzuordnen.  <br/> |-  <br/> |[Aktivieren der Gruppenanrufannahme für Benutzer und Zuweisen einer Gruppennummer in Skype for Business](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|Benachrichtigen von Benutzern über ihre zugewiesene Anrufannahmenummer und jede andere Anzahl von Interesse  <br/> |Nachdem Sie die Gruppenanrufannahme für Benutzer aktiviert haben, verwenden Sie E-Mails oder einen anderen Mechanismus, um Benutzer über ihre Telefonnummer für die Anrufannahmegruppe zu informieren. Benachrichtigen Sie Die Benutzer über die Nummer der Anrufannahmegruppe für jede Gruppe, die sie möglicherweise überwachen möchten. Da Benutzer Anrufe für andere Benutzer auch dann abrufen können, wenn sie sich nicht in derselben Gruppe befinden, benötigen Benutzer möglicherweise die Nummer der Anrufannahmegruppe für mehrere Gruppen.  <br/> |-  <br/> ||
|Überprüfen der Bereitstellung der Gruppenanrufannahme  <br/> | Testen Sie das Platzieren und Abrufen von Anrufen, um sicherzustellen, dass Ihre Konfiguration wie erwartet funktioniert. Überprüfen Sie mindestens Folgendes: <br/>  Rufen Sie einen Benutzer auf, der für die Gruppenanrufannahme aktiviert ist, und fordern Sie einen anderen Benutzer auf, den Anruf abzurufen. Der andere Benutzer kann in derselben Gruppe, in einer anderen Gruppe oder nicht aktiviert sein. <br/>  Rufen Sie einen Benutzer an, der für die Gruppenanrufannahme aktiviert ist, und nehmen Sie den Anruf nicht an. <br/> |-  <br/> ||
