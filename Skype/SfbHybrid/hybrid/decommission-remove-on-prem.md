---
title: Außerbetriebsetzen von Skype for Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Anweisungen zum Außerbetriebsetzen von Skype for Business Server.
ms.openlocfilehash: 668e3d5ebf5dfa03fcfb883adcc3e08fc5924bae
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593885"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a>Entfernen Ihrer lokalen Skype for Business-Bereitstellung

In diesem Artikel wird beschrieben, wie Sie Ihre lokale Skype for Business-Bereitstellung entfernen. Dies ist Schritt 3 der folgenden Schritte zum Außerbetriebsetzen Ihrer lokalen Umgebung:

- Schritt 1. [Verschieben Sie alle erforderlichen Benutzer und Anwendungsendpunkte von lokal in online.](decommission-move-on-prem-users.md) 

- Schritt 2. [Deaktivieren Sie Die Hybridkonfiguration](cloud-consolidation-disabling-hybrid.md).

- **Schritt 3. Entfernen Sie Ihre lokale Skype for Business-Bereitstellung.** (Dieser Artikel)


> [!IMPORTANT] 
> Die Schritte in diesem Artikel gelten nur, wenn Sie Methode 2 zum Verwalten von Benutzerattributen verwenden, wie hier [beschrieben.](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory) Wenn Sie Methode 1 verwenden, verwenden Sie nicht die in diesem Artikel beschriebenen Schritte, um Ihre Skype for Business-Server zu entfernen. Stattdessen können Sie die Server neu abbilden.

Zum Ausführen der Schritte in diesem Artikel benötigen Sie Berechtigungen sowohl für die Gruppe Schemaadministratoren als auch für die Gruppe "Enterprise-Admin". Sie benötigen diese Berechtigungen, um das Skype for Business Server-Schema und Änderungen auf Gesamtstrukturebene an Active Directory-Domänendienste rückgängig zu machen. Sie müssen auch Mitglied der Gruppe "RTCUniversalServerAdmins" sein.


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a>Vorbereiten des Entfernens der Skype for Business-Bereitstellung

Nachdem Sie alle erforderlichen Benutzerkonten in die Cloud verschieben, sind möglicherweise noch einige lokale Objekte wie Kontakte und Anwendungen übrig, die Sie bereinigen müssen.

Verwenden Sie die folgenden Schritte, um diese Objekte zu bereinigen, und stellen Sie sicher, dass Sie Mitglied der Gruppe Lokaler Administrator und der Gruppe RTCUniversalServerAdmins sind. Beachten Sie, dass ExUmContacts und PersistantChatEndPoints in Skype for Business Server 2019 nicht verfügbar sind. Wenn Sie Skype for Business Server 2019 verwenden, sollten die entsprechenden Cmdlets in den folgenden Schritten nicht angegeben werden.

1. Führen Sie die folgenden Skype for Business Server PowerShell-Cmdlets aus, um zu überprüfen, ob kontakte oder Anwendungen der lokalen Skype for Business Server-Bereitstellung zugeordnet sind.

   ```PowerShell
   Get-CsMeetingRoom
   Get-CsCommonAreaPhone
   Get-CsAnalogDevice
   Get-CsExUmContact
   Get-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication
   Get-CsPersistentChatEndpoint
   Get-CsAudioTestServiceApplication
   Get-CsCallParkOrbit
   ```
2. Überprüfen Sie die Ausgabelisten der Cmdlets in Schritt 1. Wenn Objekte entfernt werden können, führen Sie die folgenden Skype for Business Server PowerShell-Cmdlets aus:

   ```PowerShell
   Get-CsMeetingRoom | Disable-CsMeetingRoom
   Get-CsCommonAreaPhone | Remove-CsCommonAreaPhone 
   Get-CsAnalogDevice | Remove-CsAnalogDevice
   Get-CsExUmContact | Remove-CsExUmContact
   Get-CsDialInConferencingAccessNumber | Remove-CsDialInConferencingAccessNumber
   Get-CsRgsWorkflow | Remove-CsRgsWorkflow
   Get-CsTrustedApplicationEndpoint | Remove-CsTrustedApplicationEndpoint
   Get-CsTrustedApplication | Remove-CsTrustedApplication -Force
   Get-CsPersistentChatEndpoint |  Remove-CsPersistentChatEndpoint
   Get-CsCallParkOrbit | Remove-CsCallParkOrbit -Force
   Get-CsVoiceRoute | Remove-CsVoiceRoute -Force
   ```
## <a name="remove-your-on-premises-skype-for-business-deployment"></a>Entfernen Ihrer lokalen Skype for Business-Bereitstellung

Nachdem Sie alle vorbereitenden Schritte abgeschlossen haben, können Sie die Skype for Business-Bereitstellung entfernen, indem Sie die folgenden Schritte ausführen:

1. Entfernen Sie die Skype for Business Server-Bereitstellung logisch, mit Ausnahme eines einzelnen Front-Ends wie folgt:

   a. Aktualisieren Sie Ihre Skype for Business Server-Topologie so, dass sie über einen einzelnen Front-End-Pool verfügen:

     - Laden Sie im Topologie-Generator eine neue Kopie herunter, und navigieren Sie zum Frontend-Pool.
     - Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie auf **Eigenschaften bearbeiten**.
     - Deaktivieren **Sie in Zuordnungen** die Option **Edgepool zuordnen** (für Medienkomponenten), und klicken Sie auf **OK**.
     - Wenn mehrere FrontendPools zur Verfügung stehen, entfernen Sie Zuordnungen für alle verbleibenden Pools.
     - Wählen **Sie Aktion > Bereitstellung entfernen aus.**
     - Wählen **Sie Aktion > Topologie veröffentlichen aus.**

    b. Führen Sie nach der Veröffentlichung der Topologie die im Assistenten beschriebenen zusätzlichen Schritte aus.

2. Entfernen Sie Skype for Business Server-Konferenzverzeichnissen, indem Sie das folgende Skype for Business Server PowerShell-Cmdlet ausführen:

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. Finalize the uninstall of your Skype for Business Server deployment by running the following Skype for Business Server PowerShell cmdlet:

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > Wenn dieser Schritt einen Fehler zurückgibt, öffnen Sie bitte ein Microsoft-Supportticket, um Hilfe beim Entfernen der verbleibenden veralteten Objekte zu erhalten.

4. Entfernen Sie den zentralen Verwaltungsspeicher-Dienststeuerungspunkt, indem Sie das folgende Skype for Business Server PowerShell-Cmdlet ausführen:

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. Rückgängig machen Sie Änderungen auf Gesamtstrukturebene von Skype for Business Server Active Directory Domain, indem Sie das folgende Skype for Business Server PowerShell-Cmdlet ausführen:

   ```PowerShell
   Disable-CsAdDomain
   ```
6. Rückgängig machen Sie Änderungen des Active Directory-Domänenschemas von Skype for Business Server, indem Sie das folgende Skype for Business Server PowerShell-Cmdlet ausführen:

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a>Siehe auch

- [Außerbetriebsetzen Ihrer lokalen Skype for Business-Umgebung](decommission-on-prem-overview.md)

- [Verschieben von Benutzern und Endpunkten in die Cloud](decommission-move-on-prem-users.md)

- [Deaktivieren der Hybridkonfiguration](cloud-consolidation-disabling-hybrid.md)














