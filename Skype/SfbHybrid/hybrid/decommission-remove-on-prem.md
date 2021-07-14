---
title: Außerbetriebnahme Skype for Business Server
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
description: Anweisungen für die Außerbetriebnahme Skype for Business Server.
ms.openlocfilehash: a69ba2d9a3bbdce8bee342c3554b758138ad1d87
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420790"
---
# <a name="remove-your-on-premises-skype-for-business-deployment"></a>Entfernen Ihrer lokalen Skype for Business-Bereitstellung

In diesem Artikel wird beschrieben, wie Sie Ihre lokale Skype for Business Bereitstellung entfernen. Dies ist Schritt 4 der folgenden Schritte zum Außerbetriebsetzen Ihrer lokalen Umgebung:

- Schritt 1. [Verschieben Sie alle erforderlichen Benutzer aus der lokalen Umgebung in die Onlineumgebung.](decommission-move-on-prem-users.md) 

- Schritt 2. [Deaktivieren Sie Ihre Hybridkonfiguration.](cloud-consolidation-disabling-hybrid.md)

- Schritt 3: [Migrieren von Hybridanwendungsendpunkten von der lokalen Umgebung zur Onlinebereitstellung](decommission-move-on-prem-endpoints.md)

- **Schritt 4. Entfernen Sie Ihre lokale Skype for Business Bereitstellung.** (Dieser Artikel)


> [!IMPORTANT] 
> Die Schritte in diesem Artikel gelten nur, wenn Sie Methode 2 zum Verwalten von Benutzerattributen verwenden, wie [hier](cloud-consolidation-disabling-hybrid.md#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory)beschrieben. Wenn Sie Methode 1 verwenden, verwenden Sie nicht die in diesem Artikel beschriebenen Schritte, um Ihre Skype for Business Server zu entfernen. Stattdessen können Sie die Server neu abbilden.

Zum Ausführen der Schritte in diesem Artikel benötigen Sie Berechtigungen sowohl für die Gruppe "Schemaadministratoren" als auch für die Gruppe "Enterprise-Administrator". Sie benötigen diese Berechtigungen, um das Skype for Business Server Schema und Änderungen auf Gesamtstrukturebene an Active Directory Domain Services rückgängig zu machen. Sie müssen auch Mitglied der Gruppe "RTCUniversalServerAdmins" sein.


## <a name="prepare-to-remove-the-skype-for-business-deployment"></a>Vorbereiten des Entfernens der Skype for Business Bereitstellung

Nachdem Sie alle erforderlichen Benutzerkonten in die Cloud verschoben haben, sind möglicherweise noch einige lokale Objekte wie Kontakte und Anwendungen vorhanden, die Sie bereinigen müssen.

Führen Sie die folgenden Schritte aus, um diese Objekte zu bereinigen, und stellen Sie sicher, dass Sie mitglied der Gruppe "Lokaler Administrator" und der Gruppe "RTCUniversalServerAdmins" sind. Beachten Sie, dass ExUmContacts und PersistantChatEndPoints in Skype for Business Server 2019 nicht verfügbar sind. Wenn Sie Skype for Business Server 2019 haben, sollten die entsprechenden Cmdlets in den folgenden Schritten weggelassen werden.

1. Führen Sie die folgenden Skype for Business Server PowerShell-Cmdlets aus, um zu überprüfen, ob kontakte oder Anwendungen mit der Skype for Business Server lokalen Bereitstellung verknüpft sind.

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
2. Überprüfen Sie die Ausgabelisten aus den Cmdlets in Schritt 1. Wenn Objekte entfernt werden können, führen Sie dann die folgenden Skype for Business Server PowerShell-Cmdlets aus:

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

Nach Abschluss aller vorbereitenden Schritte können Sie die Skype for Business Bereitstellung entfernen, indem Sie die folgenden Schritte ausführen:

1. Entfernen Sie die Skype for Business Server Bereitstellung logisch, mit Ausnahme eines einzelnen Front-Ends, wie folgt:

   1. Aktualisieren Sie Ihre Skype for Business Server-Topologie so, dass sie über einen einzelnen Front-End-Pool verfügt:

      1. Laden Sie im Topologie-Generator eine neue Kopie herunter, und navigieren Sie zum Frontend-Pool.
      1. Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie auf **Eigenschaften bearbeiten**.
      1. Deaktivieren Sie in **Zuordnungen** die Option **Edgepool zuordnen** (für Medienkomponenten), und klicken Sie auf **OK.**
      1. Wenn mehrere Front-End-Pools vorhanden sind, entfernen Sie Zuordnungen für alle verbleibenden Pools.
      1. Wählen Sie **"Aktion > Bereitstellung entfernen" aus.**
      1. Wählen Sie **Aktion > Topologie veröffentlichen** aus.

    1. Führen Sie nach der Veröffentlichung der Topologie die im Assistenten beschriebenen zusätzlichen Schritte aus.

2. Entfernen Sie Skype for Business Server Konferenzverzeichnisse, indem Sie das folgende Skype for Business Server PowerShell-Cmdlet ausführen:

   ```PowerShell
   Get-CsConferenceDirectory | Remove-CsConferenceDirectory -Force
   ```

3. Beenden Sie die Deinstallation Ihrer Skype for Business Server-Bereitstellung, indem Sie das folgende Skype for Business Server PowerShell-Cmdlet ausführen:

   ```PowerShell
   Publish-CsTopology -FinalizeUninstall
   ```
   > [!NOTE]
   > Wenn dieser Schritt einen Fehler zurückgibt, öffnen Sie ein Microsoft-Supportticket, um Hilfe beim Entfernen der verbleibenden veralteten Objekte zu erhalten.

4. Entfernen Sie die zentrale Verwaltung Store Dienststeuerungspunkt, indem Sie das folgende Skype for Business Server PowerShell-Cmdlet ausführen:

   ```PowerShell
   Remove-CsConfigurationStoreLocation
   ``` 

5. Rückgängigmachen Skype for Business Server Änderungen auf Active Directory-Domänenebene durch Ausführen des folgenden Skype for Business Server PowerShell-Cmdlets:

   ```PowerShell
   Disable-CsAdDomain
   ```
6. Rückgängigmachen Skype for Business Server Änderungen auf Der Active Directory-Gesamtstrukturebene durch Ausführen des folgenden Skype for Business Server PowerShell-Cmdlets:

   ```PowerShell
   Disable-CsAdForest
   ```

## <a name="see-also"></a>Siehe auch

- [Außerbetriebnahme Ihrer lokalen Skype for Business-Umgebung](decommission-on-prem-overview.md)

- [Verschieben aller erforderlichen Benutzer aus der lokalen Umgebung in die Onlineumgebung](decommission-move-on-prem-users.md)

- [Deaktivieren der Hybridkonfiguration](cloud-consolidation-disabling-hybrid.md)

- [Verschieben von Hybridanwendungsendpunkten von der lokalen Umgebung zur Onlinebereitstellung](decommission-move-on-prem-endpoints.md)

