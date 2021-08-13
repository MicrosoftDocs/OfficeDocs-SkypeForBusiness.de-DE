---
title: Konfigurieren von Richtlinien zum Steuern des Zugriffs durch Verbundbenutzer
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Wenn Sie Richtlinien zur Unterstützung der Kommunikation mit Verbundpartnern konfigurieren, gelten die Richtlinien für Benutzer von Partnerdomänen. '
ms.openlocfilehash: 57b674e0b75a310b56b6aaedaf4338eda94d75452f7f4b3d59580a4a52759453
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301391"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a>Konfigurieren von Richtlinien zum Steuern des Verbundbenutzerzugriffs in Skype for Business Server

Wenn Sie Richtlinien zur Unterstützung der Kommunikation mit Verbundpartnern konfigurieren, gelten die Richtlinien für Benutzer von Partnerdomänen. Sie können eine oder mehrere Zugriffsrichtlinien für externe Benutzer konfigurieren, um zu steuern, ob Benutzer von Verbunddomänen mit Ihren Skype for Business Server Benutzern zusammenarbeiten können. Zum Steuern des Zugriffs durch Partnerbenutzer können Sie Richtlinien auf globaler Ebene sowie Standort- und Benutzerebene konfigurieren. Skype for Business Server Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden. Prioritätenreihenfolge für Skype for Business Server-Richtlinien: Eine Benutzerrichtlinie (größter Einfluss) hat Vorrang vor einer Standortrichtlinie, und eine Standortrichtlinie wiederum hat Vorrang vor einer globalen Richtlinie (geringster Einfluss). Dies bedeutet Folgendes: Je näher sich die Richtlinieneinstellung am betroffenen Objekt befindet, umso mehr Einfluss auf das Objekt hat sie.


> [!NOTE]  
> Sie können auch dann Richtlinien zur Steuerung des Zugriffs durch Partnerbenutzer konfigurieren, wenn Sie den Partnerverbund für Ihre Organisation nicht aktiviert haben. Die von Ihnen konfigurierten Richtlinien treten jedoch erst dann in Kraft, wenn der Partnerverbund für Ihre Organisation aktiviert ist. Ausführliche Informationen zum Aktivieren des Partnerverbunds finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs.](../access-edge/enable-or-disable-remote-user-access.md)  Wenn Sie außerdem eine Benutzerrichtlinie zum Steuern des Verbundbenutzerzugriffs angeben, gilt die Richtlinie nur für Benutzer, die für Skype for Business Server aktiviert und für die Verwendung der Richtlinie konfiguriert sind.


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>So konfigurieren Sie eine Richtlinie zur Unterstützung des Zugriffs durch Benutzer von Partnerdomänen

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Richtlinie für den externen Zugriff**.

4.  Führen Sie auf der Seite **Richtlinie für den externen Zugriff** einen der folgenden Schritte aus:
    
      - Um die globale Richtlinie für die Unterstützung des Zugriffs durch Partnerbenutzer zu konfigurieren, klicken Sie auf die globale Richtlinie, dann auf **Bearbeiten** und schließlich auf **Details anzeigen**.
    
      - Klicken Sie zum Erstellen einer neuen Standortrichtlinie auf **Neu** und anschließend auf **Standortrichtlinie**. Klicken Sie im Dialogfeld **Standort auswählen** in der Liste auf den entsprechenden Standort, und klicken Sie dann auf **OK**.
    
      - Klicken Sie zum Erstellen einer neuen Benutzerrichtlinie auf **Neu** und anschließend auf **Benutzerrichtlinie**. Erstellen Sie unter **Neue Richtlinie für den externen Zugriff** einen eindeutigen Namen im Feld **Name**, der auf den Zweck der Benutzerrichtlinie hinweist (z. B. **EnableFederatedUsers** für eine Benutzerrichtlinie, welche die Kommunikation für Benutzer aus Partnerdomänen ermöglicht).
    
      - Klicken Sie zum Ändern einer vorhandenen Richtlinie in der Tabelle auf die entsprechende Richtlinie, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.

5.  (Optional) Wenn Sie eine Beschreibung hinzufügen oder bearbeiten möchten, geben Sie die Informationen zur Richtlinie unter **Beschreibung** an.

6.  Führen Sie einen der folgenden Schritte aus:
    
      - Aktivieren Sie das Kontrollkästchen **Kommunikation mit Partnerbenutzern aktivieren**, um den Zugriff durch Partnerbenutzer für die Richtlinie zu aktivieren.
    
      - Deaktivieren Sie das Kontrollkästchen **Kommunikation mit Partnerbenutzern aktivieren**, um den Zugriff durch Partnerbenutzer für die Richtlinie zu deaktivieren.

7.  Klicken Sie auf **Commit**.

Um den Zugriff durch Partnerbenutzer zu ermöglichen, müssen Sie auch die Unterstützung für den Partnerverbund in Ihrer Organisation aktivieren. Ausführliche Informationen finden Sie unter Aktivieren oder Deaktivieren des [Partnerverbunds und der Verbindung mit öffentlichen Chatdiensten.](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

Handelt es sich um eine Benutzerrichtlinie, müssen Sie die Richtlinie auch auf Benutzer anwenden, die mit Partnerbenutzern zusammenarbeiten sollen. Ausführliche Informationen finden Sie unter [Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer.](assign-an-external-user-access-policy.md)

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>So konfigurieren Sie eine vorhandene Richtlinie mithilfe von Windows PowerShell, um den Zugriff durch Benutzer von Verbunddomänen zu unterstützen

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Starten Sie die Skype für die Busines Server-Verwaltungsshell: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business Server** und dann auf **Skype for Business Server Verwaltungsshell.**

3.  Geben Sie Folgendes in die Skype for Business Server-Verwaltungsshell ein:
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > Der Parameter "EnablePublicCloudAudioVideoAccess" verfügt nicht über eine entsprechende Auswahl in der Skype for Business Server Systemsteuerung.


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>So erstellen Sie eine neue Richtlinie mithilfe von Windows PowerShell, um den Zugriff durch Benutzer von Verbunddomänen zu unterstützen

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **"Microsoft Skype for Business Server"** und dann auf **Skype for Business Server Verwaltungsshell.**

3.  Geben Sie Folgendes in die Skype for Business Server-Verwaltungsshell ein:
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    Nachstehend finden Sie ein Beispiel für das Erstellen einer neuen Standortrichtlinie:
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>So löschen oder setzen Sie eine Richtlinie mithilfe von Windows PowerShell zurück, um den Zugriff durch Benutzer von Verbunddomänen zu unterstützen

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Geben Sie Folgendes in die Skype for Business Server-Verwaltungsshell ein.
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    Nachstehend finden Sie ein Beispiel für das Zurücksetzen der globalen Richtlinie (die Einstellungen der globalen Richtlinie können zwar entfernt, die Richtlinie selbst kann jedoch nicht gelöscht werden):
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    Geben Sie den folgenden Befehl ein, um eine Standortrichtlinie zu löschen:
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    Mit diesem Befehl wird die Standortrichtlinie "Redmond" gelöscht. Geben Sie den folgenden Befehl ein, um die Richtlinie "UserEAPPolicy" zu löschen:
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a>Siehe auch


[Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[Zuweisen einer Richtlinie für den Zugriff durch externe Benutzer](assign-an-external-user-access-policy.md)

[Verwalten von SIP-Partnerdomänen für eine Organisation](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[Verwalten von SIP-Partnerverbundanbietern für eine Organisation](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[Set-CsExternalAccessPolicy](/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](/powershell/module/skype/Grant-CsExternalAccessPolicy)  
