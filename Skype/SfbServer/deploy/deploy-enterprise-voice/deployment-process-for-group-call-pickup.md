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
ms.openlocfilehash: 5c89522828e5e5a0dc04ffccb0907c0a2cb8a008
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812345"
---
# <a name="deployment-process-for-group-call-pickup-in-skype-for-business"></a>Bereitstellungsprozess für die Gruppenanrufannahme in Skype for Business
 
Bereitstellungsprozess und Schritte für die Gruppenanrufannahme in Skype for Business Server Enterprise-VoIP.
  
Mit der Gruppenanrufannahme können Benutzer eingehende Anrufe an kollegen von ihren eigenen Telefonen aus entgegennahmen. 
  
 Die von der Gruppenanrufannahme verwendeten Komponenten werden automatisch auf dem Front-End-Server oder Standard Edition-Server installiert und aktiviert, wenn Sie Enterprise-VoIP. Sie müssen jedoch die folgenden Schritte ausführen, um die Gruppenanrufannahme zu konfigurieren, bevor sie für Benutzer verfügbar ist.
  
**Bereitstellungsprozess für die Gruppenanrufannahme**

|**Phase**|**Schritte**|**Erforderliche Gruppen und Rollen**|**Bereitstellungsdokumentation**|
|:-----|:-----|:-----|:-----|
|Aktivieren des Tools SEFAUtil in Ihrer Topologie|Verwenden Sie New-CsTrustedApplicationPool cmdlet, um einen neuen vertrauenswürdigen Anwendungspool zu erstellen. Verwenden Sie New-CsTrustedApplication Cmdlet, um das Tool SEFAUtil als vertrauenswürdige Anwendung anzugeben. Führen Sie Enable-CsTopology cmdlet aus, um die Topologie zu aktivieren. Wenn Sie sie noch nicht haben, laden Sie die Skype for Business Server-Version des SEFAUtil-Tools von diesem Speicherort herunter, und installieren Sie sie in dem vertrauenswürdigen Anwendungspool, den Sie in Schritt 1 erstellt haben. Stellen Sie sicher, dass SEFAUtil ordnungsgemäß ausgeführt wird, indem Sie es ausführen, um die Anruf weiterleitungseinstellungen eines Benutzers in der Bereitstellung anzeigen. |RTCUniversalServerAdmins  <br/> |[Bereitstellen des Tools SEFAUtil in Skype for Business](deploy-the-sefautil-tool.md) <br/> [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps) </br>[New-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplication?view=skype-ps)</br>[Enable-CsTopology](https://docs.microsoft.com/powershell/module/skype/enable-cstopology?view=skype-ps) <br/> [Dokumentation zu Skype for Business Server 2015 Resource Kit Tools](../../management-tools/resource-kit-tools.md). (Für Skype for Business Server müssen Sie die aktuelle Version des Tools verwenden, aber diese Dokumentation aus Lync Server 2013 gilt weiterhin.)  <br/> |
|Konfigurieren von Nummernbereichen für die Anrufannahme in der Orbittabelle für das Parken von Anrufen  <br/> |Verwenden Sie **das Cmdlet New-CSCallParkOrbit,** um Nummernbereiche für die Anrufannahme in der Orbittabelle für das Parken von Anrufen zu erstellen und den Anrufannahmebereichen den Typ **"GroupPickup" zuzuordnen.**  <br/> Für eine nahtlose Integration in vorhandene Wählpläne werden Nummernbereiche in der Regel als Block virtueller Durchwahlen konfiguriert. Das Zuweisen von Direct Inward Dialing (DID)-Nummern als Bereichsnummern in der Orbittabelle zum Parken von Anrufen wird nicht unterstützt.  <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> |[Erstellen oder Ändern eines Nummernbereichs für die Gruppenanrufannahme in Skype for Business](create-or-modify-a-group-call-pickup-number-range.md) <br/> |
|Zuweisen einer Anrufannahmenummer zu Benutzern und Aktivieren der Gruppenanrufannahme für die Benutzer  <br/> |Verwenden Sie den Parameter /enablegrouppickup im SEFAUtil Resource Kit-Tool, um die Gruppenanrufannahme zu aktivieren und benutzern eine Anrufannahmenummer zuzuordnen.  <br/> |-  <br/> |[Aktivieren der Gruppenanrufannahme für Benutzer und Zuweisen einer Gruppennummer in Skype for Business](enable-group-call-pickup-for-users-and-assign-a-group-number.md) <br/> |
|Benachrichtigen der Benutzer über ihre zugewiesene Anrufannahmenummer und eine beliebige andere Anzahl von Interesse  <br/> |Nachdem Sie die Gruppenanrufannahme für Benutzer aktiviert haben, verwenden Sie E-Mail oder einen anderen Mechanismus, um Benutzer über ihre Nummer der Anrufannahmegruppe zu informieren. Benachrichtigen Sie die Benutzer über die Nummer der Anrufannahmegruppe für jede Gruppe, die sie möglicherweise überwachen möchten. Da Benutzer Anrufe für andere Benutzer auch dann abrufen können, wenn sie sich nicht in derselben Gruppe befinden, benötigen Benutzer möglicherweise die Nummer der Anrufannahmegruppe für mehrere Gruppen.  <br/> |-  <br/> ||
|Überprüfen der Bereitstellung der Gruppenanrufannahme  <br/> | Testen Sie das Platzieren und Abrufen von Anrufen, um sicherzustellen, dass Ihre Konfiguration wie erwartet funktioniert. Überprüfen Sie mindestens Folgendes: <br/>  Rufen Sie einen Benutzer an, der für die Gruppenanrufannahme aktiviert ist, und fordern Sie einen anderen Benutzer auf, den Anruf abzurufen. Der andere Benutzer kann in derselben Gruppe, in einer anderen Gruppe oder nicht aktiviert sein. <br/>  Rufen Sie einen Benutzer an, der für die Gruppenanrufannahme aktiviert ist, und nehmen Sie den Anruf nicht an. <br/> |-  <br/> ||
   

